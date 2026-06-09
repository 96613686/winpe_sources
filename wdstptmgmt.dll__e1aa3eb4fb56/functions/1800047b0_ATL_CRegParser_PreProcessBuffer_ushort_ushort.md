# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800047b0`
- end: `0x1800049e7`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `567`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180004b10`

## callees

- `0x180002ae8`
- `0x180003580`
- `0x1800037ac`
- `0x1800047b0`
- `0x180005658`
- `0x1800056a4`
- `0x18001e9f0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800048e1`
- `msvcrt!wcsncpy_s` at `0x1800048e1`
- `USER32!CharNextW` at `0x18000488b`
- `USER32!CharNextW` at `0x18000493f`
- `USER32!CharNextW` at `0x18000496e`
- `USER32!CharNextW` at `0x18000488b`
- `USER32!CharNextW` at `0x18000493f`
- `USER32!CharNextW` at `0x18000496e`
- `ole32!CoTaskMemAlloc` at `0x180004836`
- `ole32!CoTaskMemAlloc` at `0x180004836`
- `ole32!CoTaskMemFree` at `0x180004856`
- `ole32!CoTaskMemFree` at `0x1800049a9`
- `ole32!CoTaskMemFree` at `0x180004856`
- `ole32!CoTaskMemFree` at `0x1800049a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  unsigned int v6; // edi
  __int64 v7; // rax
  int v8; // eax
  unsigned __int64 v9; // rcx
  _WORD *v10; // rax
  LPWSTR v12; // rax
  const unsigned __int16 *v13; // rdx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r14
  __int64 v16; // rcx
  errno_t v17; // eax
  const unsigned __int16 *v18; // rax
  __int64 v19; // r8
  int v20; // ebx
  const WCHAR *i; // rax
  unsigned __int16 *v22; // rcx
  _DWORD v23[2]; // [rsp+20h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v25; // [rsp+30h] [rbp-29h] BYREF
  wchar_t Destination[32]; // [rsp+40h] [rbp-19h] BYREF

  v4 = a2;
  v6 = 0;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v8 = 2 * v7;
  if ( v8 < 100 )
    v8 = 1000;
  v23[0] = 0;
  v23[1] = v8;
  v9 = 2LL * (unsigned int)v8;
  if ( v9 <= 0xFFFFFFFF )
  {
    v10 = CoTaskMemAlloc((unsigned int)v9);
    pv = v10;
    if ( v10 )
      *v10 = 0;
  }
  else
  {
    v10 = 0;
    pv = 0;
  }
  if ( !v10 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v13 = v4;
LABEL_29:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v23, v13, 1) )
        goto LABEL_33;
      goto LABEL_30;
    }
    v12 = CharNextW(v4);
    *(_QWORD *)this = v12;
    if ( *v12 == 37 )
    {
      v13 = v12;
      goto LABEL_29;
    }
    v14 = ATL::CRegParser::StrChrW(v12, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_32;
    v16 = ((__int64)v14 - *(_QWORD *)this) >> 1;
    if ( v16 > 31 )
    {
      v6 = -2147467259;
      goto LABEL_35;
    }
    v17 = wcsncpy_s(Destination, 0x20u, *(const wchar_t **)this, (int)v16);
    ATL::AtlCrtErrorCheck(v17);
    v18 = ATL::CRegObject::StrFromMap(*((ATL::CRegObject **)this + 1), Destination);
    if ( !v18 )
    {
LABEL_32:
      v6 = -2147352567;
      goto LABEL_35;
    }
    v25 = 0;
    v19 = -1;
    do
      ++v19;
    while ( v18[v19] );
    v20 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v23, v18, v19);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v25);
    if ( !v20 )
    {
LABEL_33:
      v6 = -2147024882;
      goto LABEL_35;
    }
    for ( i = *(const WCHAR **)this; i != v15; *(_QWORD *)this = i )
      i = CharNextW(i);
LABEL_30:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  v22 = (unsigned __int16 *)pv;
  pv = 0;
  *a3 = v22;
LABEL_35:
  CoTaskMemFree(pv);
  return v6;
}

```

## disassembly

```asm
0x1800047b0  mov     [rsp-8+arg_8], rbx
0x1800047b5  mov     [rsp-8+arg_18], rsi
0x1800047ba  push    rbp
0x1800047bb  push    rdi
0x1800047bc  push    r12
0x1800047be  push    r14
0x1800047c0  push    r15
0x1800047c2  lea     rbp, [rsp-37h]
0x1800047c7  sub     rsp, 90h
0x1800047ce  mov     rax, cs:__security_cookie
0x1800047d5  xor     rax, rsp
0x1800047d8  mov     [rbp+57h+var_30], rax
0x1800047dc  mov     r15, r8
0x1800047df  mov     rbx, rdx
0x1800047e2  mov     rsi, rcx
0x1800047e5  xor     edi, edi
0x1800047e7  test    rdx, rdx
0x1800047ea  jz      loc_1800049B9
0x1800047f0  test    r8, r8
0x1800047f3  jz      loc_1800049B9
0x1800047f9  mov     [r8], rdi
0x1800047fc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004800  inc     rax
0x180004803  cmp     [rdx+rax*2], di
0x180004807  jnz     short loc_180004800
0x180004809  add     eax, eax
0x18000480b  mov     ecx, 3E8h
0x180004810  cmp     eax, 64h ; 'd'
0x180004813  cmovl   eax, ecx
0x180004816  mov     [rbp+57h+var_90], edi
0x180004819  mov     [rbp+57h+var_8C], eax
0x18000481c  mov     ecx, eax
0x18000481e  add     rcx, rcx
0x180004821  mov     eax, 0FFFFFFFFh
0x180004826  cmp     rcx, rax
0x180004829  jbe     short loc_180004834
0x18000482b  mov     rax, rdi
0x18000482e  mov     [rbp+57h+pv], rdi
0x180004832  jmp     short loc_18000484E
0x180004834  mov     ecx, ecx; cb
0x180004836  call    cs:__imp_CoTaskMemAlloc
0x18000483d  nop     dword ptr [rax+rax+00h]
0x180004842  mov     [rbp+57h+pv], rax
0x180004846  test    rax, rax
0x180004849  jz      short loc_18000484E
0x18000484b  mov     [rax], di
0x18000484e  test    rax, rax
0x180004851  jnz     short loc_18000486C
0x180004853  mov     rcx, rax; pv
0x180004856  call    cs:__imp_CoTaskMemFree
0x18000485d  nop     dword ptr [rax+rax+00h]
0x180004862  mov     eax, 8007000Eh
0x180004867  jmp     loc_1800049BE
0x18000486c  mov     [rsi], rbx
0x18000486f  mov     r12d, 25h ; '%'
0x180004875  cmp     [rbx], di
0x180004878  jz      loc_18000499A
0x18000487e  cmp     [rbx], r12w
0x180004882  jnz     loc_180004955
0x180004888  mov     rcx, rbx; lpsz
0x18000488b  call    cs:__imp_CharNextW
0x180004892  nop     dword ptr [rax+rax+00h]
0x180004897  mov     [rsi], rax
0x18000489a  cmp     [rax], r12w
0x18000489e  jnz     short loc_1800048A8
0x1800048a0  mov     rdx, rax
0x1800048a3  jmp     loc_180004958
0x1800048a8  mov     edx, r12d; unsigned __int16
0x1800048ab  mov     rcx, rax; lpsz
0x1800048ae  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800048b3  mov     r14, rax
0x1800048b6  test    rax, rax
0x1800048b9  jz      loc_18000498C
0x1800048bf  mov     rcx, rax
0x1800048c2  sub     rcx, [rsi]
0x1800048c5  sar     rcx, 1
0x1800048c8  cmp     rcx, 1Fh
0x1800048cc  jg      loc_180004985
0x1800048d2  movsxd  r9, ecx; MaxCount
0x1800048d5  mov     r8, [rsi]; Source
0x1800048d8  mov     edx, 20h ; ' '; SizeInWords
0x1800048dd  lea     rcx, [rbp+57h+Destination]; Destination
0x1800048e1  call    cs:__imp_wcsncpy_s
0x1800048e8  nop     dword ptr [rax+rax+00h]
0x1800048ed  mov     ecx, eax; int
0x1800048ef  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800048f4  lea     rdx, [rbp+57h+Destination]; unsigned __int16 *
0x1800048f8  mov     rcx, [rsi+8]; this
0x1800048fc  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x180004901  test    rax, rax
0x180004904  jz      loc_18000498C
0x18000490a  mov     [rbp+57h+var_80], rdi
0x18000490e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180004912  inc     r8; int
0x180004915  cmp     [rax+r8*2], di
0x18000491a  jnz     short loc_180004912
0x18000491c  mov     rdx, rax; unsigned __int16 *
0x18000491f  lea     rcx, [rbp+57h+var_90]; this
0x180004923  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180004928  mov     ebx, eax
0x18000492a  lea     rcx, [rbp+57h+var_80]
0x18000492e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180004933  test    ebx, ebx
0x180004935  jz      short loc_180004993
0x180004937  mov     rax, [rsi]
0x18000493a  jmp     short loc_18000494E
0x18000493c  mov     rcx, rax; lpsz
0x18000493f  call    cs:__imp_CharNextW
0x180004946  nop     dword ptr [rax+rax+00h]
0x18000494b  mov     [rsi], rax
0x18000494e  cmp     rax, r14
0x180004951  jnz     short loc_18000493C
0x180004953  jmp     short loc_18000496B
0x180004955  mov     rdx, rbx; unsigned __int16 *
0x180004958  mov     r8d, 1; int
0x18000495e  lea     rcx, [rbp+57h+var_90]; this
0x180004962  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180004967  test    eax, eax
0x180004969  jz      short loc_180004993
0x18000496b  mov     rcx, [rsi]; lpsz
0x18000496e  call    cs:__imp_CharNextW
0x180004975  nop     dword ptr [rax+rax+00h]
0x18000497a  mov     rbx, rax
0x18000497d  mov     [rsi], rax
0x180004980  jmp     loc_180004875
0x180004985  mov     edi, 80004005h
0x18000498a  jmp     short loc_1800049A5
0x18000498c  mov     edi, 80020009h
0x180004991  jmp     short loc_1800049A5
0x180004993  mov     edi, 8007000Eh
0x180004998  jmp     short loc_1800049A5
0x18000499a  mov     rcx, [rbp+57h+pv]
0x18000499e  mov     [rbp+57h+pv], rdi
0x1800049a2  mov     [r15], rcx
0x1800049a5  mov     rcx, [rbp+57h+pv]; pv
0x1800049a9  call    cs:__imp_CoTaskMemFree
0x1800049b0  nop     dword ptr [rax+rax+00h]
0x1800049b5  mov     eax, edi
0x1800049b7  jmp     short loc_1800049BE
0x1800049b9  mov     eax, 80004003h
0x1800049be  mov     rcx, [rbp+57h+var_30]
0x1800049c2  xor     rcx, rsp; StackCookie
0x1800049c5  call    __security_check_cookie
0x1800049ca  lea     r11, [rsp+0B0h+var_20]
0x1800049d2  mov     rbx, [r11+38h]
0x1800049d6  mov     rsi, [r11+48h]
0x1800049da  mov     rsp, r11
0x1800049dd  pop     r15
0x1800049df  pop     r14
0x1800049e1  pop     r12
0x1800049e3  pop     rdi
0x1800049e4  pop     rbp
0x1800049e5  retn
```
