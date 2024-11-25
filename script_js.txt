const prefixes = {
    'Y': 24, 'Z': 21, 'E': 18, 'P': 15, 'T': 12, 'G': 9,
    'M': 6, 'k': 3, 'h': 2, 'da': 1, 'd': -1, 'c': -2,
    'm': -3, 'u': -6, 'n': -9, 'p': -12, 'f': -15, 'a': -18,
    'z': -21, 'y': -24
};

function convertUnits() {
    const a1 = parseFloat(document.getElementById('a1').value);
    const b1 = document.getElementById('b1').value;
    const c1 = document.getElementById('c1').value;

    if (isNaN(a1) || !(b1 in prefixes) || !(c1 in prefixes)) {
        document.getElementById('result').innerText = "คำหน้าหน่วยที่ป้อนไม่ถูกต้อง";
        return;
    }

    const e1 = prefixes[b1] - prefixes[c1];
    const result = `${a1} ${b1} เป็น ${a1} * 10^${e1} ${c1}`;
    document.getElementById('result').innerText = result;
}