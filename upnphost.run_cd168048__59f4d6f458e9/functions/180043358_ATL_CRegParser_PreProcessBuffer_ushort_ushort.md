# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180043358`
- end: `0x180043599`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `577`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180044058`

## callees

- `0x18003cb60`
- `0x18003ec5c`
- `0x180040448`
- `0x1800405e0`
- `0x180043358`
- `0x180045a2c`
- `0x180045a8c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180043485`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180043485`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800433f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800433f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800433d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043546`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800433d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043546`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18004342f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800434e7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180043516`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18004342f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800434e7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180043516`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  void *v9; // rcx
  _WORD *v11; // rax
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
  LODWORD(v24) = 0;
  if ( v7 < 100 )
    v7 = 1000;
  HIDWORD(v24) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = 0;
LABEL_9:
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  v11 = CoTaskMemAlloc((unsigned int)v8);
  pv = v11;
  v9 = v11;
  if ( !v11 )
    goto LABEL_9;
  *v11 = 0;
  *(_QWORD *)this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_29:
    v23 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_30;
  }
  while ( v12 != 37 )
  {
    v14 = v4;
LABEL_26:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v24, v14, 1) )
      goto LABEL_33;
LABEL_27:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v9 = pv;
      goto LABEL_29;
    }
  }
  v13 = CharNextW(v4);
  *(_QWORD *)this = v13;
  if ( *v13 == 37 )
  {
    v14 = v13;
    goto LABEL_26;
  }
  v15 = ATL::CRegParser::StrChrW(v13, 0x25u);
  v16 = v15;
  if ( !v15 )
    goto LABEL_32;
  v17 = ((__int64)v15 - *(_QWORD *)this) >> 1;
  if ( v17 > 31 )
  {
    v23 = -2147467259;
    goto LABEL_30;
  }
  v18 = _o_wcsncpy_s(v27, 32, *(_QWORD *)this, (int)v17, v24);
  ATL::AtlCrtErrorCheck(v18);
  v19 = ATL::CRegObject::StrFromMap(*((ATL::CRegObject **)this + 1), v27);
  if ( !v19 )
  {
LABEL_32:
    v23 = -2147352567;
    goto LABEL_30;
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
    goto LABEL_27;
  }
LABEL_33:
  v23 = -2147024882;
LABEL_30:
  CoTaskMemFree(pv);
  return v23;
}

```

## disassembly

```asm
0x180043358  mov     [rsp-8+arg_8], rbx
0x18004335d  mov     [rsp-8+arg_18], rsi
0x180043362  push    rbp
0x180043363  push    rdi
0x180043364  push    r12
0x180043366  push    r14
0x180043368  push    r15
0x18004336a  lea     rbp, [rsp-37h]
0x18004336f  sub     rsp, 90h
0x180043376  mov     rax, cs:__security_cookie
0x18004337d  xor     rax, rsp
0x180043380  mov     [rbp+57h+var_30], rax
0x180043384  xor     r15d, r15d
0x180043387  mov     r14, r8
0x18004338a  mov     rbx, rdx
0x18004338d  mov     rdi, rcx
0x180043390  test    rdx, rdx
0x180043393  jz      loc_18004356B
0x180043399  test    r8, r8
0x18004339c  jz      loc_18004356B
0x1800433a2  mov     [r8], r15
0x1800433a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800433a9  inc     rax
0x1800433ac  cmp     [rdx+rax*2], r15w
0x1800433b1  jnz     short loc_1800433A9
0x1800433b3  add     eax, eax
0x1800433b5  mov     [rbp+57h+var_90], r15d
0x1800433b9  cmp     eax, 64h ; 'd'
0x1800433bc  mov     ecx, 3E8h
0x1800433c1  cmovl   eax, ecx
0x1800433c4  mov     ecx, eax
0x1800433c6  mov     [rbp+57h+var_8C], eax
0x1800433c9  add     rcx, rcx
0x1800433cc  mov     eax, 0FFFFFFFFh
0x1800433d1  cmp     rcx, rax
0x1800433d4  jbe     short loc_1800433EF
0x1800433d6  mov     rcx, r15; pv
0x1800433d9  call    cs:__imp_CoTaskMemFree
0x1800433e0  nop     dword ptr [rax+rax+00h]
0x1800433e5  mov     eax, 8007000Eh
0x1800433ea  jmp     loc_180043570
0x1800433ef  mov     ecx, ecx; cb
0x1800433f1  call    cs:__imp_CoTaskMemAlloc
0x1800433f8  nop     dword ptr [rax+rax+00h]
0x1800433fd  mov     [rbp+57h+pv], rax
0x180043401  mov     rcx, rax
0x180043404  test    rax, rax
0x180043407  jz      short loc_1800433D9
0x180043409  mov     [rax], r15w
0x18004340d  mov     [rdi], rbx
0x180043410  movzx   eax, word ptr [rbx]
0x180043413  test    ax, ax
0x180043416  jz      loc_180043538
0x18004341c  mov     r12d, 25h ; '%'
0x180043422  cmp     ax, r12w
0x180043426  jnz     loc_1800434FD
0x18004342c  mov     rcx, rbx; lpsz
0x18004342f  call    cs:__imp_CharNextW
0x180043436  nop     dword ptr [rax+rax+00h]
0x18004343b  mov     [rdi], rax
0x18004343e  cmp     [rax], r12w
0x180043442  jnz     short loc_18004344C
0x180043444  mov     rdx, rax
0x180043447  jmp     loc_180043500
0x18004344c  mov     edx, r12d; unsigned __int16
0x18004344f  mov     rcx, rax; lpsz
0x180043452  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180043457  mov     rsi, rax
0x18004345a  test    rax, rax
0x18004345d  jz      loc_18004355D
0x180043463  mov     rcx, rax
0x180043466  sub     rcx, [rdi]
0x180043469  sar     rcx, 1
0x18004346c  cmp     rcx, 1Fh
0x180043470  jg      loc_180043556
0x180043476  mov     r8, [rdi]
0x180043479  mov     edx, 20h ; ' '
0x18004347e  movsxd  r9, ecx
0x180043481  lea     rcx, [rbp+57h+var_70]
0x180043485  call    cs:__imp__o_wcsncpy_s
0x18004348c  nop     dword ptr [rax+rax+00h]
0x180043491  mov     ecx, eax; int
0x180043493  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180043498  mov     rcx, [rdi+8]; this
0x18004349c  lea     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x1800434a0  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x1800434a5  test    rax, rax
0x1800434a8  jz      loc_18004355D
0x1800434ae  mov     [rbp+57h+var_80], r15
0x1800434b2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800434b6  inc     r8; int
0x1800434b9  cmp     [rax+r8*2], r15w
0x1800434be  jnz     short loc_1800434B6
0x1800434c0  mov     rdx, rax; unsigned __int16 *
0x1800434c3  lea     rcx, [rbp+57h+var_90]; this
0x1800434c7  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800434cc  lea     rcx, [rbp+57h+var_80]
0x1800434d0  mov     ebx, eax
0x1800434d2  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800434d7  test    ebx, ebx
0x1800434d9  jz      loc_180043564
0x1800434df  mov     rax, [rdi]
0x1800434e2  jmp     short loc_1800434F6
0x1800434e4  mov     rcx, rax; lpsz
0x1800434e7  call    cs:__imp_CharNextW
0x1800434ee  nop     dword ptr [rax+rax+00h]
0x1800434f3  mov     [rdi], rax
0x1800434f6  cmp     rax, rsi
0x1800434f9  jnz     short loc_1800434E4
0x1800434fb  jmp     short loc_180043513
0x1800434fd  mov     rdx, rbx; unsigned __int16 *
0x180043500  mov     r8d, 1; int
0x180043506  lea     rcx, [rbp+57h+var_90]; this
0x18004350a  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18004350f  test    eax, eax
0x180043511  jz      short loc_180043564
0x180043513  mov     rcx, [rdi]; lpsz
0x180043516  call    cs:__imp_CharNextW
0x18004351d  nop     dword ptr [rax+rax+00h]
0x180043522  mov     rbx, rax
0x180043525  mov     [rdi], rax
0x180043528  movzx   eax, word ptr [rax]
0x18004352b  test    ax, ax
0x18004352e  jnz     loc_180043422
0x180043534  mov     rcx, [rbp+57h+pv]
0x180043538  mov     ebx, r15d
0x18004353b  mov     [rbp+57h+pv], r15
0x18004353f  mov     [r14], rcx
0x180043542  mov     rcx, [rbp+57h+pv]; pv
0x180043546  call    cs:__imp_CoTaskMemFree
0x18004354d  nop     dword ptr [rax+rax+00h]
0x180043552  mov     eax, ebx
0x180043554  jmp     short loc_180043570
0x180043556  mov     ebx, 80004005h
0x18004355b  jmp     short loc_180043542
0x18004355d  mov     ebx, 80020009h
0x180043562  jmp     short loc_180043542
0x180043564  mov     ebx, 8007000Eh
0x180043569  jmp     short loc_180043542
0x18004356b  mov     eax, 80004003h
0x180043570  mov     rcx, [rbp+57h+var_30]
0x180043574  xor     rcx, rsp; StackCookie
0x180043577  call    __security_check_cookie
0x18004357c  lea     r11, [rsp+0B0h+var_20]
0x180043584  mov     rbx, [r11+38h]
0x180043588  mov     rsi, [r11+48h]
0x18004358c  mov     rsp, r11
0x18004358f  pop     r15
0x180043591  pop     r14
0x180043593  pop     r12
0x180043595  pop     rdi
0x180043596  pop     rbp
0x180043597  retn
```
