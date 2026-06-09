# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000b670`
- end: `0x18000b8d4`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `612`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bb2c`

## callees

- `0x180001580`
- `0x180007f50`
- `0x180008c58`
- `0x180008e8c`
- `0x18000a33c`
- `0x18000b670`
- `0x18000ca70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000b7aa`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000b7aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b80b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b80b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b7c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b7c2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b740`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b84f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b865`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b740`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b84f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b865`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000b7e3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000b7e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b712`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b89e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b712`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b89e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b6f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b6f7`

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
  __int64 v27; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v29; // [rsp+30h] [rbp-39h] BYREF
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
  LODWORD(v27) = 0;
  HIDWORD(v27) = v7;
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
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_18:
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v12, 1) )
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
    v17 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v16, v27);
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
    v29 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v29);
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
0x18000b670  mov     [rsp-8+arg_8], rbx
0x18000b675  push    rbp
0x18000b676  push    rsi
0x18000b677  push    rdi
0x18000b678  push    r12
0x18000b67a  push    r13
0x18000b67c  push    r14
0x18000b67e  push    r15
0x18000b680  lea     rbp, [rsp-27h]
0x18000b685  sub     rsp, 90h
0x18000b68c  mov     rax, cs:__security_cookie
0x18000b693  xor     rax, rsp
0x18000b696  mov     [rbp+57h+var_40], rax
0x18000b69a  mov     r15, r8
0x18000b69d  mov     rbx, rdx
0x18000b6a0  mov     rdi, rcx
0x18000b6a3  xor     r13d, r13d
0x18000b6a6  test    rdx, rdx
0x18000b6a9  jz      loc_18000B8A8
0x18000b6af  test    r8, r8
0x18000b6b2  jz      loc_18000B8A8
0x18000b6b8  mov     [r8], r13
0x18000b6bb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b6bf  inc     rax
0x18000b6c2  cmp     [rdx+rax*2], r13w
0x18000b6c7  jnz     short loc_18000B6BF
0x18000b6c9  add     eax, eax
0x18000b6cb  mov     ecx, 3E8h
0x18000b6d0  cmp     eax, 64h ; 'd'
0x18000b6d3  cmovl   eax, ecx
0x18000b6d6  mov     [rbp+57h+var_A0], r13d
0x18000b6da  mov     [rbp+57h+var_9C], eax
0x18000b6dd  mov     ecx, eax
0x18000b6df  add     rcx, rcx
0x18000b6e2  mov     eax, 0FFFFFFFFh
0x18000b6e7  cmp     rcx, rax
0x18000b6ea  jbe     short loc_18000B6F5
0x18000b6ec  mov     rax, r13
0x18000b6ef  mov     [rbp+57h+pv], r13
0x18000b6f3  jmp     short loc_18000B70A
0x18000b6f5  mov     ecx, ecx; cb
0x18000b6f7  call    cs:__imp_CoTaskMemAlloc
0x18000b6fd  mov     [rbp+57h+pv], rax
0x18000b701  test    rax, rax
0x18000b704  jz      short loc_18000B70A
0x18000b706  mov     [rax], r13w
0x18000b70a  test    rax, rax
0x18000b70d  jnz     short loc_18000B722
0x18000b70f  mov     rcx, rax; pv
0x18000b712  call    cs:__imp_CoTaskMemFree
0x18000b718  mov     eax, 8007000Eh
0x18000b71d  jmp     loc_18000B8AD
0x18000b722  mov     [rdi], rbx
0x18000b725  mov     esi, 25h ; '%'
0x18000b72a  cmp     [rbx], r13w
0x18000b72e  jz      loc_18000B88C
0x18000b734  cmp     [rbx], si
0x18000b737  jnz     loc_18000B876
0x18000b73d  mov     rcx, rbx; lpsz
0x18000b740  call    cs:__imp_CharNextW
0x18000b746  mov     [rdi], rax
0x18000b749  cmp     [rax], si
0x18000b74c  jnz     short loc_18000B772
0x18000b74e  mov     rdx, rax; unsigned __int16 *
0x18000b751  mov     r8d, 1; int
0x18000b757  lea     rcx, [rbp+57h+var_A0]; this
0x18000b75b  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000b760  test    eax, eax
0x18000b762  jnz     loc_18000B862
0x18000b768  mov     ebx, 8007000Eh
0x18000b76d  jmp     loc_18000B89A
0x18000b772  mov     edx, esi; unsigned __int16
0x18000b774  mov     rcx, rax; lpsz
0x18000b777  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000b77c  mov     rsi, rax
0x18000b77f  test    rax, rax
0x18000b782  jz      loc_18000B885
0x18000b788  mov     rcx, rax
0x18000b78b  sub     rcx, [rdi]
0x18000b78e  sar     rcx, 1
0x18000b791  cmp     rcx, 1Fh
0x18000b795  jg      loc_18000B87E
0x18000b79b  movsxd  r9, ecx
0x18000b79e  mov     r8, [rdi]
0x18000b7a1  mov     edx, 20h ; ' '
0x18000b7a6  lea     rcx, [rbp+57h+String2]
0x18000b7aa  call    cs:__imp__o_wcsncpy_s
0x18000b7b0  mov     ecx, eax; int
0x18000b7b2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000b7b7  mov     rbx, [rdi+8]
0x18000b7bb  lea     r12, [rbx+20h]
0x18000b7bf  mov     rcx, r12; lpCriticalSection
0x18000b7c2  call    cs:__imp_EnterCriticalSection
0x18000b7c8  lea     r14, [rbx+8]
0x18000b7cc  mov     ebx, r13d
0x18000b7cf  cmp     ebx, [r14+10h]
0x18000b7d3  jge     short loc_18000B805
0x18000b7d5  movsxd  rax, ebx
0x18000b7d8  mov     rcx, [r14]
0x18000b7db  lea     rdx, [rbp+57h+String2]; lpString2
0x18000b7df  mov     rcx, [rcx+rax*8]; lpString1
0x18000b7e3  call    cs:__imp_lstrcmpiW
0x18000b7e9  test    eax, eax
0x18000b7eb  jz      short loc_18000B7F1
0x18000b7ed  inc     ebx
0x18000b7ef  jmp     short loc_18000B7CF
0x18000b7f1  cmp     ebx, 0FFFFFFFFh
0x18000b7f4  jz      short loc_18000B805
0x18000b7f6  mov     edx, ebx
0x18000b7f8  mov     rcx, r14
0x18000b7fb  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18000b800  mov     rbx, [rax]
0x18000b803  jmp     short loc_18000B808
0x18000b805  mov     rbx, r13
0x18000b808  mov     rcx, r12; lpCriticalSection
0x18000b80b  call    cs:__imp_LeaveCriticalSection
0x18000b811  test    rbx, rbx
0x18000b814  jz      short loc_18000B885
0x18000b816  mov     [rbp+57h+var_90], r13
0x18000b81a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000b81e  inc     r8; int
0x18000b821  cmp     [rbx+r8*2], r13w
0x18000b826  jnz     short loc_18000B81E
0x18000b828  mov     rdx, rbx; unsigned __int16 *
0x18000b82b  lea     rcx, [rbp+57h+var_A0]; this
0x18000b82f  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000b834  mov     ebx, eax
0x18000b836  lea     rcx, [rbp+57h+var_90]
0x18000b83a  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000b83f  test    ebx, ebx
0x18000b841  jz      loc_18000B768
0x18000b847  mov     rax, [rdi]
0x18000b84a  jmp     short loc_18000B858
0x18000b84c  mov     rcx, rax; lpsz
0x18000b84f  call    cs:__imp_CharNextW
0x18000b855  mov     [rdi], rax
0x18000b858  cmp     rax, rsi
0x18000b85b  jnz     short loc_18000B84C
0x18000b85d  mov     esi, 25h ; '%'
0x18000b862  mov     rcx, [rdi]; lpsz
0x18000b865  call    cs:__imp_CharNextW
0x18000b86b  mov     rbx, rax
0x18000b86e  mov     [rdi], rax
0x18000b871  jmp     loc_18000B72A
0x18000b876  mov     rdx, rbx
0x18000b879  jmp     loc_18000B751
0x18000b87e  mov     ebx, 80004005h
0x18000b883  jmp     short loc_18000B89A
0x18000b885  mov     ebx, 80020009h
0x18000b88a  jmp     short loc_18000B89A
0x18000b88c  mov     ebx, r13d
0x18000b88f  mov     rcx, [rbp+57h+pv]
0x18000b893  mov     [rbp+57h+pv], r13
0x18000b897  mov     [r15], rcx
0x18000b89a  mov     rcx, [rbp+57h+pv]; pv
0x18000b89e  call    cs:__imp_CoTaskMemFree
0x18000b8a4  mov     eax, ebx
0x18000b8a6  jmp     short loc_18000B8AD
0x18000b8a8  mov     eax, 80004003h
0x18000b8ad  mov     rcx, [rbp+57h+var_40]
0x18000b8b1  xor     rcx, rsp; StackCookie
0x18000b8b4  call    __security_check_cookie
0x18000b8b9  mov     rbx, [rsp+0C0h+arg_8]
0x18000b8c1  add     rsp, 90h
0x18000b8c8  pop     r15
0x18000b8ca  pop     r14
0x18000b8cc  pop     r13
0x18000b8ce  pop     r12
0x18000b8d0  pop     rdi
0x18000b8d1  pop     rsi
0x18000b8d2  pop     rbp
0x18000b8d3  retn
```
