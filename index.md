

# Your GitHub Repositories

<div class="container">
  <ul class="repo-list" id="repos-list"></ul>
</div>

<script>
  const apiUrl = 'https://api.github.com/users/amihsan/repos';

  fetch(apiUrl)
    .then(response => response.json())
    .then(repos => {
      const reposList = document.getElementById('repos-list');
      repos.forEach(repo => {
        const repoItem = document.createElement('li');
        repoItem.className = 'repo-item';

        const repoName = document.createElement('div');
        repoName.className = 'repo-name';
        repoName.innerHTML = `<a href="${repo.html_url}" target="_blank">${repo.name}</a>`;

        const repoDescription = document.createElement('div');
        repoDescription.className = 'repo-description';
        repoDescription.textContent = repo.description || 'No description provided.';

        repoItem.appendChild(repoName);
        repoItem.appendChild(repoDescription);
        reposList.appendChild(repoItem);
      });
    })
    .catch(error => console.error('Error fetching repositories:', error));
</script>



