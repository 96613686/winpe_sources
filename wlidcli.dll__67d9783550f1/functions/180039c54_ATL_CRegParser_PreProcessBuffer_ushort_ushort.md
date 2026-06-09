# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180039c54`
- end: `0x180039e9f`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `587`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003a0dc`

## callees

- `0x180002da0`
- `0x18000ac9c`
- `0x180013410`
- `0x180038418`
- `0x180038e80`
- `0x1800396ec`
- `0x180039c54`
- `0x18003ac20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180039d7f`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180039d7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039ce4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039ce4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039cff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039e69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039cff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039e69`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180039d2f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180039e08`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180039e31`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180039d2f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180039e08`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180039e31`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180039dac`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180039dac`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rdx
  __int64 v7; // rdx
  _WORD *v8; // rax
  LPWSTR v10; // rax
  const unsigned __int16 *v11; // rdx
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rsi
  __int64 v14; // rcx
  unsigned int v15; // eax
  LPCWSTR v16; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v18; // rdx
  __int64 v19; // r8
  int v20; // ebx
  const WCHAR *j; // rax
  unsigned int v22; // ebx
  unsigned __int16 *v23; // rcx
  SIZE_T cb; // [rsp+20h] [rbp-49h] BYREF
  _DWORD v25[2]; // [rsp+28h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-39h]
  WCHAR String2[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( v4[v6] );
  v7 = (unsigned int)(2 * v6);
  if ( (int)v7 < 100 )
    v7 = 1000;
  v25[0] = 0;
  v25[1] = v7;
  LODWORD(cb) = 0;
  if ( (int)ATL::AtlMultiply<unsigned long>(&cb, v7, 2) >= 0 )
  {
    v8 = CoTaskMemAlloc((unsigned int)cb);
    pv = v8;
    if ( v8 )
      *v8 = 0;
  }
  else
  {
    v8 = 0;
    pv = 0;
  }
  if ( !v8 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  for ( *this = v4; ; *this = v4 )
  {
    if ( !*v4 )
    {
      v22 = 0;
      v23 = (unsigned __int16 *)pv;
      pv = 0;
      *a3 = v23;
      goto LABEL_40;
    }
    if ( *v4 == 37 )
      break;
    v11 = v4;
LABEL_34:
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v11, 1) )
    {
LABEL_38:
      v22 = -2147024882;
      goto LABEL_40;
    }
LABEL_35:
    v4 = CharNextW(*this);
  }
  v10 = CharNextW(v4);
  *this = v10;
  if ( *v10 == 37 )
  {
    v11 = v10;
    goto LABEL_34;
  }
  v12 = ATL::CRegParser::StrChrW(v10, 0x25u);
  v13 = v12;
  if ( v12 )
  {
    v14 = v12 - *this;
    if ( v14 > 31 )
    {
      v22 = -2147467259;
      goto LABEL_40;
    }
    v15 = _o_wcsncpy_s(String2, 32, *this, (int)v14);
    ATL::AtlCrtErrorCheck(v15);
    v16 = this[1];
    for ( i = 0; (signed int)i < *((_DWORD *)v16 + 6); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v16 + 1) + 8LL * (int)i), String2) )
      {
        if ( i == -1 )
          break;
        v18 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                            v16 + 4,
                                            i);
        if ( !v18 )
          break;
        cb = 0;
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        v20 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v18, v19);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&cb);
        if ( v20 )
        {
          for ( j = *this; j != v13; *this = j )
            j = CharNextW(j);
          goto LABEL_35;
        }
        goto LABEL_38;
      }
    }
  }
  v22 = -2147352567;
LABEL_40:
  CoTaskMemFree(pv);
  return v22;
}

```

## disassembly

```asm
0x180039c54  mov     [rsp-8+arg_8], rbx
0x180039c59  push    rbp
0x180039c5a  push    rsi
0x180039c5b  push    rdi
0x180039c5c  push    r12
0x180039c5e  push    r13
0x180039c60  push    r14
0x180039c62  push    r15
0x180039c64  lea     rbp, [rsp-27h]
0x180039c69  sub     rsp, 90h
0x180039c70  mov     rax, cs:__security_cookie
0x180039c77  xor     rax, rsp
0x180039c7a  mov     [rbp+57h+var_40], rax
0x180039c7e  mov     r15, r8
0x180039c81  mov     rbx, rdx
0x180039c84  mov     rdi, rcx
0x180039c87  xor     r12d, r12d
0x180039c8a  test    rdx, rdx
0x180039c8d  jz      loc_180039E73
0x180039c93  test    r8, r8
0x180039c96  jz      loc_180039E73
0x180039c9c  mov     [r8], r12
0x180039c9f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180039ca3  inc     rdx
0x180039ca6  cmp     [rbx+rdx*2], r12w
0x180039cab  jnz     short loc_180039CA3
0x180039cad  add     edx, edx
0x180039caf  mov     eax, 3E8h
0x180039cb4  cmp     edx, 64h ; 'd'
0x180039cb7  cmovl   edx, eax
0x180039cba  mov     [rbp+57h+var_98], r12d
0x180039cbe  mov     [rbp+57h+var_94], edx
0x180039cc1  mov     dword ptr [rbp+57h+cb], r12d
0x180039cc5  mov     r8d, 2
0x180039ccb  lea     rcx, [rbp+57h+cb]
0x180039ccf  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x180039cd4  test    eax, eax
0x180039cd6  jns     short loc_180039CE1
0x180039cd8  mov     rax, r12
0x180039cdb  mov     [rbp+57h+pv], r12
0x180039cdf  jmp     short loc_180039CF7
0x180039ce1  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x180039ce4  call    cs:__imp_CoTaskMemAlloc
0x180039cea  mov     [rbp+57h+pv], rax
0x180039cee  test    rax, rax
0x180039cf1  jz      short loc_180039CF7
0x180039cf3  mov     [rax], r12w
0x180039cf7  test    rax, rax
0x180039cfa  jnz     short loc_180039D0F
0x180039cfc  mov     rcx, rax; pv
0x180039cff  call    cs:__imp_CoTaskMemFree
0x180039d05  mov     eax, 8007000Eh
0x180039d0a  jmp     loc_180039E78
0x180039d0f  mov     [rdi], rbx
0x180039d12  mov     r13d, 25h ; '%'
0x180039d18  cmp     [rbx], r12w
0x180039d1c  jz      loc_180039E57
0x180039d22  cmp     [rbx], r13w
0x180039d26  jnz     loc_180039E18
0x180039d2c  mov     rcx, rbx; lpsz
0x180039d2f  call    cs:__imp_CharNextW
0x180039d35  mov     [rdi], rax
0x180039d38  cmp     [rax], r13w
0x180039d3c  jnz     short loc_180039D46
0x180039d3e  mov     rdx, rax
0x180039d41  jmp     loc_180039E1B
0x180039d46  mov     edx, r13d; unsigned __int16
0x180039d49  mov     rcx, rax; lpsz
0x180039d4c  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180039d51  mov     rsi, rax
0x180039d54  test    rax, rax
0x180039d57  jz      loc_180039E49
0x180039d5d  mov     rcx, rax
0x180039d60  sub     rcx, [rdi]
0x180039d63  sar     rcx, 1
0x180039d66  cmp     rcx, 1Fh
0x180039d6a  jg      loc_180039E42
0x180039d70  movsxd  r9, ecx
0x180039d73  mov     r8, [rdi]
0x180039d76  mov     edx, 20h ; ' '
0x180039d7b  lea     rcx, [rbp+57h+String2]
0x180039d7f  call    cs:__imp__o_wcsncpy_s
0x180039d85  mov     ecx, eax; int
0x180039d87  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180039d8c  mov     r14, [rdi+8]
0x180039d90  mov     ebx, r12d
0x180039d93  cmp     ebx, [r14+18h]
0x180039d97  jge     loc_180039E49
0x180039d9d  movsxd  rax, ebx
0x180039da0  mov     rcx, [r14+8]
0x180039da4  lea     rdx, [rbp+57h+String2]; lpString2
0x180039da8  mov     rcx, [rcx+rax*8]; lpString1
0x180039dac  call    cs:__imp_lstrcmpiW
0x180039db2  test    eax, eax
0x180039db4  jz      short loc_180039DBA
0x180039db6  inc     ebx
0x180039db8  jmp     short loc_180039D93
0x180039dba  cmp     ebx, 0FFFFFFFFh
0x180039dbd  jz      loc_180039E49
0x180039dc3  mov     edx, ebx
0x180039dc5  lea     rcx, [r14+8]
0x180039dc9  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180039dce  mov     rdx, [rax]; unsigned __int16 *
0x180039dd1  test    rdx, rdx
0x180039dd4  jz      short loc_180039E49
0x180039dd6  mov     [rbp+57h+cb], r12
0x180039dda  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039dde  inc     r8; int
0x180039de1  cmp     [rdx+r8*2], r12w
0x180039de6  jnz     short loc_180039DDE
0x180039de8  lea     rcx, [rbp+57h+var_98]; this
0x180039dec  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180039df1  mov     ebx, eax
0x180039df3  lea     rcx, [rbp+57h+cb]
0x180039df7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180039dfc  test    ebx, ebx
0x180039dfe  jz      short loc_180039E50
0x180039e00  mov     rax, [rdi]
0x180039e03  jmp     short loc_180039E11
0x180039e05  mov     rcx, rax; lpsz
0x180039e08  call    cs:__imp_CharNextW
0x180039e0e  mov     [rdi], rax
0x180039e11  cmp     rax, rsi
0x180039e14  jnz     short loc_180039E05
0x180039e16  jmp     short loc_180039E2E
0x180039e18  mov     rdx, rbx; unsigned __int16 *
0x180039e1b  mov     r8d, 1; int
0x180039e21  lea     rcx, [rbp+57h+var_98]; this
0x180039e25  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180039e2a  test    eax, eax
0x180039e2c  jz      short loc_180039E50
0x180039e2e  mov     rcx, [rdi]; lpsz
0x180039e31  call    cs:__imp_CharNextW
0x180039e37  mov     rbx, rax
0x180039e3a  mov     [rdi], rax
0x180039e3d  jmp     loc_180039D18
0x180039e42  mov     ebx, 80004005h
0x180039e47  jmp     short loc_180039E65
0x180039e49  mov     ebx, 80020009h
0x180039e4e  jmp     short loc_180039E65
0x180039e50  mov     ebx, 8007000Eh
0x180039e55  jmp     short loc_180039E65
0x180039e57  mov     ebx, r12d
0x180039e5a  mov     rcx, [rbp+57h+pv]
0x180039e5e  mov     [rbp+57h+pv], r12
0x180039e62  mov     [r15], rcx
0x180039e65  mov     rcx, [rbp+57h+pv]; pv
0x180039e69  call    cs:__imp_CoTaskMemFree
0x180039e6f  mov     eax, ebx
0x180039e71  jmp     short loc_180039E78
0x180039e73  mov     eax, 80004003h
0x180039e78  mov     rcx, [rbp+57h+var_40]
0x180039e7c  xor     rcx, rsp; StackCookie
0x180039e7f  call    __security_check_cookie
0x180039e84  mov     rbx, [rsp+0C0h+arg_8]
0x180039e8c  add     rsp, 90h
0x180039e93  pop     r15
0x180039e95  pop     r14
0x180039e97  pop     r13
0x180039e99  pop     r12
0x180039e9b  pop     rdi
0x180039e9c  pop     rsi
0x180039e9d  pop     rbp
0x180039e9e  retn
```
