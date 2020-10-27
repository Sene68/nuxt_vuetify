<template>
  <v-card
    class="mx-auto"
    max-width="1000"
    outlined
  >
    <v-row justify="space-between" class="fill-height">
      <v-col cols="8" md="8">
        <v-list-item>
          <v-col cols="8" md="8">
            <v-list-item-content style="padding-top: 0px">
              <v-list-item-title>
                샌드박스 설명
                <v-chip
                  class="ma-2"
                  color="green"
                  outlined
                  small
                >
                  Running
                </v-chip>
              </v-list-item-title>
              <v-list-item-subtitle>Sandbox 설명</v-list-item-subtitle>
            </v-list-item-content>
          </v-col>
          <v-col cols="4" md="4">
            <v-list-item-content style="padding-top: 0px">
              <v-list-item-title>
                <v-chip
                  class="ma-2"
                  color="green"
                  outlined
                  small
                >
                  시작
                </v-chip>
                <v-chip
                  class="ma-2"
                  color="red"
                  outlined
                  small
                >
                  종료
                </v-chip>
              </v-list-item-title>
              <v-list-item-subtitle>
                접속 주소 : 12.34.56.123
                <v-btn icon class="ma-2" x-small>
                  <v-icon>mdi-content-copy</v-icon>
                </v-btn>
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-col>
        </v-list-item>
        <v-divider/>
        <v-list-item>
          <v-col cols="2" md="2">
            <v-list-item-content style="padding-bottom:2px">
              <v-list-item-title>OS</v-list-item-title>
              <v-list-item-subtitle>
                Windows
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-col>
          <v-col cols="2" md="2">
            <v-list-item-content style="padding-bottom:2px">
              <v-list-item-title>CPU</v-list-item-title>
              <v-list-item-subtitle>
                4 GB
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-col>
          <v-col cols="2" md="2">
            <v-list-item-content style="padding-bottom:2px">
              <v-list-item-title>Memory</v-list-item-title>
              <v-list-item-subtitle>
                16 GB
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-col>
          <v-col cols="2" md="2">
            <v-list-item-content style="padding-bottom:2px">
              <v-list-item-title>Volume</v-list-item-title>
              <v-list-item-subtitle>
                30 GB
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-col>
          <v-col cols="4" md="4">
            <v-list-item-content style="padding-bottom:2px">
              <v-list-item-title>
                요금
                <v-tooltip top>
                  <template v-slot:activator="{ on, attrs }">
                    <v-btn
                      icon
                      v-bind="attrs"
                      v-on="on"
                    ><v-icon>mdi-information-outline</v-icon></v-btn>
                  </template>
                  <span>환율 : 1200원 기준</span>
                </v-tooltip>
              </v-list-item-title>
              <v-list-item-subtitle>
                23 원 (시간)
              </v-list-item-subtitle>
              <v-list-item-subtitle>
                19,456 원 (월 전체 사용)
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-col>
        </v-list-item>
      </v-col>
      <v-col cols="4" md="4">
        <v-list-item>
          <v-col cols="12" md="12">
            <v-list-item-content>
              <v-list-item-title>접속 정보</v-list-item-title>
              <v-list-item-subtitle>아이디 : sandboxUser</v-list-item-subtitle>
              <v-list-item-subtitle>비밀번호 : sandboxPassword</v-list-item-subtitle>
            </v-list-item-content>
            <v-list-item-content style="padding-top: 0px">
              <v-list-item-title>생성 시간</v-list-item-title>
              <v-list-item-subtitle>2020-10-27 12:34:56</v-list-item-subtitle>
            </v-list-item-content>
            <v-list-item-content style="padding-top: 0px">
              <v-list-item-title>시작 시간</v-list-item-title>
              <v-list-item-subtitle>2020-10-27 18:34:56</v-list-item-subtitle>
            </v-list-item-content>
          </v-col>
        </v-list-item>
      </v-col>
    </v-row>
  </v-card>
</template>
<script>
export default {}
</script>
