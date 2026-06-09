# I_RedirectionContextReleaseRegister(void)

- ea: `0x180017580`
- end: `0x180017698`
- name: `?I_RedirectionContextReleaseRegister@@YAKXZ`
- size: `280`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006c80`

## callees

- `0x180007bc0`
- `0x180017580`
- `0x18001991c`
- `0x1800239b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800175db`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800175db`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180017640`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180017640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175ed`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001760f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001760f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180017633`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180017633`

## pseudocode

```c
__int64 __fastcall I_RedirectionContextReleaseRegister(__int64 a1)
{
  HANDLE EventW; // rax
  __int64 v2; // rcx
  DWORD LastError; // ebx
  struct _TP_WAIT *v4; // rcx
  int v5; // r9d

  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids);
  }
  EventW = g_hReleaseRedirectionContextEvent;
  if ( !g_hReleaseRedirectionContextEvent )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    g_hReleaseRedirectionContextEvent = EventW;
    if ( !EventW )
      goto LABEL_7;
  }
  v4 = g_ReleaseRedirectionContextWait;
  if ( g_ReleaseRedirectionContextWait )
  {
LABEL_11:
    LastError = 0;
    SetThreadpoolWait(v4, EventW, 0);
    InitializeCriticalSection(&g_ReleaseRedirectionContextListCS);
    g_fReleaseRedirectionContextRegistered = 1;
    goto LABEL_12;
  }
  g_ReleaseRedirectionContextWait = CreateThreadpoolWait(ReleaseRedirectionContextCallback, 0, 0);
  v4 = g_ReleaseRedirectionContextWait;
  if ( g_ReleaseRedirectionContextWait )
  {
    EventW = g_hReleaseRedirectionContextEvent;
    goto LABEL_11;
  }
LABEL_7:
  LastError = GetLastError();
LABEL_12:
  WppTraceIndent(v2, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids,
      v5,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180017580  mov     [rsp+arg_0], rbx
0x180017585  push    rdi
0x180017586  sub     rsp, 30h
0x18001758a  xor     edx, edx
0x18001758c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180017591  mov     rcx, cs:WPP_GLOBAL_Control
0x180017598  lea     rdi, WPP_GLOBAL_Control
0x18001759f  cmp     rcx, rdi
0x1800175a2  jz      short loc_1800175C5
0x1800175a4  test    byte ptr [rcx+1Ch], 2
0x1800175a8  jz      short loc_1800175C5
0x1800175aa  cmp     byte ptr [rcx+19h], 5
0x1800175ae  jb      short loc_1800175C5
0x1800175b0  mov     rcx, [rcx+10h]
0x1800175b4  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x1800175bb  mov     edx, 16h
0x1800175c0  call    WPP_SF_s
0x1800175c5  mov     rax, cs:?g_hReleaseRedirectionContextEvent@@3PEAXEA; void * g_hReleaseRedirectionContextEvent
0x1800175cc  test    rax, rax
0x1800175cf  jnz     short loc_1800175F7
0x1800175d1  xor     r9d, r9d; lpName
0x1800175d4  xor     r8d, r8d; bInitialState
0x1800175d7  xor     edx, edx; bManualReset
0x1800175d9  xor     ecx, ecx; lpEventAttributes
0x1800175db  call    cs:__imp_CreateEventW
0x1800175e1  mov     cs:?g_hReleaseRedirectionContextEvent@@3PEAXEA, rax; void * g_hReleaseRedirectionContextEvent
0x1800175e8  test    rax, rax
0x1800175eb  jnz     short loc_1800175F7
0x1800175ed  call    cs:__imp_GetLastError
0x1800175f3  mov     ebx, eax
0x1800175f5  jmp     short loc_180017650
0x1800175f7  mov     rcx, cs:?g_ReleaseRedirectionContextWait@@3PEAU_TP_WAIT@@EA; _TP_WAIT * g_ReleaseRedirectionContextWait
0x1800175fe  test    rcx, rcx
0x180017601  jnz     short loc_18001762B
0x180017603  xor     r8d, r8d; pcbe
0x180017606  lea     rcx, ?ReleaseRedirectionContextCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18001760d  xor     edx, edx; pv
0x18001760f  call    cs:__imp_CreateThreadpoolWait
0x180017615  mov     cs:?g_ReleaseRedirectionContextWait@@3PEAU_TP_WAIT@@EA, rax; _TP_WAIT * g_ReleaseRedirectionContextWait
0x18001761c  mov     rcx, rax; pwa
0x18001761f  test    rax, rax
0x180017622  jz      short loc_1800175ED
0x180017624  mov     rax, cs:?g_hReleaseRedirectionContextEvent@@3PEAXEA; void * g_hReleaseRedirectionContextEvent
0x18001762b  xor     r8d, r8d; pftTimeout
0x18001762e  mov     rdx, rax; h
0x180017631  xor     ebx, ebx
0x180017633  call    cs:__imp_SetThreadpoolWait
0x180017639  lea     rcx, ?g_ReleaseRedirectionContextListCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180017640  call    cs:__imp_InitializeCriticalSection
0x180017646  mov     cs:?g_fReleaseRedirectionContextRegistered@@3HA, 1; int g_fReleaseRedirectionContextRegistered
0x180017650  mov     edx, 1
0x180017655  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001765a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017661  cmp     rcx, rdi
0x180017664  jz      short loc_18001768B
0x180017666  test    byte ptr [rcx+1Ch], 2
0x18001766a  jz      short loc_18001768B
0x18001766c  cmp     byte ptr [rcx+19h], 5
0x180017670  jb      short loc_18001768B
0x180017672  mov     rcx, [rcx+10h]
0x180017676  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x18001767d  mov     edx, 17h
0x180017682  mov     [rsp+38h+var_18], ebx
0x180017686  call    WPP_SF_sd
0x18001768b  mov     eax, ebx
0x18001768d  mov     rbx, [rsp+38h+arg_0]
0x180017692  add     rsp, 30h
0x180017696  pop     rdi
0x180017697  retn
```
