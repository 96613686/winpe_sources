# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180029c78`
- end: `0x180029eba`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `578`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18002a25c`

## callees

- `0x180024850`
- `0x180025d84`
- `0x180025f74`
- `0x18002838c`
- `0x180029c78`
- `0x18002c1e0`
- `0x180055030`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180029d9a`
- `msvcrt!wcsncpy_s` at `0x180029d9a`
- `KERNEL32!lstrcmpiW` at `0x180029dc7`
- `KERNEL32!lstrcmpiW` at `0x180029dc7`
- `ole32!CoTaskMemFree` at `0x180029d1a`
- `ole32!CoTaskMemFree` at `0x180029e84`
- `ole32!CoTaskMemFree` at `0x180029d1a`
- `ole32!CoTaskMemFree` at `0x180029e84`
- `ole32!CoTaskMemAlloc` at `0x180029cff`
- `ole32!CoTaskMemAlloc` at `0x180029cff`
- `USER32!CharNextW` at `0x180029d4a`
- `USER32!CharNextW` at `0x180029e23`
- `USER32!CharNextW` at `0x180029e4c`
- `USER32!CharNextW` at `0x180029d4a`
- `USER32!CharNextW` at `0x180029e23`
- `USER32!CharNextW` at `0x180029e4c`

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
  errno_t v16; // eax
  LPCWSTR v17; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v19; // rdx
  __int64 v20; // r8
  int v21; // ebx
  const WCHAR *j; // rax
  unsigned int v23; // ebx
  unsigned __int16 *v24; // rcx
  _DWORD v25[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v27; // [rsp+30h] [rbp-39h] BYREF
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
  v25[0] = 0;
  v25[1] = v7;
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
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v12, 1) )
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
    v16 = wcsncpy_s(Destination, 0x20u, *this, (int)v15);
    ATL::AtlCrtErrorCheck(v16);
    v17 = this[1];
    for ( i = 0; (signed int)i < *((_DWORD *)v17 + 6); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v17 + 1) + 8LL * (int)i), Destination) )
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
        v21 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v19, v20);
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
0x180029c78  mov     [rsp-8+arg_8], rbx
0x180029c7d  push    rbp
0x180029c7e  push    rsi
0x180029c7f  push    rdi
0x180029c80  push    r12
0x180029c82  push    r13
0x180029c84  push    r14
0x180029c86  push    r15
0x180029c88  lea     rbp, [rsp-27h]
0x180029c8d  sub     rsp, 90h
0x180029c94  mov     rax, cs:__security_cookie
0x180029c9b  xor     rax, rsp
0x180029c9e  mov     [rbp+57h+var_40], rax
0x180029ca2  mov     r15, r8
0x180029ca5  mov     rbx, rdx
0x180029ca8  mov     rdi, rcx
0x180029cab  xor     r12d, r12d
0x180029cae  test    rdx, rdx
0x180029cb1  jz      loc_180029E8E
0x180029cb7  test    r8, r8
0x180029cba  jz      loc_180029E8E
0x180029cc0  mov     [r8], r12
0x180029cc3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029cc7  inc     rax
0x180029cca  cmp     [rdx+rax*2], r12w
0x180029ccf  jnz     short loc_180029CC7
0x180029cd1  add     eax, eax
0x180029cd3  mov     ecx, 3E8h
0x180029cd8  cmp     eax, 64h ; 'd'
0x180029cdb  cmovl   eax, ecx
0x180029cde  mov     [rbp+57h+var_A0], r12d
0x180029ce2  mov     [rbp+57h+var_9C], eax
0x180029ce5  mov     ecx, eax
0x180029ce7  add     rcx, rcx
0x180029cea  mov     eax, 0FFFFFFFFh
0x180029cef  cmp     rcx, rax
0x180029cf2  jbe     short loc_180029CFD
0x180029cf4  mov     rax, r12
0x180029cf7  mov     [rbp+57h+pv], r12
0x180029cfb  jmp     short loc_180029D12
0x180029cfd  mov     ecx, ecx; cb
0x180029cff  call    cs:__imp_CoTaskMemAlloc
0x180029d05  mov     [rbp+57h+pv], rax
0x180029d09  test    rax, rax
0x180029d0c  jz      short loc_180029D12
0x180029d0e  mov     [rax], r12w
0x180029d12  test    rax, rax
0x180029d15  jnz     short loc_180029D2A
0x180029d17  mov     rcx, rax; pv
0x180029d1a  call    cs:__imp_CoTaskMemFree
0x180029d20  mov     eax, 8007000Eh
0x180029d25  jmp     loc_180029E93
0x180029d2a  mov     [rdi], rbx
0x180029d2d  mov     r13d, 25h ; '%'
0x180029d33  cmp     [rbx], r12w
0x180029d37  jz      loc_180029E72
0x180029d3d  cmp     [rbx], r13w
0x180029d41  jnz     loc_180029E33
0x180029d47  mov     rcx, rbx; lpsz
0x180029d4a  call    cs:__imp_CharNextW
0x180029d50  mov     [rdi], rax
0x180029d53  cmp     [rax], r13w
0x180029d57  jnz     short loc_180029D61
0x180029d59  mov     rdx, rax
0x180029d5c  jmp     loc_180029E36
0x180029d61  mov     edx, r13d; unsigned __int16
0x180029d64  mov     rcx, rax; lpsz
0x180029d67  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180029d6c  mov     rsi, rax
0x180029d6f  test    rax, rax
0x180029d72  jz      loc_180029E64
0x180029d78  mov     rcx, rax
0x180029d7b  sub     rcx, [rdi]
0x180029d7e  sar     rcx, 1
0x180029d81  cmp     rcx, 1Fh
0x180029d85  jg      loc_180029E5D
0x180029d8b  movsxd  r9, ecx; MaxCount
0x180029d8e  mov     r8, [rdi]; Source
0x180029d91  mov     edx, 20h ; ' '; SizeInWords
0x180029d96  lea     rcx, [rbp+57h+Destination]; Destination
0x180029d9a  call    cs:__imp_wcsncpy_s
0x180029da0  mov     ecx, eax; int
0x180029da2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180029da7  mov     r14, [rdi+8]
0x180029dab  mov     ebx, r12d
0x180029dae  cmp     ebx, [r14+18h]
0x180029db2  jge     loc_180029E64
0x180029db8  movsxd  rax, ebx
0x180029dbb  mov     rcx, [r14+8]
0x180029dbf  lea     rdx, [rbp+57h+Destination]; lpString2
0x180029dc3  mov     rcx, [rcx+rax*8]; lpString1
0x180029dc7  call    cs:__imp_lstrcmpiW
0x180029dcd  test    eax, eax
0x180029dcf  jz      short loc_180029DD5
0x180029dd1  inc     ebx
0x180029dd3  jmp     short loc_180029DAE
0x180029dd5  cmp     ebx, 0FFFFFFFFh
0x180029dd8  jz      loc_180029E64
0x180029dde  mov     edx, ebx
0x180029de0  lea     rcx, [r14+8]
0x180029de4  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180029de9  mov     rdx, [rax]; unsigned __int16 *
0x180029dec  test    rdx, rdx
0x180029def  jz      short loc_180029E64
0x180029df1  mov     [rbp+57h+var_90], r12
0x180029df5  or      r8, 0FFFFFFFFFFFFFFFFh
0x180029df9  inc     r8; int
0x180029dfc  cmp     [rdx+r8*2], r12w
0x180029e01  jnz     short loc_180029DF9
0x180029e03  lea     rcx, [rbp+57h+var_A0]; this
0x180029e07  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180029e0c  mov     ebx, eax
0x180029e0e  lea     rcx, [rbp+57h+var_90]
0x180029e12  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180029e17  test    ebx, ebx
0x180029e19  jz      short loc_180029E6B
0x180029e1b  mov     rax, [rdi]
0x180029e1e  jmp     short loc_180029E2C
0x180029e20  mov     rcx, rax; lpsz
0x180029e23  call    cs:__imp_CharNextW
0x180029e29  mov     [rdi], rax
0x180029e2c  cmp     rax, rsi
0x180029e2f  jnz     short loc_180029E20
0x180029e31  jmp     short loc_180029E49
0x180029e33  mov     rdx, rbx; unsigned __int16 *
0x180029e36  mov     r8d, 1; int
0x180029e3c  lea     rcx, [rbp+57h+var_A0]; this
0x180029e40  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180029e45  test    eax, eax
0x180029e47  jz      short loc_180029E6B
0x180029e49  mov     rcx, [rdi]; lpsz
0x180029e4c  call    cs:__imp_CharNextW
0x180029e52  mov     rbx, rax
0x180029e55  mov     [rdi], rax
0x180029e58  jmp     loc_180029D33
0x180029e5d  mov     ebx, 80004005h
0x180029e62  jmp     short loc_180029E80
0x180029e64  mov     ebx, 80020009h
0x180029e69  jmp     short loc_180029E80
0x180029e6b  mov     ebx, 8007000Eh
0x180029e70  jmp     short loc_180029E80
0x180029e72  mov     ebx, r12d
0x180029e75  mov     rcx, [rbp+57h+pv]
0x180029e79  mov     [rbp+57h+pv], r12
0x180029e7d  mov     [r15], rcx
0x180029e80  mov     rcx, [rbp+57h+pv]; pv
0x180029e84  call    cs:__imp_CoTaskMemFree
0x180029e8a  mov     eax, ebx
0x180029e8c  jmp     short loc_180029E93
0x180029e8e  mov     eax, 80004003h
0x180029e93  mov     rcx, [rbp+57h+var_40]
0x180029e97  xor     rcx, rsp; StackCookie
0x180029e9a  call    __security_check_cookie
0x180029e9f  mov     rbx, [rsp+0C0h+arg_8]
0x180029ea7  add     rsp, 90h
0x180029eae  pop     r15
0x180029eb0  pop     r14
0x180029eb2  pop     r13
0x180029eb4  pop     r12
0x180029eb6  pop     rdi
0x180029eb7  pop     rsi
0x180029eb8  pop     rbp
0x180029eb9  retn
```
