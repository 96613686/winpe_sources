# SpShutdown(void)

- ea: `0x180017b70`
- end: `0x180017c21`
- name: `?SpShutdown@@YAJXZ`
- size: `177`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x18001528c`
- `0x180017b70`
- `0x18001c0ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017bd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017bd3`
- `ntdll!EtwUnregisterTraceGuids` at `0x180017b9d`
- `ntdll!EtwUnregisterTraceGuids` at `0x180017b9d`
- `ntdll!RtlDeleteCriticalSection` at `0x180017bc1`
- `ntdll!RtlDeleteCriticalSection` at `0x180017bc1`
- `LSASRV!LsaICancelNotification` at `0x180017bf0`
- `LSASRV!LsaICancelNotification` at `0x180017bf0`

## pseudocode

```c
__int64 SpShutdown(void)
{
  _QWORD *v0; // rbx
  struct _RTL_CRITICAL_SECTION *v1; // rcx

  TSUnloadCredTable();
  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    while ( v0 )
    {
      if ( v0[1] )
      {
        EtwUnregisterTraceGuids();
        v0[1] = 0;
      }
      v0 = (_QWORD *)*v0;
    }
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
  }
  RtlDeleteCriticalSection(&WTSVirtualChannelLoaderLock);
  if ( g_hKeyParams )
  {
    RegCloseKey(g_hKeyParams);
    g_hKeyParams = 0;
  }
  if ( g_LsaNotification )
  {
    LsaICancelNotification();
    g_LsaNotification = 0;
  }
  v1 = (struct _RTL_CRITICAL_SECTION *)_InterlockedExchange64((volatile __int64 *)&TSGlobalEventLogHandle, 0);
  if ( v1 )
    NetpEventlogClose(v1);
  return 0;
}

```

## disassembly

```asm
0x180017b70  mov     [rsp+arg_0], rbx
0x180017b75  push    rsi
0x180017b76  sub     rsp, 20h
0x180017b7a  call    ?TSUnloadCredTable@@YAXXZ; TSUnloadCredTable(void)
0x180017b7f  mov     rbx, cs:WPP_GLOBAL_Control
0x180017b86  lea     rsi, WPP_GLOBAL_Control
0x180017b8d  cmp     rbx, rsi
0x180017b90  jz      short loc_180017BBA
0x180017b92  jmp     short loc_180017BAE
0x180017b94  mov     rcx, [rbx+8]
0x180017b98  test    rcx, rcx
0x180017b9b  jz      short loc_180017BAB
0x180017b9d  call    cs:__imp_EtwUnregisterTraceGuids
0x180017ba3  mov     qword ptr [rbx+8], 0
0x180017bab  mov     rbx, [rbx]
0x180017bae  test    rbx, rbx
0x180017bb1  jnz     short loc_180017B94
0x180017bb3  mov     cs:WPP_GLOBAL_Control, rsi
0x180017bba  lea     rcx, ?WTSVirtualChannelLoaderLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180017bc1  call    cs:__imp_RtlDeleteCriticalSection
0x180017bc7  mov     rcx, cs:?g_hKeyParams@@3PEAUHKEY__@@EA; hKey
0x180017bce  test    rcx, rcx
0x180017bd1  jz      short loc_180017BE4
0x180017bd3  call    cs:__imp_RegCloseKey
0x180017bd9  mov     cs:?g_hKeyParams@@3PEAUHKEY__@@EA, 0; HKEY__ * g_hKeyParams
0x180017be4  mov     rcx, cs:?g_LsaNotification@@3PEAXEA; void * g_LsaNotification
0x180017beb  test    rcx, rcx
0x180017bee  jz      short loc_180017C01
0x180017bf0  call    cs:__imp_LsaICancelNotification
0x180017bf6  mov     cs:?g_LsaNotification@@3PEAXEA, 0; void * g_LsaNotification
0x180017c01  xor     ecx, ecx
0x180017c03  xchg    rcx, cs:?TSGlobalEventLogHandle@@3PEAXEA; lpCriticalSection
0x180017c0a  test    rcx, rcx
0x180017c0d  jz      short loc_180017C14
0x180017c0f  call    NetpEventlogClose
0x180017c14  mov     rbx, [rsp+28h+arg_0]
0x180017c19  xor     eax, eax
0x180017c1b  add     rsp, 20h
0x180017c1f  pop     rsi
0x180017c20  retn
```
