# bot_telegram-jogando-dice
Bot de telegram em python jogando dice 🎲 com o usuário 

# emxeplo de como jogar o dice
```
/jogar 4 

```
# CÓDIGO 
```
############jogar############## 
@bot.message_handler(commands=['jogar' , 'JOGAR'])
def email_0(mensagem):
    try:
        jogar = int(mensagem.text.lstrip('/JOGAR'). lstrip('jogar'))
        
        if jogar >= 7:
            bot.reply_to(mensagem , 'nao pode numero maior que 6 ')
        elif jogar <= 6:
            k00 = bot.send_message(mensagem.chat.id , 'testando sua sorte ....')
            
            
            b  = bot.send_dice(mensagem.chat.id ,'🎲')
            
            if jogar == b.dice.value:
                sleep(3.5)
                bot.reply_to(mensagem , 'você ganhou 🥰')
            else:
                    sleep(3.5)
                    perdeu = bot.reply_to(mensagem , 'você perdeu 🥰')
                    sleep(0.5)
                    bot.delete_message(mensagem.chat.id , perdeu.id)
                    bot.delete_message(mensagem.chat.id , k00.id)
                    
                    
    except:
        j_ap = bot.send_message(mensagem.chat.id , 'NAO PODE LETRAS OU SÍMBOLO  ')
        jogou = bot.reply_to(mensagem , 'EXEMPLO DE COMO JOGAR O JOGO DE DADO /jogar 1 até 6 ')
        sleep(6)
        
        bot.delete_message(mensagem.chat.id , j_ap.id )
        bot.delete_message(mensagem.chat.id , jogou.id)
############jogar##############        

```

