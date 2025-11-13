# movie_booking.py

movies = {
    1: {"name": "Avengers: Endgame", "available_seats": 50, "price": 250},
    2: {"name": "Spider-Man: No Way Home", "available_seats": 40, "price": 200},
    3: {"name": "Joker", "available_seats": 30, "price": 180},
    4: {"name": "Pushpa 2", "available_seats": 60, "price": 220}
}

bookings = []

def show_movies():
    print("\n🎬 Available Movies:")
    for movie_id, movie in movies.items():
        print(f"{movie_id}. {movie['name']} (Seats: {movie['available_seats']}, Price: ₹{movie['price']})")

def book_ticket():
    show_movies()
    try:
        movie_id = int(input("\nEnter movie number you want to book: "))
        if movie_id not in movies:
            print("❌ Invalid movie number.")
            return

        movie = movies[movie_id]
        print(f"You selected: {movie['name']}")

        tickets = int(input("Enter number of tickets: "))
        if tickets <= 0:
            print("❌ Invalid ticket count.")
            return

        if tickets > movie['available_seats']:
            print("❌ Not enough seats available.")
            return

        total = tickets * movie['price']
        print(f"💰 Total amount to pay: ₹{total}")
        confirm = input("Confirm booking? (yes/no): ").lower()

        if confirm == "yes":
            movie['available_seats'] -= tickets
            bookings.append({
                "movie": movie['name'],
                "tickets": tickets,
                "total": total
            })
            print(f"✅ Booking successful for {tickets} tickets of '{movie['name']}'!")
        else:
            print("❌ Booking cancelled.")

    except ValueError:
        print("⚠️ Please enter valid input.")

def view_bookings():
    if not bookings:
        print("\n📭 No bookings yet.")
    else:
        print("\n🎟️ Your Bookings:")
        for b in bookings:
            print(f"- {b['movie']} | Tickets: {b['tickets']} | Paid: ₹{b['total']}")

def main():
    while True:
        print("\n====== 🎥 Movie Booking System ======")
        print("1. Show Movies")
        print("2. Book Tickets")
        print("3. View My Bookings")
        print("4. Exit")

        choice = input("Enter your choice: ")

        if choice == "1":
            show_movies()
        elif choice == "2":
            book_ticket()
        elif choice == "3":
            view_bookings()
        elif choice == "4":
            print("👋 Thank you for using Movie Booking App!")
            break
        else:
            print("⚠️ Invalid choice, try again.")

if __name__ == "__main__":
    main()
