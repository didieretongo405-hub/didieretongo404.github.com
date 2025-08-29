<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gestion des Rapports de Stage</title>
    
   
</head>
<style>* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

body {
    background-color: #f5f5f5;
    color: #333;
}

.container {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}

/* Header */
header {
    background-color: #2c3e50;
    color: white;
    padding: 1rem 2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.header-buttons {
    display: flex;
    gap: 1rem;
}

.header-buttons button {
    background-color: #3498db;
    color: white;
    border: none;
    padding: 0.5rem 1rem;
    border-radius: 4px;
    cursor: pointer;
    display: flex;
    align-items: center;
    gap: 0.5rem;
}

.header-buttons button:hover {
    background-color: #2980b9;
}

/* Main Content */
.main-content {
    display: flex;
    flex: 1;
}

/* Sidebar */
.sidebar {
    width: 250px;
    background-color: #34495e;
    color: white;
    padding: 1rem 0;
}

.sidebar ul {
    list-style: none;
}

.sidebar li {
    padding: 1rem 2rem;
    cursor: pointer;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    transition: background-color 0.3s;
}

.sidebar li:hover {
    background-color: #2c3e50;
}

.sidebar li.active {
    background-color: #3498db;
}

/* Content Area */
.content {
    flex: 1;
    padding: 2rem;
    overflow-y: auto;
}

.tab-content {
    display: none;
}

.tab-content.active {
    display: block;
}

/* Form Styles */
.form-row {
    display: flex;
    gap: 1rem;
    margin-bottom: 1rem;
}

.form-group {
    flex: 1;
    display: flex;
    flex-direction: column;
}

.form-group label {
    margin-bottom: 0.5rem;
    font-weight: 500;
}

.form-group input,
.form-group select {
    padding: 0.75rem;
    border: 1px solid #ddd;
    border-radius: 4px;
    font-size: 1rem;
}

.file-upload {
    margin-top: 0.5rem;
}

.file-label {
    display: inline-block;
    padding: 0.75rem 1.5rem;
    background-color: #3498db;
    color: white;
    border-radius: 4px;
    cursor: pointer;
    text-align: center;
}

.file-label:hover {
    background-color: #2980b9;
}

input[type="file"] {
    display: none;
}

.form-buttons {
    display: flex;
    gap: 1rem;
    margin-top: 1.5rem;
}

.btn-primary {
    background-color: #2ecc71;
    color: white;
    border: none;
    padding: 0.75rem 1.5rem;
    border-radius: 4px;
    cursor: pointer;
    font-size: 1rem;
}

.btn-primary:hover {
    background-color: #27ae60;
}

.btn-secondary {
    background-color: #e74c3c;
    color: white;
    border: none;
    padding: 0.75rem 1.5rem;
    border-radius: 4px;
    cursor: pointer;
    font-size: 1rem;
}

.btn-secondary:hover {
    background-color: #c0392b;
}

/* Search Bar */
.search-bar {
    display: flex;
    gap: 1rem;
    margin-bottom: 1.5rem;
}

.search-bar input {
    flex: 1;
    padding: 0.75rem;
    border: 1px solid #ddd;
    border-radius: 4px;
    font-size: 1rem;
}

.search-bar button {
    background-color: #3498db;
    color: white;
    border: none;
    padding: 0.75rem 1.5rem;
    border-radius: 4px;
    cursor: pointer;
    display: flex;
    align-items: center;
    gap: 0.5rem;
}

.search-bar button:hover {
    background-color: #2980b9;
}

/* Filters */
.filters {
    background-color: #f9f9f9;
    padding: 1.5rem;
    border-radius: 4px;
    margin-bottom: 1.5rem;
    border: 1px solid #eee;
}

.filters h3 {
    margin-bottom: 1rem;
}

.filter-group {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    margin-bottom: 1rem;
}

.filter-group label {
    min-width: 100px;
    font-weight: 500;
}

.filter-group input,
.filter-group select {
    padding: 0.5rem;
    border: 1px solid #ddd;
    border-radius: 4px;
}

/* Tables */
table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 1rem;
    background-color: white;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

th, td {
    padding: 0.75rem 1rem;
    text-align: left;
    border-bottom: 1px solid #eee;
}

th {
    background-color: #f5f5f5;
    font-weight: 600;
}

tr:hover {
    background-color: #f9f9f9;
}

/* Action buttons */
.action-btn {
    background: none;
    border: none;
    cursor: pointer;
    font-size: 1rem;
    margin-right: 0.5rem;
}

.view-btn {
    color: #3498db;
}

.edit-btn {
    color: #2ecc71;
}

.delete-btn {
    color: #e74c3c;
}

/* Departments */
.departments-list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 1rem;
    margin-bottom: 2rem;
}

.department-card {
    background-color: white;
    padding: 1.5rem;
    border-radius: 4px;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
    cursor: pointer;
    transition: transform 0.3s, box-shadow 0.3s;
    text-align: center;
}

.department-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.department-card h3 {
    color: #2c3e50;
    margin-bottom: 0.5rem;
}

.department-card p {
    color: #7f8c8d;
}

.department-results {
    margin-top: 2rem;
}

#dept-title {
    margin-bottom: 1rem;
}

#dept-title span {
    color: #3498db;
}

/* Sort options */
.sort-options {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    margin-bottom: 1rem;
}

.sort-options select {
    padding: 0.5rem;
    border: 1px solid #ddd;
    border-radius: 4px;
}

/* Modal */
.modal {
    display: none;
    position: fixed;
    z-index: 1000;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
}

.modal-content {
    background-color: white;
    margin: 10% auto;
    padding: 2rem;
    border-radius: 4px;
    width: 50%;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    position: relative;
}

.close {
    color: #aaa;
    float: right;
    font-size: 28px;
    font-weight: bold;
    position: absolute;
    right: 1rem;
    top: 0.5rem;
    cursor: pointer;
}

.close:hover {
    color: #000;
}

.modal textarea {
    width: 100%;
    height: 150px;
    padding: 0.75rem;
    border: 1px solid #ddd;
    border-radius: 4px;
    margin: 1rem 0;
    resize: vertical;
}

.modal-buttons {
    display: flex;
    gap: 1rem;
    justify-content: flex-end;
}

/* Responsive adjustments */
@media (max-width: 768px) {
    .main-content {
        flex-direction: column;
    }
    
    .sidebar {
        width: 100%;
    }
    
    .form-row {
        flex-direction: column;
    }
    
    .modal-content {
        width: 90%;
    }
}</style>
<body>
    <div class="container">
        <!-- Header -->
        <header>
            <h1>Gestion des Rapports de Stage</h1>
            <div class="header-buttons">
                <button id="settings-btn"><i class="fas fa-cog"></i> Paramètres</button>
                <button id="profile-btn"><i class="fas fa-user"></i> Profil</button>
                <button id="logout-btn"><i class="fas fa-sign-out-alt"></i> Déconnexion</button>
            </div>
        </header>

        <div class="main-content">
            <!-- Sidebar -->
            <aside class="sidebar">
                <nav>
                    <ul>
                        <li class="active" data-tab="nouveau-rapport"><i class="fas fa-plus-circle"></i> Nouveau Rapport</li>
                        <li data-tab="recherche"><i class="fas fa-search"></i> Recherche</li>
                        <li data-tab="departements"><i class="fas fa-building"></i> Départements</li>
                        <li data-tab="rapports"><i class="fas fa-file-alt"></i> Tous les rapports</li>
                        <li data-tab="utilisateurs"><i class="fas fa-users"></i> Utilisateurs</li>
                    </ul>
                </nav>
            </aside>

            <!-- Content Area -->
            <main class="content">
                <!-- Nouveau Rapport Tab -->
                <div id="nouveau-rapport" class="tab-content active">
                    <h2>Nouveau Rapport de Stage</h2>
                    <form id="rapport-form">
                        <div class="form-row">
                            <div class="form-group">
                                <label for="nom">Nom stagiaire</label>
                                <input type="text" id="nom" required>
                            </div>
                            <div class="form-group">
                                <label for="prenom">Prénom stagiaire</label>
                                <input type="text" id="prenom" required>
                            </div>
                        </div>

                        <div class="form-row">
                            <div class="form-group">
                                <label for="email">Email</label>
                                <input type="email" id="email" required>
                            </div>
                            <div class="form-group">
                                <label for="telephone">Téléphone</label>
                                <input type="tel" id="telephone" required>
                            </div>
                        </div>

                        <div class="form-row">
                            <div class="form-group">
                                <label for="date-naissance">Date de naissance</label>
                                <input type="date" id="date-naissance" required>
                            </div>
                            <div class="form-group">
                                <label for="date-debut">Date début</label>
                                <input type="date" id="date-debut" required>
                            </div>
                            <div class="form-group">
                                <label for="date-fin">Date fin</label>
                                <input type="date" id="date-fin" required>
                            </div>
                        </div>

                        <div class="form-row">
                            <div class="form-group">
                                <label for="etablissement">Établissement</label>
                                <input type="text" id="etablissement" required>
                            </div>
                            <div class="form-group">
                                <label for="departement">Département</label>
                                <select id="departement" required>
                                    <option value="">Sélectionner un département</option>
                                    <option value="Informatique">Informatique</option>
                                    <option value="Ressources Humaines">Ressources Humaines</option>
                                    <option value="Comptabilité">Comptabilité</option>
                                    <option value="Maintenance">Maintenance</option>
                                    <option value="Direction">Direction</option>
                                    <option value="Achat">Achat</option>
                                    <option value="Communication">Communication</option>
                                    <option value="Centre de traitement des dechets">Centre de traitement des dechets</option>
                                    <option value="Magasin">Magasin</option>
                                    <option value="QHSE">QHSE</option>
                                    <option value="PU">PU</option>
                                    <option value="service juridique">Service juridique</option>
                                </select>
                            </div>
                        </div>

                        <div class="form-group">
                            <label for="fichier">Rapport (PDF)</label>
                            <div class="file-upload">
                                <input type="file" id="fichier" accept=".pdf" required>
                                <label for="fichier" class="file-label">Choisir un fichier</label>
                            </div>
                        </div>

                        <div class="form-buttons">
                            <button type="submit" class="btn-primary">Enregistrer</button>
                            <button type="reset" class="btn-secondary">Annuler</button>
                        </div>
                    </form>
                </div>

                <!-- Recherche Tab -->
                <div id="recherche" class="tab-content">
                    <h2>Recherche de Rapports</h2>
                    <div class="search-bar">
                        <input type="text" id="search-input" placeholder="Nom stagiaire, établissement, département...">
                        <button id="search-btn"><i class="fas fa-search"></i> Rechercher</button>
                    </div>

                    <div class="filters">
                        <h3>Filtres</h3>
                        <div class="filter-group">
                            <label for="filter-departement">Département:</label>
                            <select id="filter-departement">
                                <option value="">Tous</option>
                                <option value="Informatique">Informatique</option>
                                <option value="Ressources Humaines">Ressources Humaines</option>
                                <option value="Comptabilité">Comptabilité</option>
                                <option value="Marketing">Marketing</option>
                                <option value="Direction">Direction</option>
                            </select>
                        </div>

                        <div class="filter-group">
                            <label for="filter-etablissement">Établissement:</label>
                            <input type="text" id="filter-etablissement" placeholder="Nom de l'établissement">
                        </div>

                        <div class="filter-group">
                            <label for="filter-date-debut">Période:</label>
                            <input type="date" id="filter-date-debut" placeholder="Date début">
                            <span>à</span>
                            <input type="date" id="filter-date-fin" placeholder="Date fin">
                        </div>
                    </div>

                    <div class="results">
                        <h3>Résultats</h3>
                        <table id="results-table">
                            <thead>
                                <tr>
                                    <th>Nom</th>
                                    <th>Prénom</th>
                                    <th>Département</th>
                                    <th>Établissement</th>
                                    <th>Dates</th>
                                    <th>PDF</th>
                                    <th>Appréciation</th>
                                    <th>Actions</th>
                                </tr>
                            </thead>
                            <tbody>
                                <!-- Les résultats seront ajoutés dynamiquement -->
                            </tbody>
                        </table>
                    </div>
                </div>

                <!-- Départements Tab -->
                <div id="departements" class="tab-content">
                    <h2>Départements</h2>
                    <div class="departments-list">
                        <div class="department-card" data-dept="Informatique">
                            <h3>Informatique</h3>
                            <p>5 rapports</p>
                        </div>
                        <div class="department-card" data-dept="Ressources Humaines">
                            <h3>Ressources Humaines</h3>
                            <p>3 rapports</p>
                        </div>
                        <div class="department-card" data-dept="Comptabilité">
                            <h3>Comptabilité</h3>
                            <p>2 rapports</p>
                        </div>
                        <div class="department-card" data-dept="Marketing">
                            <h3>Marketing</h3>
                            <p>4 rapports</p>
                        </div>
                        <div class="department-card" data-dept="Direction">
                            <h3>Direction</h3>
                            <p>1 rapport</p>
                        </div>
                    </div>

                    <div class="department-results">
                        <h3 id="dept-title">Rapports du département: <span></span></h3>
                        <table id="dept-results-table">
                            <thead>
                                <tr>
                                    <th>Nom</th>
                                    <th>Prénom</th>
                                    <th>Établissement</th>
                                    <th>Dates</th>
                                    <th>PDF</th>
                                    <th>Appréciation</th>
                                    <th>Actions</th>
                                </tr>
                            </thead>
                            <tbody>
                                <!-- Les résultats seront ajoutés dynamiquement -->
                            </tbody>
                        </table>
                    </div>
                </div>

                <!-- Rapports Tab -->
                <div id="rapports" class="tab-content">
                    <h2>Tous les Rapports</h2>
                    <div class="sort-options">
                        <label for="sort-by">Trier par:</label>
                        <select id="sort-by">
                            <option value="date-ajout">Date d'ajout</option>
                            <option value="nom">Nom</option>
                            <option value="prenom">Prénom</option>
                            <option value="departement">Département</option>
                            <option value="date-debut">Date de début</option>
                        </select>
                    </div>

                    <table id="all-reports-table">
                        <thead>
                            <tr>
                                <th>Nom</th>
                                <th>Prénom</th>
                                <th>Département</th>
                                <th>Établissement</th>
                                <th>Dates</th>
                                <th>PDF</th>
                                <th>Appréciation</th>
                                <th>Actions</th>
                            </tr>
                        </thead>
                        <tbody>
                            <!-- Les rapports seront ajoutés dynamiquement -->
                        </tbody>
                    </table>
                </div>

                <!-- Utilisateurs Tab -->
                <div id="utilisateurs" class="tab-content">
                    <h2>Gestion des Utilisateurs</h2>
                    <p>Interface de gestion des utilisateurs à implémenter.</p>
                </div>
            </main>
        </div>
    </div>

    <!-- Modal pour ajouter une appréciation -->
    <div id="appreciation-modal" class="modal">
        <div class="modal-content">
            <span class="close">&times;</span>
            <h2>Ajouter une appréciation</h2>
            <textarea id="appreciation-text" placeholder="Saisissez votre appréciation ici..."></textarea>
            <div class="modal-buttons">
                <button id="save-appreciation" class="btn-primary">Enregistrer</button>
                <button id="cancel-appreciation" class="btn-secondary">Annuler</button>
            </div>
        </div>
    </div>

    <script src="script.js"></script>
</body>
</html>
