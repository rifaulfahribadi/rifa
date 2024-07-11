<template>
  <div class="edrea_tm_section" id="contact">
    <div class="section_inner">
      <div class="edrea_tm_contact">
        <div class="edrea_tm_main_title">
          <h3>Get in <span class="coloring">Touch</span></h3>
        </div>
        <div class="wrapper">
          <div class="left">
            <ul>
              <li>
                <div class="list_inner">
                  <i class="icon-location"></i>
                  <span><a href="#" class="href_location">Jakarta, Indonesia</a></span>
                </div>
              </li>
              <li>
                <div class="list_inner">
                  <i class="icon-phone"></i>
                  <span><a href="https://wa.me/6283839075330" target="_blank">62 838 3907 5330</a></span>
                </div>
              </li>
              <li>
                <div class="list_inner">
                  <i class="icon-mail-1"></i>
                  <span><a href="mailto:rifaulfahribadi16@gmail.com"
                      target="_blank">rifaulfahribadi16@gmail.com</a></span>
                </div>
              </li>
              <li>
                <div class="list_inner">
                  <i class="icon-instagram-3"></i>
                  <span><a href="https://www.instagram.com/rifaulfahribadi/" target="_blank">@rifaulfahribadi</a></span>
                </div>
              </li>
            </ul>
          </div>
          <div class="right">
            <div class="fields">
              <form action="https://formspree.io/f/xldrddpn" method="post" class="contact_form" id="contact_form">
                <div class="returnmessage" data-success="Your message has been received, We will contact you soon.">
                </div>
                <div class="empty_notice">
                  <span>Please Fill Required Fields</span>
                </div>
                <div class="first">
                  <ul>
                    <li>
                      <div class="list_inner">
                        <input name="name" id="name" type="text" placeholder="Name" autocomplete="off" />
                      </div>
                    </li>
                    <li>
                      <div class="list_inner">
                        <input name="email" id="email" type="email" placeholder="Email" autocomplete="off" />
                      </div>
                    </li>
                  </ul>
                </div>
                <div class="last">
                  <textarea name="message" id="message" placeholder="Message"></textarea>
                </div>
                <div class="edrea_tm_button">
                  <button id="send_message" class="a" type="submit">Send Message</button>
                </div>

                <!-- If you want change mail address to yours, just open "modal" folder >> contact.php and go to line 4 and change detail to yours.  -->
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: `ContactComponent`,
};
</script>
