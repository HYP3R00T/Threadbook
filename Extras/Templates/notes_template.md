<%*
let fileName = tp.file.title; // Get the current file title
if (!fileName || fileName === "Untitled") {
// If the file is created manually (Ctrl + N), prompt for the file name
if (tp.config.target_file.basename === "Untitled") {
fileName = await tp.system.prompt("Enter the file name:");
} else {
// If created via wikilink, use the target file name directly
fileName = tp.config.target_file;
}
if (fileName) {
const folderPath = "Inbox"; // Define the folder where the file will be saved
const fullFilePath = `${folderPath}/${fileName}`; // Path for the new file
// Rename and move the file to the desired folder
await tp.file.rename(fileName);
await tp.file.move(fullFilePath);
} else {
fileName = "Untitled"; // Fallback if no valid file name is found
}
}
// Add the file's title as the header
tR += `# ${fileName}`;
%>

<% tp.file.cursor() %>
