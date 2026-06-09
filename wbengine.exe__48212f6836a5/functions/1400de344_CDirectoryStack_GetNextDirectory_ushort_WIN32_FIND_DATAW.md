# CDirectoryStack::GetNextDirectory(ushort * *,_WIN32_FIND_DATAW *)

- ea: `0x1400de344`
- end: `0x1400de91f`
- name: `?GetNextDirectory@CDirectoryStack@@QEAAJPEAPEAGPEAU_WIN32_FIND_DATAW@@@Z`
- size: `1499`
- prototype: `__int64 __fastcall(CDirectoryStack *__hidden this, unsigned __int16 **, struct _WIN32_FIND_DATAW *)`
- caller_count: `1`
- callee_count: `20`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1400df638`

## callees

- `0x140006984`
- `0x140006ca8`
- `0x140006d7c`
- `0x140008ac8`
- `0x140014200`
- `0x14003c69c`
- `0x1400d9fd4`
- `0x1400da030`
- `0x1400da05c`
- `0x1400db9b8`
- `0x1400dbd44`
- `0x1400dc020`
- `0x1400dc388`
- `0x1400ddd94`
- `0x1400de1f8`
- `0x1400de344`
- `0x1400de928`
- `0x1400dedcc`
- `0x1400e3d54`
- `0x140134d20`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1400de4d9`
- `KERNEL32!RaiseException` at `0x1400de5a0`
- `KERNEL32!RaiseException` at `0x1400de5f3`
- `KERNEL32!RaiseException` at `0x1400de61e`
- `KERNEL32!RaiseException` at `0x1400de75b`
- `KERNEL32!RaiseException` at `0x1400de809`
- `KERNEL32!RaiseException` at `0x1400de4d9`
- `KERNEL32!RaiseException` at `0x1400de5a0`
- `KERNEL32!RaiseException` at `0x1400de5f3`
- `KERNEL32!RaiseException` at `0x1400de61e`
- `KERNEL32!RaiseException` at `0x1400de75b`
- `KERNEL32!RaiseException` at `0x1400de809`

## string_xrefs

- `0x1400de38b`: `base\stor\blb\dsm\dsmfs\dll\directorystack.cpp`
- `0x1400de3a8`: `base\stor\blb\dsm\dsmfs\dll\directorystack.cpp`
- `0x1400de3c9`: `base\stor\blb\dsm\dsmfs\dll\directorystack.cpp`
- `0x1400de411`: `base\stor\blb\dsm\dsmfs\dll\directorystack.cpp`
- `0x1400de467`: `base\stor\blb\dsm\dsmfs\dll\directorystack.cpp`
- `0x1400de6ea`: `base\stor\blb\dsm\dsmfs\dll\directorystack.cpp`
- `0x1400de850`: `base\stor\blb\dsm\dsmfs\dll\directorystack.cpp`
- `0x1400de8e9`: `base\stor\blb\dsm\dsmfs\dll\directorystack.cpp`
- `0x1400de405`: `!pLatestDirectoryList->directoryList.IsEmpty()`
- `0x1400de37f`: `ppstrFilePath != 0`
- `0x1400de6de`: `m_strCurrentPath.Length() == 0`
- `0x1400de844`: `m_strCurrentPath.Compare(m_strRootDirectoryFullPath, m_fCaseSensitive, m_strCurrentPath.Length()) == 0`
- `0x1400de8dd`: `*ppstrFilePath || ((hr == ((HRESULT)1L)) && (m_queuedDirectoryTree.IsEmpty()))`

## pseudocode

```c

```
