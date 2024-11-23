def direct_flights(n, m, flights):

    direct_routes = {i: [] for i in range(1, n + 1)}


    for flight in flights:
        start, end = flight
        direct_routes[start].append(end)


    result = []
    for city in range(1, n + 1):
        if direct_routes[city]:
            result.append(len(direct_routes[city]))
        else:
            result.append(0)

    return result



n, m = map(int, input().split())
flights = []

for _ in range(m):
    start, end = map(int, input().split())
    flights.append((start, end))


output = direct_flights(n, m, flights)
for result in output:
    print(result)
