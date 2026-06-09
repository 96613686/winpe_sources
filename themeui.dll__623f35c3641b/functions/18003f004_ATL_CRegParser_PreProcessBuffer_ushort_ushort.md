# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18003f004`
- end: `0x18003f227`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `547`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003f35c`

## callees

- `0x1800358c0`
- `0x18003dea8`
- `0x18003e7a0`
- `0x18003e8d4`
- `0x18003f004`
- `0x18003fdac`
- `0x18003fe04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18003f130`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18003f130`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f090`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f090`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f0ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f1db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f0ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f1db`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003f0e0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003f188`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003f1b1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003f0e0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003f188`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003f1b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdx
  WCHAR v12; // ax
  LPWSTR v13; // rax
  const unsigned __int16 *v14; // rdx
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rsi
  __int64 v17; // rcx
  int v18; // eax
  const unsigned __int16 *v19; // rax
  __int64 v20; // r8
  int v21; // ebx
  const WCHAR *i; // rax
  unsigned int v23; // ebx
  __int64 v24; // [rsp+20h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v26; // [rsp+30h] [rbp-29h] BYREF
  unsigned __int16 v27[32]; // [rsp+40h] [rbp-19h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  if ( v7 < 100 )
    v7 = 1000;
  LODWORD(v24) = 0;
  HIDWORD(v24) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)v8);
    v10 = v9;
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    v10 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_31:
    v23 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_32;
  }
  while ( v12 != 37 )
  {
    v14 = v4;
LABEL_28:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v24, v14, 1) )
      goto LABEL_35;
LABEL_29:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v10 = (unsigned __int16 *)pv;
      goto LABEL_31;
    }
  }
  v13 = CharNextW(v4);
  *(_QWORD *)this = v13;
  if ( *v13 == 37 )
  {
    v14 = v13;
    goto LABEL_28;
  }
  v15 = ATL::CRegParser::StrChrW(v13, 0x25u);
  v16 = v15;
  if ( !v15 )
    goto LABEL_34;
  v17 = ((__int64)v15 - *(_QWORD *)this) >> 1;
  if ( v17 > 31 )
  {
    v23 = -2147467259;
    goto LABEL_32;
  }
  v18 = _o_wcsncpy_s(v27, 32, *(_QWORD *)this, (int)v17, v24);
  ATL::AtlCrtErrorCheck(v18);
  v19 = ATL::CRegObject::StrFromMap(*((ATL::CRegObject **)this + 1), v27);
  if ( !v19 )
  {
LABEL_34:
    v23 = -2147352567;
    goto LABEL_32;
  }
  v26 = 0;
  v20 = -1;
  do
    ++v20;
  while ( v19[v20] );
  v21 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v24, v19, v20);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v26);
  if ( v21 )
  {
    for ( i = *(const WCHAR **)this; i != v16; *(_QWORD *)this = i )
      i = CharNextW(i);
    goto LABEL_29;
  }
LABEL_35:
  v23 = -2147024882;
LABEL_32:
  CoTaskMemFree(pv);
  return v23;
}

```

## disassembly

```asm
0x18003f004  mov     [rsp-8+arg_8], rbx
0x18003f009  mov     [rsp-8+arg_18], rsi
0x18003f00e  push    rbp
0x18003f00f  push    rdi
0x18003f010  push    r12
0x18003f012  push    r14
0x18003f014  push    r15
0x18003f016  lea     rbp, [rsp-37h]
0x18003f01b  sub     rsp, 90h
0x18003f022  mov     rax, cs:__security_cookie
0x18003f029  xor     rax, rsp
0x18003f02c  mov     [rbp+57h+var_30], rax
0x18003f030  mov     r14, r8
0x18003f033  mov     rbx, rdx
0x18003f036  mov     rdi, rcx
0x18003f039  xor     r15d, r15d
0x18003f03c  test    rdx, rdx
0x18003f03f  jz      loc_18003F1FA
0x18003f045  test    r8, r8
0x18003f048  jz      loc_18003F1FA
0x18003f04e  mov     [r8], r15
0x18003f051  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003f055  inc     rax
0x18003f058  cmp     [rdx+rax*2], r15w
0x18003f05d  jnz     short loc_18003F055
0x18003f05f  add     eax, eax
0x18003f061  mov     ecx, 3E8h
0x18003f066  cmp     eax, 64h ; 'd'
0x18003f069  cmovl   eax, ecx
0x18003f06c  mov     [rbp+57h+var_90], r15d
0x18003f070  mov     [rbp+57h+var_8C], eax
0x18003f073  mov     ecx, eax
0x18003f075  add     rcx, rcx
0x18003f078  mov     eax, 0FFFFFFFFh
0x18003f07d  cmp     rcx, rax
0x18003f080  jbe     short loc_18003F08E
0x18003f082  mov     rax, r15
0x18003f085  mov     rdx, r15
0x18003f088  mov     [rbp+57h+pv], rdx
0x18003f08c  jmp     short loc_18003F0A6
0x18003f08e  mov     ecx, ecx; cb
0x18003f090  call    cs:__imp_CoTaskMemAlloc
0x18003f096  mov     rdx, rax
0x18003f099  mov     [rbp+57h+pv], rax
0x18003f09d  test    rax, rax
0x18003f0a0  jz      short loc_18003F0A6
0x18003f0a2  mov     [rax], r15w
0x18003f0a6  test    rax, rax
0x18003f0a9  jnz     short loc_18003F0BE
0x18003f0ab  mov     rcx, rax; pv
0x18003f0ae  call    cs:__imp_CoTaskMemFree
0x18003f0b4  mov     eax, 8007000Eh
0x18003f0b9  jmp     loc_18003F1FF
0x18003f0be  mov     [rdi], rbx
0x18003f0c1  movzx   eax, word ptr [rbx]
0x18003f0c4  test    ax, ax
0x18003f0c7  jz      loc_18003F1CD
0x18003f0cd  mov     r12d, 25h ; '%'
0x18003f0d3  cmp     ax, r12w
0x18003f0d7  jnz     loc_18003F198
0x18003f0dd  mov     rcx, rbx; lpsz
0x18003f0e0  call    cs:__imp_CharNextW
0x18003f0e6  mov     [rdi], rax
0x18003f0e9  cmp     [rax], r12w
0x18003f0ed  jnz     short loc_18003F0F7
0x18003f0ef  mov     rdx, rax
0x18003f0f2  jmp     loc_18003F19B
0x18003f0f7  mov     edx, r12d; unsigned __int16
0x18003f0fa  mov     rcx, rax; lpsz
0x18003f0fd  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18003f102  mov     rsi, rax
0x18003f105  test    rax, rax
0x18003f108  jz      loc_18003F1EC
0x18003f10e  mov     rcx, rax
0x18003f111  sub     rcx, [rdi]
0x18003f114  sar     rcx, 1
0x18003f117  cmp     rcx, 1Fh
0x18003f11b  jg      loc_18003F1E5
0x18003f121  movsxd  r9, ecx
0x18003f124  mov     r8, [rdi]
0x18003f127  mov     edx, 20h ; ' '
0x18003f12c  lea     rcx, [rbp+57h+var_70]
0x18003f130  call    cs:__imp__o_wcsncpy_s
0x18003f136  mov     ecx, eax; int
0x18003f138  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18003f13d  lea     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x18003f141  mov     rcx, [rdi+8]; this
0x18003f145  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x18003f14a  test    rax, rax
0x18003f14d  jz      loc_18003F1EC
0x18003f153  mov     [rbp+57h+var_80], r15
0x18003f157  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003f15b  inc     r8; int
0x18003f15e  cmp     [rax+r8*2], r15w
0x18003f163  jnz     short loc_18003F15B
0x18003f165  mov     rdx, rax; unsigned __int16 *
0x18003f168  lea     rcx, [rbp+57h+var_90]; this
0x18003f16c  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18003f171  mov     ebx, eax
0x18003f173  lea     rcx, [rbp+57h+var_80]
0x18003f177  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18003f17c  test    ebx, ebx
0x18003f17e  jz      short loc_18003F1F3
0x18003f180  mov     rax, [rdi]
0x18003f183  jmp     short loc_18003F191
0x18003f185  mov     rcx, rax; lpsz
0x18003f188  call    cs:__imp_CharNextW
0x18003f18e  mov     [rdi], rax
0x18003f191  cmp     rax, rsi
0x18003f194  jnz     short loc_18003F185
0x18003f196  jmp     short loc_18003F1AE
0x18003f198  mov     rdx, rbx; unsigned __int16 *
0x18003f19b  mov     r8d, 1; int
0x18003f1a1  lea     rcx, [rbp+57h+var_90]; this
0x18003f1a5  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18003f1aa  test    eax, eax
0x18003f1ac  jz      short loc_18003F1F3
0x18003f1ae  mov     rcx, [rdi]; lpsz
0x18003f1b1  call    cs:__imp_CharNextW
0x18003f1b7  mov     rbx, rax
0x18003f1ba  mov     [rdi], rax
0x18003f1bd  movzx   eax, word ptr [rax]
0x18003f1c0  test    ax, ax
0x18003f1c3  jnz     loc_18003F0D3
0x18003f1c9  mov     rdx, [rbp+57h+pv]
0x18003f1cd  mov     ebx, r15d
0x18003f1d0  mov     [rbp+57h+pv], r15
0x18003f1d4  mov     [r14], rdx
0x18003f1d7  mov     rcx, [rbp+57h+pv]; pv
0x18003f1db  call    cs:__imp_CoTaskMemFree
0x18003f1e1  mov     eax, ebx
0x18003f1e3  jmp     short loc_18003F1FF
0x18003f1e5  mov     ebx, 80004005h
0x18003f1ea  jmp     short loc_18003F1D7
0x18003f1ec  mov     ebx, 80020009h
0x18003f1f1  jmp     short loc_18003F1D7
0x18003f1f3  mov     ebx, 8007000Eh
0x18003f1f8  jmp     short loc_18003F1D7
0x18003f1fa  mov     eax, 80004003h
0x18003f1ff  mov     rcx, [rbp+57h+var_30]
0x18003f203  xor     rcx, rsp; StackCookie
0x18003f206  call    __security_check_cookie
0x18003f20b  lea     r11, [rsp+0B0h+var_20]
0x18003f213  mov     rbx, [r11+38h]
0x18003f217  mov     rsi, [r11+48h]
0x18003f21b  mov     rsp, r11
0x18003f21e  pop     r15
0x18003f220  pop     r14
0x18003f222  pop     r12
0x18003f224  pop     rdi
0x18003f225  pop     rbp
0x18003f226  retn
```
