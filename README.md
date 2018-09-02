# Cryptographer

Утилита командной строки, которая позволяет зашифровать или расшифровать файл с данными произвольного размера. 
Поддерживаемые алгоритмы: OFB, CTR.

Интерфейс: 
[Размер блока, бит] - Целое число бит
[Пароль] - Произвольная строка
[Алгоритм] - OFB/CTR
[Операция] - ENCRYPT/DECRYPT
[Путь к файлу IV] 
[Путь к входному файлу]
[Путь к выходному файлу]
Пример аргументов:
32 12345 OFB ENCRYPT iv.txt war_and_peace_input.txt war_and_peace_encrypted.txt
32 12345 OFB DECRYPT iv.txt war_and_peace_encrypted.txt war_and_peace_decrypted.txt

Добавление алгоритмов реализуется с помощью наследования нового класса алгоритма от класса интерфейса CryptoAlgorithm.
Далее необходимо добавить определения нового алгоритма в ALG_TYPE и StrToAlgType, затем добавить case-ветку в оператор switch конструктора Cryptographer. 
Добавление процедур шифрования реализуется с помощью добавления новой процедуры, соответствующей сигнатуре void (primitives::Block&, const primitives::Block&), в namespace crypto::procedures
