# utl_sql_selecting_only_character_variables
Sql selecting only character variables. Keywords: sas sql join merge big data analytics macros oracle teradata mysql sas communities stackoverflow statistics artificial inteligence AI Python R Java Javascript WPS Matlab SPSS Scala Perl C C# Excel MS Access JSON graphics maps NLP natural language processing machine learning igraph DOSUBL DOW loop stackoverflow SAS community.
    Sql selecting only character variables

    gtihub
    https://github.com/rogerjdeangelis/utl_sql_selecting_only_character_variables

    VARLIST MACRO
    Author: Søren Lassen, s.lassen@post.tele.dk

    DO_OVER MACRO
    Authors: Ted Clay, M.S. (do_over)
    tclay@ashlandhome.net  (541) 482-6435
    David Katz, M.S. www.davidkatzconsulting.com

    sas forum
    https://communities.sas.com/t5/Base-SAS-Programming/selecting-only-character-variables/m-p/459158


    INPUT
    ======

      sashelp.class

      WANT  (dataset with just character variables using SQL

       WORK.WANT total obs=19

      Obs    NAME       SEX

        1    Alfred      M
        2    Alice       F
        3    Barbara     F
        4    Carol       F
        5    Henry       M
        6    James       M
       ....


    PROCESS
    =======

    %array(vars,values=%utl_varlist(sashelp.class,keep=_character_));

    proc sql;
      create
        table want as
      select
        %do_over(vars,phrase=?,between=comma)
      from
        sashelp.class
    ;quit


    OUTPUT
    ======

    WORK.WANT total obs=19

    Obs    NAME       SEX

      1    Alfred      M
      2    Alice       F
      3    Barbara     F
      4    Carol       F
      5    Henry       M
      6    James       M
      7    Jane        F
      8    Janet       F
      9    Jeffrey     M
     10    John        M
     11    Joyce       F
     12    Judy        F
     13    Louise      F
     14    Mary        F
     15    Philip      M
     16    Robert      M
     17    Ronald      M
     18    Thomas      M
     19    William     M

    *                _              _       _
     _ __ ___   __ _| | _____    __| | __ _| |_ __ _
    | '_ ` _ \ / _` | |/ / _ \  / _` |/ _` | __/ _` |
    | | | | | | (_| |   <  __/ | (_| | (_| | || (_| |
    |_| |_| |_|\__,_|_|\_\___|  \__,_|\__,_|\__\__,_|

    ;

      just use sashelp.class


     *          _       _   _
     ___  ___ | |_   _| |_(_) ___  _ __
    / __|/ _ \| | | | | __| |/ _ \| '_ \
    \__ \ (_) | | |_| | |_| | (_) | | | |
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|

    ;

     see process

