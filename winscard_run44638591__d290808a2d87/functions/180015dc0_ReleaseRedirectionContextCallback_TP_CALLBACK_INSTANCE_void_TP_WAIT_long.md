# ReleaseRedirectionContextCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180015dc0`
- end: `0x180015e1b`
- name: `?ReleaseRedirectionContextCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `91`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180015dc0`
- `0x180015e24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015dcb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015dcb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015e14`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180015e03`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180015e03`

## pseudocode

```c
void __fastcall ReleaseRedirectionContextCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  struct _RTL_CRITICAL_SECTION *v4; // rcx

  EnterCriticalSection(&g_ReleaseRedirectionContextListCS);
  while ( 1 )
  {
    v4 = g_pReleaseRedirectionContextList;
    if ( !g_pReleaseRedirectionContextList )
      break;
    g_pReleaseRedirectionContextList = (LPCRITICAL_SECTION)g_pReleaseRedirectionContextList[12].DebugInfo;
    I_RedirectionContextCleanup(v4);
  }
  SetThreadpoolWait(g_ReleaseRedirectionContextWait, g_hReleaseRedirectionContextEvent, 0);
  LeaveCriticalSection(&g_ReleaseRedirectionContextListCS);
}

```

## disassembly

```asm
0x180015dc0  sub     rsp, 28h
0x180015dc4  lea     rcx, ?g_ReleaseRedirectionContextListCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180015dcb  call    cs:__imp_EnterCriticalSection
0x180015dd1  jmp     short loc_180015DE6
0x180015dd3  mov     rax, [rcx+1E0h]
0x180015dda  mov     cs:?g_pReleaseRedirectionContextList@@3PEAU_REDIRECTION_CONTEXT@@EA, rax; _REDIRECTION_CONTEXT * g_pReleaseRedirectionContextList
0x180015de1  call    ?I_RedirectionContextCleanup@@YAXPEAU_REDIRECTION_CONTEXT@@@Z; I_RedirectionContextCleanup(_REDIRECTION_CONTEXT *)
0x180015de6  mov     rcx, cs:?g_pReleaseRedirectionContextList@@3PEAU_REDIRECTION_CONTEXT@@EA; lpCriticalSection
0x180015ded  test    rcx, rcx
0x180015df0  jnz     short loc_180015DD3
0x180015df2  mov     rdx, cs:?g_hReleaseRedirectionContextEvent@@3PEAXEA; h
0x180015df9  xor     r8d, r8d; pftTimeout
0x180015dfc  mov     rcx, cs:?g_ReleaseRedirectionContextWait@@3PEAU_TP_WAIT@@EA; pwa
0x180015e03  call    cs:__imp_SetThreadpoolWait
0x180015e09  lea     rcx, ?g_ReleaseRedirectionContextListCS@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_ReleaseRedirectionContextListCS
0x180015e10  add     rsp, 28h
0x180015e14  jmp     cs:__imp_LeaveCriticalSection
```
