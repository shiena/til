Unity5.5のParticle Systemは初期マテリアルがNoneになっているので白い粒子ではなくピンクの四角になってしまう。

Particle Effect -> Render -> Materialに`Default-Particle`を設定すると白い粒子になる。

MaterialがNoneの場合
![Material-None)](particle_material_none.png)

MaterialがDefaultの場合
![Material-Default)](particle_material_default.png)

Perticle Effectの設定画面
![Particle Effect](particle_effect.png)
