# DllMain

- ea: `0x180002dd0`
- end: `0x180002e83`
- name: `DllMain`
- size: `179`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003a24`

## callees

- `0x180002dd0`
- `0x180002e90`
- `0x18000a4a0`
- `0x18000a638`
- `0x18000a670`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002e12`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002e56`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002e12`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002e56`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002ded`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002ded`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  void *v5; // rcx

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      g_module = hinstDLL;
      McGenEventRegister_EventRegister();
      v5 = (void *)_InterlockedExchange64(&g_loadevent, -1);
      if ( v5 )
        return SetEvent(v5);
    }
  }
  else
  {
    if ( MICROSOFT_WINDOWS_RRAS_PROVIDER_Context )
      McGenEventUnregister_EventUnregister(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context);
    if ( !lpvReserved )
    {
      if ( g_server )
      {
        if ( g_server[2].DebugInfo && g_serverThread )
          SetEvent(g_server[2].DebugInfo);
        else
          TraceCleanUpServer(g_server);
        g_server = 0;
      }
      StopWorkers();
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180002dd0  mov     [rsp+arg_0], rbx
0x180002dd5  push    rdi
0x180002dd6  sub     rsp, 20h
0x180002dda  mov     rbx, r8
0x180002ddd  mov     rdi, rcx
0x180002de0  test    edx, edx
0x180002de2  jz      short loc_180002E1A
0x180002de4  cmp     edx, 1
0x180002de7  jnz     loc_180002E73
0x180002ded  call    cs:__imp_DisableThreadLibraryCalls
0x180002df3  mov     cs:g_module, rdi
0x180002dfa  call    McGenEventRegister_EventRegister
0x180002dff  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180002e06  xchg    rcx, cs:g_loadevent; hEvent
0x180002e0d  test    rcx, rcx
0x180002e10  jz      short loc_180002E73
0x180002e12  call    cs:__imp_SetEvent
0x180002e18  jmp     short loc_180002E78
0x180002e1a  cmp     cs:MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, 0
0x180002e22  jz      short loc_180002E30
0x180002e24  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002e2b  call    McGenEventUnregister_EventUnregister
0x180002e30  test    rbx, rbx
0x180002e33  jnz     short loc_180002E73
0x180002e35  mov     rcx, cs:g_server; hMem
0x180002e3c  test    rcx, rcx
0x180002e3f  jz      short loc_180002E6E
0x180002e41  mov     rax, [rcx+50h]
0x180002e45  test    rax, rax
0x180002e48  jz      short loc_180002E5E
0x180002e4a  cmp     cs:g_serverThread, rbx
0x180002e51  jz      short loc_180002E5E
0x180002e53  mov     rcx, rax; hEvent
0x180002e56  call    cs:__imp_SetEvent
0x180002e5c  jmp     short loc_180002E63
0x180002e5e  call    TraceCleanUpServer
0x180002e63  mov     cs:g_server, 0
0x180002e6e  call    StopWorkers
0x180002e73  mov     eax, 1
0x180002e78  mov     rbx, [rsp+28h+arg_0]
0x180002e7d  add     rsp, 20h
0x180002e81  pop     rdi
0x180002e82  retn
```
