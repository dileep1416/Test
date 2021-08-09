    function AppendValue() {

        var checkboxChecked = document.getElementById("checkboxid").checked
        console.log(checkboxChecked);
        var x = document.getElementById("cars");
     
        if (checkboxChecked) {
            var option = document.createElement("option");
            option.text = "Not Listed";
            option.value = "4";
            x.add(option);

            for (var i = 0; i < x.options.length; i++) {
                if (x.options[i].value === "4") {
                    x.selectedIndex = i;
                    break;
                }
            }
        }
        else {
            for (var i = 0; i < x.options.length; i++) {
                if (x.options[i].value === "4") {
                    
                    x.remove(i);
                    break;
                }
            }
        }

    }
