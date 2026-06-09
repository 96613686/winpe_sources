# xxxInitializeMoveSizeData(tagWND *,MOVESIZEDATA *,uint,ulong)

- ea: `0x140279bb0`
- end: `0x14027ad4c`
- name: `?xxxInitializeMoveSizeData@@YAXPEAUtagWND@@PEAUMOVESIZEDATA@@IK@Z`
- size: `4508`
- prototype: `void __fastcall(struct tagWND *, struct MOVESIZEDATA *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `37`
- tags: `broker_com_uri`

## callers

- `0x14027ad54`
- `0x1402c96b0`

## callees

- `0x1400139c8`
- `0x14001a5e4`
- `0x14001bf00`
- `0x14001c55c`
- `0x14001d5b4`
- `0x140020d30`
- `0x1400291d0`
- `0x1400b71ac`
- `0x1400bcaa0`
- `0x1400bcac8`
- `0x1400bf0e0`
- `0x1400dd1d0`
- `0x1400df540`
- `0x1400e4134`
- `0x1400e42d4`
- `0x1400eb064`
- `0x1400ec110`
- `0x1400ed244`
- `0x1401751f4`
- `0x140179cac`
- `0x14017a758`
- `0x14017b184`
- `0x140199a78`
- `0x1401a0c64`
- `0x1401ab7d0`
- `0x1401b8df8`
- `0x1401f06f0`
- `0x14020cb30`
- `0x1402219d0`
- `0x140252680`
- `0x14025811c`
- `0x140279bb0`
- `0x140288804`
- `0x1402913f0`
- `0x1402c95cc`
- `0x1402ca68c`
- `0x140341ff0`

## import_xrefs

- `win32kbase!TransformPointBetweenCoordinateSpaces` at `0x14027a07e`
- `win32kbase!TransformPointBetweenCoordinateSpaces` at `0x14027a07e`
- `win32kbase!GreGetRgnBox` at `0x140279fb4`
- `win32kbase!GreGetRgnBox` at `0x140279fb4`
- `win32kbase!GreRectInRegion` at `0x14027a091`
- `win32kbase!GreRectInRegion` at `0x14027a091`
- `win32kbase!?SetClip@CCursorClip@@QEAAXUtagRECT@@@Z` at `0x14027a36f`
- `win32kbase!?SetClip@CCursorClip@@QEAAXUtagRECT@@@Z` at `0x14027a36f`
- `win32kbase!MoveSizeReadAndClearMouseMoveBoundHitFlags` at `0x14027ad17`
- `win32kbase!MoveSizeReadAndClearMouseMoveBoundHitFlags` at `0x14027ad17`
- `win32kbase!GrePtInRegion` at `0x14027a0c3`
- `win32kbase!GrePtInRegion` at `0x14027a0c3`
- `win32kbase!LogicalToPhysicalDPIRect` at `0x14027a00e`
- `win32kbase!LogicalToPhysicalDPIRect` at `0x14027a00e`
- `win32kbase!GetDispInfo` at `0x140279ef4`
- `win32kbase!GetDispInfo` at `0x140279f1b`
- `win32kbase!GetDispInfo` at `0x140279ef4`
- `win32kbase!GetDispInfo` at `0x140279f1b`
- `win32kbase!TransformRectBetweenCoordinateSpaces` at `0x140279f80`
- `win32kbase!TransformRectBetweenCoordinateSpaces` at `0x14027a062`
- `win32kbase!TransformRectBetweenCoordinateSpaces` at `0x140279f80`
- `win32kbase!TransformRectBetweenCoordinateSpaces` at `0x14027a062`
- `win32kbase!IsWindowDesktopComposed` at `0x140279fde`
- `win32kbase!IsWindowDesktopComposed` at `0x140279fde`
- `win32kbase!ValidateHmonitorNoRip` at `0x14027aa8b`
- `win32kbase!ValidateHmonitorNoRip` at `0x14027aa8b`
- `WIN32K!W32GetUserSessionState` at `0x140279c42`
- `WIN32K!W32GetUserSessionState` at `0x140279cb2`
- `WIN32K!W32GetUserSessionState` at `0x140279d7b`
- `WIN32K!W32GetUserSessionState` at `0x140279e52`
- `WIN32K!W32GetUserSessionState` at `0x140279ed9`
- `WIN32K!W32GetUserSessionState` at `0x14027a195`
- `WIN32K!W32GetUserSessionState` at `0x14027a22d`
- `WIN32K!W32GetUserSessionState` at `0x14027a2d4`
- `WIN32K!W32GetUserSessionState` at `0x14027a34f`
- `WIN32K!W32GetUserSessionState` at `0x14027a389`
- `WIN32K!W32GetUserSessionState` at `0x14027a3aa`
- `WIN32K!W32GetUserSessionState` at `0x14027a42b`
- `WIN32K!W32GetUserSessionState` at `0x14027a5f1`
- `WIN32K!W32GetUserSessionState` at `0x14027a743`
- `WIN32K!W32GetUserSessionState` at `0x14027a840`
- `WIN32K!W32GetUserSessionState` at `0x14027a8ae`
- `WIN32K!W32GetUserSessionState` at `0x14027a978`
- `WIN32K!W32GetUserSessionState` at `0x14027aa03`
- `WIN32K!W32GetUserSessionState` at `0x14027ab57`
- `WIN32K!W32GetUserSessionState` at `0x14027ac6b`
- `WIN32K!W32GetUserSessionState` at `0x140279c42`
- `WIN32K!W32GetUserSessionState` at `0x140279cb2`
- `WIN32K!W32GetUserSessionState` at `0x140279d7b`
- `WIN32K!W32GetUserSessionState` at `0x140279e52`
- `WIN32K!W32GetUserSessionState` at `0x140279ed9`
- `WIN32K!W32GetUserSessionState` at `0x14027a195`
- `WIN32K!W32GetUserSessionState` at `0x14027a22d`
- `WIN32K!W32GetUserSessionState` at `0x14027a2d4`
- `WIN32K!W32GetUserSessionState` at `0x14027a34f`
- `WIN32K!W32GetUserSessionState` at `0x14027a389`
- `WIN32K!W32GetUserSessionState` at `0x14027a3aa`
- `WIN32K!W32GetUserSessionState` at `0x14027a42b`
- `WIN32K!W32GetUserSessionState` at `0x14027a5f1`
- `WIN32K!W32GetUserSessionState` at `0x14027a743`
- `WIN32K!W32GetUserSessionState` at `0x14027a840`
- `WIN32K!W32GetUserSessionState` at `0x14027a8ae`
- `WIN32K!W32GetUserSessionState` at `0x14027a978`
- `WIN32K!W32GetUserSessionState` at `0x14027aa03`
- `WIN32K!W32GetUserSessionState` at `0x14027ab57`
- `WIN32K!W32GetUserSessionState` at `0x14027ac6b`

## pseudocode

```c

```
