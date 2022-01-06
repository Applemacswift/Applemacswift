- 👋 Hi, I’m @Applemacswift
- 👀 I’m interested in work ios developer
- 🌱 I’m currently learning in Netology
- 💞️ I’m looking to collaborate ...
- 📫 How to reach me telegram @andrei_chepkasov, mobile: +7 922 3000 446
- below is an example of my code 👇👇👇
- Number 1
var busStops = ["Ленина": 0,
                "Кировский проспект": 10+15,
                "Площадь": 25+10,
                "Вокзал": 35+15,
                "Ломоносова": 50+10,
                "Северная": 60+13,
                "Южная": 73+15]


func busTimeCalculation (initial start: String, final stop: String) -> Int {
    let x:Int = (busStops[start] ?? 0) - (busStops[stop] ?? 0)

    if busStops[start] == nil {
        print("Такой остановки не существует, проверьте правильность введенных данных начальной станции")
    } else if  busStops[stop] == nil {
        print("Такой остановки не существует, проверьте правильность введенных данных конечной станции")
    } else if x < 0 {
        print(-x)
    } else if x > 0 {
        print(x)
    }
    return(x)
}
busTimeCalculation(initial: "Вокзал", final: "Северная")




- Number 2

var theFirstPerson = (favoriteMovie: "Avatar",
                 favoriteNum: "20",
                 favoriteFood: "Carbonara")

let (movie, num, food) = theFirstPerson
movie
num
food

var theSecondPerson = (favoriteMovie: "Men in black",
                     favoriteNum: "7",
                     favoriteFood: "barbecue")

var guest = theFirstPerson
guest = theSecondPerson

var numbers = (theFirstPerson.favoriteNum, theSecondPerson.favoriteNum)

if numbers.0 != numbers.1 {
    let a: Int = Int(numbers.0)!
    let b: Int = Int(numbers.1)!
    let c = a - b
    print("Разница между числами первого и второго кортежа равна: \(c)")
}


/// #                          
let numOfItems = ["Математика" : 5, "Русский язык" : 3, "История" : 4]
let students = ["Andrew" : numOfItems]
students["Andrew"]


/// #                          
typealias Chessman = [String: (alpha: Character, num: Int)?]
var chessmans: Chessman = ["Белый король" : ("b", 5), "Слон" : ("d", 3), "Конь" : nil]

// разкомментируйте ниже код для проверки состояния фигуры =)
//chessmans["Конь"] = ("d", 4)
if let info = chessmans["Конь"] as? (Character, Int) {
    print("Фигура сейчас на координатах: \(info)\n")
} else {
    print("Вас подбили, фигура уничтожена\n")
}


/// #                           
chessmans.forEach { (key: String, value: (alpha: Character, num: Int)?) in
    if let _ = value {
        print("Проверка по фигурам завершена. \(key) на координатах: \(value!)")
    }
}




- Number 3

import Darwin
enum Country {
    case UK
    case USA
    case France
}

struct Track {
    let title: String
    let performer: String
    let duration: Int
    let country: Country
}

class Category {
    var name: String
    private lazy var tracks = [Track]()
    var amountOfTracks: Int {
        return tracks.count
    }
    
    init(name: String) {
        self.name = name
    }
    
    func addTrack(_ track: Track) {
        tracks.append(track)
    }
    
    func removeTrackWith(title: String) {
        if let index = tracks.firstIndex(where: {$0.title == title}) {
            tracks.remove(at: index)
        }
    }
    
    func printSelf() {
        print("Category: \(name), amount of tracks: \(amountOfTracks)")
        for (i, track) in tracks.enumerated() {
            print(" \(i+1). \(track.title), \(track.performer), \(track.duration) sec, \(track.country)")
        }
    }
}


let track1 = Track(title: "Title1", performer: "Perf1", duration: 100, country: .France)
let track2 = Track(title: "Title2", performer: "Perf2", duration: 110, country: .UK)
let track3 = Track(title: "Title3", performer: "Perf3", duration: 120, country: .USA)

let category = Category(name: "Grindcore")
category.addTrack(track1)
category.addTrack(track2)
category.addTrack(track3)

category.printSelf()

category.removeTrackWith(title: "Title2")

category.printSelf()


class Libraries {
    var listCategories = [Category]()
}
