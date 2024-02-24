<script>
  import { writable } from "svelte/store";

  const formData = writable({
    name: "",
    age: "",
    gender: "",
    mothersAge: "",
    FathersName: "",
    FathersAge: "",
    BloodTest:"",
    BloodCellCount:"",
    WhiteBloodCellCount:"",
    RespiratoryRate:"",
    HeartRate:"",
    BirthAsphyxia:"",
    GenesInMotherSide:"",
    InheritedFromFather:"",
    MaternalGene:"",
    PaternalGene:"",
    FollowUp:"",
    FolicAcid:"",
    HOSeriousMIllness:"",
    HORadiationExposure:"",
    HOSubstanceAbuse:"",
    AssistedConceptionIVFART:"",
    HistoryOfAnamolyInPrvsPreg:"",
    NumOfPrvsAbortion:"",
    BirthDefects:"",
    DisorderSubclass:""
  });

  let currentStep = 1;

  const handleSubmit = (event) => {
    console.log($formData);
    event.preventDefault();
  };

  const nextStep = () => {
    currentStep += 1;
  };

</script>

<main>
  <div class="container">
    <div class="heading">
      <div class="helixPic"></div>
      Helix
    </div>
    <div class="content">
      {#if currentStep === 1}
        <form on:submit={nextStep}>
          <div class="contentBox">
            <div class="List1">
              <input
                bind:value={$formData.name}
                class="box"
                type="text"
                id="name"
                placeholder="Name"
              />

              <input
                bind:value={$formData.age}
                class="box"
                type="number"
                id="age"
                placeholder="Age"
              />
            </div>
            <div class="list2">
              <select
                bind:value={$formData.gender}
                class="box"
                id="gender"
              >
                <option value="" disabled selected>Gender</option>
                <option>Male</option>
                <option>Female</option>
              </select>
              <input
                bind:value={$formData.mothersAge}
                class="box"
               
                type="number"
                id="mAge"
                placeholder="Mother's Age"
              />
            </div>
            <div class="list3">
              <input
                bind:value={$formData.FathersName}
                class="box"
                type="text"
                placeholder="Father's Name"
              />

              <input
                bind:value={$formData.FathersAge}
                class="box"
                type="number"
                id="fAge"
                placeholder="Father's Age"
              />
            </div>
          </div>
          <button type="submit">Next</button>
        </form>
      {/if}
      {#if currentStep === 2}
        <form on:submit={nextStep}>
          <div class="contentbox">
            <div class="list1">
                <select
                bind:value={$formData.genesinmotherside}
                class="box"
                id="bloodtest">
                <option value="" disabled selected>genes in mother's side</option>
                <option>yes</option>
                <option>no</option>
              </select>

              <select
                bind:value={$formData.inheritedfromfather}
                class="box"
                id="bloodtest">
                <option value="" disabled selected>inherited from father? </option>
                <option>yes</option>
                <option>no</option>
              </select>
            </div>
            <div class="list2">
                <select
                bind:value={$formData.maternalgene}
                class="box"
                id="bloodtest">
                <option value="" disabled selected>maternalgene</option>
                <option>yes</option>
                <option>no</option>
              </select>
              <select
                bind:value={$formData.paternalgene}
                class="box"
                id="bloodtest">
                <option value="" disabled selected>paternalgene</option>
                <option>yes</option>
                <option>no</option>
              </select>
            </div>
          </div>
          <button type="submit">next</button>
        </form>
      {/if}
      
      {#if currentStep === 3}
        <form on:submit={nextStep}>
          <div class="contentBox">
            <div class="List1">
                <select
                bind:value={$formData.BloodTest}
                class="box"
                id="BloodTest">
                <option value="" disabled selected>Blood Test</option>
                <option>Normal</option>
                <option>Inconclusive</option>
                <option>Slighty Abnormal</option>
              </select>

              <input
                bind:value={$formData.BloodCellCount}
                class="box"
                type="number"
                id="BloodCell"
                placeholder="Blood Cell Count"
              />
            </div>
            <div class="list2">
                <input
                bind:value={$formData.WhiteBloodCellCount}
                class="box"
                type="number"
                id="WhiteBloodCell"
                placeholder="White Blood Cell Count"
              />
              <select
                bind:value={$formData.RespiratoryRate}
                class="box"
                id="BloodTest">
                <option value="" disabled selected>Respiratory Rate</option>
                <option>Normal</option>
                <option>Tachypnea</option>
                
              </select>
            </div>
            <div class="list3">
                <select
                bind:value={$formData.HeartRateRate}
                class="box"
                id="BloodTest">
                <option value="" disabled selected>Heart Rate</option>
                <option>Normal</option>
                <option>Tachycardia</option>
                
              </select>

              <input
                bind:value={$formData.BirthAsphyxia}
                class="box"
                type="number"
                id="fAge"
                placeholder="Birth Asphyxia"
              />
            </div>
          </div>
          <button type="submit">Next</button>
        </form>
      {/if}
      {#if currentStep === 4 && $formData.gender === 'Female'}
        <form on:submit={nextStep}>
          <div class="contentBox">
            <div class="List1">
                <select
                bind:value={$formData.FollowUp}
                class="box"
                id="BloodTest">
                <option value="" disabled selected>Follow up</option>
                <option>High</option>
                <option>Low</option>
              </select>
              <select
                bind:value={$formData.BirthDefects}
                class="box"
                id="BloodTest">
                <option value="" disabled selected>Birth Defects</option>
                <option>Multiple</option>
                <option>Singular</option>
              </select>
              
            </div>
            <div class="list2">
                <select
                bind:value={$formData.HOSeriousMIllness}
                class="box"
                id="BloodTest">
                <option value="" disabled selected>H/O serious maternal illness</option>
                <option>Yes</option>
                <option>No</option>
              </select>
              <select
                bind:value={$formData.HORadiationExposure}
                class="box"
                id="BloodTest">
                <option value="" disabled selected>H/O radiation expoosure(x-ray)</option>
                <option>Yes</option>
                <option>No</option>
              </select>
            </div>
            <div class="list3">
                <select
                bind:value={$formData.HOSubstanceAbuse}
                class="box"
                id="BloodTest">
                <option value="" disabled selected>H/O substance abuse</option>
                <option>Yes</option>
                <option>No</option>
              </select>
            </div>
          </div>
          <button type="submit">Next</button>
        </form>
      {/if}
      {#if currentStep === 4 && $formData.gender !== 'Female'}
        <form on:submit={handleSubmit}>
          <div class="contentBox">
            <div class="List1">
                <select
                bind:value={$formData.FollowUp}
                class="box"
                id="BloodTest">
                <option value="" disabled selected>Follow up</option>
                <option>High</option>
                <option>Low</option>
              </select>
              <select
                bind:value={$formData.BirthDefects}
                class="box"
                id="BloodTest">
                <option value="" disabled selected>Birth Defects</option>
                <option>Multiple</option>
                <option>Singular</option>
              </select>
              
            </div>
            <div class="list2">
                <select
                bind:value={$formData.HOSeriousMIllness}
                class="box"
                id="BloodTest">
                <option value="" disabled selected>H/O serious maternal illness</option>
                <option>Yes</option>
                <option>No</option>
              </select>
              <select
                bind:value={$formData.HORadiationExposure}
                class="box"
                id="BloodTest">
                <option value="" disabled selected>H/O radiation expoosure(x-ray)</option>
                <option>Yes</option>
                <option>No</option>
              </select>
            </div>
            <div class="list3">
                <select
                bind:value={$formData.HOSubstanceAbuse}
                class="box"
                id="BloodTest">
                <option value="" disabled selected>H/O substance abuse</option>
                <option>Yes</option>
                <option>No</option>
              </select>
            </div>
          </div>
          <button type="submit">Next</button>
        </form>
      {/if}
      {#if currentStep === 5}
        <form on:submit={handleSubmit}>
          <div class="contentBox">
            <div class="List1">
                <select
                bind:value={$formData.HistoryOfAnamolyInPrvsPreg}
                class="box"
                id="BloodTest">
                <option value="" disabled selected>previous pregnancies anomaly</option>
                <option>Yes</option>
                <option>No</option>
              </select>

              <input placeholder="Number of prev abortion" bind:value={$formData.NumOfPrvsAbortion} type="number"/>
            </div>
            <div class="list2">
              <select
              bind:value={$formData.AssistedConceptionIVFART}
              class="box"
              id="BloodTest">
              <option value="" disabled selected>Assisted conception IVF/ART</option>
              <option>Yes</option>
              <option>No</option>
            </select>
            <select
                bind:value={$formData.FolicAcid}
                class="box"
                id="BloodTest">
                <option value="" disabled selected>Folic Acid</option>
                <option>Yes</option>
                <option>No</option>
              </select>
            </div>
          </div>
          <button type="submit">Next</button>
        </form>
        {/if}
      
    </div>
  </div>
</main>


