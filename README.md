# roe-pdf
dfs = []
for i in pdf_files:
    with pdfplumber.open(f"./mock_roe_4/{i}") as pdf:
        for i, page in enumerate(pdf.pages):
            table = page.extract_table()
            if table:  # Check if a table is found
                df = pd.DataFrame(table)  # Convert to DataFrame
                dfs.append(df)
