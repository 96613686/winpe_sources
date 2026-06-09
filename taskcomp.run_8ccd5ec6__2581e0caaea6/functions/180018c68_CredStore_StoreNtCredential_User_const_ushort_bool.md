# CredStore::StoreNtCredential(User const &,ushort *,bool)

- ea: `0x180018c68`
- end: `0x180018f71`
- name: `?StoreNtCredential@CredStore@@QEAAJAEBVUser@@PEAG_N@Z`
- size: `777`
- prototype: `int(CredStore *__hidden this, const struct User *, unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005efc`

## callees

- `0x1800050d0`
- `0x1800052d8`
- `0x180005b30`
- `0x18000757c`
- `0x1800075e8`
- `0x180007988`
- `0x1800139fc`
- `0x18001822c`
- `0x18001824c`
- `0x180018534`
- `0x180018550`
- `0x180018c68`
- `0x1800306c2`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e99`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x180018e89`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x180018e89`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CredStore::StoreNtCredential(CredStore *this, const struct User *a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // rdi
  char v5; // bl
  __int64 v6; // rcx
  __int64 Domain; // rax
  __int64 Account; // rax
  char v9; // r14
  __int64 v10; // rax
  __int64 i; // rax
  unsigned __int16 ***v13; // rax
  unsigned __int16 *v14; // rcx
  int AliasCredId; // ebx
  __int64 v16; // rax
  __int64 j; // rax
  __int64 v18; // rax
  __int64 k; // rax
  void *v20; // rbx
  WCHAR **v21; // rax
  WCHAR *v22; // rax
  int v23; // r14d
  __int64 v24; // rax
  __int64 ii; // rax
  signed int LastError; // eax
  unsigned int v27; // esi
  __int64 v28; // rax
  __int64 n; // rax
  const unsigned __int16 ***v30; // rax
  const unsigned __int16 *v31; // r14
  const unsigned __int16 ***v32; // rax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  __int64 m; // rax
  _CREDENTIALW Credential; // [rsp+20h] [rbp-58h] BYREF
  void *Block; // [rsp+B0h] [rbp+38h] BYREF
  unsigned __int64 v38; // [rsp+B8h] [rbp+40h] BYREF
  unsigned __int16 *v39; // [rsp+C0h] [rbp+48h]
  int v40; // [rsp+C8h] [rbp+50h]

  Block = this;
  v3 = a3;
  v5 = 0;
  v40 = 0;
  v39 = a3;
  if ( !*(_QWORD *)a2
    || User::IsAlias(a2)
    || (Domain = User::GetDomain(v6, &v38), v5 = 1, (unsigned __int8)_bstr_t::operator!(Domain))
    || (Account = User::GetAccount(a2, &Block), v5 = 3, v9 = 0, (unsigned __int8)_bstr_t::operator!(Account)) )
  {
    v9 = 1;
  }
  if ( (v5 & 2) != 0 )
  {
    v5 &= ~2u;
    _bstr_t::~_bstr_t((_bstr_t *)&Block);
  }
  if ( (v5 & 1) != 0 )
    _bstr_t::~_bstr_t((_bstr_t *)&v38);
  if ( v9 )
  {
    if ( v3 )
    {
      v10 = -1;
      do
        ++v10;
      while ( v3[v10] );
      for ( i = 2 * v10; i; --i )
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
  v13 = (unsigned __int16 ***)User::GetAccount(a2, &v38);
  if ( *v13 )
    v14 = **v13;
  else
    v14 = 0;
  AliasCredId = CredStore::GetAliasCredId(v14);
  _bstr_t::~_bstr_t((_bstr_t *)&v38);
  if ( AliasCredId < 0 )
  {
    operator delete(Block);
    v16 = -1;
    do
      ++v16;
    while ( v3[v16] );
    for ( j = 2 * v16; j; --j )
    {
      *(_BYTE *)v3 = 0;
      v3 = (unsigned __int16 *)((char *)v3 + 1);
    }
    return (unsigned int)AliasCredId;
  }
  v38 = 0;
  AliasCredId = StringCchLengthW(v3, 0x101u, &v38);
  if ( AliasCredId < 0 )
  {
    operator delete(Block);
    v18 = -1;
    do
      ++v18;
    while ( v3[v18] );
    for ( k = 2 * v18; k; --k )
    {
      *(_BYTE *)v3 = 0;
      v3 = (unsigned __int16 *)((char *)v3 + 1);
    }
    return (unsigned int)AliasCredId;
  }
  memset_0(&Credential, 0, sizeof(Credential));
  Credential.Flags = 16388;
  Credential.Type = 2;
  v20 = Block;
  Credential.TargetName = (LPWSTR)Block;
  Credential.CredentialBlob = (LPBYTE)v3;
  Credential.Persist = 2;
  v21 = *(WCHAR ***)User::GetDomainAccount(a2, &Block);
  if ( v21 )
    v22 = *v21;
  else
    v22 = 0;
  Credential.UserName = v22;
  _bstr_t::~_bstr_t((_bstr_t *)&Block);
  v23 = ULongLongToULong(2 * v38, &Credential.CredentialBlobSize);
  if ( v23 >= 0 )
  {
    if ( CredWriteW(&Credential, 0) )
    {
      v30 = (const unsigned __int16 ***)User::GetDomain(a2, &v38);
      if ( *v30 )
        v31 = **v30;
      else
        v31 = 0;
      v32 = (const unsigned __int16 ***)User::GetAccount(a2, &Block);
      if ( *v32 )
        v33 = **v32;
      else
        v33 = 0;
      NotifyLsaOfPasswordChange(v33, v31, v3);
      _bstr_t::~_bstr_t((_bstr_t *)&Block);
      _bstr_t::~_bstr_t((_bstr_t *)&v38);
      operator delete(v20);
      v34 = -1;
      do
        ++v34;
      while ( v3[v34] );
      for ( m = 2 * v34; m; --m )
      {
        *(_BYTE *)v3 = 0;
        v3 = (unsigned __int16 *)((char *)v3 + 1);
      }
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v27 = LastError;
      if ( LastError > 0 )
        v27 = (unsigned __int16)LastError | 0x80070000;
      operator delete(v20);
      v28 = -1;
      do
        ++v28;
      while ( v3[v28] );
      for ( n = 2 * v28; n; --n )
      {
        *(_BYTE *)v3 = 0;
        v3 = (unsigned __int16 *)((char *)v3 + 1);
      }
      return v27;
    }
  }
  else
  {
    operator delete(v20);
    v24 = -1;
    do
      ++v24;
    while ( v3[v24] );
    for ( ii = 2 * v24; ii; --ii )
    {
      *(_BYTE *)v3 = 0;
      v3 = (unsigned __int16 *)((char *)v3 + 1);
    }
    return (unsigned int)v23;
  }
}

```

## disassembly

```asm
0x180018c68  mov     [rsp-30h+Block], rcx
0x180018c6d  push    rbp
0x180018c6e  push    rbx
0x180018c6f  push    rsi
0x180018c70  push    rdi
0x180018c71  push    r14
0x180018c73  push    r15
0x180018c75  mov     rbp, rsp
0x180018c78  sub     rsp, 78h
0x180018c7c  mov     rdi, r8
0x180018c7f  mov     rsi, rdx
0x180018c82  xor     r15d, r15d
0x180018c85  mov     ebx, r15d
0x180018c88  mov     [rbp+arg_18], ebx
0x180018c8b  mov     [rbp+arg_10], r8
0x180018c8f  cmp     [rdx], r15
0x180018c92  jz      short loc_180018CD8
0x180018c94  mov     rcx, rdx; this
0x180018c97  call    ?IsAlias@User@@QEBA_NXZ; User::IsAlias(void)
0x180018c9c  test    al, al
0x180018c9e  jnz     short loc_180018CD8
0x180018ca0  lea     rdx, [rbp+arg_8]
0x180018ca4  call    ?GetDomain@User@@QEBA?BV_bstr_t@@XZ; User::GetDomain(void)
0x180018ca9  lea     ebx, [r15+1]
0x180018cad  mov     rcx, rax
0x180018cb0  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180018cb5  test    al, al
0x180018cb7  jnz     short loc_180018CD8
0x180018cb9  lea     rdx, [rbp+Block]
0x180018cbd  mov     rcx, rsi
0x180018cc0  call    ?GetAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetAccount(void)
0x180018cc5  lea     ebx, [r15+3]
0x180018cc9  mov     rcx, rax
0x180018ccc  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180018cd1  test    al, al
0x180018cd3  mov     r14b, r15b
0x180018cd6  jz      short loc_180018CDB
0x180018cd8  mov     r14b, 1
0x180018cdb  test    bl, 2
0x180018cde  jz      short loc_180018CEC
0x180018ce0  and     ebx, 0FFFFFFFDh
0x180018ce3  lea     rcx, [rbp+Block]; this
0x180018ce7  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180018cec  test    bl, 1
0x180018cef  jz      short loc_180018CFA
0x180018cf1  lea     rcx, [rbp+arg_8]; this
0x180018cf5  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180018cfa  test    r14b, r14b
0x180018cfd  jz      short loc_180018D2D
0x180018cff  test    rdi, rdi
0x180018d02  jz      short loc_180018D23
0x180018d04  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018d08  inc     rax
0x180018d0b  cmp     [rdi+rax*2], r15w
0x180018d10  jnz     short loc_180018D08
0x180018d12  add     rax, rax
0x180018d15  jz      short loc_180018D23
0x180018d17  mov     [rdi], r15b
0x180018d1a  inc     rdi
0x180018d1d  sub     rax, 1
0x180018d21  jnz     short loc_180018D17
0x180018d23  mov     eax, 80070057h
0x180018d28  jmp     loc_180018F63
0x180018d2d  test    rdi, rdi
0x180018d30  jnz     short loc_180018D34
0x180018d32  jmp     short loc_180018D23
0x180018d34  mov     [rbp+Block], r15
0x180018d38  lea     rdx, [rbp+arg_8]
0x180018d3c  mov     rcx, rsi
0x180018d3f  call    ?GetAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetAccount(void)
0x180018d44  nop
0x180018d45  mov     rcx, [rax]
0x180018d48  test    rcx, rcx
0x180018d4b  jz      short loc_180018D52
0x180018d4d  mov     rcx, [rcx]
0x180018d50  jmp     short loc_180018D55
0x180018d52  mov     rcx, r15; unsigned __int16 *
0x180018d55  lea     rdx, [rbp+Block]
0x180018d59  call    ?GetAliasCredId@CredStore@@SAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; CredStore::GetAliasCredId(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x180018d5e  mov     ebx, eax
0x180018d60  lea     rcx, [rbp+arg_8]; this
0x180018d64  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180018d69  test    ebx, ebx
0x180018d6b  jns     short loc_180018D9D
0x180018d6d  mov     rcx, [rbp+Block]; Block
0x180018d71  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018d76  nop
0x180018d77  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018d7b  inc     rax
0x180018d7e  cmp     [rdi+rax*2], r15w
0x180018d83  jnz     short loc_180018D7B
0x180018d85  add     rax, rax
0x180018d88  jz      short loc_180018D96
0x180018d8a  mov     [rdi], r15b
0x180018d8d  inc     rdi
0x180018d90  sub     rax, 1
0x180018d94  jnz     short loc_180018D8A
0x180018d96  mov     eax, ebx
0x180018d98  jmp     loc_180018F63
0x180018d9d  mov     [rbp+arg_8], r15
0x180018da1  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x180018da5  mov     edx, 101h; unsigned __int64
0x180018daa  mov     rcx, rdi; unsigned __int16 *
0x180018dad  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180018db2  mov     ebx, eax
0x180018db4  test    eax, eax
0x180018db6  jns     short loc_180018DE3
0x180018db8  mov     rcx, [rbp+Block]; Block
0x180018dbc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018dc1  nop
0x180018dc2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018dc6  inc     rax
0x180018dc9  cmp     [rdi+rax*2], r15w
0x180018dce  jnz     short loc_180018DC6
0x180018dd0  add     rax, rax
0x180018dd3  jz      short loc_180018D96
0x180018dd5  mov     [rdi], r15b
0x180018dd8  inc     rdi
0x180018ddb  sub     rax, 1
0x180018ddf  jnz     short loc_180018DD5
0x180018de1  jmp     short loc_180018D96
0x180018de3  xor     edx, edx; Val
0x180018de5  lea     r8d, [rdx+50h]; Size
0x180018de9  lea     rcx, [rbp+Credential]; void *
0x180018ded  call    memset_0
0x180018df2  mov     [rbp+Credential.Flags], 4004h
0x180018df9  mov     [rbp+Credential.Type], 2
0x180018e00  mov     rbx, [rbp+Block]
0x180018e04  mov     [rbp+Credential.TargetName], rbx
0x180018e08  mov     [rbp+Credential.CredentialBlob], rdi
0x180018e0c  mov     [rbp+Credential.Persist], 2
0x180018e13  lea     rdx, [rbp+Block]
0x180018e17  mov     rcx, rsi
0x180018e1a  call    ?GetDomainAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetDomainAccount(void)
0x180018e1f  mov     rax, [rax]
0x180018e22  test    rax, rax
0x180018e25  jz      short loc_180018E2C
0x180018e27  mov     rax, [rax]
0x180018e2a  jmp     short loc_180018E2F
0x180018e2c  mov     rax, r15
0x180018e2f  mov     [rbp+Credential.UserName], rax
0x180018e33  lea     rcx, [rbp+Block]; this
0x180018e37  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180018e3c  mov     rcx, [rbp+arg_8]
0x180018e40  add     rcx, rcx; unsigned __int64
0x180018e43  lea     rdx, [rbp+Credential.CredentialBlobSize]; unsigned int *
0x180018e47  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180018e4c  mov     r14d, eax
0x180018e4f  test    eax, eax
0x180018e51  jns     short loc_180018E83
0x180018e53  mov     rcx, rbx; Block
0x180018e56  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018e5b  nop
0x180018e5c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018e60  inc     rax
0x180018e63  cmp     [rdi+rax*2], r15w
0x180018e68  jnz     short loc_180018E60
0x180018e6a  add     rax, rax
0x180018e6d  jz      short loc_180018E7B
0x180018e6f  mov     [rdi], r15b
0x180018e72  inc     rdi
0x180018e75  sub     rax, 1
0x180018e79  jnz     short loc_180018E6F
0x180018e7b  mov     eax, r14d
0x180018e7e  jmp     loc_180018F63
0x180018e83  xor     edx, edx; Flags
0x180018e85  lea     rcx, [rbp+Credential]; Credential
0x180018e89  call    cs:__imp_CredWriteW
0x180018e90  nop     dword ptr [rax+rax+00h]
0x180018e95  test    eax, eax
0x180018e97  jnz     short loc_180018EE3
0x180018e99  call    cs:__imp_GetLastError
0x180018ea0  nop     dword ptr [rax+rax+00h]
0x180018ea5  mov     esi, eax
0x180018ea7  test    eax, eax
0x180018ea9  jle     short loc_180018EB4
0x180018eab  movzx   esi, ax
0x180018eae  or      esi, 80070000h
0x180018eb4  mov     rcx, rbx; Block
0x180018eb7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018ebc  nop
0x180018ebd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018ec1  inc     rax
0x180018ec4  cmp     [rdi+rax*2], r15w
0x180018ec9  jnz     short loc_180018EC1
0x180018ecb  add     rax, rax
0x180018ece  jz      short loc_180018EDC
0x180018ed0  mov     [rdi], r15b
0x180018ed3  inc     rdi
0x180018ed6  sub     rax, 1
0x180018eda  jnz     short loc_180018ED0
0x180018edc  mov     eax, esi
0x180018ede  jmp     loc_180018F63
0x180018ee3  lea     rdx, [rbp+arg_8]
0x180018ee7  mov     rcx, rsi
0x180018eea  call    ?GetDomain@User@@QEBA?BV_bstr_t@@XZ; User::GetDomain(void)
0x180018eef  mov     rcx, [rax]
0x180018ef2  test    rcx, rcx
0x180018ef5  jz      short loc_180018EFC
0x180018ef7  mov     r14, [rcx]
0x180018efa  jmp     short loc_180018EFF
0x180018efc  mov     r14, r15
0x180018eff  lea     rdx, [rbp+Block]
0x180018f03  mov     rcx, rsi
0x180018f06  call    ?GetAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetAccount(void)
0x180018f0b  mov     rcx, [rax]
0x180018f0e  test    rcx, rcx
0x180018f11  jz      short loc_180018F18
0x180018f13  mov     rcx, [rcx]
0x180018f16  jmp     short loc_180018F1B
0x180018f18  mov     rcx, r15; unsigned __int16 *
0x180018f1b  mov     r8, rdi; unsigned __int16 *
0x180018f1e  mov     rdx, r14; unsigned __int16 *
0x180018f21  call    ?NotifyLsaOfPasswordChange@@YAKPEBG00@Z; NotifyLsaOfPasswordChange(ushort const *,ushort const *,ushort const *)
0x180018f26  lea     rcx, [rbp+Block]; this
0x180018f2a  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180018f2f  lea     rcx, [rbp+arg_8]; this
0x180018f33  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180018f38  nop
0x180018f39  mov     rcx, rbx; Block
0x180018f3c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018f41  nop
0x180018f42  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018f46  inc     rax
0x180018f49  cmp     [rdi+rax*2], r15w
0x180018f4e  jnz     short loc_180018F46
0x180018f50  add     rax, rax
0x180018f53  jz      short loc_180018F61
0x180018f55  mov     [rdi], r15b
0x180018f58  inc     rdi
0x180018f5b  sub     rax, 1
0x180018f5f  jnz     short loc_180018F55
0x180018f61  xor     eax, eax
0x180018f63  add     rsp, 78h
0x180018f67  pop     r15
0x180018f69  pop     r14
0x180018f6b  pop     rdi
0x180018f6c  pop     rsi
0x180018f6d  pop     rbx
0x180018f6e  pop     rbp
0x180018f6f  retn
```
