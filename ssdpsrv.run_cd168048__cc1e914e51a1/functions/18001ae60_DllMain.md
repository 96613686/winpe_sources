# DllMain

- ea: `0x18001ae60`
- end: `0x18001aeab`
- name: `DllMain`
- size: `75`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180028644`

## callees

- `0x18001ae60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001ae7f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001ae7f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ae9d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ae9d`

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
0x18001ae60  sub     rsp, 28h
0x18001ae64  cmp     edx, 1
0x18001ae67  jz      short loc_18001AE78
0x18001ae69  test    edx, edx
0x18001ae6b  jz      short loc_18001AE96
0x18001ae6d  mov     eax, 1
0x18001ae72  add     rsp, 28h
0x18001ae76  retn
0x18001ae78  lea     rcx, ?g_csSsdpRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001ae7f  call    cs:__imp_InitializeCriticalSection
0x18001ae86  nop     dword ptr [rax+rax+00h]
0x18001ae8b  mov     eax, 1
0x18001ae90  add     rsp, 28h
0x18001ae94  retn
0x18001ae96  lea     rcx, ?g_csSsdpRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001ae9d  call    cs:__imp_DeleteCriticalSection
0x18001aea4  nop     dword ptr [rax+rax+00h]
0x18001aea9  jmp     short loc_18001AE6D
```
