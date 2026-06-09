# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180009274`
- end: `0x1800094d8`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `612`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ab4c`

## callees

- `0x180002cc0`
- `0x1800049b0`
- `0x180004c00`
- `0x180007e8c`
- `0x180009274`
- `0x18000bbb8`
- `0x18002d840`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800093ae`
- `msvcrt!wcsncpy_s` at `0x1800093ae`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009344`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009453`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009469`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009344`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009453`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009469`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800092fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800092fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009316`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800094a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009316`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800094a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800093c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800093c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000940f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000940f`
- `KERNEL32!lstrcmpiW` at `0x1800093e7`
- `KERNEL32!lstrcmpiW` at `0x1800093e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(const wchar_t **this, unsigned __int16 *a2, unsigned __int16 **a3)
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
  errno_t v17; // eax
  const wchar_t *v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // r12
  const wchar_t *v20; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  int v24; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v26; // rcx
  _DWORD v27[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v29; // [rsp+30h] [rbp-39h] BYREF
  wchar_t Destination[32]; // [rsp+40h] [rbp-29h] BYREF

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
  v27[0] = 0;
  v27[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = CoTaskMemAlloc((unsigned int)v8);
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_18:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v12, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v11 = CharNextW(v4);
    *this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_18;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_39;
    v16 = v14 - *this;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_41;
    }
    v17 = wcsncpy_s(Destination, 0x20u, *this, (int)v16);
    ATL::AtlCrtErrorCheck(v17);
    v18 = this[1];
    v19 = (struct _RTL_CRITICAL_SECTION *)(v18 + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
    v20 = v18 + 4;
    for ( i = 0; (signed int)i < *((_DWORD *)v20 + 4); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v20 + 8LL * (int)i), Destination) )
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
    v29 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v29);
    if ( !v24 )
    {
LABEL_19:
      v13 = -2147024882;
      goto LABEL_41;
    }
    for ( j = *this; j != v15; *this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*this);
    *this = v4;
  }
  v13 = 0;
  v26 = (unsigned __int16 *)pv;
  pv = 0;
  *a3 = v26;
LABEL_41:
  CoTaskMemFree(pv);
  return v13;
}

```

## disassembly

```asm
0x180009274  mov     [rsp-8+arg_8], rbx
0x180009279  push    rbp
0x18000927a  push    rsi
0x18000927b  push    rdi
0x18000927c  push    r12
0x18000927e  push    r13
0x180009280  push    r14
0x180009282  push    r15
0x180009284  lea     rbp, [rsp-27h]
0x180009289  sub     rsp, 90h
0x180009290  mov     rax, cs:__security_cookie
0x180009297  xor     rax, rsp
0x18000929a  mov     [rbp+57h+var_40], rax
0x18000929e  mov     r15, r8
0x1800092a1  mov     rbx, rdx
0x1800092a4  mov     rdi, rcx
0x1800092a7  xor     r13d, r13d
0x1800092aa  test    rdx, rdx
0x1800092ad  jz      loc_1800094AC
0x1800092b3  test    r8, r8
0x1800092b6  jz      loc_1800094AC
0x1800092bc  mov     [r8], r13
0x1800092bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800092c3  inc     rax
0x1800092c6  cmp     [rdx+rax*2], r13w
0x1800092cb  jnz     short loc_1800092C3
0x1800092cd  add     eax, eax
0x1800092cf  mov     ecx, 3E8h
0x1800092d4  cmp     eax, 64h ; 'd'
0x1800092d7  cmovl   eax, ecx
0x1800092da  mov     [rbp+57h+var_A0], r13d
0x1800092de  mov     [rbp+57h+var_9C], eax
0x1800092e1  mov     ecx, eax
0x1800092e3  add     rcx, rcx
0x1800092e6  mov     eax, 0FFFFFFFFh
0x1800092eb  cmp     rcx, rax
0x1800092ee  jbe     short loc_1800092F9
0x1800092f0  mov     rax, r13
0x1800092f3  mov     [rbp+57h+pv], r13
0x1800092f7  jmp     short loc_18000930E
0x1800092f9  mov     ecx, ecx; cb
0x1800092fb  call    cs:__imp_CoTaskMemAlloc
0x180009301  mov     [rbp+57h+pv], rax
0x180009305  test    rax, rax
0x180009308  jz      short loc_18000930E
0x18000930a  mov     [rax], r13w
0x18000930e  test    rax, rax
0x180009311  jnz     short loc_180009326
0x180009313  mov     rcx, rax; pv
0x180009316  call    cs:__imp_CoTaskMemFree
0x18000931c  mov     eax, 8007000Eh
0x180009321  jmp     loc_1800094B1
0x180009326  mov     [rdi], rbx
0x180009329  mov     esi, 25h ; '%'
0x18000932e  cmp     [rbx], r13w
0x180009332  jz      loc_180009490
0x180009338  cmp     [rbx], si
0x18000933b  jnz     loc_18000947A
0x180009341  mov     rcx, rbx; lpsz
0x180009344  call    cs:__imp_CharNextW
0x18000934a  mov     [rdi], rax
0x18000934d  cmp     [rax], si
0x180009350  jnz     short loc_180009376
0x180009352  mov     rdx, rax; unsigned __int16 *
0x180009355  mov     r8d, 1; int
0x18000935b  lea     rcx, [rbp+57h+var_A0]; this
0x18000935f  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180009364  test    eax, eax
0x180009366  jnz     loc_180009466
0x18000936c  mov     ebx, 8007000Eh
0x180009371  jmp     loc_18000949E
0x180009376  mov     edx, esi; unsigned __int16
0x180009378  mov     rcx, rax; lpsz
0x18000937b  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180009380  mov     rsi, rax
0x180009383  test    rax, rax
0x180009386  jz      loc_180009489
0x18000938c  mov     rcx, rax
0x18000938f  sub     rcx, [rdi]
0x180009392  sar     rcx, 1
0x180009395  cmp     rcx, 1Fh
0x180009399  jg      loc_180009482
0x18000939f  movsxd  r9, ecx; MaxCount
0x1800093a2  mov     r8, [rdi]; Source
0x1800093a5  mov     edx, 20h ; ' '; SizeInWords
0x1800093aa  lea     rcx, [rbp+57h+Destination]; Destination
0x1800093ae  call    cs:__imp_wcsncpy_s
0x1800093b4  mov     ecx, eax; int
0x1800093b6  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800093bb  mov     rbx, [rdi+8]
0x1800093bf  lea     r12, [rbx+20h]
0x1800093c3  mov     rcx, r12; lpCriticalSection
0x1800093c6  call    cs:__imp_EnterCriticalSection
0x1800093cc  lea     r14, [rbx+8]
0x1800093d0  mov     ebx, r13d
0x1800093d3  cmp     ebx, [r14+10h]
0x1800093d7  jge     short loc_180009409
0x1800093d9  movsxd  rax, ebx
0x1800093dc  mov     rcx, [r14]
0x1800093df  lea     rdx, [rbp+57h+Destination]; lpString2
0x1800093e3  mov     rcx, [rcx+rax*8]; lpString1
0x1800093e7  call    cs:__imp_lstrcmpiW
0x1800093ed  test    eax, eax
0x1800093ef  jz      short loc_1800093F5
0x1800093f1  inc     ebx
0x1800093f3  jmp     short loc_1800093D3
0x1800093f5  cmp     ebx, 0FFFFFFFFh
0x1800093f8  jz      short loc_180009409
0x1800093fa  mov     edx, ebx
0x1800093fc  mov     rcx, r14
0x1800093ff  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180009404  mov     rbx, [rax]
0x180009407  jmp     short loc_18000940C
0x180009409  mov     rbx, r13
0x18000940c  mov     rcx, r12; lpCriticalSection
0x18000940f  call    cs:__imp_LeaveCriticalSection
0x180009415  test    rbx, rbx
0x180009418  jz      short loc_180009489
0x18000941a  mov     [rbp+57h+var_90], r13
0x18000941e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009422  inc     r8; int
0x180009425  cmp     [rbx+r8*2], r13w
0x18000942a  jnz     short loc_180009422
0x18000942c  mov     rdx, rbx; unsigned __int16 *
0x18000942f  lea     rcx, [rbp+57h+var_A0]; this
0x180009433  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180009438  mov     ebx, eax
0x18000943a  lea     rcx, [rbp+57h+var_90]
0x18000943e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009443  test    ebx, ebx
0x180009445  jz      loc_18000936C
0x18000944b  mov     rax, [rdi]
0x18000944e  jmp     short loc_18000945C
0x180009450  mov     rcx, rax; lpsz
0x180009453  call    cs:__imp_CharNextW
0x180009459  mov     [rdi], rax
0x18000945c  cmp     rax, rsi
0x18000945f  jnz     short loc_180009450
0x180009461  mov     esi, 25h ; '%'
0x180009466  mov     rcx, [rdi]; lpsz
0x180009469  call    cs:__imp_CharNextW
0x18000946f  mov     rbx, rax
0x180009472  mov     [rdi], rax
0x180009475  jmp     loc_18000932E
0x18000947a  mov     rdx, rbx
0x18000947d  jmp     loc_180009355
0x180009482  mov     ebx, 80004005h
0x180009487  jmp     short loc_18000949E
0x180009489  mov     ebx, 80020009h
0x18000948e  jmp     short loc_18000949E
0x180009490  mov     ebx, r13d
0x180009493  mov     rcx, [rbp+57h+pv]
0x180009497  mov     [rbp+57h+pv], r13
0x18000949b  mov     [r15], rcx
0x18000949e  mov     rcx, [rbp+57h+pv]; pv
0x1800094a2  call    cs:__imp_CoTaskMemFree
0x1800094a8  mov     eax, ebx
0x1800094aa  jmp     short loc_1800094B1
0x1800094ac  mov     eax, 80004003h
0x1800094b1  mov     rcx, [rbp+57h+var_40]
0x1800094b5  xor     rcx, rsp; StackCookie
0x1800094b8  call    __security_check_cookie
0x1800094bd  mov     rbx, [rsp+0C0h+arg_8]
0x1800094c5  add     rsp, 90h
0x1800094cc  pop     r15
0x1800094ce  pop     r14
0x1800094d0  pop     r13
0x1800094d2  pop     r12
0x1800094d4  pop     rdi
0x1800094d5  pop     rsi
0x1800094d6  pop     rbp
0x1800094d7  retn
```
