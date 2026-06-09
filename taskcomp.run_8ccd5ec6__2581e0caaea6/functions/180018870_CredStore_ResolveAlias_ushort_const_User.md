# CredStore::ResolveAlias(ushort const *,User &)

- ea: `0x180018870`
- end: `0x180018b7d`
- name: `?ResolveAlias@CredStore@@QEAAJPEBGAEAVUser@@@Z`
- size: `781`
- prototype: `int(CredStore *__hidden this, const unsigned __int16 *, struct User *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800036a0`

## callees

- `0x180003600`
- `0x1800050d0`
- `0x18000525c`
- `0x1800053bc`
- `0x1800053e8`
- `0x180007988`
- `0x180007994`
- `0x1800181ec`
- `0x18001845c`
- `0x180018870`
- `0x18001a394`
- `0x1800306c2`

## import_xrefs

- `msvcrt!_wtoi` at `0x180018a13`
- `msvcrt!_wtoi` at `0x180018a13`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180018aad`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180018aad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018a8e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800188cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018974`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800188cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018974`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180018a35`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180018a35`

## string_xrefs

- `0x1800188c1`: `AtServiceAccount`
- `0x180018969`: `AtServiceAccount`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LSTATUS __fastcall CredStore::ResolveAlias(HKEY *this, const unsigned __int16 *a2, struct User *a3)
{
  LSTATUS result; // eax
  int v6; // ecx
  unsigned __int64 v7; // rsi
  __int64 v8; // r14
  BYTE *v9; // rax
  BYTE *v10; // rbx
  LSTATUS v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rax
  unsigned __int64 v14; // rax
  const wchar_t *v15; // rcx
  __int64 v16; // rdx
  const WCHAR *v17; // rsi
  __int64 v18; // rax
  enum _SID_NAME_USE v19; // r14d
  PSID v20; // rdi
  signed int LastError; // eax
  struct _RTL_CRITICAL_SECTION *v22; // rdi
  _QWORD *User; // rax
  enum _SID_NAME_USE lpData; // [rsp+20h] [rbp-50h]
  PSID Sid; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v26[8]; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v27[8]; // [rsp+40h] [rbp-30h] BYREF
  BYTE *v28; // [rsp+48h] [rbp-28h]
  _BYTE v29[8]; // [rsp+50h] [rbp-20h] BYREF
  HLOCAL (__stdcall *v30)(HLOCAL); // [rsp+58h] [rbp-18h]
  PSID v31; // [rsp+60h] [rbp-10h]
  const unsigned __int16 *cbData; // [rsp+A8h] [rbp+38h] BYREF
  DWORD Type; // [rsp+B8h] [rbp+48h] BYREF

  cbData = a2;
  result = CredStore::InitAliasesKey((CredStore *)this);
  if ( result >= 0 )
  {
    Type = 0;
    LODWORD(cbData) = 0;
    result = RegQueryValueExW(this[5], L"AtServiceAccount", 0, &Type, 0, (LPDWORD)&cbData);
    if ( result )
    {
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    if ( Type != 7 )
      return -2147418113;
    v6 = (int)cbData;
    if ( !(_DWORD)cbData )
      return -2147418113;
    LODWORD(cbData) = (_DWORD)cbData + 2;
    v7 = (unsigned __int64)(unsigned int)(v6 + 2) >> 1;
    v8 = -1;
    v9 = (BYTE *)operator new[](saturated_mul(v7, 2u));
    v10 = v9;
    v28 = v9;
    if ( !v9 )
    {
      operator delete(0);
      return -2147024882;
    }
    memset_0(v9, 0, (unsigned int)cbData);
    v11 = RegQueryValueExW(this[5], L"AtServiceAccount", 0, &Type, v10, (LPDWORD)&cbData);
    v12 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v12 = (unsigned __int16)v11 | 0x80070000;
      goto LABEL_44;
    }
    if ( Type != 7 )
      goto LABEL_43;
    if ( !*(_WORD *)v10 )
      goto LABEL_42;
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)&v10[2 * v13] );
    v14 = v13 + 1;
    if ( v14 >= v7 )
    {
LABEL_42:
      v12 = -2147467259;
      goto LABEL_44;
    }
    v15 = (const wchar_t *)&v10[2 * v14];
    if ( *v15 )
    {
      v16 = -1;
      do
        ++v16;
      while ( v15[v16] );
      v14 += v16 + 1;
      if ( v14 >= v7 )
        goto LABEL_21;
    }
    else
    {
      v15 = 0;
    }
    v17 = (const WCHAR *)&v10[2 * v14];
    if ( *v17 )
    {
      do
        ++v8;
      while ( v17[v8] );
      v14 += v8 + 1;
LABEL_22:
      v18 = 2 * v14;
      if ( v18 == (unsigned int)cbData || v18 + 2 == (unsigned int)cbData )
      {
        v19 = SidTypeUnknown;
        if ( v15 )
          v19 = _wtoi(v15);
        v20 = 0;
        Sid = 0;
        if ( v17 )
        {
          if ( !ConvertStringSidToSidW(v17, &Sid) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v12 = LastError;
            goto LABEL_44;
          }
          v20 = Sid;
        }
        v29[0] = 0;
        v30 = LocalFree;
        v31 = v20;
        if ( v20 )
        {
          if ( !IsValidSid(v20) )
          {
            wmi::ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>(v29);
            v12 = -2147024809;
LABEL_44:
            operator delete(v10);
            return v12;
          }
          v22 = (struct _RTL_CRITICAL_SECTION *)Sid;
          if ( Sid )
          {
            _bstr_t::_bstr_t((_bstr_t *)v26, (const unsigned __int16 *)v10);
            User = (_QWORD *)User::CreateUser((__int64)v27, (const struct _bstr_t *)v26, v19, v22, lpData);
            wmi::AutoRef<User::UserEntry>::operator=(a3, *User);
            wmi::AutoRef<User::UserEntry>::Release(v27);
            _bstr_t::~_bstr_t((_bstr_t *)v26);
            wmi::ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>(v29);
            operator delete(v10);
            return 0;
          }
        }
        v12 = User::FromUsername(a3, (LPCWSTR)v10);
        wmi::ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>(v29);
        goto LABEL_44;
      }
LABEL_43:
      v12 = -2147418113;
      goto LABEL_44;
    }
LABEL_21:
    v17 = 0;
    goto LABEL_22;
  }
  return result;
}

```

## disassembly

```asm
0x180018870  mov     [rsp-28h+arg_0], rbx
0x180018875  mov     [rsp-28h+arg_10], rsi
0x18001887a  mov     [rsp-28h+cbData], rdx
0x18001887f  push    rbp
0x180018880  push    rdi
0x180018881  push    r12
0x180018883  push    r14
0x180018885  push    r15
0x180018887  mov     rbp, rsp
0x18001888a  sub     rsp, 70h
0x18001888e  mov     r15, r8
0x180018891  mov     rdi, rcx
0x180018894  call    ?InitAliasesKey@CredStore@@AEAAJXZ; CredStore::InitAliasesKey(void)
0x180018899  xor     r12d, r12d
0x18001889c  test    eax, eax
0x18001889e  js      loc_180018B63
0x1800188a4  mov     [rbp+Type], r12d
0x1800188a8  mov     dword ptr [rbp+cbData], r12d
0x1800188ac  lea     rax, [rbp+cbData]
0x1800188b0  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800188b5  mov     [rsp+70h+lpData], r12; lpData
0x1800188ba  lea     r9, [rbp+Type]; lpType
0x1800188be  xor     r8d, r8d; lpReserved
0x1800188c1  lea     rdx, ValueName; "AtServiceAccount"
0x1800188c8  mov     rcx, [rdi+28h]; hKey
0x1800188cc  call    cs:__imp_RegQueryValueExW
0x1800188d3  nop     dword ptr [rax+rax+00h]
0x1800188d8  test    eax, eax
0x1800188da  jz      short loc_1800188EF
0x1800188dc  jle     loc_180018B63
0x1800188e2  movzx   eax, ax
0x1800188e5  or      eax, 80070000h
0x1800188ea  jmp     loc_180018B63
0x1800188ef  cmp     [rbp+Type], 7
0x1800188f3  jnz     loc_180018B5E
0x1800188f9  mov     ecx, dword ptr [rbp+cbData]
0x1800188fc  test    ecx, ecx
0x1800188fe  jz      loc_180018B5E
0x180018904  mov     eax, 2
0x180018909  add     ecx, eax
0x18001890b  mov     dword ptr [rbp+cbData], ecx
0x18001890e  mov     esi, ecx
0x180018910  shr     rsi, 1
0x180018913  mul     rsi
0x180018916  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18001891d  cmovb   rax, r14
0x180018921  mov     rcx, rax; unsigned __int64
0x180018924  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180018929  mov     rbx, rax
0x18001892c  mov     [rbp+var_28], rax
0x180018930  test    rax, rax
0x180018933  jnz     short loc_180018946
0x180018935  xor     ecx, ecx; Block
0x180018937  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001893c  mov     eax, 8007000Eh
0x180018941  jmp     loc_180018B63
0x180018946  mov     r8d, dword ptr [rbp+cbData]; Size
0x18001894a  xor     edx, edx; Val
0x18001894c  mov     rcx, rbx; void *
0x18001894f  call    memset_0
0x180018954  lea     rax, [rbp+cbData]
0x180018958  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18001895d  mov     [rsp+70h+lpData], rbx; lpData
0x180018962  lea     r9, [rbp+Type]; lpType
0x180018966  xor     r8d, r8d; lpReserved
0x180018969  lea     rdx, ValueName; "AtServiceAccount"
0x180018970  mov     rcx, [rdi+28h]; hKey
0x180018974  call    cs:__imp_RegQueryValueExW
0x18001897b  nop     dword ptr [rax+rax+00h]
0x180018980  mov     edi, eax
0x180018982  test    eax, eax
0x180018984  jz      short loc_18001899A
0x180018986  jle     loc_180018B52
0x18001898c  movzx   edi, ax
0x18001898f  or      edi, 80070000h
0x180018995  jmp     loc_180018B52
0x18001899a  cmp     [rbp+Type], 7
0x18001899e  jnz     loc_180018B4D
0x1800189a4  cmp     [rbx], r12w
0x1800189a8  jz      loc_180018B46
0x1800189ae  mov     rax, r14
0x1800189b1  inc     rax
0x1800189b4  cmp     [rbx+rax*2], r12w
0x1800189b9  jnz     short loc_1800189B1
0x1800189bb  inc     rax
0x1800189be  cmp     rax, rsi
0x1800189c1  jnb     loc_180018B46
0x1800189c7  lea     rcx, [rbx+rax*2]; String
0x1800189cb  cmp     [rcx], r12w
0x1800189cf  jz      loc_180018A64
0x1800189d5  mov     rdx, r14
0x1800189d8  inc     rdx
0x1800189db  cmp     [rcx+rdx*2], r12w
0x1800189e0  jnz     short loc_1800189D8
0x1800189e2  inc     rax
0x1800189e5  add     rax, rdx
0x1800189e8  cmp     rax, rsi
0x1800189eb  jb      short loc_180018A67
0x1800189ed  mov     rsi, r12
0x1800189f0  mov     edx, dword ptr [rbp+cbData]
0x1800189f3  add     rax, rax
0x1800189f6  cmp     rax, rdx
0x1800189f9  jz      short loc_180018A08
0x1800189fb  add     rax, 2
0x1800189ff  cmp     rax, rdx
0x180018a02  jnz     loc_180018B4D
0x180018a08  mov     r14d, 8
0x180018a0e  test    rcx, rcx
0x180018a11  jz      short loc_180018A22
0x180018a13  call    cs:__imp__wtoi
0x180018a1a  nop     dword ptr [rax+rax+00h]
0x180018a1f  mov     r14d, eax
0x180018a22  mov     rdi, r12
0x180018a25  mov     [rbp+Sid], r12
0x180018a29  test    rsi, rsi
0x180018a2c  jz      short loc_180018A8E
0x180018a2e  lea     rdx, [rbp+Sid]; Sid
0x180018a32  mov     rcx, rsi; StringSid
0x180018a35  call    cs:__imp_ConvertStringSidToSidW
0x180018a3c  nop     dword ptr [rax+rax+00h]
0x180018a41  test    eax, eax
0x180018a43  jnz     short loc_180018A8A
0x180018a45  call    cs:__imp_GetLastError
0x180018a4c  nop     dword ptr [rax+rax+00h]
0x180018a51  test    eax, eax
0x180018a53  jle     short loc_180018A5D
0x180018a55  movzx   eax, ax
0x180018a58  or      eax, 80070000h
0x180018a5d  mov     edi, eax
0x180018a5f  jmp     loc_180018B52
0x180018a64  mov     rcx, r12
0x180018a67  lea     rsi, [rbx+rax*2]
0x180018a6b  cmp     [rsi], r12w
0x180018a6f  jz      loc_1800189ED
0x180018a75  inc     r14
0x180018a78  cmp     [rsi+r14*2], r12w
0x180018a7d  jnz     short loc_180018A75
0x180018a7f  inc     rax
0x180018a82  add     rax, r14
0x180018a85  jmp     loc_1800189F0
0x180018a8a  mov     rdi, [rbp+Sid]
0x180018a8e  mov     rax, cs:__imp_LocalFree
0x180018a95  mov     [rbp+var_20], r12b
0x180018a99  mov     [rbp+var_18], rax
0x180018a9d  mov     [rbp+var_10], rdi
0x180018aa1  test    rdi, rdi
0x180018aa4  jz      loc_180018B2E
0x180018aaa  mov     rcx, rdi; pSid
0x180018aad  call    cs:__imp_IsValidSid
0x180018ab4  nop     dword ptr [rax+rax+00h]
0x180018ab9  test    eax, eax
0x180018abb  jnz     short loc_180018AD0
0x180018abd  lea     rcx, [rbp+var_20]
0x180018ac1  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x180018ac6  mov     edi, 80070057h
0x180018acb  jmp     loc_180018B52
0x180018ad0  mov     rdi, [rbp+Sid]
0x180018ad4  test    rdi, rdi
0x180018ad7  jz      short loc_180018B2E
0x180018ad9  mov     rdx, rbx; unsigned __int16 *
0x180018adc  lea     rcx, [rbp+var_38]; this
0x180018ae0  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180018ae5  nop
0x180018ae6  mov     r9, rdi
0x180018ae9  mov     r8d, r14d
0x180018aec  lea     rdx, [rbp+var_38]
0x180018af0  lea     rcx, [rbp+var_30]
0x180018af4  call    ?CreateUser@User@@SA?AV1@AEBV_bstr_t@@W4_SID_NAME_USE@@PEAX_N@Z; User::CreateUser(_bstr_t const &,_SID_NAME_USE,void *,bool)
0x180018af9  mov     rdx, [rax]
0x180018afc  mov     rcx, r15
0x180018aff  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180018b04  lea     rcx, [rbp+var_30]
0x180018b08  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180018b0d  nop
0x180018b0e  lea     rcx, [rbp+var_38]; this
0x180018b12  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180018b17  nop
0x180018b18  lea     rcx, [rbp+var_20]
0x180018b1c  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x180018b21  nop
0x180018b22  mov     rcx, rbx; Block
0x180018b25  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018b2a  xor     eax, eax
0x180018b2c  jmp     short loc_180018B63
0x180018b2e  mov     rdx, rbx; lpAccountName
0x180018b31  mov     rcx, r15; this
0x180018b34  call    ?FromUsername@User@@SAJAEAV1@PEBG@Z; User::FromUsername(User &,ushort const *)
0x180018b39  mov     edi, eax
0x180018b3b  lea     rcx, [rbp+var_20]
0x180018b3f  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x180018b44  jmp     short loc_180018B52
0x180018b46  mov     edi, 80004005h
0x180018b4b  jmp     short loc_180018B52
0x180018b4d  mov     edi, 8000FFFFh
0x180018b52  mov     rcx, rbx; Block
0x180018b55  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018b5a  mov     eax, edi
0x180018b5c  jmp     short loc_180018B63
0x180018b5e  mov     eax, 8000FFFFh
0x180018b63  lea     r11, [rsp+70h+var_s0]
0x180018b68  mov     rbx, [r11+30h]
0x180018b6c  mov     rsi, [r11+40h]
0x180018b70  mov     rsp, r11
0x180018b73  pop     r15
0x180018b75  pop     r14
0x180018b77  pop     r12
0x180018b79  pop     rdi
0x180018b7a  pop     rbp
0x180018b7b  retn
```
