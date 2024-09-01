<label><input type="radio" name="q8" value="C"> أستخدم التنفس البطيء لتهدئة نفسي.</label>
    </div>
    <div class="question">
        <p>9. كيف تشعر أثناء التأمل أو اليوغا؟</p>
        <label><input type="radio" name="q9" value="A"> أفكر في أشياء كثيرة وأشعر بالتوتر.</label><br>
        <label><input type="radio" name="q9" value="B"> أشعر بالهدوء والتركيز.</label><br>
        <label><input type="radio" name="q9" value="C"> أستطيع التركيز على تنفسي وأشعر بالراحة.</label>
    </div>
    <div class="question">
        <p>10. كيف تتعامل مع الضغوط اليومية؟</p>
        <label><input type="radio" name="q10" value="A"> أشعر بالضغط وألهث.</label><br>
        <label><input type="radio" name="q10" value="B"> أتعامل معها بشكل طبيعي.</label><br>
        <label><input type="radio" name="q10" value="C"> أستخدم تقنيات التنفس البطيء للتهدئة.</label>
    </div>
    <button type="button" class="button" onclick="calculateResult()">احسب نتيجتي</button>
</form>

<div class="result" id="result"></div>

<script>
    function calculateResult() {
        const answers = ['A', 'B', 'C'];
        let score = { A: 0, B: 0, C: 0 };

        for (let i = 1; i <= 10; i++) {
            const q = document.querySelector(`input[name="q${i}"]:checked`);
            if (q) {
                score[q.value]++;
            }
        }

        let resultText;
        if (score.A > score.B && score.A > score.C) {
            resultText = "مستوى التنفس: تنفس طبيعي (الأزرق)";
        } else if (score.B > score.A && score.B > score.C) {
            resultText = "مستوى التنفس: تنفس عميق (الأخضر)";
        } else {
            resultText = "مستوى التنفس: تنفس بطيء (البنفسجي)";
        }

        document.getElementById("result").innerText = resultText;
    }
</script>

</body>
</html>
