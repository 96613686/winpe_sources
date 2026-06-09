# CredStore::StoreNtCredential(User const &,ushort *,bool)

- ea: `0x180017b90`
- end: `0x180017e8d`
- name: `?StoreNtCredential@CredStore@@QEAAJAEBVUser@@PEAG_N@Z`
- size: `765`
- prototype: `int(CredStore *__hidden this, const struct User *, unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005b98`

## callees

- `0x180004e50`
- `0x180005034`
- `0x180005840`
- `0x180007100`
- `0x180007160`
- `0x1800074c8`
- `0x180012e24`
- `0x18001724c`
- `0x18001726c`
- `0x180017518`
- `0x180017b90`
- `0x18002e572`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dbc`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x180017db2`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x180017db2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CredStore::StoreNtCredential(CredStore *this, const struct User *a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // rdi
  char v5; // bl
  __int64 Domain; // rax
  __int64 Account; // rax
  char v8; // r14
  __int64 v9; // rax
  __int64 i; // rax
  unsigned __int16 ***v12; // rax
  unsigned __int16 *v13; // rcx
  int AliasCredId; // ebx
  __int64 v15; // rax
  __int64 j; // rax
  __int64 v17; // rax
  __int64 k; // rax
  void *v19; // rbx
  WCHAR **v20; // rax
  WCHAR *v21; // rax
  int v22; // r14d
  __int64 v23; // rax
  __int64 ii; // rax
  signed int LastError; // eax
  unsigned int v26; // esi
  __int64 v27; // rax
  __int64 n; // rax
  const unsigned __int16 ***v29; // rax
  const unsigned __int16 *v30; // r14
  const unsigned __int16 ***v31; // rax
  const unsigned __int16 *v32; // rcx
  __int64 v33; // rax
  __int64 m; // rax
  _CREDENTIALW Credential; // [rsp+20h] [rbp-58h] BYREF
  void *Block; // [rsp+B0h] [rbp+38h] BYREF
  unsigned __int64 v37; // [rsp+B8h] [rbp+40h] BYREF
  unsigned __int16 *v38; // [rsp+C0h] [rbp+48h]
  int v39; // [rsp+C8h] [rbp+50h]

  Block = this;
  v3 = a3;
  v5 = 0;
  v39 = 0;
  v38 = a3;
  if ( !*(_QWORD *)a2
    || **(_BYTE **)a2
    || (Domain = User::GetDomain(a2, &v37), v5 = 1, (unsigned __int8)_bstr_t::operator!(Domain))
    || (Account = User::GetAccount(a2, &Block), v5 = 3, (unsigned __int8)_bstr_t::operator!(Account)) )
  {
    v8 = 1;
    if ( (v5 & 2) == 0 )
      goto LABEL_8;
  }
  else
  {
    v8 = 0;
  }
  v5 &= ~2u;
  _bstr_t::~_bstr_t((_bstr_t *)&Block);
LABEL_8:
  if ( (v5 & 1) != 0 )
    _bstr_t::~_bstr_t((_bstr_t *)&v37);
  if ( v8 )
  {
    if ( v3 )
    {
      v9 = -1;
      do
        ++v9;
      while ( v3[v9] );
      for ( i = 2 * v9; i; --i )
      {
        *(_BYTE *)v3 = 0;
        v3 = (unsigned __int16 *)((char *)v3 + 1);
      }
    }
    return 2147942487LL;
  }
  if ( !v3 )
    return 2147942487LL;
  Block = 0;
  v12 = (unsigned __int16 ***)User::GetAccount(a2, &v37);
  if ( *v12 )
    v13 = **v12;
  else
    v13 = 0;
  AliasCredId = CredStore::GetAliasCredId(v13, &Block);
  _bstr_t::~_bstr_t((_bstr_t *)&v37);
  if ( AliasCredId < 0 )
  {
    operator delete(Block);
    v15 = -1;
    do
      ++v15;
    while ( v3[v15] );
    for ( j = 2 * v15; j; --j )
    {
      *(_BYTE *)v3 = 0;
      v3 = (unsigned __int16 *)((char *)v3 + 1);
    }
    return (unsigned int)AliasCredId;
  }
  v37 = 0;
  AliasCredId = StringCchLengthW(v3, 0x101u, &v37);
  if ( AliasCredId < 0 )
  {
    operator delete(Block);
    v17 = -1;
    do
      ++v17;
    while ( v3[v17] );
    for ( k = 2 * v17; k; --k )
    {
      *(_BYTE *)v3 = 0;
      v3 = (unsigned __int16 *)((char *)v3 + 1);
    }
    return (unsigned int)AliasCredId;
  }
  memset_0(&Credential, 0, sizeof(Credential));
  Credential.Flags = 16388;
  Credential.Type = 2;
  v19 = Block;
  Credential.TargetName = (LPWSTR)Block;
  Credential.CredentialBlob = (LPBYTE)v3;
  Credential.Persist = 2;
  v20 = *(WCHAR ***)User::GetDomainAccount(a2, &Block);
  if ( v20 )
    v21 = *v20;
  else
    v21 = 0;
  Credential.UserName = v21;
  _bstr_t::~_bstr_t((_bstr_t *)&Block);
  v22 = ULongLongToULong(2 * v37, &Credential.CredentialBlobSize);
  if ( v22 >= 0 )
  {
    if ( CredWriteW(&Credential, 0) )
    {
      v29 = (const unsigned __int16 ***)User::GetDomain(a2, &v37);
      if ( *v29 )
        v30 = **v29;
      else
        v30 = 0;
      v31 = (const unsigned __int16 ***)User::GetAccount(a2, &Block);
      if ( *v31 )
        v32 = **v31;
      else
        v32 = 0;
      NotifyLsaOfPasswordChange(v32, v30, v3);
      _bstr_t::~_bstr_t((_bstr_t *)&Block);
      _bstr_t::~_bstr_t((_bstr_t *)&v37);
      operator delete(v19);
      v33 = -1;
      do
        ++v33;
      while ( v3[v33] );
      for ( m = 2 * v33; m; --m )
      {
        *(_BYTE *)v3 = 0;
        v3 = (unsigned __int16 *)((char *)v3 + 1);
      }
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v26 = LastError;
      if ( LastError > 0 )
        v26 = (unsigned __int16)LastError | 0x80070000;
      operator delete(v19);
      v27 = -1;
      do
        ++v27;
      while ( v3[v27] );
      for ( n = 2 * v27; n; --n )
      {
        *(_BYTE *)v3 = 0;
        v3 = (unsigned __int16 *)((char *)v3 + 1);
      }
      return v26;
    }
  }
  else
  {
    operator delete(v19);
    v23 = -1;
    do
      ++v23;
    while ( v3[v23] );
    for ( ii = 2 * v23; ii; --ii )
    {
      *(_BYTE *)v3 = 0;
      v3 = (unsigned __int16 *)((char *)v3 + 1);
    }
    return (unsigned int)v22;
  }
}

```

## disassembly

```asm
0x180017b90  mov     [rsp-30h+Block], rcx
0x180017b95  push    rbp
0x180017b96  push    rbx
0x180017b97  push    rsi
0x180017b98  push    rdi
0x180017b99  push    r14
0x180017b9b  push    r15
0x180017b9d  mov     rbp, rsp
0x180017ba0  sub     rsp, 78h
0x180017ba4  mov     rdi, r8
0x180017ba7  mov     rsi, rdx
0x180017baa  xor     r15d, r15d
0x180017bad  mov     ebx, r15d
0x180017bb0  mov     [rbp+arg_18], ebx
0x180017bb3  mov     [rbp+arg_10], r8
0x180017bb7  mov     rax, [rdx]
0x180017bba  test    rax, rax
0x180017bbd  jz      short loc_180017C01
0x180017bbf  cmp     [rax], r15b
0x180017bc2  jnz     short loc_180017C01
0x180017bc4  lea     rdx, [rbp+arg_8]
0x180017bc8  mov     rcx, rsi
0x180017bcb  call    ?GetDomain@User@@QEBA?BV_bstr_t@@XZ; User::GetDomain(void)
0x180017bd0  lea     ebx, [r15+1]
0x180017bd4  mov     rcx, rax
0x180017bd7  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180017bdc  test    al, al
0x180017bde  jnz     short loc_180017C01
0x180017be0  lea     rdx, [rbp+Block]
0x180017be4  mov     rcx, rsi
0x180017be7  call    ?GetAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetAccount(void)
0x180017bec  lea     ebx, [r15+3]
0x180017bf0  mov     rcx, rax
0x180017bf3  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180017bf8  test    al, al
0x180017bfa  jnz     short loc_180017C01
0x180017bfc  mov     r14b, r15b
0x180017bff  jmp     short loc_180017C09
0x180017c01  mov     r14b, 1
0x180017c04  test    bl, 2
0x180017c07  jz      short loc_180017C15
0x180017c09  and     ebx, 0FFFFFFFDh
0x180017c0c  lea     rcx, [rbp+Block]; this
0x180017c10  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180017c15  test    bl, 1
0x180017c18  jz      short loc_180017C23
0x180017c1a  lea     rcx, [rbp+arg_8]; this
0x180017c1e  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180017c23  test    r14b, r14b
0x180017c26  jz      short loc_180017C56
0x180017c28  test    rdi, rdi
0x180017c2b  jz      short loc_180017C4C
0x180017c2d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017c31  inc     rax
0x180017c34  cmp     [rdi+rax*2], r15w
0x180017c39  jnz     short loc_180017C31
0x180017c3b  add     rax, rax
0x180017c3e  jz      short loc_180017C4C
0x180017c40  mov     [rdi], r15b
0x180017c43  inc     rdi
0x180017c46  sub     rax, 1
0x180017c4a  jnz     short loc_180017C40
0x180017c4c  mov     eax, 80070057h
0x180017c51  jmp     loc_180017E80
0x180017c56  test    rdi, rdi
0x180017c59  jnz     short loc_180017C5D
0x180017c5b  jmp     short loc_180017C4C
0x180017c5d  mov     [rbp+Block], r15
0x180017c61  lea     rdx, [rbp+arg_8]
0x180017c65  mov     rcx, rsi
0x180017c68  call    ?GetAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetAccount(void)
0x180017c6d  nop
0x180017c6e  mov     rcx, [rax]
0x180017c71  test    rcx, rcx
0x180017c74  jz      short loc_180017C7B
0x180017c76  mov     rcx, [rcx]
0x180017c79  jmp     short loc_180017C7E
0x180017c7b  mov     rcx, r15; unsigned __int16 *
0x180017c7e  lea     rdx, [rbp+Block]
0x180017c82  call    ?GetAliasCredId@CredStore@@SAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; CredStore::GetAliasCredId(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x180017c87  mov     ebx, eax
0x180017c89  lea     rcx, [rbp+arg_8]; this
0x180017c8d  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180017c92  test    ebx, ebx
0x180017c94  jns     short loc_180017CC6
0x180017c96  mov     rcx, [rbp+Block]; Block
0x180017c9a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017c9f  nop
0x180017ca0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017ca4  inc     rax
0x180017ca7  cmp     [rdi+rax*2], r15w
0x180017cac  jnz     short loc_180017CA4
0x180017cae  add     rax, rax
0x180017cb1  jz      short loc_180017CBF
0x180017cb3  mov     [rdi], r15b
0x180017cb6  inc     rdi
0x180017cb9  sub     rax, 1
0x180017cbd  jnz     short loc_180017CB3
0x180017cbf  mov     eax, ebx
0x180017cc1  jmp     loc_180017E80
0x180017cc6  mov     [rbp+arg_8], r15
0x180017cca  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x180017cce  mov     edx, 101h; unsigned __int64
0x180017cd3  mov     rcx, rdi; unsigned __int16 *
0x180017cd6  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180017cdb  mov     ebx, eax
0x180017cdd  test    eax, eax
0x180017cdf  jns     short loc_180017D0C
0x180017ce1  mov     rcx, [rbp+Block]; Block
0x180017ce5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017cea  nop
0x180017ceb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017cef  inc     rax
0x180017cf2  cmp     [rdi+rax*2], r15w
0x180017cf7  jnz     short loc_180017CEF
0x180017cf9  add     rax, rax
0x180017cfc  jz      short loc_180017CBF
0x180017cfe  mov     [rdi], r15b
0x180017d01  inc     rdi
0x180017d04  sub     rax, 1
0x180017d08  jnz     short loc_180017CFE
0x180017d0a  jmp     short loc_180017CBF
0x180017d0c  xor     edx, edx; Val
0x180017d0e  lea     r8d, [rdx+50h]; Size
0x180017d12  lea     rcx, [rbp+Credential]; void *
0x180017d16  call    memset_0
0x180017d1b  mov     [rbp+Credential.Flags], 4004h
0x180017d22  mov     [rbp+Credential.Type], 2
0x180017d29  mov     rbx, [rbp+Block]
0x180017d2d  mov     [rbp+Credential.TargetName], rbx
0x180017d31  mov     [rbp+Credential.CredentialBlob], rdi
0x180017d35  mov     [rbp+Credential.Persist], 2
0x180017d3c  lea     rdx, [rbp+Block]
0x180017d40  mov     rcx, rsi
0x180017d43  call    ?GetDomainAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetDomainAccount(void)
0x180017d48  mov     rax, [rax]
0x180017d4b  test    rax, rax
0x180017d4e  jz      short loc_180017D55
0x180017d50  mov     rax, [rax]
0x180017d53  jmp     short loc_180017D58
0x180017d55  mov     rax, r15
0x180017d58  mov     [rbp+Credential.UserName], rax
0x180017d5c  lea     rcx, [rbp+Block]; this
0x180017d60  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180017d65  mov     rcx, [rbp+arg_8]
0x180017d69  add     rcx, rcx; unsigned __int64
0x180017d6c  lea     rdx, [rbp+Credential.CredentialBlobSize]; unsigned int *
0x180017d70  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180017d75  mov     r14d, eax
0x180017d78  test    eax, eax
0x180017d7a  jns     short loc_180017DAC
0x180017d7c  mov     rcx, rbx; Block
0x180017d7f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017d84  nop
0x180017d85  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017d89  inc     rax
0x180017d8c  cmp     [rdi+rax*2], r15w
0x180017d91  jnz     short loc_180017D89
0x180017d93  add     rax, rax
0x180017d96  jz      short loc_180017DA4
0x180017d98  mov     [rdi], r15b
0x180017d9b  inc     rdi
0x180017d9e  sub     rax, 1
0x180017da2  jnz     short loc_180017D98
0x180017da4  mov     eax, r14d
0x180017da7  jmp     loc_180017E80
0x180017dac  xor     edx, edx; Flags
0x180017dae  lea     rcx, [rbp+Credential]; Credential
0x180017db2  call    cs:__imp_CredWriteW
0x180017db8  test    eax, eax
0x180017dba  jnz     short loc_180017E00
0x180017dbc  call    cs:__imp_GetLastError
0x180017dc2  mov     esi, eax
0x180017dc4  test    eax, eax
0x180017dc6  jle     short loc_180017DD1
0x180017dc8  movzx   esi, ax
0x180017dcb  or      esi, 80070000h
0x180017dd1  mov     rcx, rbx; Block
0x180017dd4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017dd9  nop
0x180017dda  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017dde  inc     rax
0x180017de1  cmp     [rdi+rax*2], r15w
0x180017de6  jnz     short loc_180017DDE
0x180017de8  add     rax, rax
0x180017deb  jz      short loc_180017DF9
0x180017ded  mov     [rdi], r15b
0x180017df0  inc     rdi
0x180017df3  sub     rax, 1
0x180017df7  jnz     short loc_180017DED
0x180017df9  mov     eax, esi
0x180017dfb  jmp     loc_180017E80
0x180017e00  lea     rdx, [rbp+arg_8]
0x180017e04  mov     rcx, rsi
0x180017e07  call    ?GetDomain@User@@QEBA?BV_bstr_t@@XZ; User::GetDomain(void)
0x180017e0c  mov     rcx, [rax]
0x180017e0f  test    rcx, rcx
0x180017e12  jz      short loc_180017E19
0x180017e14  mov     r14, [rcx]
0x180017e17  jmp     short loc_180017E1C
0x180017e19  mov     r14, r15
0x180017e1c  lea     rdx, [rbp+Block]
0x180017e20  mov     rcx, rsi
0x180017e23  call    ?GetAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetAccount(void)
0x180017e28  mov     rcx, [rax]
0x180017e2b  test    rcx, rcx
0x180017e2e  jz      short loc_180017E35
0x180017e30  mov     rcx, [rcx]
0x180017e33  jmp     short loc_180017E38
0x180017e35  mov     rcx, r15; unsigned __int16 *
0x180017e38  mov     r8, rdi; unsigned __int16 *
0x180017e3b  mov     rdx, r14; unsigned __int16 *
0x180017e3e  call    ?NotifyLsaOfPasswordChange@@YAKPEBG00@Z; NotifyLsaOfPasswordChange(ushort const *,ushort const *,ushort const *)
0x180017e43  lea     rcx, [rbp+Block]; this
0x180017e47  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180017e4c  lea     rcx, [rbp+arg_8]; this
0x180017e50  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180017e55  nop
0x180017e56  mov     rcx, rbx; Block
0x180017e59  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017e5e  nop
0x180017e5f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017e63  inc     rax
0x180017e66  cmp     [rdi+rax*2], r15w
0x180017e6b  jnz     short loc_180017E63
0x180017e6d  add     rax, rax
0x180017e70  jz      short loc_180017E7E
0x180017e72  mov     [rdi], r15b
0x180017e75  inc     rdi
0x180017e78  sub     rax, 1
0x180017e7c  jnz     short loc_180017E72
0x180017e7e  xor     eax, eax
0x180017e80  add     rsp, 78h
0x180017e84  pop     r15
0x180017e86  pop     r14
0x180017e88  pop     rdi
0x180017e89  pop     rsi
0x180017e8a  pop     rbx
0x180017e8b  pop     rbp
0x180017e8c  retn
```
