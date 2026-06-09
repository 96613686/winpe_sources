# rimObsCheckForRegistrationConflicts

- ea: `0x1402084ac`
- end: `0x1402087a7`
- name: `rimObsCheckForRegistrationConflicts`
- size: `763`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140208a3c`
- `0x14020ad6c`

## callees

- `0x140065730`
- `0x140072a90`
- `0x140077684`
- `0x1400951c0`
- `0x1401a9f9c`
- `0x1402084ac`
- `0x1402087b0`
- `0x1402088dc`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x1402085ef`
- `ntoskrnl!PsGetProcessId` at `0x1402085ef`
- `ntoskrnl!PsGetThreadId` at `0x140208602`
- `ntoskrnl!PsGetThreadId` at `0x140208602`
- `WIN32K!W32GetUserSessionState` at `0x1402084f9`
- `WIN32K!W32GetUserSessionState` at `0x14020851b`
- `WIN32K!W32GetUserSessionState` at `0x14020852e`
- `WIN32K!W32GetUserSessionState` at `0x140208611`
- `WIN32K!W32GetUserSessionState` at `0x14020869a`
- `WIN32K!W32GetUserSessionState` at `0x14020873e`
- `WIN32K!W32GetUserSessionState` at `0x1402084f9`
- `WIN32K!W32GetUserSessionState` at `0x14020851b`
- `WIN32K!W32GetUserSessionState` at `0x14020852e`
- `WIN32K!W32GetUserSessionState` at `0x140208611`
- `WIN32K!W32GetUserSessionState` at `0x14020869a`
- `WIN32K!W32GetUserSessionState` at `0x14020873e`

## pseudocode

```c
char __fastcall rimObsCheckForRegistrationConflicts(__int64 a1, unsigned int a2, unsigned int a3, unsigned int a4)
{
  char v7; // bp
  __int64 v8; // rbx
  int v9; // ebp
  __int64 v10; // rcx
  __int64 v11; // rcx
  _QWORD *i; // rdi
  _QWORD *v13; // r13
  const char *v14; // rax
  char v15; // bp
  bool v16; // r12
  char ProcessId; // si
  char ThreadId; // di
  __int64 v19; // rcx
  __int64 UserSessionState; // rax
  int v21; // edx
  int v22; // r8d
  bool v23; // di
  __int64 v24; // rax
  int v25; // r8d
  int v26; // edx
  __int64 v27; // r9
  const char *v28; // rax
  char v29; // bp
  bool v30; // di
  bool v31; // si
  __int64 v32; // rax
  int v33; // r8d
  int v34; // edx
  int v36; // [rsp+20h] [rbp-88h]
  int v37; // [rsp+28h] [rbp-80h]
  int v38; // [rsp+30h] [rbp-78h]
  int v39; // [rsp+38h] [rbp-70h]
  __int64 v40; // [rsp+60h] [rbp-48h]
  int v41; // [rsp+B0h] [rbp+8h]
  bool v42; // [rsp+B8h] [rbp+10h]

  v7 = a1;
  if ( a2 > 2 )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 687);
  v8 = W32GetUserSessionState(a1) + 48;
  RIMLockExclusive(v8);
  v9 = v7 & 2;
  v41 = v9;
  for ( i = *(_QWORD **)(W32GetUserSessionState(v10) + 144);
        i != (_QWORD *)(W32GetUserSessionState(v11) + 144);
        i = (_QWORD *)*i )
  {
    v13 = i - 2;
    if ( v9 )
    {
      if ( (unsigned int)rimObsIsObserverTarget_0(i - 2, a2, a3, a4) )
      {
        v14 = "existing observer exists";
        goto LABEL_12;
      }
    }
    else if ( (v13[14] & 2) != 0 && (unsigned int)rimObsIsObserverTarget_0(i - 2, a2, a3, a4) )
    {
      v14 = "existing exclusive observer exists";
LABEL_12:
      v40 = (__int64)v14;
      v15 = 1;
      v16 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u;
      v42 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v16 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        ProcessId = (unsigned __int8)PsGetProcessId((PEPROCESS)v13[4]);
        ThreadId = (unsigned __int8)PsGetThreadId((PETHREAD)v13[5]);
        UserSessionState = W32GetUserSessionState(v19);
        LOBYTE(v21) = v16;
        LOBYTE(v22) = v42;
        WPP_RECORDER_AND_TRACE_SF_qdd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v21,
          v22,
          *(_QWORD *)(UserSessionState + 69136),
          3,
          1,
          36,
          (__int64)WPP_c696d146d7263bd817038d8ba47edda4_Traceguids,
          (char)v13,
          ThreadId,
          ProcessId);
      }
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
      {
        v15 = 0;
      }
      v23 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v24 = W32GetUserSessionState(WPP_GLOBAL_Control);
        LOBYTE(v25) = v23;
        LOBYTE(v26) = v15;
        v27 = *(_QWORD *)(v24 + 69136);
        v28 = "exclusive";
        if ( !v41 )
          v28 = "shared";
        WPP_RECORDER_AND_TRACE_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v26,
          v25,
          v27,
          v36,
          v37,
          v38,
          v39,
          (__int64)v28,
          v40);
      }
      v29 = 0;
      goto LABEL_38;
    }
  }
  v29 = 1;
  v30 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v31 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v30 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v32 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v33) = v31;
    LOBYTE(v34) = v30;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v34,
      v33,
      *(_QWORD *)(v32 + 69136),
      4,
      1,
      38,
      (__int64)WPP_c696d146d7263bd817038d8ba47edda4_Traceguids);
  }
LABEL_38:
  RIMUnlockExclusive(v8);
  return v29;
}

```

## disassembly

```asm
0x1402084ac  mov     [rsp+arg_10], rbx
0x1402084b1  push    rbp
0x1402084b2  push    rsi
0x1402084b3  push    rdi
0x1402084b4  push    r12
0x1402084b6  push    r13
0x1402084b8  push    r14
0x1402084ba  push    r15
0x1402084bc  sub     rsp, 70h
0x1402084c0  mov     r12d, 2
0x1402084c6  mov     r14d, r9d
0x1402084c9  mov     r15d, r8d
0x1402084cc  mov     esi, edx
0x1402084ce  mov     ebp, ecx
0x1402084d0  cmp     edx, r12d
0x1402084d3  jbe     short loc_1402084F9
0x1402084d5  mov     [rsp+0A8h+arg_0], 20000h
0x1402084e0  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1402084e7  mov     edx, [rsp+0A8h+arg_0]
0x1402084ee  mov     r8d, 2AFh
0x1402084f4  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1402084f9  call    cs:__imp_W32GetUserSessionState
0x140208500  nop     dword ptr [rax+rax+00h]
0x140208505  lea     rbx, [rax+30h]
0x140208509  mov     rcx, rbx
0x14020850c  call    RIMLockExclusive
0x140208511  and     ebp, r12d
0x140208514  mov     [rsp+0A8h+arg_0], ebp
0x14020851b  call    cs:__imp_W32GetUserSessionState
0x140208522  nop     dword ptr [rax+rax+00h]
0x140208527  mov     rdi, [rax+90h]
0x14020852e  call    cs:__imp_W32GetUserSessionState
0x140208535  nop     dword ptr [rax+rax+00h]
0x14020853a  add     rax, 90h
0x140208540  cmp     rdi, rax
0x140208543  jz      loc_1402086F4
0x140208549  lea     r13, [rdi-10h]
0x14020854d  test    ebp, ebp
0x14020854f  jz      short loc_14020856E
0x140208551  mov     r9d, r14d
0x140208554  mov     r8d, r15d
0x140208557  mov     edx, esi
0x140208559  mov     rcx, r13
0x14020855c  call    rimObsIsObserverTarget_0
0x140208561  test    eax, eax
0x140208563  jz      short loc_14020858B
0x140208565  lea     rax, aExistingObserv; "existing observer exists"
0x14020856c  jmp     short loc_140208597
0x14020856e  mov     eax, [r13+70h]
0x140208572  test    r12b, al
0x140208575  jz      short loc_14020858B
0x140208577  mov     r9d, r14d
0x14020857a  mov     r8d, r15d
0x14020857d  mov     edx, esi
0x14020857f  mov     rcx, r13
0x140208582  call    rimObsIsObserverTarget_0
0x140208587  test    eax, eax
0x140208589  jnz     short loc_140208590
0x14020858b  mov     rdi, [rdi]
0x14020858e  jmp     short loc_14020852E
0x140208590  lea     rax, aExistingExclus; "existing exclusive observer exists"
0x140208597  mov     [rsp+0A8h+var_48], rax
0x14020859c  mov     rcx, cs:WPP_GLOBAL_Control
0x1402085a3  lea     r14, WPP_GLOBAL_Control
0x1402085aa  mov     ebp, 1
0x1402085af  cmp     rcx, r14
0x1402085b2  jz      short loc_1402085C7
0x1402085b4  mov     eax, [rcx+2Ch]
0x1402085b7  test    bpl, al
0x1402085ba  jz      short loc_1402085C7
0x1402085bc  cmp     byte ptr [rcx+29h], 3
0x1402085c0  jb      short loc_1402085C7
0x1402085c2  mov     r12b, bpl
0x1402085c5  jmp     short loc_1402085CA
0x1402085c7  xor     r12b, r12b
0x1402085ca  lea     r15, WPP_RECORDER_INITIALIZED
0x1402085d1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1402085d8  setnz   al
0x1402085db  mov     [rsp+0A8h+arg_8], al
0x1402085e2  test    r12b, r12b
0x1402085e5  jnz     short loc_1402085EB
0x1402085e7  test    al, al
0x1402085e9  jz      short loc_140208668
0x1402085eb  mov     rcx, [r13+20h]; Process
0x1402085ef  call    cs:__imp_PsGetProcessId
0x1402085f6  nop     dword ptr [rax+rax+00h]
0x1402085fb  mov     rcx, [r13+28h]; Thread
0x1402085ff  mov     rsi, rax
0x140208602  call    cs:__imp_PsGetThreadId
0x140208609  nop     dword ptr [rax+rax+00h]
0x14020860e  mov     rdi, rax
0x140208611  call    cs:__imp_W32GetUserSessionState
0x140208618  nop     dword ptr [rax+rax+00h]
0x14020861d  mov     rcx, cs:WPP_GLOBAL_Control
0x140208624  mov     dl, r12b
0x140208627  mov     r8b, [rsp+0A8h+arg_8]
0x14020862f  mov     [rsp+0A8h+var_58], esi
0x140208633  mov     r9, [rax+10E10h]
0x14020863a  lea     rax, WPP_c696d146d7263bd817038d8ba47edda4_Traceguids
0x140208641  mov     rcx, [rcx+18h]
0x140208645  mov     dword ptr [rsp+0A8h+var_60], edi
0x140208649  mov     [rsp+0A8h+var_68], r13
0x14020864e  mov     [rsp+0A8h+var_70], rax
0x140208653  mov     [rsp+0A8h+var_78], 24h ; '$'
0x14020865a  mov     [rsp+0A8h+var_80], ebp
0x14020865e  mov     [rsp+0A8h+var_88], 3
0x140208663  call    WPP_RECORDER_AND_TRACE_SF_qdd
0x140208668  mov     rcx, cs:WPP_GLOBAL_Control
0x14020866f  cmp     rcx, r14
0x140208672  jz      short loc_140208682
0x140208674  mov     eax, [rcx+2Ch]
0x140208677  test    bpl, al
0x14020867a  jz      short loc_140208682
0x14020867c  cmp     byte ptr [rcx+29h], 3
0x140208680  jnb     short loc_140208685
0x140208682  xor     bpl, bpl
0x140208685  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14020868c  setnz   dil
0x140208690  test    bpl, bpl
0x140208693  jnz     short loc_14020869A
0x140208695  test    dil, dil
0x140208698  jz      short loc_1402086EC
0x14020869a  call    cs:__imp_W32GetUserSessionState
0x1402086a1  nop     dword ptr [rax+rax+00h]
0x1402086a6  cmp     [rsp+0A8h+arg_0], 0
0x1402086ae  lea     rcx, aShared; "shared"
0x1402086b5  mov     r8b, dil
0x1402086b8  mov     dl, bpl
0x1402086bb  mov     r9, [rax+10E10h]
0x1402086c2  lea     rax, aExclusive; "exclusive"
0x1402086c9  cmovz   rax, rcx
0x1402086cd  mov     rcx, [rsp+0A8h+var_48]
0x1402086d2  mov     [rsp+0A8h+var_60], rcx
0x1402086d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1402086de  mov     [rsp+0A8h+var_68], rax
0x1402086e3  mov     rcx, [rcx+18h]
0x1402086e7  call    WPP_RECORDER_AND_TRACE_SF_ss
0x1402086ec  xor     bpl, bpl
0x1402086ef  jmp     loc_140208783
0x1402086f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1402086fb  lea     r14, WPP_GLOBAL_Control
0x140208702  mov     ebp, 1
0x140208707  cmp     rcx, r14
0x14020870a  jz      short loc_14020871F
0x14020870c  mov     eax, [rcx+2Ch]
0x14020870f  test    bpl, al
0x140208712  jz      short loc_14020871F
0x140208714  cmp     byte ptr [rcx+29h], 4
0x140208718  jb      short loc_14020871F
0x14020871a  mov     dil, bpl
0x14020871d  jmp     short loc_140208722
0x14020871f  xor     dil, dil
0x140208722  lea     r15, WPP_RECORDER_INITIALIZED
0x140208729  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140208730  setnz   sil
0x140208734  test    dil, dil
0x140208737  jnz     short loc_14020873E
0x140208739  test    sil, sil
0x14020873c  jz      short loc_140208783
0x14020873e  call    cs:__imp_W32GetUserSessionState
0x140208745  nop     dword ptr [rax+rax+00h]
0x14020874a  mov     rcx, cs:WPP_GLOBAL_Control
0x140208751  mov     r8b, sil
0x140208754  mov     dl, dil
0x140208757  mov     r9, [rax+10E10h]
0x14020875e  lea     rax, WPP_c696d146d7263bd817038d8ba47edda4_Traceguids
0x140208765  mov     rcx, [rcx+18h]
0x140208769  mov     [rsp+0A8h+var_70], rax
0x14020876e  mov     [rsp+0A8h+var_78], 26h ; '&'
0x140208775  mov     [rsp+0A8h+var_80], ebp
0x140208779  mov     [rsp+0A8h+var_88], 4
0x14020877e  call    WPP_RECORDER_AND_TRACE_SF_
0x140208783  mov     rcx, rbx
0x140208786  call    RIMUnlockExclusive
0x14020878b  mov     rbx, [rsp+0A8h+arg_10]
0x140208793  mov     al, bpl
0x140208796  add     rsp, 70h
0x14020879a  pop     r15
0x14020879c  pop     r14
0x14020879e  pop     r13
0x1402087a0  pop     r12
0x1402087a2  pop     rdi
0x1402087a3  pop     rsi
0x1402087a4  pop     rbp
0x1402087a5  retn
```
