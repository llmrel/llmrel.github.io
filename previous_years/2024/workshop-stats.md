<section id="stats" class="workshop-stats">
  <h2>Workshop Statistics</h2>
  <div class="stats-grid">
    <div class="stat-card">
      <i class="fas fa-file-alt"></i>
      <h3>Submissions</h3>
      <p class="stat-number" data-target="113">0</p>
    </div>
    <div class="stat-card">
      <i class="fas fa-check"></i>
      <h3>Accepted Papers</h3>
      <p class="stat-number" data-target="43">0</p>
    </div>
    <div class="stat-card">
      <i class="fas fa-percentage"></i>
      <h3>Acceptance Rate</h3>
      <p class="stat-number" data-target="38">0</p>
    </div>
    <div class="stat-card">
      <i class="fas fa-users"></i>
      <h3>Reviewers Recruited</h3>
      <p class="stat-number" data-target="121">0</p>
    </div>
    <div class="stat-card">
      <i class="fas fa-comment-dots"></i>
      <h3>Reviews Submitted</h3>
      <p class="stat-number" data-target="349">0</p>
    </div>
    <div class="stat-card">
      <i class="fas fa-chart-line"></i>
      <h3>Average Reviews Per Paper</h3>
      <p class="stat-number" data-target="3.08">0</p>
    </div>
  </div>
</section>

<!-- Add some CSS -->
<style>
  .workshop-stats {
    text-align: center;
    padding: 40px;
    background: linear-gradient(135deg, #74ebd5 0%, #ACB6E5 100%);
    color: white;
    font-family: Arial, sans-serif;
  }

  .stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: 20px;
    margin-top: 20px;
  }

  .stat-card {
    background-color: rgba(255, 255, 255, 0.2);
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .stat-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 6px 10px rgba(0, 0, 0, 0.2);
  }

  .stat-card h3 {
    font-size: 1.2rem;
    margin-bottom: 10px;
  }

  .stat-card p {
    font-size: 2rem;
    color: white;
  }

  .stat-card i {
    font-size: 3rem;
    margin-bottom: 10px;
    color: #FFD700;
  }

  /* Animating the numbers */
  @keyframes countUp {
    from {
      content: "0";
    }
    to {
      content: attr(data-target);
    }
  }

  .stat-number {
    font-size: 2rem;
    font-weight: bold;
    color: white;
    transition: color 0.5s;
  }
</style>

<!-- Add counter-up animation with JavaScript -->
<script>
  document.addEventListener('DOMContentLoaded', function () {
    const counters = document.querySelectorAll('.stat-number');
    counters.forEach(counter => {
      counter.innerText = '0';
      
      const updateCounter = () => {
        const target = +counter.getAttribute('data-target');
        const current = +counter.innerText;
        const increment = target / 100;
        
        if (current < target) {
          counter.innerText = `${Math.ceil(current + increment)}`;
          setTimeout(updateCounter, 30);
        } else {
          counter.innerText = target;
        }
      };
      
      updateCounter();
    });
  });
</script>
