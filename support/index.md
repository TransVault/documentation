# Support
Whether you have a general 'how to' question, questions about a specific report, or anything else, we're available to help you.




# Feedback

We are very keen to hear about your experiences. Any improvements, suggestions, and comments are welcome. We review every piece of
feedback that we receive, and if we need to we'll reach out to you to get additional information.

<center><button type="button" class="btn btn-primary" data-toggle="modal" data-target="#feedbackModal">Give us your feedback!</button></center>

<!-- feedbackModal -->
<div id="feedbackModal" class="modal fade">
    <div class="modal-dialog">
        <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal" aria-hidden="true">&times;</button>
                <h3 class="modal-title">Feedback</h3>
            </div>
            <form>
            <div class="modal-body">
              <b>Email</b>
              <input class="form-control" type="email" id="mEmail" placeholder="name@company.com" required>
              <br>
              <b>Feedback</b>
              <textarea class="form-control" id="mFeedback" rows="3" placeholder="Any improvements, suggestions, and comments"></textarea>
              <br>
              <p id="info"></p>
            </div>
            <div class="modal-footer">
                <button type="button" class="btn btn-default" data-dismiss="modal">Close</button>
                <button type="button" class="btn btn-primary" onclick="myFunction()">Send</button>
            </div>
            </form>
        </div>
    </div>
</div>

<script src="https://smtpjs.com/v3/smtp.js"></script>
<script>
function myFunction() {
  console.log(mFeedback.value);
  console.log(mEmail.value);

  Email.send({
    SecureToken : "494246b5-9be7-4736-aabf-56db44de940e",
    To : 'inflight.support@transvault.com',
    From : "tcp@transvault.com",
    Subject : "Help Feedback - " + mEmail.value,
    Body : mFeedback.value
    }).then(
        document.getElementById("info").innerHTML = "Submitted"
    );
}
</script>
