// ==UserScript==
// @name         Print GeCo
// @namespace    https://github.com/gestionece/scriptGeCo
// @version      0.3
// @description  Toglie delle collone per simplificare la stampa
// @author       Ruslan Dzyuba(Trorker)
// @match        https://geco.impresalevratti.it/admin/backend/pratica/?*
// @grant        none
// ==/UserScript==

(function() {
    'use strict';

    // Your code here...
    window.Stampa = function () {
        window.open(window.location.href + '&o=9','_self');
        var resultList = document.querySelector("#changelist-form > div.results").innerHTML;
        var a = window.open('','','width=733,height=454');
        a.document.open("text/html");
        a.document.write('<html><head><title>Stampa GeCo</title>');
        a.document.write('<link rel="stylesheet" type="text/css" href="/static/admin/css/base.css">');
        a.document.write('<style>body{opacity: 0}@media print { body{opacity: 1}}</style>');
        a.document.write('</head><body style="overflow: hidden;">');
        a.document.write(resultList);
        a.document.write("</body></html>");
        a.document.close(); // necessary for IE >= 10
        a.focus(); // necessary for IE >= 10*/

        setTimeout(function(){ a.print(); a.close(); }, 500);
    }

    if(window.location.hash == "#simple") {
        document.querySelector("#result_list > thead > tr > th.action-checkbox-column").style.opacity = "0";

        document.querySelector("#result_list > thead > tr > th.sortable.column-stato_esecuzione_display_html").style.display = "none";
        document.querySelector("#result_list > thead > tr > th.sortable.column-tipo_misuratore").style.display = "none";
        document.querySelector("#result_list > thead > tr > th.sortable.column-collocazione_contatore").style.display = "none";
        document.querySelector("#result_list > thead > tr > th.sortable.column-orario_assegnazione").style.display = "none";
        document.querySelector("#result_list > thead > tr > th.sortable.column-lotto").style.display = "none";
        document.querySelector("#result_list > thead > tr > th.sortable.column-contratto").style.display = "none";
        document.querySelector("#result_list > thead > tr > th.sortable.column-data_esecuzione_display").style.display = "none";
        document.querySelector("#result_list > thead > tr > th.sortable.column-data_sopralluogo_display").style.display = "none";
        document.querySelector("#result_list > thead > tr > th.sortable.column-data_sopralluogo_display").style.display = "none";
        document.querySelector("#result_list > thead > tr > th.column-contatore_link").style.display = "none";
        document.querySelector("#result_list > thead > tr > th.sortable.column-codice_ante_sostituzione").style.display = "none";
        document.querySelector("#result_list > thead > tr > th.sortable.column-matricola_ante_sostituzione").style.display = "none";
        document.querySelector("#result_list > thead > tr > th.sortable.column-pod").style.display = "none";
        document.querySelector("#result_list > thead > tr > th.sortable.column-idrda").style.display = "none";

        var operators = document.querySelector("#result_list > tbody").childElementCount;
        var i;
        for (i = 1; i <= operators; i++) {
            document.querySelector("#result_list > tbody > tr:nth-child(" + i + ") > td.field-stato_esecuzione_display_html").style.display = "none";
            document.querySelector("#result_list > tbody > tr:nth-child(" + i + ") > td.field-tipo_misuratore").style.display = "none";
            document.querySelector("#result_list > tbody > tr:nth-child(" + i + ") > td.field-collocazione_contatore").style.display = "none";
            document.querySelector("#result_list > tbody > tr:nth-child(" + i + ") > td.field-orario_assegnazione").style.display = "none";
            document.querySelector("#result_list > tbody > tr:nth-child(" + i + ") > td.field-lotto.nowrap").style.display = "none";
            document.querySelector("#result_list > tbody > tr:nth-child(" + i + ") > td.field-contratto.nowrap").style.display = "none";
            document.querySelector("#result_list > tbody > tr:nth-child(" + i + ") > td.field-data_esecuzione_display").style.display = "none";
            document.querySelector("#result_list > tbody > tr:nth-child(" + i + ") > td.field-data_sopralluogo_display").style.display = "none";
            document.querySelector("#result_list > tbody > tr:nth-child(" + i + ") > td.field-contatore_link").style.display = "none";
            document.querySelector("#result_list > tbody > tr:nth-child(" + i + ") > td.field-codice_ante_sostituzione").style.display = "none";
            document.querySelector("#result_list > tbody > tr:nth-child(" + i + ") > td.field-matricola_ante_sostituzione").style.display = "none";
            document.querySelector("#result_list > tbody > tr:nth-child(" + i + ") > td.field-pod").style.display = "none";
            document.querySelector("#result_list > tbody > tr:nth-child(" + i + ") > td.field-idrda").style.display = "none";
        }

        var btnS = document.createElement("li");
        btnS.innerHTML = '<a href="javascript:Stampa();" class="historylink">Stampa</a>';

        var contBtnS = document.querySelector("#content-main > ul");
        contBtnS.insertBefore(btnS, contBtnS.childNodes[0]);
    } else {
        var btn = document.createElement("li");
        btn.innerHTML = '<a href="' + window.location.href + '&o=9#simple" class="historylink" target="_blank">Semplificato</a>';

        var contBtn = document.querySelector("#content-main > ul");
        contBtn.insertBefore(btn, contBtn.childNodes[0]);
    }
})();
