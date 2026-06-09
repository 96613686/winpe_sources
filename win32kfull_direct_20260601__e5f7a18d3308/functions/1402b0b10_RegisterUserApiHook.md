# _RegisterUserApiHook

- ea: `0x1402b0b10`
- end: `0x1402b0ef9`
- name: `_RegisterUserApiHook`
- size: `1001`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140235500`

## callees

- `0x1400c58cc`
- `0x1400c5adc`
- `0x1400c5b74`
- `0x1400cf450`
- `0x1400e8c20`
- `0x140126de0`
- `0x1402938dc`
- `0x1402b0b10`
- `0x1403d31c8`
- `0x1403d3204`

## import_xrefs

- `ntoskrnl!ExRaiseAccessViolation` at `0x1402b0e3b`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1402b0e6a`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1402b0e99`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1402b0ec8`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1402b0e3b`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1402b0e6a`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1402b0e99`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1402b0ec8`
- `ntoskrnl!ProbeForRead` at `0x1402b0c16`
- `ntoskrnl!ProbeForRead` at `0x1402b0c70`
- `ntoskrnl!ProbeForRead` at `0x1402b0ce0`
- `ntoskrnl!ProbeForRead` at `0x1402b0d3b`
- `ntoskrnl!ProbeForRead` at `0x1402b0c16`
- `ntoskrnl!ProbeForRead` at `0x1402b0c70`
- `ntoskrnl!ProbeForRead` at `0x1402b0ce0`
- `ntoskrnl!ProbeForRead` at `0x1402b0d3b`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402b0b59`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402b0b8b`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402b0dd3`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402b0b59`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402b0b8b`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402b0dd3`
- `win32kbase!IsRestricted` at `0x1402b0b45`
- `win32kbase!IsRestricted` at `0x1402b0b45`
- `win32kbase!HasTcbPrivilege` at `0x1402b0bbe`
- `win32kbase!HasTcbPrivilege` at `0x1402b0bbe`
- `win32kbase!luidSystem` at `0x1402b0b76`
- `win32kbase!luidSystem` at `0x1402b0ba8`
- `WIN32K!W32GetUserSessionState` at `0x1402b0bd2`
- `WIN32K!W32GetUserSessionState` at `0x1402b0df7`
- `WIN32K!W32GetUserSessionState` at `0x1402b0bd2`
- `WIN32K!W32GetUserSessionState` at `0x1402b0df7`

## pseudocode

```c
__int64 __fastcall RegisterUserApiHook(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 CurrentProcessWin32Process; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 UserSessionState; // rsi
  volatile void *ULong64FromUser; // r15
  volatile void *v14; // r14
  volatile void *v15; // r12
  int v16; // edi
  volatile void *v17; // r14
  unsigned int HmodTableIndex; // eax
  __int64 v19; // rcx
  unsigned int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  int ULongFromUser; // [rsp+38h] [rbp-80h]
  int v26; // [rsp+48h] [rbp-70h]
  int v27; // [rsp+58h] [rbp-60h]

  if ( (unsigned int)IsInsideUserApiHook() || (unsigned __int8)IsRestricted(KeGetCurrentThread()) )
    goto LABEL_37;
  CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
  if ( CurrentProcessWin32Process )
    CurrentProcessWin32Process &= -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0);
  if ( *(_DWORD *)(CurrentProcessWin32Process + 764) != luidSystem[0] )
    goto LABEL_37;
  v9 = PsGetCurrentProcessWin32Process();
  if ( v9 )
    v9 &= -(__int64)(*(_QWORD *)v9 != 0);
  if ( *(_DWORD *)(v9 + 768) != luidSystem[1] || !(unsigned __int8)HasTcbPrivilege() )
  {
LABEL_37:
    v19 = 5;
    goto LABEL_38;
  }
  UserSessionState = W32GetUserSessionState(v11, v10);
  ULongFromUser = RtlReadULongFromUser(a1);
  ULong64FromUser = (volatile void *)RtlReadULong64FromUser(a1 + 8);
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
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2939);
LABEL_36:
    ExRaiseAccessViolation();
  }
  v26 = RtlReadULongFromUser(a2);
  v14 = (volatile void *)RtlReadULong64FromUser(a2 + 8);
  ProbeForRead(v14, (unsigned __int16)v26 + 2LL, 2u);
  if ( (unsigned __int16)v26 > HIWORD(v26) )
  {
    if ( (v26 & 1) == 0 )
      goto LABEL_33;
    goto LABEL_32;
  }
  if ( (v26 & 1) != 0 )
  {
LABEL_32:
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2942);
LABEL_33:
    ExRaiseAccessViolation();
  }
  RtlStringCchCopyW((unsigned __int16 *)(UserSessionState + 63988), 0x104u, (const unsigned __int16 *)v14);
  v27 = RtlReadULongFromUser(a3);
  v15 = (volatile void *)RtlReadULong64FromUser(a3 + 8);
  ProbeForRead(v15, (unsigned __int16)v27 + 2LL, 2u);
  if ( (unsigned __int16)v27 > HIWORD(v27) )
  {
    if ( (v27 & 1) == 0 )
      goto LABEL_30;
    goto LABEL_29;
  }
  if ( (v27 & 1) != 0 )
  {
LABEL_29:
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2948);
LABEL_30:
    ExRaiseAccessViolation();
  }
  v16 = RtlReadULongFromUser(a4);
  v17 = (volatile void *)RtlReadULong64FromUser(a4 + 8);
  ProbeForRead(v17, (unsigned __int16)v16 + 2LL, 2u);
  if ( (unsigned __int16)v16 > HIWORD(v16) )
  {
    if ( (v16 & 1) == 0 )
      goto LABEL_27;
    goto LABEL_26;
  }
  if ( (v16 & 1) != 0 )
  {
LABEL_26:
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2951);
LABEL_27:
    ExRaiseAccessViolation();
  }
  RtlStringCchCopyW((unsigned __int16 *)(UserSessionState + 64512), 0x104u, (const unsigned __int16 *)v17);
  HmodTableIndex = GetHmodTableIndex(ULong64FromUser);
  *(_DWORD *)(UserSessionState + 63984) = HmodTableIndex;
  if ( HmodTableIndex == -1 )
  {
    v19 = 126;
LABEL_38:
    UserSetLastError(v19);
    return 0;
  }
  AddHmodDependency(HmodTableIndex);
  v20 = GetHmodTableIndex(v15);
  *(_DWORD *)(UserSessionState + 64508) = v20;
  if ( v20 == -1 )
  {
    UserSetLastError(126);
    RemoveHmodDependency(*(unsigned int *)(UserSessionState + 63984));
    *(_DWORD *)(UserSessionState + 63984) = -1;
    return 0;
  }
  AddHmodDependency(v20);
  v21 = PsGetCurrentProcessWin32Process();
  if ( v21 )
  {
    v23 = -*(_QWORD *)v21;
    v22 = -(__int64)(*(_QWORD *)v21 != 0);
    v21 &= v22;
  }
  *(_QWORD *)(UserSessionState + 63976) = v21;
  _InterlockedOr(*(volatile signed __int32 **)(W32GetUserSessionState(v23, v22) + 19704), 0x10u);
  return 1;
}

```

## disassembly

```asm
0x1402b0b10  push    rbx
0x1402b0b12  push    rsi
0x1402b0b13  push    rdi
0x1402b0b14  push    r12
0x1402b0b16  push    r13
0x1402b0b18  push    r14
0x1402b0b1a  push    r15
0x1402b0b1c  sub     rsp, 80h
0x1402b0b23  mov     r13, r9
0x1402b0b26  mov     r12, r8
0x1402b0b29  mov     r14, rdx
0x1402b0b2c  mov     rbx, rcx
0x1402b0b2f  call    ?IsInsideUserApiHook@@YAHXZ; IsInsideUserApiHook(void)
0x1402b0b34  test    eax, eax
0x1402b0b36  jnz     loc_1402B0ED9
0x1402b0b3c  mov     rcx, gs:188h
0x1402b0b45  call    cs:__imp_IsRestricted
0x1402b0b4c  nop     dword ptr [rax+rax+00h]
0x1402b0b51  test    al, al
0x1402b0b53  jnz     loc_1402B0ED9
0x1402b0b59  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1402b0b60  nop     dword ptr [rax+rax+00h]
0x1402b0b65  test    rax, rax
0x1402b0b68  jz      short loc_1402B0B76
0x1402b0b6a  mov     rcx, [rax]
0x1402b0b6d  neg     rcx
0x1402b0b70  sbb     rdx, rdx
0x1402b0b73  and     rax, rdx
0x1402b0b76  mov     rcx, cs:__imp_luidSystem
0x1402b0b7d  mov     edx, [rcx]
0x1402b0b7f  cmp     [rax+2FCh], edx
0x1402b0b85  jnz     loc_1402B0ED9
0x1402b0b8b  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1402b0b92  nop     dword ptr [rax+rax+00h]
0x1402b0b97  test    rax, rax
0x1402b0b9a  jz      short loc_1402B0BA8
0x1402b0b9c  mov     rcx, [rax]
0x1402b0b9f  neg     rcx
0x1402b0ba2  sbb     rdx, rdx
0x1402b0ba5  and     rax, rdx
0x1402b0ba8  mov     rcx, cs:__imp_luidSystem
0x1402b0baf  mov     edx, [rcx+4]
0x1402b0bb2  cmp     [rax+300h], edx
0x1402b0bb8  jnz     loc_1402B0ED9
0x1402b0bbe  call    cs:__imp_HasTcbPrivilege
0x1402b0bc5  nop     dword ptr [rax+rax+00h]
0x1402b0bca  test    al, al
0x1402b0bcc  jz      loc_1402B0ED9
0x1402b0bd2  call    cs:__imp_W32GetUserSessionState
0x1402b0bd9  nop     dword ptr [rax+rax+00h]
0x1402b0bde  mov     rsi, rax
0x1402b0be1  mov     rcx, rbx
0x1402b0be4  call    RtlReadULongFromUser
0x1402b0be9  mov     edi, eax
0x1402b0beb  mov     [rsp+0B8h+var_80], edi
0x1402b0bef  lea     rcx, [rbx+8]
0x1402b0bf3  call    RtlReadULong64FromUser
0x1402b0bf8  mov     r15, rax
0x1402b0bfb  mov     [rsp+0B8h+var_78], rax
0x1402b0c00  mov     ebx, edi
0x1402b0c02  shr     ebx, 10h
0x1402b0c05  movzx   edx, di
0x1402b0c08  mov     eax, 2
0x1402b0c0d  add     rdx, rax; Length
0x1402b0c10  mov     r8d, eax; Alignment
0x1402b0c13  mov     rcx, r15; Address
0x1402b0c16  call    cs:__imp_ProbeForRead
0x1402b0c1d  nop     dword ptr [rax+rax+00h]
0x1402b0c22  movzx   ecx, di
0x1402b0c25  and     cx, 1
0x1402b0c29  cmp     di, bx
0x1402b0c2c  ja      loc_1402B0EA5
0x1402b0c32  test    cx, cx
0x1402b0c35  jnz     loc_1402B0EAA
0x1402b0c3b  mov     rcx, r14
0x1402b0c3e  call    RtlReadULongFromUser
0x1402b0c43  mov     edi, eax
0x1402b0c45  mov     [rsp+0B8h+var_70], edi
0x1402b0c49  lea     rcx, [r14+8]
0x1402b0c4d  call    RtlReadULong64FromUser
0x1402b0c52  mov     r14, rax
0x1402b0c55  mov     [rsp+0B8h+var_68], rax
0x1402b0c5a  mov     ebx, edi
0x1402b0c5c  shr     ebx, 10h
0x1402b0c5f  movzx   edx, di
0x1402b0c62  mov     eax, 2
0x1402b0c67  add     rdx, rax; Length
0x1402b0c6a  mov     r8d, eax; Alignment
0x1402b0c6d  mov     rcx, r14; Address
0x1402b0c70  call    cs:__imp_ProbeForRead
0x1402b0c77  nop     dword ptr [rax+rax+00h]
0x1402b0c7c  movzx   ecx, di
0x1402b0c7f  and     cx, 1
0x1402b0c83  cmp     di, bx
0x1402b0c86  ja      loc_1402B0E76
0x1402b0c8c  test    cx, cx
0x1402b0c8f  jnz     loc_1402B0E7B
0x1402b0c95  lea     rcx, [rsi+0F9F4h]; unsigned __int16 *
0x1402b0c9c  mov     r8, r14; unsigned __int16 *
0x1402b0c9f  mov     edx, 104h; unsigned __int64
0x1402b0ca4  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1402b0ca9  mov     rcx, r12
0x1402b0cac  call    RtlReadULongFromUser
0x1402b0cb1  mov     edi, eax
0x1402b0cb3  mov     [rsp+0B8h+var_60], edi
0x1402b0cb7  lea     rcx, [r12+8]
0x1402b0cbc  call    RtlReadULong64FromUser
0x1402b0cc1  mov     r12, rax
0x1402b0cc4  mov     [rsp+0B8h+var_58], rax
0x1402b0cc9  mov     ebx, edi
0x1402b0ccb  shr     ebx, 10h
0x1402b0cce  movzx   edx, di
0x1402b0cd1  mov     r14d, 2
0x1402b0cd7  add     rdx, r14; Length
0x1402b0cda  mov     r8d, r14d; Alignment
0x1402b0cdd  mov     rcx, rax; Address
0x1402b0ce0  call    cs:__imp_ProbeForRead
0x1402b0ce7  nop     dword ptr [rax+rax+00h]
0x1402b0cec  movzx   ecx, di
0x1402b0cef  and     cx, 1
0x1402b0cf3  cmp     di, bx
0x1402b0cf6  ja      loc_1402B0E47
0x1402b0cfc  test    cx, cx
0x1402b0cff  jnz     loc_1402B0E4C
0x1402b0d05  mov     rcx, r13
0x1402b0d08  call    RtlReadULongFromUser
0x1402b0d0d  mov     edi, eax
0x1402b0d0f  mov     [rsp+0B8h+var_50], edi
0x1402b0d13  lea     rcx, [r13+8]
0x1402b0d17  call    RtlReadULong64FromUser
0x1402b0d1c  mov     r14, rax
0x1402b0d1f  mov     [rsp+0B8h+var_48], rax
0x1402b0d24  mov     ebx, edi
0x1402b0d26  shr     ebx, 10h
0x1402b0d29  movzx   edx, di
0x1402b0d2c  mov     r13d, 2
0x1402b0d32  add     rdx, r13; Length
0x1402b0d35  mov     r8d, r13d; Alignment
0x1402b0d38  mov     rcx, rax; Address
0x1402b0d3b  call    cs:__imp_ProbeForRead
0x1402b0d42  nop     dword ptr [rax+rax+00h]
0x1402b0d47  movzx   ecx, di
0x1402b0d4a  and     cx, 1
0x1402b0d4e  cmp     di, bx
0x1402b0d51  ja      loc_1402B0E18
0x1402b0d57  test    cx, cx
0x1402b0d5a  jnz     loc_1402B0E1D
0x1402b0d60  lea     rcx, [rsi+0FC00h]; unsigned __int16 *
0x1402b0d67  mov     r8, r14; unsigned __int16 *
0x1402b0d6a  mov     edx, 104h; unsigned __int64
0x1402b0d6f  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1402b0d74  nop
0x1402b0d75  mov     rcx, r15
0x1402b0d78  call    GetHmodTableIndex
0x1402b0d7d  mov     [rsi+0F9F0h], eax
0x1402b0d83  cmp     eax, 0FFFFFFFFh
0x1402b0d86  jnz     short loc_1402B0D90
0x1402b0d88  lea     ecx, [rax+7Fh]
0x1402b0d8b  jmp     loc_1402B0EDE
0x1402b0d90  mov     ecx, eax
0x1402b0d92  call    AddHmodDependency
0x1402b0d97  mov     rcx, r12
0x1402b0d9a  call    GetHmodTableIndex
0x1402b0d9f  mov     [rsi+0FBFCh], eax
0x1402b0da5  cmp     eax, 0FFFFFFFFh
0x1402b0da8  jnz     short loc_1402B0DCC
0x1402b0daa  lea     ecx, [rax+7Fh]
0x1402b0dad  call    UserSetLastError
0x1402b0db2  mov     ecx, [rsi+0F9F0h]
0x1402b0db8  call    RemoveHmodDependency
0x1402b0dbd  mov     dword ptr [rsi+0F9F0h], 0FFFFFFFFh
0x1402b0dc7  jmp     loc_1402B0EE3
0x1402b0dcc  mov     ecx, eax
0x1402b0dce  call    AddHmodDependency
0x1402b0dd3  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1402b0dda  nop     dword ptr [rax+rax+00h]
0x1402b0ddf  test    rax, rax
0x1402b0de2  jz      short loc_1402B0DF0
0x1402b0de4  mov     rcx, [rax]
0x1402b0de7  neg     rcx
0x1402b0dea  sbb     rdx, rdx
0x1402b0ded  and     rax, rdx
0x1402b0df0  mov     [rsi+0F9E8h], rax
0x1402b0df7  call    cs:__imp_W32GetUserSessionState
0x1402b0dfe  nop     dword ptr [rax+rax+00h]
0x1402b0e03  mov     rcx, [rax+4CF8h]
0x1402b0e0a  lock or dword ptr [rcx], 10h
0x1402b0e0e  mov     eax, 1
0x1402b0e13  jmp     loc_1402B0EE5
0x1402b0e18  test    cx, cx
0x1402b0e1b  jz      short loc_1402B0E3B
0x1402b0e1d  mov     [rsp+0B8h+var_98], 20000h
0x1402b0e25  mov     r8d, 0B87h
0x1402b0e2b  mov     edx, [rsp+0B8h+var_98]
0x1402b0e2f  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1402b0e36  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1402b0e3b  call    cs:__imp_ExRaiseAccessViolation
0x1402b0e42  nop     dword ptr [rax+rax+00h]
0x1402b0e47  test    cx, cx
0x1402b0e4a  jz      short loc_1402B0E6A
0x1402b0e4c  mov     [rsp+0B8h+var_94], 20000h
0x1402b0e54  mov     r8d, 0B84h
0x1402b0e5a  mov     edx, [rsp+0B8h+var_94]
0x1402b0e5e  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1402b0e65  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1402b0e6a  call    cs:__imp_ExRaiseAccessViolation
0x1402b0e71  nop     dword ptr [rax+rax+00h]
0x1402b0e76  test    cx, cx
0x1402b0e79  jz      short loc_1402B0E99
0x1402b0e7b  mov     [rsp+0B8h+var_90], 20000h
0x1402b0e83  mov     r8d, 0B7Eh
0x1402b0e89  mov     edx, [rsp+0B8h+var_90]
0x1402b0e8d  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1402b0e94  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1402b0e99  call    cs:__imp_ExRaiseAccessViolation
0x1402b0ea0  nop     dword ptr [rax+rax+00h]
0x1402b0ea5  test    cx, cx
0x1402b0ea8  jz      short loc_1402B0EC8
0x1402b0eaa  mov     [rsp+0B8h+var_8C], 20000h
0x1402b0eb2  mov     r8d, 0B7Bh
0x1402b0eb8  mov     edx, [rsp+0B8h+var_8C]
0x1402b0ebc  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1402b0ec3  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1402b0ec8  call    cs:__imp_ExRaiseAccessViolation
0x1402b0ecf  nop     dword ptr [rax+rax+00h]
0x1402b0ed4  nop
0x1402b0ed5  xor     eax, eax
0x1402b0ed7  jmp     short loc_1402B0EE5
0x1402b0ed9  mov     ecx, 5
0x1402b0ede  call    UserSetLastError
0x1402b0ee3  xor     eax, eax
0x1402b0ee5  add     rsp, 80h
0x1402b0eec  pop     r15
0x1402b0eee  pop     r14
0x1402b0ef0  pop     r13
0x1402b0ef2  pop     r12
0x1402b0ef4  pop     rdi
0x1402b0ef5  pop     rsi
0x1402b0ef6  pop     rbx
0x1402b0ef7  retn
0x14034930c  push    rbp
0x14034930e  sub     rsp, 20h
0x140349312  mov     rbp, rdx
0x140349315  mov     eax, 1
0x14034931a  add     rsp, 20h
0x14034931e  pop     rbp
0x14034931f  retn
```
