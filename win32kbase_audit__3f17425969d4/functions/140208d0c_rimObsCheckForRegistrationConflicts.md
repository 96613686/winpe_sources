# rimObsCheckForRegistrationConflicts

- ea: `0x140208d0c`
- end: `0x140209007`
- name: `rimObsCheckForRegistrationConflicts`
- size: `763`
- prototype: `char __fastcall(__int64, __int64, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14020929c`
- `0x14020b5cc`

## callees

- `0x140049ec0`
- `0x14004eab4`
- `0x140062ff0`
- `0x1400682c0`
- `0x1401aab9c`
- `0x140208d0c`
- `0x140209010`
- `0x14020913c`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140208e4f`
- `ntoskrnl!PsGetProcessId` at `0x140208e4f`
- `ntoskrnl!PsGetThreadId` at `0x140208e62`
- `ntoskrnl!PsGetThreadId` at `0x140208e62`
- `WIN32K!W32GetUserSessionState` at `0x140208d59`
- `WIN32K!W32GetUserSessionState` at `0x140208d7b`
- `WIN32K!W32GetUserSessionState` at `0x140208d8e`
- `WIN32K!W32GetUserSessionState` at `0x140208e71`
- `WIN32K!W32GetUserSessionState` at `0x140208efa`
- `WIN32K!W32GetUserSessionState` at `0x140208f9e`
- `WIN32K!W32GetUserSessionState` at `0x140208d59`
- `WIN32K!W32GetUserSessionState` at `0x140208d7b`
- `WIN32K!W32GetUserSessionState` at `0x140208d8e`
- `WIN32K!W32GetUserSessionState` at `0x140208e71`
- `WIN32K!W32GetUserSessionState` at `0x140208efa`
- `WIN32K!W32GetUserSessionState` at `0x140208f9e`

## pseudocode

```c
char __fastcall rimObsCheckForRegistrationConflicts(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  unsigned int v6; // esi
  char v7; // bp
  __int64 v8; // rbx
  int v9; // ebp
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  _QWORD *i; // rdi
  _QWORD *v15; // r13
  const char *v16; // rax
  char v17; // bp
  char v18; // r12
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 UserSessionState; // rax
  bool v22; // di
  __int64 v23; // rax
  int v24; // r8d
  int v25; // edx
  __int64 v26; // r9
  const char *v27; // rax
  char v28; // bp
  char v29; // di
  char v30; // si
  __int64 v31; // rax
  int v33; // [rsp+20h] [rbp-88h]
  int v34; // [rsp+28h] [rbp-80h]
  int v35; // [rsp+30h] [rbp-78h]
  int v36; // [rsp+38h] [rbp-70h]
  __int64 v37; // [rsp+60h] [rbp-48h]
  int v38; // [rsp+B0h] [rbp+8h]
  char v39; // [rsp+B8h] [rbp+10h]

  v6 = a2;
  v7 = a1;
  if ( (unsigned int)a2 > 2 )
    MicrosoftTelemetryAssertTriggeredArgsKM((__int64)"IXPTelAssert", 0x20000, 687);
  v8 = W32GetUserSessionState(a1, a2) + 48;
  RIMLockExclusive(v8);
  v9 = v7 & 2;
  v38 = v9;
  for ( i = *(_QWORD **)(W32GetUserSessionState(v11, v10) + 144);
        i != (_QWORD *)(W32GetUserSessionState(v13, v12) + 144);
        i = (_QWORD *)*i )
  {
    v15 = i - 2;
    if ( v9 )
    {
      if ( (unsigned int)rimObsIsObserverTarget_0(i - 2, v6, a3, a4) )
      {
        v16 = "existing observer exists";
        goto LABEL_12;
      }
    }
    else if ( (v15[14] & 2) != 0 && (unsigned int)rimObsIsObserverTarget_0(i - 2, v6, a3, a4) )
    {
      v16 = "existing exclusive observer exists";
LABEL_12:
      v37 = (__int64)v16;
      v17 = 1;
      v18 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u;
      v39 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v18 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        PsGetProcessId((PEPROCESS)v15[4]);
        PsGetThreadId((PETHREAD)v15[5]);
        UserSessionState = W32GetUserSessionState(v20, v19);
        WPP_RECORDER_AND_TRACE_SF_qdd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v18,
          v39,
          *(_QWORD *)(UserSessionState + 69136),
          3u,
          1u,
          0x24u,
          (__int64)WPP_c696d146d7263bd817038d8ba47edda4_Traceguids);
      }
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
      {
        v17 = 0;
      }
      v22 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v17 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v23 = W32GetUserSessionState(WPP_GLOBAL_Control, v12);
        LOBYTE(v24) = v22;
        LOBYTE(v25) = v17;
        v26 = *(_QWORD *)(v23 + 69136);
        v27 = "exclusive";
        if ( !v38 )
          v27 = "shared";
        WPP_RECORDER_AND_TRACE_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v25,
          v24,
          v26,
          v33,
          v34,
          v35,
          v36,
          (__int64)v27,
          v37);
      }
      v28 = 0;
      goto LABEL_38;
    }
  }
  v28 = 1;
  v29 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v30 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v29 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v31 = W32GetUserSessionState(WPP_GLOBAL_Control, v12);
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v29,
      v30,
      *(_QWORD *)(v31 + 69136),
      4u,
      1u,
      0x26u,
      (__int64)WPP_c696d146d7263bd817038d8ba47edda4_Traceguids);
  }
LABEL_38:
  RIMUnlockExclusive(v8);
  return v28;
}

```

## disassembly

```asm
0x140208d0c  mov     [rsp+arg_10], rbx
0x140208d11  push    rbp
0x140208d12  push    rsi
0x140208d13  push    rdi
0x140208d14  push    r12
0x140208d16  push    r13
0x140208d18  push    r14
0x140208d1a  push    r15
0x140208d1c  sub     rsp, 70h
0x140208d20  mov     r12d, 2
0x140208d26  mov     r14d, r9d
0x140208d29  mov     r15d, r8d
0x140208d2c  mov     esi, edx
0x140208d2e  mov     ebp, ecx
0x140208d30  cmp     edx, r12d
0x140208d33  jbe     short loc_140208D59
0x140208d35  mov     [rsp+0A8h+arg_0], 20000h
0x140208d40  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140208d47  mov     edx, [rsp+0A8h+arg_0]
0x140208d4e  mov     r8d, 2AFh
0x140208d54  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140208d59  call    cs:__imp_W32GetUserSessionState
0x140208d60  nop     dword ptr [rax+rax+00h]
0x140208d65  lea     rbx, [rax+30h]
0x140208d69  mov     rcx, rbx
0x140208d6c  call    RIMLockExclusive
0x140208d71  and     ebp, r12d
0x140208d74  mov     [rsp+0A8h+arg_0], ebp
0x140208d7b  call    cs:__imp_W32GetUserSessionState
0x140208d82  nop     dword ptr [rax+rax+00h]
0x140208d87  mov     rdi, [rax+90h]
0x140208d8e  call    cs:__imp_W32GetUserSessionState
0x140208d95  nop     dword ptr [rax+rax+00h]
0x140208d9a  add     rax, 90h
0x140208da0  cmp     rdi, rax
0x140208da3  jz      loc_140208F54
0x140208da9  lea     r13, [rdi-10h]
0x140208dad  test    ebp, ebp
0x140208daf  jz      short loc_140208DCE
0x140208db1  mov     r9d, r14d
0x140208db4  mov     r8d, r15d
0x140208db7  mov     edx, esi
0x140208db9  mov     rcx, r13
0x140208dbc  call    rimObsIsObserverTarget_0
0x140208dc1  test    eax, eax
0x140208dc3  jz      short loc_140208DEB
0x140208dc5  lea     rax, aExistingObserv; "existing observer exists"
0x140208dcc  jmp     short loc_140208DF7
0x140208dce  mov     eax, [r13+70h]
0x140208dd2  test    r12b, al
0x140208dd5  jz      short loc_140208DEB
0x140208dd7  mov     r9d, r14d
0x140208dda  mov     r8d, r15d
0x140208ddd  mov     edx, esi
0x140208ddf  mov     rcx, r13
0x140208de2  call    rimObsIsObserverTarget_0
0x140208de7  test    eax, eax
0x140208de9  jnz     short loc_140208DF0
0x140208deb  mov     rdi, [rdi]
0x140208dee  jmp     short loc_140208D8E
0x140208df0  lea     rax, aExistingExclus; "existing exclusive observer exists"
0x140208df7  mov     [rsp+0A8h+var_48], rax
0x140208dfc  mov     rcx, cs:WPP_GLOBAL_Control
0x140208e03  lea     r14, WPP_GLOBAL_Control
0x140208e0a  mov     ebp, 1
0x140208e0f  cmp     rcx, r14
0x140208e12  jz      short loc_140208E27
0x140208e14  mov     eax, [rcx+2Ch]
0x140208e17  test    bpl, al
0x140208e1a  jz      short loc_140208E27
0x140208e1c  cmp     byte ptr [rcx+29h], 3
0x140208e20  jb      short loc_140208E27
0x140208e22  mov     r12b, bpl
0x140208e25  jmp     short loc_140208E2A
0x140208e27  xor     r12b, r12b
0x140208e2a  lea     r15, WPP_RECORDER_INITIALIZED
0x140208e31  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140208e38  setnz   al
0x140208e3b  mov     [rsp+0A8h+arg_8], al
0x140208e42  test    r12b, r12b
0x140208e45  jnz     short loc_140208E4B
0x140208e47  test    al, al
0x140208e49  jz      short loc_140208EC8
0x140208e4b  mov     rcx, [r13+20h]; Process
0x140208e4f  call    cs:__imp_PsGetProcessId
0x140208e56  nop     dword ptr [rax+rax+00h]
0x140208e5b  mov     rcx, [r13+28h]; Thread
0x140208e5f  mov     rsi, rax
0x140208e62  call    cs:__imp_PsGetThreadId
0x140208e69  nop     dword ptr [rax+rax+00h]
0x140208e6e  mov     rdi, rax
0x140208e71  call    cs:__imp_W32GetUserSessionState
0x140208e78  nop     dword ptr [rax+rax+00h]
0x140208e7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140208e84  mov     dl, r12b
0x140208e87  mov     r8b, [rsp+0A8h+arg_8]
0x140208e8f  mov     [rsp+0A8h+var_58], esi
0x140208e93  mov     r9, [rax+10E10h]
0x140208e9a  lea     rax, WPP_c696d146d7263bd817038d8ba47edda4_Traceguids
0x140208ea1  mov     rcx, [rcx+18h]
0x140208ea5  mov     dword ptr [rsp+0A8h+var_60], edi
0x140208ea9  mov     [rsp+0A8h+var_68], r13
0x140208eae  mov     [rsp+0A8h+var_70], rax
0x140208eb3  mov     [rsp+0A8h+var_78], 24h ; '$'
0x140208eba  mov     [rsp+0A8h+var_80], ebp
0x140208ebe  mov     [rsp+0A8h+var_88], 3
0x140208ec3  call    WPP_RECORDER_AND_TRACE_SF_qdd
0x140208ec8  mov     rcx, cs:WPP_GLOBAL_Control
0x140208ecf  cmp     rcx, r14
0x140208ed2  jz      short loc_140208EE2
0x140208ed4  mov     eax, [rcx+2Ch]
0x140208ed7  test    bpl, al
0x140208eda  jz      short loc_140208EE2
0x140208edc  cmp     byte ptr [rcx+29h], 3
0x140208ee0  jnb     short loc_140208EE5
0x140208ee2  xor     bpl, bpl
0x140208ee5  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140208eec  setnz   dil
0x140208ef0  test    bpl, bpl
0x140208ef3  jnz     short loc_140208EFA
0x140208ef5  test    dil, dil
0x140208ef8  jz      short loc_140208F4C
0x140208efa  call    cs:__imp_W32GetUserSessionState
0x140208f01  nop     dword ptr [rax+rax+00h]
0x140208f06  cmp     [rsp+0A8h+arg_0], 0
0x140208f0e  lea     rcx, aShared; "shared"
0x140208f15  mov     r8b, dil
0x140208f18  mov     dl, bpl
0x140208f1b  mov     r9, [rax+10E10h]
0x140208f22  lea     rax, aExclusive; "exclusive"
0x140208f29  cmovz   rax, rcx
0x140208f2d  mov     rcx, [rsp+0A8h+var_48]
0x140208f32  mov     [rsp+0A8h+var_60], rcx
0x140208f37  mov     rcx, cs:WPP_GLOBAL_Control
0x140208f3e  mov     [rsp+0A8h+var_68], rax
0x140208f43  mov     rcx, [rcx+18h]
0x140208f47  call    WPP_RECORDER_AND_TRACE_SF_ss
0x140208f4c  xor     bpl, bpl
0x140208f4f  jmp     loc_140208FE3
0x140208f54  mov     rcx, cs:WPP_GLOBAL_Control
0x140208f5b  lea     r14, WPP_GLOBAL_Control
0x140208f62  mov     ebp, 1
0x140208f67  cmp     rcx, r14
0x140208f6a  jz      short loc_140208F7F
0x140208f6c  mov     eax, [rcx+2Ch]
0x140208f6f  test    bpl, al
0x140208f72  jz      short loc_140208F7F
0x140208f74  cmp     byte ptr [rcx+29h], 4
0x140208f78  jb      short loc_140208F7F
0x140208f7a  mov     dil, bpl
0x140208f7d  jmp     short loc_140208F82
0x140208f7f  xor     dil, dil
0x140208f82  lea     r15, WPP_RECORDER_INITIALIZED
0x140208f89  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140208f90  setnz   sil
0x140208f94  test    dil, dil
0x140208f97  jnz     short loc_140208F9E
0x140208f99  test    sil, sil
0x140208f9c  jz      short loc_140208FE3
0x140208f9e  call    cs:__imp_W32GetUserSessionState
0x140208fa5  nop     dword ptr [rax+rax+00h]
0x140208faa  mov     rcx, cs:WPP_GLOBAL_Control
0x140208fb1  mov     r8b, sil
0x140208fb4  mov     dl, dil
0x140208fb7  mov     r9, [rax+10E10h]
0x140208fbe  lea     rax, WPP_c696d146d7263bd817038d8ba47edda4_Traceguids
0x140208fc5  mov     rcx, [rcx+18h]
0x140208fc9  mov     [rsp+0A8h+var_70], rax
0x140208fce  mov     [rsp+0A8h+var_78], 26h ; '&'
0x140208fd5  mov     [rsp+0A8h+var_80], ebp
0x140208fd9  mov     [rsp+0A8h+var_88], 4
0x140208fde  call    WPP_RECORDER_AND_TRACE_SF_
0x140208fe3  mov     rcx, rbx
0x140208fe6  call    RIMUnlockExclusive
0x140208feb  mov     rbx, [rsp+0A8h+arg_10]
0x140208ff3  mov     al, bpl
0x140208ff6  add     rsp, 70h
0x140208ffa  pop     r15
0x140208ffc  pop     r14
0x140208ffe  pop     r13
0x140209000  pop     r12
0x140209002  pop     rdi
0x140209003  pop     rsi
0x140209004  pop     rbp
0x140209005  retn
```
