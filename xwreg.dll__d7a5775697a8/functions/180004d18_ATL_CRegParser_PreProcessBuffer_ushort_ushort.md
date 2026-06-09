# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180004d18`
- end: `0x180004f7c`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `612`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000527c`

## callees

- `0x180002b1c`
- `0x180003968`
- `0x180003b44`
- `0x18000492c`
- `0x180004d18`
- `0x180005f2c`
- `0x180012800`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180004e52`
- `msvcrt!wcsncpy_s` at `0x180004e52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004eb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004eb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004e6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004e6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004dba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004f46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004dba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004f46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004d9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004d9f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004de8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004ef7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004f0d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004de8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004ef7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004f0d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004e8b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004e8b`

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
0x180004d18  mov     [rsp-8+arg_8], rbx
0x180004d1d  push    rbp
0x180004d1e  push    rsi
0x180004d1f  push    rdi
0x180004d20  push    r12
0x180004d22  push    r13
0x180004d24  push    r14
0x180004d26  push    r15
0x180004d28  lea     rbp, [rsp-27h]
0x180004d2d  sub     rsp, 90h
0x180004d34  mov     rax, cs:__security_cookie
0x180004d3b  xor     rax, rsp
0x180004d3e  mov     [rbp+57h+var_40], rax
0x180004d42  mov     r15, r8
0x180004d45  mov     rbx, rdx
0x180004d48  mov     rdi, rcx
0x180004d4b  xor     r13d, r13d
0x180004d4e  test    rdx, rdx
0x180004d51  jz      loc_180004F50
0x180004d57  test    r8, r8
0x180004d5a  jz      loc_180004F50
0x180004d60  mov     [r8], r13
0x180004d63  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004d67  inc     rax
0x180004d6a  cmp     [rdx+rax*2], r13w
0x180004d6f  jnz     short loc_180004D67
0x180004d71  add     eax, eax
0x180004d73  mov     ecx, 3E8h
0x180004d78  cmp     eax, 64h ; 'd'
0x180004d7b  cmovl   eax, ecx
0x180004d7e  mov     [rbp+57h+var_A0], r13d
0x180004d82  mov     [rbp+57h+var_9C], eax
0x180004d85  mov     ecx, eax
0x180004d87  add     rcx, rcx
0x180004d8a  mov     eax, 0FFFFFFFFh
0x180004d8f  cmp     rcx, rax
0x180004d92  jbe     short loc_180004D9D
0x180004d94  mov     rax, r13
0x180004d97  mov     [rbp+57h+pv], r13
0x180004d9b  jmp     short loc_180004DB2
0x180004d9d  mov     ecx, ecx; cb
0x180004d9f  call    cs:__imp_CoTaskMemAlloc
0x180004da5  mov     [rbp+57h+pv], rax
0x180004da9  test    rax, rax
0x180004dac  jz      short loc_180004DB2
0x180004dae  mov     [rax], r13w
0x180004db2  test    rax, rax
0x180004db5  jnz     short loc_180004DCA
0x180004db7  mov     rcx, rax; pv
0x180004dba  call    cs:__imp_CoTaskMemFree
0x180004dc0  mov     eax, 8007000Eh
0x180004dc5  jmp     loc_180004F55
0x180004dca  mov     [rdi], rbx
0x180004dcd  mov     esi, 25h ; '%'
0x180004dd2  cmp     [rbx], r13w
0x180004dd6  jz      loc_180004F34
0x180004ddc  cmp     [rbx], si
0x180004ddf  jnz     loc_180004F1E
0x180004de5  mov     rcx, rbx; lpsz
0x180004de8  call    cs:__imp_CharNextW
0x180004dee  mov     [rdi], rax
0x180004df1  cmp     [rax], si
0x180004df4  jnz     short loc_180004E1A
0x180004df6  mov     rdx, rax; unsigned __int16 *
0x180004df9  mov     r8d, 1; int
0x180004dff  lea     rcx, [rbp+57h+var_A0]; this
0x180004e03  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180004e08  test    eax, eax
0x180004e0a  jnz     loc_180004F0A
0x180004e10  mov     ebx, 8007000Eh
0x180004e15  jmp     loc_180004F42
0x180004e1a  mov     edx, esi; unsigned __int16
0x180004e1c  mov     rcx, rax; lpsz
0x180004e1f  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180004e24  mov     rsi, rax
0x180004e27  test    rax, rax
0x180004e2a  jz      loc_180004F2D
0x180004e30  mov     rcx, rax
0x180004e33  sub     rcx, [rdi]
0x180004e36  sar     rcx, 1
0x180004e39  cmp     rcx, 1Fh
0x180004e3d  jg      loc_180004F26
0x180004e43  movsxd  r9, ecx; MaxCount
0x180004e46  mov     r8, [rdi]; Source
0x180004e49  mov     edx, 20h ; ' '; SizeInWords
0x180004e4e  lea     rcx, [rbp+57h+Destination]; Destination
0x180004e52  call    cs:__imp_wcsncpy_s
0x180004e58  mov     ecx, eax; int
0x180004e5a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180004e5f  mov     rbx, [rdi+8]
0x180004e63  lea     r12, [rbx+20h]
0x180004e67  mov     rcx, r12; lpCriticalSection
0x180004e6a  call    cs:__imp_EnterCriticalSection
0x180004e70  lea     r14, [rbx+8]
0x180004e74  mov     ebx, r13d
0x180004e77  cmp     ebx, [r14+10h]
0x180004e7b  jge     short loc_180004EAD
0x180004e7d  movsxd  rax, ebx
0x180004e80  mov     rcx, [r14]
0x180004e83  lea     rdx, [rbp+57h+Destination]; lpString2
0x180004e87  mov     rcx, [rcx+rax*8]; lpString1
0x180004e8b  call    cs:__imp_lstrcmpiW
0x180004e91  test    eax, eax
0x180004e93  jz      short loc_180004E99
0x180004e95  inc     ebx
0x180004e97  jmp     short loc_180004E77
0x180004e99  cmp     ebx, 0FFFFFFFFh
0x180004e9c  jz      short loc_180004EAD
0x180004e9e  mov     edx, ebx
0x180004ea0  mov     rcx, r14
0x180004ea3  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180004ea8  mov     rbx, [rax]
0x180004eab  jmp     short loc_180004EB0
0x180004ead  mov     rbx, r13
0x180004eb0  mov     rcx, r12; lpCriticalSection
0x180004eb3  call    cs:__imp_LeaveCriticalSection
0x180004eb9  test    rbx, rbx
0x180004ebc  jz      short loc_180004F2D
0x180004ebe  mov     [rbp+57h+var_90], r13
0x180004ec2  or      r8, 0FFFFFFFFFFFFFFFFh
0x180004ec6  inc     r8; int
0x180004ec9  cmp     [rbx+r8*2], r13w
0x180004ece  jnz     short loc_180004EC6
0x180004ed0  mov     rdx, rbx; unsigned __int16 *
0x180004ed3  lea     rcx, [rbp+57h+var_A0]; this
0x180004ed7  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180004edc  mov     ebx, eax
0x180004ede  lea     rcx, [rbp+57h+var_90]
0x180004ee2  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180004ee7  test    ebx, ebx
0x180004ee9  jz      loc_180004E10
0x180004eef  mov     rax, [rdi]
0x180004ef2  jmp     short loc_180004F00
0x180004ef4  mov     rcx, rax; lpsz
0x180004ef7  call    cs:__imp_CharNextW
0x180004efd  mov     [rdi], rax
0x180004f00  cmp     rax, rsi
0x180004f03  jnz     short loc_180004EF4
0x180004f05  mov     esi, 25h ; '%'
0x180004f0a  mov     rcx, [rdi]; lpsz
0x180004f0d  call    cs:__imp_CharNextW
0x180004f13  mov     rbx, rax
0x180004f16  mov     [rdi], rax
0x180004f19  jmp     loc_180004DD2
0x180004f1e  mov     rdx, rbx
0x180004f21  jmp     loc_180004DF9
0x180004f26  mov     ebx, 80004005h
0x180004f2b  jmp     short loc_180004F42
0x180004f2d  mov     ebx, 80020009h
0x180004f32  jmp     short loc_180004F42
0x180004f34  mov     ebx, r13d
0x180004f37  mov     rcx, [rbp+57h+pv]
0x180004f3b  mov     [rbp+57h+pv], r13
0x180004f3f  mov     [r15], rcx
0x180004f42  mov     rcx, [rbp+57h+pv]; pv
0x180004f46  call    cs:__imp_CoTaskMemFree
0x180004f4c  mov     eax, ebx
0x180004f4e  jmp     short loc_180004F55
0x180004f50  mov     eax, 80004003h
0x180004f55  mov     rcx, [rbp+57h+var_40]
0x180004f59  xor     rcx, rsp; StackCookie
0x180004f5c  call    __security_check_cookie
0x180004f61  mov     rbx, [rsp+0C0h+arg_8]
0x180004f69  add     rsp, 90h
0x180004f70  pop     r15
0x180004f72  pop     r14
0x180004f74  pop     r13
0x180004f76  pop     r12
0x180004f78  pop     rdi
0x180004f79  pop     rsi
0x180004f7a  pop     rbp
0x180004f7b  retn
```
