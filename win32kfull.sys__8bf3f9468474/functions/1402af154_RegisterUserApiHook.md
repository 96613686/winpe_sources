# _RegisterUserApiHook

- ea: `0x1402af154`
- end: `0x1402af53d`
- name: `_RegisterUserApiHook`
- size: `1001`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140234f60`

## callees

- `0x14000b370`
- `0x1400c2a10`
- `0x140110830`
- `0x14012167c`
- `0x14012188c`
- `0x140121924`
- `0x1402913f0`
- `0x1402af154`
- `0x1403d21c8`
- `0x1403d2204`

## import_xrefs

- `ntoskrnl!ExRaiseAccessViolation` at `0x1402af47f`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1402af4ae`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1402af4dd`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1402af50c`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1402af47f`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1402af4ae`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1402af4dd`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1402af50c`
- `ntoskrnl!ProbeForRead` at `0x1402af25a`
- `ntoskrnl!ProbeForRead` at `0x1402af2b4`
- `ntoskrnl!ProbeForRead` at `0x1402af324`
- `ntoskrnl!ProbeForRead` at `0x1402af37f`
- `ntoskrnl!ProbeForRead` at `0x1402af25a`
- `ntoskrnl!ProbeForRead` at `0x1402af2b4`
- `ntoskrnl!ProbeForRead` at `0x1402af324`
- `ntoskrnl!ProbeForRead` at `0x1402af37f`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402af19d`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402af1cf`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402af417`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402af19d`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402af1cf`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402af417`
- `win32kbase!IsRestricted` at `0x1402af189`
- `win32kbase!IsRestricted` at `0x1402af189`
- `win32kbase!HasTcbPrivilege` at `0x1402af202`
- `win32kbase!HasTcbPrivilege` at `0x1402af202`
- `win32kbase!luidSystem` at `0x1402af1ba`
- `win32kbase!luidSystem` at `0x1402af1ec`
- `WIN32K!W32GetUserSessionState` at `0x1402af216`
- `WIN32K!W32GetUserSessionState` at `0x1402af43b`
- `WIN32K!W32GetUserSessionState` at `0x1402af216`
- `WIN32K!W32GetUserSessionState` at `0x1402af43b`

## pseudocode

```c
__int64 __fastcall RegisterUserApiHook(unsigned int *a1, unsigned int *a2, unsigned int *a3, unsigned int *a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 CurrentProcessWin32Process; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 UserSessionState; // rsi
  volatile void *ULong64FromUser; // r15
  volatile void *v22; // r14
  volatile void *v23; // r12
  int v24; // edi
  volatile void *v25; // r14
  unsigned int HmodTableIndex; // eax
  __int64 v27; // rcx
  unsigned int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  int ULongFromUser; // [rsp+38h] [rbp-80h]
  int v40; // [rsp+48h] [rbp-70h]
  int v41; // [rsp+58h] [rbp-60h]

  if ( (unsigned int)IsInsideUserApiHook() || (unsigned __int8)IsRestricted(KeGetCurrentThread()) )
    goto LABEL_37;
  CurrentProcessWin32Process = PsGetCurrentProcessWin32Process(v9, v8, v10, v11);
  if ( CurrentProcessWin32Process )
    CurrentProcessWin32Process &= -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0);
  if ( *(_DWORD *)(CurrentProcessWin32Process + 764) != luidSystem[0] )
    goto LABEL_37;
  v15 = PsGetCurrentProcessWin32Process(*(_QWORD *)luidSystem, luidSystem[0], v13, v14);
  if ( v15 )
    v15 &= -(__int64)(*(_QWORD *)v15 != 0);
  if ( *(_DWORD *)(v15 + 768) != luidSystem[1] || !(unsigned __int8)HasTcbPrivilege(*(_QWORD *)luidSystem) )
  {
LABEL_37:
    v27 = 5;
    goto LABEL_38;
  }
  UserSessionState = W32GetUserSessionState(v17, v16, v18, v19);
  ULongFromUser = RtlReadULongFromUser(a1);
  ULong64FromUser = (volatile void *)RtlReadULong64FromUser(a1 + 2);
  ProbeForRead(ULong64FromUser, (unsigned __int16)ULongFromUser + 2LL, 2u);
  if ( (unsigned __int16)ULongFromUser > HIWORD(ULongFromUser) )
  {
    if ( (ULongFromUser & 1) == 0 )
      goto LABEL_36;
    goto LABEL_35;
  }
  if ( (ULongFromUser & 1) != 0 )
  {
LABEL_35:
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2823);
LABEL_36:
    ExRaiseAccessViolation();
  }
  v40 = RtlReadULongFromUser(a2);
  v22 = (volatile void *)RtlReadULong64FromUser(a2 + 2);
  ProbeForRead(v22, (unsigned __int16)v40 + 2LL, 2u);
  if ( (unsigned __int16)v40 > HIWORD(v40) )
  {
    if ( (v40 & 1) == 0 )
      goto LABEL_33;
    goto LABEL_32;
  }
  if ( (v40 & 1) != 0 )
  {
LABEL_32:
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2826);
LABEL_33:
    ExRaiseAccessViolation();
  }
  RtlStringCchCopyW((unsigned __int16 *)(UserSessionState + 63988), 0x104u, (const unsigned __int16 *)v22);
  v41 = RtlReadULongFromUser(a3);
  v23 = (volatile void *)RtlReadULong64FromUser(a3 + 2);
  ProbeForRead(v23, (unsigned __int16)v41 + 2LL, 2u);
  if ( (unsigned __int16)v41 > HIWORD(v41) )
  {
    if ( (v41 & 1) == 0 )
      goto LABEL_30;
    goto LABEL_29;
  }
  if ( (v41 & 1) != 0 )
  {
LABEL_29:
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2832);
LABEL_30:
    ExRaiseAccessViolation();
  }
  v24 = RtlReadULongFromUser(a4);
  v25 = (volatile void *)RtlReadULong64FromUser(a4 + 2);
  ProbeForRead(v25, (unsigned __int16)v24 + 2LL, 2u);
  if ( (unsigned __int16)v24 > HIWORD(v24) )
  {
    if ( (v24 & 1) == 0 )
      goto LABEL_27;
    goto LABEL_26;
  }
  if ( (v24 & 1) != 0 )
  {
LABEL_26:
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2835);
LABEL_27:
    ExRaiseAccessViolation();
  }
  RtlStringCchCopyW((unsigned __int16 *)(UserSessionState + 64512), 0x104u, (const unsigned __int16 *)v25);
  HmodTableIndex = GetHmodTableIndex(ULong64FromUser);
  *(_DWORD *)(UserSessionState + 63984) = HmodTableIndex;
  if ( HmodTableIndex == -1 )
  {
    v27 = 126;
LABEL_38:
    UserSetLastError(v27);
    return 0;
  }
  AddHmodDependency(HmodTableIndex);
  v28 = GetHmodTableIndex(v23);
  *(_DWORD *)(UserSessionState + 64508) = v28;
  if ( v28 == -1 )
  {
    UserSetLastError(126);
    RemoveHmodDependency(*(unsigned int *)(UserSessionState + 63984));
    *(_DWORD *)(UserSessionState + 63984) = -1;
    return 0;
  }
  AddHmodDependency(v28);
  v33 = PsGetCurrentProcessWin32Process(v30, v29, v31, v32);
  if ( v33 )
  {
    v35 = -*(_QWORD *)v33;
    v34 = -(__int64)(*(_QWORD *)v33 != 0);
    v33 &= v34;
  }
  *(_QWORD *)(UserSessionState + 63976) = v33;
  _InterlockedOr(*(volatile signed __int32 **)(W32GetUserSessionState(v35, v34, v36, v37) + 19704), 0x10u);
  return 1;
}

```

## disassembly

```asm
0x1402af154  push    rbx
0x1402af156  push    rsi
0x1402af157  push    rdi
0x1402af158  push    r12
0x1402af15a  push    r13
0x1402af15c  push    r14
0x1402af15e  push    r15
0x1402af160  sub     rsp, 80h
0x1402af167  mov     r13, r9
0x1402af16a  mov     r12, r8
0x1402af16d  mov     r14, rdx
0x1402af170  mov     rbx, rcx
0x1402af173  call    ?IsInsideUserApiHook@@YAHXZ; IsInsideUserApiHook(void)
0x1402af178  test    eax, eax
0x1402af17a  jnz     loc_1402AF51D
0x1402af180  mov     rcx, gs:188h
0x1402af189  call    cs:__imp_IsRestricted
0x1402af190  nop     dword ptr [rax+rax+00h]
0x1402af195  test    al, al
0x1402af197  jnz     loc_1402AF51D
0x1402af19d  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1402af1a4  nop     dword ptr [rax+rax+00h]
0x1402af1a9  test    rax, rax
0x1402af1ac  jz      short loc_1402AF1BA
0x1402af1ae  mov     rcx, [rax]
0x1402af1b1  neg     rcx
0x1402af1b4  sbb     rdx, rdx
0x1402af1b7  and     rax, rdx
0x1402af1ba  mov     rcx, cs:__imp_luidSystem
0x1402af1c1  mov     edx, [rcx]
0x1402af1c3  cmp     [rax+2FCh], edx
0x1402af1c9  jnz     loc_1402AF51D
0x1402af1cf  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1402af1d6  nop     dword ptr [rax+rax+00h]
0x1402af1db  test    rax, rax
0x1402af1de  jz      short loc_1402AF1EC
0x1402af1e0  mov     rcx, [rax]
0x1402af1e3  neg     rcx
0x1402af1e6  sbb     rdx, rdx
0x1402af1e9  and     rax, rdx
0x1402af1ec  mov     rcx, cs:__imp_luidSystem
0x1402af1f3  mov     edx, [rcx+4]
0x1402af1f6  cmp     [rax+300h], edx
0x1402af1fc  jnz     loc_1402AF51D
0x1402af202  call    cs:__imp_HasTcbPrivilege
0x1402af209  nop     dword ptr [rax+rax+00h]
0x1402af20e  test    al, al
0x1402af210  jz      loc_1402AF51D
0x1402af216  call    cs:__imp_W32GetUserSessionState
0x1402af21d  nop     dword ptr [rax+rax+00h]
0x1402af222  mov     rsi, rax
0x1402af225  mov     rcx, rbx
0x1402af228  call    RtlReadULongFromUser
0x1402af22d  mov     edi, eax
0x1402af22f  mov     [rsp+0B8h+var_80], edi
0x1402af233  lea     rcx, [rbx+8]
0x1402af237  call    RtlReadULong64FromUser
0x1402af23c  mov     r15, rax
0x1402af23f  mov     [rsp+0B8h+var_78], rax
0x1402af244  mov     ebx, edi
0x1402af246  shr     ebx, 10h
0x1402af249  movzx   edx, di
0x1402af24c  mov     eax, 2
0x1402af251  add     rdx, rax; Length
0x1402af254  mov     r8d, eax; Alignment
0x1402af257  mov     rcx, r15; Address
0x1402af25a  call    cs:__imp_ProbeForRead
0x1402af261  nop     dword ptr [rax+rax+00h]
0x1402af266  movzx   ecx, di
0x1402af269  and     cx, 1
0x1402af26d  cmp     di, bx
0x1402af270  ja      loc_1402AF4E9
0x1402af276  test    cx, cx
0x1402af279  jnz     loc_1402AF4EE
0x1402af27f  mov     rcx, r14
0x1402af282  call    RtlReadULongFromUser
0x1402af287  mov     edi, eax
0x1402af289  mov     [rsp+0B8h+var_70], edi
0x1402af28d  lea     rcx, [r14+8]
0x1402af291  call    RtlReadULong64FromUser
0x1402af296  mov     r14, rax
0x1402af299  mov     [rsp+0B8h+var_68], rax
0x1402af29e  mov     ebx, edi
0x1402af2a0  shr     ebx, 10h
0x1402af2a3  movzx   edx, di
0x1402af2a6  mov     eax, 2
0x1402af2ab  add     rdx, rax; Length
0x1402af2ae  mov     r8d, eax; Alignment
0x1402af2b1  mov     rcx, r14; Address
0x1402af2b4  call    cs:__imp_ProbeForRead
0x1402af2bb  nop     dword ptr [rax+rax+00h]
0x1402af2c0  movzx   ecx, di
0x1402af2c3  and     cx, 1
0x1402af2c7  cmp     di, bx
0x1402af2ca  ja      loc_1402AF4BA
0x1402af2d0  test    cx, cx
0x1402af2d3  jnz     loc_1402AF4BF
0x1402af2d9  lea     rcx, [rsi+0F9F4h]; unsigned __int16 *
0x1402af2e0  mov     r8, r14; unsigned __int16 *
0x1402af2e3  mov     edx, 104h; unsigned __int64
0x1402af2e8  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1402af2ed  mov     rcx, r12
0x1402af2f0  call    RtlReadULongFromUser
0x1402af2f5  mov     edi, eax
0x1402af2f7  mov     [rsp+0B8h+var_60], edi
0x1402af2fb  lea     rcx, [r12+8]
0x1402af300  call    RtlReadULong64FromUser
0x1402af305  mov     r12, rax
0x1402af308  mov     [rsp+0B8h+var_58], rax
0x1402af30d  mov     ebx, edi
0x1402af30f  shr     ebx, 10h
0x1402af312  movzx   edx, di
0x1402af315  mov     r14d, 2
0x1402af31b  add     rdx, r14; Length
0x1402af31e  mov     r8d, r14d; Alignment
0x1402af321  mov     rcx, rax; Address
0x1402af324  call    cs:__imp_ProbeForRead
0x1402af32b  nop     dword ptr [rax+rax+00h]
0x1402af330  movzx   ecx, di
0x1402af333  and     cx, 1
0x1402af337  cmp     di, bx
0x1402af33a  ja      loc_1402AF48B
0x1402af340  test    cx, cx
0x1402af343  jnz     loc_1402AF490
0x1402af349  mov     rcx, r13
0x1402af34c  call    RtlReadULongFromUser
0x1402af351  mov     edi, eax
0x1402af353  mov     [rsp+0B8h+var_50], edi
0x1402af357  lea     rcx, [r13+8]
0x1402af35b  call    RtlReadULong64FromUser
0x1402af360  mov     r14, rax
0x1402af363  mov     [rsp+0B8h+var_48], rax
0x1402af368  mov     ebx, edi
0x1402af36a  shr     ebx, 10h
0x1402af36d  movzx   edx, di
0x1402af370  mov     r13d, 2
0x1402af376  add     rdx, r13; Length
0x1402af379  mov     r8d, r13d; Alignment
0x1402af37c  mov     rcx, rax; Address
0x1402af37f  call    cs:__imp_ProbeForRead
0x1402af386  nop     dword ptr [rax+rax+00h]
0x1402af38b  movzx   ecx, di
0x1402af38e  and     cx, 1
0x1402af392  cmp     di, bx
0x1402af395  ja      loc_1402AF45C
0x1402af39b  test    cx, cx
0x1402af39e  jnz     loc_1402AF461
0x1402af3a4  lea     rcx, [rsi+0FC00h]; unsigned __int16 *
0x1402af3ab  mov     r8, r14; unsigned __int16 *
0x1402af3ae  mov     edx, 104h; unsigned __int64
0x1402af3b3  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1402af3b8  nop
0x1402af3b9  mov     rcx, r15
0x1402af3bc  call    GetHmodTableIndex
0x1402af3c1  mov     [rsi+0F9F0h], eax
0x1402af3c7  cmp     eax, 0FFFFFFFFh
0x1402af3ca  jnz     short loc_1402AF3D4
0x1402af3cc  lea     ecx, [rax+7Fh]
0x1402af3cf  jmp     loc_1402AF522
0x1402af3d4  mov     ecx, eax
0x1402af3d6  call    AddHmodDependency
0x1402af3db  mov     rcx, r12
0x1402af3de  call    GetHmodTableIndex
0x1402af3e3  mov     [rsi+0FBFCh], eax
0x1402af3e9  cmp     eax, 0FFFFFFFFh
0x1402af3ec  jnz     short loc_1402AF410
0x1402af3ee  lea     ecx, [rax+7Fh]
0x1402af3f1  call    UserSetLastError
0x1402af3f6  mov     ecx, [rsi+0F9F0h]
0x1402af3fc  call    RemoveHmodDependency
0x1402af401  mov     dword ptr [rsi+0F9F0h], 0FFFFFFFFh
0x1402af40b  jmp     loc_1402AF527
0x1402af410  mov     ecx, eax
0x1402af412  call    AddHmodDependency
0x1402af417  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1402af41e  nop     dword ptr [rax+rax+00h]
0x1402af423  test    rax, rax
0x1402af426  jz      short loc_1402AF434
0x1402af428  mov     rcx, [rax]
0x1402af42b  neg     rcx
0x1402af42e  sbb     rdx, rdx
0x1402af431  and     rax, rdx
0x1402af434  mov     [rsi+0F9E8h], rax
0x1402af43b  call    cs:__imp_W32GetUserSessionState
0x1402af442  nop     dword ptr [rax+rax+00h]
0x1402af447  mov     rcx, [rax+4CF8h]
0x1402af44e  lock or dword ptr [rcx], 10h
0x1402af452  mov     eax, 1
0x1402af457  jmp     loc_1402AF529
0x1402af45c  test    cx, cx
0x1402af45f  jz      short loc_1402AF47F
0x1402af461  mov     [rsp+0B8h+var_98], 20000h
0x1402af469  mov     r8d, 0B13h
0x1402af46f  mov     edx, [rsp+0B8h+var_98]
0x1402af473  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1402af47a  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1402af47f  call    cs:__imp_ExRaiseAccessViolation
0x1402af486  nop     dword ptr [rax+rax+00h]
0x1402af48b  test    cx, cx
0x1402af48e  jz      short loc_1402AF4AE
0x1402af490  mov     [rsp+0B8h+var_94], 20000h
0x1402af498  mov     r8d, 0B10h
0x1402af49e  mov     edx, [rsp+0B8h+var_94]
0x1402af4a2  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1402af4a9  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1402af4ae  call    cs:__imp_ExRaiseAccessViolation
0x1402af4b5  nop     dword ptr [rax+rax+00h]
0x1402af4ba  test    cx, cx
0x1402af4bd  jz      short loc_1402AF4DD
0x1402af4bf  mov     [rsp+0B8h+var_90], 20000h
0x1402af4c7  mov     r8d, 0B0Ah
0x1402af4cd  mov     edx, [rsp+0B8h+var_90]
0x1402af4d1  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1402af4d8  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1402af4dd  call    cs:__imp_ExRaiseAccessViolation
0x1402af4e4  nop     dword ptr [rax+rax+00h]
0x1402af4e9  test    cx, cx
0x1402af4ec  jz      short loc_1402AF50C
0x1402af4ee  mov     [rsp+0B8h+var_8C], 20000h
0x1402af4f6  mov     r8d, 0B07h
0x1402af4fc  mov     edx, [rsp+0B8h+var_8C]
0x1402af500  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1402af507  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1402af50c  call    cs:__imp_ExRaiseAccessViolation
0x1402af513  nop     dword ptr [rax+rax+00h]
0x1402af518  nop
0x1402af519  xor     eax, eax
0x1402af51b  jmp     short loc_1402AF529
0x1402af51d  mov     ecx, 5
0x1402af522  call    UserSetLastError
0x1402af527  xor     eax, eax
0x1402af529  add     rsp, 80h
0x1402af530  pop     r15
0x1402af532  pop     r14
0x1402af534  pop     r13
0x1402af536  pop     r12
0x1402af538  pop     rdi
0x1402af539  pop     rsi
0x1402af53a  pop     rbx
0x1402af53b  retn
0x140348309  push    rbp
0x14034830b  sub     rsp, 20h
0x14034830f  mov     rbp, rdx
0x140348312  mov     eax, 1
0x140348317  add     rsp, 20h
0x14034831b  pop     rbp
0x14034831c  retn
```
