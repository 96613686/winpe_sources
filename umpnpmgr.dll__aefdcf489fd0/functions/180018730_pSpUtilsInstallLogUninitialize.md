# _pSpUtilsInstallLogUninitialize

- ea: `0x180018730`
- end: `0x1800187b0`
- name: `_pSpUtilsInstallLogUninitialize`
- size: `128`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000cab0`
- `0x18001632c`

## callees

- `0x180018730`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018749`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001876f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018795`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018749`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001876f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018795`

## pseudocode

```c
__int64 pSpUtilsInstallLogUninitialize()
{
  if ( InstallLogFilePath )
  {
    HeapFree(hHeap, 0, InstallLogFilePath);
    InstallLogFilePath = 0;
  }
  if ( EventLogFilePath )
  {
    HeapFree(hHeap, 0, EventLogFilePath);
    EventLogFilePath = 0;
  }
  if ( StringLogFilePath )
  {
    HeapFree(hHeap, 0, StringLogFilePath);
    StringLogFilePath = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180018730  sub     rsp, 28h
0x180018734  mov     r8, cs:InstallLogFilePath; lpMem
0x18001873b  test    r8, r8
0x18001873e  jz      short loc_18001875A
0x180018740  mov     rcx, cs:hHeap; hHeap
0x180018747  xor     edx, edx; dwFlags
0x180018749  call    cs:__imp_HeapFree
0x18001874f  mov     cs:InstallLogFilePath, 0
0x18001875a  mov     r8, cs:EventLogFilePath; lpMem
0x180018761  test    r8, r8
0x180018764  jz      short loc_180018780
0x180018766  mov     rcx, cs:hHeap; hHeap
0x18001876d  xor     edx, edx; dwFlags
0x18001876f  call    cs:__imp_HeapFree
0x180018775  mov     cs:EventLogFilePath, 0
0x180018780  mov     r8, cs:StringLogFilePath; lpMem
0x180018787  test    r8, r8
0x18001878a  jz      short loc_1800187A6
0x18001878c  mov     rcx, cs:hHeap; hHeap
0x180018793  xor     edx, edx; dwFlags
0x180018795  call    cs:__imp_HeapFree
0x18001879b  mov     cs:StringLogFilePath, 0
0x1800187a6  mov     eax, 1
0x1800187ab  add     rsp, 28h
0x1800187af  retn
```
