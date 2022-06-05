<template>
  <div class="home">
    <!-- As a heading -->
    <nav class="navbar navbar-light bg-light">
      <div class="container-fluid">
        <a
          class="navbar-brand"
          href="https://github.com/jungyitsai/manchu_input_transliteration"
          target="_blank"
          >Manchu Input Transliteration Repository</a
        >
      </div>
    </nav>
    <div class="container">
      <div class="row mt-2">
        <div class="col">
          <div class="row">
            <ul class="nav nav-tabs">
              <li class="nav-item">
                <a
                  class="nav-link"
                  :class="{ active: convertMethod == 'Möllendorff' }"
                  href="#"
                  @click.prevent="convertMethod = 'Möllendorff'"
                  >Möllendorff</a
                >
              </li>
              <li class="nav-item">
                <a
                  class="nav-link"
                  :class="{ active: convertMethod == 'Abkai' }"
                  href="#"
                  @click.prevent="convertMethod = 'Abkai'"
                  >Abkai</a
                >
              </li>
              <li class="nav-item">
                <a
                  class="nav-link"
                  :class="{ active: convertMethod == 'CMCD' }"
                  href="#"
                  @click.prevent="convertMethod = 'CMCD'"
                  >CMCD</a
                >
              </li>
            </ul>
          </div>
          <div class="row">
            <textarea rows="10" v-model="inputText"></textarea>
          </div>
        </div>
        <div class="col">
          <div class="row">
            <ul class="nav nav-tabs">
              <li class="nav-item">
                <a class="nav-link active" aria-current="page" href="#"
                  >Manchu Script</a
                >
              </li>
            </ul>
          </div>

          <div class="row">
            <textarea
              id="manchu_text"
              rows="10"
              v-model="outputText"
              readonly
            ></textarea>
          </div>
        </div>
      </div>

      <div class="row mt-2 mb-5">
        <h2 class="px-0">Manchu transliterations</h2>
        <table id="myTable" class="wikitable">
          <tbody>
            <tr>
              <th><b>Sound (IPA)</b></th>
              <th><b>Möllendorff</b></th>
              <th><b>Abkai</b></th>
              <th><b>CMCD</b></th>
              <th>
                Manchu and
                <a
                  href="https://en.m.wiktionary.org/wiki/Unicode"
                  title="Unicode"
                  >Unicode</a
                >
              </th>
              <th>Notes</th>
            </tr>
            <tr>
              <td><span class="IPA">[a]</span></td>
              <td>a</td>
              <td>a</td>
              <td>a</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A0%A0"
                    title="ᠠ"
                    >ᠠ</a
                  ></span
                >
                1820
              </td>
            </tr>
            <tr>
              <td><span class="IPA">[ə]</span></td>
              <td>e</td>
              <td>e</td>
              <td>e</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%9D"
                    title="ᡝ"
                    >ᡝ</a
                  ></span
                >
                185D
              </td>
            </tr>
            <tr>
              <td><span class="IPA">[i]</span></td>
              <td>
                i<sup id="cite_ref-y_1-0" class="reference"
                  ><a href="#cite_note-y-1">[1]</a></sup
                >
              </td>
              <td>i</td>
              <td>
                i<sup id="cite_ref-y_1-1" class="reference"
                  ><a href="#cite_note-y-1">[1]</a></sup
                >
              </td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%B3"
                    title="ᡳ"
                    >ᡳ</a
                  ></span
                >
                1873
              </td>
            </tr>
            <tr>
              <td><span class="IPA">[ɨ]</span></td>
              <td>
                y<sup id="cite_ref-yy_2-0" class="reference"
                  ><a href="#cite_note-yy-2">[2]</a></sup
                >
              </td>
              <td>yʻ</td>
              <td>y</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%9F"
                    title="ᡟ"
                    >ᡟ</a
                  ></span
                >
                185F
              </td>
              <td>only used in loanwords</td>
            </tr>
            <tr>
              <td><span class="IPA">[ɔ]</span></td>
              <td>o</td>
              <td>o</td>
              <td>o</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A0%A3"
                    title="ᠣ"
                    >ᠣ</a
                  ></span
                >
                1823
              </td>
            </tr>
            <tr>
              <td><span class="IPA">[u]</span></td>
              <td>u</td>
              <td>u</td>
              <td>u</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%A0"
                    title="ᡠ"
                    >ᡠ</a
                  ></span
                >
                1860
              </td>
            </tr>
            <tr>
              <td><span class="IPA">[ʊ]</span></td>
              <td>ū</td>
              <td>v</td>
              <td>uu</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%A1"
                    title="ᡡ"
                    >ᡡ</a
                  ></span
                >
                1861
              </td>
            </tr>
            <tr>
              <td><span class="IPA">[n]</span></td>
              <td>n</td>
              <td>n</td>
              <td>n</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A0%A8"
                    title="ᠨ"
                    >ᠨ</a
                  ></span
                >
                1828
              </td>
            </tr>
            <tr>
              <td><span class="IPA">[ŋ]</span></td>
              <td>ng</td>
              <td>ng</td>
              <td>ng</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A0%A9"
                    title="ᠩ"
                    >ᠩ</a
                  ></span
                >
                1829
              </td>
            </tr>
            <tr>
              <td>
                <span class="IPA">[qʰ]</span> &amp;
                <span class="IPA">[kʰ]</span>
              </td>
              <td>k</td>
              <td>k</td>
              <td>k</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%B4"
                    title="ᡴ"
                    >ᡴ</a
                  ></span
                >
                1874
              </td>
            </tr>
            <tr>
              <td>
                <span class="IPA">[q]</span> &amp; <span class="IPA">[k]</span>
              </td>
              <td>g</td>
              <td>g</td>
              <td>g</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%A4"
                    title="ᡤ"
                    >ᡤ</a
                  ></span
                >
                1864
              </td>
            </tr>
            <tr>
              <td>
                <span class="IPA">[χ]</span> &amp; <span class="IPA">[x]</span>
              </td>
              <td>h</td>
              <td>h</td>
              <td>h</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%A5"
                    title="ᡥ"
                    >ᡥ</a
                  ></span
                >
                1865
              </td>
            </tr>
            <tr>
              <td><span class="IPA">[p]</span></td>
              <td>b</td>
              <td>b</td>
              <td>b</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A0%AA"
                    title="ᠪ"
                    >ᠪ</a
                  ></span
                >
                182A
              </td>
            </tr>
            <tr>
              <td><span class="IPA">[pʰ]</span></td>
              <td>p</td>
              <td>p</td>
              <td>p</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%A6"
                    title="ᡦ"
                    >ᡦ</a
                  ></span
                >
                1866
              </td>
            </tr>
            <tr>
              <td>
                <span class="IPA">[s]</span>;
                <span class="IPA">[ɕ]</span> before <span class="IPA">[i]</span>
              </td>
              <td>s</td>
              <td>s</td>
              <td>s</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A0%B0"
                    title="ᠰ"
                    >ᠰ</a
                  ></span
                >
                1830
              </td>
            </tr>
            <tr>
              <td>
                <span class="IPA">[ʃ]</span>;
                <span class="IPA">[ɕ]</span> before <span class="IPA">[i]</span>
              </td>
              <td>š</td>
              <td>x</td>
              <td>
                sh<sup id="cite_ref-yyy_3-0" class="reference"
                  ><a href="#cite_note-yyy-3">[3]</a></sup
                >
              </td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%A7"
                    title="ᡧ"
                    >ᡧ</a
                  ></span
                >
                1867
              </td>
            </tr>
            <tr>
              <td><span class="IPA">[tʰ]</span></td>
              <td>t</td>
              <td>t</td>
              <td>t</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%A8"
                    title="ᡨ"
                    >ᡨ</a
                  ></span
                >
                1868
              </td>
            </tr>
            <tr>
              <td><span class="IPA">[t]</span></td>
              <td>d</td>
              <td>d</td>
              <td>d</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%A9"
                    title="ᡩ"
                    >ᡩ</a
                  ></span
                >
                1869
              </td>
            </tr>
            <tr>
              <td><span class="IPA">[l]</span></td>
              <td>l</td>
              <td>l</td>
              <td>l</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A0%AF"
                    title="ᠯ"
                    >ᠯ</a
                  ></span
                >
                182F
              </td>
            </tr>
            <tr>
              <td><span class="IPA">[m]</span></td>
              <td>m</td>
              <td>m</td>
              <td>m</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A0%AE"
                    title="ᠮ"
                    >ᠮ</a
                  ></span
                >
                182E
              </td>
            </tr>
            <tr>
              <td>
                <span class="IPA">[t͡ʃʰ]</span>;
                <span class="IPA">[t͡ɕʰ]</span> before
                <span class="IPA">[i]</span>
              </td>
              <td>c</td>
              <td>q</td>
              <td>ch</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A0%B4"
                    title="ᠴ"
                    >ᠴ</a
                  ></span
                >
                1834
              </td>
            </tr>
            <tr>
              <td>
                <span class="IPA">[t͡ʃ]</span>;
                <span class="IPA">[t͡ɕ]</span> before
                <span class="IPA">[i]</span>
              </td>
              <td>j</td>
              <td>j</td>
              <td>zh</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A0%B5"
                    title="ᠵ"
                    >ᠵ</a
                  ></span
                >
                1835
              </td>
            </tr>
            <tr>
              <td><span class="IPA">[j]</span></td>
              <td>y</td>
              <td>y</td>
              <td>y</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A0%B6"
                    title="ᠶ"
                    >ᠶ</a
                  ></span
                >
                1836
              </td>
            </tr>
            <tr>
              <td><span class="IPA">[r]</span></td>
              <td>r</td>
              <td>r</td>
              <td>r</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%B5"
                    title="ᡵ"
                    >ᡵ</a
                  ></span
                >
                1875
              </td>
            </tr>
            <tr>
              <td><span class="IPA">[f]</span></td>
              <td>f</td>
              <td>f</td>
              <td>f</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%B6"
                    title="ᡶ"
                    >ᡶ</a
                  ></span
                >
                1876
              </td>
            </tr>
            <tr>
              <td><span class="IPA">[w]</span></td>
              <td>w</td>
              <td>w</td>
              <td>w</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A0%B8"
                    title="ᠸ"
                    >ᠸ</a
                  ></span
                >
                1838
              </td>
            </tr>
            <tr>
              <td><span class="IPA">[kʰ]</span></td>
              <td>k῾</td>
              <td>kʻ</td>
              <td>kk</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A0%BA"
                    title="ᠺ"
                    >ᠺ</a
                  ></span
                >
                183A
              </td>
              <td>only used in loanwords</td>
            </tr>
            <tr>
              <td><span class="IPA">[k]</span></td>
              <td>g῾</td>
              <td>gʻ</td>
              <td>gg</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%AC"
                    title="ᡬ"
                    >ᡬ</a
                  ></span
                >
                186C
              </td>
              <td>only used in loanwords</td>
            </tr>
            <tr>
              <td><span class="IPA">[x]</span></td>
              <td>h῾</td>
              <td>hʻ</td>
              <td>hh</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%AD"
                    title="ᡭ"
                    >ᡭ</a
                  ></span
                >
                186D
              </td>
              <td>only used in loanwords</td>
            </tr>
            <tr>
              <td><span class="IPA">[tsʰ]</span></td>
              <td>
                ts῾<sup id="cite_ref-yy_2-1" class="reference"
                  ><a href="#cite_note-yy-2">[2]</a></sup
                >
              </td>
              <td>c</td>
              <td>c</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%AE"
                    title="ᡮ"
                    >ᡮ</a
                  ></span
                >
                186E
              </td>
              <td>only used in loanwords</td>
            </tr>
            <tr>
              <td><span class="IPA">[tsʰ]</span></td>
              <td>ts</td>
              <td>cyʻ</td>
              <td>cy</td>
              <td><span class="Mong" lang="mnc">ᡮᡟ</span> 186E 185F</td>
              <td>only used in loanwords</td>
            </tr>
            <tr>
              <td><span class="IPA">[t͡s]</span></td>
              <td>dz</td>
              <td>z</td>
              <td>z</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%AF"
                    title="ᡯ"
                    >ᡯ</a
                  ></span
                >
                186F
              </td>
              <td>only used in loanwords</td>
            </tr>
            <tr>
              <td><span class="IPA">[ʐ]</span></td>
              <td>ž</td>
              <td>rʻ</td>
              <td>rr</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%B0"
                    title="ᡰ"
                    >ᡰ</a
                  ></span
                >
                1870
              </td>
              <td>only used in loanwords</td>
            </tr>
            <tr>
              <td><span class="IPA">[sɨ]</span></td>
              <td>sy</td>
              <td>syʻ</td>
              <td>sy</td>
              <td><span class="Mong" lang="mnc">ᠰᡟ</span> 1830 185F</td>
              <td>only used in loanwords</td>
            </tr>
            <tr>
              <td><span class="IPA">[tʂʰ]</span></td>
              <td>c῾</td>
              <td>q</td>
              <td>ch</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%B1"
                    title="ᡱ"
                    >ᡱ</a
                  ></span
                >
                1871
              </td>
              <td>only used in loanwords</td>
            </tr>
            <tr>
              <td><span class="IPA">[tʂʰɨ]</span></td>
              <td>c῾y</td>
              <td>qyʻ</td>
              <td>chy</td>
              <td><span class="Mong" lang="mnc">ᡱᡳ</span> 1871 1873</td>
              <td>only used in loanwords</td>
            </tr>
            <tr>
              <td><span class="IPA">[tʂ]</span></td>
              <td>j</td>
              <td>zh</td>
              <td>zh</td>
              <td>
                <span class="Mong" lang="mnc"
                  ><a
                    href="https://en.m.wiktionary.org/wiki/%E1%A1%B7"
                    title="ᡷ"
                    >ᡷ</a
                  ></span
                >
                1877
              </td>
              <td>only used in loanwords</td>
            </tr>
            <tr>
              <td><span class="IPA">[tʂɨ]</span></td>
              <td>jy</td>
              <td>jyʻ</td>
              <td>zhy</td>
              <td><span class="Mong" lang="mnc">ᡷᡳ</span> 1877 1873</td>
              <td>only used in loanwords</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
    <div class="footer">
      &copy;
      <span>Jung-Yi, Tsai </span>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "HomeView",
  data() {
    return {
      inputText: "",
      convertMethod: "Möllendorff",
      convertMethodList: ["Möllendorff", "Abkai", "CMCD"],
      mollenCharList: [],
      abkaiCharList: [],
      cmcdCharList: [],
      manchuCharList: [],
      query: "",
    };
  },
  mounted() {
    this.query = this.$route.query;
    // console.log("hi");
    //gets table
    var oTable = document.getElementById("myTable");
    // console.log("oTable", oTable);

    //gets rows of table
    var rowLength = oTable.rows.length;
    console.log("rowLength", rowLength);
    //loops through rows
    for (let i = 1; i < rowLength; i++) {
      //gets cells of current row
      let oCells = oTable.rows.item(i).cells;

      //gets amount of cells of current row
      // let cellLength = oCells.length;

      //loops through each cell in current row
      for (let j = 1; j < 5; j++) {
        /* get your cell info here */
        /* var cellVal = oCells.item(j).innerHTML; */
        let cellVal = oCells.item(j).innerText;

        const regex = /\[.+\]/gm;
        const subst = ``;

        // The substituted value will be contained in the result variable
        const result = cellVal.replace(regex, subst);
        cellVal = result;

        // console.log('Substitution result: ', result);

        if (j == 4) {
          cellVal = cellVal.split(" ")[0];
          // console.log("cellVal", cellVal);
        }

        // build char mapping table
        if (j == 1) {
          this.mollenCharList.push(cellVal);
        } else if (j == 2) {
          this.abkaiCharList.push(cellVal);
        } else if (j == 3) {
          this.cmcdCharList.push(cellVal);
        } else if (j == 4) {
          this.manchuCharList.push(cellVal);
        }
      }
    }

    // parse query for converting single word
    if (this.query["word"] && this.query["input_method"]) {
      console.log(this.query);
      let is_match = this.convertMethodList.indexOf(this.query["input_method"]);

      console.log(is_match);
      if (is_match >= 0) {
        this.convertMethod = this.query["input_method"];
      } else {
        return;
      }

      // if not single word, then return
      let seq_len = this.query["word"].split(" ");
      console.log(seq_len);
      if (seq_len > 1) {
        return;
      }

      this.inputText = this.query["word"];
    }
  },
  computed: {
    outputText: function () {
      return this.convertText();
    },
  },
  methods: {
    convertText() {
      let converTable = -1;
      switch (this.convertMethod) {
        case "Möllendorff":
          converTable = this.mollenCharList;
          break;
        case "Abkai":
          converTable = this.abkaiCharList;
          break;
        case "CMCD":
          converTable = this.cmcdCharList;
          break;
        default:
          converTable = this.mollenCharList;
      }

      let cleanInputText = this.inputText.toLowerCase();
      let charList = cleanInputText.split("");
      let convCharList = [];
      let skipIndexList = [];

      for (let index = 0; index < charList.length; ++index) {
        if (skipIndexList.includes(index)) {
          continue;
        }
        let item = charList[index];

        // console.log(item, index);

        if (item === " " || item === "\n") {
          convCharList.push(item);
          continue;
        }

        // three char case
        let endIndex = Math.min(index + 3, charList.length);
        let subStr = cleanInputText.slice(index, endIndex);
        if (subStr.length == 3) {
          let subStrIndex = converTable.indexOf(subStr);
          // console.log("subStrIndex", subStrIndex, subStr);
          if (subStrIndex >= 0) {
            // console.log("subStrIndex", this.manchuCharList[subStrIndex]);
            convCharList.push(this.manchuCharList[subStrIndex]);
            skipIndexList.push(index + 1);
            skipIndexList.push(index + 2);
            continue;
          }
        }

        // two char case
        endIndex = Math.min(index + 2, charList.length);
        subStr = cleanInputText.slice(index, endIndex);
        if (subStr.length == 2) {
          let subStrIndex = converTable.indexOf(subStr);
          // console.log("subStrIndex", subStrIndex, subStr);
          if (subStrIndex >= 0) {
            // console.log("subStrIndex", this.manchuCharList[subStrIndex]);
            convCharList.push(this.manchuCharList[subStrIndex]);
            skipIndexList.push(index + 1);
            continue;
          }
        }

        // one char case
        let subStrIndex = converTable.indexOf(item);
        if (subStrIndex >= 0) {
          convCharList.push(this.manchuCharList[subStrIndex]);
        }
      }

      return convCharList.join("");
    },
  },
};
</script>

<style src="@/assets/css/fontface/fontface.css"></style>
<style lang="css" scoped>
table,
th,
td {
  border: 1px solid black;
  border-collapse: collapse;
  padding-left: 3px;
  font-size: 16px;
}
a {
  text-decoration: none;
}

.footer,
.push {
  height: 50px; /* .push must be the same height as .footer */
}
.footer {
  background-color: #dddddd;
  padding: 15px;
}
</style>
