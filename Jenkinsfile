pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }

        stage('Delete Folder') {
            steps {
                script {
                    // Caminho da pasta a ser apagada
                    def folderPath = 'C:\\Users\\adriano.oliveira\\Downloads\\arquivoparaexcluir'

                    // Apagar a pasta
                    bat "rmdir /s /q \"${folderPath}\""
                }
            }
        }

        stage('Copy New Folder') {
            steps {
                script {
                    // Caminho do local de origem da nova pasta
                    def sourceFolder = 'C:\\arquivoparaexcluir'

                    // Caminho de destino onde a pasta foi deletada
                    def destinationFolder = 'C:\\Users\\adriano.oliveira\\Downloads\\arquivoparaexcluir'

                    // Copiar a nova pasta para o local onde a pasta foi excluída
                    bat "xcopy /E /I /H /Y \"${sourceFolder}\" \"${destinationFolder}\""
                }
            }
        }
    }
}
