# CredStore::ResolveAlias(ushort const *,User &)

- ea: `0x1800177d0`
- end: `0x180017aac`
- name: `?ResolveAlias@CredStore@@QEAAJPEBGAEAVUser@@@Z`
- size: `732`
- prototype: `int(CredStore *__hidden this, const unsigned __int16 *, struct User *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180003500`

## callees

- `0x180003470`
- `0x180004e50`
- `0x180004fbc`
- `0x1800050fc`
- `0x18000518c`
- `0x1800074c8`
- `0x1800074d4`
- `0x180017210`
- `0x180017454`
- `0x1800177d0`
- `0x180019168`
- `0x18002e572`

## import_xrefs

- `msvcrt!_wtoi` at `0x180017963`
- `msvcrt!_wtoi` at `0x180017963`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800179e3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800179e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017989`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017989`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800179c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001782c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800178ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001782c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800178ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001797f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001797f`

## string_xrefs

- `0x180017821`: `AtServiceAccount`
- `0x1800178c3`: `AtServiceAccount`

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
  _QWORD *v23; // rax
  enum _SID_NAME_USE lpData; // [rsp+20h] [rbp-50h]
  PSID Sid; // [rsp+30h] [rbp-40h] BYREF
  __int64 *v26; // [rsp+38h] [rbp-38h] BYREF
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
            wmi::ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>((__int64)v29);
            v12 = -2147024809;
LABEL_44:
            operator delete(v10);
            return v12;
          }
          v22 = (struct _RTL_CRITICAL_SECTION *)Sid;
          if ( Sid )
          {
            _bstr_t::_bstr_t((_bstr_t *)&v26, (const unsigned __int16 *)v10);
            v23 = (_QWORD *)User::CreateUser((__int64)v27, &v26, v19, v22, lpData);
            wmi::AutoRef<User::UserEntry>::operator=(a3, *v23);
            wmi::AutoRef<User::UserEntry>::Release(v27);
            _bstr_t::~_bstr_t((_bstr_t *)&v26);
            wmi::ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>((__int64)v29);
            operator delete(v10);
            return 0;
          }
        }
        v12 = User::FromUsername(a3, (LPCWSTR)v10);
        wmi::ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>((__int64)v29);
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
0x1800177d0  mov     [rsp-28h+arg_0], rbx
0x1800177d5  mov     [rsp-28h+arg_10], rsi
0x1800177da  mov     [rsp-28h+cbData], rdx
0x1800177df  push    rbp
0x1800177e0  push    rdi
0x1800177e1  push    r12
0x1800177e3  push    r14
0x1800177e5  push    r15
0x1800177e7  mov     rbp, rsp
0x1800177ea  sub     rsp, 70h
0x1800177ee  mov     r15, r8
0x1800177f1  mov     rdi, rcx
0x1800177f4  call    ?InitAliasesKey@CredStore@@AEAAJXZ; CredStore::InitAliasesKey(void)
0x1800177f9  xor     r12d, r12d
0x1800177fc  test    eax, eax
0x1800177fe  js      loc_180017A93
0x180017804  mov     [rbp+Type], r12d
0x180017808  mov     dword ptr [rbp+cbData], r12d
0x18001780c  lea     rax, [rbp+cbData]
0x180017810  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180017815  mov     [rsp+70h+lpData], r12; lpData
0x18001781a  lea     r9, [rbp+Type]; lpType
0x18001781e  xor     r8d, r8d; lpReserved
0x180017821  lea     rdx, ValueName; "AtServiceAccount"
0x180017828  mov     rcx, [rdi+28h]; hKey
0x18001782c  call    cs:__imp_RegQueryValueExW
0x180017832  test    eax, eax
0x180017834  jz      short loc_180017849
0x180017836  jle     loc_180017A93
0x18001783c  movzx   eax, ax
0x18001783f  or      eax, 80070000h
0x180017844  jmp     loc_180017A93
0x180017849  cmp     [rbp+Type], 7
0x18001784d  jnz     loc_180017A8E
0x180017853  mov     ecx, dword ptr [rbp+cbData]
0x180017856  test    ecx, ecx
0x180017858  jz      loc_180017A8E
0x18001785e  mov     eax, 2
0x180017863  add     ecx, eax
0x180017865  mov     dword ptr [rbp+cbData], ecx
0x180017868  mov     esi, ecx
0x18001786a  shr     rsi, 1
0x18001786d  mul     rsi
0x180017870  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180017877  cmovb   rax, r14
0x18001787b  mov     rcx, rax; unsigned __int64
0x18001787e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180017883  mov     rbx, rax
0x180017886  mov     [rbp+var_28], rax
0x18001788a  test    rax, rax
0x18001788d  jnz     short loc_1800178A0
0x18001788f  xor     ecx, ecx; Block
0x180017891  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017896  mov     eax, 8007000Eh
0x18001789b  jmp     loc_180017A93
0x1800178a0  mov     r8d, dword ptr [rbp+cbData]; Size
0x1800178a4  xor     edx, edx; Val
0x1800178a6  mov     rcx, rbx; void *
0x1800178a9  call    memset_0
0x1800178ae  lea     rax, [rbp+cbData]
0x1800178b2  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800178b7  mov     [rsp+70h+lpData], rbx; lpData
0x1800178bc  lea     r9, [rbp+Type]; lpType
0x1800178c0  xor     r8d, r8d; lpReserved
0x1800178c3  lea     rdx, ValueName; "AtServiceAccount"
0x1800178ca  mov     rcx, [rdi+28h]; hKey
0x1800178ce  call    cs:__imp_RegQueryValueExW
0x1800178d4  mov     edi, eax
0x1800178d6  test    eax, eax
0x1800178d8  jz      short loc_1800178EE
0x1800178da  jle     loc_180017A82
0x1800178e0  movzx   edi, ax
0x1800178e3  or      edi, 80070000h
0x1800178e9  jmp     loc_180017A82
0x1800178ee  cmp     [rbp+Type], 7
0x1800178f2  jnz     loc_180017A7D
0x1800178f8  cmp     [rbx], r12w
0x1800178fc  jz      loc_180017A76
0x180017902  mov     rax, r14
0x180017905  inc     rax
0x180017908  cmp     [rbx+rax*2], r12w
0x18001790d  jnz     short loc_180017905
0x18001790f  inc     rax
0x180017912  cmp     rax, rsi
0x180017915  jnb     loc_180017A76
0x18001791b  lea     rcx, [rbx+rax*2]; String
0x18001791f  cmp     [rcx], r12w
0x180017923  jz      short loc_1800179A2
0x180017925  mov     rdx, r14
0x180017928  inc     rdx
0x18001792b  cmp     [rcx+rdx*2], r12w
0x180017930  jnz     short loc_180017928
0x180017932  inc     rax
0x180017935  add     rax, rdx
0x180017938  cmp     rax, rsi
0x18001793b  jb      short loc_1800179A5
0x18001793d  mov     rsi, r12
0x180017940  mov     edx, dword ptr [rbp+cbData]
0x180017943  add     rax, rax
0x180017946  cmp     rax, rdx
0x180017949  jz      short loc_180017958
0x18001794b  add     rax, 2
0x18001794f  cmp     rax, rdx
0x180017952  jnz     loc_180017A7D
0x180017958  mov     r14d, 8
0x18001795e  test    rcx, rcx
0x180017961  jz      short loc_18001796C
0x180017963  call    cs:__imp__wtoi
0x180017969  mov     r14d, eax
0x18001796c  mov     rdi, r12
0x18001796f  mov     [rbp+Sid], r12
0x180017973  test    rsi, rsi
0x180017976  jz      short loc_1800179C8
0x180017978  lea     rdx, [rbp+Sid]; Sid
0x18001797c  mov     rcx, rsi; StringSid
0x18001797f  call    cs:__imp_ConvertStringSidToSidW
0x180017985  test    eax, eax
0x180017987  jnz     short loc_1800179C4
0x180017989  call    cs:__imp_GetLastError
0x18001798f  test    eax, eax
0x180017991  jle     short loc_18001799B
0x180017993  movzx   eax, ax
0x180017996  or      eax, 80070000h
0x18001799b  mov     edi, eax
0x18001799d  jmp     loc_180017A82
0x1800179a2  mov     rcx, r12
0x1800179a5  lea     rsi, [rbx+rax*2]
0x1800179a9  cmp     [rsi], r12w
0x1800179ad  jz      short loc_18001793D
0x1800179af  inc     r14
0x1800179b2  cmp     [rsi+r14*2], r12w
0x1800179b7  jnz     short loc_1800179AF
0x1800179b9  inc     rax
0x1800179bc  add     rax, r14
0x1800179bf  jmp     loc_180017940
0x1800179c4  mov     rdi, [rbp+Sid]
0x1800179c8  mov     rax, cs:__imp_LocalFree
0x1800179cf  mov     [rbp+var_20], r12b
0x1800179d3  mov     [rbp+var_18], rax
0x1800179d7  mov     [rbp+var_10], rdi
0x1800179db  test    rdi, rdi
0x1800179de  jz      short loc_180017A5E
0x1800179e0  mov     rcx, rdi; pSid
0x1800179e3  call    cs:__imp_IsValidSid
0x1800179e9  test    eax, eax
0x1800179eb  jnz     short loc_180017A00
0x1800179ed  lea     rcx, [rbp+var_20]
0x1800179f1  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x1800179f6  mov     edi, 80070057h
0x1800179fb  jmp     loc_180017A82
0x180017a00  mov     rdi, [rbp+Sid]
0x180017a04  test    rdi, rdi
0x180017a07  jz      short loc_180017A5E
0x180017a09  mov     rdx, rbx; unsigned __int16 *
0x180017a0c  lea     rcx, [rbp+var_38]; this
0x180017a10  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180017a15  nop
0x180017a16  mov     r9, rdi
0x180017a19  mov     r8d, r14d
0x180017a1c  lea     rdx, [rbp+var_38]
0x180017a20  lea     rcx, [rbp+var_30]
0x180017a24  call    ?CreateUser@User@@SA?AV1@AEBV_bstr_t@@W4_SID_NAME_USE@@PEAX_N@Z; User::CreateUser(_bstr_t const &,_SID_NAME_USE,void *,bool)
0x180017a29  mov     rdx, [rax]
0x180017a2c  mov     rcx, r15
0x180017a2f  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180017a34  lea     rcx, [rbp+var_30]
0x180017a38  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180017a3d  nop
0x180017a3e  lea     rcx, [rbp+var_38]; this
0x180017a42  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180017a47  nop
0x180017a48  lea     rcx, [rbp+var_20]
0x180017a4c  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x180017a51  nop
0x180017a52  mov     rcx, rbx; Block
0x180017a55  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017a5a  xor     eax, eax
0x180017a5c  jmp     short loc_180017A93
0x180017a5e  mov     rdx, rbx; lpAccountName
0x180017a61  mov     rcx, r15; this
0x180017a64  call    ?FromUsername@User@@SAJAEAV1@PEBG@Z; User::FromUsername(User &,ushort const *)
0x180017a69  mov     edi, eax
0x180017a6b  lea     rcx, [rbp+var_20]
0x180017a6f  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x180017a74  jmp     short loc_180017A82
0x180017a76  mov     edi, 80004005h
0x180017a7b  jmp     short loc_180017A82
0x180017a7d  mov     edi, 8000FFFFh
0x180017a82  mov     rcx, rbx; Block
0x180017a85  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017a8a  mov     eax, edi
0x180017a8c  jmp     short loc_180017A93
0x180017a8e  mov     eax, 8000FFFFh
0x180017a93  lea     r11, [rsp+70h+var_s0]
0x180017a98  mov     rbx, [r11+30h]
0x180017a9c  mov     rsi, [r11+40h]
0x180017aa0  mov     rsp, r11
0x180017aa3  pop     r15
0x180017aa5  pop     r14
0x180017aa7  pop     r12
0x180017aa9  pop     rdi
0x180017aaa  pop     rbp
0x180017aab  retn
```
