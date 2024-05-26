# fb2tex_template

This project provides a LaTeX template for converting FB2 (FictionBook 2) files to a well-formatted PDF.

## How to Run

1. **Convert FB2 to LaTeX**

   ```sh
   pandoc --from=fb2 --to=latex --output=karamazov.tex karamazov.fb2
   ```

2. **Modify the LaTeX File**

   ```sh
   sed -i -e 's/subsection/section/g' karamazov.tex
   sed -i -e 's/--/—/g' karamazov.tex
   ```

3. **Build the Docker Image**

   ```sh
   docker build -t latex-env docker
   ```

4. **Compile the LaTeX File**

   ```sh
   docker run --rm -v $(pwd)/tex:/work -w /work latex-env xelatex main.tex
   ```
