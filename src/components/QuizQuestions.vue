<template>
  <div>
    <div class="rq-label">
      順位の発表は必要ですか？
      <span class="required">必須 </span>
    </div>
    <div class="rq-field">
      <div class="rq-radio-buttons">
        <div class="rq-radio-buttons--btn">
          <input
            type="radio"
            value="yes"
            v-model="selectedRequiredRanking"
            name="events_forms_entry_request[required_ranking]"
            id="events_forms_entry_request_required_ranking_yes"
          />
          <label
            for="events_forms_entry_request_required_ranking_yes"
            class="radio-buttons--btn--label"
            >はい
          </label>
        </div>
        <div class="rq-radio-buttons--btn">
          <input
            type="radio"
            value="no"
            v-model="selectedRequiredRanking"
            name="events_forms_entry_request[required_ranking]"
            id="events_forms_entry_request_required_ranking_no"
          />
          <label
            for="events_forms_entry_request_required_ranking_no"
            class="radio-buttons--btn--label"
            >いいえ
          </label>
        </div>
      </div>
    </div>
    <div v-if="selectedRequiredRanking == 'yes'" class="rq-label">
      順位は何位まで発表いたしますか？
      <span class="required">必須 </span>
    </div>
    <div v-if="selectedRequiredRanking == 'yes'" class="rq-label">
      <div class="rq-radio-buttons">
        <div class="rq-radio-buttons--btn">
          <input
            type="radio"
            value="one"
            v-model="selectedRequiredRankingRange"
            name="events_forms_entry_request[required_ranking_range]"
            id="events_forms_entry_request_required_ranking_range_one"
          />
          <label
            for="events_forms_entry_request_required_ranking_range_one"
            class="radio-buttons--btn--label"
            >1位のみ
          </label>
        </div>
        <div class="rq-radio-buttons--btn">
          <input
            type="radio"
            value="two"
            v-model="selectedRequiredRankingRange"
            name="events_forms_entry_request[required_ranking_range]"
            id="events_forms_entry_request_required_ranking_range_two"
          />
          <label
            for="events_forms_entry_request_required_ranking_range_two"
            class="radio-buttons--btn--label"
            >2位まで
          </label>
        </div>
        <div class="rq-radio-buttons--btn">
          <input
            type="radio"
            value="three"
            v-model="selectedRequiredRankingRange"
            name="events_forms_entry_request[required_ranking_range]"
            id="events_forms_entry_request_required_ranking_range_three"
          />
          <label
            for="events_forms_entry_request_required_ranking_range_three"
            class="radio-buttons--btn--label"
            >3位まで
          </label>
        </div>
      </div>
    </div>
    <div v-if="selectedRequiredRanking == 'yes'" class="rq-label">
      下記より、順位の対象についてお選びください。
      <span class="required">必須 </span>
    </div>
    <div v-if="selectedRequiredRanking == 'yes'" class="rq-label">
      <div class="rq-radio-buttons">
        <div class="rq-radio-buttons--btn">
          <input
            type="radio"
            value="individual"
            v-model="selectedRequiredRankingStyle"
            name="events_forms_entry_request[required_ranking_style]"
            id="events_forms_entry_request_required_ranking_style_individual"
          />
          <label
            for="events_forms_entry_request_required_ranking_style_individual"
            class="radio-buttons--btn--label"
            >個人単位
          </label>
        </div>
        <div class="rq-radio-buttons--btn">
          <input
            type="radio"
            value="team"
            v-model="selectedRequiredRankingStyle"
            name="events_forms_entry_request[required_ranking_style]"
            id="events_forms_entry_request_required_ranking_style_team"
          />
          <label
            for="events_forms_entry_request_required_ranking_style_team"
            class="radio-buttons--btn--label"
            >チーム単位
          </label>
        </div>
      </div>
    </div>
    <div v-if="selectedRequiredRanking == 'yes'" class="rq-label">
      景品の有無をお選びください。
      <span class="required">必須 </span>
    </div>
    <div v-if="selectedRequiredRanking == 'yes'" class="rq-label">
      <div class="rq-radio-buttons">
        <div class="rq-radio-buttons--btn">
          <input
            type="radio"
            value="yes"
            v-model="selectedRequiredRankingFirstPrize"
            name="events_forms_entry_request[required_ranking_prize]"
            id="events_forms_entry_request_required_ranking_prize_yes"
          />
          <label
            for="events_forms_entry_request_required_ranking_prize_yes"
            class="radio-buttons--btn--label"
            >あり
          </label>
        </div>
        <div class="rq-radio-buttons--btn">
          <input
            type="radio"
            value="no"
            v-model="selectedRequiredRankingFirstPrize"
            name="events_forms_entry_request[required_ranking_prize]"
            id="events_forms_entry_request_required_ranking_prize_no"
          />
          <label
            for="events_forms_entry_request_required_ranking_prize_no"
            class="radio-buttons--btn--label"
            >なし
          </label>
        </div>
      </div>
    </div>
    <div v-if="selectedRequiredRanking == 'yes'" class="rq-label">
      景品の内容について
      <span class="required">必須 </span>
    </div>
    <div v-if="selectedRequiredRanking == 'yes'" class="rq-label">
      <div class="rq-notification">
        ※当日に景品の発表がない場合は、「後日発表」とご記載ください。
      </div>
      <label for="events_forms_entry_request_ranking_first_prize"
        >1位の景品
      </label>
      <input
        placeholder="選べる日本三大和牛"
        type="text"
        v-model="firstPraze"
        name="events_forms_entry_request[ranking_first_prize]"
        id="events_forms_entry_request_ranking_first_prize"
      />
    </div>
    <div v-if="selectedRequiredRanking == 'yes'" class="rq-label">
      <label for="events_forms_entry_request_ranking_second_prize"
        >2位の景品
      </label>
      <input
        placeholder="ハーゲンダッツラバーズコレクション"
        type="text"
        v-model="secondPraze"
        name="events_forms_entry_request[ranking_second_prize]"
        id="events_forms_entry_request_ranking_second_prize"
      />
    </div>
    <div v-if="selectedRequiredRanking == 'yes'" class="rq-label">
      <label for="events_forms_entry_request_ranking_third_prize"
        >3位の景品
      </label>
      <input
        placeholder="アマゾンギフト1000円"
        type="text"
        v-model="thirdPraze"
        name="events_forms_entry_request[ranking_third_prize]"
        id="events_forms_entry_request_ranking_third_prize"
      />
    </div>
    <div v-if="selectedRequiredRanking == 'yes'" class="rq-label">
      同順位が複数いる場合の対応をお選びください。
      <span class="required">必須 </span>
    </div>
    <div v-if="selectedRequiredRanking == 'yes'" class="rq-label">
      <div class="rq-notification">※決定方法はじゃんけんになります。</div>
      <div class="rq-radio-buttons">
        <div class="rq-radio-buttons--btn">
          <input
            type="radio"
            value="ok"
            name="events_forms_entry_request[permission_same_rank]"
            id="events_forms_entry_request_permission_same_rank_ok"
          />
          <label
            for="events_forms_entry_request_permission_same_rank_ok"
            class="radio-buttons--btn--label"
            >複数名のままで可
          </label>
        </div>
        <div class="rq-radio-buttons--btn">
          <input
            type="radio"
            value="ng"
            name="events_forms_entry_request[permission_same_rank]"
            id="events_forms_entry_request_permission_same_rank_ng"
          />
          <label
            for="events_forms_entry_request_permission_same_rank_ng"
            class="radio-buttons--btn--label"
            >順位決定を行いたい
          </label>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "QuizQuestions",
  props: {
    requiredRanking: {
      type: String,
      default: "",
    },
    requiredRankingRange: {
      type: String,
      default: "",
    },
    requiredRankingStyle: {
      type: String,
      default: "",
    },
    requiredPrizeRank: {
      type: String,
      default: "",
    },
    permissionSameRank: {
      type: String,
      default: "",
    },
  },
  data() {
    return {
      selectedRequiredRanking: this.requiredRanking,
      selectedRequiredRankingStyle: this.requiredRankingStyle,
      selectedRequiredPrizeRank: this.requiredPrizeRank,
      firstPraze: "",
      secondPraze: "",
      thirdPraze: "",
      selectedPermissionSameRank: this.permissionSameRank,
    };
  },
  computed: {
    isError() {
      return (
        this.isBlankFirstPraze() &&
        this.isBlankSecondPraze() &&
        this.isBlankThirdPraze()
      );
    },
    isBlankFirstPraze() {
      return this.selectedRequiredRankingRange === "one" && !this.firstPraze;
    },
    isBlankSecondPraze() {
      return this.selectedRequiredRankingRange === "two" && !this.secondPraze;
    },
    isBlankThirdPraze() {
      return this.selectedRequiredRankingRange === "three" && !this.thirdPraze;
    },
  },
};
</script>

<style scoped>
</style>