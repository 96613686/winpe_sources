# InitProcessUipiInfo(tagPROCESSINFO *,void *,ulong)

- ea: `0x1401c680c`
- end: `0x1401c6bfa`
- name: `?InitProcessUipiInfo@@YAJPEAUtagPROCESSINFO@@PEAXK@Z`
- size: `1006`
- prototype: `int(struct tagPROCESSINFO *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14014c4ec`

## callees

- `0x1400b1d40`
- `0x1400b22cc`
- `0x140173cc0`
- `0x14018597c`
- `0x1401c680c`
- `0x1401c6d80`
- `0x140238160`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x1401c6857`
- `ntoskrnl!SeQueryInformationToken` at `0x1401c6a48`
- `ntoskrnl!SeQueryInformationToken` at `0x1401c6857`
- `ntoskrnl!SeQueryInformationToken` at `0x1401c6a48`
- `ntoskrnl!PsIsProtectedProcess` at `0x1401c69e9`
- `ntoskrnl!PsIsProtectedProcess` at `0x1401c69e9`
- `ntoskrnl!PsGetProcessProtection` at `0x1401c69fc`
- `ntoskrnl!PsGetProcessProtection` at `0x1401c69fc`
- `WIN32K!W32GetUserSessionState` at `0x1401c68b8`
- `WIN32K!W32GetUserSessionState` at `0x1401c6984`
- `WIN32K!W32GetUserSessionState` at `0x1401c6af4`
- `WIN32K!W32GetUserSessionState` at `0x1401c6b8a`
- `WIN32K!W32GetUserSessionState` at `0x1401c68b8`
- `WIN32K!W32GetUserSessionState` at `0x1401c6984`
- `WIN32K!W32GetUserSessionState` at `0x1401c6af4`
- `WIN32K!W32GetUserSessionState` at `0x1401c6b8a`

## pseudocode

```c
__int64 __fastcall InitProcessUipiInfo(struct tagPROCESSINFO *a1, void *a2, int a3)
{
  void *v3; // rbx
  __int64 v5; // rcx
  __int64 v6; // r8
  NTSTATUS v7; // r12d
  bool v8; // di
  bool v9; // si
  int v10; // ebx
  __int64 UserSessionState; // rax
  int v12; // r8d
  int v13; // edx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // ecx
  char v19; // di
  bool v20; // r12
  bool v21; // r13
  __int64 v22; // rax
  int v23; // r8d
  int v24; // edx
  int v25; // eax
  __int64 v26; // rcx
  unsigned __int8 ProcessProtection; // al
  __int64 v28; // rdx
  __int64 v29; // r8
  bool v30; // r12
  bool v31; // si
  int v32; // ebx
  __int64 v33; // rax
  int v34; // r8d
  int v35; // edx
  bool v36; // r13
  __int64 v37; // rax
  int v38; // r8d
  int v39; // edx
  PVOID v40; // [rsp+70h] [rbp-9h] BYREF
  void *v41; // [rsp+78h] [rbp-1h]
  PVOID TokenInformation; // [rsp+80h] [rbp+7h] BYREF
  int v43; // [rsp+88h] [rbp+Fh]

  v41 = a2;
  v3 = a2;
  LODWORD(TokenInformation) = 0;
  HIDWORD(TokenInformation) = a3;
  v43 = 0;
  v7 = SeQueryInformationToken(a2, TokenIntegrityLevel, &TokenInformation);
  if ( v7 < 0 )
  {
    v8 = 0;
    if ( WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control )
    {
      v5 = *((unsigned int *)WPP_GLOBAL_Control + 11);
      if ( (v5 & 0x80u) != 0LL && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
        v8 = 1;
    }
    v9 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v10 = *((_DWORD *)a1 + 14);
      UserSessionState = W32GetUserSessionState(v5, WPP_GLOBAL_Control, v6);
      LOBYTE(v12) = v9;
      LOBYTE(v13) = v8;
      WPP_RECORDER_AND_TRACE_SF_dD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v13,
        v12,
        *(_QWORD *)(UserSessionState + 69136),
        3,
        8,
        24,
        (__int64)WPP_a173d8203b92344252851dea77c1a613_Traceguids,
        v7,
        v10);
    }
    return (unsigned int)v7;
  }
  IsEnabledDeviceUsageNoInline = Feature_UIPIDecoupleACFromIL__private_IsEnabledDeviceUsageNoInline();
  v18 = HIDWORD(TokenInformation);
  v19 = 1;
  if ( IsEnabledDeviceUsageNoInline )
  {
    if ( HIDWORD(TokenInformation) && (_DWORD)TokenInformation != 4096 )
    {
      v20 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v21 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v20 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v22 = W32GetUserSessionState(HIDWORD(TokenInformation), WPP_GLOBAL_Control, v17);
        LOBYTE(v23) = v21;
        LOBYTE(v24) = v20;
        WPP_RECORDER_AND_TRACE_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 3), v24, v23, *(_QWORD *)(v22 + 69136));
        v18 = HIDWORD(TokenInformation);
        v3 = v41;
      }
    }
    goto LABEL_22;
  }
  if ( !HIDWORD(TokenInformation) || (_DWORD)TokenInformation == 4096 )
  {
LABEL_22:
    v25 = (int)TokenInformation;
    *((_DWORD *)a1 + 217) = v18;
    v26 = *(_QWORD *)a1;
    *((_DWORD *)a1 + 216) = v25;
    if ( (unsigned int)PsIsProtectedProcess(v26) )
    {
      ProcessProtection = PsGetProcessProtection(*(_QWORD *)a1);
      *((_DWORD *)a1 + 218) = ((ProcessProtection >> 4)
                             | ((((ProcessProtection & 7) << 8) | (ProcessProtection >> 3) & 1) << 8)) << 8;
    }
    LODWORD(v40) = 0;
    if ( SeQueryInformationToken(v3, TokenDeviceClaimAttributes|TokenAuditPolicy, &v40) >= 0 && (_DWORD)v40 )
      *((_QWORD *)a1 + 101) |= 0x4000000000uLL;
    v30 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v36 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v30 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v37 = W32GetUserSessionState(WPP_GLOBAL_Control, v28, v29);
      LOBYTE(v38) = v36;
      LOBYTE(v39) = v30;
      WPP_RECORDER_AND_TRACE_SF_DDDDD(*((_QWORD *)WPP_GLOBAL_Control + 3), v39, v38, *(_QWORD *)(v37 + 69136));
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
  {
    v19 = 0;
  }
  v31 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v19 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v32 = *((_DWORD *)a1 + 14);
    v33 = W32GetUserSessionState(WPP_GLOBAL_Control, v16, v17);
    LOBYTE(v34) = v31;
    LOBYTE(v35) = v19;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v35,
      v34,
      *(_QWORD *)(v33 + 69136),
      3,
      8,
      26,
      (__int64)WPP_a173d8203b92344252851dea77c1a613_Traceguids,
      v32);
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x1401c680c  mov     [rsp-8+arg_18], rbx
0x1401c6811  push    rbp
0x1401c6812  push    rsi
0x1401c6813  push    rdi
0x1401c6814  push    r12
0x1401c6816  push    r13
0x1401c6818  push    r14
0x1401c681a  push    r15
0x1401c681c  lea     rbp, [rsp-27h]
0x1401c6821  sub     rsp, 0A0h
0x1401c6828  mov     rax, cs:__security_cookie
0x1401c682f  xor     rax, rsp
0x1401c6832  mov     [rbp+57h+var_40], rax
0x1401c6836  xor     eax, eax
0x1401c6838  mov     [rbp+57h+var_58], rdx
0x1401c683c  mov     rbx, rdx
0x1401c683f  mov     [rbp+57h+TokenInformation], rax
0x1401c6843  mov     r14, rcx
0x1401c6846  mov     dword ptr [rbp+57h+TokenInformation+4], r8d
0x1401c684a  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1401c684e  mov     [rbp+57h+var_48], eax
0x1401c6851  lea     edx, [rax+19h]; TokenInformationClass
0x1401c6854  mov     rcx, rbx; Token
0x1401c6857  call    cs:__imp_SeQueryInformationToken
0x1401c685e  nop     dword ptr [rax+rax+00h]
0x1401c6863  mov     r12d, eax
0x1401c6866  test    eax, eax
0x1401c6868  jns     loc_1401C6912
0x1401c686e  mov     rdx, cs:WPP_GLOBAL_Control
0x1401c6875  lea     rsi, WPP_GLOBAL_Control
0x1401c687c  cmp     rdx, rsi
0x1401c687f  jz      short loc_1401C6895
0x1401c6881  mov     ecx, [rdx+2Ch]
0x1401c6884  test    cl, cl
0x1401c6886  jns     short loc_1401C6895
0x1401c6888  cmp     byte ptr [rdx+29h], 3
0x1401c688c  jb      short loc_1401C6895
0x1401c688e  mov     edi, 1
0x1401c6893  jmp     short loc_1401C6898
0x1401c6895  xor     dil, dil
0x1401c6898  lea     r15, WPP_RECORDER_INITIALIZED
0x1401c689f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1401c68a6  setnz   sil
0x1401c68aa  test    dil, dil
0x1401c68ad  jnz     short loc_1401C68B4
0x1401c68af  test    sil, sil
0x1401c68b2  jz      short loc_1401C690A
0x1401c68b4  mov     ebx, [r14+38h]
0x1401c68b8  call    cs:__imp_W32GetUserSessionState
0x1401c68bf  nop     dword ptr [rax+rax+00h]
0x1401c68c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c68cb  mov     r8b, sil
0x1401c68ce  mov     [rsp+0D0h+var_88], ebx
0x1401c68d2  mov     dl, dil
0x1401c68d5  mov     [rsp+0D0h+var_90], r12d
0x1401c68da  mov     r9, [rax+10E10h]
0x1401c68e1  lea     rax, WPP_a173d8203b92344252851dea77c1a613_Traceguids
0x1401c68e8  mov     rcx, [rcx+18h]
0x1401c68ec  mov     [rsp+0D0h+var_98], rax
0x1401c68f1  mov     [rsp+0D0h+var_A0], 18h
0x1401c68f8  mov     [rsp+0D0h+var_A8], 8
0x1401c6900  mov     [rsp+0D0h+var_B0], 3
0x1401c6905  call    WPP_RECORDER_AND_TRACE_SF_dD
0x1401c690a  mov     eax, r12d
0x1401c690d  jmp     loc_1401C6BD2
0x1401c6912  call    Feature_UIPIDecoupleACFromIL__private_IsEnabledDeviceUsageNoInline
0x1401c6917  mov     ecx, dword ptr [rbp+57h+TokenInformation+4]
0x1401c691a  lea     rsi, WPP_GLOBAL_Control
0x1401c6921  lea     r15, WPP_RECORDER_INITIALIZED
0x1401c6928  mov     edi, 1
0x1401c692d  test    eax, eax
0x1401c692f  jz      loc_1401C6A9C
0x1401c6935  test    ecx, ecx
0x1401c6937  jz      loc_1401C69D5
0x1401c693d  cmp     dword ptr [rbp+57h+TokenInformation], 1000h
0x1401c6944  jz      loc_1401C69D5
0x1401c694a  mov     rdx, cs:WPP_GLOBAL_Control
0x1401c6951  cmp     rdx, rsi
0x1401c6954  jz      short loc_1401C6968
0x1401c6956  mov     eax, [rdx+2Ch]
0x1401c6959  test    al, al
0x1401c695b  jns     short loc_1401C6968
0x1401c695d  cmp     byte ptr [rdx+29h], 4
0x1401c6961  jb      short loc_1401C6968
0x1401c6963  mov     r12b, dil
0x1401c6966  jmp     short loc_1401C696B
0x1401c6968  xor     r12b, r12b
0x1401c696b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1401c6972  setnz   r13b
0x1401c6976  test    r12b, r12b
0x1401c6979  jnz     short loc_1401C6980
0x1401c697b  test    r13b, r13b
0x1401c697e  jz      short loc_1401C69D5
0x1401c6980  mov     ebx, [r14+38h]
0x1401c6984  call    cs:__imp_W32GetUserSessionState
0x1401c698b  nop     dword ptr [rax+rax+00h]
0x1401c6990  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c6997  mov     r8b, r13b
0x1401c699a  mov     dl, r12b
0x1401c699d  mov     r9, [rax+10E10h]
0x1401c69a4  mov     eax, dword ptr [rbp+57h+TokenInformation]
0x1401c69a7  mov     rcx, [rcx+18h]
0x1401c69ab  mov     [rsp+0D0h+var_80], eax
0x1401c69af  mov     eax, dword ptr [rbp+57h+TokenInformation+4]
0x1401c69b2  mov     [rsp+0D0h+var_88], eax
0x1401c69b6  mov     [rsp+0D0h+var_90], ebx
0x1401c69ba  mov     [rsp+0D0h+var_A0], 19h
0x1401c69c1  mov     [rsp+0D0h+var_A8], 8
0x1401c69c9  call    WPP_RECORDER_AND_TRACE_SF_DDD
0x1401c69ce  mov     ecx, dword ptr [rbp+57h+TokenInformation+4]
0x1401c69d1  mov     rbx, [rbp+57h+var_58]
0x1401c69d5  mov     eax, dword ptr [rbp+57h+TokenInformation]
0x1401c69d8  mov     [r14+364h], ecx
0x1401c69df  mov     rcx, [r14]
0x1401c69e2  mov     [r14+360h], eax
0x1401c69e9  call    cs:__imp_PsIsProtectedProcess
0x1401c69f0  nop     dword ptr [rax+rax+00h]
0x1401c69f5  test    eax, eax
0x1401c69f7  jz      short loc_1401C6A35
0x1401c69f9  mov     rcx, [r14]
0x1401c69fc  call    cs:__imp_PsGetProcessProtection
0x1401c6a03  nop     dword ptr [rax+rax+00h]
0x1401c6a08  movzx   edx, al
0x1401c6a0b  mov     r8d, edx
0x1401c6a0e  mov     eax, edx
0x1401c6a10  shr     r8d, 3
0x1401c6a14  and     eax, 7
0x1401c6a17  and     r8d, edi
0x1401c6a1a  shl     eax, 8
0x1401c6a1d  or      r8d, eax
0x1401c6a20  shr     edx, 4
0x1401c6a23  shl     r8d, 8
0x1401c6a27  or      r8d, edx
0x1401c6a2a  shl     r8d, 8
0x1401c6a2e  mov     [r14+368h], r8d
0x1401c6a35  lea     r8, [rbp+57h+var_60]; TokenInformation
0x1401c6a39  mov     dword ptr [rbp+57h+var_60], 0
0x1401c6a40  mov     edx, 32h ; '2'; TokenInformationClass
0x1401c6a45  mov     rcx, rbx; Token
0x1401c6a48  call    cs:__imp_SeQueryInformationToken
0x1401c6a4f  nop     dword ptr [rax+rax+00h]
0x1401c6a54  test    eax, eax
0x1401c6a56  js      short loc_1401C6A6F
0x1401c6a58  cmp     dword ptr [rbp+57h+var_60], 0
0x1401c6a5c  jz      short loc_1401C6A6F
0x1401c6a5e  mov     rax, 4000000000h
0x1401c6a68  or      [r14+328h], rax
0x1401c6a6f  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c6a76  cmp     rcx, rsi
0x1401c6a79  jz      loc_1401C6B4B
0x1401c6a7f  mov     eax, [rcx+2Ch]
0x1401c6a82  test    al, al
0x1401c6a84  jns     loc_1401C6B4B
0x1401c6a8a  cmp     byte ptr [rcx+29h], 4
0x1401c6a8e  jb      loc_1401C6B4B
0x1401c6a94  mov     r12b, dil
0x1401c6a97  jmp     loc_1401C6B4E
0x1401c6a9c  test    ecx, ecx
0x1401c6a9e  jz      loc_1401C69D5
0x1401c6aa4  cmp     dword ptr [rbp+57h+TokenInformation], 1000h
0x1401c6aab  jz      loc_1401C69D5
0x1401c6ab1  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c6ab8  lea     rsi, WPP_GLOBAL_Control
0x1401c6abf  cmp     rcx, rsi
0x1401c6ac2  jz      short loc_1401C6AD1
0x1401c6ac4  mov     eax, [rcx+2Ch]
0x1401c6ac7  test    al, al
0x1401c6ac9  jns     short loc_1401C6AD1
0x1401c6acb  cmp     byte ptr [rcx+29h], 3
0x1401c6acf  jnb     short loc_1401C6AD4
0x1401c6ad1  xor     dil, dil
0x1401c6ad4  lea     r15, WPP_RECORDER_INITIALIZED
0x1401c6adb  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1401c6ae2  setnz   sil
0x1401c6ae6  test    dil, dil
0x1401c6ae9  jnz     short loc_1401C6AF0
0x1401c6aeb  test    sil, sil
0x1401c6aee  jz      short loc_1401C6B41
0x1401c6af0  mov     ebx, [r14+38h]
0x1401c6af4  call    cs:__imp_W32GetUserSessionState
0x1401c6afb  nop     dword ptr [rax+rax+00h]
0x1401c6b00  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c6b07  mov     r8b, sil
0x1401c6b0a  mov     [rsp+0D0h+var_90], ebx
0x1401c6b0e  mov     dl, dil
0x1401c6b11  mov     r9, [rax+10E10h]
0x1401c6b18  lea     rax, WPP_a173d8203b92344252851dea77c1a613_Traceguids
0x1401c6b1f  mov     rcx, [rcx+18h]
0x1401c6b23  mov     [rsp+0D0h+var_98], rax
0x1401c6b28  mov     [rsp+0D0h+var_A0], 1Ah
0x1401c6b2f  mov     [rsp+0D0h+var_A8], 8
0x1401c6b37  mov     [rsp+0D0h+var_B0], 3
0x1401c6b3c  call    WPP_RECORDER_AND_TRACE_SF_D
0x1401c6b41  mov     eax, 0C0000001h
0x1401c6b46  jmp     loc_1401C6BD2
0x1401c6b4b  xor     r12b, r12b
0x1401c6b4e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1401c6b55  setnz   r13b
0x1401c6b59  test    r12b, r12b
0x1401c6b5c  jnz     short loc_1401C6B63
0x1401c6b5e  test    r13b, r13b
0x1401c6b61  jz      short loc_1401C6BD0
0x1401c6b63  mov     r15, [r14+328h]
0x1401c6b6a  mov     ebx, [r14+368h]
0x1401c6b71  mov     esi, [r14+360h]
0x1401c6b78  shr     r15, 26h
0x1401c6b7c  and     r15d, edi
0x1401c6b7f  mov     edi, [r14+364h]
0x1401c6b86  mov     r14d, [r14+38h]
0x1401c6b8a  call    cs:__imp_W32GetUserSessionState
0x1401c6b91  nop     dword ptr [rax+rax+00h]
0x1401c6b96  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c6b9d  mov     r8b, r13b
0x1401c6ba0  mov     [rsp+0D0h+var_70], r15d
0x1401c6ba5  mov     dl, r12b
0x1401c6ba8  mov     [rsp+0D0h+var_78], ebx
0x1401c6bac  mov     r9, [rax+10E10h]
0x1401c6bb3  mov     rcx, [rcx+18h]
0x1401c6bb7  mov     [rsp+0D0h+var_80], edi
0x1401c6bbb  mov     [rsp+0D0h+var_88], esi
0x1401c6bbf  mov     [rsp+0D0h+var_90], r14d
0x1401c6bc4  mov     [rsp+0D0h+var_A0], 1Bh
0x1401c6bcb  call    WPP_RECORDER_AND_TRACE_SF_DDDDD
0x1401c6bd0  xor     eax, eax
0x1401c6bd2  mov     rcx, [rbp+57h+var_40]
0x1401c6bd6  xor     rcx, rsp; StackCookie
0x1401c6bd9  call    __security_check_cookie
0x1401c6bde  mov     rbx, [rsp+0D0h+arg_18]
0x1401c6be6  add     rsp, 0A0h
0x1401c6bed  pop     r15
0x1401c6bef  pop     r14
0x1401c6bf1  pop     r13
0x1401c6bf3  pop     r12
0x1401c6bf5  pop     rdi
0x1401c6bf6  pop     rsi
0x1401c6bf7  pop     rbp
0x1401c6bf8  retn
```
