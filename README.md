# tab-9
def baholash_tizimi():
    baholar = []
    print("Iltimos, 5 ta bahoni kiriting (0 dan 100 gacha):")

    while len(baholar) < 5:
        qiymat = input(f"{len(baholar) + 1}-bahoni kiriting: ")
        try:
            baho = float(qiymat)
            if 0 <= baho <= 100:
                baholar.append(baho)
            else:
                print("Xato: Baho 0 va 100 oralig'ida bo'lishi kerak!")
        except ValueError:
            print("Xato: Iltimos, faqat raqam kiriting!")

    baholar.sort()

    n = len(baholar)
    ortacha = sum(baholar) / n
    eng_past = baholar[0]
    eng_yuqori = baholar[-1]

    if n % 2 == 1:
        mediana = baholar[n // 2]
    else:
        mediana = (baholar[n // 2 - 1] + baholar[n // 2]) / 2

    print("\n--- Natijalar ---")
    print(f"Barcha baholar (tartiblangan): {baholar}")
    print(f"Eng past baho: {eng_past}")
    print(f"Eng yuqori baho: {eng_yuqori}")
    print(f"O'rtacha baho: {ortacha:.2f}")
    print(f"Mediana: {mediana:.2f}")

    qoniqarsizlar = [baho for baho in baholar if baho < 60]
    if qoniqarsizlar:
        print(f"Qoniqarsiz baholar: {qoniqarsizlar}")
    else:
        print("Qoniqarsiz baholar yo'q.")

    alo_baholar = [baho for baho in baholar if baho >= 90]
    if alo_baholar:
        print(f"A'lo baholar (90+): {alo_baholar}")
    else:
        print("A'lo baholar (90+) yo'q.")


baholash_tizimi()
