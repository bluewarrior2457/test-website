if (!!localStorage.getItem("FacebookHelper")) {
    var facebookHelper = JSON.parse(localStorage.getItem("FacebookHelper"));
    if (window.location.href.indexOf("#_=_") > 0) {
        if (!!facebookHelper["href"]) {
            window.location.href = facebookHelper["href"];
        }
    } else if ((!!facebookHelper["href"]) && (facebookHelper["href"] === window.location.href)) {
        eval('var backload = ' + facebookHelper["function"] + ';');
        localStorage.removeItem("FacebookHelper");
        backload();
    }
}

var facebookDialogTemplate;
if ((!!window["jQuery"]) && (!mobile)) {    
    var FacebookDialogTemplate = function() {
        this.show = function(type, header, text) {
            $($("#popup-header > div")[0]).attr("id", type + "-icon");
            $("#facebook-popup-header").text(header);
            $("#facebook-popup-text").text(text);
            $("#fb-popup-bg").removeClass("invisible");
            $(".width-change").width(400).height(200).offset({left: $("#facebook-popup").offset().left, top: ($(window).height() - 200) >> 1});
            setTimeout(function() {
                $("#facebook-popup-header").removeClass("invisible");
                $("#" + type + "-icon").removeClass("invisible");
                $("#fb-popup-button").removeClass("invisible");
                $("#designed-x").removeClass("invisible");
                $("#facebook-popup-text").removeClass("invisible");
            }, 500);
        };
        
        this.hide = function() {
            $(".width-change").width(0).height(0).offset({left: $("#facebook-popup").offset().left, top: ($(window).height()) >> 1});
            $("#facebook-popup-header").addClass("invisible");
            $("#info-icon, #warning-icon, #error-icon").addClass("invisible");
            $("#fb-popup-button").addClass("invisible");
            $("#designed-x").addClass("invisible");
            $("#facebook-popup-text").addClass("invisible");
            setTimeout(function() {
                $("#fb-popup-bg").addClass("invisible");
            }, 700);
        };
        
        $("#facebook-popup").offset({left: $("#facebook-popup").offset().left, top: ($(window).height() - $("#facebook-popup").height()) >> 1});
        $("#facebook-popup-header").addClass("invisible");
        $("#info-icon, #warning-icon, #error-icon").addClass("invisible");
        $("#fb-popup-button").addClass("invisible");
        $("#designed-x").addClass("invisible");
    };
    facebookDialogTemplate = new FacebookDialogTemplate();
} else {
    var FacebookDialogTemplate = function() {
        this.show = function(type, header, text) {
            document.getElementById("fb-popup-bg").className = "";
            document.querySelector("#facebook-popup-header").innerHTML = header;
            document.querySelector("#facebook-popup-text").innerHTML = text;
            document.querySelector("#popup-header > div").id = type + "-icon";
            setTimeout(function() {
                document.getElementsByClassName("width-change")[0].style.width = "250px";
                document.getElementsByClassName("width-change")[0].style.height = "250px";
                document.querySelector("#facebook-popup").style.marginTop = ((window.innerHeight - 250) >> 1) + "px";
                setTimeout(function() {
                    document.querySelector("#facebook-popup-header").className = "";
                    document.querySelector("#" + type + "-icon").className = "";
                    document.querySelector("#fb-popup-button").className = "";
                    document.querySelector("#designed-x").className = "";
                    document.querySelector("#facebook-popup-text").className = "";
                }, 500);
            }, 10);
        };
        
        this.hide = function() {
            document.querySelector("#facebook-popup-header").className = "invisible";
            document.querySelector("#info-icon, #warning-icon, #error-icon").className = "invisible";
            document.querySelector("#fb-popup-button").className = "invisible";
            document.querySelector("#designed-x").className = "invisible";
            document.querySelector("#facebook-popup-text").className = "invisible";
            document.querySelector("#facebook-popup").style.marginTop = ((window.innerHeight) >> 1) + "px";
            document.getElementsByClassName("width-change")[0].style.width = "0px";
            document.getElementsByClassName("width-change")[0].style.height = "0px";
            setTimeout(function() {
               document.getElementById("fb-popup-bg").className = "invisible";
            }, 700);
        };
        
        document.querySelector("#facebook-popup").style.marginTop = ((window.innerHeight - document.querySelector("#facebook-popup").getBoundingClientRect().height) >> 1) + "px";
        document.querySelector("#facebook-popup-header").className = "invisible";
        document.querySelector("#info-icon, #error-icon, #warning-icon").className = "invisible";
        document.querySelector("#fb-popup-button").className = "invisible";
        document.querySelector("#designed-x").className = "invisible";
        document.querySelector("#facebook-popup-text").className = "invisible";
    };
    facebookDialogTemplate = new FacebookDialogTemplate();
}
