<script>
    let referenceWidth
    let referenceHeight

    let newWidth
    let newHeight
    
    let errorMessage

    const calculateHeight = () => {
        if(newWidth < 1) {
            errorMessage = "The new width has to be greater than 0"
            return
        }
        if(!newWidth){
            errorMessage = "Please enter new Width"
            return
        }
        if(!referenceHeight || !referenceWidth){
            errorMessage = "Reference values missing"
            return
        }
        if(referenceWidth < 1) {
            errorMessage = "The reference width has to be greater than 0"
            return
        }

        let ratio = referenceHeight / referenceWidth
        newHeight = Math.round(newWidth * ratio)
        errorMessage = false
    }

    const calculateWidth = () => {
        if(newHeight < 1) {
            errorMessage = "The new height has to be greater than 0"
            return
        }
        if(!newHeight){
            errorMessage = "Please enter new Width"
            return
        }
        if(!referenceHeight || !referenceWidth){
            errorMessage = "Reference values missing"
            return
        }
        if(referenceHeight < 1) {
            errorMessage = "The reference height has to be greater than 0"
            return
        }

        let ratio = referenceWidth/ referenceHeight
        newWidth = Math.round(newHeight * ratio)
        errorMessage = false
    }

</script>

<div class="container">
    <!-- Row 1 -->
    <div class="columns is-centered is-mobile">
        <div class="column is-one-quarter">
            <div class="field">
                <div class="control has-floating-label">
                    <input class="input is-medium with-floating-label mt-2" id="referenceWidth" type="number" placeholder=" " bind:value={referenceWidth}>
                    <label class="label is-medium is-floating-label has-text-grey" for="referenceWidth">Reference Width</label>
                </div>
            </div>
        </div>
        <div class="column is-one-quarter">
            <div class="field">
                <div class="control has-floating-label">
                    <input class="input is-medium with-floating-label mt-2" type="number" id="referenceHeight" placeholder=" " bind:value="{referenceHeight}">
                    <label class="label is-medium has-text-grey is-floating-label" for="referenceHeight">Reference Height</label>
                </div>
            </div>
        </div>
    </div>

    <!-- Row 2 -->
    <div class="columns is-centered is-mobile">
        <div class="column is-one-quarter">
            <div class="field">
                <div class="control has-floating-label">
                    <input class="input is-medium with-floating-label mt-2" type="number" id="newWidth" placeholder=" " bind:value="{newWidth}" on:blur={calculateHeight}>
                    <label class="label is-medium has-text-grey is-floating-label" for="newWidth">New Width</label>
                </div>
            </div>
        </div>
        <div class="column is-one-quarter">
            <div class="field">
                <div class="control has-floating-label">
                    <input class="input is-medium with-floating-label mt-2" type="number" id="newHeight" placeholder=" " bind:value="{newHeight}" on:blur={calculateWidth}>
                    <label class="label is-medium has-text-grey is-floating-label" for="newHeight">New Height</label>
                </div>
            </div>
        </div>
    </div>

    {#if errorMessage }
	    <p class="p-2 tag is-danger is-medium">{errorMessage}</p>
    {/if}

</div>
