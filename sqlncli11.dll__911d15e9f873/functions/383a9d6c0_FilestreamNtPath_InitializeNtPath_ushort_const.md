# FilestreamNtPath::InitializeNtPath(ushort const *)

- ea: `0x383a9d6c0`
- end: `0x383a9dc68`
- name: `?InitializeNtPath@FilestreamNtPath@@QEAAJPEBG@Z`
- size: `1448`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x383a9dc90`

## callees

- `0x3838434c0`
- `0x38391ac10`
- `0x38391ac40`
- `0x38391aed0`
- `0x38391af80`
- `0x383a9d250`
- `0x383a9d340`
- `0x383a9d6c0`

## import_xrefs

- `MSVCR100!malloc` at `0x383a9d865`
- `MSVCR100!malloc` at `0x383a9d865`
- `RPCRT4!UuidCreate` at `0x383a9d7a7`
- `RPCRT4!UuidCreate` at `0x383a9d7a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FilestreamNtPath::InitializeNtPath(
        struct _UNICODE_STRING *this,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rcx
  const unsigned __int16 *v7; // rax
  int v8; // edx
  __int64 v9; // rsi
  unsigned int v10; // eax
  signed int v11; // edi
  WCHAR *v13; // rax
  const unsigned __int16 *v14; // rdx
  unsigned __int64 v15; // r8
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  _BYTE *v19; // r8
  __int64 v20; // r9
  _QWORD v21[2]; // [rsp+30h] [rbp-48h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-38h] BYREF

  v21[1] = -2;
  v21[0] = -1;
  if ( (bidGblFlags & 4) != 0 && off_383B4AD50[0] )
    bidScopeEnterW(v21, off_383B4AD50[0], a2, a4);
  if ( !a2 )
    goto LABEL_12;
  v6 = 0x7FFF;
  v7 = a2;
  v8 = 0;
  while ( *v7 )
  {
    ++v7;
    if ( !--v6 )
    {
      v8 = -2147024809;
      v9 = 0;
      goto LABEL_10;
    }
  }
  v9 = 0x7FFF - v6;
LABEL_10:
  if ( v8 < 0 )
  {
LABEL_12:
    if ( (bidGblFlags & 2) != 0 && off_383B4A260[0] )
      bidTraceW(off_383B43530[0], 290816, off_383B4A260[0], 3221225485LL);
LABEL_76:
    if ( v21[0] != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
      off_383B15058();
    return 3221225485LL;
  }
  v10 = UuidCreate(&Uuid);
  v11 = v10;
  if ( v10 && v10 != 1824 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B4A220[0] )
      bidTraceW(off_383B43530[0], 303104, off_383B4A220[0], v10);
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0xC0070000;
LABEL_22:
    if ( v21[0] != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
      off_383B15058();
    return (unsigned int)v11;
  }
  if ( !v9 || *a2 != 92 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B4A240[0] )
      bidTraceW(off_383B43530[0], 313344, off_383B4A240[0], 3221225485LL);
    goto LABEL_76;
  }
  v13 = (WCHAR *)malloc(2 * (v9 + 39));
  this->Buffer = v13;
  if ( v13 )
  {
    this->Length = 0;
    this->MaximumLength = 2 * (v9 + 39);
    v16 = RtlUnicodeStringCchCopyStringN(this, v14, v15);
    v11 = v16;
    if ( v16 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B4A248[0] )
        bidTraceW(off_383B43530[0], 359424, off_383B4A248[0], v16);
      goto LABEL_22;
    }
    v17 = RtlUnicodeStringCchCatStringN(this, a2 + 1, v9 - 1);
    v11 = v17;
    if ( v17 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B4A1E0[0] )
        bidTraceW(off_383B43530[0], 373760, off_383B4A1E0[0], v17);
      goto LABEL_22;
    }
    v18 = RtlUnicodeStringCchCatStringN(this, L"\\", 1u);
    v11 = v18;
    if ( v18 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B4A218[0] )
        bidTraceW(off_383B43530[0], 388096, off_383B4A218[0], v18);
      goto LABEL_22;
    }
    if ( (unsigned __int64)this->Length + 64 <= this->MaximumLength )
    {
      v19 = (char *)&Uuid.Data1 + 1;
      v20 = 4;
      do
      {
        this->Buffer[(unsigned __int64)this->Length >> 1] = a0123456789abcd[(unsigned __int64)(unsigned __int8)*(v19 - 1) >> 4];
        this->Length += 2;
        this->Buffer[(unsigned __int64)this->Length >> 1] = a0123456789abcd[*(v19 - 1) & 0xF];
        this->Length += 2;
        this->Buffer[(unsigned __int64)this->Length >> 1] = a0123456789abcd[(unsigned __int64)(unsigned __int8)*v19 >> 4];
        this->Length += 2;
        this->Buffer[(unsigned __int64)this->Length >> 1] = a0123456789abcd[*v19 & 0xF];
        this->Length += 2;
        this->Buffer[(unsigned __int64)this->Length >> 1] = a0123456789abcd[(unsigned __int64)(unsigned __int8)v19[1] >> 4];
        this->Length += 2;
        this->Buffer[(unsigned __int64)this->Length >> 1] = a0123456789abcd[v19[1] & 0xF];
        this->Length += 2;
        this->Buffer[(unsigned __int64)this->Length >> 1] = a0123456789abcd[(unsigned __int64)(unsigned __int8)v19[2] >> 4];
        this->Length += 2;
        this->Buffer[(unsigned __int64)this->Length >> 1] = a0123456789abcd[v19[2] & 0xF];
        this->Length += 2;
        v19 += 4;
        --v20;
      }
      while ( v20 );
      if ( (bidGblFlags & 2) != 0 && off_383B4A1D8[0] && bidID != -1 )
        off_383B15040();
      if ( v21[0] != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
        off_383B15058();
      return 0;
    }
    else
    {
      if ( (bidGblFlags & 2) != 0 && off_383B4A238[0] )
        bidTraceW(off_383B43530[0], 399360, off_383B4A238[0], 2147483653LL);
      if ( v21[0] != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
        off_383B15058();
      return 2147483653LL;
    }
  }
  else
  {
    if ( (bidGblFlags & 2) != 0 && off_383B4A1D0[0] )
      bidTraceW(off_383B43530[0], 343040, off_383B4A1D0[0], 3221225495LL);
    if ( v21[0] != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
      off_383B15058();
    return 3221225495LL;
  }
}

```

## disassembly

```asm
0x383a9d6c0  mov     r11, rsp
0x383a9d6c3  push    rsi
0x383a9d6c4  push    rdi
0x383a9d6c5  push    r14
0x383a9d6c7  sub     rsp, 60h
0x383a9d6cb  mov     qword ptr [r11-40h], 0FFFFFFFFFFFFFFFEh
0x383a9d6d3  mov     [r11+18h], rbx
0x383a9d6d7  mov     [r11+20h], rbp
0x383a9d6db  mov     rax, cs:__security_cookie
0x383a9d6e2  xor     rax, rsp
0x383a9d6e5  mov     [rsp+78h+var_28], rax
0x383a9d6ea  mov     rbp, rdx
0x383a9d6ed  mov     rbx, rcx
0x383a9d6f0  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFFh
0x383a9d6f8  test    byte ptr cs:_bidGblFlags, 4
0x383a9d6ff  jz      short loc_383A9D720
0x383a9d701  mov     rax, cs:off_383B4AD50; "<FilestreamNtPath::InitializeNtPath>  '"...
0x383a9d708  test    rax, rax
0x383a9d70b  jz      short loc_383A9D720
0x383a9d70d  mov     r8, rdx
0x383a9d710  mov     rdx, cs:off_383B4AD50; "<FilestreamNtPath::InitializeNtPath>  '"...
0x383a9d717  lea     rcx, [r11-48h]
0x383a9d71b  call    _bidScopeEnterW
0x383a9d720  xor     r14d, r14d
0x383a9d723  test    rbp, rbp
0x383a9d726  jz      short loc_383A9D75D
0x383a9d728  mov     esi, 7FFFh
0x383a9d72d  mov     ecx, esi
0x383a9d72f  mov     rax, rbp
0x383a9d732  mov     edx, r14d
0x383a9d735  cmp     [rax], dx
0x383a9d738  jz      short loc_383A9D745
0x383a9d73a  add     rax, 2
0x383a9d73e  dec     rcx
0x383a9d741  jnz     short loc_383A9D735
0x383a9d743  jmp     short loc_383A9D74A
0x383a9d745  test    rcx, rcx
0x383a9d748  jnz     short loc_383A9D754
0x383a9d74a  mov     edx, 80070057h
0x383a9d74f  mov     rsi, r14
0x383a9d752  jmp     short loc_383A9D757
0x383a9d754  sub     rsi, rcx
0x383a9d757  test    edx, edx
0x383a9d759  jns     short loc_383A9D7A2
0x383a9d75b  jmp     short loc_383A9D762
0x383a9d75d  mov     edx, 80070057h
0x383a9d762  mov     rsi, r14
0x383a9d765  test    edx, edx
0x383a9d767  jns     short loc_383A9D7A2
0x383a9d769  test    byte ptr cs:_bidGblFlags, 2
0x383a9d770  jz      short loc_383A9D79D
0x383a9d772  mov     rax, cs:off_383B4A260; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x383a9d779  test    rax, rax
0x383a9d77c  jz      short loc_383A9D79D
0x383a9d77e  mov     r9d, 0C000000Dh
0x383a9d784  mov     r8, cs:off_383B4A260; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x383a9d78b  mov     edx, 47000h
0x383a9d790  mov     rcx, cs:off_383B43530; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a9d797  call    _bidTraceW
0x383a9d79c  nop
0x383a9d79d  jmp     loc_383A9DC13
0x383a9d7a2  lea     rcx, [rsp+78h+Uuid]; Uuid
0x383a9d7a7  call    cs:__imp_UuidCreate
0x383a9d7ad  mov     edi, eax
0x383a9d7af  test    eax, eax
0x383a9d7b1  jz      loc_383A9D848
0x383a9d7b7  cmp     eax, 720h
0x383a9d7bc  jz      loc_383A9D848
0x383a9d7c2  test    byte ptr cs:_bidGblFlags, 2
0x383a9d7c9  jz      short loc_383A9D806
0x383a9d7cb  mov     rax, cs:off_383B4A220; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x383a9d7d2  test    rax, rax
0x383a9d7d5  jz      short loc_383A9D806
0x383a9d7d7  test    edi, edi
0x383a9d7d9  jg      short loc_383A9D7DF
0x383a9d7db  mov     eax, edi
0x383a9d7dd  jmp     short loc_383A9D7E7
0x383a9d7df  movzx   eax, di
0x383a9d7e2  or      eax, 0C0070000h
0x383a9d7e7  mov     dword ptr [rsp+78h+var_58], eax
0x383a9d7eb  mov     r9d, edi
0x383a9d7ee  mov     r8, cs:off_383B4A220; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x383a9d7f5  mov     edx, 4A000h
0x383a9d7fa  mov     rcx, cs:off_383B43530; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a9d801  call    _bidTraceW
0x383a9d806  test    edi, edi
0x383a9d808  jle     short loc_383A9D813
0x383a9d80a  movzx   edi, di
0x383a9d80d  or      edi, 0C0070000h
0x383a9d813  cmp     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFFh
0x383a9d819  jz      short loc_383A9D841
0x383a9d81b  test    byte ptr cs:_bidGblFlags, 4
0x383a9d822  jz      short loc_383A9D841
0x383a9d824  mov     rcx, cs:_bidID
0x383a9d82b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383a9d82f  jz      short loc_383A9D841
0x383a9d831  lea     r9, [rsp+78h+var_48]
0x383a9d836  xor     r8d, r8d
0x383a9d839  xor     edx, edx
0x383a9d83b  call    cs:off_383B15058
0x383a9d841  mov     eax, edi
0x383a9d843  jmp     loc_383A9DC46
0x383a9d848  cmp     rsi, 1
0x383a9d84c  jb      loc_383A9DBDF
0x383a9d852  cmp     word ptr [rbp+0], 5Ch ; '\'
0x383a9d857  jnz     loc_383A9DBDF
0x383a9d85d  lea     rdi, [rsi+27h]
0x383a9d861  lea     rcx, [rdi+rdi]; Size
0x383a9d865  call    cs:__imp_malloc
0x383a9d86b  mov     [rbx+8], rax
0x383a9d86f  test    rax, rax
0x383a9d872  jnz     short loc_383A9D8E0
0x383a9d874  test    byte ptr cs:_bidGblFlags, 2
0x383a9d87b  jz      short loc_383A9D8A8
0x383a9d87d  mov     rax, cs:off_383B4A1D0; "<FilestreamNtPath::InitializeNtPath|MEM"...
0x383a9d884  test    rax, rax
0x383a9d887  jz      short loc_383A9D8A8
0x383a9d889  mov     r9d, 0C0000017h
0x383a9d88f  mov     r8, cs:off_383B4A1D0; "<FilestreamNtPath::InitializeNtPath|MEM"...
0x383a9d896  mov     edx, 53C00h
0x383a9d89b  mov     rcx, cs:off_383B43530; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a9d8a2  call    _bidTraceW
0x383a9d8a7  nop
0x383a9d8a8  cmp     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFFh
0x383a9d8ae  jz      short loc_383A9D8D6
0x383a9d8b0  test    byte ptr cs:_bidGblFlags, 4
0x383a9d8b7  jz      short loc_383A9D8D6
0x383a9d8b9  mov     rcx, cs:_bidID
0x383a9d8c0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383a9d8c4  jz      short loc_383A9D8D6
0x383a9d8c6  lea     r9, [rsp+78h+var_48]
0x383a9d8cb  xor     r8d, r8d
0x383a9d8ce  xor     edx, edx
0x383a9d8d0  call    cs:off_383B15058
0x383a9d8d6  mov     eax, 0C0000017h
0x383a9d8db  jmp     loc_383A9DC46
0x383a9d8e0  mov     [rbx], r14w
0x383a9d8e4  add     di, di
0x383a9d8e7  mov     [rbx+2], di
0x383a9d8eb  mov     rcx, rbx; struct _UNICODE_STRING *
0x383a9d8ee  call    ?RtlUnicodeStringCchCopyStringN@@YAJPEAU_UNICODE_STRING@@PEBG_K@Z; RtlUnicodeStringCchCopyStringN(_UNICODE_STRING *,ushort const *,unsigned __int64)
0x383a9d8f3  mov     edi, eax
0x383a9d8f5  test    eax, eax
0x383a9d8f7  jz      short loc_383A9D92F
0x383a9d8f9  test    byte ptr cs:_bidGblFlags, 2
0x383a9d900  jz      short loc_383A9D92A
0x383a9d902  mov     rcx, cs:off_383B4A248; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x383a9d909  test    rcx, rcx
0x383a9d90c  jz      short loc_383A9D92A
0x383a9d90e  mov     r9d, eax
0x383a9d911  mov     r8, cs:off_383B4A248; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x383a9d918  mov     edx, 57C00h
0x383a9d91d  mov     rcx, cs:off_383B43530; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a9d924  call    _bidTraceW
0x383a9d929  nop
0x383a9d92a  jmp     loc_383A9D813
0x383a9d92f  lea     r8, [rsi-1]; unsigned __int64
0x383a9d933  lea     rdx, [rbp+2]; unsigned __int16 *
0x383a9d937  mov     rcx, rbx; struct _UNICODE_STRING *
0x383a9d93a  call    ?RtlUnicodeStringCchCatStringN@@YAJPEAU_UNICODE_STRING@@PEBG_K@Z; RtlUnicodeStringCchCatStringN(_UNICODE_STRING *,ushort const *,unsigned __int64)
0x383a9d93f  mov     edi, eax
0x383a9d941  test    eax, eax
0x383a9d943  jz      short loc_383A9D97B
0x383a9d945  test    byte ptr cs:_bidGblFlags, 2
0x383a9d94c  jz      short loc_383A9D976
0x383a9d94e  mov     rcx, cs:off_383B4A1E0; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x383a9d955  test    rcx, rcx
0x383a9d958  jz      short loc_383A9D976
0x383a9d95a  mov     r9d, eax
0x383a9d95d  mov     r8, cs:off_383B4A1E0; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x383a9d964  mov     edx, 5B400h
0x383a9d969  mov     rcx, cs:off_383B43530; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a9d970  call    _bidTraceW
0x383a9d975  nop
0x383a9d976  jmp     loc_383A9D813
0x383a9d97b  mov     r8d, 1; unsigned __int64
0x383a9d981  lea     rdx, asc_38391A060; "\\"
0x383a9d988  mov     rcx, rbx; struct _UNICODE_STRING *
0x383a9d98b  call    ?RtlUnicodeStringCchCatStringN@@YAJPEAU_UNICODE_STRING@@PEBG_K@Z; RtlUnicodeStringCchCatStringN(_UNICODE_STRING *,ushort const *,unsigned __int64)
0x383a9d990  mov     edi, eax
0x383a9d992  test    eax, eax
0x383a9d994  jz      short loc_383A9D9CC
0x383a9d996  test    byte ptr cs:_bidGblFlags, 2
0x383a9d99d  jz      short loc_383A9D9C7
0x383a9d99f  mov     rcx, cs:off_383B4A218; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x383a9d9a6  test    rcx, rcx
0x383a9d9a9  jz      short loc_383A9D9C7
0x383a9d9ab  mov     r9d, eax
0x383a9d9ae  mov     r8, cs:off_383B4A218; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x383a9d9b5  mov     edx, 5EC00h
0x383a9d9ba  mov     rcx, cs:off_383B43530; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a9d9c1  call    _bidTraceW
0x383a9d9c6  nop
0x383a9d9c7  jmp     loc_383A9D813
0x383a9d9cc  movzx   ecx, word ptr [rbx]
0x383a9d9cf  add     rcx, 40h ; '@'
0x383a9d9d3  movzx   eax, word ptr [rbx+2]
0x383a9d9d7  cmp     rcx, rax
0x383a9d9da  jbe     short loc_383A9DA48
0x383a9d9dc  test    byte ptr cs:_bidGblFlags, 2
0x383a9d9e3  jz      short loc_383A9DA10
0x383a9d9e5  mov     rax, cs:off_383B4A238; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x383a9d9ec  test    rax, rax
0x383a9d9ef  jz      short loc_383A9DA10
0x383a9d9f1  mov     r9d, 80000005h
0x383a9d9f7  mov     r8, cs:off_383B4A238; "<FilestreamNtPath::InitializeNtPath|ERR"...
0x383a9d9fe  mov     edx, 61800h
0x383a9da03  mov     rcx, cs:off_383B43530; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a9da0a  call    _bidTraceW
0x383a9da0f  nop
0x383a9da10  cmp     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFFh
0x383a9da16  jz      short loc_383A9DA3E
0x383a9da18  test    byte ptr cs:_bidGblFlags, 4
0x383a9da1f  jz      short loc_383A9DA3E
0x383a9da21  mov     rcx, cs:_bidID
0x383a9da28  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383a9da2c  jz      short loc_383A9DA3E
0x383a9da2e  lea     r9, [rsp+78h+var_48]
0x383a9da33  xor     r8d, r8d
0x383a9da36  xor     edx, edx
0x383a9da38  call    cs:off_383B15058
0x383a9da3e  mov     eax, 80000005h
0x383a9da43  jmp     loc_383A9DC46
0x383a9da48  lea     r8, [rsp+78h+Uuid.Data1+1]
0x383a9da4d  mov     r9d, 4
0x383a9da53  lea     r10, a0123456789abcd; "0123456789ABCDEF"
0x383a9da5a  nop     word ptr [rax+rax+00h]
0x383a9da60  movzx   eax, byte ptr [r8-1]
0x383a9da65  shr     rax, 4
0x383a9da69  movzx   edx, word ptr [rbx]
0x383a9da6c  shr     rdx, 1
0x383a9da6f  mov     rcx, [rbx+8]
0x383a9da73  movzx   eax, word ptr [r10+rax*2]
0x383a9da78  mov     [rcx+rdx*2], ax
0x383a9da7c  add     word ptr [rbx], 2
0x383a9da80  movzx   edx, word ptr [rbx]
0x383a9da83  movzx   eax, byte ptr [r8-1]
0x383a9da88  and     eax, 0Fh
0x383a9da8b  shr     rdx, 1
0x383a9da8e  mov     rcx, [rbx+8]
0x383a9da92  movzx   eax, word ptr [r10+rax*2]
0x383a9da97  mov     [rcx+rdx*2], ax
0x383a9da9b  add     word ptr [rbx], 2
0x383a9da9f  movzx   edx, word ptr [rbx]
0x383a9daa2  movzx   eax, byte ptr [r8]
0x383a9daa6  shr     rax, 4
0x383a9daaa  shr     rdx, 1
0x383a9daad  mov     rcx, [rbx+8]
0x383a9dab1  movzx   eax, word ptr [r10+rax*2]
0x383a9dab6  mov     [rcx+rdx*2], ax
0x383a9daba  add     word ptr [rbx], 2
0x383a9dabe  movzx   edx, word ptr [rbx]
0x383a9dac1  movzx   eax, byte ptr [r8]
0x383a9dac5  and     eax, 0Fh
0x383a9dac8  shr     rdx, 1
0x383a9dacb  mov     rcx, [rbx+8]
0x383a9dacf  movzx   eax, word ptr [r10+rax*2]
0x383a9dad4  mov     [rcx+rdx*2], ax
0x383a9dad8  add     word ptr [rbx], 2
0x383a9dadc  movzx   edx, word ptr [rbx]
0x383a9dadf  movzx   eax, byte ptr [r8+1]
0x383a9dae4  shr     rax, 4
0x383a9dae8  shr     rdx, 1
0x383a9daeb  mov     rcx, [rbx+8]
0x383a9daef  movzx   eax, word ptr [r10+rax*2]
0x383a9daf4  mov     [rcx+rdx*2], ax
0x383a9daf8  add     word ptr [rbx], 2
0x383a9dafc  movzx   edx, word ptr [rbx]
0x383a9daff  movzx   eax, byte ptr [r8+1]
0x383a9db04  and     eax, 0Fh
0x383a9db07  shr     rdx, 1
0x383a9db0a  mov     rcx, [rbx+8]
0x383a9db0e  movzx   eax, word ptr [r10+rax*2]
0x383a9db13  mov     [rcx+rdx*2], ax
0x383a9db17  add     word ptr [rbx], 2
0x383a9db1b  movzx   edx, word ptr [rbx]
0x383a9db1e  movzx   eax, byte ptr [r8+2]
0x383a9db23  shr     rax, 4
0x383a9db27  shr     rdx, 1
0x383a9db2a  mov     rcx, [rbx+8]
0x383a9db2e  movzx   eax, word ptr [r10+rax*2]
0x383a9db33  mov     [rcx+rdx*2], ax
0x383a9db37  add     word ptr [rbx], 2
0x383a9db3b  movzx   edx, word ptr [rbx]
0x383a9db3e  movzx   eax, byte ptr [r8+2]
0x383a9db43  and     eax, 0Fh
0x383a9db46  shr     rdx, 1
0x383a9db49  mov     rcx, [rbx+8]
0x383a9db4d  movzx   eax, word ptr [r10+rax*2]
0x383a9db52  mov     [rcx+rdx*2], ax
0x383a9db56  add     word ptr [rbx], 2
0x383a9db5a  add     r8, 4
0x383a9db5e  dec     r9
0x383a9db61  jnz     loc_383A9DA60
0x383a9db67  test    byte ptr cs:_bidGblFlags, 2
0x383a9db6e  jz      short loc_383A9DBAD
0x383a9db70  mov     rax, cs:off_383B4A1D8; "<FilestreamNtPath::InitializeNtPath|RET"...
0x383a9db77  test    rax, rax
0x383a9db7a  jz      short loc_383A9DBAD
0x383a9db7c  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
