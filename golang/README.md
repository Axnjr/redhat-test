# After completing the `Python` version of the task I thought to implement it `Go` as well !!

# Usage / test cases: 
## All methods are same as `python` version !
```go
// # Basic test
func run_test1() {
	sample_data := [][]string{
		{"Name", "Age", "Score"},
		{"Radha", "23", "85"},
		{"Bob", "23", "90"},
		{"Radha", "25", "78"},
	}
	test_file := "sample.csv"
	_write_csv(test_file, sample_data)
}

// --------------------------------------------------------------------------------------------------------------- //

// # mid completion test
func run_test2() {

	csvUtil, err := new_csv_utils_go("C:/Users/yaksh/redhat-test/ppl.csv")
	if err != nil {
		fmt.Println(err)
		return
	}

	csvUtil.display_csv(3, true)

	csvUtil.remove_duplicates("Job Title", "./output.csv")

	csvUtil.replace_all_vals("First Name", "Shelby", "Radha", "./output.csv")
	// output_file_name if empty then the original csv file is modified
	csvUtil.replace_first_val("First Name", "Radha", "Kanha", "./output.csv")

	csvUtil.count_valid_palindromes()

	// show first and last rows of the file
	csvUtil.summerize(3)
}

// --------------------------------------------------------------------------------------------------------------------- //

func run_test3() {

	csvUtil, err := new_csv_utils_go("C:/Users/yaksh/redhat-test/fruits.csv")
	if err != nil {
		fmt.Println(err)
		return
	}

	csvUtil.display_csv(3, true)

	csvUtil.filter_rows("Product", func(s string) bool { return s == "Apple" }, "./filterd_fruits.csv")

	csvUtil.sort_csv("Price", "./sorted_fruits.csv", true)

	sum_of_prices, err := csvUtil.aggregate_column("Price", "sum")

	if err != nil {
		fmt.Println(err)
	} else {
		fmt.Println("Aggregated sum of prices: ", sum_of_prices)
	}

	csvUtil.export_json("fruits.json")

	csvUtil.apply_func("Price", func(s float64) float64 { return s + 54.7 }, "./expensive_fruits.csv")
}
```
