# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800194d0`
- end: `0x18001973d`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `621`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019cfc`

## callees

- `0x180015290`
- `0x1800167cc`
- `0x180016a1c`
- `0x180018d1c`
- `0x1800194d0`
- `0x18001abf8`
- `0x18002dec0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180019613`
- `msvcrt!wcsncpy_s` at `0x180019613`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019674`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019674`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001962b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001962b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001957b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019707`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001957b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019707`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019560`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019560`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800195a9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800196b8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800196ce`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800195a9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800196b8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800196ce`
- `KERNEL32!lstrcmpiW` at `0x18001964c`
- `KERNEL32!lstrcmpiW` at `0x18001964c`

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
  _DWORD v27[2]; // [rsp+28h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-41h]
  _QWORD *v29[2]; // [rsp+38h] [rbp-39h] BYREF
  wchar_t Destination[32]; // [rsp+48h] [rbp-29h] BYREF

  v29[1] = (_QWORD *)-2LL;
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
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v12, 1) )
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
    v29[0] = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v29);
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
0x1800194d0  mov     rax, rsp
0x1800194d3  push    rbp
0x1800194d4  push    rsi
0x1800194d5  push    rdi
0x1800194d6  push    r12
0x1800194d8  push    r13
0x1800194da  push    r14
0x1800194dc  push    r15
0x1800194de  lea     rbp, [rax-5Fh]
0x1800194e2  sub     rsp, 90h
0x1800194e9  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x1800194f1  mov     [rax+10h], rbx
0x1800194f5  mov     rax, cs:__security_cookie
0x1800194fc  xor     rax, rsp
0x1800194ff  mov     [rbp+57h+var_40], rax
0x180019503  mov     r15, r8
0x180019506  mov     rbx, rdx
0x180019509  mov     rdi, rcx
0x18001950c  xor     r13d, r13d
0x18001950f  test    rdx, rdx
0x180019512  jz      loc_180019711
0x180019518  test    r8, r8
0x18001951b  jz      loc_180019711
0x180019521  mov     [r8], r13
0x180019524  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019528  inc     rax
0x18001952b  cmp     [rdx+rax*2], r13w
0x180019530  jnz     short loc_180019528
0x180019532  add     eax, eax
0x180019534  mov     ecx, 3E8h
0x180019539  cmp     eax, 64h ; 'd'
0x18001953c  cmovl   eax, ecx
0x18001953f  mov     [rbp+57h+var_A0], r13d
0x180019543  mov     [rbp+57h+var_9C], eax
0x180019546  mov     ecx, eax
0x180019548  add     rcx, rcx
0x18001954b  mov     eax, 0FFFFFFFFh
0x180019550  cmp     rcx, rax
0x180019553  jbe     short loc_18001955E
0x180019555  mov     rax, r13
0x180019558  mov     [rbp+57h+pv], r13
0x18001955c  jmp     short loc_180019573
0x18001955e  mov     ecx, ecx; cb
0x180019560  call    cs:__imp_CoTaskMemAlloc
0x180019566  mov     [rbp+57h+pv], rax
0x18001956a  test    rax, rax
0x18001956d  jz      short loc_180019573
0x18001956f  mov     [rax], r13w
0x180019573  test    rax, rax
0x180019576  jnz     short loc_18001958B
0x180019578  mov     rcx, rax; pv
0x18001957b  call    cs:__imp_CoTaskMemFree
0x180019581  mov     eax, 8007000Eh
0x180019586  jmp     loc_180019716
0x18001958b  mov     [rdi], rbx
0x18001958e  mov     esi, 25h ; '%'
0x180019593  cmp     [rbx], r13w
0x180019597  jz      loc_1800196F5
0x18001959d  cmp     [rbx], si
0x1800195a0  jnz     loc_1800196DF
0x1800195a6  mov     rcx, rbx; lpsz
0x1800195a9  call    cs:__imp_CharNextW
0x1800195af  mov     [rdi], rax
0x1800195b2  cmp     [rax], si
0x1800195b5  jnz     short loc_1800195DB
0x1800195b7  mov     rdx, rax; unsigned __int16 *
0x1800195ba  mov     r8d, 1; int
0x1800195c0  lea     rcx, [rbp+57h+var_A0]; this
0x1800195c4  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800195c9  test    eax, eax
0x1800195cb  jnz     loc_1800196CB
0x1800195d1  mov     ebx, 8007000Eh
0x1800195d6  jmp     loc_180019703
0x1800195db  mov     edx, esi; unsigned __int16
0x1800195dd  mov     rcx, rax; lpsz
0x1800195e0  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800195e5  mov     rsi, rax
0x1800195e8  test    rax, rax
0x1800195eb  jz      loc_1800196EE
0x1800195f1  mov     rcx, rax
0x1800195f4  sub     rcx, [rdi]
0x1800195f7  sar     rcx, 1
0x1800195fa  cmp     rcx, 1Fh
0x1800195fe  jg      loc_1800196E7
0x180019604  movsxd  r9, ecx; MaxCount
0x180019607  mov     r8, [rdi]; Source
0x18001960a  mov     edx, 20h ; ' '; SizeInWords
0x18001960f  lea     rcx, [rbp+57h+Destination]; Destination
0x180019613  call    cs:__imp_wcsncpy_s
0x180019619  mov     ecx, eax; int
0x18001961b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180019620  mov     rbx, [rdi+8]
0x180019624  lea     r12, [rbx+20h]
0x180019628  mov     rcx, r12; lpCriticalSection
0x18001962b  call    cs:__imp_EnterCriticalSection
0x180019631  lea     r14, [rbx+8]
0x180019635  mov     ebx, r13d
0x180019638  cmp     ebx, [r14+10h]
0x18001963c  jge     short loc_18001966E
0x18001963e  movsxd  rax, ebx
0x180019641  mov     rcx, [r14]
0x180019644  lea     rdx, [rbp+57h+Destination]; lpString2
0x180019648  mov     rcx, [rcx+rax*8]; lpString1
0x18001964c  call    cs:__imp_lstrcmpiW
0x180019652  test    eax, eax
0x180019654  jz      short loc_18001965A
0x180019656  inc     ebx
0x180019658  jmp     short loc_180019638
0x18001965a  cmp     ebx, 0FFFFFFFFh
0x18001965d  jz      short loc_18001966E
0x18001965f  mov     edx, ebx
0x180019661  mov     rcx, r14
0x180019664  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180019669  mov     rbx, [rax]
0x18001966c  jmp     short loc_180019671
0x18001966e  mov     rbx, r13
0x180019671  mov     rcx, r12; lpCriticalSection
0x180019674  call    cs:__imp_LeaveCriticalSection
0x18001967a  test    rbx, rbx
0x18001967d  jz      short loc_1800196EE
0x18001967f  mov     [rbp+57h+var_90], r13
0x180019683  or      r8, 0FFFFFFFFFFFFFFFFh
0x180019687  inc     r8; int
0x18001968a  cmp     [rbx+r8*2], r13w
0x18001968f  jnz     short loc_180019687
0x180019691  mov     rdx, rbx; unsigned __int16 *
0x180019694  lea     rcx, [rbp+57h+var_A0]; this
0x180019698  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18001969d  mov     ebx, eax
0x18001969f  lea     rcx, [rbp+57h+var_90]
0x1800196a3  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800196a8  test    ebx, ebx
0x1800196aa  jz      loc_1800195D1
0x1800196b0  mov     rax, [rdi]
0x1800196b3  jmp     short loc_1800196C1
0x1800196b5  mov     rcx, rax; lpsz
0x1800196b8  call    cs:__imp_CharNextW
0x1800196be  mov     [rdi], rax
0x1800196c1  cmp     rax, rsi
0x1800196c4  jnz     short loc_1800196B5
0x1800196c6  mov     esi, 25h ; '%'
0x1800196cb  mov     rcx, [rdi]; lpsz
0x1800196ce  call    cs:__imp_CharNextW
0x1800196d4  mov     rbx, rax
0x1800196d7  mov     [rdi], rax
0x1800196da  jmp     loc_180019593
0x1800196df  mov     rdx, rbx
0x1800196e2  jmp     loc_1800195BA
0x1800196e7  mov     ebx, 80004005h
0x1800196ec  jmp     short loc_180019703
0x1800196ee  mov     ebx, 80020009h
0x1800196f3  jmp     short loc_180019703
0x1800196f5  mov     ebx, r13d
0x1800196f8  mov     rcx, [rbp+57h+pv]
0x1800196fc  mov     [rbp+57h+pv], r13
0x180019700  mov     [r15], rcx
0x180019703  mov     rcx, [rbp+57h+pv]; pv
0x180019707  call    cs:__imp_CoTaskMemFree
0x18001970d  mov     eax, ebx
0x18001970f  jmp     short loc_180019716
0x180019711  mov     eax, 80004003h
0x180019716  mov     rcx, [rbp+57h+var_40]
0x18001971a  xor     rcx, rsp; StackCookie
0x18001971d  call    __security_check_cookie
0x180019722  mov     rbx, [rsp+0C0h+arg_8]
0x18001972a  add     rsp, 90h
0x180019731  pop     r15
0x180019733  pop     r14
0x180019735  pop     r13
0x180019737  pop     r12
0x180019739  pop     rdi
0x18001973a  pop     rsi
0x18001973b  pop     rbp
0x18001973c  retn
```
