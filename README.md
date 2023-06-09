# trabalhandoComEnum

Adicionando meu comando para depois clonar no meus projetos. 

#include <iostream>
#include <string>

enum DiaSemana {
    SEGUNDA,
    TERCA,
    QUARTA,
    QUINTA,
    SEXTA,
    SABADO,
    DOMINGO
};

std::string obterNomeDia(DiaSemana dia) {
    switch (dia) {
        case SEGUNDA:
            return "Segunda-feira";
        case TERCA:
            return "Terça-feira";
        case QUARTA:
            return "Quarta-feira";
        case QUINTA:
            return "Quinta-feira";
        case SEXTA:
            return "Sexta-feira";
        case SABADO:
            return "Sábado";
        case DOMINGO:
            return "Domingo";
        default:
            return "";
    }
}

DiaSemana obterDia(const std::string& nomeDia) {
    if (nomeDia == "segunda" || nomeDia == "Segunda-feira")
        return SEGUNDA;
    else if (nomeDia == "terca" || nomeDia == "Terça-feira")
        return TERCA;
    else if (nomeDia == "quarta" || nomeDia == "Quarta-feira")
        return QUARTA;
    else if (nomeDia == "quinta" || nomeDia == "Quinta-feira")
        return QUINTA;
    else if (nomeDia == "sexta" || nomeDia == "Sexta-feira")
        return SEXTA;
    else if (nomeDia == "sabado" || nomeDia == "Sábado")
        return SABADO;
    else if (nomeDia == "domingo" || nomeDia == "Domingo")
        return DOMINGO;
    else
        return DOMINGO;  // Valor padrão para dia inválido
}

bool ehDiaDeSemana(DiaSemana dia) {
    return dia >= SEGUNDA && dia <= SEXTA;
}

bool ehFinalDeSemana(DiaSemana dia) {
    return dia == SABADO || dia == DOMINGO;
}

int main() {
    std::string nomeDia;
    std::cout << "Digite um dia da semana: ";
    std::cin >> nomeDia;

    DiaSemana dia = obterDia(nomeDia);
    std::string nomeDiaCompleto = obterNomeDia(dia);

    if (ehDiaDeSemana(dia)) {
        std::cout << nomeDiaCompleto << " é um dia de semana." << std::endl;
    } else if (ehFinalDeSemana(dia)) {
        std::cout << nomeDiaCompleto << " é um final de semana." << std::endl;
    } else {
        std::cout << "Dia inválido." << std::endl;
    }

    return 0;
}
