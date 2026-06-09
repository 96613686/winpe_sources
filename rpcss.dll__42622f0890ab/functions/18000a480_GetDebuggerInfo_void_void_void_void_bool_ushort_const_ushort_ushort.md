# GetDebuggerInfo(void *,void *,void *,void *,bool,ushort const *,ushort * *,ushort * *)

- ea: `0x18000a480`
- end: `0x18000a761`
- name: `?GetDebuggerInfo@@YAJPEAX000_NPEBGPEAPEAG3@Z`
- size: `737`
- prototype: `int __fastcall(HANDLE hToken, void *, void *, void *, bool, unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004cd64`
- `0x1800507c0`

## callees

- `0x18000a480`
- `0x18000a768`
- `0x18000a898`
- `0x18001ec28`
- `0x18002ba28`
- `0x18008cd90`
- `0x18008e98c`
- `0x1800b27e0`
- `0x1800b3128`

## import_xrefs

- `ntdll!RtlQueryPackageIdentity` at `0x18000a50b`
- `ntdll!RtlQueryPackageIdentity` at `0x18000a50b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000a5ce`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000a64e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000a68d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000a6a1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000a6e2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000a5ce`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000a64e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000a68d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000a6a1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000a6e2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a72b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a736`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a72b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a736`

## string_xrefs

- `0x18000a55b`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000a621`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000a6ba`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000a701`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000a748`: `onecore\com\combase\rpcss\olescm\launch.cxx`

## pseudocode

```c
int __fastcall GetDebuggerInfo(
        HANDLE hToken,
        void *a2,
        void *a3,
        void *a4,
        bool a5,
        unsigned __int16 *a6,
        unsigned __int16 **a7,
        unsigned __int16 **a8)
{
  char v8; // di
  int v11; // eax
  unsigned int v12; // r8d
  unsigned __int64 v13; // rcx
  int ExeComponent; // ebx
  __int64 v15; // rdx
  int DebuggerInfoForUser; // eax
  const char *v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rcx
  const char *v21; // r9
  int *v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+20h] [rbp-E0h]
  int v24[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  PSID Sid; // [rsp+48h] [rbp-B8h]
  PSID v27; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v28[72]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v29[128]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v30[264]; // [rsp+1F0h] [rbp+F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+448h] [rbp+348h]

  v8 = 0;
  v27 = a4;
  Sid = a2;
  if ( !a6 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(hToken);
    v15 = 203;
    ExeComponent = -2147024809;
    goto LABEL_7;
  }
  v22 = v24;
  v25 = 256;
  *(_QWORD *)v24 = 132;
  v11 = RtlQueryPackageIdentity(hToken, v29, &v25, v28);
  if ( v11 < 0 )
  {
    if ( v11 == -1073741275 )
      return 0;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x105,
             (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
             (const char *)(unsigned int)v11,
             (int)v24);
  }
  else
  {
    memset_0(v30, 0, 0x208u);
    v13 = -1;
    do
      ++v13;
    while ( a6[v13] );
    ExeComponent = FindExeComponent(v13, a6, v12, v30);
    if ( ExeComponent < 0 )
    {
      v15 = 212;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)(unsigned int)ExeComponent,
        (int)v22);
      return ExeComponent;
    }
    if ( a5 )
      goto LABEL_10;
    if ( ImpersonateLoggedOnUser(hToken) )
    {
      v8 = 1;
LABEL_10:
      DebuggerInfoForUser = GetDebuggerInfoForUser(Sid, v29, v28, v30, a7, a8);
      if ( DebuggerInfoForUser == -2147024894 && a3 )
      {
        if ( !ImpersonateLoggedOnUser(a3) )
        {
          ExeComponent = wil::details::in1diag3::Return_GetLastError(
                           retaddr,
                           (void *)0xF9,
                           (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                           v18);
          if ( !v8 )
            return ExeComponent;
          if ( a5 )
          {
            if ( ImpersonateLoggedOnUser(hToken) )
              return ExeComponent;
            goto LABEL_20;
          }
LABEL_35:
          RevertToSelf();
          return ExeComponent;
        }
        v8 = 1;
        DebuggerInfoForUser = GetDebuggerInfoForUser(v27, v29, v28, v30, a7, a8);
      }
      ExeComponent = 0;
      if ( DebuggerInfoForUser != -2147024894 )
        ExeComponent = DebuggerInfoForUser;
      if ( ExeComponent < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x101,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
          (const char *)(unsigned int)ExeComponent,
          v23);
        if ( !v8 )
          return ExeComponent;
        if ( a5 )
        {
          if ( ImpersonateLoggedOnUser(hToken) )
            return ExeComponent;
LABEL_20:
          MicrosoftTelemetryAssertTriggeredNoArgs(v19);
          return ExeComponent;
        }
        goto LABEL_35;
      }
      if ( v8 )
      {
        if ( a5 )
        {
          if ( !ImpersonateLoggedOnUser(hToken) )
            MicrosoftTelemetryAssertTriggeredNoArgs(v20);
        }
        else
        {
          RevertToSelf();
        }
      }
      return 0;
    }
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xED,
             (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
             v21);
  }
}

```

## disassembly

```asm
0x18000a480  push    rbp
0x18000a482  push    rbx
0x18000a483  push    rdi
0x18000a484  push    r12
0x18000a486  push    r13
0x18000a488  push    r14
0x18000a48a  push    r15
0x18000a48c  lea     rbp, [rsp-310h]
0x18000a494  sub     rsp, 410h
0x18000a49b  mov     rax, cs:__security_cookie
0x18000a4a2  xor     rax, rsp
0x18000a4a5  mov     [rbp+340h+var_40], rax
0x18000a4ac  mov     rbx, [rbp+340h+arg_28]
0x18000a4b3  xor     edi, edi
0x18000a4b5  mov     r12, [rbp+340h+arg_30]
0x18000a4bc  mov     r15, r8
0x18000a4bf  mov     r13, [rbp+340h+arg_38]
0x18000a4c6  mov     r14, rcx
0x18000a4c9  mov     [rsp+440h+var_3F0], r9
0x18000a4ce  mov     [rsp+440h+Sid], rdx
0x18000a4d3  test    rbx, rbx
0x18000a4d6  jz      loc_18000A717
0x18000a4dc  lea     rax, [rsp+440h+var_408]
0x18000a4e1  mov     [rsp+440h+var_418], rdi
0x18000a4e6  lea     r9, [rsp+440h+var_3E0]
0x18000a4eb  mov     [rsp+440h+var_420], rax; int
0x18000a4f0  lea     r8, [rsp+440h+var_400]
0x18000a4f5  mov     [rsp+440h+var_400], 100h
0x18000a4fe  lea     rdx, [rbp+340h+var_350]
0x18000a502  mov     qword ptr [rsp+440h+var_408], 84h
0x18000a50b  call    cs:__imp_RtlQueryPackageIdentity
0x18000a511  test    eax, eax
0x18000a513  js      loc_18000A666
0x18000a519  xor     edx, edx; Val
0x18000a51b  lea     rcx, [rbp+340h+var_250]; void *
0x18000a522  mov     r8d, 208h; Size
0x18000a528  call    memset_0
0x18000a52d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000a531  inc     rcx; unsigned __int64
0x18000a534  cmp     [rbx+rcx*2], di
0x18000a538  jnz     short loc_18000A531
0x18000a53a  lea     r9, [rbp+340h+var_250]; unsigned __int16 *
0x18000a541  mov     rdx, rbx; unsigned __int16 *
0x18000a544  call    ?FindExeComponent@@YAJ_KPEBGKPEAG@Z; FindExeComponent(unsigned __int64,ushort const *,ulong,ushort *)
0x18000a549  mov     ebx, eax
0x18000a54b  test    eax, eax
0x18000a54d  jns     short loc_18000A58E
0x18000a54f  mov     edx, 0D4h; void *
0x18000a554  mov     rcx, [rbp+348h]; this
0x18000a55b  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18000a562  mov     r9d, ebx; char *
0x18000a565  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a56a  mov     eax, ebx
0x18000a56c  mov     rcx, [rbp+340h+var_40]
0x18000a573  xor     rcx, rsp; StackCookie
0x18000a576  call    __security_check_cookie
0x18000a57b  add     rsp, 410h
0x18000a582  pop     r15
0x18000a584  pop     r14
0x18000a586  pop     r13
0x18000a588  pop     r12
0x18000a58a  pop     rdi
0x18000a58b  pop     rbx
0x18000a58c  pop     rbp
0x18000a58d  retn
0x18000a58e  cmp     [rbp+340h+arg_20], dil
0x18000a595  jz      loc_18000A69E
0x18000a59b  mov     rcx, [rsp+440h+Sid]; Sid
0x18000a5a0  lea     r9, [rbp+340h+var_250]; unsigned __int16 *
0x18000a5a7  mov     [rsp+440h+var_418], r13; unsigned __int16 **
0x18000a5ac  lea     r8, [rsp+440h+var_3E0]; unsigned __int16 *
0x18000a5b1  lea     rdx, [rbp+340h+var_350]; unsigned __int16 *
0x18000a5b5  mov     [rsp+440h+var_420], r12; int
0x18000a5ba  call    ?GetDebuggerInfoForUser@@YAJPEAXPEBG11PEAPEAG2@Z; GetDebuggerInfoForUser(void *,ushort const *,ushort const *,ushort const *,ushort * *,ushort * *)
0x18000a5bf  cmp     eax, 80070002h
0x18000a5c4  jnz     short loc_18000A608
0x18000a5c6  test    r15, r15
0x18000a5c9  jz      short loc_18000A608
0x18000a5cb  mov     rcx, r15; hToken
0x18000a5ce  call    cs:__imp_ImpersonateLoggedOnUser
0x18000a5d4  xor     r15d, r15d
0x18000a5d7  test    eax, eax
0x18000a5d9  jz      loc_18000A6B3
0x18000a5df  mov     rcx, [rsp+440h+var_3F0]; Sid
0x18000a5e4  lea     r9, [rbp+340h+var_250]; unsigned __int16 *
0x18000a5eb  mov     [rsp+440h+var_418], r13; unsigned __int16 **
0x18000a5f0  lea     r8, [rsp+440h+var_3E0]; unsigned __int16 *
0x18000a5f5  lea     rdx, [rbp+340h+var_350]; unsigned __int16 *
0x18000a5f9  mov     [rsp+440h+var_420], r12; unsigned __int16 **
0x18000a5fe  mov     dil, 1
0x18000a601  call    ?GetDebuggerInfoForUser@@YAJPEAXPEBG11PEAPEAG2@Z; GetDebuggerInfoForUser(void *,ushort const *,ushort const *,ushort const *,ushort * *,ushort * *)
0x18000a606  jmp     short loc_18000A60B
0x18000a608  xor     r15d, r15d
0x18000a60b  cmp     eax, 80070002h
0x18000a610  mov     ebx, r15d
0x18000a613  cmovnz  ebx, eax
0x18000a616  test    ebx, ebx
0x18000a618  jns     short loc_18000A678
0x18000a61a  mov     rcx, [rbp+348h]; this
0x18000a621  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18000a628  mov     r9d, ebx; char *
0x18000a62b  mov     edx, 101h; void *
0x18000a630  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a635  test    dil, dil
0x18000a638  jz      loc_18000A56A
0x18000a63e  cmp     [rbp+340h+arg_20], r15b
0x18000a645  jz      loc_18000A72B
0x18000a64b  mov     rcx, r14; hToken
0x18000a64e  call    cs:__imp_ImpersonateLoggedOnUser
0x18000a654  test    eax, eax
0x18000a656  jnz     loc_18000A56A
0x18000a65c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a661  jmp     loc_18000A56A
0x18000a666  cmp     eax, 0C0000225h
0x18000a66b  jnz     loc_18000A741
0x18000a671  xor     eax, eax
0x18000a673  jmp     loc_18000A56C
0x18000a678  test    dil, dil
0x18000a67b  jz      short loc_18000A671
0x18000a67d  cmp     [rbp+340h+arg_20], r15b
0x18000a684  jz      loc_18000A736
0x18000a68a  mov     rcx, r14; hToken
0x18000a68d  call    cs:__imp_ImpersonateLoggedOnUser
0x18000a693  test    eax, eax
0x18000a695  jnz     short loc_18000A671
0x18000a697  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a69c  jmp     short loc_18000A671
0x18000a69e  mov     rcx, r14; hToken
0x18000a6a1  call    cs:__imp_ImpersonateLoggedOnUser
0x18000a6a7  test    eax, eax
0x18000a6a9  jz      short loc_18000A6FA
0x18000a6ab  mov     dil, 1
0x18000a6ae  jmp     loc_18000A59B
0x18000a6b3  mov     rcx, [rbp+348h]; this
0x18000a6ba  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18000a6c1  mov     edx, 0F9h; void *
0x18000a6c6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a6cb  mov     ebx, eax
0x18000a6cd  test    dil, dil
0x18000a6d0  jz      loc_18000A56A
0x18000a6d6  cmp     [rbp+340h+arg_20], r15b
0x18000a6dd  jz      short loc_18000A72B
0x18000a6df  mov     rcx, r14; hToken
0x18000a6e2  call    cs:__imp_ImpersonateLoggedOnUser
0x18000a6e8  test    eax, eax
0x18000a6ea  jnz     loc_18000A56A
0x18000a6f0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a6f5  jmp     loc_18000A56A
0x18000a6fa  mov     rcx, [rbp+348h]; this
0x18000a701  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18000a708  mov     edx, 0EDh; void *
0x18000a70d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a712  jmp     loc_18000A56C
0x18000a717  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a71c  mov     edx, 0CBh
0x18000a721  mov     ebx, 80070057h
0x18000a726  jmp     loc_18000A554
0x18000a72b  call    cs:__imp_RevertToSelf
0x18000a731  jmp     loc_18000A56A
0x18000a736  call    cs:__imp_RevertToSelf
0x18000a73c  jmp     loc_18000A671
0x18000a741  mov     rcx, [rbp+348h]; this
0x18000a748  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18000a74f  mov     r9d, eax; char *
0x18000a752  mov     edx, 105h; void *
0x18000a757  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000a75c  jmp     loc_18000A56C
```
