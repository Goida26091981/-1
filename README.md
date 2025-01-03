import random

def weather_advice():
    # Запрашиваем данные у пользователя
    temperature = input("Какая сейчас температура на улице (в градусах Цельсия)? ").strip()
    weather = input("Как описать погоду? (солнечно, облачно, дождливо, ветрено, снежно): ").strip().lower()
    season = input("Какое сейчас время года? (зима, весна, лето, осень): ").strip().lower()

    # Проверяем температуру, преобразуем в число
    try:
        temperature = float(temperature)
    except ValueError:
        print("Пожалуйста, введите числовое значение температуры.")
        return

    # Основные рекомендации по температуре
    if temperature <= -10:
        temp_advice = [
            "На улице сильный мороз! Обязательно наденьте теплую куртку, шапку, шарф, перчатки и теплые сапоги.",
            "Очень холодно, советую надеть пуховик и термобелье."
        ]
    elif -10 < temperature <= 0:
        temp_advice = [
            "На улице холодно. Лучше всего подойдет зимняя куртка, шапка и шарф.",
            "Холодновато, можно надеть теплый свитер и пальто."
        ]
    elif 0 < temperature <= 10:
        temp_advice = [
            "Погода прохладная, наденьте легкую куртку или свитер.",
            "Прохладно, подойдет пальто или ветровка с шарфом."
        ]
    elif 10 < temperature <= 20:
        temp_advice = [
            "На улице комфортная погода, можно надеть легкий свитер или толстовку.",
            "Тепло, подойдет футболка и легкая куртка."
        ]
    elif 20 < temperature <= 30:
        temp_advice = [
            "Погода теплая, достаточно футболки и легких брюк или шорт.",
            "Очень тепло, подойдет легкая одежда."
        ]
    else:
        temp_advice = [
            "На улице жара! Лучше надеть шорты, майку и легкую обувь.",
            "Очень жарко, надевайте легкие вещи и не забывайте головной убор."
        ]

    # Советы по погодным условиям
    weather_conditions = {
        "солнечно": [
            "Солнечно, не забудьте солнцезащитные очки и крем от загара.",
            "Сегодня ясно, возьмите шляпу или кепку, чтобы защититься от солнца."
        ],
        "облачно": [
            "На улице облачно, но не очень холодно.",
            "Облачно, можно надеть что-то легкое, но на всякий случай взять с собой куртку."
        ],
        "дождливо": [
            "Идет дождь, возьмите зонт или дождевик.",
            "На улице дождливо — наденьте водонепроницаемую куртку и непромокаемую обувь."
        ],
        "ветрено": [
            "На улице ветрено, возьмите ветровку и шарф.",
            "Сильный ветер, наденьте куртку с капюшоном или защиту для головы."
        ],
        "снежно": [
            "Идет снег, утеплитесь и возьмите шарф и перчатки.",
            "Снежная погода, лучше выбрать теплую зимнюю одежду и обувь."
        ]
    }

    # Дополнительные советы по сезону
    seasonal_advice = {
        "зима": [
            "Зимой особенно важно одеваться тепло, чтобы не замерзнуть.",
            "Не забывайте про теплые носки и перчатки зимой."
        ],
        "весна": [
            "Весной погода может меняться, лучше надеть что-то многослойное.",
            "Весной бывает прохладно утром и тепло днем, так что выбирайте многослойную одежду."
        ],
        "лето": [
            "Летом не забывайте пить достаточно воды и защищаться от солнца.",
            "В жаркие дни лета стоит выбирать легкую и светлую одежду."
        ],
        "осень": [
            "Осенью погода может быть непредсказуемой, лучше взять с собой дождевик.",
            "Осенью прохладно и дождливо, подойдут водонепроницаемая куртка и зонт."
        ]
    }

    # Выводим основные советы
    print("\nСовет по температуре:")
    print(random.choice(temp_advice))

    # Выводим советы по погодным условиям
    if weather in weather_conditions:
        print("\nСовет по погоде:")
        print(random.choice(weather_conditions[weather]))

    # Выводим советы по сезону
    if season in seasonal_advice:
        print("\nСовет по сезону:")
        print(random.choice(seasonal_advice[season]))
# Запускаем функцию
weather_advice()
