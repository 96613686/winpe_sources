# rimObsCheckForRegistrationConflicts

- ea: `0x140208ccc`
- end: `0x140208fc7`
- name: `rimObsCheckForRegistrationConflicts`
- size: `763`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14020925c`
- `0x14020b58c`

## callees

- `0x140066bf0`
- `0x1400718f0`
- `0x1400764e4`
- `0x14009e3c0`
- `0x1401aa4fc`
- `0x140208ccc`
- `0x140208fd0`
- `0x1402090fc`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140208e0f`
- `ntoskrnl!PsGetProcessId` at `0x140208e0f`
- `ntoskrnl!PsGetThreadId` at `0x140208e22`
- `ntoskrnl!PsGetThreadId` at `0x140208e22`
- `WIN32K!W32GetUserSessionState` at `0x140208d19`
- `WIN32K!W32GetUserSessionState` at `0x140208d3b`
- `WIN32K!W32GetUserSessionState` at `0x140208d4e`
- `WIN32K!W32GetUserSessionState` at `0x140208e31`
- `WIN32K!W32GetUserSessionState` at `0x140208eba`
- `WIN32K!W32GetUserSessionState` at `0x140208f5e`
- `WIN32K!W32GetUserSessionState` at `0x140208d19`
- `WIN32K!W32GetUserSessionState` at `0x140208d3b`
- `WIN32K!W32GetUserSessionState` at `0x140208d4e`
- `WIN32K!W32GetUserSessionState` at `0x140208e31`
- `WIN32K!W32GetUserSessionState` at `0x140208eba`
- `WIN32K!W32GetUserSessionState` at `0x140208f5e`

## pseudocode

```c
char __fastcall rimObsCheckForRegistrationConflicts(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned int v5; // r15d
  unsigned int v6; // esi
  char v7; // bp
  __int64 v8; // rbx
  int v9; // ebp
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  _QWORD *i; // rdi
  __int64 v16; // r8
  _QWORD *v17; // r13
  const char *v18; // rax
  char v19; // bp
  bool v20; // r12
  char ProcessId; // si
  char ThreadId; // di
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 UserSessionState; // rax
  int v27; // edx
  int v28; // r8d
  bool v29; // di
  __int64 v30; // rax
  int v31; // r8d
  int v32; // edx
  __int64 v33; // r9
  const char *v34; // rax
  char v35; // bp
  bool v36; // di
  bool v37; // si
  __int64 v38; // rax
  int v39; // r8d
  int v40; // edx
  int v42; // [rsp+20h] [rbp-88h]
  int v43; // [rsp+28h] [rbp-80h]
  int v44; // [rsp+30h] [rbp-78h]
  int v45; // [rsp+38h] [rbp-70h]
  __int64 v46; // [rsp+60h] [rbp-48h]
  int v47; // [rsp+B0h] [rbp+8h]
  bool v48; // [rsp+B8h] [rbp+10h]

  v5 = a3;
  v6 = a2;
  v7 = a1;
  if ( (unsigned int)a2 > 2 )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 687);
  v8 = W32GetUserSessionState(a1, a2, a3) + 48;
  RIMLockExclusive(v8);
  v9 = v7 & 2;
  v47 = v9;
  for ( i = *(_QWORD **)(W32GetUserSessionState(v11, v10, v12) + 144);
        i != (_QWORD *)(W32GetUserSessionState(v14, v13, v16) + 144);
        i = (_QWORD *)*i )
  {
    v17 = i - 2;
    if ( v9 )
    {
      if ( (unsigned int)rimObsIsObserverTarget_0(i - 2, v6, v5, a4) )
      {
        v18 = "existing observer exists";
        goto LABEL_12;
      }
    }
    else if ( (v17[14] & 2) != 0 && (unsigned int)rimObsIsObserverTarget_0(i - 2, v6, v5, a4) )
    {
      v18 = "existing exclusive observer exists";
LABEL_12:
      v46 = (__int64)v18;
      v19 = 1;
      v20 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u;
      v48 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v20 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        ProcessId = (unsigned __int8)PsGetProcessId((PEPROCESS)v17[4]);
        ThreadId = (unsigned __int8)PsGetThreadId((PETHREAD)v17[5]);
        UserSessionState = W32GetUserSessionState(v24, v23, v25);
        LOBYTE(v27) = v20;
        LOBYTE(v28) = v48;
        WPP_RECORDER_AND_TRACE_SF_qdd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v27,
          v28,
          *(_QWORD *)(UserSessionState + 69136),
          3,
          1,
          36,
          (__int64)WPP_c696d146d7263bd817038d8ba47edda4_Traceguids,
          (char)v17,
          ThreadId,
          ProcessId);
      }
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
      {
        v19 = 0;
      }
      v29 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v19 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v30 = W32GetUserSessionState(WPP_GLOBAL_Control, v13, v16);
        LOBYTE(v31) = v29;
        LOBYTE(v32) = v19;
        v33 = *(_QWORD *)(v30 + 69136);
        v34 = "exclusive";
        if ( !v47 )
          v34 = "shared";
        WPP_RECORDER_AND_TRACE_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v32,
          v31,
          v33,
          v42,
          v43,
          v44,
          v45,
          (__int64)v34,
          v46);
      }
      v35 = 0;
      goto LABEL_38;
    }
  }
  v35 = 1;
  v36 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v37 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v36 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v38 = W32GetUserSessionState(WPP_GLOBAL_Control, v13, v16);
    LOBYTE(v39) = v37;
    LOBYTE(v40) = v36;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v40,
      v39,
      *(_QWORD *)(v38 + 69136),
      4,
      1,
      38,
      (__int64)WPP_c696d146d7263bd817038d8ba47edda4_Traceguids);
  }
LABEL_38:
  RIMUnlockExclusive(v8);
  return v35;
}

```

## disassembly

```asm
0x140208ccc  mov     [rsp+arg_10], rbx
0x140208cd1  push    rbp
0x140208cd2  push    rsi
0x140208cd3  push    rdi
0x140208cd4  push    r12
0x140208cd6  push    r13
0x140208cd8  push    r14
0x140208cda  push    r15
0x140208cdc  sub     rsp, 70h
0x140208ce0  mov     r12d, 2
0x140208ce6  mov     r14d, r9d
0x140208ce9  mov     r15d, r8d
0x140208cec  mov     esi, edx
0x140208cee  mov     ebp, ecx
0x140208cf0  cmp     edx, r12d
0x140208cf3  jbe     short loc_140208D19
0x140208cf5  mov     [rsp+0A8h+arg_0], 20000h
0x140208d00  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140208d07  mov     edx, [rsp+0A8h+arg_0]
0x140208d0e  mov     r8d, 2AFh
0x140208d14  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140208d19  call    cs:__imp_W32GetUserSessionState
0x140208d20  nop     dword ptr [rax+rax+00h]
0x140208d25  lea     rbx, [rax+30h]
0x140208d29  mov     rcx, rbx
0x140208d2c  call    RIMLockExclusive
0x140208d31  and     ebp, r12d
0x140208d34  mov     [rsp+0A8h+arg_0], ebp
0x140208d3b  call    cs:__imp_W32GetUserSessionState
0x140208d42  nop     dword ptr [rax+rax+00h]
0x140208d47  mov     rdi, [rax+90h]
0x140208d4e  call    cs:__imp_W32GetUserSessionState
0x140208d55  nop     dword ptr [rax+rax+00h]
0x140208d5a  add     rax, 90h
0x140208d60  cmp     rdi, rax
0x140208d63  jz      loc_140208F14
0x140208d69  lea     r13, [rdi-10h]
0x140208d6d  test    ebp, ebp
0x140208d6f  jz      short loc_140208D8E
0x140208d71  mov     r9d, r14d
0x140208d74  mov     r8d, r15d
0x140208d77  mov     edx, esi
0x140208d79  mov     rcx, r13
0x140208d7c  call    rimObsIsObserverTarget_0
0x140208d81  test    eax, eax
0x140208d83  jz      short loc_140208DAB
0x140208d85  lea     rax, aExistingObserv; "existing observer exists"
0x140208d8c  jmp     short loc_140208DB7
0x140208d8e  mov     eax, [r13+70h]
0x140208d92  test    r12b, al
0x140208d95  jz      short loc_140208DAB
0x140208d97  mov     r9d, r14d
0x140208d9a  mov     r8d, r15d
0x140208d9d  mov     edx, esi
0x140208d9f  mov     rcx, r13
0x140208da2  call    rimObsIsObserverTarget_0
0x140208da7  test    eax, eax
0x140208da9  jnz     short loc_140208DB0
0x140208dab  mov     rdi, [rdi]
0x140208dae  jmp     short loc_140208D4E
0x140208db0  lea     rax, aExistingExclus; "existing exclusive observer exists"
0x140208db7  mov     [rsp+0A8h+var_48], rax
0x140208dbc  mov     rcx, cs:WPP_GLOBAL_Control
0x140208dc3  lea     r14, WPP_GLOBAL_Control
0x140208dca  mov     ebp, 1
0x140208dcf  cmp     rcx, r14
0x140208dd2  jz      short loc_140208DE7
0x140208dd4  mov     eax, [rcx+2Ch]
0x140208dd7  test    bpl, al
0x140208dda  jz      short loc_140208DE7
0x140208ddc  cmp     byte ptr [rcx+29h], 3
0x140208de0  jb      short loc_140208DE7
0x140208de2  mov     r12b, bpl
0x140208de5  jmp     short loc_140208DEA
0x140208de7  xor     r12b, r12b
0x140208dea  lea     r15, WPP_RECORDER_INITIALIZED
0x140208df1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140208df8  setnz   al
0x140208dfb  mov     [rsp+0A8h+arg_8], al
0x140208e02  test    r12b, r12b
0x140208e05  jnz     short loc_140208E0B
0x140208e07  test    al, al
0x140208e09  jz      short loc_140208E88
0x140208e0b  mov     rcx, [r13+20h]; Process
0x140208e0f  call    cs:__imp_PsGetProcessId
0x140208e16  nop     dword ptr [rax+rax+00h]
0x140208e1b  mov     rcx, [r13+28h]; Thread
0x140208e1f  mov     rsi, rax
0x140208e22  call    cs:__imp_PsGetThreadId
0x140208e29  nop     dword ptr [rax+rax+00h]
0x140208e2e  mov     rdi, rax
0x140208e31  call    cs:__imp_W32GetUserSessionState
0x140208e38  nop     dword ptr [rax+rax+00h]
0x140208e3d  mov     rcx, cs:WPP_GLOBAL_Control
0x140208e44  mov     dl, r12b
0x140208e47  mov     r8b, [rsp+0A8h+arg_8]
0x140208e4f  mov     [rsp+0A8h+var_58], esi
0x140208e53  mov     r9, [rax+10E10h]
0x140208e5a  lea     rax, WPP_c696d146d7263bd817038d8ba47edda4_Traceguids
0x140208e61  mov     rcx, [rcx+18h]
0x140208e65  mov     dword ptr [rsp+0A8h+var_60], edi
0x140208e69  mov     [rsp+0A8h+var_68], r13
0x140208e6e  mov     [rsp+0A8h+var_70], rax
0x140208e73  mov     [rsp+0A8h+var_78], 24h ; '$'
0x140208e7a  mov     [rsp+0A8h+var_80], ebp
0x140208e7e  mov     [rsp+0A8h+var_88], 3
0x140208e83  call    WPP_RECORDER_AND_TRACE_SF_qdd
0x140208e88  mov     rcx, cs:WPP_GLOBAL_Control
0x140208e8f  cmp     rcx, r14
0x140208e92  jz      short loc_140208EA2
0x140208e94  mov     eax, [rcx+2Ch]
0x140208e97  test    bpl, al
0x140208e9a  jz      short loc_140208EA2
0x140208e9c  cmp     byte ptr [rcx+29h], 3
0x140208ea0  jnb     short loc_140208EA5
0x140208ea2  xor     bpl, bpl
0x140208ea5  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140208eac  setnz   dil
0x140208eb0  test    bpl, bpl
0x140208eb3  jnz     short loc_140208EBA
0x140208eb5  test    dil, dil
0x140208eb8  jz      short loc_140208F0C
0x140208eba  call    cs:__imp_W32GetUserSessionState
0x140208ec1  nop     dword ptr [rax+rax+00h]
0x140208ec6  cmp     [rsp+0A8h+arg_0], 0
0x140208ece  lea     rcx, aShared; "shared"
0x140208ed5  mov     r8b, dil
0x140208ed8  mov     dl, bpl
0x140208edb  mov     r9, [rax+10E10h]
0x140208ee2  lea     rax, aExclusive; "exclusive"
0x140208ee9  cmovz   rax, rcx
0x140208eed  mov     rcx, [rsp+0A8h+var_48]
0x140208ef2  mov     [rsp+0A8h+var_60], rcx
0x140208ef7  mov     rcx, cs:WPP_GLOBAL_Control
0x140208efe  mov     [rsp+0A8h+var_68], rax
0x140208f03  mov     rcx, [rcx+18h]
0x140208f07  call    WPP_RECORDER_AND_TRACE_SF_ss
0x140208f0c  xor     bpl, bpl
0x140208f0f  jmp     loc_140208FA3
0x140208f14  mov     rcx, cs:WPP_GLOBAL_Control
0x140208f1b  lea     r14, WPP_GLOBAL_Control
0x140208f22  mov     ebp, 1
0x140208f27  cmp     rcx, r14
0x140208f2a  jz      short loc_140208F3F
0x140208f2c  mov     eax, [rcx+2Ch]
0x140208f2f  test    bpl, al
0x140208f32  jz      short loc_140208F3F
0x140208f34  cmp     byte ptr [rcx+29h], 4
0x140208f38  jb      short loc_140208F3F
0x140208f3a  mov     dil, bpl
0x140208f3d  jmp     short loc_140208F42
0x140208f3f  xor     dil, dil
0x140208f42  lea     r15, WPP_RECORDER_INITIALIZED
0x140208f49  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140208f50  setnz   sil
0x140208f54  test    dil, dil
0x140208f57  jnz     short loc_140208F5E
0x140208f59  test    sil, sil
0x140208f5c  jz      short loc_140208FA3
0x140208f5e  call    cs:__imp_W32GetUserSessionState
0x140208f65  nop     dword ptr [rax+rax+00h]
0x140208f6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140208f71  mov     r8b, sil
0x140208f74  mov     dl, dil
0x140208f77  mov     r9, [rax+10E10h]
0x140208f7e  lea     rax, WPP_c696d146d7263bd817038d8ba47edda4_Traceguids
0x140208f85  mov     rcx, [rcx+18h]
0x140208f89  mov     [rsp+0A8h+var_70], rax
0x140208f8e  mov     [rsp+0A8h+var_78], 26h ; '&'
0x140208f95  mov     [rsp+0A8h+var_80], ebp
0x140208f99  mov     [rsp+0A8h+var_88], 4
0x140208f9e  call    WPP_RECORDER_AND_TRACE_SF_
0x140208fa3  mov     rcx, rbx
0x140208fa6  call    RIMUnlockExclusive
0x140208fab  mov     rbx, [rsp+0A8h+arg_10]
0x140208fb3  mov     al, bpl
0x140208fb6  add     rsp, 70h
0x140208fba  pop     r15
0x140208fbc  pop     r14
0x140208fbe  pop     r13
0x140208fc0  pop     r12
0x140208fc2  pop     rdi
0x140208fc3  pop     rsi
0x140208fc4  pop     rbp
0x140208fc5  retn
```
