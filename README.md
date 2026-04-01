# Borradores
Borradores
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](
https://colab.research.google.com/drive/1LdiGUG3lx5_d5qHiBXkLM4m_02Ijmf_N)

[Abrir en Colab](https://colab.research.google.com/drive/1LdiGUG3lx5_d5qHiBXkLM4m_02Ijmf_N)

# Hola


✅ Enlace simple en Markdown
[Abrir en Colab](https://colab.research.google.com/drive/1LdiGUG3lx5_d5qHiBXkLM4m_02Ijmf_N)

✅ Botón “Open in Colab” para un notebook de Drive

Colab acepta una URL directa a Drive. Usá este Markdown:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](
https://colab.research.google.com/drive/1LdiGUG3lx5_d5qHiBXkLM4m_02Ijmf_N)


1. Entrá a tu repositorio

👉 https://github.com/tu_usuario/tu_repo

2. Hacé clic en la pestaña Add file

La vas a ver arriba a la derecha.

3. Elegí Create new file
4. Escribí este nombre EXACTO del archivo:
.github/workflows/run-python.yml


GitHub va a crear automáticamente las carpetas .github y workflows.

5. Pegá este contenido entero dentro del archivo:
name: Run Python Script

on:
  push:
  workflow_dispatch:

jobs:
  run-script:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v3

      - name: Setup Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.10'

      - name: Install dependencies (if any)
        run: |
          if [ -f requirements.txt ]; then
            python -m pip install --upgrade pip
            pip install -r requirements.txt
          else
            echo "No requirements.txt found"
          fi

      - name: Run Python script
        env:
          API_KEY: ${{ secrets.API_KEY }}
        run: |
          python main.py

6. Bajá hasta la parte de abajo del editor

Completá:

Commit message:
Add workflow to run Python script

Elegí: Commit directly to main (o la branch que uses)

7. Hacé clic en Commit new file

🎉 ¡Listo!
Ya tenés creado el workflow en tu repo.


