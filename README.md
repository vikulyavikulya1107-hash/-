def make_protected_callback(password,callback):
    def protected():
        user_input = input("Введите пароль:")
        if user_input == password :
            return callback()
        else:
            print("Ошибка: неверный пароль")
            return None
        return protected
    def say_hello():
        print ("Доступ разрешен:Привет!")
        protected = make_protected_callback("2345",say_hello)
        protected()
        protected()
