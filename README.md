# number-to-roman

// not optimized

    function numericToRoman(num) {
        var one = ['', 'I', 'II', 'III', 'IV', 'V', 'VI', 'VII', 'VIII', 'IX'];
        var str = '';
        var roman = ['MMM','MM','M','CM','DCCC','DCC','DC','D','CD','CCC','CC','C','XC','LXXX','LXX','LX','L','XL','XXX','XX','X'];
        var associate = [3000, 2000,1000,900,800,700,600,500,400,300,200,100,90,80,70,60,50,40,30,20,10];
    
        for (var x = 0; x< 21; x++) {
          if (num >= associate[x]) {
            str += roman[x];
            num = num - associate[x];
          }
        }
    
        str += one[num];
    
        return str;
    }



// Optimized

    function numericToRoman(num) {
        var one = ['', 'I', 'II', 'III', 'IV', 'V', 'VI', 'VII', 'VIII', 'IX'];
        var ten = '';
        var thousand = '';
        var hundred = '';
    
        if (num >= 3000) {
          thousand = 'MMM';
          num = num - 3000;
        }
    
        if (num >= 2000) {
          thousand = 'MM';
          num = num - 2000;
        }
        if (num >= 1000) {
          thousand = 'M';
          num = num - 1000;
        }
        if (num >= 900) {
          hundred = 'CM';
          num = num - 900;
        }
        if (num >= 800) {
          hundred = 'DCCC';
          num = num - 800;
        }
        if (num >= 700) {
    
          hundred = 'DCC';
          num = num - 700;
        }
        if (num >= 600) {
          hundred = 'DC';
          num = num - 600;
        }
        if (num >= 500) {
          hundred = 'D';
          num = num - 500;
        }
        if (num >= 400) {
          hundred = 'CD';
          num = num - 400;
        }
        if (num >= 300) {
          hundred = 'CCC';
          num = num - 300;
        }
        if (num >= 200) {
          hundred = 'CC';
          num = num - 200;
        }
        if (num >= 100) {
          hundred = 'C';
          num = num - 100;
        }
        if (num >= 90) {
          ten = 'XC';
          num = num - 90;
        }
        if (num >= 80) {
          ten = 'LXXX';
          num = num - 80;
        }
        if (num >= 70) {
          ten = 'LXX';
          num = num - 70;
        }
        if (num >= 60) {
          ten = 'LX';
          num = num - 60;
        }
        if (num >= 50) {
          ten = 'L';
          num = num - 50;
        }
        if (num >= 40) {
          ten = 'XL';
          num = num - 40;
        }
        if (num >= 30) {
          ten = 'XXX';
          num = num - 30;
        }
        if (num >= 20) {
          ten = 'XX';
          num = num - 20;
        }
        if (num >= 10) {
          ten = 'X'
          num = num - 10;
        }
    
        var str = thousand + hundred + ten + one[num];
    
        return str;
    }
