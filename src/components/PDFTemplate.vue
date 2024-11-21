<template>
  <div class="mt-5">
    <div ref="pdfContent">

      <!-- Main Text Page -->
      <div class="page border border-black text-content">
        <!-- Header for the First Page -->
        <div v-if="showHeaderOnFirstPage" class="d-flex justify-content-evenly align-items-center border-bottom">
          <div class="text-center">
            <p class="fw-bold">Report Requested By</p>
            <p class="">Sandy Lane Pet Clinic</p>
            <p class="">Dr. Lee</p>
          </div>
          <div class="text-center">
            <img src="../assets/company.svg" alt="Company Logo" class="rounded logo" />
          </div>
          <div class="text-center">
            <p class="fw-bold">Report Provided By</p>
            <p class="">CompanyName@gmail.com</p>
          </div>
        </div>
        <!-- Text Content -->
        <div class="row p-2 border-bottom border-2 mb-3">
          <div class="col-4">
            <h6><span class="badge text-bg-secondary">Example heading</span></h6>
          </div>
          <div class="col-4">Submitted:10/26/2024</div>
          <div class="col-4">Report On:11/9/2024</div>
          <div class="mt-2">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident harum fuga soluta, beatae ratione sequi
            cum
            dolorem fugit nam natus architecto dolor molestias tempora officiis perspiciatis aspernatur ipsam aliquid
            modi!
          </div>
        </div>
        <div class="p-2 border-bottom border-2 mb-3">
          <div class="d-flex justify-content-between align-items-center">
            <div>
              <h6><span class="badge text-bg-secondary">Example heading</span></h6>
            </div>
            <div></div>
            <div></div>
          </div>
          <div class="mt-2">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident harum fuga soluta, beatae ratione sequi
            cum
            dolorem fugit nam natus architecto dolor molestias tempora officiis perspiciatis aspernatur ipsam aliquid
            modi!
          </div>
        </div>
        <div class="p-2 mb-3">
          <div class="d-flex justify-content-between align-items-center">
            <div>
              <h6><span class="badge text-bg-secondary">Example heading</span></h6>
            </div>
            <div></div>
            <div></div>
          </div>
          <div class="my-3">
            <p class="fw-bold">Findings</p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident harum fuga soluta, beatae ratione sequi
            cum
            dolorem fugit nam natus architecto dolor molestias tempora officiis perspiciatis aspernatur ipsam aliquid
            modi!
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque ab debitis consequatur perspiciatis
            laboriosam illum
            accusamus? Rem nisi numquam harum, earum voluptate tenetur accusantium amet nihil facilis recusandae
            voluptates dicta.
          </div>
          <div class="my-3">
            <p class="fw-bold">Interpretation</p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident harum fuga soluta, beatae ratione sequi
            cum
            dolorem fugit nam natus architecto dolor molestias tempora officiis perspiciatis aspernatur ipsam aliquid
            modi!
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque ab debitis consequatur perspiciatis
            laboriosam illum
            accusamus? Rem nisi numquam harum, earum voluptate tenetur accusantium amet nihil facilis recusandae
            voluptates dicta.
          </div>
          <div class="my-3">
            <p class="fw-bold">Recommendations</p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident harum fuga soluta, beatae ratione sequi
            cum
            dolorem fugit nam natus architecto dolor molestias tempora officiis perspiciatis aspernatur ipsam aliquid
            modi!
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque ab debitis consequatur perspiciatis
            laboriosam illum
            accusamus? Rem nisi numquam harum, earum voluptate tenetur accusantium amet nihil facilis recusandae
            voluptates dicta.
          </div>
        </div>
        <!-- Footer For First Page -->
        <div class="d-flex justify-content-evenly align-items-center mt-auto">
          <div class="text-center">
            <span class="text-secondary">Page 1 of {{ totalPages }}</span>
          </div>
          <div class="text-center">
            <p>CompanyName</p>
            <p>Copyright ©2024 - All Rights Reserved</p>
          </div>
          <div class="text-center">
            <img src="../assets/company.svg" alt="Company Logo" class="logo image-fluid" />
          </div>
        </div>
      </div>

      <!-- Image Pages -->
      <div v-for="(page, pageIndex) in imagePages" :key="pageIndex" class="page border border-black">
        <div class="row">
          <div v-for="(image, index) in page" :key="index" class="col-6 mb-2">
            <!-- <img :src="image.download_url" class="img-fluid" alt="Image"  style="height: auto; max-width: 100%;" /> -->
            <div class="card shadow-sm my-2">
              <img :src="image.download_url" :alt="image.author" class="card-img-top image-frame" />
            </div>
          </div>
        </div>

        <!-- Footer for Image Pages -->
        <div class="d-flex justify-content-evenly align-items-center p-1 mt-auto">
          <div class="text-center">
            <span class="text-secondary">Page {{ pageIndex + 2 }} of {{ totalPages }}</span>
          </div>
          <div class="text-center">
            <p>CompanyName</p>
            <p>Copyright ©2024 - All Rights Reserved</p>
          </div>
          <div class="text-center">
            <img src="../assets/company.svg" alt="Company Logo" class="logo image-fluid" />
          </div>
        </div>
      </div>

      <!-- Signature Page -->
      <div v-if="showSignaturePage" class="page border border-black">
        <div class="border-bottom mt-auto pb-2">
          <p class="fw-bold">Signature</p>
          <div class="d-flex justify-content-evenly align-items-center">
            <div class="text-end">
              <img src="../assets/company.svg" alt="Company Logo" class="logo" />
            </div>
            <div class="text-end">
              <p class="fw-bold fs-3">CompanyFullName</p>
            </div>
            <div class="text-end">
              <p class="fw-bold">Report Requested By</p>
              <p class="">Sandy Lane Pet Clinic</p>
              <p class="">Dr. Lee</p>
            </div>
          </div>
          <div>
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Illum ex voluptatum obcaecati aperiam incidunt?
            Nobis veritatis voluptatum, odit iusto pariatur aspernatur tempora amet numquam porro veniam eveniet nihil
            ea vitae.Lorem ipsum dolor sit, amet consectetur adipisicing elit. Id accusamus molestias at, cupiditate,
            repudiandae
            corrupti maiores sed cumque delectus ratione dicta excepturi minus pariatur repellendus fugiat dignissimos
            et quos. Impedit? Lorem ipsum dolor sit amet consectetur adipisicing elit. Ex temporibus blanditiis quis
            sapiente quod dolore
            commodi illum dolorem sint rem amet, facilis labore? Magni, natus eos ut voluptatum temporibus soluta.
          </div>
        </div>

        <!-- Footer for Signature Page -->
        <div class="d-flex justify-content-evenly align-items-center p-1">
          <div class="text-center">
            <span class="text-secondary">Page {{ totalPages }} of {{ totalPages }}</span>
          </div>
          <div class="text-center">
            <p>CompanyName</p>
            <p>Copyright ©2024 - All Rights Reserved</p>
          </div>
          <div class="text-center">
            <img src="../assets/company.svg" alt="Company Logo" class="logo image-fluid" />
          </div>
        </div>
      </div>
    </div>

    <!-- Generate PDF Button -->
    <div class="text-center my-5">
      <button class="btn btn-primary" @click="generatePdf">Generate PDF</button>
    </div>
  </div>
</template>

<script>
import { ref, onMounted } from "vue";
import html2pdf from "html2pdf.js";

export default {
  setup() {
    const pdfContent = ref(null);
    const images = ref([]);
    const imagePages = ref([]);
    const showSignaturePage = ref(false);
    const totalPages = ref(0);
    const showHeaderOnFirstPage = true; // To manage the header visibility

    const MAX_IMAGES_PER_ROW = 2;
    const MAX_ROWS_PER_PAGE = 4;

    // Fetch and process images
    const loadImages = async () => {
      const response = await fetch("https://picsum.photos/v2/list?limit=12");
      images.value = await response.json();
      prepareImagePages();
      calculateTotalPages();
    };

    const prepareImagePages = () => {
      const imagesPerPage = MAX_IMAGES_PER_ROW * MAX_ROWS_PER_PAGE;

      imagePages.value = [];
      for (let i = 0; i < images.value.length; i += imagesPerPage) {
        imagePages.value.push(images.value.slice(i, i + imagesPerPage));
      }
    };

    const calculateTotalPages = () => {
      const numImagePages = imagePages.value.length;
      showSignaturePage.value = true; // Always include the signature page
      totalPages.value = 1 + numImagePages + (showSignaturePage.value ? 1 : 0); // Text page + image pages + signature page
    };

    // Generate the PDF
    const generatePdf = () => {
      const element = pdfContent.value;
      const options = {
        margin: 0.1,
        filename: "report.pdf",
        image: { type: "jpeg", quality: 0.8 }, // Adjust quality for size
        html2canvas: { scale: 2, useCORS: true },
        jsPDF: { unit: "in", format: "a4", orientation: "portrait" },
        pagebreak: { mode: ['avoid-all', 'css', 'legacy'] } // Ensure proper page breaking
        // pagebreak: { mode: ['avoid-all', 'css', 'legacy'] }
        // pagebreak: { after: '.page', avoid: 'img' }
      };

      html2pdf().set(options).from(element).save();
    };

    onMounted(loadImages);

    return {
      pdfContent,
      images,
      imagePages,
      showSignaturePage,
      totalPages,
      showHeaderOnFirstPage,
      generatePdf,
    };
  },
};
</script>

<style scoped>
.text-content {
  font-size: 12px;
}

.logo {
  width: 200px;
  height: 200px;
}

.image-frame {
  height: 200px;
  object-fit: cover;
  width: 100%;
}
</style>
