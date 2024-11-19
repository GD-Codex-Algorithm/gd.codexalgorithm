# gd.codexalgorithm.github.io
Open source library of AI systems and algorithms used in and for game development.

number test images are taken from https://www.flaticon.com/free-icons/numbers - Numbers icons created by riajulislam - Flaticon


python script is not shared directly and modified to protect data:

_______________________________________________________________________________________________________________________________________
import pandas as pd

# Load the Excel file
excel_file = 'pages_content.xlsx'
data = pd.read_excel(excel_file)

# Define a template for the HTML content
html_template = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{title}</title>
    <link rel="stylesheet" href="styles.css"> <!-- Optional CSS link -->
</head>
<body>
    <header>
        <h1>{title}</h1>
    </header>
    <main>
        <section>
            <h2>{section_title}</h2>
            <p>{description}</p>
            <img src="{image}" alt="{section_title}" />
            <pre>{pseudo_code}</pre>
        </section>
    </main>
</body>
</html>
"""

# Iterate through rows in the Excel file
for index, row in data.iterrows():
    # Fill the HTML template with content from the Excel file
    html_content = html_template.format(
        title=row['Title'],
        section_title=row['Title'],
        description=row['Description'],
        image=row['Image URL'],
        pseudo_code=row['Pseudo Code']
    )

    # Save the generated HTML file
    file_name = f"{row['Page Identifier']}.html"
    with open(file_name, 'w', encoding='utf-8') as file:
        file.write(html_content)

    print(f"Generated: {file_name}")
_______________________________________________________________________________________________________________________________________
