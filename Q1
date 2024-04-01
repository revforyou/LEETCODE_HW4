class Solution:
    def numBusesToDestination(self, routes: List[List[int]], s: int, t: int) -> int:
        mp = {}
        n = len(routes)

        for i in range(n):
            for j in range(len(routes[i])):
                bus_stop_no = routes[i][j]
                ls = mp.get(bus_stop_no,[])
                ls.append(i)
                mp[bus_stop_no] = ls
        
        bus_stop_vis = set([])
        bus_vis = set([])
        lev = 0

        queue = []
        queue.append(s)
        bus_stop_vis.add(s)

        while len(queue):
            sz = len(queue)

            while sz:
                rem = queue.pop(0)

                if rem == t:
                    return lev

                bus_ls = mp[rem]

                for bus in bus_ls:
                    if bus in bus_vis:
                        continue 

                    for bus_stop in routes[bus]:
                        if bus_stop in bus_stop_vis:
                            continue

                        queue.append(bus_stop)
                        bus_stop_vis.add(bus_stop)
                    
                    bus_vis.add(bus)

                sz-=1
            
            lev+=1

            
        return -1
        

