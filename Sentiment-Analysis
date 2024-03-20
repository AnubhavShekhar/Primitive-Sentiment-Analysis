from typing import List

punctuation_chars = ["'", '"', ",", ".", "!", ":", ";", '#', '@']

def strip_punctuation(string: str) -> str:
    """Strip punctuation characters from a string.

    Args:
        string (str): The input string.

    Returns:
        str: The input string with punctuation characters removed.
    """
    for punc in punctuation_chars:
        string = string.replace(punc, "")
    return string

def get_pos(string: str, positive_words: List[str]) -> int:
    """Count the number of positive words in a string.

    Args:
        string (str): The input string.
        positive_words (List[str]): List of positive words.

    Returns:
        int: The number of positive words found in the string.
    """
    string = strip_punctuation(string).lower()
    counter = 0
    for word in positive_words:
        for term in string.split():
            if term == word:
                counter += 1
    return counter

def get_neg(string: str, negative_words: List[str]) -> int:
    """Count the number of negative words in a string.

    Args:
        string (str): The input string.
        negative_words (List[str]): List of negative words.

    Returns:
        int: The number of negative words found in the string.
    """
    string = strip_punctuation(string).lower()
    counter = 0
    for word in negative_words:
        for term in string.split():
            if term == word:
                counter += 1
    return counter

def main():
    """Process Twitter data and calculate scores."""
    # Lists of words to use
    positive_words = []
    with open("positive_words.txt") as pos_f:
        for lin in pos_f:
            if lin[0] != ';' and lin[0] != '\n':
                positive_words.append(lin.strip())

    negative_words = []
    with open("negative_words.txt") as pos_f:
        for lin in pos_f:
            if lin[0] != ';' and lin[0] != '\n':
                negative_words.append(lin.strip())

    with open("..\project_twitter_data.csv", "r") as f:
        twitter_data = []

        for line in f.readlines():
            twitter_data.append(line.split(","))

        twitter_data_headers = twitter_data[0]
        twitter_data = twitter_data[1:]

        with open("resulting_data.csv", "w") as fh:
            results_headers = ["Number of Retweets", "Number of Replies", "Positive Score", "Negative Score", "Net Score"]
            fh.write(",".join(results_headers))

            for data in twitter_data:
                if len(data) == 3:
                    p_words = get_pos(strip_punctuation(data[0]), positive_words)
                    n_words = get_neg(strip_punctuation(data[0]), negative_words)
                    net = p_words - n_words
                    numRT = data[1]
                    numRE = data[2]
                    row = [numRT.strip(), numRE.strip(), str(p_words), str(n_words), str(net)]
                    print(row)
                    fh.write("\n")
                    fh.write(",".join(row))

if __name__ == "__main__":
    main()
