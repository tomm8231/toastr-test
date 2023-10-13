<script>
    import toastr from 'toastr'
    import 'toastr/build/toastr.css'

    toastr.options = {
  "closeButton": true,
  "debug": false,
  "newestOnTop": true,
  "progressBar": false,
  "positionClass": "toast-top-right",
  "preventDuplicates": false,
  "onclick": null,
  "showDuration": "300",
  "hideDuration": "1000",
  "timeOut": "5000",
  "extendedTimeOut": "1000",
  "showEasing": "swing",
  "hideEasing": "linear",
  "showMethod": "fadeIn",
  "hideMethod": "fadeOut"
}

let infoText = ""

function showInfo() {
    toastr.options.closeButton = true   
    toastr.info("Button 1 pushed")
    infoText = "Info given"
}

function showWarning() {
    toastr.options.closeButton = true
    toastr.warning("WARNING GIVEN!")
    infoText = "Warning given"
}

function clearToastsNoAnimation() {
    toastr.remove()
    infoText = "Toasts removed without any animations"
}

function clearToastsAnimated() {
    toastr.clear()
    infoText = "Toasts removed with a fading animation"
}

function showError() {
    toastr.options.closeButton = false
    toastr.error("ERROR!")
    infoText = "Error given"
}

</script>

<button on:click={showInfo}>Show info</button>
<button on:click={showWarning}>Show warning</button>
<button on:click={showError}>Show warning</button>
<button on:click={clearToastsNoAnimation}>Clear - no animation</button>
<button on:click={clearToastsAnimated}>Clear - animated</button>

<p>{infoText}</p>