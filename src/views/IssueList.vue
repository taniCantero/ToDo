<!-- compendio -->
<script>
import axios from 'axios';

const client = axios.create({
  baseURL: 'URL base del endpoint en su repositorio.',
  headers: {
    'Accept': 'application/vnd.github.v3+json',
    'Content-Type':'application/json',
    // Añade lo siguiente.
    'Authorization': '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' 
  },
})

export default {
  name: ' IssueList',
  data() {
    return {
      issues: []
    }
  },
  methods: {
    getIssues() {
      client.get('/issues')
        .then((res) => {
          this.issues = res.data;
      })
    }
  }
}
</script>