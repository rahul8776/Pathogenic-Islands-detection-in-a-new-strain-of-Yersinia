import SeqIO

sequence_found = Falsewhile not sequence_found:
    # User should have file in the directory that they are running their code from    file_name = input("File name with extension: ")
    file_type = input("File type: ")
    seq_ID_q = input("Give the sequence ID you are looking for: ")

    try:
        for record in SeqIO.parse(file_name, file_type):
            if seq_ID_q in record.id:
                print(record)
                sequence_found = True        if not sequence_found:
            print("This sequence ID does not exist in your file")

    except (FileNotFoundError, ValueError):
        print("This file doesn't exist in this directory")i
