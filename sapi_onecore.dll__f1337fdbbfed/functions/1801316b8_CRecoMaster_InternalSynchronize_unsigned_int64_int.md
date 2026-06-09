# CRecoMaster::InternalSynchronize(unsigned __int64,int)

- ea: `0x1801316b8`
- end: `0x180131b88`
- name: `?InternalSynchronize@CRecoMaster@@QEAAJ_KH@Z`
- size: `1232`
- prototype: `__int64 __fastcall(CRecoMaster *__hidden this, unsigned __int64, int)`
- caller_count: `4`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18012c8ac`
- `0x1801311e4`
- `0x180134c98`
- `0x180137c00`

## callees

- `0x180013ec0`
- `0x180026508`
- `0x180045938`
- `0x18004fe48`
- `0x180050d0c`
- `0x180079e30`
- `0x18012af34`
- `0x18012d7c8`
- `0x18012e428`
- `0x1801308e4`
- `0x1801316b8`
- `0x18013750c`
- `0x180137f38`
- `0x18018d9d8`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180131b1b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180131b54`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180131b1b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180131b54`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180131707`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180131707`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18013187e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18013192e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18013187e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18013192e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18013183f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18013190b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18013183f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18013190b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180131716`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180131716`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180131923`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180131923`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x180131871`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x180131871`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x18013185a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x18013185a`

## string_xrefs

- `0x180131808`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x180131743`: `CRecoMaster: %ums to serve RequestSync; kinda slow?`
- `0x180131999`: `RecoMaster: InternalSynchronize wait failed with hr=0x%08x`
- `0x180131b3c`: `InternalSynchronize failed with 0x%08x, exiting engine thread`
- `0x180131b08`: `InternalSynchronize: gracefully exiting engine thread. engineRecoState = %S, activeRule=%d, m_ullLastSyncPos = %d, m_ullRecoInactivePos = %d, pause = %d`
- `0x18013181f`: `ReaderDiscardBuffers at pos %u`

## pseudocode

```c

```
