# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18004861c`
- end: `0x18004885e`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `578`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180049120`

## callees

- `0x1800321f0`
- `0x18003d940`
- `0x18003ffec`
- `0x1800400b4`
- `0x180045cb4`
- `0x18004861c`
- `0x18004d834`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004873e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004873e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800486ee`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800487c7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800487f0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800486ee`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800487c7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800487f0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004876b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004876b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800486a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800486a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800486be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048828`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800486be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048828`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  LPWSTR v11; // rax
  const unsigned __int16 *v12; // rdx
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rsi
  __int64 v15; // rcx
  int v16; // eax
  LPCWSTR v17; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v19; // rdx
  __int64 v20; // r8
  int v21; // ebx
  const WCHAR *j; // rax
  unsigned int v23; // ebx
  unsigned __int16 *v24; // rcx
  __int64 v25; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v27; // [rsp+30h] [rbp-39h] BYREF
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
  if ( v7 < 100 )
    v7 = 1000;
  LODWORD(v25) = 0;
  HIDWORD(v25) = v7;
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
  for ( *this = v4; ; *this = v4 )
  {
    if ( !*v4 )
    {
      v23 = 0;
      v24 = (unsigned __int16 *)pv;
      pv = 0;
      *a3 = v24;
      goto LABEL_40;
    }
    if ( *v4 == 37 )
      break;
    v12 = v4;
LABEL_34:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v25, v12, 1) )
    {
LABEL_38:
      v23 = -2147024882;
      goto LABEL_40;
    }
LABEL_35:
    v4 = CharNextW(*this);
  }
  v11 = CharNextW(v4);
  *this = v11;
  if ( *v11 == 37 )
  {
    v12 = v11;
    goto LABEL_34;
  }
  v13 = ATL::CRegParser::StrChrW(v11, 0x25u);
  v14 = v13;
  if ( v13 )
  {
    v15 = v13 - *this;
    if ( v15 > 31 )
    {
      v23 = -2147467259;
      goto LABEL_40;
    }
    v16 = _o_wcsncpy_s(String2, 32, *this, (int)v15, v25);
    ATL::AtlCrtErrorCheck(v16);
    v17 = this[1];
    for ( i = 0; (signed int)i < *((_DWORD *)v17 + 6); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v17 + 1) + 8LL * (int)i), String2) )
      {
        if ( i == -1 )
          break;
        v19 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                            v17 + 4,
                                            i);
        if ( !v19 )
          break;
        v27 = 0;
        v20 = -1;
        do
          ++v20;
        while ( v19[v20] );
        v21 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v25, v19, v20);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v27);
        if ( v21 )
        {
          for ( j = *this; j != v14; *this = j )
            j = CharNextW(j);
          goto LABEL_35;
        }
        goto LABEL_38;
      }
    }
  }
  v23 = -2147352567;
LABEL_40:
  CoTaskMemFree(pv);
  return v23;
}

```

## disassembly

```asm
0x18004861c  mov     [rsp-8+arg_8], rbx
0x180048621  push    rbp
0x180048622  push    rsi
0x180048623  push    rdi
0x180048624  push    r12
0x180048626  push    r13
0x180048628  push    r14
0x18004862a  push    r15
0x18004862c  lea     rbp, [rsp-27h]
0x180048631  sub     rsp, 90h
0x180048638  mov     rax, cs:__security_cookie
0x18004863f  xor     rax, rsp
0x180048642  mov     [rbp+57h+var_40], rax
0x180048646  mov     r15, r8
0x180048649  mov     rbx, rdx
0x18004864c  mov     rdi, rcx
0x18004864f  xor     r12d, r12d
0x180048652  test    rdx, rdx
0x180048655  jz      loc_180048832
0x18004865b  test    r8, r8
0x18004865e  jz      loc_180048832
0x180048664  mov     [r8], r12
0x180048667  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004866b  inc     rax
0x18004866e  cmp     [rdx+rax*2], r12w
0x180048673  jnz     short loc_18004866B
0x180048675  add     eax, eax
0x180048677  mov     ecx, 3E8h
0x18004867c  cmp     eax, 64h ; 'd'
0x18004867f  cmovl   eax, ecx
0x180048682  mov     [rbp+57h+var_A0], r12d
0x180048686  mov     [rbp+57h+var_9C], eax
0x180048689  mov     ecx, eax
0x18004868b  add     rcx, rcx
0x18004868e  mov     eax, 0FFFFFFFFh
0x180048693  cmp     rcx, rax
0x180048696  jbe     short loc_1800486A1
0x180048698  mov     rax, r12
0x18004869b  mov     [rbp+57h+pv], r12
0x18004869f  jmp     short loc_1800486B6
0x1800486a1  mov     ecx, ecx; cb
0x1800486a3  call    cs:__imp_CoTaskMemAlloc
0x1800486a9  mov     [rbp+57h+pv], rax
0x1800486ad  test    rax, rax
0x1800486b0  jz      short loc_1800486B6
0x1800486b2  mov     [rax], r12w
0x1800486b6  test    rax, rax
0x1800486b9  jnz     short loc_1800486CE
0x1800486bb  mov     rcx, rax; pv
0x1800486be  call    cs:__imp_CoTaskMemFree
0x1800486c4  mov     eax, 8007000Eh
0x1800486c9  jmp     loc_180048837
0x1800486ce  mov     [rdi], rbx
0x1800486d1  mov     r13d, 25h ; '%'
0x1800486d7  cmp     [rbx], r12w
0x1800486db  jz      loc_180048816
0x1800486e1  cmp     [rbx], r13w
0x1800486e5  jnz     loc_1800487D7
0x1800486eb  mov     rcx, rbx; lpsz
0x1800486ee  call    cs:__imp_CharNextW
0x1800486f4  mov     [rdi], rax
0x1800486f7  cmp     [rax], r13w
0x1800486fb  jnz     short loc_180048705
0x1800486fd  mov     rdx, rax
0x180048700  jmp     loc_1800487DA
0x180048705  mov     edx, r13d; unsigned __int16
0x180048708  mov     rcx, rax; lpsz
0x18004870b  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180048710  mov     rsi, rax
0x180048713  test    rax, rax
0x180048716  jz      loc_180048808
0x18004871c  mov     rcx, rax
0x18004871f  sub     rcx, [rdi]
0x180048722  sar     rcx, 1
0x180048725  cmp     rcx, 1Fh
0x180048729  jg      loc_180048801
0x18004872f  movsxd  r9, ecx
0x180048732  mov     r8, [rdi]
0x180048735  mov     edx, 20h ; ' '
0x18004873a  lea     rcx, [rbp+57h+String2]
0x18004873e  call    cs:__imp__o_wcsncpy_s
0x180048744  mov     ecx, eax; int
0x180048746  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18004874b  mov     r14, [rdi+8]
0x18004874f  mov     ebx, r12d
0x180048752  cmp     ebx, [r14+18h]
0x180048756  jge     loc_180048808
0x18004875c  movsxd  rax, ebx
0x18004875f  mov     rcx, [r14+8]
0x180048763  lea     rdx, [rbp+57h+String2]; lpString2
0x180048767  mov     rcx, [rcx+rax*8]; lpString1
0x18004876b  call    cs:__imp_lstrcmpiW
0x180048771  test    eax, eax
0x180048773  jz      short loc_180048779
0x180048775  inc     ebx
0x180048777  jmp     short loc_180048752
0x180048779  cmp     ebx, 0FFFFFFFFh
0x18004877c  jz      loc_180048808
0x180048782  mov     edx, ebx
0x180048784  lea     rcx, [r14+8]
0x180048788  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18004878d  mov     rdx, [rax]; unsigned __int16 *
0x180048790  test    rdx, rdx
0x180048793  jz      short loc_180048808
0x180048795  mov     [rbp+57h+var_90], r12
0x180048799  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004879d  inc     r8; int
0x1800487a0  cmp     [rdx+r8*2], r12w
0x1800487a5  jnz     short loc_18004879D
0x1800487a7  lea     rcx, [rbp+57h+var_A0]; this
0x1800487ab  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800487b0  mov     ebx, eax
0x1800487b2  lea     rcx, [rbp+57h+var_90]
0x1800487b6  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800487bb  test    ebx, ebx
0x1800487bd  jz      short loc_18004880F
0x1800487bf  mov     rax, [rdi]
0x1800487c2  jmp     short loc_1800487D0
0x1800487c4  mov     rcx, rax; lpsz
0x1800487c7  call    cs:__imp_CharNextW
0x1800487cd  mov     [rdi], rax
0x1800487d0  cmp     rax, rsi
0x1800487d3  jnz     short loc_1800487C4
0x1800487d5  jmp     short loc_1800487ED
0x1800487d7  mov     rdx, rbx; unsigned __int16 *
0x1800487da  mov     r8d, 1; int
0x1800487e0  lea     rcx, [rbp+57h+var_A0]; this
0x1800487e4  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800487e9  test    eax, eax
0x1800487eb  jz      short loc_18004880F
0x1800487ed  mov     rcx, [rdi]; lpsz
0x1800487f0  call    cs:__imp_CharNextW
0x1800487f6  mov     rbx, rax
0x1800487f9  mov     [rdi], rax
0x1800487fc  jmp     loc_1800486D7
0x180048801  mov     ebx, 80004005h
0x180048806  jmp     short loc_180048824
0x180048808  mov     ebx, 80020009h
0x18004880d  jmp     short loc_180048824
0x18004880f  mov     ebx, 8007000Eh
0x180048814  jmp     short loc_180048824
0x180048816  mov     ebx, r12d
0x180048819  mov     rcx, [rbp+57h+pv]
0x18004881d  mov     [rbp+57h+pv], r12
0x180048821  mov     [r15], rcx
0x180048824  mov     rcx, [rbp+57h+pv]; pv
0x180048828  call    cs:__imp_CoTaskMemFree
0x18004882e  mov     eax, ebx
0x180048830  jmp     short loc_180048837
0x180048832  mov     eax, 80004003h
0x180048837  mov     rcx, [rbp+57h+var_40]
0x18004883b  xor     rcx, rsp; StackCookie
0x18004883e  call    __security_check_cookie
0x180048843  mov     rbx, [rsp+0C0h+arg_8]
0x18004884b  add     rsp, 90h
0x180048852  pop     r15
0x180048854  pop     r14
0x180048856  pop     r13
0x180048858  pop     r12
0x18004885a  pop     rdi
0x18004885b  pop     rsi
0x18004885c  pop     rbp
0x18004885d  retn
```
