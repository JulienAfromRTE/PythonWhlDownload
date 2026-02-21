# PythonWhlDownload

voici comment l'appeler : 

# Lecture du fichier local et envoi via l'API GitHub
REQ_CONTENT=$(cat requirements.txt)

curl -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer VOTRE_TOKEN_GITHUB" \
  https://api.github.com/repos/PROPRIETAIRE/NOM_DEPOT/actions/workflows/NOM_DU_FICHIER_YAML/dispatches \
  -d "{\"ref\":\"main\", \"inputs\":{\"requirements_content\":\"$REQ_CONTENT\"}}"
