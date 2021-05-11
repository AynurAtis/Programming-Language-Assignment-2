irregular_number([]).
irregular_number([H|T]):-
    member(H, T).

del(X,[X|Tail],Tail):- !.
del(X, [], []):-
    format("Irregular number is ~w ", [X]),
    nl, !.
del(X,[Y|Tail],[Y|Tail1]) :- del(X, Tail, Tail1).
member(H, T):-
    del(H, T, T1),
    irregular_number(T1).
