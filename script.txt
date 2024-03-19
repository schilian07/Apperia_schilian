const form = document.getElementById("#form")
document.getElementById('rg');
document.getElementById('email');


addEventListener('submit', function(event) {
    var rgInput = document.getElementById('rg');
    var rg = rgInput.value.trim();

    if (!rg.match(/^\d{2}\.\d{3}\.\d{3}\-\d{1}$/)) {
        alert('Por favor, insira o RG no formato correto (00.000.000-0)');
        event.preventDefault();
        return false;
    }
    return true;
});

function validateEmail(email) {
    var emailRegex = /[a-zA-Z0-9]+@[a-zA-Z0-9]+\.[a-zA-Z0-9]{2,}/;
    return emailRegex.test(email);
}

addEventListener('submit', function(event) {
    var emailInput = document.getElementById('email');
    var email = emailInput.value.trim();

    if (!validateEmail(email)) {
        alert('Por favor, insira um email válido no formato emailuser@server.domain');
        event.preventDefault();
        return false;
    }

    return true;
});
