# DllMain(x,x,x)

- ea: `0x10004fe6`
- end: `0x10005060`
- name: `_DllMain@12`
- size: `122`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x10003aa8`

## callees

- `0x1000307a`
- `0x1000308a`
- `0x10004fe6`
- `0x10009e7c`
- `0x1000a518`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005022`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10005022`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x10005002`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x10005002`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  int v3; // esi
  void *v4; // eax

  if ( fdwReason )
    return fdwReason != 1
        || (DisableThreadLibraryCalls(hinstDLL),
            g_module = hinstDLL,
            RasRtUtilsRegisterEtw(),
            (v4 = (void *)_InterlockedExchange(&g_loadevent, -1)) == 0)
        || SetEvent(v4);
  RasRtUtilsUnRegisterEtw();
  v3 = 1;
  if ( !lpvReserved )
  {
    if ( g_server )
    {
      v3 = TraceShutdownServer();
      g_server = 0;
    }
    StopWorkers();
  }
  return v3;
}

```

## disassembly

```asm
0x10004fe6  mov     edi, edi
0x10004fe8  push    ebp
0x10004fe9  mov     ebp, esp
0x10004feb  mov     eax, [ebp+fdwReason]
0x10004fee  push    esi
0x10004fef  sub     eax, 0
0x10004ff2  jz      short loc_1000502C
0x10004ff4  sub     eax, 1
0x10004ff7  jz      short loc_10004FFE
0x10004ff9  xor     esi, esi
0x10004ffb  inc     esi
0x10004ffc  jmp     short loc_10005059
0x10004ffe  mov     esi, [ebp+hinstDLL]
0x10005001  push    esi; hLibModule
0x10005002  call    ds:__imp__DisableThreadLibraryCalls@4; DisableThreadLibraryCalls(x)
0x10005008  mov     _g_module, esi
0x1000500e  call    _RasRtUtilsRegisterEtw@0; RasRtUtilsRegisterEtw()
0x10005013  or      eax, 0FFFFFFFFh
0x10005016  mov     ecx, offset _g_loadevent
0x1000501b  xchg    eax, [ecx]
0x1000501d  test    eax, eax
0x1000501f  jz      short loc_10004FF9
0x10005021  push    eax; hEvent
0x10005022  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10005028  mov     esi, eax
0x1000502a  jmp     short loc_10005059
0x1000502c  call    _RasRtUtilsUnRegisterEtw@0; RasRtUtilsUnRegisterEtw()
0x10005031  xor     esi, esi
0x10005033  inc     esi
0x10005034  cmp     [ebp+lpvReserved], 0
0x10005038  jnz     short loc_10005059
0x1000503a  cmp     _g_server, 0
0x10005041  jz      short loc_10005054
0x10005043  call    _TraceShutdownServer@4; TraceShutdownServer(x)
0x10005048  mov     esi, eax
0x1000504a  mov     _g_server, 0
0x10005054  call    _StopWorkers@0; StopWorkers()
0x10005059  mov     eax, esi
0x1000505b  pop     esi
0x1000505c  pop     ebp
0x1000505d  retn    0Ch
```
