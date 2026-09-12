origin	git@github.com:TheAlgorithms/Python.git (fetch)
origin	git@github.com:TheAlgorithms/Python.git (push)

commit dbf22d3c48a460375d7c92e996974271c8bc833b
Author: Ashwin R <ashwin06charan12@gmail.com>
Date:   Sat Sep 12 16:32:21 2026 +0530

    sorts: make heap sort support comparable items (#15291)
    
    * sorts: make heap sort support comparable items
    
    * style: remove unnecessary blank lines from heap sort

commit 611418cfb2f6cdc49637324489ace42db605d969
Author: priya-sundaram-dev <oc-409d01@agentmail.to>
Date:   Sat Sep 12 09:18:13 2026 +0000

    machine_learning: add numeric doctests to gradient_descent (#15286)

commit 12d064871be7d221ed9010be66d40a501df80856
Author: Vibhor Gautam <55019395+VibhorGautam@users.noreply.github.com>
Date:   Sat Sep 12 13:41:49 2026 +0530

    fix: use geodetic latitudes in haversine distance formula (#14351)
    
    * fix: use geodetic latitudes in haversine distance formula
    
    The implementation was incorrectly using reduced latitudes (via a
    flattening factor from WGS84 ellipsoid constants) instead of raw
    geodetic latitudes. Reduced latitudes are appropriate for ellipsoidal
    models like Lambert's formula, but the Haversine formula operates on
    a sphere and should use geodetic latitudes directly.
    
    Changes:
    - Use radians(lat) directly instead of computing reduced latitudes
      with atan((1 - flattening) * tan(radians(lat)))
    - Replace equatorial radius (6378137m) with mean Earth radius
      (6371000m) for better spherical approximation
    - Remove unused WGS84 ellipsoid constants (AXIS_A, AXIS_B)
    - Remove unused imports (atan, tan)
    - Add edge case and cross-continental doctests
    
    Fixes #11308
    
    * fix: update Lambert's to use corrected haversine radius for central angle
    
    Lambert's ellipsoidal distance computes the central angle sigma by
    dividing the haversine distance by a radius. Previously both functions
    used the same equatorial radius (6378137m), so the values cancelled
    out. After correcting haversine to use the mean Earth radius (6371000m),
    Lambert's must divide by the same radius to recover the correct angle.
    
    Also update the expected doctest values to match the corrected
    haversine output.
    
    Fixes #11308
    
    * Fix typos
    
    Updated the docstring for the haversine_distance function to improve clarity and fix minor grammatical issues.
    
    * Fix typos in docstring and variable names
    
    * Clarify note on using haversine_distance.py
    
    Updated the note to clarify the use of haversine_distance.py.
    
    ---------
    
    Co-authored-by: Christian Clauss <cclauss@me.com>

commit d5020134382bf0719974232595467bd3227243f8
Author: Orji Patricia <81320550+otrisha@users.noreply.github.com>
Date:   Sat Sep 12 06:53:55 2026 +0100

    sorts: make comb_sort generic for comparable items (#15288)
    
    * sorts: make comb sort generic for comparable items
    
    * tests: cover comb sort incomparable inputs
    
    * Update sorts/comb_sort.py
    
    * Apply suggestion from @cclauss
    
    * Apply suggestion from @cclauss
    
    ---------
    
    Co-authored-by: Christian Clauss <cclauss@me.com>

commit 3e34e8ef752f2a8032a9e9de659d0f1ac214556f
Author: priya-sundaram-dev <oc-409d01@agentmail.to>
Date:   Sat Sep 12 00:12:26 2026 +0000

    machine_learning: pin numeric output of k_means_clust with doctests (#15285)

commit 0fe748a33e609fc817a9a5d1a73a8b2c5bb3d129
Author: Jarvis-J-Jacob <287212888+Jarvis-J-Jacob@users.noreply.github.com>
Date:   Sat Sep 12 02:53:33 2026 +0300

    Add docstring to build_tree() (#15091)
    
    Co-authored-by: Jarvis Jeason Jacob <jarvis@Jarviss-MacBook-Pro.local>
    Co-authored-by: Christian Clauss <cclauss@me.com>

commit e548737115ffbee732041a1eef4b96fae0281874
Author: Nikita Kedari <117960918+Nikita-Kedari@users.noreply.github.com>
Date:   Sat Sep 12 05:08:47 2026 +0530

    Implement K-Medoids Clustering Algorithm #13488 (#13510)
    
    * Added k_medoids algorithm
    
    * updating DIRECTORY.md
    
    ---------
    
    Co-authored-by: Christian Clauss <cclauss@me.com>
    Co-authored-by: cclauss <cclauss@users.noreply.github.com>

commit 102078a50a3b16ae2b210b22ed52b5343ed962e0
Author: somrita-banerjee <144698416+somrita-banerjee@users.noreply.github.com>
Date:   Sat Sep 12 04:57:12 2026 +0530

    Add vectorized implementations of Linear Regression using Gradient Descent (#13221)
    
    * Add naive and vectorized implementations of Linear Regression using Gradient Descent
    
    * Add references section to docstrings in linear regression implementations
    
    * [pre-commit.ci] auto fixes from pre-commit.com hooks
    
    for more information, see https://pre-commit.ci
    
    * Refactor function signatures for improved readability in linear regression implementation
    
    * [pre-commit.ci] auto fixes from pre-commit.com hooks
    
    for more information, see https://pre-commit.ci
    
    * Refactor function signatures for improved readability in linear regression implementation
    
    * Update README sections for dataset inputs and usage instructions in linear regression implementations
    
    * [pre-commit.ci] auto fixes from pre-commit.com hooks
    
    for more information, see https://pre-commit.ci
    
    * Add doctests for dataset collection and gradient descent functions
    
    * [pre-commit.ci] auto fixes from pre-commit.com hooks
    
    for more information, see https://pre-commit.ci
    
    * Refactor imports and improve README formatting in linear regression scripts
    
    * fix doctests
    
    * Remove linear regression naive implementation script
    
    * Refactor docstring and improve script documentation for clarity
    
    * [pre-commit.ci] auto fixes from pre-commit.com hooks
    
    for more information, see https://pre-commit.ci
    
    * Fix formatting in gradient_descent doctest and streamline main function call
    
    * fix doctest
    
    * updating DIRECTORY.md
    
    * Change httpx to httpx2 and update docstring
    
    Updated import from httpx to httpx2 and modified docstring for dataset return type.
    
    ---------
    
    Co-authored-by: pre-commit-ci[bot] <66853113+pre-commit-ci[bot]@users.noreply.github.com>
    Co-authored-by: Christian Clauss <cclauss@me.com>
    Co-authored-by: cclauss <cclauss@users.noreply.github.com>

commit 2e1c752f76ead091b26ec741dabf4960331fc35e
Author: dwaddle <dwaddle@users.noreply.github.com>
Date:   Sat Sep 12 01:04:47 2026 +0200

    docs: add docstrings and doctests to generate_all_subsequences (#15090)
    
    * docs: add docstring and doctests to generate_all_permutations)
    
    * docs: add docstring and doctests to generate_all_subsequences

commit b96d9d90b176188d92f87d10ba6769b8c8b91914
Author: kdt523 <krushna.datir231@vit.edu>
Date:   Sat Sep 12 04:29:19 2026 +0530

    Feature federated learning (#13615)
    
    * Add_Federated_Averaging_FedAvg_module_with_doctests
    
    * Update_FedAvg_doctests
    
    * Rename_normalize_weights_param_to_num_clients
    
    * Fix_ruff_issues_in_FedAvg_module

commit a7029989d602c46d7e95ead20e5d8030efbab010
Author: Adhithya Laxman <94938999+Adhithya-Laxman@users.noreply.github.com>
Date:   Sat Sep 12 00:15:59 2026 +0200

    Add Momentum SGD optimizer implementation (#13680)
    
    * Add Momentum SGD optimizer implementation
    
    - Implements SGD with momentum using pure NumPy
    - Includes comprehensive docstrings and type hints
    - Adds doctests for validation
    - Provides usage example demonstrating convergence
    - Follows PEP8 coding standards
    
    * updating DIRECTORY.md
    
    * updating DIRECTORY.md
    
    ---------
    
    Co-authored-by: Christian Clauss <cclauss@me.com>
    Co-authored-by: cclauss <cclauss@users.noreply.github.com>

commit f644edd6dc75fbe144c93257b83cf283974d08ba
Author: Adhithya Laxman <94938999+Adhithya-Laxman@users.noreply.github.com>
Date:   Sat Sep 12 00:14:49 2026 +0200

    Added Nesterov and Adam Optimizers (#13718)
    
    * Add Adagrad optimizer implementation
    
    - Implements Adagrad (Adaptive Gradient) using pure NumPy
    - Adapts learning rate individually for each parameter
    - Includes comprehensive docstrings and type hints
    - Adds doctests for validation
    - Provides usage example demonstrating convergence
    - Follows PEP8 coding standards
    - Part of issue #13662
    
    * Add Adam and Nesterov Accelerated Gradient optimizers
    
    - Implements Adam (Adaptive Moment Estimation) optimizer
    - Implements Nesterov Accelerated Gradient (NAG) optimizer
    - Both use pure NumPy without deep learning frameworks
    - Includes comprehensive docstrings and type hints
    - Adds doctests for validation
    - Provides usage examples demonstrating convergence
    - Follows PEP8 coding standards
    - Part of issue #13662
    
    * updating DIRECTORY.md
    
    ---------
    
    Co-authored-by: Christian Clauss <cclauss@me.com>
    Co-authored-by: cclauss <cclauss@users.noreply.github.com>

commit 26e432088507237b99137201703977d6602e4fa9
Author: Ge Yingshan <180310075+ElenaGe216@users.noreply.github.com>
Date:   Sat Sep 12 05:59:59 2026 +0800

    sorts: type cocktail shaker sort for comparable items (#15278)
    
    Co-authored-by: Gavin-Yau <2695188238@qq.com>

commit 6fc7a99505813bedb0338b4a28588735beba3106
Author: Ali Satwat Khan <alisatwat3@gmail.com>
Date:   Sat Sep 12 02:10:48 2026 +0500

    docs: explain Strassen's algorithm complexity in docstrings (#14925)
    
    * docs: explain Strassen's algorithm complexity in docstrings
    
    Expand actual_strassen() docstring to describe the divide-and-conquer
    approach (7 recursive multiplications instead of 8) and note time
    complexity O(n^log2(7)) ~= O(n^2.807) vs O(n^3) for naive matrix
    multiplication, plus space complexity O(n^2). Also expand strassen()
    docstring to explain the padding/trimming wrapper logic. No behavior
    changes; all existing doctests pass.
    
    * [pre-commit.ci] auto fixes from pre-commit.com hooks
    
    for more information, see https://pre-commit.ci
    
    * Fix Ruff 0.16 lint failures
    
    * Fix grammar in docstrings and comments
    
    Corrected minor grammatical issues in docstrings and comments.
    
    * [pre-commit.ci] auto fixes from pre-commit.com hooks
    
    for more information, see https://pre-commit.ci
    
    ---------
    
    Co-authored-by: pre-commit-ci[bot] <66853113+pre-commit-ci[bot]@users.noreply.github.com>
    Co-authored-by: Christian Clauss <cclauss@me.com>

commit afce564da3fa91d946fdb20660e6a3ee6515c162
Author: kadambari25 <sureshkadambari62@gmail.com>
Date:   Fri Sep 11 22:58:54 2026 +0200

    Add get_word_path function to word_search.py (#14511)
    
    * Added get_word_path function
    
    * [pre-commit.ci] auto fixes from pre-commit.com hooks
    
    for more information, see https://pre-commit.ci
    
    * updating DIRECTORY.md
    
    * Implement board and word validation function
    
    Added a new validation function to check the board and word parameters, ensuring proper input types and values. Updated existing function docstrings for clarity and consistency.
    
    * [pre-commit.ci] auto fixes from pre-commit.com hooks
    
    for more information, see https://pre-commit.ci
    
    * Improve readability of validate_board_and_word call
    
    Refactor the validate_board_and_word function call for better readability.
    
    ---------
    
    Co-authored-by: Kadambari <kadambari179@gmail.com>
    Co-authored-by: pre-commit-ci[bot] <66853113+pre-commit-ci[bot]@users.noreply.github.com>
    Co-authored-by: Christian Clauss <cclauss@me.com>
    Co-authored-by: cclauss <cclauss@users.noreply.github.com>

commit 5bb1027f5b5f8b487a7a173c162f3346c974094d
Author: priya-sundaram-dev <oc-409d01@agentmail.to>
Date:   Fri Sep 11 18:17:39 2026 +0000

    ci: prep for 3.15t — install libhdf5-dev on pre-release Python; pin scikit-learn>=1.9.1 (#15283)
    
    Land the non-3.15t-gated pieces of #15105 ahead of GA:
    - build.yml/sphinx.yml: install libhdf5-dev only when running a pre-release
      interpreter (keras needs hdf5 there); guarded so it is a no-op on final builds.
    - pyproject.toml: pin scikit-learn>=1.9.1, the first release with cp315t
      free-threaded wheels, so uv resolves a wheel instead of building from source.
    
    The .python-version bump to 3.15t stays in #15105 as a draft until 3.15 GA.

commit 2853adfbc21151c79710379bd031836b3fd87ff1
Author: github-actions[bot] <41898282+github-actions[bot]@users.noreply.github.com>
Date:   Fri Sep 11 18:43:26 2026 +0200

    chore: refresh Hacktoberfest 2026 prep tracker (#15280)
    
    Co-authored-by: cclauss <cclauss@users.noreply.github.com>

commit 38be0a698615c94cb3f496f5f2cbf3bccb299c25
Author: Jubayer Ahmed Sojib <151145553+Clear20-22@users.noreply.github.com>
Date:   Fri Sep 11 22:42:34 2026 +0600

    Add Rotating Calipers algorithm for convex polygon diameter (#15275)
    
    * Add Rotating Calipers algorithm for convex polygon diameter
    
    * refactor: define Point as NamedTuple class to adhere to naming conventions
    
    ---------
    
    Co-authored-by: Christian Clauss <cclauss@me.com>

commit 1eb3c71d7f84ea4e8ba6bcec2accf11a175532b2
Author: BHUMIKA KADU✨ <kadubhumika2468@gmail.com>
Date:   Fri Sep 11 22:10:07 2026 +0530

    Fix invalid parameter default (#15281)
    
    * updating DIRECTORY.md
    
    * ty: fix invalid parameter defaults
    
    * Fix invalid parameter defaults
    
    ---------
    
    Co-authored-by: kadubhumika <kadubhumika@users.noreply.github.com>

commit 3825c3e809e362e5eddce0e5cf0527737b667c5a
Author: Jubayer Ahmed Sojib <151145553+Clear20-22@users.noreply.github.com>
Date:   Fri Sep 11 22:39:03 2026 +0600

    Add Andrew's Monotone Chain convex hull algorithm (#15165)
    
    * Add Andrew's Monotone Chain convex hull algorithm
    
    * Apply suggestion from @cclauss
    
    * [pre-commit.ci] auto fixes from pre-commit.com hooks
    
    for more information, see https://pre-commit.ci
    
    ---------
    
    Co-authored-by: Christian Clauss <cclauss@me.com>
    Co-authored-by: pre-commit-ci[bot] <66853113+pre-commit-ci[bot]@users.noreply.github.com>
