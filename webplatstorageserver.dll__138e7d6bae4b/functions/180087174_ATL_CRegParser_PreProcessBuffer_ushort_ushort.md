# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180087174`
- end: `0x1800873df`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `619`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800875fc`

## callees

- `0x180080fb0`
- `0x180085820`
- `0x1800863b0`
- `0x1800864f0`
- `0x180086e8c`
- `0x180087174`
- `0x180088124`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800872b5`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800872b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800872cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800872cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087316`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087316`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18008724b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18008735a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180087370`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18008724b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18008735a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180087370`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800872ee`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800872ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180087202`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180087202`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008721d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800873a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008721d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800873a9`

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
  _WORD *v9; // rax
  LPWSTR v11; // rax
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // ebx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rsi
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // r12
  __int64 v20; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  int v24; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v26; // rcx
  LPVOID pv[2]; // [rsp+20h] [rbp-49h] BYREF
  __int64 v28; // [rsp+30h] [rbp-39h] BYREF
  WCHAR String2[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  *(_OWORD *)pv = 0;
  if ( v7 < 100 )
    v7 = 1000;
  LODWORD(pv[0]) = 0;
  HIDWORD(pv[0]) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = CoTaskMemAlloc((unsigned int)v8);
    pv[1] = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    pv[1] = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_18:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)pv, v12, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v11 = CharNextW(v4);
    *(_QWORD *)this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_18;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_39;
    v16 = ((__int64)v14 - *(_QWORD *)this) >> 1;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_41;
    }
    v17 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v16, pv[0]);
    ATL::AtlCrtErrorCheck(v17);
    v18 = *((_QWORD *)this + 1);
    v19 = (struct _RTL_CRITICAL_SECTION *)(v18 + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 32));
    v20 = v18 + 8;
    for ( i = 0; (signed int)i < *(_DWORD *)(v20 + 16); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v20 + 8LL * (int)i), String2) )
      {
        if ( i != -1 )
        {
          v22 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                              v20,
                                              i);
          goto LABEL_29;
        }
        break;
      }
    }
    v22 = 0;
LABEL_29:
    LeaveCriticalSection(v19);
    if ( !v22 )
    {
LABEL_39:
      v13 = -2147352567;
      goto LABEL_41;
    }
    v28 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)pv, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v28);
    if ( !v24 )
    {
LABEL_19:
      v13 = -2147024882;
      goto LABEL_41;
    }
    for ( j = *(const WCHAR **)this; j != v15; *(_QWORD *)this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  v13 = 0;
  v26 = (unsigned __int16 *)pv[1];
  pv[1] = 0;
  *a3 = v26;
LABEL_41:
  CoTaskMemFree(pv[1]);
  return v13;
}

```

## disassembly

```asm
0x180087174  mov     [rsp-8+arg_8], rbx
0x180087179  push    rbp
0x18008717a  push    rsi
0x18008717b  push    rdi
0x18008717c  push    r12
0x18008717e  push    r13
0x180087180  push    r14
0x180087182  push    r15
0x180087184  lea     rbp, [rsp-27h]
0x180087189  sub     rsp, 90h
0x180087190  mov     rax, cs:__security_cookie
0x180087197  xor     rax, rsp
0x18008719a  mov     [rbp+57h+var_40], rax
0x18008719e  mov     r15, r8
0x1800871a1  mov     rbx, rdx
0x1800871a4  mov     rdi, rcx
0x1800871a7  xor     r13d, r13d
0x1800871aa  test    rdx, rdx
0x1800871ad  jz      loc_1800873B3
0x1800871b3  test    r8, r8
0x1800871b6  jz      loc_1800873B3
0x1800871bc  mov     [r8], r13
0x1800871bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800871c3  inc     rax
0x1800871c6  cmp     [rdx+rax*2], r13w
0x1800871cb  jnz     short loc_1800871C3
0x1800871cd  add     eax, eax
0x1800871cf  xorps   xmm0, xmm0
0x1800871d2  movups  xmmword ptr [rbp+57h+pv], xmm0
0x1800871d6  mov     ecx, 3E8h
0x1800871db  cmp     eax, 64h ; 'd'
0x1800871de  cmovl   eax, ecx
0x1800871e1  mov     dword ptr [rbp+57h+pv], r13d
0x1800871e5  mov     dword ptr [rbp+57h+pv+4], eax
0x1800871e8  mov     ecx, eax
0x1800871ea  add     rcx, rcx
0x1800871ed  mov     eax, 0FFFFFFFFh
0x1800871f2  cmp     rcx, rax
0x1800871f5  jbe     short loc_180087200
0x1800871f7  mov     rax, r13
0x1800871fa  mov     [rbp+57h+pv+8], r13
0x1800871fe  jmp     short loc_180087215
0x180087200  mov     ecx, ecx; cb
0x180087202  call    cs:__imp_CoTaskMemAlloc
0x180087208  mov     [rbp+57h+pv+8], rax
0x18008720c  test    rax, rax
0x18008720f  jz      short loc_180087215
0x180087211  mov     [rax], r13w
0x180087215  test    rax, rax
0x180087218  jnz     short loc_18008722D
0x18008721a  mov     rcx, rax; pv
0x18008721d  call    cs:__imp_CoTaskMemFree
0x180087223  mov     eax, 8007000Eh
0x180087228  jmp     loc_1800873B8
0x18008722d  mov     [rdi], rbx
0x180087230  mov     esi, 25h ; '%'
0x180087235  cmp     [rbx], r13w
0x180087239  jz      loc_180087397
0x18008723f  cmp     [rbx], si
0x180087242  jnz     loc_180087381
0x180087248  mov     rcx, rbx; lpsz
0x18008724b  call    cs:__imp_CharNextW
0x180087251  mov     [rdi], rax
0x180087254  cmp     [rax], si
0x180087257  jnz     short loc_18008727D
0x180087259  mov     rdx, rax; unsigned __int16 *
0x18008725c  mov     r8d, 1; int
0x180087262  lea     rcx, [rbp+57h+pv]; this
0x180087266  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18008726b  test    eax, eax
0x18008726d  jnz     loc_18008736D
0x180087273  mov     ebx, 8007000Eh
0x180087278  jmp     loc_1800873A5
0x18008727d  mov     edx, esi; unsigned __int16
0x18008727f  mov     rcx, rax; lpsz
0x180087282  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180087287  mov     rsi, rax
0x18008728a  test    rax, rax
0x18008728d  jz      loc_180087390
0x180087293  mov     rcx, rax
0x180087296  sub     rcx, [rdi]
0x180087299  sar     rcx, 1
0x18008729c  cmp     rcx, 1Fh
0x1800872a0  jg      loc_180087389
0x1800872a6  movsxd  r9, ecx
0x1800872a9  mov     r8, [rdi]
0x1800872ac  mov     edx, 20h ; ' '
0x1800872b1  lea     rcx, [rbp+57h+String2]
0x1800872b5  call    cs:__imp__o_wcsncpy_s
0x1800872bb  mov     ecx, eax; int
0x1800872bd  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800872c2  mov     rbx, [rdi+8]
0x1800872c6  lea     r12, [rbx+20h]
0x1800872ca  mov     rcx, r12; lpCriticalSection
0x1800872cd  call    cs:__imp_EnterCriticalSection
0x1800872d3  lea     r14, [rbx+8]
0x1800872d7  mov     ebx, r13d
0x1800872da  cmp     ebx, [r14+10h]
0x1800872de  jge     short loc_180087310
0x1800872e0  movsxd  rax, ebx
0x1800872e3  mov     rcx, [r14]
0x1800872e6  lea     rdx, [rbp+57h+String2]; lpString2
0x1800872ea  mov     rcx, [rcx+rax*8]; lpString1
0x1800872ee  call    cs:__imp_lstrcmpiW
0x1800872f4  test    eax, eax
0x1800872f6  jz      short loc_1800872FC
0x1800872f8  inc     ebx
0x1800872fa  jmp     short loc_1800872DA
0x1800872fc  cmp     ebx, 0FFFFFFFFh
0x1800872ff  jz      short loc_180087310
0x180087301  mov     edx, ebx
0x180087303  mov     rcx, r14
0x180087306  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18008730b  mov     rbx, [rax]
0x18008730e  jmp     short loc_180087313
0x180087310  mov     rbx, r13
0x180087313  mov     rcx, r12; lpCriticalSection
0x180087316  call    cs:__imp_LeaveCriticalSection
0x18008731c  test    rbx, rbx
0x18008731f  jz      short loc_180087390
0x180087321  mov     [rbp+57h+var_90], r13
0x180087325  or      r8, 0FFFFFFFFFFFFFFFFh
0x180087329  inc     r8; int
0x18008732c  cmp     [rbx+r8*2], r13w
0x180087331  jnz     short loc_180087329
0x180087333  mov     rdx, rbx; unsigned __int16 *
0x180087336  lea     rcx, [rbp+57h+pv]; this
0x18008733a  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18008733f  mov     ebx, eax
0x180087341  lea     rcx, [rbp+57h+var_90]
0x180087345  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18008734a  test    ebx, ebx
0x18008734c  jz      loc_180087273
0x180087352  mov     rax, [rdi]
0x180087355  jmp     short loc_180087363
0x180087357  mov     rcx, rax; lpsz
0x18008735a  call    cs:__imp_CharNextW
0x180087360  mov     [rdi], rax
0x180087363  cmp     rax, rsi
0x180087366  jnz     short loc_180087357
0x180087368  mov     esi, 25h ; '%'
0x18008736d  mov     rcx, [rdi]; lpsz
0x180087370  call    cs:__imp_CharNextW
0x180087376  mov     rbx, rax
0x180087379  mov     [rdi], rax
0x18008737c  jmp     loc_180087235
0x180087381  mov     rdx, rbx
0x180087384  jmp     loc_18008725C
0x180087389  mov     ebx, 80004005h
0x18008738e  jmp     short loc_1800873A5
0x180087390  mov     ebx, 80020009h
0x180087395  jmp     short loc_1800873A5
0x180087397  mov     ebx, r13d
0x18008739a  mov     rcx, [rbp+57h+pv+8]
0x18008739e  mov     [rbp+57h+pv+8], r13
0x1800873a2  mov     [r15], rcx
0x1800873a5  mov     rcx, [rbp+57h+pv+8]; pv
0x1800873a9  call    cs:__imp_CoTaskMemFree
0x1800873af  mov     eax, ebx
0x1800873b1  jmp     short loc_1800873B8
0x1800873b3  mov     eax, 80004003h
0x1800873b8  mov     rcx, [rbp+57h+var_40]
0x1800873bc  xor     rcx, rsp; StackCookie
0x1800873bf  call    __security_check_cookie
0x1800873c4  mov     rbx, [rsp+0C0h+arg_8]
0x1800873cc  add     rsp, 90h
0x1800873d3  pop     r15
0x1800873d5  pop     r14
0x1800873d7  pop     r13
0x1800873d9  pop     r12
0x1800873db  pop     rdi
0x1800873dc  pop     rsi
0x1800873dd  pop     rbp
0x1800873de  retn
```
