# xxxInitializeMoveSizeData(tagWND *,MOVESIZEDATA *,uint,ulong)

- ea: `0x14027be60`
- end: `0x14027cffc`
- name: `?xxxInitializeMoveSizeData@@YAXPEAUtagWND@@PEAUMOVESIZEDATA@@IK@Z`
- size: `4508`
- prototype: `void __fastcall(struct tagWND *, struct MOVESIZEDATA *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `37`
- tags: `broker_com_uri`

## callers

- `0x14027d004`
- `0x1402cb5a0`

## callees

- `0x1400103f0`
- `0x140012790`
- `0x14001b9c0`
- `0x1400240e0`
- `0x140092764`
- `0x140094080`
- `0x1400946dc`
- `0x1400952d4`
- `0x1400c0418`
- `0x1400c636c`
- `0x1400dd43c`
- `0x1400e2cb0`
- `0x1400e2cd8`
- `0x1400e52f0`
- `0x14016b868`
- `0x14016ccb4`
- `0x140173a94`
- `0x140175838`
- `0x1401762ec`
- `0x14017cc14`
- `0x140186aac`
- `0x140187558`
- `0x140187f84`
- `0x14019bab8`
- `0x1401a2174`
- `0x1401aa194`
- `0x1401f4bc8`
- `0x14020ded0`
- `0x140214aac`
- `0x1402541a0`
- `0x14025957c`
- `0x14027be60`
- `0x14028acf4`
- `0x1402938dc`
- `0x1402cb4bc`
- `0x1402cc57c`
- `0x140342fa0`

## import_xrefs

- `win32kbase!TransformPointBetweenCoordinateSpaces` at `0x14027c32e`
- `win32kbase!TransformPointBetweenCoordinateSpaces` at `0x14027c32e`
- `win32kbase!GreGetRgnBox` at `0x14027c264`
- `win32kbase!GreGetRgnBox` at `0x14027c264`
- `win32kbase!GreRectInRegion` at `0x14027c341`
- `win32kbase!GreRectInRegion` at `0x14027c341`
- `win32kbase!?SetClip@CCursorClip@@QEAAXUtagRECT@@@Z` at `0x14027c61f`
- `win32kbase!?SetClip@CCursorClip@@QEAAXUtagRECT@@@Z` at `0x14027c61f`
- `win32kbase!MoveSizeReadAndClearMouseMoveBoundHitFlags` at `0x14027cfc7`
- `win32kbase!MoveSizeReadAndClearMouseMoveBoundHitFlags` at `0x14027cfc7`
- `win32kbase!GrePtInRegion` at `0x14027c373`
- `win32kbase!GrePtInRegion` at `0x14027c373`
- `win32kbase!LogicalToPhysicalDPIRect` at `0x14027c2be`
- `win32kbase!LogicalToPhysicalDPIRect` at `0x14027c2be`
- `win32kbase!GetDispInfo` at `0x14027c1a4`
- `win32kbase!GetDispInfo` at `0x14027c1cb`
- `win32kbase!GetDispInfo` at `0x14027c1a4`
- `win32kbase!GetDispInfo` at `0x14027c1cb`
- `win32kbase!TransformRectBetweenCoordinateSpaces` at `0x14027c230`
- `win32kbase!TransformRectBetweenCoordinateSpaces` at `0x14027c312`
- `win32kbase!TransformRectBetweenCoordinateSpaces` at `0x14027c230`
- `win32kbase!TransformRectBetweenCoordinateSpaces` at `0x14027c312`
- `win32kbase!IsWindowDesktopComposed` at `0x14027c28e`
- `win32kbase!IsWindowDesktopComposed` at `0x14027c28e`
- `win32kbase!ValidateHmonitorNoRip` at `0x14027cd3b`
- `win32kbase!ValidateHmonitorNoRip` at `0x14027cd3b`
- `WIN32K!W32GetUserSessionState` at `0x14027bef2`
- `WIN32K!W32GetUserSessionState` at `0x14027bf62`
- `WIN32K!W32GetUserSessionState` at `0x14027c02b`
- `WIN32K!W32GetUserSessionState` at `0x14027c102`
- `WIN32K!W32GetUserSessionState` at `0x14027c189`
- `WIN32K!W32GetUserSessionState` at `0x14027c445`
- `WIN32K!W32GetUserSessionState` at `0x14027c4dd`
- `WIN32K!W32GetUserSessionState` at `0x14027c584`
- `WIN32K!W32GetUserSessionState` at `0x14027c5ff`
- `WIN32K!W32GetUserSessionState` at `0x14027c639`
- `WIN32K!W32GetUserSessionState` at `0x14027c65a`
- `WIN32K!W32GetUserSessionState` at `0x14027c6db`
- `WIN32K!W32GetUserSessionState` at `0x14027c8a1`
- `WIN32K!W32GetUserSessionState` at `0x14027c9f3`
- `WIN32K!W32GetUserSessionState` at `0x14027caf0`
- `WIN32K!W32GetUserSessionState` at `0x14027cb5e`
- `WIN32K!W32GetUserSessionState` at `0x14027cc28`
- `WIN32K!W32GetUserSessionState` at `0x14027ccb3`
- `WIN32K!W32GetUserSessionState` at `0x14027ce07`
- `WIN32K!W32GetUserSessionState` at `0x14027cf1b`
- `WIN32K!W32GetUserSessionState` at `0x14027bef2`
- `WIN32K!W32GetUserSessionState` at `0x14027bf62`
- `WIN32K!W32GetUserSessionState` at `0x14027c02b`
- `WIN32K!W32GetUserSessionState` at `0x14027c102`
- `WIN32K!W32GetUserSessionState` at `0x14027c189`
- `WIN32K!W32GetUserSessionState` at `0x14027c445`
- `WIN32K!W32GetUserSessionState` at `0x14027c4dd`
- `WIN32K!W32GetUserSessionState` at `0x14027c584`
- `WIN32K!W32GetUserSessionState` at `0x14027c5ff`
- `WIN32K!W32GetUserSessionState` at `0x14027c639`
- `WIN32K!W32GetUserSessionState` at `0x14027c65a`
- `WIN32K!W32GetUserSessionState` at `0x14027c6db`
- `WIN32K!W32GetUserSessionState` at `0x14027c8a1`
- `WIN32K!W32GetUserSessionState` at `0x14027c9f3`
- `WIN32K!W32GetUserSessionState` at `0x14027caf0`
- `WIN32K!W32GetUserSessionState` at `0x14027cb5e`
- `WIN32K!W32GetUserSessionState` at `0x14027cc28`
- `WIN32K!W32GetUserSessionState` at `0x14027ccb3`
- `WIN32K!W32GetUserSessionState` at `0x14027ce07`
- `WIN32K!W32GetUserSessionState` at `0x14027cf1b`

## pseudocode

```c

```
