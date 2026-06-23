# Main.py
from collections import deque


def bfs(graph, start):
    visited = set()
    queue = deque([start])

    visited.add(start)

    print("Порядок обходу BFS:")

    while queue:
        vertex = queue.popleft()
        print(vertex, end=" ")

        for neighbor in graph[vertex]:
            if neighbor not in visited:
                visited.add(neighbor)
                queue.append(neighbor)

    print()


def main():
    graph = {
        'A': ['B', 'C'],
        'B': ['A', 'D', 'E'],
        'C': ['A', 'F'],
        'D': ['B'],
        'E': ['B'],
        'F': ['C']
    }

    bfs(graph, 'A')


if __name__ == "__main__":
    main()
