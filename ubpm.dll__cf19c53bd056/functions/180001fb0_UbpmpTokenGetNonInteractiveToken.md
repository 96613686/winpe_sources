# UbpmpTokenGetNonInteractiveToken

- ea: `0x180001fb0`
- end: `0x1800023c1`
- name: `UbpmpTokenGetNonInteractiveToken`
- size: `1041`
- prototype: `__int64 __fastcall(__int64, void *, __int64, const unsigned __int16 *, void **, void **)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180001e14`
- `0x180019480`
- `0x180019fb0`

## callees

- `0x180001fb0`
- `0x1800023c8`
- `0x180002964`
- `0x1800029d8`
- `0x180004240`
- `0x180019d90`
- `0x18001f764`
- `0x180034f3c`
- `0x18003d64c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180002003`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000201b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180002003`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000201b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000230c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000230c`
- `SspiCli!LogonUserExExW` at `0x1800020c1`
- `SspiCli!LogonUserExExW` at `0x1800020c1`

## string_xrefs

- `0x180002030`: `LocalService`
- `0x18000212e`: `NetworkService`

## pseudocode

```c
__int64 __fastcall UbpmpTokenGetNonInteractiveToken(
        __int64 a1,
        void *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        void **a5,
        void **a6)
{
  const unsigned __int16 *v6; // r15
  __int64 *v7; // rdi
  const unsigned __int16 *v8; // r14
  void *v12; // rbx
  const unsigned __int16 *v13; // rbx
  const unsigned __int16 *v14; // rbp
  const wchar_t *v15; // rax
  __int64 v16; // rcx
  unsigned int v17; // ecx
  const wchar_t *v18; // r8
  DWORD S4UToken; // esi
  SECURITY_LOGON_TYPE v21; // ecx
  int v22; // r8d
  int v23; // r8d
  const wchar_t *v24; // r9
  const wchar_t *v25; // rax
  const unsigned __int16 *v26; // r9
  const wchar_t *v27; // r9
  const wchar_t *v28; // r9
  int v29; // r8d
  int v30; // r8d
  const wchar_t *v31; // r9
  const wchar_t *v32; // rax
  const unsigned __int16 *v33; // [rsp+A0h] [rbp+8h] BYREF
  const unsigned __int16 *v34; // [rsp+A8h] [rbp+10h] BYREF

  v6 = 0;
  v7 = (__int64 *)(a1 + 32);
  v8 = 0;
  v34 = 0;
  v33 = 0;
  if ( a2 )
    v12 = a2;
  else
    v12 = *(void **)(*(_QWORD *)(*v7 + 8) + 8LL);
  if ( *v7 )
  {
    v14 = *(const unsigned __int16 **)(*v7 + 16);
    if ( v14 )
    {
      v13 = 0;
      goto LABEL_10;
    }
  }
  if ( EqualSid(v12, pSid2) )
  {
    v13 = L"NT AUTHORITY";
    v14 = L"NetworkService";
    goto LABEL_10;
  }
  if ( EqualSid(v12, pSid1) )
  {
    v13 = L"NT AUTHORITY";
    v14 = L"LocalService";
LABEL_10:
    v15 = 0;
    goto LABEL_11;
  }
  if ( UbpmUtilsIsServiceSid(v12) )
    return UbpmpTokenGetServiceAccountToken(v12, a5);
  UbpmUtilsGetAccountNamesFromSid((_DWORD)v12, 1, (unsigned int)&v33, (unsigned int)&v34, 0);
  v8 = v33;
  v6 = v34;
  v13 = v33;
  v14 = v34;
  if ( !*v7 )
    goto LABEL_10;
  v15 = *(const wchar_t **)(*v7 + 24);
LABEL_11:
  v16 = *v7;
  if ( (*(_DWORD *)(*v7 + 76) & 1) != 0 )
  {
    if ( a2 )
      v21 = Service;
    else
      v21 = *(_DWORD *)(v16 + 32);
    S4UToken = UbpmpTokenGetS4UToken(v14, v13, v21, a5, a6);
    if ( !S4UToken )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        if ( *v7 )
          v22 = *(_DWORD *)(*v7 + 32);
        else
          LOBYTE(v22) = 0;
        if ( v13 )
        {
          LODWORD(v28) = (_DWORD)v14;
        }
        else
        {
          v28 = L"NULL";
          v13 = L"NULL";
        }
        WPP_SF_SSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)WPP_134408c016563692a0776b6ad2359b4f_Traceguids,
          (_DWORD)v28,
          (__int64)v13,
          v22);
      }
      goto LABEL_20;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( *v7 )
        v23 = *(_DWORD *)(*v7 + 32);
      else
        v23 = 0;
      v24 = L"NULL";
      v25 = L"NULL";
      if ( v13 )
        v25 = v13;
      if ( v14 )
        v24 = v14;
      WPP_SF_dSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v23, S4UToken, (__int64)v24, (__int64)v25, v23);
    }
    v26 = L"LogonUserS4U";
  }
  else
  {
    if ( a2 )
      v17 = 5;
    else
      v17 = *(_DWORD *)(v16 + 32);
    v18 = L"_SA_{262E99C9-6160-4871-ACEC-4E61736B6F21}";
    if ( (*(_DWORD *)(*v7 + 76) & 2) == 0 )
      v18 = v15;
    if ( (unsigned int)LogonUserExExW(v14, v13, v18, v17, 0, a3, a5, a6, 0, 0, 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        if ( *v7 )
          v30 = *(_DWORD *)(*v7 + 32);
        else
          LOBYTE(v30) = 0;
        v31 = L"NULL";
        v32 = L"NULL";
        if ( v13 )
          v32 = v13;
        if ( v14 )
          LODWORD(v31) = (_DWORD)v14;
        WPP_SF_SSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)WPP_134408c016563692a0776b6ad2359b4f_Traceguids,
          (_DWORD)v31,
          (__int64)v32,
          v30);
      }
      S4UToken = 0;
      goto LABEL_20;
    }
    S4UToken = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( *v7 )
        v29 = *(_DWORD *)(*v7 + 32);
      else
        v29 = 0;
      if ( v13 )
      {
        v27 = v14;
      }
      else
      {
        v27 = L"NULL";
        v13 = L"NULL";
      }
      WPP_SF_dSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v29, S4UToken, (__int64)v27, (__int64)v13, v29);
    }
    v26 = L"LogonUserExEx";
  }
  ReportTaskEvent(g_hTaskEventManager, &LOGON_FAILURE, a4, v26, S4UToken);
LABEL_20:
  if ( v6 )
    UBPM_MIDL_user_free(v6);
  if ( v8 )
    UBPM_MIDL_user_free(v8);
  return S4UToken;
}

```

## disassembly

```asm
0x180001fb0  mov     rax, rsp
0x180001fb3  mov     [rax+18h], rbx
0x180001fb7  push    rbp
0x180001fb8  push    rsi
0x180001fb9  push    rdi
0x180001fba  push    r12
0x180001fbc  push    r13
0x180001fbe  push    r14
0x180001fc0  push    r15
0x180001fc2  sub     rsp, 60h
0x180001fc6  xor     r15d, r15d
0x180001fc9  lea     rdi, [rcx+20h]
0x180001fcd  xor     r14d, r14d
0x180001fd0  mov     [rax+10h], r15
0x180001fd4  mov     [rax+8], r14
0x180001fd8  mov     r12, r9
0x180001fdb  mov     r13, r8
0x180001fde  mov     rsi, rdx
0x180001fe1  test    rdx, rdx
0x180001fe4  jnz     short loc_180002039
0x180001fe6  mov     rax, [rdi]
0x180001fe9  mov     rcx, [rax+8]
0x180001fed  mov     rbx, [rcx+8]
0x180001ff1  mov     rbp, [rdi]
0x180001ff4  test    rbp, rbp
0x180001ff7  jnz     short loc_18000203E
0x180001ff9  mov     rdx, cs:pSid2; pSid2
0x180002000  mov     rcx, rbx; pSid1
0x180002003  call    cs:__imp_EqualSid
0x180002009  test    eax, eax
0x18000200b  jnz     loc_180002127
0x180002011  mov     rdx, cs:pSid1; pSid2
0x180002018  mov     rcx, rbx; pSid1
0x18000201b  call    cs:__imp_EqualSid
0x180002021  test    eax, eax
0x180002023  jz      loc_18000213A
0x180002029  lea     rbx, aNtAuthority; "NT AUTHORITY"
0x180002030  lea     rbp, Src; "LocalService"
0x180002037  jmp     short loc_180002049
0x180002039  mov     rbx, rsi
0x18000203c  jmp     short loc_180001FF1
0x18000203e  mov     rbp, [rbp+10h]
0x180002042  test    rbp, rbp
0x180002045  jz      short loc_180001FF9
0x180002047  xor     ebx, ebx
0x180002049  xor     eax, eax
0x18000204b  mov     rcx, [rdi]
0x18000204e  mov     edx, [rcx+4Ch]
0x180002051  test    dl, 1
0x180002054  jnz     loc_18000215E
0x18000205a  and     edx, 2
0x18000205d  test    rsi, rsi
0x180002060  jnz     loc_18000211D
0x180002066  mov     ecx, [rcx+20h]
0x180002069  mov     [rsp+98h+var_48], 0
0x180002072  lea     r8, aSa262e99c96160; "_SA_{262E99C9-6160-4871-ACEC-4E61736B6F"...
0x180002079  mov     [rsp+98h+var_50], 0
0x180002082  test    edx, edx
0x180002084  mov     [rsp+98h+var_58], 0
0x18000208d  mov     r9d, ecx
0x180002090  cmovz   r8, rax
0x180002094  mov     rdx, rbx
0x180002097  mov     rax, [rsp+98h+arg_28]
0x18000209f  mov     rcx, rbp
0x1800020a2  mov     [rsp+98h+var_60], rax
0x1800020a7  mov     rax, [rsp+98h+arg_20]
0x1800020af  mov     [rsp+98h+var_68], rax
0x1800020b4  mov     [rsp+98h+var_70], r13
0x1800020b9  mov     dword ptr [rsp+98h+var_78], 0
0x1800020c1  call    cs:__imp_LogonUserExExW
0x1800020c7  test    eax, eax
0x1800020c9  jz      loc_18000230C
0x1800020cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800020d6  lea     rax, WPP_GLOBAL_Control
0x1800020dd  cmp     rcx, rax
0x1800020e0  jz      short loc_1800020EF
0x1800020e2  test    dword ptr [rcx+1Ch], 100h
0x1800020e9  jnz     loc_18000235A
0x1800020ef  xor     esi, esi
0x1800020f1  test    r15, r15
0x1800020f4  jnz     loc_1800023A7
0x1800020fa  test    r14, r14
0x1800020fd  jnz     loc_1800023B4
0x180002103  mov     rbx, [rsp+98h+arg_10]
0x18000210b  mov     eax, esi
0x18000210d  add     rsp, 60h
0x180002111  pop     r15
0x180002113  pop     r14
0x180002115  pop     r13
0x180002117  pop     r12
0x180002119  pop     rdi
0x18000211a  pop     rsi
0x18000211b  pop     rbp
0x18000211c  retn
0x18000211d  mov     ecx, 5
0x180002122  jmp     loc_180002069
0x180002127  lea     rbx, aNtAuthority; "NT AUTHORITY"
0x18000212e  lea     rbp, aNetworkservice; "NetworkService"
0x180002135  jmp     loc_180002049
0x18000213a  mov     rcx, rbx; pSid
0x18000213d  call    ?UbpmUtilsIsServiceSid@@YAEPEAX@Z; UbpmUtilsIsServiceSid(void *)
0x180002142  mov     rcx, rbx; void *
0x180002145  test    al, al
0x180002147  jz      loc_1800021D3
0x18000214d  mov     rdx, [rsp+98h+arg_20]; void **
0x180002155  call    ?UbpmpTokenGetServiceAccountToken@@YAKPEAXPEAPEAX@Z; UbpmpTokenGetServiceAccountToken(void *,void * *)
0x18000215a  mov     esi, eax
0x18000215c  jmp     short loc_180002103
0x18000215e  test    rsi, rsi
0x180002161  jz      short loc_1800021CE
0x180002163  mov     ecx, 5
0x180002168  mov     rax, [rsp+98h+arg_28]
0x180002170  mov     r8d, ecx; LogonType
0x180002173  mov     r9, [rsp+98h+arg_20]; void **
0x18000217b  mov     rcx, rbp; Src
0x18000217e  mov     rdx, rbx; unsigned __int16 *
0x180002181  mov     [rsp+98h+var_78], rax; void **
0x180002186  call    ?UbpmpTokenGetS4UToken@@YAKPEBG0KPEAPEAX1@Z; UbpmpTokenGetS4UToken(ushort const *,ushort const *,ulong,void * *,void * *)
0x18000218b  mov     esi, eax
0x18000218d  test    eax, eax
0x18000218f  jnz     loc_18000221D
0x180002195  mov     rcx, cs:WPP_GLOBAL_Control
0x18000219c  lea     rax, WPP_GLOBAL_Control
0x1800021a3  cmp     rcx, rax
0x1800021a6  jz      loc_1800020F1
0x1800021ac  test    dword ptr [rcx+1Ch], 100h
0x1800021b3  jz      loc_1800020F1
0x1800021b9  mov     rax, [rdi]
0x1800021bc  test    rax, rax
0x1800021bf  jz      loc_1800022D1
0x1800021c5  mov     r8d, [rax+20h]
0x1800021c9  jmp     loc_1800022D4
0x1800021ce  mov     ecx, [rcx+20h]
0x1800021d1  jmp     short loc_180002168
0x1800021d3  lea     r9, [rsp+98h+arg_8]
0x1800021db  mov     [rsp+98h+var_78], r14
0x1800021e0  lea     r8, [rsp+98h+arg_0]
0x1800021e8  mov     edx, 1
0x1800021ed  call    UbpmUtilsGetAccountNamesFromSid
0x1800021f2  mov     rax, [rdi]
0x1800021f5  mov     r14, [rsp+98h+arg_0]
0x1800021fd  mov     r15, [rsp+98h+arg_8]
0x180002205  mov     rbx, r14
0x180002208  mov     rbp, r15
0x18000220b  test    rax, rax
0x18000220e  jz      loc_180002049
0x180002214  mov     rax, [rax+18h]
0x180002218  jmp     loc_18000204B
0x18000221d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002224  lea     rax, WPP_GLOBAL_Control
0x18000222b  cmp     rcx, rax
0x18000222e  jz      short loc_18000227F
0x180002230  test    byte ptr [rcx+1Ch], 1
0x180002234  jz      short loc_18000227F
0x180002236  mov     rax, [rdi]
0x180002239  test    rax, rax
0x18000223c  jz      short loc_180002244
0x18000223e  mov     r8d, [rax+20h]
0x180002242  jmp     short loc_180002247
0x180002244  xor     r8d, r8d
0x180002247  mov     rcx, [rcx+10h]
0x18000224b  lea     r9, aNull_0; "NULL"
0x180002252  mov     rax, r9
0x180002255  mov     dword ptr [rsp+98h+var_68], r8d
0x18000225a  test    rbx, rbx
0x18000225d  mov     edx, 1Ch
0x180002262  cmovnz  rax, rbx
0x180002266  test    rbp, rbp
0x180002269  mov     [rsp+98h+var_70], rax
0x18000226e  cmovnz  r9, rbp
0x180002272  mov     [rsp+98h+var_78], r9
0x180002277  mov     r9d, esi
0x18000227a  call    WPP_SF_dSSd
0x18000227f  lea     r9, aLogonusers4u; "LogonUserS4U"
0x180002286  jmp     short loc_1800022B2
0x180002288  mov     r9, rbp
0x18000228b  mov     rcx, [rcx+10h]
0x18000228f  mov     edx, 1Eh
0x180002294  mov     dword ptr [rsp+98h+var_68], r8d
0x180002299  mov     [rsp+98h+var_70], rbx
0x18000229e  mov     [rsp+98h+var_78], r9
0x1800022a3  mov     r9d, esi
0x1800022a6  call    WPP_SF_dSSd
0x1800022ab  lea     r9, aLogonuserexex; "LogonUserExEx"
0x1800022b2  mov     rcx, cs:g_hTaskEventManager; void *
0x1800022b9  lea     rdx, LOGON_FAILURE; struct _EVENT_DESCRIPTOR *
0x1800022c0  mov     r8, r12; unsigned __int16 *
0x1800022c3  mov     dword ptr [rsp+98h+var_78], esi; unsigned int
0x1800022c7  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBG2K@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ulong)
0x1800022cc  jmp     loc_1800020F1
0x1800022d1  xor     r8d, r8d
0x1800022d4  test    rbx, rbx
0x1800022d7  jnz     short loc_1800022E5
0x1800022d9  lea     r9, aNull_0; "NULL"
0x1800022e0  mov     rbx, r9
0x1800022e3  jmp     short loc_1800022E8
0x1800022e5  mov     r9, rbp
0x1800022e8  mov     rcx, [rcx+10h]
0x1800022ec  mov     edx, 1Dh
0x1800022f1  mov     dword ptr [rsp+98h+var_70], r8d
0x1800022f6  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x1800022fd  mov     [rsp+98h+var_78], rbx
0x180002302  call    WPP_SF_SSd
0x180002307  jmp     loc_1800020F1
0x18000230c  call    cs:__imp_GetLastError
0x180002312  mov     esi, eax
0x180002314  mov     rcx, cs:WPP_GLOBAL_Control
0x18000231b  lea     rax, WPP_GLOBAL_Control
0x180002322  cmp     rcx, rax
0x180002325  jz      short loc_1800022AB
0x180002327  test    byte ptr [rcx+1Ch], 1
0x18000232b  jz      loc_1800022AB
0x180002331  mov     rax, [rdi]
0x180002334  test    rax, rax
0x180002337  jz      short loc_18000233F
0x180002339  mov     r8d, [rax+20h]
0x18000233d  jmp     short loc_180002342
0x18000233f  xor     r8d, r8d
0x180002342  test    rbx, rbx
0x180002345  jnz     loc_180002288
0x18000234b  lea     r9, aNull_0; "NULL"
0x180002352  mov     rbx, r9
0x180002355  jmp     loc_18000228B
0x18000235a  mov     rax, [rdi]
0x18000235d  test    rax, rax
0x180002360  jz      short loc_180002368
0x180002362  mov     r8d, [rax+20h]
0x180002366  jmp     short loc_18000236B
0x180002368  xor     r8d, r8d
0x18000236b  mov     rcx, [rcx+10h]
0x18000236f  lea     r9, aNull_0; "NULL"
0x180002376  test    rbx, rbx
0x180002379  mov     dword ptr [rsp+98h+var_70], r8d
0x18000237e  mov     rax, r9
0x180002381  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180002388  cmovnz  rax, rbx
0x18000238c  mov     edx, 1Fh
0x180002391  test    rbp, rbp
0x180002394  mov     [rsp+98h+var_78], rax
0x180002399  cmovnz  r9, rbp
0x18000239d  call    WPP_SF_SSd
0x1800023a2  jmp     loc_1800020EF
0x1800023a7  mov     rcx, r15
0x1800023aa  call    UBPM_MIDL_user_free
0x1800023af  jmp     loc_1800020FA
0x1800023b4  mov     rcx, r14
0x1800023b7  call    UBPM_MIDL_user_free
0x1800023bc  jmp     loc_180002103
```
