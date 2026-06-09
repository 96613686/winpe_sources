# InitDllLight(void)

- ea: `0x180016c18`
- end: `0x180016c86`
- name: `?InitDllLight@@YAJXZ`
- size: `110`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180016db4`

## callees

- `0x180016c18`
- `0x180016fd8`
- `0x18004d350`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x180016c5b`
- `KERNEL32!LoadLibraryW` at `0x180016c5b`
- `KERNEL32!GetProcessHeap` at `0x180016c2b`
- `KERNEL32!GetProcessHeap` at `0x180016c2b`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180016c6d`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180016c6d`
- `KERNEL32!TlsAlloc` at `0x180016c43`
- `KERNEL32!TlsAlloc` at `0x180016c43`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180016c25`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180016c25`

## pseudocode

```c
__int64 InitDllLight(void)
{
  unsigned int InterestingFileNames; // ebx

  DisableThreadLibraryCalls(g_DllInstance);
  g_hXSPHeap = GetProcessHeap();
  InterestingFileNames = Names::GetInterestingFileNames();
  if ( !InterestingFileNames )
  {
    g_tlsiEventCateg = TlsAlloc();
    if ( g_tlsiEventCateg == -1 )
      return (unsigned int)GetLastWin32Error();
    LoadLibraryW(&Names::s_wszEngineFullPath);
    if ( !InitializeCriticalSectionAndSpinCount(&g_csExternalConfig, 0x7D0u) )
      return (unsigned int)GetLastWin32Error();
  }
  return InterestingFileNames;
}

```

## disassembly

```asm
0x180016c18  push    rbx
0x180016c1a  sub     rsp, 20h
0x180016c1e  mov     rcx, cs:?g_DllInstance@@3PEAUHINSTANCE__@@EA; hLibModule
0x180016c25  call    cs:__imp_DisableThreadLibraryCalls
0x180016c2b  call    cs:__imp_GetProcessHeap
0x180016c31  mov     cs:?g_hXSPHeap@@3PEAXEA, rax; void * g_hXSPHeap
0x180016c38  call    ?GetInterestingFileNames@Names@@SAJXZ; Names::GetInterestingFileNames(void)
0x180016c3d  mov     ebx, eax
0x180016c3f  test    eax, eax
0x180016c41  jnz     short loc_180016C7E
0x180016c43  call    cs:__imp_TlsAlloc
0x180016c49  mov     cs:?g_tlsiEventCateg@@3KA, eax; ulong g_tlsiEventCateg
0x180016c4f  cmp     eax, 0FFFFFFFFh
0x180016c52  jz      short loc_180016C77
0x180016c54  lea     rcx, ?s_wszEngineFullPath@Names@@0PAGA; lpLibFileName
0x180016c5b  call    cs:__imp_LoadLibraryW
0x180016c61  mov     edx, 7D0h; dwSpinCount
0x180016c66  lea     rcx, ?g_csExternalConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180016c6d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180016c73  test    eax, eax
0x180016c75  jnz     short loc_180016C7E
0x180016c77  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180016c7c  mov     ebx, eax
0x180016c7e  mov     eax, ebx
0x180016c80  add     rsp, 20h
0x180016c84  pop     rbx
0x180016c85  retn
```
