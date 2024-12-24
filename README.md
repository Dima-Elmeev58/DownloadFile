# DownloadFile
class Program 
{
    static void Main(string[] args) 
    {
        using (WebClient wc = new WebClient()) // Создаем объект WebClient для загрузки файлов, используем блок using для автоматического освобождения ресурсов.
        {
            string file = "https://vscode.ru/filesForArticles/test.docx"; // URL файла, который нужно скачать.
            string folder = @"C:\Users\revno\Doc\SaveFile\"; // Путь к папке, где будет сохранен файл.
            string name = "test1.docx"; // Имя, под которым будет сохранен скачанный файл.
            
            try // Начинаем блок try для перехвата исключений.
            {
                wc.DownloadFile(file, folder + name); // Скачиваем файл по указанному URL и сохраняем его в указанной папке с заданным именем.
                Console.WriteLine("Файл загружен " + folder + name); // Выводим сообщение о том, что файл успешно скачан.
            }
            catch (Exception ex) // Перехватываем исключения, если они возникли в блоке try.
            {
                Console.WriteLine("Ошибка: " + ex.Message); // Выводим сообщение об ошибке, если произошла ошибка при скачивании файла.
            }
        } 
    } 
} 
