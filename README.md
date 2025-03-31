# Kmlocal espAtivo = true

function alternarESP() espAtivo = not espAtivo if espAtivo then print("ESP Ativado") else print("ESP Desativado") end end

function desenharJogadores(jogadores, meuTime) if not espAtivo then return end

for _, jogador in ipairs(jogadores) do
    local cor = jogador.time == meuTime and {0, 0, 255} or {255, 0, 0}
    desenharCaixa(jogador.posicao, cor)
    desenharFOV(jogador.posicao)
    desenharSeta(jogador.posicao)
end

end

function desenharCaixa(posicao, cor) print(string.format("Desenhando caixa na posição %s com a cor RGB(%d, %d, %d)", posicao, cor[1], cor[2], cor[3])) end

function desenharFOV(posicao) print(string.format("Desenhando FOV na posição %s", posicao)) end

function desenharSeta(posicao) print(string.format("Desenhando seta apontando para posição %s", posicao)) end

local jogadores = { {posicao = "10,20", time = "amigo"}, {posicao = "30,40", time = "inimigo"} }

desenharJogadores(jogadores, "amigo")

