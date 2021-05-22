# ToxicSpansDetection

In the field of Natural Language Processing, the detection of text toxicity has become a significant challenge. To facilitate the research in this sphere, one of the tasks of the International Workshop on Semantic Evaluation 2021 is Toxic Spans Detection. The essential objective of this task is to identify toxic spans within English passages. In this paper, two approaches for toxic spans detection considered: Machine Reading Comprehension and modified Named Entity Recognition approach altogether with Machine Reading Comprehension, but also these approaches are improved by Question Generation method. Furthermore, this research presents the exploratory analysis of provided data, proposes a training process and examines the analysis of the results on F1-score of new state-of-the-art BERT-based Language Models: BERT, ALBERT, RoBERTa, XLM-RoBERTa and SpanBERT. Finally, the best language model obtained an F1-score of 0.688 on the test data.


\begin{table}[h!]
\centering
\caption{Результаты F1-метрики, полученные на $BASE$-моделях, на обучающей выборке}
\label{tab:base-train}
\resizebox{\textwidth}{!}{%
\begin{tabular}{|l|c|c|c|c|c|c|}
\hline
\diagbox[]{Модель}{Подход}& MRC & MRC SQuAD & \begin{tabular}[c]{@{}c@{}}MRC SQuAD \\ QG\end{tabular} & MRC+NER & \begin{tabular}[c]{@{}c@{}}MRC+NER\\ QG\end{tabular} & $AVG_{models}$\\ \hline
BERT        & 0.489          & 0.471          & 0.480          & \textbf{0.652} & \textit{\textbf{0.763}} & 0.571\\ \hline
RoBERTa     & 0.365          & 0.347          & 0.400          & 0.577          & \textit{0.756}   & 0.489       \\ \hline
XLM-RoBERTa & \textbf{0.569} & \textbf{0.537} & 0.515          & 0.533          & \textit{0.715}    & 0.573      \\ \hline
ALBERT      & 0.546          & 0.515          & \textbf{0.534} & 0.640          & \textit{0.731} & \textbf{0.593}          \\ \hline
SpanBERT    & 0.483          & 0.477          & 0.464          & \textbf{0.652} & \textit{0.746} & 0.564 \\ \hline
$AVG_{approaches}$    & 0.490          & 0.469          & 0.478        & 0.611 & \textit{0.742} & \\ \hline
\end{tabular}%
}
\end{table}


\begin{table}[h!]
\centering
\caption{Результаты F1-метрики, полученные на $BASE$-моделях, на валидационной выборке}
\label{tab:base-val}
\resizebox{\textwidth}{!}{%
\begin{tabular}{|l|c|c|c|c|c|c|}
\hline
 \diagbox[]{Модель}{Подход}& MRC & MRC SQuAD & \begin{tabular}[c]{@{}c@{}}MRC SQuAD\\ QG\end{tabular} & MRC+NER & \begin{tabular}[c]{@{}c@{}}MRC+NER\\ QG\end{tabular} & $AVG_{models}$\\ \hline
BERT        & 0.582                   & 0.576          & 0.581          & 0.601                   & \textit{0.621}       & 0.592   \\ \hline
RoBERTa     & 0.465                   & 0.445          & 0.515          & 0.586                   & \textit{\textbf{0.653}} & 0.533 \\ \hline
XLM-RoBERTa & \textit{\textbf{0.675}} & 0.632          & 0.635          & 0.544                   & 0.643  & \textbf{0.626}                 \\ \hline
ALBERT      & \textit{0.662}          & \textbf{0.637} & \textbf{0.660} & 0.587                   & 0.583     & \textbf{0.626}              \\ \hline
SpanBERT    & 0.571                   & 0.581          & 0.578          & \textit{\textbf{0.631}} & 0.628              & 0.598
     \\ \hline
$AVG_{approaches}$ & 0.591 &	0.574 &	0.594 &	0.590 & 	\textit{0.626} &	 \\
\hline
\end{tabular}%
}
\end{table}


\begin{table}[h!]
\centering
\caption{Результаты F1-метрики, полученные на $BASE$-моделях, на тестовой выборке}
\label{tab:base-test}
\resizebox{\textwidth}{!}{%
\begin{tabular}{|l|c|c|c|c|c|c|}
\hline
\diagbox[]{Модель}{Подход} & MRC            & MRC SQuAD      & \begin{tabular}[c]{@{}c@{}}MRC SQuAD\\ QG\end{tabular} & MRC+NER & \begin{tabular}[c]{@{}c@{}}MRC+NER\\ QG\end{tabular} & $AVG_{models}$ \\ \hline
BERT     & 0.612          & 0.617 & 0.610 & 0.613          & \textit{0.641} & 0.619\\ \hline
RoBERTa  & 0.475          & 0.492 & 0.542 & 0.622          & \textit{0.647} & 0.556\\ \hline
XLM-RoBERTa & \textbf{0.683} & \textbf{0.686} & \textit{\textbf{0.688}}                                & 0.566   & \textbf{0.658}   & \textbf{0.656}                                     \\ \hline
ALBERT   & \textit{0.682} & 0.659 & 0.657 & 0.624          & 0.593    & 0.643      \\ \hline
SpanBERT & 0.624          & 0.620  & 0.607 & \textbf{0.631} & \textit{0.644} & 0.625\\ \hline
$AVG_{approaches}$ &  0.615 & 	0.615 & 	0.621 & 	0.611 & 	\textit{0.637}  & 
\\
\hline
\end{tabular}%
}
\end{table}


\begin{table}[h!]
\centering
\caption{Результаты F1-метрики, полученные на $LARGE$-моделях, на обучающей выборке}
\label{tab:large-train}
\resizebox{\textwidth}{!}{%
\begin{tabular}{|l|c|c|c|c|c|c|}
\hline
 \diagbox[]{Модель}{Подход} & MRC            & MRC SQuAD      & \begin{tabular}[c]{@{}c@{}}MRC SQuAD\\ QG\end{tabular} & MRC+NER                 & \begin{tabular}[c]{@{}c@{}}MRC+NER\\ QG\end{tabular} & $AVG_{models}$ \\ \hline
BERT           & 0.486          & 0.490          & 0.496                                                  & \textit{\textbf{0.848}} & 0.706    & 0.605                                             \\ \hline
RoBERTa        & 0.360          & 0.365          & 0.372                                                  & 0.649                   & \textit{0.696}     & 0.488                                  \\ \hline
XLM-RoBERTa    & 0.578          & \textbf{0.570} & \textbf{0.547}                                         & 0.670                   & \textit{0.792}        & 0.631                               \\ \hline
ALBERT Large   & 0.536          & 0.540          & 0.505                                                  & 0.564                   & \textit{0.680}  & 0.565                                     \\ \hline
ALBERT XLarge  & 0.439          & 0.452          & 0.463                                                  & 0.558                   & \textit{0.645}    & 0.511                                   \\ \hline
ALBERT XXLarge & \textbf{0.584} & 0.548          & 0.524                                                  & 0.713                   & \textit{\textbf{0.835}}      & \textbf{0.641}                        \\ \hline
SpanBERT       & 0.509          & 0.492          & 0.469                                                  & 0.715                   & \textit{0.787}  & 0.594                                     \\ \hline

$AVG_{approaches}$ &      0.499 & 	0.494 & 	0.482 & 	0.674 & 	\textbf{0.734} &                                     \\ \hline
\end{tabular}%
}
\end{table}

\begin{table}[h!]
\centering
\caption{Результаты F1-метрики, полученные на $LARGE$-моделях, на валидационной выборке}
\label{tab:large-val}
\resizebox{\textwidth}{!}{%
\begin{tabular}{|l|c|c|c|c|c|c|}
\hline
  \diagbox[]{Модель}{Подход}& MRC            & MRC SQuAD      & \begin{tabular}[c]{@{}c@{}}MRC SQuAD\\ QG\end{tabular} & MRC+NER        & \begin{tabular}[c]{@{}c@{}}MRC+NER\\ QG\end{tabular} & $AVG_{models}$ \\ \hline
BERT           & 0.582          & 0.578          & 0.566                                                  & 0.629          & 0.641               & 0.599                                 \\ \hline
RoBERTa        & 0.433          & 0.448          & 0.454                                                  & \textbf{0.643} & \textbf{0.666}   & 0.528                                    \\ \hline
XLM-RoBERTa    & \textbf{0.680} & 0.650          & \textbf{0.657}                                         & 0.624          & 0.648     & \textbf{0.651}                                           \\ \hline
ALBERT         & 0.663          & 0.666          & 0.639                                                  & 0.580          & 0.614               & 0.632                              \\ \hline
ALBERT XLarge  & 0.569          & 0.573          & 0.580                                                  & 0.559          & 0.636  & 0.583                                              \\ \hline
ALBERT XXLarge & 0.661          & \textbf{0.668} & 0.617                                                  & 0.559          & 0.611                               & 0.623                 \\ \hline
SpanBERT       & 0.565          & 0.572          & 0.567                                                  & 0.628          & 0.647       & 0.596                                         \\ \hline

$AVG_{approaches}$ & 0.593 & 	0.594 & 	0.583 & 	0.603 & 	0.638 & 
\\ \hline

\end{tabular}%
}
\end{table}


\begin{table}[]
\centering
\caption{Результаты F1-метрики, полученные на $LARGE$-моделях, на тестовой выборке}
\label{tab:large-test}
\resizebox{\textwidth}{!}{%
\begin{tabular}{|l|c|c|c|c|c|c|}
\hline
\diagbox[]{Модель}{Подход}& MRC                     & MRC SQUAD               & \begin{tabular}[c]{@{}c@{}}MRC SQUAD\\ QG\end{tabular} & MRC+NER        & \begin{tabular}[c]{@{}c@{}}MRC+NER\\  QG\end{tabular} & $AVG_{models}$ \\ \hline
BERT           & 0.605                   & 0.602                   & 0.606                                                  & 0.634          & \textit{0.652}      & 0.620                                 \\ \hline
RoBERTa        & 0.474                   & 0.473                   & 0.416                                                  & \textbf{0.638} & \textit{\textbf{0.654}}  & 0.531                             \\ \hline
XLM-RoBERTa    & \textit{\textbf{0.683}} & 0.598                   & \textbf{0.677}                                         & 0.632          & 0.647   & \textbf{0.647}                                              \\ \hline
ALBERT         & 0.674                   & \textit{0.681}          & 0.649                                                  & 0.596          & 0.625      & 0.645                                           \\ \hline
ALBERT XLarge  & 0.593                   & \textit{0.666}          & 0.613                                                  & 0.591          & 0.607   & 0.614                                              \\ \hline
ALBERT XXLarge & 0.679                   & \textit{\textbf{0.685}} & 0.618                                                  & 0.603          & 0.599                                  & 0.637          \\ \hline
SpanBERT       & 0.601                   & 0.595                   & 0.603                                                  & 0.635          & \textit{0.636}  & 0.614                                      \\ \hline

$AVG_{approaches}$ & 0.616 & 	0.614 & 	0.597 & 	0.618 & 	\textit{0.631} & 
\\ \hline
\end{tabular}%
}
\end{table}
