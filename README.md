# memove

memove is a public motion-library demo for reviewing generated human motion from source video through reconstruction to editable BVH.

**Live demo:** https://arthen97.github.io/memove-web/

## What you can do

- Browse 19 male/female motion pairs.
- Search by motion name, action ID, or category.
- Compare source video, reconstructed motion, and BVH preview.
- Inspect BVH files in an interactive Blender-style 3D viewport.
- Review motion lineage, validation status, duration, and physical-audit information.
- Add non-destructive BVH rotation keyframes and download a derived BVH.
- Inspect the editable motion blueprint.

## Quick start

1. Open the [memove public demo](https://arthen97.github.io/memove-web/).
2. Select **Explore**.
3. Search for a motion or use the category filters.
4. Click a motion card to open its workspace.
5. Switch between:
   - **BVH 3D** — interactive skeleton and keyframe workspace.
   - **Source** — validated male/female source videos.
   - **Reconstruction** — in-camera or global reconstructed motion.
   - **Compare** — source, reconstruction, and BVH shown together.
   - **Blueprint** — editable node view of the motion package.

## 3D viewport controls

- **Left-drag / middle-drag:** orbit
- **Shift + middle-drag:** pan
- **Mouse wheel:** zoom
- **Click a joint:** select a bone
- **Space:** play or pause
- **1 / 3 / 7:** front, side, or top view
- **Home:** frame all visible bodies

The viewport displays male and female motion together. Use the Outliner to hide either body, change rendering mode, show contact markers, or toggle trajectories.

## Editing BVH keyframes

1. Open **BVH 3D**.
2. Select a male or female bone in the viewport or Outliner.
3. Move the timeline to the required frame.
4. Adjust the rotation values in **Motion Inspector**.
5. Insert a keyframe.
6. Use **Download edited BVH** to export a new file.

The source BVH remains unchanged. Every edit is exported as a derived motion file.

## Understanding status labels

- **PASS:** the available validation gates passed.
- **REVIEW:** the motion is viewable, but at least one contact/support metric requires manual review.
- **Source BVH:** original exported motion.
- **Contact-refined:** a derived BVH was accepted only when refinement gates improved contact behavior without exceeding the source-deviation limit.

Passing a structural BVH check does not prove reconstruction accuracy. The physical audit is a plausibility diagnostic and should not be treated as ground-truth evaluation.

## Static demo limitations

This GitHub Pages deployment is a read-only public showcase:

- Library, videos, reports, BVH files, 3D viewing, comparison, and local BVH editing are available.
- The **Generate** page is visible as a product demonstration, but it cannot submit real production jobs.
- The cloud motion engine, private API, and GPU worker are intentionally not included.
- Edits remain in the browser until you download the derived BVH.

## Troubleshooting

### The site redirects to `memove.app`

An old browser may have cached the previous redirect. Open:

https://arthen97.github.io/memove-web/explore

If it still redirects, use a private/incognito window or clear site data for `arthen97.github.io`.

### A video does not play

- Wait briefly for the media file to load.
- Confirm that autoplay or media playback is not blocked.
- Reload the page and try another network.

### The 3D viewport is blank

- Wait for both BVH files to download.
- Press **Home** to frame the bodies.
- Confirm WebGL/hardware acceleration is enabled in the browser.
- Use the latest Chrome, Edge, Firefox, or Safari.

## 中文快速指南

1. 打开 [memove 公网展示](https://arthen97.github.io/memove-web/)。
2. 点击 **Explore** 浏览动作库。
3. 使用搜索栏或分类筛选动作。
4. 点击动作卡片进入工作区。
5. 使用 **BVH 3D / Source / Reconstruction / Compare / Blueprint** 查看不同阶段。
6. 在 3D 视图中拖拽旋转、滚轮缩放，按 `Home` 自动取景。
7. 选择骨骼后可在时间线上添加旋转关键帧，并下载新的 BVH；原始 BVH 不会被修改。

当前公网版本是只读展示版，真实视频生成、云端重建和 GPU 任务没有对外开放。

## Repository

This repository contains the production-built static demo and public motion assets. Internal service credentials, signed URLs, local filesystem paths, and private GPU configuration are excluded.

