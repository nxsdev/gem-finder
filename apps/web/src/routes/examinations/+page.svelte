<script lang="ts">
  import { onMount } from 'svelte';

  // 質問データの例
  const questions = [
    "質問1",
    "質問2",
    "質問3",
    // ... 他の質問
  ];

  let currentQuestionIndex = 0;
  let currentQuestion = questions[currentQuestionIndex];

  function nextQuestion() {
    currentQuestionIndex += 1;
    if (currentQuestionIndex < questions.length) {
      currentQuestion = questions[currentQuestionIndex];
    } else {
      // 質問が終わったら何かの処理をする
      console.log("試験終了");
    }
  }
</script>

<div class="container mx-auto p-8 space-y-8">
  <section>
    <div class="flex">
      <div class="card p-4">
        <div class="card variant-soft p-4 font-bold">
          自分の性格タイプを明らかにするため、深く考えず直感で回答してください。
        </div>
        <div class="card p-4 font-bold">
          質問は全部で80問あります。
          15分程度を目安にすべての質問項目にお応えください。
        </div>
        <div class="card p-4 font-bold">途中でブラウザを閉じると最初からやり直しとなります。
          必ず最後まですべての質問に回答してください。
        </div>
        <div class="flex justify-center align-center my-6">
          <button on:click={nextQuestion} class="btn variant-filled-secondary">
            テストを開始
          </button>
        </div>
      </div>
    </div>
    
  </section>
</div>
