# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180019f20`
- end: `0x18001a184`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `612`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001aa9c`

## callees

- `0x1800034b0`
- `0x180014f98`
- `0x180016ca8`
- `0x180016efc`
- `0x1800198dc`
- `0x180019f20`
- `0x18001b98c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001a05a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001a05a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019fc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a14e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019fc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a14e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019fa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019fa7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a0bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a0bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a072`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a072`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019ff0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001a0ff`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001a115`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019ff0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001a0ff`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001a115`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a093`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a093`

## pseudocode

```c
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
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v12, 1) )
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
0x180019f20  mov     [rsp-8+arg_8], rbx
0x180019f25  push    rbp
0x180019f26  push    rsi
0x180019f27  push    rdi
0x180019f28  push    r12
0x180019f2a  push    r13
0x180019f2c  push    r14
0x180019f2e  push    r15
0x180019f30  lea     rbp, [rsp-27h]
0x180019f35  sub     rsp, 90h
0x180019f3c  mov     rax, cs:__security_cookie
0x180019f43  xor     rax, rsp
0x180019f46  mov     [rbp+57h+var_40], rax
0x180019f4a  mov     r15, r8
0x180019f4d  mov     rbx, rdx
0x180019f50  mov     rdi, rcx
0x180019f53  xor     r13d, r13d
0x180019f56  test    rdx, rdx
0x180019f59  jz      loc_18001A158
0x180019f5f  test    r8, r8
0x180019f62  jz      loc_18001A158
0x180019f68  mov     [r8], r13
0x180019f6b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019f6f  inc     rax
0x180019f72  cmp     [rdx+rax*2], r13w
0x180019f77  jnz     short loc_180019F6F
0x180019f79  add     eax, eax
0x180019f7b  mov     ecx, 3E8h
0x180019f80  cmp     eax, 64h ; 'd'
0x180019f83  cmovl   eax, ecx
0x180019f86  mov     [rbp+57h+var_A0], r13d
0x180019f8a  mov     [rbp+57h+var_9C], eax
0x180019f8d  mov     ecx, eax
0x180019f8f  add     rcx, rcx
0x180019f92  mov     eax, 0FFFFFFFFh
0x180019f97  cmp     rcx, rax
0x180019f9a  jbe     short loc_180019FA5
0x180019f9c  mov     rax, r13
0x180019f9f  mov     [rbp+57h+pv], r13
0x180019fa3  jmp     short loc_180019FBA
0x180019fa5  mov     ecx, ecx; cb
0x180019fa7  call    cs:__imp_CoTaskMemAlloc
0x180019fad  mov     [rbp+57h+pv], rax
0x180019fb1  test    rax, rax
0x180019fb4  jz      short loc_180019FBA
0x180019fb6  mov     [rax], r13w
0x180019fba  test    rax, rax
0x180019fbd  jnz     short loc_180019FD2
0x180019fbf  mov     rcx, rax; pv
0x180019fc2  call    cs:__imp_CoTaskMemFree
0x180019fc8  mov     eax, 8007000Eh
0x180019fcd  jmp     loc_18001A15D
0x180019fd2  mov     [rdi], rbx
0x180019fd5  mov     esi, 25h ; '%'
0x180019fda  cmp     [rbx], r13w
0x180019fde  jz      loc_18001A13C
0x180019fe4  cmp     [rbx], si
0x180019fe7  jnz     loc_18001A126
0x180019fed  mov     rcx, rbx; lpsz
0x180019ff0  call    cs:__imp_CharNextW
0x180019ff6  mov     [rdi], rax
0x180019ff9  cmp     [rax], si
0x180019ffc  jnz     short loc_18001A022
0x180019ffe  mov     rdx, rax; unsigned __int16 *
0x18001a001  mov     r8d, 1; int
0x18001a007  lea     rcx, [rbp+57h+var_A0]; this
0x18001a00b  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18001a010  test    eax, eax
0x18001a012  jnz     loc_18001A112
0x18001a018  mov     ebx, 8007000Eh
0x18001a01d  jmp     loc_18001A14A
0x18001a022  mov     edx, esi; unsigned __int16
0x18001a024  mov     rcx, rax; lpsz
0x18001a027  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001a02c  mov     rsi, rax
0x18001a02f  test    rax, rax
0x18001a032  jz      loc_18001A135
0x18001a038  mov     rcx, rax
0x18001a03b  sub     rcx, [rdi]
0x18001a03e  sar     rcx, 1
0x18001a041  cmp     rcx, 1Fh
0x18001a045  jg      loc_18001A12E
0x18001a04b  movsxd  r9, ecx
0x18001a04e  mov     r8, [rdi]
0x18001a051  mov     edx, 20h ; ' '
0x18001a056  lea     rcx, [rbp+57h+String2]
0x18001a05a  call    cs:__imp__o_wcsncpy_s
0x18001a060  mov     ecx, eax; int
0x18001a062  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001a067  mov     rbx, [rdi+8]
0x18001a06b  lea     r12, [rbx+20h]
0x18001a06f  mov     rcx, r12; lpCriticalSection
0x18001a072  call    cs:__imp_EnterCriticalSection
0x18001a078  lea     r14, [rbx+8]
0x18001a07c  mov     ebx, r13d
0x18001a07f  cmp     ebx, [r14+10h]
0x18001a083  jge     short loc_18001A0B5
0x18001a085  movsxd  rax, ebx
0x18001a088  mov     rcx, [r14]
0x18001a08b  lea     rdx, [rbp+57h+String2]; lpString2
0x18001a08f  mov     rcx, [rcx+rax*8]; lpString1
0x18001a093  call    cs:__imp_lstrcmpiW
0x18001a099  test    eax, eax
0x18001a09b  jz      short loc_18001A0A1
0x18001a09d  inc     ebx
0x18001a09f  jmp     short loc_18001A07F
0x18001a0a1  cmp     ebx, 0FFFFFFFFh
0x18001a0a4  jz      short loc_18001A0B5
0x18001a0a6  mov     edx, ebx
0x18001a0a8  mov     rcx, r14
0x18001a0ab  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18001a0b0  mov     rbx, [rax]
0x18001a0b3  jmp     short loc_18001A0B8
0x18001a0b5  mov     rbx, r13
0x18001a0b8  mov     rcx, r12; lpCriticalSection
0x18001a0bb  call    cs:__imp_LeaveCriticalSection
0x18001a0c1  test    rbx, rbx
0x18001a0c4  jz      short loc_18001A135
0x18001a0c6  mov     [rbp+57h+var_90], r13
0x18001a0ca  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001a0ce  inc     r8; int
0x18001a0d1  cmp     [rbx+r8*2], r13w
0x18001a0d6  jnz     short loc_18001A0CE
0x18001a0d8  mov     rdx, rbx; unsigned __int16 *
0x18001a0db  lea     rcx, [rbp+57h+var_A0]; this
0x18001a0df  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18001a0e4  mov     ebx, eax
0x18001a0e6  lea     rcx, [rbp+57h+var_90]
0x18001a0ea  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a0ef  test    ebx, ebx
0x18001a0f1  jz      loc_18001A018
0x18001a0f7  mov     rax, [rdi]
0x18001a0fa  jmp     short loc_18001A108
0x18001a0fc  mov     rcx, rax; lpsz
0x18001a0ff  call    cs:__imp_CharNextW
0x18001a105  mov     [rdi], rax
0x18001a108  cmp     rax, rsi
0x18001a10b  jnz     short loc_18001A0FC
0x18001a10d  mov     esi, 25h ; '%'
0x18001a112  mov     rcx, [rdi]; lpsz
0x18001a115  call    cs:__imp_CharNextW
0x18001a11b  mov     rbx, rax
0x18001a11e  mov     [rdi], rax
0x18001a121  jmp     loc_180019FDA
0x18001a126  mov     rdx, rbx
0x18001a129  jmp     loc_18001A001
0x18001a12e  mov     ebx, 80004005h
0x18001a133  jmp     short loc_18001A14A
0x18001a135  mov     ebx, 80020009h
0x18001a13a  jmp     short loc_18001A14A
0x18001a13c  mov     ebx, r13d
0x18001a13f  mov     rcx, [rbp+57h+pv]
0x18001a143  mov     [rbp+57h+pv], r13
0x18001a147  mov     [r15], rcx
0x18001a14a  mov     rcx, [rbp+57h+pv]; pv
0x18001a14e  call    cs:__imp_CoTaskMemFree
0x18001a154  mov     eax, ebx
0x18001a156  jmp     short loc_18001A15D
0x18001a158  mov     eax, 80004003h
0x18001a15d  mov     rcx, [rbp+57h+var_40]
0x18001a161  xor     rcx, rsp; StackCookie
0x18001a164  call    __security_check_cookie
0x18001a169  mov     rbx, [rsp+0C0h+arg_8]
0x18001a171  add     rsp, 90h
0x18001a178  pop     r15
0x18001a17a  pop     r14
0x18001a17c  pop     r13
0x18001a17e  pop     r12
0x18001a180  pop     rdi
0x18001a181  pop     rsi
0x18001a182  pop     rbp
0x18001a183  retn
```
