# TODO — Sentience

- [ ] Add visible movement, jump, crouch, Interface, and route-ability controls in `src/game.rs` and `src/ui.rs`, supporting simultaneous touch inputs through toolkit helpers. Update tutorial/objective text, `README.md`, and `game_page.json` to name visible controls alongside shortcuts; verify gameplay and recovery without a keyboard (§7.5).
- [ ] Migrate `src/state_tests.rs`, `src/route_tests.rs`, `src/map_spec*_tests.rs`, and `src/data/tests.rs`, including helpers, into `tests/` before adding coverage. Expose intentional game APIs through `src/lib.rs`, use the library from `main.rs`, and remove test declarations from `src/`. Preserve regressions, consolidate related cases toward five per feature, and correct the gate test's obsolete “non-test lines” comment (§11, §2.2).
- [ ] Add semantic validation after toolkit loading in `src/data.rs`: enforce campaign size/order, unique level and texture IDs, required texture references, and valid movement/balance ranges. Return actionable errors and test invalid inputs as well as the shipped data (§5.3).
- [ ] Move authored level layouts, guard/setpiece definitions, and upgrade/combat balance from `src/levels.rs`, `src/level_*.rs`, `src/entities.rs`, `src/progression.rs`, and `src/state.rs` into typed JSON under `assets/`; load through the toolkit and preserve campaign behavior (§5.3).
- [ ] Move hardcoded UI labels, objectives, notifications, ending text, and world labels from Rust into toolkit-loaded JSON under `assets/`, with validated text keys (§5.3).
- [ ] Extract cohesive simulation/persistence responsibilities from `src/state.rs` (770 lines) and split oversized functions, including guard-room builders, `ui::draw_side_panel`, and `world_render::draw_guard`. Keep functions within 100 lines and every Rust file within 800 total lines; coordinate guard-builder changes with the JSON migration (§2.2, §4.1).
- [ ] Replace duplicated button interaction logic in `src/ui.rs` (`draw_button`, `draw_choice_card`) with shared toolkit widgets/input helpers while preserving appearance, disabled states, release activation, and returned UI actions (§7.1–7.4).
- [ ] After test migration, add focused gameplay regressions for line-of-sight occlusion/range, smoke/darkness, cloak expiry, crouch/jump boundaries, and capture/retry transitions. Add separate progression coverage for Helpful/Gremlin upgrade scaling, caps, and route ties through `src/progression.rs` (§11).
- [ ] After test migration, cover `migrate_save_value` and restored sessions: wrapped/raw saves, legacy ending repair, malformed payloads, level-index clamping, and choice truncation with preserved morality/upgrades (§11).

## Settings and display

- [ ] Add a player-accessible Settings option with a persisted Fullscreen toggle.
