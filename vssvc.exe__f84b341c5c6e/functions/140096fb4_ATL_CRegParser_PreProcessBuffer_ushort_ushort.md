# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x140096fb4`
- end: `0x1400971d7`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `547`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140097560`

## callees

- `0x140091560`
- `0x140093e80`
- `0x14009506c`
- `0x1400951a0`
- `0x140096fb4`
- `0x140098758`
- `0x1400987b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1400970e0`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1400970e0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140097090`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140097138`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140097161`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140097090`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140097138`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140097161`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140097040`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140097040`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14009705e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14009718b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14009705e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14009718b`

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
0x140096fb4  mov     [rsp-8+arg_8], rbx
0x140096fb9  mov     [rsp-8+arg_18], rsi
0x140096fbe  push    rbp
0x140096fbf  push    rdi
0x140096fc0  push    r12
0x140096fc2  push    r14
0x140096fc4  push    r15
0x140096fc6  lea     rbp, [rsp-37h]
0x140096fcb  sub     rsp, 90h
0x140096fd2  mov     rax, cs:__security_cookie
0x140096fd9  xor     rax, rsp
0x140096fdc  mov     [rbp+57h+var_30], rax
0x140096fe0  mov     r14, r8
0x140096fe3  mov     rbx, rdx
0x140096fe6  mov     rdi, rcx
0x140096fe9  xor     r15d, r15d
0x140096fec  test    rdx, rdx
0x140096fef  jz      loc_1400971AA
0x140096ff5  test    r8, r8
0x140096ff8  jz      loc_1400971AA
0x140096ffe  mov     [r8], r15
0x140097001  or      rax, 0FFFFFFFFFFFFFFFFh
0x140097005  inc     rax
0x140097008  cmp     [rdx+rax*2], r15w
0x14009700d  jnz     short loc_140097005
0x14009700f  add     eax, eax
0x140097011  mov     ecx, 3E8h
0x140097016  cmp     eax, 64h ; 'd'
0x140097019  cmovl   eax, ecx
0x14009701c  mov     [rbp+57h+var_90], r15d
0x140097020  mov     [rbp+57h+var_8C], eax
0x140097023  mov     ecx, eax
0x140097025  add     rcx, rcx
0x140097028  mov     eax, 0FFFFFFFFh
0x14009702d  cmp     rcx, rax
0x140097030  jbe     short loc_14009703E
0x140097032  mov     rax, r15
0x140097035  mov     rdx, r15
0x140097038  mov     [rbp+57h+pv], rdx
0x14009703c  jmp     short loc_140097056
0x14009703e  mov     ecx, ecx; cb
0x140097040  call    cs:__imp_CoTaskMemAlloc
0x140097046  mov     rdx, rax
0x140097049  mov     [rbp+57h+pv], rax
0x14009704d  test    rax, rax
0x140097050  jz      short loc_140097056
0x140097052  mov     [rax], r15w
0x140097056  test    rax, rax
0x140097059  jnz     short loc_14009706E
0x14009705b  mov     rcx, rax; pv
0x14009705e  call    cs:__imp_CoTaskMemFree
0x140097064  mov     eax, 8007000Eh
0x140097069  jmp     loc_1400971AF
0x14009706e  mov     [rdi], rbx
0x140097071  movzx   eax, word ptr [rbx]
0x140097074  test    ax, ax
0x140097077  jz      loc_14009717D
0x14009707d  mov     r12d, 25h ; '%'
0x140097083  cmp     ax, r12w
0x140097087  jnz     loc_140097148
0x14009708d  mov     rcx, rbx; lpsz
0x140097090  call    cs:__imp_CharNextW
0x140097096  mov     [rdi], rax
0x140097099  cmp     [rax], r12w
0x14009709d  jnz     short loc_1400970A7
0x14009709f  mov     rdx, rax
0x1400970a2  jmp     loc_14009714B
0x1400970a7  mov     edx, r12d; unsigned __int16
0x1400970aa  mov     rcx, rax; lpsz
0x1400970ad  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1400970b2  mov     rsi, rax
0x1400970b5  test    rax, rax
0x1400970b8  jz      loc_14009719C
0x1400970be  mov     rcx, rax
0x1400970c1  sub     rcx, [rdi]
0x1400970c4  sar     rcx, 1
0x1400970c7  cmp     rcx, 1Fh
0x1400970cb  jg      loc_140097195
0x1400970d1  movsxd  r9, ecx
0x1400970d4  mov     r8, [rdi]
0x1400970d7  mov     edx, 20h ; ' '
0x1400970dc  lea     rcx, [rbp+57h+var_70]
0x1400970e0  call    cs:__imp__o_wcsncpy_s
0x1400970e6  mov     ecx, eax; int
0x1400970e8  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1400970ed  lea     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x1400970f1  mov     rcx, [rdi+8]; this
0x1400970f5  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x1400970fa  test    rax, rax
0x1400970fd  jz      loc_14009719C
0x140097103  mov     [rbp+57h+var_80], r15
0x140097107  or      r8, 0FFFFFFFFFFFFFFFFh
0x14009710b  inc     r8; int
0x14009710e  cmp     [rax+r8*2], r15w
0x140097113  jnz     short loc_14009710B
0x140097115  mov     rdx, rax; unsigned __int16 *
0x140097118  lea     rcx, [rbp+57h+var_90]; this
0x14009711c  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x140097121  mov     ebx, eax
0x140097123  lea     rcx, [rbp+57h+var_80]
0x140097127  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x14009712c  test    ebx, ebx
0x14009712e  jz      short loc_1400971A3
0x140097130  mov     rax, [rdi]
0x140097133  jmp     short loc_140097141
0x140097135  mov     rcx, rax; lpsz
0x140097138  call    cs:__imp_CharNextW
0x14009713e  mov     [rdi], rax
0x140097141  cmp     rax, rsi
0x140097144  jnz     short loc_140097135
0x140097146  jmp     short loc_14009715E
0x140097148  mov     rdx, rbx; unsigned __int16 *
0x14009714b  mov     r8d, 1; int
0x140097151  lea     rcx, [rbp+57h+var_90]; this
0x140097155  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x14009715a  test    eax, eax
0x14009715c  jz      short loc_1400971A3
0x14009715e  mov     rcx, [rdi]; lpsz
0x140097161  call    cs:__imp_CharNextW
0x140097167  mov     rbx, rax
0x14009716a  mov     [rdi], rax
0x14009716d  movzx   eax, word ptr [rax]
0x140097170  test    ax, ax
0x140097173  jnz     loc_140097083
0x140097179  mov     rdx, [rbp+57h+pv]
0x14009717d  mov     ebx, r15d
0x140097180  mov     [rbp+57h+pv], r15
0x140097184  mov     [r14], rdx
0x140097187  mov     rcx, [rbp+57h+pv]; pv
0x14009718b  call    cs:__imp_CoTaskMemFree
0x140097191  mov     eax, ebx
0x140097193  jmp     short loc_1400971AF
0x140097195  mov     ebx, 80004005h
0x14009719a  jmp     short loc_140097187
0x14009719c  mov     ebx, 80020009h
0x1400971a1  jmp     short loc_140097187
0x1400971a3  mov     ebx, 8007000Eh
0x1400971a8  jmp     short loc_140097187
0x1400971aa  mov     eax, 80004003h
0x1400971af  mov     rcx, [rbp+57h+var_30]
0x1400971b3  xor     rcx, rsp; StackCookie
0x1400971b6  call    __security_check_cookie
0x1400971bb  lea     r11, [rsp+0B0h+var_20]
0x1400971c3  mov     rbx, [r11+38h]
0x1400971c7  mov     rsi, [r11+48h]
0x1400971cb  mov     rsp, r11
0x1400971ce  pop     r15
0x1400971d0  pop     r14
0x1400971d2  pop     r12
0x1400971d4  pop     rdi
0x1400971d5  pop     rbp
0x1400971d6  retn
```
