# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180030434`
- end: `0x180030657`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `547`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800307ac`

## callees

- `0x180019a20`
- `0x18002f054`
- `0x18002f9dc`
- `0x18002fb10`
- `0x180030434`
- `0x1800312c4`
- `0x18003131c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180030560`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180030560`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180030510`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800305b8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800305e1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180030510`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800305b8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800305e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800304c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800304c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800304de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003060b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800304de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003060b`

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
0x180030434  mov     [rsp-8+arg_8], rbx
0x180030439  mov     [rsp-8+arg_18], rsi
0x18003043e  push    rbp
0x18003043f  push    rdi
0x180030440  push    r12
0x180030442  push    r14
0x180030444  push    r15
0x180030446  lea     rbp, [rsp-37h]
0x18003044b  sub     rsp, 90h
0x180030452  mov     rax, cs:__security_cookie
0x180030459  xor     rax, rsp
0x18003045c  mov     [rbp+57h+var_30], rax
0x180030460  mov     r14, r8
0x180030463  mov     rbx, rdx
0x180030466  mov     rdi, rcx
0x180030469  xor     r15d, r15d
0x18003046c  test    rdx, rdx
0x18003046f  jz      loc_18003062A
0x180030475  test    r8, r8
0x180030478  jz      loc_18003062A
0x18003047e  mov     [r8], r15
0x180030481  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030485  inc     rax
0x180030488  cmp     [rdx+rax*2], r15w
0x18003048d  jnz     short loc_180030485
0x18003048f  add     eax, eax
0x180030491  mov     ecx, 3E8h
0x180030496  cmp     eax, 64h ; 'd'
0x180030499  cmovl   eax, ecx
0x18003049c  mov     [rbp+57h+var_90], r15d
0x1800304a0  mov     [rbp+57h+var_8C], eax
0x1800304a3  mov     ecx, eax
0x1800304a5  add     rcx, rcx
0x1800304a8  mov     eax, 0FFFFFFFFh
0x1800304ad  cmp     rcx, rax
0x1800304b0  jbe     short loc_1800304BE
0x1800304b2  mov     rax, r15
0x1800304b5  mov     rdx, r15
0x1800304b8  mov     [rbp+57h+pv], rdx
0x1800304bc  jmp     short loc_1800304D6
0x1800304be  mov     ecx, ecx; cb
0x1800304c0  call    cs:__imp_CoTaskMemAlloc
0x1800304c6  mov     rdx, rax
0x1800304c9  mov     [rbp+57h+pv], rax
0x1800304cd  test    rax, rax
0x1800304d0  jz      short loc_1800304D6
0x1800304d2  mov     [rax], r15w
0x1800304d6  test    rax, rax
0x1800304d9  jnz     short loc_1800304EE
0x1800304db  mov     rcx, rax; pv
0x1800304de  call    cs:__imp_CoTaskMemFree
0x1800304e4  mov     eax, 8007000Eh
0x1800304e9  jmp     loc_18003062F
0x1800304ee  mov     [rdi], rbx
0x1800304f1  movzx   eax, word ptr [rbx]
0x1800304f4  test    ax, ax
0x1800304f7  jz      loc_1800305FD
0x1800304fd  mov     r12d, 25h ; '%'
0x180030503  cmp     ax, r12w
0x180030507  jnz     loc_1800305C8
0x18003050d  mov     rcx, rbx; lpsz
0x180030510  call    cs:__imp_CharNextW
0x180030516  mov     [rdi], rax
0x180030519  cmp     [rax], r12w
0x18003051d  jnz     short loc_180030527
0x18003051f  mov     rdx, rax
0x180030522  jmp     loc_1800305CB
0x180030527  mov     edx, r12d; unsigned __int16
0x18003052a  mov     rcx, rax; lpsz
0x18003052d  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180030532  mov     rsi, rax
0x180030535  test    rax, rax
0x180030538  jz      loc_18003061C
0x18003053e  mov     rcx, rax
0x180030541  sub     rcx, [rdi]
0x180030544  sar     rcx, 1
0x180030547  cmp     rcx, 1Fh
0x18003054b  jg      loc_180030615
0x180030551  movsxd  r9, ecx
0x180030554  mov     r8, [rdi]
0x180030557  mov     edx, 20h ; ' '
0x18003055c  lea     rcx, [rbp+57h+var_70]
0x180030560  call    cs:__imp__o_wcsncpy_s
0x180030566  mov     ecx, eax; int
0x180030568  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18003056d  lea     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x180030571  mov     rcx, [rdi+8]; this
0x180030575  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x18003057a  test    rax, rax
0x18003057d  jz      loc_18003061C
0x180030583  mov     [rbp+57h+var_80], r15
0x180030587  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003058b  inc     r8; int
0x18003058e  cmp     [rax+r8*2], r15w
0x180030593  jnz     short loc_18003058B
0x180030595  mov     rdx, rax; unsigned __int16 *
0x180030598  lea     rcx, [rbp+57h+var_90]; this
0x18003059c  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800305a1  mov     ebx, eax
0x1800305a3  lea     rcx, [rbp+57h+var_80]
0x1800305a7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800305ac  test    ebx, ebx
0x1800305ae  jz      short loc_180030623
0x1800305b0  mov     rax, [rdi]
0x1800305b3  jmp     short loc_1800305C1
0x1800305b5  mov     rcx, rax; lpsz
0x1800305b8  call    cs:__imp_CharNextW
0x1800305be  mov     [rdi], rax
0x1800305c1  cmp     rax, rsi
0x1800305c4  jnz     short loc_1800305B5
0x1800305c6  jmp     short loc_1800305DE
0x1800305c8  mov     rdx, rbx; unsigned __int16 *
0x1800305cb  mov     r8d, 1; int
0x1800305d1  lea     rcx, [rbp+57h+var_90]; this
0x1800305d5  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800305da  test    eax, eax
0x1800305dc  jz      short loc_180030623
0x1800305de  mov     rcx, [rdi]; lpsz
0x1800305e1  call    cs:__imp_CharNextW
0x1800305e7  mov     rbx, rax
0x1800305ea  mov     [rdi], rax
0x1800305ed  movzx   eax, word ptr [rax]
0x1800305f0  test    ax, ax
0x1800305f3  jnz     loc_180030503
0x1800305f9  mov     rdx, [rbp+57h+pv]
0x1800305fd  mov     ebx, r15d
0x180030600  mov     [rbp+57h+pv], r15
0x180030604  mov     [r14], rdx
0x180030607  mov     rcx, [rbp+57h+pv]; pv
0x18003060b  call    cs:__imp_CoTaskMemFree
0x180030611  mov     eax, ebx
0x180030613  jmp     short loc_18003062F
0x180030615  mov     ebx, 80004005h
0x18003061a  jmp     short loc_180030607
0x18003061c  mov     ebx, 80020009h
0x180030621  jmp     short loc_180030607
0x180030623  mov     ebx, 8007000Eh
0x180030628  jmp     short loc_180030607
0x18003062a  mov     eax, 80004003h
0x18003062f  mov     rcx, [rbp+57h+var_30]
0x180030633  xor     rcx, rsp; StackCookie
0x180030636  call    __security_check_cookie
0x18003063b  lea     r11, [rsp+0B0h+var_20]
0x180030643  mov     rbx, [r11+38h]
0x180030647  mov     rsi, [r11+48h]
0x18003064b  mov     rsp, r11
0x18003064e  pop     r15
0x180030650  pop     r14
0x180030652  pop     r12
0x180030654  pop     rdi
0x180030655  pop     rbp
0x180030656  retn
```
