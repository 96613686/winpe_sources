# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180007120`
- end: `0x180007343`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `547`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800074dc`

## callees

- `0x180002570`
- `0x180005798`
- `0x1800062dc`
- `0x180006510`
- `0x180007120`
- `0x1800080c0`
- `0x180008118`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000724c`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000724c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800071ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800071ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800071ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800072f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800071ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800072f7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800071fc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800072a4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800072cd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800071fc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800072a4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800072cd`

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
  _DWORD v24[2]; // [rsp+20h] [rbp-39h] BYREF
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
  v24[0] = 0;
  v24[1] = v7;
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
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v14, 1) )
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
  v18 = _o_wcsncpy_s(v27, 32, *(_QWORD *)this, (int)v17);
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
  v21 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v19, v20);
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
0x180007120  mov     [rsp-8+arg_8], rbx
0x180007125  mov     [rsp-8+arg_18], rsi
0x18000712a  push    rbp
0x18000712b  push    rdi
0x18000712c  push    r12
0x18000712e  push    r14
0x180007130  push    r15
0x180007132  lea     rbp, [rsp-37h]
0x180007137  sub     rsp, 90h
0x18000713e  mov     rax, cs:__security_cookie
0x180007145  xor     rax, rsp
0x180007148  mov     [rbp+57h+var_30], rax
0x18000714c  mov     r14, r8
0x18000714f  mov     rbx, rdx
0x180007152  mov     rdi, rcx
0x180007155  xor     r15d, r15d
0x180007158  test    rdx, rdx
0x18000715b  jz      loc_180007316
0x180007161  test    r8, r8
0x180007164  jz      loc_180007316
0x18000716a  mov     [r8], r15
0x18000716d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007171  inc     rax
0x180007174  cmp     [rdx+rax*2], r15w
0x180007179  jnz     short loc_180007171
0x18000717b  add     eax, eax
0x18000717d  mov     ecx, 3E8h
0x180007182  cmp     eax, 64h ; 'd'
0x180007185  cmovl   eax, ecx
0x180007188  mov     [rbp+57h+var_90], r15d
0x18000718c  mov     [rbp+57h+var_8C], eax
0x18000718f  mov     ecx, eax
0x180007191  add     rcx, rcx
0x180007194  mov     eax, 0FFFFFFFFh
0x180007199  cmp     rcx, rax
0x18000719c  jbe     short loc_1800071AA
0x18000719e  mov     rax, r15
0x1800071a1  mov     rdx, r15
0x1800071a4  mov     [rbp+57h+pv], rdx
0x1800071a8  jmp     short loc_1800071C2
0x1800071aa  mov     ecx, ecx; cb
0x1800071ac  call    cs:__imp_CoTaskMemAlloc
0x1800071b2  mov     rdx, rax
0x1800071b5  mov     [rbp+57h+pv], rax
0x1800071b9  test    rax, rax
0x1800071bc  jz      short loc_1800071C2
0x1800071be  mov     [rax], r15w
0x1800071c2  test    rax, rax
0x1800071c5  jnz     short loc_1800071DA
0x1800071c7  mov     rcx, rax; pv
0x1800071ca  call    cs:__imp_CoTaskMemFree
0x1800071d0  mov     eax, 8007000Eh
0x1800071d5  jmp     loc_18000731B
0x1800071da  mov     [rdi], rbx
0x1800071dd  movzx   eax, word ptr [rbx]
0x1800071e0  test    ax, ax
0x1800071e3  jz      loc_1800072E9
0x1800071e9  mov     r12d, 25h ; '%'
0x1800071ef  cmp     ax, r12w
0x1800071f3  jnz     loc_1800072B4
0x1800071f9  mov     rcx, rbx; lpsz
0x1800071fc  call    cs:__imp_CharNextW
0x180007202  mov     [rdi], rax
0x180007205  cmp     [rax], r12w
0x180007209  jnz     short loc_180007213
0x18000720b  mov     rdx, rax
0x18000720e  jmp     loc_1800072B7
0x180007213  mov     edx, r12d; unsigned __int16
0x180007216  mov     rcx, rax; lpsz
0x180007219  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000721e  mov     rsi, rax
0x180007221  test    rax, rax
0x180007224  jz      loc_180007308
0x18000722a  mov     rcx, rax
0x18000722d  sub     rcx, [rdi]
0x180007230  sar     rcx, 1
0x180007233  cmp     rcx, 1Fh
0x180007237  jg      loc_180007301
0x18000723d  movsxd  r9, ecx
0x180007240  mov     r8, [rdi]
0x180007243  mov     edx, 20h ; ' '
0x180007248  lea     rcx, [rbp+57h+var_70]
0x18000724c  call    cs:__imp__o_wcsncpy_s
0x180007252  mov     ecx, eax; int
0x180007254  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180007259  lea     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x18000725d  mov     rcx, [rdi+8]; this
0x180007261  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x180007266  test    rax, rax
0x180007269  jz      loc_180007308
0x18000726f  mov     [rbp+57h+var_80], r15
0x180007273  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007277  inc     r8; int
0x18000727a  cmp     [rax+r8*2], r15w
0x18000727f  jnz     short loc_180007277
0x180007281  mov     rdx, rax; unsigned __int16 *
0x180007284  lea     rcx, [rbp+57h+var_90]; this
0x180007288  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000728d  mov     ebx, eax
0x18000728f  lea     rcx, [rbp+57h+var_80]
0x180007293  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180007298  test    ebx, ebx
0x18000729a  jz      short loc_18000730F
0x18000729c  mov     rax, [rdi]
0x18000729f  jmp     short loc_1800072AD
0x1800072a1  mov     rcx, rax; lpsz
0x1800072a4  call    cs:__imp_CharNextW
0x1800072aa  mov     [rdi], rax
0x1800072ad  cmp     rax, rsi
0x1800072b0  jnz     short loc_1800072A1
0x1800072b2  jmp     short loc_1800072CA
0x1800072b4  mov     rdx, rbx; unsigned __int16 *
0x1800072b7  mov     r8d, 1; int
0x1800072bd  lea     rcx, [rbp+57h+var_90]; this
0x1800072c1  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800072c6  test    eax, eax
0x1800072c8  jz      short loc_18000730F
0x1800072ca  mov     rcx, [rdi]; lpsz
0x1800072cd  call    cs:__imp_CharNextW
0x1800072d3  mov     rbx, rax
0x1800072d6  mov     [rdi], rax
0x1800072d9  movzx   eax, word ptr [rax]
0x1800072dc  test    ax, ax
0x1800072df  jnz     loc_1800071EF
0x1800072e5  mov     rdx, [rbp+57h+pv]
0x1800072e9  mov     ebx, r15d
0x1800072ec  mov     [rbp+57h+pv], r15
0x1800072f0  mov     [r14], rdx
0x1800072f3  mov     rcx, [rbp+57h+pv]; pv
0x1800072f7  call    cs:__imp_CoTaskMemFree
0x1800072fd  mov     eax, ebx
0x1800072ff  jmp     short loc_18000731B
0x180007301  mov     ebx, 80004005h
0x180007306  jmp     short loc_1800072F3
0x180007308  mov     ebx, 80020009h
0x18000730d  jmp     short loc_1800072F3
0x18000730f  mov     ebx, 8007000Eh
0x180007314  jmp     short loc_1800072F3
0x180007316  mov     eax, 80004003h
0x18000731b  mov     rcx, [rbp+57h+var_30]
0x18000731f  xor     rcx, rsp; StackCookie
0x180007322  call    __security_check_cookie
0x180007327  lea     r11, [rsp+0B0h+var_20]
0x18000732f  mov     rbx, [r11+38h]
0x180007333  mov     rsi, [r11+48h]
0x180007337  mov     rsp, r11
0x18000733a  pop     r15
0x18000733c  pop     r14
0x18000733e  pop     r12
0x180007340  pop     rdi
0x180007341  pop     rbp
0x180007342  retn
```
