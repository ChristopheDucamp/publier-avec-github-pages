# publier-avec-github-pages
Publier avec github pages, en 3 étapes
Source https://github.com/blog/2289-publishing-with-github-pages-now-as-easy-as-1-2-3


[Source](https://github.com/blog/2289-publishing-with-github-pages-now-as-easy-as-1-2-3 "Permalink to Publishing with GitHub Pages, now as easy as 1, 2, 3 · GitHub") by @benbalter (2016-12-09)

## Publier avec GitHub Pages, maintenant aussi facile que 1, 2, 3 

La publication d'un site Web ou d'une documentation logicielle avec GitHub Pages nécessite maintenant beaucoup moins d'étapes - 
trois pour être exact :

1. [Créer un référentiel][1] (ou naviguer vers un référentiel existant)
2. Créer et "committer" un fichier Markdown via l'interface Web, tout comme vous le feriez pour tout autre fichier
3. Activer les pages GitHub via les paramètres de votre référentiel

Et c'est tout - vous avez maintenant un site Web. 
Si vous connaissez déjà GitHub Pages, vous pourriez être intéressé de savoir que dans les coulisses, nous faisons désormais quelques trucs pour simplifier l'expérience de publication et la rendre plus en ligne avec ce que vous pouvez attendre de la création de contenu Markdown ailleurs Sur GitHub :

1. Tous les fichiers Markdown sont maintenant rendus par les pages GitHub, ce qui vous évite d'avoir à ajouter de la face avant YAML (les métadonnées en haut du fichier séparées par `\ ---` s) à chaque fichier.

2. Nous utiliserons votre fichier README comme index du site si vous n'avez pas `index.md` (ou` index.html`), ce qui n'est pas différent de lorsque vous naviguez vers un référentiel sur GitHub.

3. Si vous ne spécifiez pas de thème dans la configuration de votre site (ou si vous n'avez pas de fichier de configuration), nous définirons un thème par défaut minimal qui correspond à l'aspect de Markdown ailleurs sur GitHub.

4. Si un fichier donné n'a pas de mise en page spécifiée, nous allons lui en assigner une en fonction de son contexte. Par exemple, les pages obtiendront automatiquement la mise en page `page`, ou la mise en page` default`, si la mise en page `page` n'existe pas.

5. Si votre page n'a pas de titre explicite et que le fichier commence par H1, H2 ou H3, nous utiliserons ce titre comme titre de la page, qui apparaît dans des endroits tels que les onglets du navigateur.

Ces améliorations devraient vous permettre de publier rapidement et facilement votre premier (ou 100e) site Web en quelques clics, ou de documenter votre projet logiciel [en ajoutant simplement des fichiers Markdown à un dossier `/ docs`][2] au sein de votre référentiel. Bien sûr, vous pouvez continuer à contrôler l'aspect et la convivialité en optant pour des personnalisations supplémentaires (comme la substitution du thème par défaut à vos propres mises en page ou styles).

Bien que ces changements ne devraient pas affecter la façon dont la plupart des sites existants de construire, il y a deux hasards potentiels pour certains utilisateurs plus avancés Jekyll:

1. If your site iterates through all pages (e.g., `for page in site.pages`), you may find that there are now additional pages (such as the README of a vendored dependency) in that list. You can explicitly exclude these files with your config file's `exclude` directive.

2. If you don't specify a page's layout or title, and expect either to be unset (e.g., if you need to serve unstyled content), you'll need to explicitly set those values as `null`.

And if for any reason you don't want these features, you can disable them by adding a `.nojekyll` file to your site's root directory.


1. Si votre site parcourt toutes les pages (par exemple, `pour page dans site.pages`), il se peut que vous ayez maintenant des pages supplémentaires (comme le fichier README d'une dépendance) dans cette liste. Vous pouvez explicitement exclure ces fichiers avec la directive `exclude` de votre fichier de configuration.

2. Si vous ne spécifiez pas la mise en page ou le titre d'une page et que vous vous attendiez à ce qu'elle soit désactivée (par exemple, si vous devez diffuser du contenu non modifié), vous devrez définir explicitement ces valeurs comme `null`.

Et si pour une raison quelconque vous ne voulez pas ces fonctionnalités, vous pouvez les désactiver en ajoutant un fichier `.nojekyll` au répertoire racine de votre site.

Pour que le processus de génération des Pages GitHub puisse être aussi transparent et personnalisable que possible, toutes les fonctionnalités ci-dessus sont mises en œuvre sous forme de plugins Jekyll open source, à savoir [Jekyll Optional Front Matter][3], [Jekyll README Index][4], [Jekyll Default Layout][5], et [Jekyll Titles from Headings][6].

Encore une fois, ces changements ne devraient pas affecter la façon dont la plupart des sites existants se construisent (bien que vous puissiez commencer à utiliser ces fonctionnalités en toute sécurité), mais si vous avez des questions, n'hésitez pas à nous contacter[7].

Bonne édition en trois étapes !

[1]: https://github.com/new
[2]: https://github.com/blog/2228-simpler-github-pages-publishing
[3]: https://github.com/benbalter/jekyll-optional-front-matter
[4]: https://github.com/benbalter/jekyll-readme-index
[5]: https://github.com/benbalter/jekyll-default-layout
[6]: https://github.com/benbalter/jekyll-titles-from-headings
[7]: https://github.com/contact?form%5Bsubject%5D=Simplified%20Pages%20publishing
