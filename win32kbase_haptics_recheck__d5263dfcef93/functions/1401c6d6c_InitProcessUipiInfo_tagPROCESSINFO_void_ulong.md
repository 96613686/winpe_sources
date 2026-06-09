# InitProcessUipiInfo(tagPROCESSINFO *,void *,ulong)

- ea: `0x1401c6d6c`
- end: `0x1401c715a`
- name: `?InitProcessUipiInfo@@YAJPEAUtagPROCESSINFO@@PEAXK@Z`
- size: `1006`
- prototype: `int(struct tagPROCESSINFO *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400b471c`

## callees

- `0x1400cb450`
- `0x1400cb9dc`
- `0x140172fa0`
- `0x14018481c`
- `0x1401c6d6c`
- `0x1401c72e0`
- `0x140238b10`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x1401c6db7`
- `ntoskrnl!SeQueryInformationToken` at `0x1401c6fa8`
- `ntoskrnl!SeQueryInformationToken` at `0x1401c6db7`
- `ntoskrnl!SeQueryInformationToken` at `0x1401c6fa8`
- `ntoskrnl!PsIsProtectedProcess` at `0x1401c6f49`
- `ntoskrnl!PsIsProtectedProcess` at `0x1401c6f49`
- `ntoskrnl!PsGetProcessProtection` at `0x1401c6f5c`
- `ntoskrnl!PsGetProcessProtection` at `0x1401c6f5c`
- `WIN32K!W32GetUserSessionState` at `0x1401c6e18`
- `WIN32K!W32GetUserSessionState` at `0x1401c6ee4`
- `WIN32K!W32GetUserSessionState` at `0x1401c7054`
- `WIN32K!W32GetUserSessionState` at `0x1401c70ea`
- `WIN32K!W32GetUserSessionState` at `0x1401c6e18`
- `WIN32K!W32GetUserSessionState` at `0x1401c6ee4`
- `WIN32K!W32GetUserSessionState` at `0x1401c7054`
- `WIN32K!W32GetUserSessionState` at `0x1401c70ea`

## pseudocode

```c
__int64 __fastcall InitProcessUipiInfo(struct tagPROCESSINFO *a1, void *a2, int a3)
{
  void *v3; // rbx
  __int64 v5; // rcx
  NTSTATUS v6; // r12d
  bool v7; // di
  bool v8; // si
  int v9; // ebx
  __int64 UserSessionState; // rax
  int v11; // r8d
  int v12; // edx
  int IsEnabledDeviceUsageNoInline; // eax
  int v15; // ecx
  char v16; // di
  bool v17; // r12
  bool v18; // r13
  __int64 v19; // rax
  int v20; // r8d
  int v21; // edx
  int v22; // eax
  __int64 v23; // rcx
  unsigned __int8 ProcessProtection; // al
  bool v25; // r12
  bool v26; // si
  int v27; // ebx
  __int64 v28; // rax
  int v29; // r8d
  int v30; // edx
  bool v31; // r13
  __int64 v32; // rax
  int v33; // r8d
  int v34; // edx
  PVOID v35; // [rsp+70h] [rbp-9h] BYREF
  void *v36; // [rsp+78h] [rbp-1h]
  PVOID TokenInformation; // [rsp+80h] [rbp+7h] BYREF
  int v38; // [rsp+88h] [rbp+Fh]

  v36 = a2;
  v3 = a2;
  LODWORD(TokenInformation) = 0;
  HIDWORD(TokenInformation) = a3;
  v38 = 0;
  v6 = SeQueryInformationToken(a2, TokenIntegrityLevel, &TokenInformation);
  if ( v6 < 0 )
  {
    v7 = 0;
    if ( WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control )
    {
      v5 = *((unsigned int *)WPP_GLOBAL_Control + 11);
      if ( (v5 & 0x80u) != 0LL && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
        v7 = 1;
    }
    v8 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = *((_DWORD *)a1 + 14);
      UserSessionState = W32GetUserSessionState(v5);
      LOBYTE(v11) = v8;
      LOBYTE(v12) = v7;
      WPP_RECORDER_AND_TRACE_SF_dD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v12,
        v11,
        *(_QWORD *)(UserSessionState + 69136),
        3,
        8,
        24,
        (__int64)WPP_a173d8203b92344252851dea77c1a613_Traceguids,
        v6,
        v9);
    }
    return (unsigned int)v6;
  }
  IsEnabledDeviceUsageNoInline = Feature_UIPIDecoupleACFromIL__private_IsEnabledDeviceUsageNoInline();
  v15 = HIDWORD(TokenInformation);
  v16 = 1;
  if ( IsEnabledDeviceUsageNoInline )
  {
    if ( HIDWORD(TokenInformation) && (_DWORD)TokenInformation != 4096 )
    {
      v17 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v18 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v17 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v19 = W32GetUserSessionState(HIDWORD(TokenInformation));
        LOBYTE(v20) = v18;
        LOBYTE(v21) = v17;
        WPP_RECORDER_AND_TRACE_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 3), v21, v20, *(_QWORD *)(v19 + 69136));
        v15 = HIDWORD(TokenInformation);
        v3 = v36;
      }
    }
    goto LABEL_22;
  }
  if ( !HIDWORD(TokenInformation) || (_DWORD)TokenInformation == 4096 )
  {
LABEL_22:
    v22 = (int)TokenInformation;
    *((_DWORD *)a1 + 217) = v15;
    v23 = *(_QWORD *)a1;
    *((_DWORD *)a1 + 216) = v22;
    if ( (unsigned int)PsIsProtectedProcess(v23) )
    {
      ProcessProtection = PsGetProcessProtection(*(_QWORD *)a1);
      *((_DWORD *)a1 + 218) = ((ProcessProtection >> 4)
                             | ((((ProcessProtection & 7) << 8) | (ProcessProtection >> 3) & 1) << 8)) << 8;
    }
    LODWORD(v35) = 0;
    if ( SeQueryInformationToken(v3, TokenDeviceClaimAttributes|TokenAuditPolicy, &v35) >= 0 && (_DWORD)v35 )
      *((_QWORD *)a1 + 101) |= 0x4000000000uLL;
    v25 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v31 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v25 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v32 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v33) = v31;
      LOBYTE(v34) = v25;
      WPP_RECORDER_AND_TRACE_SF_DDDDD(*((_QWORD *)WPP_GLOBAL_Control + 3), v34, v33, *(_QWORD *)(v32 + 69136));
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
  {
    v16 = 0;
  }
  v26 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v16 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v27 = *((_DWORD *)a1 + 14);
    v28 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v29) = v26;
    LOBYTE(v30) = v16;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v30,
      v29,
      *(_QWORD *)(v28 + 69136),
      3,
      8,
      26,
      (__int64)WPP_a173d8203b92344252851dea77c1a613_Traceguids,
      v27);
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x1401c6d6c  mov     [rsp-8+arg_18], rbx
0x1401c6d71  push    rbp
0x1401c6d72  push    rsi
0x1401c6d73  push    rdi
0x1401c6d74  push    r12
0x1401c6d76  push    r13
0x1401c6d78  push    r14
0x1401c6d7a  push    r15
0x1401c6d7c  lea     rbp, [rsp-27h]
0x1401c6d81  sub     rsp, 0A0h
0x1401c6d88  mov     rax, cs:__security_cookie
0x1401c6d8f  xor     rax, rsp
0x1401c6d92  mov     [rbp+57h+var_40], rax
0x1401c6d96  xor     eax, eax
0x1401c6d98  mov     [rbp+57h+var_58], rdx
0x1401c6d9c  mov     rbx, rdx
0x1401c6d9f  mov     [rbp+57h+TokenInformation], rax
0x1401c6da3  mov     r14, rcx
0x1401c6da6  mov     dword ptr [rbp+57h+TokenInformation+4], r8d
0x1401c6daa  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1401c6dae  mov     [rbp+57h+var_48], eax
0x1401c6db1  lea     edx, [rax+19h]; TokenInformationClass
0x1401c6db4  mov     rcx, rbx; Token
0x1401c6db7  call    cs:__imp_SeQueryInformationToken
0x1401c6dbe  nop     dword ptr [rax+rax+00h]
0x1401c6dc3  mov     r12d, eax
0x1401c6dc6  test    eax, eax
0x1401c6dc8  jns     loc_1401C6E72
0x1401c6dce  mov     rdx, cs:WPP_GLOBAL_Control
0x1401c6dd5  lea     rsi, WPP_GLOBAL_Control
0x1401c6ddc  cmp     rdx, rsi
0x1401c6ddf  jz      short loc_1401C6DF5
0x1401c6de1  mov     ecx, [rdx+2Ch]
0x1401c6de4  test    cl, cl
0x1401c6de6  jns     short loc_1401C6DF5
0x1401c6de8  cmp     byte ptr [rdx+29h], 3
0x1401c6dec  jb      short loc_1401C6DF5
0x1401c6dee  mov     edi, 1
0x1401c6df3  jmp     short loc_1401C6DF8
0x1401c6df5  xor     dil, dil
0x1401c6df8  lea     r15, WPP_RECORDER_INITIALIZED
0x1401c6dff  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1401c6e06  setnz   sil
0x1401c6e0a  test    dil, dil
0x1401c6e0d  jnz     short loc_1401C6E14
0x1401c6e0f  test    sil, sil
0x1401c6e12  jz      short loc_1401C6E6A
0x1401c6e14  mov     ebx, [r14+38h]
0x1401c6e18  call    cs:__imp_W32GetUserSessionState
0x1401c6e1f  nop     dword ptr [rax+rax+00h]
0x1401c6e24  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c6e2b  mov     r8b, sil
0x1401c6e2e  mov     [rsp+0D0h+var_88], ebx
0x1401c6e32  mov     dl, dil
0x1401c6e35  mov     [rsp+0D0h+var_90], r12d
0x1401c6e3a  mov     r9, [rax+10E10h]
0x1401c6e41  lea     rax, WPP_a173d8203b92344252851dea77c1a613_Traceguids
0x1401c6e48  mov     rcx, [rcx+18h]
0x1401c6e4c  mov     [rsp+0D0h+var_98], rax
0x1401c6e51  mov     [rsp+0D0h+var_A0], 18h
0x1401c6e58  mov     [rsp+0D0h+var_A8], 8
0x1401c6e60  mov     [rsp+0D0h+var_B0], 3
0x1401c6e65  call    WPP_RECORDER_AND_TRACE_SF_dD
0x1401c6e6a  mov     eax, r12d
0x1401c6e6d  jmp     loc_1401C7132
0x1401c6e72  call    Feature_UIPIDecoupleACFromIL__private_IsEnabledDeviceUsageNoInline
0x1401c6e77  mov     ecx, dword ptr [rbp+57h+TokenInformation+4]
0x1401c6e7a  lea     rsi, WPP_GLOBAL_Control
0x1401c6e81  lea     r15, WPP_RECORDER_INITIALIZED
0x1401c6e88  mov     edi, 1
0x1401c6e8d  test    eax, eax
0x1401c6e8f  jz      loc_1401C6FFC
0x1401c6e95  test    ecx, ecx
0x1401c6e97  jz      loc_1401C6F35
0x1401c6e9d  cmp     dword ptr [rbp+57h+TokenInformation], 1000h
0x1401c6ea4  jz      loc_1401C6F35
0x1401c6eaa  mov     rdx, cs:WPP_GLOBAL_Control
0x1401c6eb1  cmp     rdx, rsi
0x1401c6eb4  jz      short loc_1401C6EC8
0x1401c6eb6  mov     eax, [rdx+2Ch]
0x1401c6eb9  test    al, al
0x1401c6ebb  jns     short loc_1401C6EC8
0x1401c6ebd  cmp     byte ptr [rdx+29h], 4
0x1401c6ec1  jb      short loc_1401C6EC8
0x1401c6ec3  mov     r12b, dil
0x1401c6ec6  jmp     short loc_1401C6ECB
0x1401c6ec8  xor     r12b, r12b
0x1401c6ecb  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1401c6ed2  setnz   r13b
0x1401c6ed6  test    r12b, r12b
0x1401c6ed9  jnz     short loc_1401C6EE0
0x1401c6edb  test    r13b, r13b
0x1401c6ede  jz      short loc_1401C6F35
0x1401c6ee0  mov     ebx, [r14+38h]
0x1401c6ee4  call    cs:__imp_W32GetUserSessionState
0x1401c6eeb  nop     dword ptr [rax+rax+00h]
0x1401c6ef0  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c6ef7  mov     r8b, r13b
0x1401c6efa  mov     dl, r12b
0x1401c6efd  mov     r9, [rax+10E10h]
0x1401c6f04  mov     eax, dword ptr [rbp+57h+TokenInformation]
0x1401c6f07  mov     rcx, [rcx+18h]
0x1401c6f0b  mov     [rsp+0D0h+var_80], eax
0x1401c6f0f  mov     eax, dword ptr [rbp+57h+TokenInformation+4]
0x1401c6f12  mov     [rsp+0D0h+var_88], eax
0x1401c6f16  mov     [rsp+0D0h+var_90], ebx
0x1401c6f1a  mov     [rsp+0D0h+var_A0], 19h
0x1401c6f21  mov     [rsp+0D0h+var_A8], 8
0x1401c6f29  call    WPP_RECORDER_AND_TRACE_SF_DDD
0x1401c6f2e  mov     ecx, dword ptr [rbp+57h+TokenInformation+4]
0x1401c6f31  mov     rbx, [rbp+57h+var_58]
0x1401c6f35  mov     eax, dword ptr [rbp+57h+TokenInformation]
0x1401c6f38  mov     [r14+364h], ecx
0x1401c6f3f  mov     rcx, [r14]
0x1401c6f42  mov     [r14+360h], eax
0x1401c6f49  call    cs:__imp_PsIsProtectedProcess
0x1401c6f50  nop     dword ptr [rax+rax+00h]
0x1401c6f55  test    eax, eax
0x1401c6f57  jz      short loc_1401C6F95
0x1401c6f59  mov     rcx, [r14]
0x1401c6f5c  call    cs:__imp_PsGetProcessProtection
0x1401c6f63  nop     dword ptr [rax+rax+00h]
0x1401c6f68  movzx   edx, al
0x1401c6f6b  mov     r8d, edx
0x1401c6f6e  mov     eax, edx
0x1401c6f70  shr     r8d, 3
0x1401c6f74  and     eax, 7
0x1401c6f77  and     r8d, edi
0x1401c6f7a  shl     eax, 8
0x1401c6f7d  or      r8d, eax
0x1401c6f80  shr     edx, 4
0x1401c6f83  shl     r8d, 8
0x1401c6f87  or      r8d, edx
0x1401c6f8a  shl     r8d, 8
0x1401c6f8e  mov     [r14+368h], r8d
0x1401c6f95  lea     r8, [rbp+57h+var_60]; TokenInformation
0x1401c6f99  mov     dword ptr [rbp+57h+var_60], 0
0x1401c6fa0  mov     edx, 32h ; '2'; TokenInformationClass
0x1401c6fa5  mov     rcx, rbx; Token
0x1401c6fa8  call    cs:__imp_SeQueryInformationToken
0x1401c6faf  nop     dword ptr [rax+rax+00h]
0x1401c6fb4  test    eax, eax
0x1401c6fb6  js      short loc_1401C6FCF
0x1401c6fb8  cmp     dword ptr [rbp+57h+var_60], 0
0x1401c6fbc  jz      short loc_1401C6FCF
0x1401c6fbe  mov     rax, 4000000000h
0x1401c6fc8  or      [r14+328h], rax
0x1401c6fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c6fd6  cmp     rcx, rsi
0x1401c6fd9  jz      loc_1401C70AB
0x1401c6fdf  mov     eax, [rcx+2Ch]
0x1401c6fe2  test    al, al
0x1401c6fe4  jns     loc_1401C70AB
0x1401c6fea  cmp     byte ptr [rcx+29h], 4
0x1401c6fee  jb      loc_1401C70AB
0x1401c6ff4  mov     r12b, dil
0x1401c6ff7  jmp     loc_1401C70AE
0x1401c6ffc  test    ecx, ecx
0x1401c6ffe  jz      loc_1401C6F35
0x1401c7004  cmp     dword ptr [rbp+57h+TokenInformation], 1000h
0x1401c700b  jz      loc_1401C6F35
0x1401c7011  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c7018  lea     rsi, WPP_GLOBAL_Control
0x1401c701f  cmp     rcx, rsi
0x1401c7022  jz      short loc_1401C7031
0x1401c7024  mov     eax, [rcx+2Ch]
0x1401c7027  test    al, al
0x1401c7029  jns     short loc_1401C7031
0x1401c702b  cmp     byte ptr [rcx+29h], 3
0x1401c702f  jnb     short loc_1401C7034
0x1401c7031  xor     dil, dil
0x1401c7034  lea     r15, WPP_RECORDER_INITIALIZED
0x1401c703b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1401c7042  setnz   sil
0x1401c7046  test    dil, dil
0x1401c7049  jnz     short loc_1401C7050
0x1401c704b  test    sil, sil
0x1401c704e  jz      short loc_1401C70A1
0x1401c7050  mov     ebx, [r14+38h]
0x1401c7054  call    cs:__imp_W32GetUserSessionState
0x1401c705b  nop     dword ptr [rax+rax+00h]
0x1401c7060  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c7067  mov     r8b, sil
0x1401c706a  mov     [rsp+0D0h+var_90], ebx
0x1401c706e  mov     dl, dil
0x1401c7071  mov     r9, [rax+10E10h]
0x1401c7078  lea     rax, WPP_a173d8203b92344252851dea77c1a613_Traceguids
0x1401c707f  mov     rcx, [rcx+18h]
0x1401c7083  mov     [rsp+0D0h+var_98], rax
0x1401c7088  mov     [rsp+0D0h+var_A0], 1Ah
0x1401c708f  mov     [rsp+0D0h+var_A8], 8
0x1401c7097  mov     [rsp+0D0h+var_B0], 3
0x1401c709c  call    WPP_RECORDER_AND_TRACE_SF_D
0x1401c70a1  mov     eax, 0C0000001h
0x1401c70a6  jmp     loc_1401C7132
0x1401c70ab  xor     r12b, r12b
0x1401c70ae  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1401c70b5  setnz   r13b
0x1401c70b9  test    r12b, r12b
0x1401c70bc  jnz     short loc_1401C70C3
0x1401c70be  test    r13b, r13b
0x1401c70c1  jz      short loc_1401C7130
0x1401c70c3  mov     r15, [r14+328h]
0x1401c70ca  mov     ebx, [r14+368h]
0x1401c70d1  mov     esi, [r14+360h]
0x1401c70d8  shr     r15, 26h
0x1401c70dc  and     r15d, edi
0x1401c70df  mov     edi, [r14+364h]
0x1401c70e6  mov     r14d, [r14+38h]
0x1401c70ea  call    cs:__imp_W32GetUserSessionState
0x1401c70f1  nop     dword ptr [rax+rax+00h]
0x1401c70f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c70fd  mov     r8b, r13b
0x1401c7100  mov     [rsp+0D0h+var_70], r15d
0x1401c7105  mov     dl, r12b
0x1401c7108  mov     [rsp+0D0h+var_78], ebx
0x1401c710c  mov     r9, [rax+10E10h]
0x1401c7113  mov     rcx, [rcx+18h]
0x1401c7117  mov     [rsp+0D0h+var_80], edi
0x1401c711b  mov     [rsp+0D0h+var_88], esi
0x1401c711f  mov     [rsp+0D0h+var_90], r14d
0x1401c7124  mov     [rsp+0D0h+var_A0], 1Bh
0x1401c712b  call    WPP_RECORDER_AND_TRACE_SF_DDDDD
0x1401c7130  xor     eax, eax
0x1401c7132  mov     rcx, [rbp+57h+var_40]
0x1401c7136  xor     rcx, rsp; StackCookie
0x1401c7139  call    __security_check_cookie
0x1401c713e  mov     rbx, [rsp+0D0h+arg_18]
0x1401c7146  add     rsp, 0A0h
0x1401c714d  pop     r15
0x1401c714f  pop     r14
0x1401c7151  pop     r13
0x1401c7153  pop     r12
0x1401c7155  pop     rdi
0x1401c7156  pop     rsi
0x1401c7157  pop     rbp
0x1401c7158  retn
```
