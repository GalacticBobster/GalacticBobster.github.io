---
permalink: /
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

👋 Welcome! I'm Ananyo Bhattacharya, a space scientist and engineer bridging scientific research with technological innovation. I am a Research Fellow at Department of Climate and Space Sciences and Engineering, University of Michigan.

I am working on problems at intersection of natural sciences and engineering focused on understanding Earth and outer space. At University of Michigan's [Atmospheric Dynamics Modeling Laboratory](https://admg.engin.umich.edu), I work on technical development of [NOAA Unified Forecast System](https://ufs.epic.noaa.gov) for operational weather forecasting over the Great Lakes region. Short-term weather forecasting provides insights on lake effect winter storms, rainfall patterns and sources of moisture. I am also working with applications of deep learning models for Earth System Modeling. Emerging technologies in machine learning combined with physics based methods help us to take on challenging problems.

I am also a scientific collaborator to [NASA Juno mission](https://science.nasa.gov/mission/juno/) to Jupiter. I have led projects focused on Microwave Radiometry applications to sensing Jupiter's deep clouds and its space environment. I completed my Ph.D. in Climate and Space Sciences and Engineering from University of Michigan with a Graduate Certificate in Entrepreneurship and Innovation. I also received summer research fellowships to intern at NASA Jet Propulsion Laboratory and Los Alamos National Laboratory. Before my graduate studies, I completed my undergraduate education in Mechnical Engineering from Sardar Vallabhbhai National Institute of Technology Surat, India.



------
<style>
.carousel-container {
    position: relative;
    width: 100%;
    max-width: 800px;
    margin: 20px auto;
    overflow: hidden;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.carousel-slides {
    display: flex;
    transition: transform 0.5s ease-in-out;
}

.carousel-slide {
    min-width: 100%;
    height: 400px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.carousel-slide img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.carousel-indicators {
    position: absolute;
    bottom: 15px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    gap: 8px;
}

.indicator {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.5);
    cursor: pointer;
    transition: background 0.3s;
}

.indicator.active {
    background: white;
}

.carousel-button {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background: rgba(0,0,0,0.5);
    color: white;
    border: none;
    padding: 8px 12px;
    cursor: pointer;
    border-radius: 50%;
    font-size: 18px;
}

.carousel-button.prev { left: 10px; }
.carousel-button.next { right: 10px; }
</style>

<div class="carousel-container">
    <div class="carousel-slides" id="carouselSlides">
        <div class="carousel-slide">
            <img src="../images/protostar.png" alt="Research at University of Michigan">
        </div>
        <div class="carousel-slide">
            <img src="../images/OccultationGeometry.png" alt="NASA Juno Mission to Jupiter">
        </div>
        <div class="carousel-slide">
            <img src="../images/great-lakes-weather.jpg" alt="Great Lakes Weather Forecasting">
        </div>
    </div>

    <!-- Navigation buttons -->
    <button class="carousel-button prev">&#10094;</button>
    <button class="carousel-button next">&#10095;</button>

    <!-- Indicators -->
    <div class="carousel-indicators" id="indicators"></div>
</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
    const slides = document.getElementById('carouselSlides');
    const indicatorsContainer = document.getElementById('indicators');
    const prevBtn = document.querySelector('.carousel-button.prev');
    const nextBtn = document.querySelector('.carousel-button.next');

    const totalSlides = slides.children.length;
    let currentSlide = 0;

    // Create indicators
    for (let i = 0; i < totalSlides; i++) {
        const indicator = document.createElement('div');
        indicator.className = 'indicator';
        if (i === 0) indicator.classList.add('active');
        indicator.addEventListener('click', () => goToSlide(i));
        indicatorsContainer.appendChild(indicator);
    }

    function goToSlide(index) {
        currentSlide = index;
        slides.style.transform = `translateX(-${currentSlide * 100}%)`;
        updateIndicators();
    }

    function nextSlide() {
        currentSlide = (currentSlide + 1) % totalSlides;
        goToSlide(currentSlide);
    }

    function prevSlide() {
        currentSlide = (currentSlide - 1 + totalSlides) % totalSlides;
        goToSlide(currentSlide);
    }

    function updateIndicators() {
        const indicators = indicatorsContainer.children;
        for (let i = 0; i < indicators.length; i++) {
            indicators[i].classList.toggle('active', i === currentSlide);
        }
    }

    // Attach button events
    nextBtn.addEventListener('click', nextSlide);
    prevBtn.addEventListener('click', prevSlide);

    // Optional: auto-play every 5 seconds
    setInterval(nextSlide, 5000);
});
</script>

   

------
