# Subscription::EventsCallback(_WSMAN_EVENTS_RESULT const *,WSMAN_SENDER_DETAILS_INTERNAL const *,WSMAN_DELIVERY *,void *)

- ea: `0x18000cd50`
- end: `0x18000cef1`
- name: `?EventsCallback@Subscription@@SAXPEBU_WSMAN_EVENTS_RESULT@@PEBVWSMAN_SENDER_DETAILS_INTERNAL@@PEAUWSMAN_DELIVERY@@PEAX@Z`
- size: `417`
- prototype: `void __fastcall(const struct _WSMAN_EVENTS_RESULT *, const struct WSMAN_SENDER_DETAILS_INTERNAL *, struct WSMAN_DELIVERY *, struct SubscriptionCallbackContext *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180002510`
- `0x180007fc0`
- `0x18000cd50`
- `0x18000e2f8`
- `0x1800116c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cdae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce0b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000cd98`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000cd98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000cd7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000cd7e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000ce05`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000cdc6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000ce05`
- `WsmSvc!WSManAckEvents` at `0x18000ce68`
- `WsmSvc!WSManAckEvents` at `0x18000ce68`

## pseudocode

```c
void __fastcall Subscription::EventsCallback(
        const struct _WSMAN_EVENTS_RESULT *a1,
        const struct WSMAN_SENDER_DETAILS_INTERNAL *a2,
        struct WSMAN_DELIVERY *a3,
        struct SubscriptionCallbackContext *a4)
{
  struct WSMAN_DELIVERY *v5; // rsi
  HANDLE CurrentThread; // rax
  struct WSMAN_DELIVERY *v9; // r9
  BOOL (__stdcall *v10)(HANDLE); // rax
  void *v11; // rcx
  _QWORD *v12; // rdi
  const wchar_t *v13; // rbx
  char LastError; // al
  int v15; // r8d
  _QWORD *v16; // r9
  char v17; // al
  int v18; // r8d
  _QWORD *v19; // r9
  wmi::Exception *v20; // [rsp+40h] [rbp-68h] BYREF
  char v21[8]; // [rsp+48h] [rbp-60h] BYREF
  BOOL (__stdcall *v22)(HANDLE); // [rsp+50h] [rbp-58h]
  void *v23; // [rsp+58h] [rbp-50h]
  bool v24[8]; // [rsp+60h] [rbp-48h] BYREF
  BOOL (__stdcall *v25)(PHANDLE, HANDLE); // [rsp+68h] [rbp-40h]
  __int64 v26; // [rsp+70h] [rbp-38h]
  void *v27; // [rsp+78h] [rbp-30h]
  void *TokenHandle; // [rsp+B8h] [rbp+10h] BYREF
  struct WSMAN_DELIVERY *v29; // [rsp+C0h] [rbp+18h]
  const wchar_t *v30; // [rsp+C8h] [rbp+20h]

  v29 = a3;
  v5 = a3;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
  {
    TokenHandle = 0;
    v10 = CloseHandle;
LABEL_3:
    v11 = 0;
    v21[0] = 1;
    goto LABEL_4;
  }
  SetThreadToken(0, 0);
  v10 = CloseHandle;
  v11 = TokenHandle;
  if ( !TokenHandle )
    goto LABEL_3;
  v21[0] = 0;
LABEL_4:
  v22 = v10;
  v23 = v11;
  v24[0] = v11 == 0;
  v25 = SetThreadToken;
  v26 = 0;
  v27 = v11;
  v12 = (_QWORD *)*((_QWORD *)a4 + 1);
  if ( a2 )
    v13 = (const wchar_t *)*((_QWORD *)a2 + 5);
  else
    v13 = &word_180026AD8;
  try
  {
    v30 = v13;
    Subscription::OnEventsCallback((Subscription *)v12, a1, a2, v9, a4);
  }
  catch ( wmi::Exception *v20 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = (**(__int64 (__fastcall ***)(wmi::Exception *))v20)(v20);
      v19 = v12 + 7;
      if ( v12[10] >= 8u )
        v19 = (_QWORD *)*v19;
      WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v18, (_DWORD)v19, (__int64)v30, v17);
    }
    v5 = v29;
    v13 = v30;
  }
  v30 = v13;
  Subscription::OnEventsCallback((Subscription *)v12, a1, a2, v9, a4);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = (**(__int64 (__fastcall ***)(wmi::Exception *))v20)(v20);
    v19 = v12 + 7;
    if ( v12[10] >= 8u )
      v19 = (_QWORD *)*v19;
    WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v18, (_DWORD)v19, (__int64)v30, v17);
  }
}

```

## disassembly

```asm
0x18000cd50  mov     rax, rsp
0x18000cd53  mov     [rax+8], rbx
0x18000cd57  mov     [rax+18h], r8
0x18000cd5b  push    rsi
0x18000cd5c  push    rdi
0x18000cd5d  push    r12
0x18000cd5f  push    r14
0x18000cd61  push    r15
0x18000cd63  sub     rsp, 80h
0x18000cd6a  mov     r15, r9
0x18000cd6d  mov     rsi, r8
0x18000cd70  mov     r14, rdx
0x18000cd73  mov     r12, rcx
0x18000cd76  mov     qword ptr [rax+10h], 0
0x18000cd7e  call    cs:__imp_GetCurrentThread
0x18000cd84  mov     rcx, rax; ThreadHandle
0x18000cd87  lea     r9, [rsp+0A8h+TokenHandle]; TokenHandle
0x18000cd8f  mov     edx, 4; DesiredAccess
0x18000cd94  lea     r8d, [rdx-3]; OpenAsSelf
0x18000cd98  call    cs:__imp_OpenThreadToken
0x18000cd9e  test    eax, eax
0x18000cda0  jnz     short loc_18000CE01
0x18000cda2  mov     [rsp+0A8h+TokenHandle], 0
0x18000cdae  mov     rax, cs:__imp_CloseHandle
0x18000cdb5  xor     ecx, ecx
0x18000cdb7  mov     [rsp+0A8h+var_60], 1
0x18000cdbc  mov     [rsp+0A8h+var_58], rax
0x18000cdc1  mov     [rsp+0A8h+var_50], rcx
0x18000cdc6  mov     rax, cs:__imp_SetThreadToken
0x18000cdcd  test    rcx, rcx
0x18000cdd0  setz    [rsp+0A8h+var_48]
0x18000cdd5  mov     [rsp+0A8h+var_40], rax
0x18000cdda  mov     [rsp+0A8h+var_38], 0
0x18000cde3  mov     [rsp+0A8h+var_30], rcx
0x18000cde8  mov     rdi, [r15+8]
0x18000cdec  mov     [rsp+0A8h+var_70], rdi
0x18000cdf1  mov     [rsp+0A8h+var_78], rdi
0x18000cdf6  test    r14, r14
0x18000cdf9  jz      short loc_18000CE26
0x18000cdfb  mov     rbx, [r14+28h]
0x18000cdff  jmp     short loc_18000CE2D
0x18000ce01  xor     edx, edx; Token
0x18000ce03  xor     ecx, ecx; Thread
0x18000ce05  call    cs:__imp_SetThreadToken
0x18000ce0b  mov     rax, cs:__imp_CloseHandle
0x18000ce12  mov     rcx, [rsp+0A8h+TokenHandle]
0x18000ce1a  test    rcx, rcx
0x18000ce1d  jz      short loc_18000CDB5
0x18000ce1f  mov     [rsp+0A8h+var_60], 0
0x18000ce24  jmp     short loc_18000CDBC
0x18000ce26  lea     rbx, word_180026AD8
0x18000ce2d  mov     [rsp+0A8h+arg_18], rbx
0x18000ce35  mov     [rsp+0A8h+var_88], r15; struct SubscriptionCallbackContext *
0x18000ce3a  mov     r8, r14; struct WSMAN_SENDER_DETAILS_INTERNAL *
0x18000ce3d  mov     rdx, r12; struct _WSMAN_EVENTS_RESULT *
0x18000ce40  mov     rcx, rdi; this
0x18000ce43  call    ?OnEventsCallback@Subscription@@QEAAXPEBU_WSMAN_EVENTS_RESULT@@PEBVWSMAN_SENDER_DETAILS_INTERNAL@@PEAUWSMAN_DELIVERY@@PEAUSubscriptionCallbackContext@@@Z; Subscription::OnEventsCallback(_WSMAN_EVENTS_RESULT const *,WSMAN_SENDER_DETAILS_INTERNAL const *,WSMAN_DELIVERY *,SubscriptionCallbackContext *)
0x18000ce48  nop
0x18000ce49  jmp     short loc_18000CE60
0x18000ce4b  mov     rsi, [rsp+0A8h+arg_10]
0x18000ce53  mov     rbx, [rsp+0A8h+arg_18]
0x18000ce5b  mov     rdi, [rsp+0A8h+var_70]
0x18000ce60  test    rsi, rsi
0x18000ce63  jz      short loc_18000CEC4
0x18000ce65  mov     rcx, rsi
0x18000ce68  call    cs:__imp_WSManAckEvents
0x18000ce6e  test    eax, eax
0x18000ce70  jnz     short loc_18000CEC4
0x18000ce72  lea     rcx, WPP_GLOBAL_Control
0x18000ce79  mov     rax, cs:WPP_GLOBAL_Control
0x18000ce80  cmp     rax, rcx
0x18000ce83  jz      short loc_18000CEC4
0x18000ce85  test    byte ptr [rax+1Ch], 10h
0x18000ce89  jz      short loc_18000CEC4
0x18000ce8b  cmp     byte ptr [rax+19h], 2
0x18000ce8f  jb      short loc_18000CEC4
0x18000ce91  call    cs:__imp_GetLastError
0x18000ce97  lea     r9, [rdi+38h]
0x18000ce9b  cmp     qword ptr [r9+18h], 8
0x18000cea0  jb      short loc_18000CEA5
0x18000cea2  mov     r9, [r9]
0x18000cea5  mov     edx, 1Bh
0x18000ceaa  mov     [rsp+0A8h+var_80], eax
0x18000ceae  mov     [rsp+0A8h+var_88], rbx
0x18000ceb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ceba  mov     rcx, [rcx+10h]
0x18000cebe  call    WPP_SF_SSD
0x18000cec3  nop
0x18000cec4  lea     rcx, [rsp+0A8h+var_48]
0x18000cec9  call    ??1?$ScopeGuardImpl2@P6AHPEAPEAXPEAX@ZPEAPEAXPEAX@wmi@@QEAA@XZ; wmi::ScopeGuardImpl2<int (*)(void * *,void *),void * *,void *>::~ScopeGuardImpl2<int (*)(void * *,void *),void * *,void *>(void)
0x18000cece  nop
0x18000cecf  lea     rcx, [rsp+0A8h+var_60]
0x18000ced4  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x18000ced9  mov     rbx, [rsp+0A8h+arg_0]
0x18000cee1  add     rsp, 80h
0x18000cee8  pop     r15
0x18000ceea  pop     r14
0x18000ceec  pop     r12
0x18000ceee  pop     rdi
0x18000ceef  pop     rsi
0x18000cef0  retn
```
