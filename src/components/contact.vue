<template>
    <div id="app-contact" class="contact-us container hero hero--purple">
        <div class="row">
            <h2 class="col-sm-6 text-center">Contact Us</h2>
            <form class="form col-sm-6 col-md-4">
                <fieldset>
                    <div class="input-group row">
                        <label class="col-sm-6 col-md-3">Who are you?</label>
                        <input class="input col-sm-6 col-md-3" placeholder="John Doe (The usual placeholder)" type="text"/>
                    </div>
                    <div class="input-group row">
                        <label class="col-sm-6 col-md-3">Where can we spam you?</label>
                        <input class="input col-sm-6 col-md-3" placeholder="john.doe@e-male.com" type="email"/>
                    </div>
                    <div class="input-group row">
                        <label class="col-sm-6 col-md-3">Where can we you at night?</label>
                        <input class="input col-sm-6 col-md-3" placeholder="+1 800 123 4567" type="text"/>
                    </div>
                    <div class="input-group row">
                        <label class="col-sm-6 col-md-3">What do you want to tell us?</label>
                        <textarea name="message" rows="4" class="input col-sm-6 col-md-3" placeholder="My website looks horrible. Pimp my website bruh." type="text" />
                    </div>
                    <div class="input-group row">
                        <input class="button button--inverted" type="reset" value="Reset the form"/>
                        <input class="button" type="submit" value="Send your message now"/>
                    </div>
                </fieldset>
            </form>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>

</style>