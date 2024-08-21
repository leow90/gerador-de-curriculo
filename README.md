<!DOCTYPE html>

<html lang="pt-br">

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Gerador de Currículo</title>

    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">

    <style>

        body {

            background-color: #f8f9fa;

        }



        h1 {

            margin-bottom: 20px;

        }



        .form-group {

            margin-bottom: 15px;

        }



        #add-experience {

            margin-top: 15px;

        }



        #experience-section h3 {

            margin-top: 20px;

        }

    </style>

</head>

<body>

    <div class="container mt-5">

        <h1 class="text-center">Gerador de Currículo</h1>



        <?php if ($_SERVER['REQUEST_METHOD'] == 'POST'): ?>

            <?php

                // Processando os dados do formulário

                $name = htmlspecialchars($_POST['name']);

                $dob = htmlspecialchars($_POST['dob']);

                $age = htmlspecialchars($_POST['age']);

                $email = htmlspecialchars($_POST['email']);

                $phone = htmlspecialchars($_POST['phone']);

                $companies = $_POST['company'];

                $roles = $_POST['role'];

                $durations = $_POST['duration'];

            ?>



            <div class="container mt-5">

                <h2 class="text-center"> <?php echo $name; ?></h2>

                <hr>

                <h3></h3>

                <p><strong></strong> <?php echo $name; ?></p>

                <p><strong></strong> <?php echo $dob; ?></p>

                <p><strong></strong> <?php echo $age; ?></p>

                <p><strong></strong> <?php echo $email; ?></p>

                <p><strong></strong> <?php echo $phone; ?></p>



                <h3></h3>

                <?php foreach ($companies as $index =>

                    <div class="experience-entry">

                        <h4><?php echo htmlspecialchars($company); ?></h4>

                        <p><strong></strong> <?php echo htmlspecialchars($roles[$index]); ?></p>

                        <p><strong></strong> <?php echo htmlspecialchars($durations[$index]); ?></p>

                        <hr>

                    </div>

                <?php endforeach; ?>

            </div>



            <script>

                window.print();

            </script>



        <?php else: ?>

            <!-- Formulário para entrada de dados -->

            <form action="" method="POST">

                <div class="form-group">

                    <label for="name">Nome Completo</label>

                    <input type="text" class="form-control" id="name" name="name" required>

                </div>

                <div class="form-group">

                    <label for="dob">Data de Nascimento</label>

                    <input type="date" class="form-control" id="dob" name="dob" required>

                </div>

                <div class="form-group">

                    <label for="age">Idade</label>

                    <input type="number" class="form-control" id="age" name="age" required>

                </div>

                <div class="form-group">

                    <label for="email">Email</label>

                    <input type="email" class="form-control" id="email" name="email" required>

                </div>

                <div class="form-group">

                    <label for="phone">Telefone</label>

                    <input type="text" class="form-control" id="phone" name="phone" required>

                </div>

                

                <div id="experience-section">

                    <h3>Experiências Profissionais</h3>

                    <div class="experience-entry">

                        <div class="form-group">

                            <label for="company[]">Empresa</label>

                            <input type="text" class="form-control" name="company[]" required>

                        </div>

                        <div class="form-group">

                            <label for="role[]">Cargo</label>

                            <input type="text" class="form-control" name="role[]" required>

                        </div>

                        <div class="form-group">

                            <label for="duration[]">Duração</label>

                            <input type="text" class="form-control" name="duration[]" required>

                        </div>

                    </div>

                </div>

                <button type="button" id="add-experience" class="btn btn-secondary">+ Adicionar Experiência</button>

                <br><br>

                <button type="submit" class="btn btn-primary">Gerar Currículo</button>

            </form>

        <?php endif; ?>

    </div>



    <script src="https://code.jquery.com/jquery-3.5.1.min.js"></script>

    <script>

        $(document).ready(function() {

            $('#add-experience').click(function() {

                var newExperience = `

                    <div class="experience-entry">

                        <div class="form-group">

                            <label for="company[]">Empresa</label>

                            <input type="text" class="form-control" name="company[]" required>

                        </div>

                        <div class="form-group">

                            <label for="role[]">Cargo</label>

                            <input type="text" class="form-control" name="role[]" required>

                        </div>

                        <div class="form-group">

                            <label for="duration[]">Duração</label>

                            <input type="text" class="form-control" name="duration[]" required>

                        </div>

                    </div>`;

                $('#experience-section').append(newExperience);

            });

        });

    </script>

</body>

</html>
