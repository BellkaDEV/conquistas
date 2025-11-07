void ExibirAlunos(Escola *inicio) {
    if (inicio == NULL) {
        cout << "Nenhum aluno cadastrado.\n";
        return;
    }

    cout << "\n=== LISTA DE ALUNOS ===\n";
    Escola *aux = inicio;
    while (aux != NULL) {
        cout << "Matricula: " << aux->matricula << " | Nome: " << aux->nome << endl;
        Nota *n = aux->notas;
        if (n == NULL) {
            cout << "  -> Sem notas registradas\n";
        } else {
            cout << "  -> Notas: ";
            while (n != NULL) {
                cout << n->valor;
                if (n->prox != NULL) cout << ", ";
                n = n->prox;
            }
            cout << endl;
        }
        aux = aux->prox;
    }
}