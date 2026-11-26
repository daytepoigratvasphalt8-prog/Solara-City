# SOLARA CITY — Android 3D Open World Game (Unity 6 URP) — v0.2.0

Оригинальная 3D-игра с открытым миром для Android на базе **Unity 6 (6000.0 LTS)**, **C#** и **Universal Render Pipeline (URP)**.

## Что обновлено в версии v0.2.0 (Фокус: визуальное и техническое качество)

- **Честный аудит 3D-ресурсов (`Docs/ASSET_AUDIT_REPORT.md`):** выявлены все примитивные заглушки и подготовлен инструмент `Solara City → 3. Run 3D Asset & Mobile GPU Audit`.
- **Инфраструктура бесшовной замены 3D-ассетов (`VisualAssetCatalog`):** добавлен `Assets/Resources/SolaraVisualCatalog.asset` для подключения реальных FBX/Prefab моделей персонажа, авто и зданий без изменения игровой логики.
- **Подготовка к Humanoid Rig и анимациям:** добавлен `CharacterAnimationBridge` (совместим с Mixamo / Humanoid Animator) и генератор контроллера `SolaraHumanoid_Template.controller` (Idle, Walk, Run, Jump, EnterVehicle, DrivingSeated, ExitVehicle).
- **Подготовка к детальному транспорту:** добавлен `VehicleVisualBinding` (автопривязка колёс, посадки водителя, точки входа и динамических стоп-сигналов) и улучшена геометрия/пропорции временных машин.
- **Улучшенные материалы, освещение и отражения:** добавлен `ProceduralTextureGenerator` (PBR-текстуры с Normal Map для асфальта, тротуара, металла и ночных окон небоскрёбов), Trilight Ambient и мобильный `EnvironmentReflectionRig` (`ReflectionProbe` 128×128 с обновлением раз в 2 игровых часа).
- **Автооптимизация под мобильные GPU (`MobileAssetImportProcessor`):** автоматический импорт с `ASTC_6x6`/`ASTC_5x5`, сжатием мешей, отключением Read/Write и автонастройкой Humanoid Avatar.
- **Обновлённый CI/CD (`android-build.yml`):** сборка APK v0.2.0 с автоматическим номером сборки, проверкой ассетов и выгрузкой отчёта аудита в артефакты.

## Быстрый старт в Unity 6

1. Распакуйте архив и откройте папку проекта в **Unity 6 (6000.0.32f1 LTS)** с модулем **Android Build Support**.
2. В меню Unity выполните: **`Solara City → 1. Configure Android + URP & Generate District Scene`**.
3. Для просмотра текущего отчёта по 3D-ассетам: **`Solara City → 3. Run 3D Asset & Mobile GPU Audit`**.
4. Откройте `Assets/Scenes/SolaraCity_District01.unity` и нажмите **Play**.

## Документация

- [`Docs/ASSET_AUDIT_REPORT.md`](Docs/ASSET_AUDIT_REPORT.md) — полный аудит примитивов и состояния ресурсов.
- [`Docs/ASSET_MIGRATION_PLAN.md`](Docs/ASSET_MIGRATION_PLAN.md) — план и техтребования перехода к качественным 3D-ассетам под Android GPU.
- [`Docs/ARCHITECTURE.md`](Docs/ARCHITECTURE.md) — архитектура модулей.
- [`Docs/GITHUB_ACTIONS_SETUP.md`](Docs/GITHUB_ACTIONS_SETUP.md) — настройка секретов и автоматической сборки APK.
