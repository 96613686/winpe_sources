# DllMain

- ea: `0x180019ca0`
- end: `0x180019cdd`
- name: `DllMain`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800268a4`

## callees

- `0x180019ca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180019cbe`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180019cbe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019cd5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019cd5`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
  {
    InitializeCriticalSection(&g_csSsdpRef);
    return 1;
  }
  else
  {
    if ( !fdwReason )
      DeleteCriticalSection(&g_csSsdpRef);
    return 1;
  }
}

```

## disassembly

```asm
0x180019ca0  sub     rsp, 28h
0x180019ca4  cmp     edx, 1
0x180019ca7  jz      short loc_180019CB7
0x180019ca9  test    edx, edx
0x180019cab  jz      short loc_180019CCE
0x180019cad  mov     eax, 1
0x180019cb2  add     rsp, 28h
0x180019cb6  retn
0x180019cb7  lea     rcx, ?g_csSsdpRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180019cbe  call    cs:__imp_InitializeCriticalSection
0x180019cc4  mov     eax, 1
0x180019cc9  add     rsp, 28h
0x180019ccd  retn
0x180019cce  lea     rcx, ?g_csSsdpRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180019cd5  call    cs:__imp_DeleteCriticalSection
0x180019cdb  jmp     short loc_180019CAD
```
