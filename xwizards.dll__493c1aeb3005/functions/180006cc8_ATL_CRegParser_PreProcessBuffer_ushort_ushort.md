# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180006cc8`
- end: `0x180006f2c`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `612`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000758c`

## callees

- `0x180002d78`
- `0x180004148`
- `0x180004324`
- `0x1800067bc`
- `0x180006cc8`
- `0x180008558`
- `0x180032a30`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180006e02`
- `msvcrt!wcsncpy_s` at `0x180006e02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006d4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006d4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006d6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ef6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006d6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ef6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006d98`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006ea7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006ebd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006d98`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006ea7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006ebd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006e3b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006e3b`

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
0x180006cc8  mov     [rsp-8+arg_8], rbx
0x180006ccd  push    rbp
0x180006cce  push    rsi
0x180006ccf  push    rdi
0x180006cd0  push    r12
0x180006cd2  push    r13
0x180006cd4  push    r14
0x180006cd6  push    r15
0x180006cd8  lea     rbp, [rsp-27h]
0x180006cdd  sub     rsp, 90h
0x180006ce4  mov     rax, cs:__security_cookie
0x180006ceb  xor     rax, rsp
0x180006cee  mov     [rbp+57h+var_40], rax
0x180006cf2  mov     r15, r8
0x180006cf5  mov     rbx, rdx
0x180006cf8  mov     rdi, rcx
0x180006cfb  xor     r13d, r13d
0x180006cfe  test    rdx, rdx
0x180006d01  jz      loc_180006F00
0x180006d07  test    r8, r8
0x180006d0a  jz      loc_180006F00
0x180006d10  mov     [r8], r13
0x180006d13  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006d17  inc     rax
0x180006d1a  cmp     [rdx+rax*2], r13w
0x180006d1f  jnz     short loc_180006D17
0x180006d21  add     eax, eax
0x180006d23  mov     ecx, 3E8h
0x180006d28  cmp     eax, 64h ; 'd'
0x180006d2b  cmovl   eax, ecx
0x180006d2e  mov     [rbp+57h+var_A0], r13d
0x180006d32  mov     [rbp+57h+var_9C], eax
0x180006d35  mov     ecx, eax
0x180006d37  add     rcx, rcx
0x180006d3a  mov     eax, 0FFFFFFFFh
0x180006d3f  cmp     rcx, rax
0x180006d42  jbe     short loc_180006D4D
0x180006d44  mov     rax, r13
0x180006d47  mov     [rbp+57h+pv], r13
0x180006d4b  jmp     short loc_180006D62
0x180006d4d  mov     ecx, ecx; cb
0x180006d4f  call    cs:__imp_CoTaskMemAlloc
0x180006d55  mov     [rbp+57h+pv], rax
0x180006d59  test    rax, rax
0x180006d5c  jz      short loc_180006D62
0x180006d5e  mov     [rax], r13w
0x180006d62  test    rax, rax
0x180006d65  jnz     short loc_180006D7A
0x180006d67  mov     rcx, rax; pv
0x180006d6a  call    cs:__imp_CoTaskMemFree
0x180006d70  mov     eax, 8007000Eh
0x180006d75  jmp     loc_180006F05
0x180006d7a  mov     [rdi], rbx
0x180006d7d  mov     esi, 25h ; '%'
0x180006d82  cmp     [rbx], r13w
0x180006d86  jz      loc_180006EE4
0x180006d8c  cmp     [rbx], si
0x180006d8f  jnz     loc_180006ECE
0x180006d95  mov     rcx, rbx; lpsz
0x180006d98  call    cs:__imp_CharNextW
0x180006d9e  mov     [rdi], rax
0x180006da1  cmp     [rax], si
0x180006da4  jnz     short loc_180006DCA
0x180006da6  mov     rdx, rax; unsigned __int16 *
0x180006da9  mov     r8d, 1; int
0x180006daf  lea     rcx, [rbp+57h+var_A0]; this
0x180006db3  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180006db8  test    eax, eax
0x180006dba  jnz     loc_180006EBA
0x180006dc0  mov     ebx, 8007000Eh
0x180006dc5  jmp     loc_180006EF2
0x180006dca  mov     edx, esi; unsigned __int16
0x180006dcc  mov     rcx, rax; lpsz
0x180006dcf  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180006dd4  mov     rsi, rax
0x180006dd7  test    rax, rax
0x180006dda  jz      loc_180006EDD
0x180006de0  mov     rcx, rax
0x180006de3  sub     rcx, [rdi]
0x180006de6  sar     rcx, 1
0x180006de9  cmp     rcx, 1Fh
0x180006ded  jg      loc_180006ED6
0x180006df3  movsxd  r9, ecx; MaxCount
0x180006df6  mov     r8, [rdi]; Source
0x180006df9  mov     edx, 20h ; ' '; SizeInWords
0x180006dfe  lea     rcx, [rbp+57h+Destination]; Destination
0x180006e02  call    cs:__imp_wcsncpy_s
0x180006e08  mov     ecx, eax; int
0x180006e0a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180006e0f  mov     rbx, [rdi+8]
0x180006e13  lea     r12, [rbx+20h]
0x180006e17  mov     rcx, r12; lpCriticalSection
0x180006e1a  call    cs:__imp_EnterCriticalSection
0x180006e20  lea     r14, [rbx+8]
0x180006e24  mov     ebx, r13d
0x180006e27  cmp     ebx, [r14+10h]
0x180006e2b  jge     short loc_180006E5D
0x180006e2d  movsxd  rax, ebx
0x180006e30  mov     rcx, [r14]
0x180006e33  lea     rdx, [rbp+57h+Destination]; lpString2
0x180006e37  mov     rcx, [rcx+rax*8]; lpString1
0x180006e3b  call    cs:__imp_lstrcmpiW
0x180006e41  test    eax, eax
0x180006e43  jz      short loc_180006E49
0x180006e45  inc     ebx
0x180006e47  jmp     short loc_180006E27
0x180006e49  cmp     ebx, 0FFFFFFFFh
0x180006e4c  jz      short loc_180006E5D
0x180006e4e  mov     edx, ebx
0x180006e50  mov     rcx, r14
0x180006e53  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180006e58  mov     rbx, [rax]
0x180006e5b  jmp     short loc_180006E60
0x180006e5d  mov     rbx, r13
0x180006e60  mov     rcx, r12; lpCriticalSection
0x180006e63  call    cs:__imp_LeaveCriticalSection
0x180006e69  test    rbx, rbx
0x180006e6c  jz      short loc_180006EDD
0x180006e6e  mov     [rbp+57h+var_90], r13
0x180006e72  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006e76  inc     r8; int
0x180006e79  cmp     [rbx+r8*2], r13w
0x180006e7e  jnz     short loc_180006E76
0x180006e80  mov     rdx, rbx; unsigned __int16 *
0x180006e83  lea     rcx, [rbp+57h+var_A0]; this
0x180006e87  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180006e8c  mov     ebx, eax
0x180006e8e  lea     rcx, [rbp+57h+var_90]
0x180006e92  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180006e97  test    ebx, ebx
0x180006e99  jz      loc_180006DC0
0x180006e9f  mov     rax, [rdi]
0x180006ea2  jmp     short loc_180006EB0
0x180006ea4  mov     rcx, rax; lpsz
0x180006ea7  call    cs:__imp_CharNextW
0x180006ead  mov     [rdi], rax
0x180006eb0  cmp     rax, rsi
0x180006eb3  jnz     short loc_180006EA4
0x180006eb5  mov     esi, 25h ; '%'
0x180006eba  mov     rcx, [rdi]; lpsz
0x180006ebd  call    cs:__imp_CharNextW
0x180006ec3  mov     rbx, rax
0x180006ec6  mov     [rdi], rax
0x180006ec9  jmp     loc_180006D82
0x180006ece  mov     rdx, rbx
0x180006ed1  jmp     loc_180006DA9
0x180006ed6  mov     ebx, 80004005h
0x180006edb  jmp     short loc_180006EF2
0x180006edd  mov     ebx, 80020009h
0x180006ee2  jmp     short loc_180006EF2
0x180006ee4  mov     ebx, r13d
0x180006ee7  mov     rcx, [rbp+57h+pv]
0x180006eeb  mov     [rbp+57h+pv], r13
0x180006eef  mov     [r15], rcx
0x180006ef2  mov     rcx, [rbp+57h+pv]; pv
0x180006ef6  call    cs:__imp_CoTaskMemFree
0x180006efc  mov     eax, ebx
0x180006efe  jmp     short loc_180006F05
0x180006f00  mov     eax, 80004003h
0x180006f05  mov     rcx, [rbp+57h+var_40]
0x180006f09  xor     rcx, rsp; StackCookie
0x180006f0c  call    __security_check_cookie
0x180006f11  mov     rbx, [rsp+0C0h+arg_8]
0x180006f19  add     rsp, 90h
0x180006f20  pop     r15
0x180006f22  pop     r14
0x180006f24  pop     r13
0x180006f26  pop     r12
0x180006f28  pop     rdi
0x180006f29  pop     rsi
0x180006f2a  pop     rbp
0x180006f2b  retn
```
