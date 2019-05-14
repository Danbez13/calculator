variables:
entries
total
temp
val
nt
i
nextNum
symbol

Peusdocode:
variable entries = []
variable total = 0

variable temp = ''
library("button").on('click', function() {
    variable val = library(this).text()
}

if(isNan(val)not or val is equal to '.'){
    temp += val
    library("#answer").val(temp.substring(0,10))
}

else if(val === 'AC') {
    entries = []
    temp = ''
    total = 0
    library("#answer").val('')
}

else if (val === 'CE') {
    temp = '';
    library("#answer").val('')
}

else if (val === 'x') {
    entries.push(temp);
    entries.push('*');
    temp = '';
}

else if (val === '÷') {
    entries.push(temp);
    entries.push('/');
    temp = '';
}

else if (val === '=') {
  	entries.push(temp);
}

variable nt = Number(entries[0]);
for (variable i = 1; i < entries.length; i++) {
    variable nextNum = Number(entries[i+1])
    variable symbol = entries[i];

    if (symbol === '+') { nt += nextNum; } 
    else if (symbol === '-') { nt -= nextNum; } 
    else if (symbol === '*') { nt *= nextNum; } 
    else if (symbol === '/') { nt /= nextNum; }     
    i++
}
    if (nt < 0) {
      nt = Math.abs(nt) + '-';
    }
    
    library("#answer").val(nt);
		entries = [];
    temp = '';

    }
    else {
    entries.push(temp);
    entries.push(val);
    temp = '';
  }
});