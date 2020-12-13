import queue
from typing import Any, List, Callable

FIFO = queue.Queue ()

class TreeNode:
    value: Any
    children: List['TreeNode']
    def __init__(self, key):
        self.value = key
        self.children = []
    def is_leaf(self):
        if len(self.children) > 0:
            return False
        return True
    def add(self, child: 'TreeNode'):
        if self == child:
            print("nope")
        self.children.append(child)
        def myFunc(e):
            return e.value
        self.children.sort(key = myFunc)

    def for_each_deep_first(self, visit: Callable[['TreeNode'], None]):
        if visit:
            for it in self.children:
                visit.for_each_deep_first(it)
            print(self.value)

    def for_each_level_order(self, visit: Callable[['TreeNode'], None]):
        if visit:
            for it in visit.children:
                FIFO.put(it)
                print(it.value)
            for it in self.children:
                visit.for_each_level_order(it)
class Tree:
    root: TreeNode
    def __init__(self, node):
        self.root = node

    def add(self, value: Any, parent_value: Any):
        r = TreeNode(value)
        if parent_value.value > value:
            if len(parent_value.children) == 2:
                self.add(value, parent_value.children[1])
            else:
                parent_value.add(r)
        elif parent_value.value < value:
            if len(parent_value.children) > 0:
                self.add(value, parent_value.children[0])
            else:
                parent_value.add(r)

    def for_each_level_order(self, Node : Callable[['TreeNode'], None]):
        if Node:
            for it in Node.children:
                self.for_each_deep_first(it)
            for it in Node.children:
                print(it.value)

    def for_each_deep_first(self, Node : Callable[['TreeNode'], None]):
        if Node:
            for it in Node.children:
                self.for_each_deep_first(it)
                print(it.value)

    def show(self):
        print("jeszcez nic")

r = TreeNode("F")
tree = Tree(r)
tree.add("B", r)
tree.add("G", r)
tree.add("I", r)
tree.add("H", r)
tree.add("A", r)
tree.add("D", r)
tree.add("C", r)
tree.add("E", r)
#tree.show()
tree.for_each_deep_first(r)
tree.for_each_level_order(r)
r.for_each_level_order(r)
r.for_each_deep_first(r)
