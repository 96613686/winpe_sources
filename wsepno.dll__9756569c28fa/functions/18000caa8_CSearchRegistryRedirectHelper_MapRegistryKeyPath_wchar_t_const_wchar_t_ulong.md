# CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)

- ea: `0x18000caa8`
- end: `0x18000cca6`
- name: `?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z`
- size: `510`
- prototype: `__int64 __fastcall(CSearchRegistryRedirectHelper *this, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c9d8`

## callees

- `0x180001770`
- `0x18000a374`
- `0x18000a6bc`
- `0x18000caa8`
- `0x18000ce80`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000cb13`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000cc20`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000cb13`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000cc20`

## string_xrefs

- `0x18000cb84`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`
- `0x18000cbc0`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`

## pseudocode

```c
__int64 __fastcall CSearchRegistryRedirectHelper::MapRegistryKeyPath(
        CSearchRegistryRedirectHelper *this,
        const wchar_t *a2,
        wchar_t *a3)
{
  __int64 v3; // rdi
  const WCHAR *v5; // rbx
  __int64 v6; // r8
  __int64 v8; // rsi
  __int64 v9; // rbp
  wchar_t *v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rax
  wchar_t *v13; // rcx
  wchar_t *v14; // rdx
  unsigned int v15; // edi
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // esi
  __int64 v20; // rdx
  const WCHAR *v21; // r8
  int v22; // edx
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  int v26; // edi
  int bIgnoreCase; // [rsp+20h] [rbp-78h]
  struct _EVENT_DATA_DESCRIPTOR lpString2; // [rsp+30h] [rbp-68h] BYREF
  const WCHAR *v29; // [rsp+40h] [rbp-58h]
  int v30; // [rsp+48h] [rbp-50h]
  int v31; // [rsp+4Ch] [rbp-4Ch]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v3 = -1;
  v5 = a2;
  v6 = 69LL * *(_QWORD *)this;
  v8 = -1;
  v9 = LODWORD(off_180015170[v6 + 2]);
  do
    ++v8;
  while ( a2[v8] );
  if ( (unsigned int)v8 >= (unsigned int)v9 && CompareStringOrdinal(a2, v9, off_180015170[v6 + 1], -1, 1) == 2 )
  {
    v10 = (wchar_t *)((char *)this + 8);
    v11 = 260;
    v12 = 2147483646;
    v13 = a3;
    do
    {
      if ( !v12 )
        break;
      if ( !*v10 )
        break;
      *v13++ = *v10++;
      --v12;
      --v11;
    }
    while ( v11 );
    v14 = v13 - 1;
    v15 = v11 == 0 ? 0x8007007A : 0;
    if ( v11 )
      v14 = v13;
    *v14 = 0;
    if ( v11 )
    {
      if ( (unsigned int)v8 <= (unsigned int)v9 )
        return 0;
      v17 = StringCchCatW(a3, 0x104u, &v5[v9]);
      v18 = v17;
      if ( v17 >= 0 )
      {
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x49,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\regredirect.cxx",
          (const char *)(unsigned int)v17,
          bIgnoreCase);
        return v18;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\regredirect.cxx",
        (const char *)v15,
        bIgnoreCase);
      return v15;
    }
  }
  else
  {
    v19 = 0;
    lpString2.Ptr = (ULONGLONG)L"Software";
    *(_QWORD *)&lpString2.Size = L"System";
    while ( 1 )
    {
      v20 = -1;
      v21 = (const WCHAR *)*(&lpString2.Ptr + v19);
      do
        ++v20;
      while ( v21[v20] );
      if ( CompareStringOrdinal(v5, v20, v21, -1, 1) == 2 )
        break;
      if ( (unsigned int)++v19 >= 2 )
        return 2147500037LL;
    }
    if ( (byte_180015BC2 & 0x20) != 0 )
    {
      if ( v5 )
      {
        do
          ++v3;
        while ( v5[v3] );
        v26 = 2 * v3 + 2;
      }
      else
      {
        v26 = 10;
      }
      v30 = v26;
      v31 = 0;
      if ( !v5 )
        v5 = L"NULL";
      v29 = v5;
      McGenEventWrite_EventWriteTransfer(v23, v22, v24, v25, &lpString2);
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x18000caa8  push    rbx
0x18000caaa  push    rbp
0x18000caab  push    rsi
0x18000caac  push    rdi
0x18000caad  push    r12
0x18000caaf  push    r14
0x18000cab1  push    r15
0x18000cab3  sub     rsp, 60h
0x18000cab7  mov     rax, cs:__security_cookie
0x18000cabe  xor     rax, rsp
0x18000cac1  mov     [rsp+98h+var_48], rax
0x18000cac6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000caca  lea     rax, off_180015170; "WSearch"
0x18000cad1  mov     r14, r8
0x18000cad4  mov     rbx, rdx
0x18000cad7  imul    r8, [rcx], 228h
0x18000cade  mov     r15, rcx
0x18000cae1  mov     rsi, rdi
0x18000cae4  xor     r12d, r12d
0x18000cae7  mov     ebp, [r8+rax+10h]
0x18000caec  inc     rsi
0x18000caef  cmp     [rdx+rsi*2], r12w
0x18000caf4  jnz     short loc_18000CAEC
0x18000caf6  cmp     esi, ebp
0x18000caf8  jb      loc_18000CBE2
0x18000cafe  mov     r8, [r8+rax+8]; lpString2
0x18000cb03  mov     r9d, edi; cchCount2
0x18000cb06  mov     edx, ebp; cchCount1
0x18000cb08  mov     [rsp+98h+bIgnoreCase], 1; int
0x18000cb10  mov     rcx, rbx; lpString1
0x18000cb13  call    cs:__imp_CompareStringOrdinal
0x18000cb19  cmp     eax, 2
0x18000cb1c  jnz     loc_18000CBE2
0x18000cb22  mov     r10d, 104h
0x18000cb28  lea     rdx, [r15+8]
0x18000cb2c  mov     r8d, r10d
0x18000cb2f  mov     eax, 7FFFFFFEh
0x18000cb34  mov     rcx, r14
0x18000cb37  test    rax, rax
0x18000cb3a  jz      short loc_18000CB5B
0x18000cb3c  movzx   r9d, word ptr [rdx]
0x18000cb40  test    r9w, r9w
0x18000cb44  jz      short loc_18000CB5B
0x18000cb46  mov     [rcx], r9w
0x18000cb4a  add     rdx, 2
0x18000cb4e  add     rcx, 2
0x18000cb52  dec     rax
0x18000cb55  sub     r8, 1
0x18000cb59  jnz     short loc_18000CB37
0x18000cb5b  mov     rax, r8
0x18000cb5e  lea     rdx, [rcx-2]
0x18000cb62  neg     rax
0x18000cb65  sbb     edi, edi
0x18000cb67  not     edi
0x18000cb69  and     edi, 8007007Ah
0x18000cb6f  test    r8, r8
0x18000cb72  cmovnz  rdx, rcx
0x18000cb76  mov     [rdx], r12w
0x18000cb7a  jnz     short loc_18000CB9F
0x18000cb7c  mov     rcx, [rsp+98h]; this
0x18000cb84  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\com"...
0x18000cb8b  mov     r9d, edi; char *
0x18000cb8e  mov     edx, 46h ; 'F'; void *
0x18000cb93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb98  mov     eax, edi
0x18000cb9a  jmp     loc_18000CC8A
0x18000cb9f  cmp     esi, ebp
0x18000cba1  jbe     short loc_18000CBDB
0x18000cba3  lea     r8, [rbx+rbp*2]; wchar_t *
0x18000cba7  mov     rdx, r10; unsigned __int64
0x18000cbaa  mov     rcx, r14; wchar_t *
0x18000cbad  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000cbb2  mov     ebx, eax
0x18000cbb4  test    eax, eax
0x18000cbb6  jns     short loc_18000CBDB
0x18000cbb8  mov     rcx, [rsp+98h]; this
0x18000cbc0  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\com"...
0x18000cbc7  mov     r9d, eax; char *
0x18000cbca  mov     edx, 49h ; 'I'; void *
0x18000cbcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cbd4  mov     eax, ebx
0x18000cbd6  jmp     loc_18000CC8A
0x18000cbdb  xor     eax, eax
0x18000cbdd  jmp     loc_18000CC8A
0x18000cbe2  lea     rax, aSoftware; "Software"
0x18000cbe9  mov     esi, r12d
0x18000cbec  mov     [rsp+98h+lpString2], rax
0x18000cbf1  lea     rax, aSystem; "System"
0x18000cbf8  mov     [rsp+98h+var_60], rax
0x18000cbfd  movsxd  rax, esi
0x18000cc00  mov     rdx, rdi
0x18000cc03  mov     r8, [rsp+rax*8+98h+lpString2]; lpString2
0x18000cc08  inc     rdx; cchCount1
0x18000cc0b  cmp     [r8+rdx*2], r12w
0x18000cc10  jnz     short loc_18000CC08
0x18000cc12  mov     r9d, edi; cchCount2
0x18000cc15  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x18000cc1d  mov     rcx, rbx; lpString1
0x18000cc20  call    cs:__imp_CompareStringOrdinal
0x18000cc26  cmp     eax, 2
0x18000cc29  jz      short loc_18000CC34
0x18000cc2b  inc     esi
0x18000cc2d  cmp     esi, 2
0x18000cc30  jb      short loc_18000CBFD
0x18000cc32  jmp     short loc_18000CC85
0x18000cc34  test    cs:byte_180015BC2, 20h
0x18000cc3b  jz      short loc_18000CC85
0x18000cc3d  test    rbx, rbx
0x18000cc40  jz      short loc_18000CC55
0x18000cc42  inc     rdi
0x18000cc45  cmp     [rbx+rdi*2], r12w
0x18000cc4a  jnz     short loc_18000CC42
0x18000cc4c  lea     edi, ds:2[rdi*2]
0x18000cc53  jmp     short loc_18000CC5A
0x18000cc55  mov     edi, 0Ah
0x18000cc5a  test    rbx, rbx
0x18000cc5d  mov     [rsp+98h+var_50], edi
0x18000cc61  lea     rax, aNull; "NULL"
0x18000cc68  mov     [rsp+98h+var_4C], r12d
0x18000cc6d  cmovz   rbx, rax
0x18000cc71  lea     rax, [rsp+98h+lpString2]
0x18000cc76  mov     qword ptr [rsp+98h+bIgnoreCase], rax; PEVENT_DATA_DESCRIPTOR
0x18000cc7b  mov     [rsp+98h+var_58], rbx
0x18000cc80  call    McGenEventWrite_EventWriteTransfer
0x18000cc85  mov     eax, 80004005h
0x18000cc8a  mov     rcx, [rsp+98h+var_48]
0x18000cc8f  xor     rcx, rsp; StackCookie
0x18000cc92  call    __security_check_cookie
0x18000cc97  add     rsp, 60h
0x18000cc9b  pop     r15
0x18000cc9d  pop     r14
0x18000cc9f  pop     r12
0x18000cca1  pop     rdi
0x18000cca2  pop     rsi
0x18000cca3  pop     rbp
0x18000cca4  pop     rbx
0x18000cca5  retn
```
