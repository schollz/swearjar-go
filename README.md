# swearjar-go

[<img src="https://api.travis-ci.org/snicol/swearjar-go.svg?branch=master">](https://travis-ci.org/snicol/swearjar-go) [![](https://godoc.org/github.com/snicol/swearjar-go?status.svg)](http://godoc.org/github.com/snicol/swearjar-go) [![Go Report Card](https://goreportcard.com/badge/snicol/swearjar-go)](https://goreportcard.com/report/snicol/swearjar-go) 

Install:

    go get github.com/snicol/swearjar-go
    
# Usage

    swears, err := swearjar.Load()
    
    if err != nil {
    	log.Fatal(err)
    }
    
    profane, reasons, err := swears.Scorecard("ass") // = true, []string{"insult"}, nil
    
    profane, err = swears.Profane("flower") // = false, nil
    
The swear list used is bundled in swearjar.go, however using this format you can load your own using `Load()`:

    {
        "swear": ["insult", "provactive"],
        ... repeat
    }
    
And in your code:

    swears, _ := swearjar.Load("custom.json")
    

# Notes 

There is currently no `censor` feature like the other swearjar projects.

This is regex based and is not optimised in the slightest.

# Acknowledgements

This is based on [Swearjar](https://github.com/joshbuddy/swearjar) for Ruby and uses the JSON config from
 [swearjar-node](https://github.com/raymondjavaxx/swearjar-node).