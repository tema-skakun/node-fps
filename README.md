# Frontend Developer (React, TypeScript, React Flow)

## Описание

Этот проект, позволяет строить граф из нод.
Каждая нода инициализируется случайным словарём значений. При соединении двух нод данные из исходной ноды добавляются в целевую.
На экране также отображается текущий FPS (кадры в секунду).

## Основная проблема

При количестве нод 3+ во время перетаскивания ноды по рабочей области наблюдалось сильное проседание FPS.
Я выявил источник проблемы и устранил её.

> Основная причина падения FPS при перемещении нод это избыточные перерендеры всего дерева компонентов при любом изменении nodes в Redux. Это вызвано тем, что nodes и edges были в глобальном Redux-состоянии и обновлялись при каждом перемещении. Это вызывало повторный рендер всей ReactFlow.

> Решение: Убрать nodes и edges из Redux. Хранить их локально в компоненте App с помощью useState.

## Стек проекта

* Vite
* TypeScript
* React
* React Flow
