# CredStore::ResolveAlias(ushort const *,User &)

- ea: `0x18002d3d0`
- end: `0x18002d6b8`
- name: `?ResolveAlias@CredStore@@QEAAJPEBGAEAVUser@@@Z`
- size: `744`
- prototype: `LSTATUS __fastcall(HKEY *this, const unsigned __int16 *, struct User *)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180029978`
- `0x18002c1b0`
- `0x180045df0`

## callees

- `0x18000b4e0`
- `0x18000dc30`
- `0x18001a260`
- `0x1800290f0`
- `0x18002ab90`
- `0x18002b1d0`
- `0x18002d3d0`
- `0x180030f80`
- `0x18004cfb0`
- `0x1800538cc`
- `0x18006f8d8`
- `0x18007e68a`

## import_xrefs

- `msvcrt!_wtoi` at `0x18002d567`
- `msvcrt!_wtoi` at `0x18002d567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d58d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d58d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d433`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d4d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d433`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d4d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d5cc`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002d5eb`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002d5eb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002d583`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002d583`

## pseudocode

```c
LSTATUS __fastcall CredStore::ResolveAlias(HKEY *this, const unsigned __int16 *a2, struct User *a3)
{
  LSTATUS result; // eax
  DWORD v7; // ecx
  unsigned __int64 v8; // r15
  __int64 v9; // r14
  BYTE *v10; // rax
  BYTE *v11; // rbx
  LSTATUS v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rax
  unsigned __int64 v15; // rax
  const wchar_t *v16; // rcx
  __int64 v17; // rdx
  const WCHAR *v18; // rsi
  __int64 v19; // rax
  unsigned int v20; // r14d
  PSID v21; // rdi
  signed int LastError; // eax
  PSID v23; // rdi
  _QWORD *User; // rax
  int lpData; // [rsp+20h] [rbp-50h]
  PSID Sid; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v27[8]; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v28[8]; // [rsp+40h] [rbp-30h] BYREF
  BYTE *v29; // [rsp+48h] [rbp-28h]
  _BYTE v30[8]; // [rsp+50h] [rbp-20h] BYREF
  HLOCAL (__stdcall *v31)(HLOCAL); // [rsp+58h] [rbp-18h]
  PSID v32; // [rsp+60h] [rbp-10h]
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
    v10 = (BYTE *)operator new(saturated_mul(v8, 2u));
    v11 = v10;
    v29 = v10;
    if ( !v10 )
    {
      operator delete(0);
      return -2147024882;
    }
    memset_0(v10, 0, cbData);
    v12 = RegQueryValueExW(this[5], a2, 0, &Type, v11, &cbData);
    v13 = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        v13 = (unsigned __int16)v12 | 0x80070000;
      goto LABEL_46;
    }
    if ( Type != 7 )
      goto LABEL_45;
    if ( !*(_WORD *)v11 )
      goto LABEL_44;
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)&v11[2 * v14] );
    v15 = v14 + 1;
    if ( v15 >= v8 )
    {
LABEL_44:
      v13 = -2147467259;
      goto LABEL_46;
    }
    v16 = (const wchar_t *)&v11[2 * v15];
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
    v18 = (const WCHAR *)&v11[2 * v15];
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
        v20 = 8;
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
        v30[0] = 0;
        v31 = LocalFree;
        v32 = v21;
        if ( v21 )
        {
          if ( !IsValidSid(v21) )
          {
            wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(v30);
            v13 = -2147024809;
LABEL_46:
            operator delete(v11);
            return v13;
          }
          v23 = Sid;
          if ( Sid )
          {
            _bstr_t::_bstr_t((_bstr_t *)v27, (const unsigned __int16 *)v11);
            LOBYTE(lpData) = 0;
            User = (_QWORD *)User::CreateUser(v28, v27, v20, v23, lpData);
            wmi::AutoRef<User::UserEntry>::operator=(a3, *User);
            wmi::AutoRef<User::UserEntry>::Release(v28);
            _bstr_t::~_bstr_t((_bstr_t *)v27);
            wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(v30);
            operator delete(v11);
            return 0;
          }
        }
        v13 = User::FromUsername(a3, (LPCWSTR)v11);
        wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(v30);
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
0x18002d3d0  mov     [rsp-38h+arg_0], rbx
0x18002d3d5  push    rbp
0x18002d3d6  push    rsi
0x18002d3d7  push    rdi
0x18002d3d8  push    r12
0x18002d3da  push    r13
0x18002d3dc  push    r14
0x18002d3de  push    r15
0x18002d3e0  mov     rbp, rsp
0x18002d3e3  sub     rsp, 70h
0x18002d3e7  mov     r12, r8
0x18002d3ea  mov     rsi, rdx
0x18002d3ed  mov     rdi, rcx
0x18002d3f0  xor     r13d, r13d
0x18002d3f3  test    rdx, rdx
0x18002d3f6  jnz     short loc_18002D402
0x18002d3f8  mov     eax, 80070057h
0x18002d3fd  jmp     loc_18002D6A0
0x18002d402  call    ?InitAliasesKey@CredStore@@AEAAJXZ; CredStore::InitAliasesKey(void)
0x18002d407  test    eax, eax
0x18002d409  js      loc_18002D6A0
0x18002d40f  mov     [rbp+Type], r13d
0x18002d413  mov     [rbp+cbData], r13d
0x18002d417  lea     rax, [rbp+cbData]
0x18002d41b  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18002d420  mov     [rsp+70h+lpData], r13; lpData
0x18002d425  lea     r9, [rbp+Type]; lpType
0x18002d429  xor     r8d, r8d; lpReserved
0x18002d42c  mov     rdx, rsi; lpValueName
0x18002d42f  mov     rcx, [rdi+28h]; hKey
0x18002d433  call    cs:__imp_RegQueryValueExW
0x18002d439  test    eax, eax
0x18002d43b  jz      short loc_18002D450
0x18002d43d  jle     loc_18002D6A0
0x18002d443  movzx   eax, ax
0x18002d446  or      eax, 80070000h
0x18002d44b  jmp     loc_18002D6A0
0x18002d450  cmp     [rbp+Type], 7
0x18002d454  jnz     loc_18002D69B
0x18002d45a  mov     ecx, [rbp+cbData]
0x18002d45d  test    ecx, ecx
0x18002d45f  jz      loc_18002D69B
0x18002d465  mov     eax, 2
0x18002d46a  add     ecx, eax
0x18002d46c  mov     [rbp+cbData], ecx
0x18002d46f  mov     r15d, ecx
0x18002d472  shr     r15, 1
0x18002d475  mul     r15
0x18002d478  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18002d47f  cmovb   rax, r14
0x18002d483  mov     rcx, rax; dwBytes
0x18002d486  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d48b  mov     rbx, rax
0x18002d48e  mov     [rbp+var_28], rax
0x18002d492  test    rax, rax
0x18002d495  jnz     short loc_18002D4A8
0x18002d497  xor     ecx, ecx; void *
0x18002d499  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d49e  mov     eax, 8007000Eh
0x18002d4a3  jmp     loc_18002D6A0
0x18002d4a8  mov     r8d, [rbp+cbData]; Size
0x18002d4ac  xor     edx, edx; Val
0x18002d4ae  mov     rcx, rbx; void *
0x18002d4b1  call    memset_0
0x18002d4b6  lea     rax, [rbp+cbData]
0x18002d4ba  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18002d4bf  mov     [rsp+70h+lpData], rbx; lpData
0x18002d4c4  lea     r9, [rbp+Type]; lpType
0x18002d4c8  xor     r8d, r8d; lpReserved
0x18002d4cb  mov     rdx, rsi; lpValueName
0x18002d4ce  mov     rcx, [rdi+28h]; hKey
0x18002d4d2  call    cs:__imp_RegQueryValueExW
0x18002d4d8  mov     edi, eax
0x18002d4da  test    eax, eax
0x18002d4dc  jz      short loc_18002D4F2
0x18002d4de  jle     loc_18002D68F
0x18002d4e4  movzx   edi, ax
0x18002d4e7  or      edi, 80070000h
0x18002d4ed  jmp     loc_18002D68F
0x18002d4f2  cmp     [rbp+Type], 7
0x18002d4f6  jnz     loc_18002D68A
0x18002d4fc  cmp     [rbx], r13w
0x18002d500  jz      loc_18002D683
0x18002d506  mov     rax, r14
0x18002d509  inc     rax
0x18002d50c  cmp     [rbx+rax*2], r13w
0x18002d511  jnz     short loc_18002D509
0x18002d513  inc     rax
0x18002d516  cmp     rax, r15
0x18002d519  jnb     loc_18002D683
0x18002d51f  lea     rcx, [rbx+rax*2]; String
0x18002d523  cmp     [rcx], r13w
0x18002d527  jz      short loc_18002D5A6
0x18002d529  mov     rdx, r14
0x18002d52c  inc     rdx
0x18002d52f  cmp     [rcx+rdx*2], r13w
0x18002d534  jnz     short loc_18002D52C
0x18002d536  inc     rax
0x18002d539  add     rax, rdx
0x18002d53c  cmp     rax, r15
0x18002d53f  jb      short loc_18002D5A9
0x18002d541  mov     rsi, r13
0x18002d544  mov     edx, [rbp+cbData]
0x18002d547  add     rax, rax
0x18002d54a  cmp     rax, rdx
0x18002d54d  jz      short loc_18002D55C
0x18002d54f  add     rax, 2
0x18002d553  cmp     rax, rdx
0x18002d556  jnz     loc_18002D68A
0x18002d55c  mov     r14d, 8
0x18002d562  test    rcx, rcx
0x18002d565  jz      short loc_18002D570
0x18002d567  call    cs:__imp__wtoi
0x18002d56d  mov     r14d, eax
0x18002d570  mov     rdi, r13
0x18002d573  mov     [rbp+Sid], r13
0x18002d577  test    rsi, rsi
0x18002d57a  jz      short loc_18002D5CC
0x18002d57c  lea     rdx, [rbp+Sid]; Sid
0x18002d580  mov     rcx, rsi; StringSid
0x18002d583  call    cs:__imp_ConvertStringSidToSidW
0x18002d589  test    eax, eax
0x18002d58b  jnz     short loc_18002D5C8
0x18002d58d  call    cs:__imp_GetLastError
0x18002d593  test    eax, eax
0x18002d595  jle     short loc_18002D59F
0x18002d597  movzx   eax, ax
0x18002d59a  or      eax, 80070000h
0x18002d59f  mov     edi, eax
0x18002d5a1  jmp     loc_18002D68F
0x18002d5a6  mov     rcx, r13
0x18002d5a9  lea     rsi, [rbx+rax*2]
0x18002d5ad  cmp     [rsi], r13w
0x18002d5b1  jz      short loc_18002D541
0x18002d5b3  inc     r14
0x18002d5b6  cmp     [rsi+r14*2], r13w
0x18002d5bb  jnz     short loc_18002D5B3
0x18002d5bd  inc     rax
0x18002d5c0  add     rax, r14
0x18002d5c3  jmp     loc_18002D544
0x18002d5c8  mov     rdi, [rbp+Sid]
0x18002d5cc  mov     rax, cs:__imp_LocalFree
0x18002d5d3  mov     [rbp+var_20], r13b
0x18002d5d7  mov     [rbp+var_18], rax
0x18002d5db  mov     [rbp+var_10], rdi
0x18002d5df  test    rdi, rdi
0x18002d5e2  jz      loc_18002D66B
0x18002d5e8  mov     rcx, rdi; pSid
0x18002d5eb  call    cs:__imp_IsValidSid
0x18002d5f1  test    eax, eax
0x18002d5f3  jnz     short loc_18002D608
0x18002d5f5  lea     rcx, [rbp+var_20]
0x18002d5f9  call    ??1?$ScopeGuardImpl1@P6AJPEAX@ZPEAX@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(void)
0x18002d5fe  mov     edi, 80070057h
0x18002d603  jmp     loc_18002D68F
0x18002d608  mov     rdi, [rbp+Sid]
0x18002d60c  test    rdi, rdi
0x18002d60f  jz      short loc_18002D66B
0x18002d611  mov     rdx, rbx; unsigned __int16 *
0x18002d614  lea     rcx, [rbp+var_38]; this
0x18002d618  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002d61d  nop
0x18002d61e  mov     byte ptr [rsp+70h+lpData], r13b
0x18002d623  mov     r9, rdi
0x18002d626  mov     r8d, r14d
0x18002d629  lea     rdx, [rbp+var_38]
0x18002d62d  lea     rcx, [rbp+var_30]
0x18002d631  call    ?CreateUser@User@@SA?AV1@AEBV_bstr_t@@W4_SID_NAME_USE@@PEAX_N@Z; User::CreateUser(_bstr_t const &,_SID_NAME_USE,void *,bool)
0x18002d636  mov     rdx, [rax]
0x18002d639  mov     rcx, r12
0x18002d63c  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18002d641  lea     rcx, [rbp+var_30]
0x18002d645  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18002d64a  nop
0x18002d64b  lea     rcx, [rbp+var_38]; this
0x18002d64f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18002d654  nop
0x18002d655  lea     rcx, [rbp+var_20]
0x18002d659  call    ??1?$ScopeGuardImpl1@P6AJPEAX@ZPEAX@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(void)
0x18002d65e  nop
0x18002d65f  mov     rcx, rbx; void *
0x18002d662  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d667  xor     eax, eax
0x18002d669  jmp     short loc_18002D6A0
0x18002d66b  mov     rdx, rbx; lpAccountName
0x18002d66e  mov     rcx, r12; this
0x18002d671  call    ?FromUsername@User@@SAJAEAV1@PEBG@Z; User::FromUsername(User &,ushort const *)
0x18002d676  mov     edi, eax
0x18002d678  lea     rcx, [rbp+var_20]
0x18002d67c  call    ??1?$ScopeGuardImpl1@P6AJPEAX@ZPEAX@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(void)
0x18002d681  jmp     short loc_18002D68F
0x18002d683  mov     edi, 80004005h
0x18002d688  jmp     short loc_18002D68F
0x18002d68a  mov     edi, 8000FFFFh
0x18002d68f  mov     rcx, rbx; void *
0x18002d692  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d697  mov     eax, edi
0x18002d699  jmp     short loc_18002D6A0
0x18002d69b  mov     eax, 8000FFFFh
0x18002d6a0  mov     rbx, [rsp+70h+arg_0]
0x18002d6a8  add     rsp, 70h
0x18002d6ac  pop     r15
0x18002d6ae  pop     r14
0x18002d6b0  pop     r13
0x18002d6b2  pop     r12
0x18002d6b4  pop     rdi
0x18002d6b5  pop     rsi
0x18002d6b6  pop     rbp
0x18002d6b7  retn
```
