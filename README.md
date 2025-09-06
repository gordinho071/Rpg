import random

player_hp = 100
enemy_hp = 50

print("Você encontrou um goblin!")
while player_hp > 0 and enemy_hp > 0:
    action = input("O que você quer fazer? [1] Atacar [2] Fugir: ")

    if action == "1":
        damage = random.randint(10, 20)
        enemy_hp -= damage
        print(f"Você causou {damage} de dano. Vida do inimigo: {enemy_hp}")

        if enemy_hp <= 0:
            print("Você derrotou o goblin!")
            break

        enemy_damage = random.randint(5, 15)
        player_hp -= enemy_damage
        print(f"O goblin te atacou! Você perdeu {enemy_damage} de vida. Sua vida: {player_hp}")

    elif action == "2":
        print("Você fugiu!")
        break
    else:
        print("Escolha inválida!")

if player_hp <= 0:
    print("Você morreu...")
