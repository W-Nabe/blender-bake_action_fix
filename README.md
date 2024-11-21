# blender-bake_action_fix
Fixing "Damped Track" Dependency Cycles During "Bake Action"


## 修正内容

以下の問題を解決するための修正を行いました：

- DAMPED TRACKを子ボーンに対して連続的に設定した場合に発生する依存関係のサイクルエラーの解決
- アニメーションベイク時に、DAMPED TRACKが最終的に適用された状態でベイクできるようにするための修正

アニメーションベイク前にフレームセットを複数回行うことで、ボーンの依存関係の安定化を図っています。多くの依存関係がある場合は、10回を30回や40回に指定しなおすとよいでしょう。

### 参照
https://projects.blender.org/blender/blender/issues/125041

> I have a rigged character model with rigify. Hair bones have a bone constraints called "Damped Track", when I rotating for example firse bone it makes other bones lag about 1 fps. I pinned blend file "test" to the description. In this file you will see 2 bones of chain with the same constraints, first work with no problem, but second is bugging.


## Fixes

We have implemented fixes for the following issues:

- Resolving cycle dependency errors when Damped Track is continuously set on child bones
- Ensuring proper Bake Action with Damped Track constraints in their final applied state

By performing multiple frame sets before Bake Action, we stabilize bone dependencies. For scenarios with complex dependencies, it is recommended to adjust the frame set count to 30 or 40 instead of 10.

### Reference
https://projects.blender.org/blender/blender/issues/125041

> I have a rigged character model with rigify. Hair bones have a bone constraints called "Damped Track", when I rotating for example firse bone it makes other bones lag about 1 fps. I pinned blend file "test" to the description. In this file you will see 2 bones of chain with the same constraints, first work with no problem, but second is bugging. CopyRetryClaude does not have the ability to run the code it generates yet.Claude can make mistakes. Please double-check responses.
