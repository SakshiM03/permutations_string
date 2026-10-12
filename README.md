# permutations_string

def permutations(s):
    result = []

    def backtrack(path, remaining):
        if not remaining:
            result.append(path)
            return

        for i in range(len(remaining)):
            backtrack(
                path + remaining[i],
                remaining[:i] + remaining[i + 1:]
            )

    backtrack("", s)
    return result


text = "ABC"

for item in permutations(text):
    print(item)
