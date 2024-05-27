# Компилятор языка TinyC
* написан на языке Python
* использует ANTLR в качестве генератора лексического и синтаксического анализаторов
* использует LLVM в качестве генератора машинного кода

For ANTLR:
* pip install antlr4-python3-runtime
* pip install antlr4-tools

For LLVM:
* pip install llvmlite

Генерация Parser, Lexer, Listener и Visitor:
* antlr4 -Dlanguage=Python3 antlr_parser/TinyC.g4 -o antlr_parser -visitor

python llvm_ir.py name_TinyC_file  -- генерация .ll  файла, содержащего LLVM IR соответствующего .tc файла

python executor.py name_ll_file -- запуск сгенерированного .ll файла с помощью llvmlite (LLVM)

Можно автоматизировать выполнение предыдущих двух команд с помощью запуска файла auto_start.py 
