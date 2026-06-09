# CredStore::ResolveAlias(ushort const *,User &)

- ea: `0x1800044fc`
- end: `0x180004811`
- name: `?ResolveAlias@CredStore@@QEAAJPEBGAEAVUser@@@Z`
- size: `789`
- prototype: `int(CredStore *__hidden this, const unsigned __int16 *, struct User *)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180003310`
- `0x180023c4c`
- `0x180047ee0`

## callees

- `0x180002260`
- `0x1800044fc`
- `0x18000cc40`
- `0x18000fe50`
- `0x180011e40`
- `0x180017740`
- `0x180027910`
- `0x18003bd70`
- `0x18004f2b0`
- `0x180056144`
- `0x1800730e0`
- `0x1800829fa`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800046a3`
- `msvcrt!_wtoi` at `0x1800046a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046d5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000455f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004604`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000455f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004604`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000471e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000473d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000473d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800046c5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800046c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LSTATUS __fastcall CredStore::ResolveAlias(HKEY *this, const unsigned __int16 *a2, struct User *a3)
{
  LSTATUS result; // eax
  DWORD v7; // ecx
  unsigned __int64 v8; // r15
  __int64 v9; // r14
  wchar_t *v10; // rax
  BYTE *lpData; // rbx
  LSTATUS v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rax
  unsigned __int64 v15; // rax
  const wchar_t *v16; // rcx
  __int64 v17; // rdx
  const WCHAR *v18; // rsi
  __int64 v19; // rax
  enum _SID_NAME_USE v20; // r14d
  PSID v21; // rdi
  signed int LastError; // eax
  PSID v23; // rdi
  const wchar_t **v24; // rax
  PSID Sid; // [rsp+30h] [rbp-40h] BYREF
  const wchar_t **v26; // [rsp+38h] [rbp-38h] BYREF
  const wchar_t *v27[2]; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v28[8]; // [rsp+50h] [rbp-20h] BYREF
  HLOCAL (__stdcall *v29)(HLOCAL); // [rsp+58h] [rbp-18h]
  PSID v30; // [rsp+60h] [rbp-10h]
  DWORD cbData; // [rsp+B8h] [rbp+48h] BYREF
  DWORD Type; // [rsp+C8h] [rbp+58h] BYREF

  if ( !a2 )
    return -2147024809;
  result = CredStore::InitAliasesKey((CredStore *)this);
  if ( result >= 0 )
  {
    Type = 0;
    cbData = 0;
    result = RegQueryValueExW(this[5], a2, 0, &Type, 0, &cbData);
    if ( result )
    {
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    if ( Type != 7 )
      return -2147418113;
    v7 = cbData;
    if ( !cbData )
      return -2147418113;
    cbData += 2;
    v8 = (unsigned __int64)(v7 + 2) >> 1;
    v9 = -1;
    v10 = (wchar_t *)operator new(saturated_mul(v8, 2u));
    lpData = (BYTE *)v10;
    v27[1] = v10;
    if ( !v10 )
    {
      operator delete(0);
      return -2147024882;
    }
    memset_0(v10, 0, cbData);
    v12 = RegQueryValueExW(this[5], a2, 0, &Type, lpData, &cbData);
    v13 = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        v13 = (unsigned __int16)v12 | 0x80070000;
      goto LABEL_46;
    }
    if ( Type != 7 )
      goto LABEL_45;
    if ( !*(_WORD *)lpData )
      goto LABEL_44;
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)&lpData[2 * v14] );
    v15 = v14 + 1;
    if ( v15 >= v8 )
    {
LABEL_44:
      v13 = -2147467259;
      goto LABEL_46;
    }
    v16 = (const wchar_t *)&lpData[2 * v15];
    if ( *v16 )
    {
      v17 = -1;
      do
        ++v17;
      while ( v16[v17] );
      v15 += v17 + 1;
      if ( v15 >= v8 )
        goto LABEL_23;
    }
    else
    {
      v16 = 0;
    }
    v18 = (const WCHAR *)&lpData[2 * v15];
    if ( *v18 )
    {
      do
        ++v9;
      while ( v18[v9] );
      v15 += v9 + 1;
LABEL_24:
      v19 = 2 * v15;
      if ( v19 == cbData || v19 + 2 == cbData )
      {
        v20 = SidTypeUnknown;
        if ( v16 )
          v20 = _wtoi(v16);
        v21 = 0;
        Sid = 0;
        if ( v18 )
        {
          if ( !ConvertStringSidToSidW(v18, &Sid) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v13 = LastError;
            goto LABEL_46;
          }
          v21 = Sid;
        }
        v28[0] = 0;
        v29 = LocalFree;
        v30 = v21;
        if ( v21 )
        {
          if ( !IsValidSid(v21) )
          {
            wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(v28);
            v13 = -2147024809;
LABEL_46:
            operator delete(lpData);
            return v13;
          }
          v23 = Sid;
          if ( Sid )
          {
            _bstr_t::_bstr_t((_bstr_t *)&v26, (const unsigned __int16 *)lpData);
            v24 = User::CreateUser(v27, &v26, v20, v23, 0);
            wmi::AutoRef<User::UserEntry>::operator=(a3, *v24);
            wmi::AutoRef<User::UserEntry>::Release(v27);
            _bstr_t::~_bstr_t((_bstr_t *)&v26);
            wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(v28);
            operator delete(lpData);
            return 0;
          }
        }
        v13 = User::FromUsername(a3, (LPCWSTR)lpData);
        wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(v28);
        goto LABEL_46;
      }
LABEL_45:
      v13 = -2147418113;
      goto LABEL_46;
    }
LABEL_23:
    v18 = 0;
    goto LABEL_24;
  }
  return result;
}

```

## disassembly

```asm
0x1800044fc  mov     [rsp-38h+arg_0], rbx
0x180004501  push    rbp
0x180004502  push    rsi
0x180004503  push    rdi
0x180004504  push    r12
0x180004506  push    r13
0x180004508  push    r14
0x18000450a  push    r15
0x18000450c  mov     rbp, rsp
0x18000450f  sub     rsp, 70h
0x180004513  mov     r12, r8
0x180004516  mov     rsi, rdx
0x180004519  mov     rdi, rcx
0x18000451c  xor     r13d, r13d
0x18000451f  test    rdx, rdx
0x180004522  jnz     short loc_18000452E
0x180004524  mov     eax, 80070057h
0x180004529  jmp     loc_1800047F8
0x18000452e  call    ?InitAliasesKey@CredStore@@AEAAJXZ; CredStore::InitAliasesKey(void)
0x180004533  test    eax, eax
0x180004535  js      loc_1800047F8
0x18000453b  mov     [rbp+Type], r13d
0x18000453f  mov     [rbp+cbData], r13d
0x180004543  lea     rax, [rbp+cbData]
0x180004547  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18000454c  mov     [rsp+70h+lpData], r13; lpData
0x180004551  lea     r9, [rbp+Type]; lpType
0x180004555  xor     r8d, r8d; lpReserved
0x180004558  mov     rdx, rsi; lpValueName
0x18000455b  mov     rcx, [rdi+28h]; hKey
0x18000455f  call    cs:__imp_RegQueryValueExW
0x180004566  nop     dword ptr [rax+rax+00h]
0x18000456b  test    eax, eax
0x18000456d  jz      short loc_180004582
0x18000456f  jle     loc_1800047F8
0x180004575  movzx   eax, ax
0x180004578  or      eax, 80070000h
0x18000457d  jmp     loc_1800047F8
0x180004582  cmp     [rbp+Type], 7
0x180004586  jnz     loc_1800047F3
0x18000458c  mov     ecx, [rbp+cbData]
0x18000458f  test    ecx, ecx
0x180004591  jz      loc_1800047F3
0x180004597  mov     eax, 2
0x18000459c  add     ecx, eax
0x18000459e  mov     [rbp+cbData], ecx
0x1800045a1  mov     r15d, ecx
0x1800045a4  shr     r15, 1
0x1800045a7  mul     r15
0x1800045aa  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800045b1  cmovb   rax, r14
0x1800045b5  mov     rcx, rax; dwBytes
0x1800045b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800045bd  mov     rbx, rax
0x1800045c0  mov     [rbp+var_28], rax
0x1800045c4  test    rax, rax
0x1800045c7  jnz     short loc_1800045DA
0x1800045c9  xor     ecx, ecx; void *
0x1800045cb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800045d0  mov     eax, 8007000Eh
0x1800045d5  jmp     loc_1800047F8
0x1800045da  mov     r8d, [rbp+cbData]; Size
0x1800045de  xor     edx, edx; Val
0x1800045e0  mov     rcx, rbx; void *
0x1800045e3  call    memset_0
0x1800045e8  lea     rax, [rbp+cbData]
0x1800045ec  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800045f1  mov     [rsp+70h+lpData], rbx; lpData
0x1800045f6  lea     r9, [rbp+Type]; lpType
0x1800045fa  xor     r8d, r8d; lpReserved
0x1800045fd  mov     rdx, rsi; lpValueName
0x180004600  mov     rcx, [rdi+28h]; hKey
0x180004604  call    cs:__imp_RegQueryValueExW
0x18000460b  nop     dword ptr [rax+rax+00h]
0x180004610  mov     edi, eax
0x180004612  test    eax, eax
0x180004614  jz      short loc_18000462A
0x180004616  jle     loc_1800047E7
0x18000461c  movzx   edi, ax
0x18000461f  or      edi, 80070000h
0x180004625  jmp     loc_1800047E7
0x18000462a  cmp     [rbp+Type], 7
0x18000462e  jnz     loc_1800047E2
0x180004634  cmp     [rbx], r13w
0x180004638  jz      loc_1800047DB
0x18000463e  mov     rax, r14
0x180004641  inc     rax
0x180004644  cmp     [rbx+rax*2], r13w
0x180004649  jnz     short loc_180004641
0x18000464b  inc     rax
0x18000464e  cmp     rax, r15
0x180004651  jnb     loc_1800047DB
0x180004657  lea     rcx, [rbx+rax*2]; String
0x18000465b  cmp     [rcx], r13w
0x18000465f  jz      loc_1800046F4
0x180004665  mov     rdx, r14
0x180004668  inc     rdx
0x18000466b  cmp     [rcx+rdx*2], r13w
0x180004670  jnz     short loc_180004668
0x180004672  inc     rax
0x180004675  add     rax, rdx
0x180004678  cmp     rax, r15
0x18000467b  jb      short loc_1800046F7
0x18000467d  mov     rsi, r13
0x180004680  mov     edx, [rbp+cbData]
0x180004683  add     rax, rax
0x180004686  cmp     rax, rdx
0x180004689  jz      short loc_180004698
0x18000468b  add     rax, 2
0x18000468f  cmp     rax, rdx
0x180004692  jnz     loc_1800047E2
0x180004698  mov     r14d, 8
0x18000469e  test    rcx, rcx
0x1800046a1  jz      short loc_1800046B2
0x1800046a3  call    cs:__imp__wtoi
0x1800046aa  nop     dword ptr [rax+rax+00h]
0x1800046af  mov     r14d, eax
0x1800046b2  mov     rdi, r13
0x1800046b5  mov     [rbp+Sid], r13
0x1800046b9  test    rsi, rsi
0x1800046bc  jz      short loc_18000471E
0x1800046be  lea     rdx, [rbp+Sid]; Sid
0x1800046c2  mov     rcx, rsi; StringSid
0x1800046c5  call    cs:__imp_ConvertStringSidToSidW
0x1800046cc  nop     dword ptr [rax+rax+00h]
0x1800046d1  test    eax, eax
0x1800046d3  jnz     short loc_18000471A
0x1800046d5  call    cs:__imp_GetLastError
0x1800046dc  nop     dword ptr [rax+rax+00h]
0x1800046e1  test    eax, eax
0x1800046e3  jle     short loc_1800046ED
0x1800046e5  movzx   eax, ax
0x1800046e8  or      eax, 80070000h
0x1800046ed  mov     edi, eax
0x1800046ef  jmp     loc_1800047E7
0x1800046f4  mov     rcx, r13
0x1800046f7  lea     rsi, [rbx+rax*2]
0x1800046fb  cmp     [rsi], r13w
0x1800046ff  jz      loc_18000467D
0x180004705  inc     r14
0x180004708  cmp     [rsi+r14*2], r13w
0x18000470d  jnz     short loc_180004705
0x18000470f  inc     rax
0x180004712  add     rax, r14
0x180004715  jmp     loc_180004680
0x18000471a  mov     rdi, [rbp+Sid]
0x18000471e  mov     rax, cs:__imp_LocalFree
0x180004725  mov     [rbp+var_20], r13b
0x180004729  mov     [rbp+var_18], rax
0x18000472d  mov     [rbp+var_10], rdi
0x180004731  test    rdi, rdi
0x180004734  jz      loc_1800047C3
0x18000473a  mov     rcx, rdi; pSid
0x18000473d  call    cs:__imp_IsValidSid
0x180004744  nop     dword ptr [rax+rax+00h]
0x180004749  test    eax, eax
0x18000474b  jnz     short loc_180004760
0x18000474d  lea     rcx, [rbp+var_20]
0x180004751  call    ??1?$ScopeGuardImpl1@P6AJPEAX@ZPEAX@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(void)
0x180004756  mov     edi, 80070057h
0x18000475b  jmp     loc_1800047E7
0x180004760  mov     rdi, [rbp+Sid]
0x180004764  test    rdi, rdi
0x180004767  jz      short loc_1800047C3
0x180004769  mov     rdx, rbx; unsigned __int16 *
0x18000476c  lea     rcx, [rbp+var_38]; this
0x180004770  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180004775  nop
0x180004776  mov     byte ptr [rsp+70h+lpData], r13b
0x18000477b  mov     r9, rdi
0x18000477e  mov     r8d, r14d
0x180004781  lea     rdx, [rbp+var_38]
0x180004785  lea     rcx, [rbp+var_30]
0x180004789  call    ?CreateUser@User@@SA?AV1@AEBV_bstr_t@@W4_SID_NAME_USE@@PEAX_N@Z; User::CreateUser(_bstr_t const &,_SID_NAME_USE,void *,bool)
0x18000478e  mov     rdx, [rax]
0x180004791  mov     rcx, r12
0x180004794  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180004799  lea     rcx, [rbp+var_30]
0x18000479d  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x1800047a2  nop
0x1800047a3  lea     rcx, [rbp+var_38]; this
0x1800047a7  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800047ac  nop
0x1800047ad  lea     rcx, [rbp+var_20]
0x1800047b1  call    ??1?$ScopeGuardImpl1@P6AJPEAX@ZPEAX@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(void)
0x1800047b6  nop
0x1800047b7  mov     rcx, rbx; void *
0x1800047ba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800047bf  xor     eax, eax
0x1800047c1  jmp     short loc_1800047F8
0x1800047c3  mov     rdx, rbx; lpAccountName
0x1800047c6  mov     rcx, r12; this
0x1800047c9  call    ?FromUsername@User@@SAJAEAV1@PEBG@Z; User::FromUsername(User &,ushort const *)
0x1800047ce  mov     edi, eax
0x1800047d0  lea     rcx, [rbp+var_20]
0x1800047d4  call    ??1?$ScopeGuardImpl1@P6AJPEAX@ZPEAX@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(void)
0x1800047d9  jmp     short loc_1800047E7
0x1800047db  mov     edi, 80004005h
0x1800047e0  jmp     short loc_1800047E7
0x1800047e2  mov     edi, 8000FFFFh
0x1800047e7  mov     rcx, rbx; void *
0x1800047ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800047ef  mov     eax, edi
0x1800047f1  jmp     short loc_1800047F8
0x1800047f3  mov     eax, 8000FFFFh
0x1800047f8  mov     rbx, [rsp+70h+arg_0]
0x180004800  add     rsp, 70h
0x180004804  pop     r15
0x180004806  pop     r14
0x180004808  pop     r13
0x18000480a  pop     r12
0x18000480c  pop     rdi
0x18000480d  pop     rsi
0x18000480e  pop     rbp
0x18000480f  retn
```
