# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18004aaac`
- end: `0x18004ad1f`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `627`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004b600`

## callees

- `0x180033f60`
- `0x18003fb5c`
- `0x1800421c8`
- `0x180042294`
- `0x1800480b4`
- `0x18004aaac`
- `0x18004fe74`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004abe0`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004abe0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18004ab8a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18004ac75`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18004aca4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18004ab8a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18004ac75`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18004aca4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004ac13`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004ac13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004ab33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004ab33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ab54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ace2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ab54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ace2`

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
0x18004aaac  mov     [rsp-8+arg_8], rbx
0x18004aab1  push    rbp
0x18004aab2  push    rsi
0x18004aab3  push    rdi
0x18004aab4  push    r12
0x18004aab6  push    r13
0x18004aab8  push    r14
0x18004aaba  push    r15
0x18004aabc  lea     rbp, [rsp-27h]
0x18004aac1  sub     rsp, 90h
0x18004aac8  mov     rax, cs:__security_cookie
0x18004aacf  xor     rax, rsp
0x18004aad2  mov     [rbp+57h+var_40], rax
0x18004aad6  mov     r15, r8
0x18004aad9  mov     rbx, rdx
0x18004aadc  mov     rdi, rcx
0x18004aadf  xor     r12d, r12d
0x18004aae2  test    rdx, rdx
0x18004aae5  jz      loc_18004ACF2
0x18004aaeb  test    r8, r8
0x18004aaee  jz      loc_18004ACF2
0x18004aaf4  mov     [r8], r12
0x18004aaf7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004aafb  inc     rax
0x18004aafe  cmp     [rdx+rax*2], r12w
0x18004ab03  jnz     short loc_18004AAFB
0x18004ab05  add     eax, eax
0x18004ab07  mov     ecx, 3E8h
0x18004ab0c  cmp     eax, 64h ; 'd'
0x18004ab0f  cmovl   eax, ecx
0x18004ab12  mov     [rbp+57h+var_A0], r12d
0x18004ab16  mov     [rbp+57h+var_9C], eax
0x18004ab19  mov     ecx, eax
0x18004ab1b  add     rcx, rcx
0x18004ab1e  mov     eax, 0FFFFFFFFh
0x18004ab23  cmp     rcx, rax
0x18004ab26  jbe     short loc_18004AB31
0x18004ab28  mov     rax, r12
0x18004ab2b  mov     [rbp+57h+pv], r12
0x18004ab2f  jmp     short loc_18004AB4C
0x18004ab31  mov     ecx, ecx; cb
0x18004ab33  call    cs:__imp_CoTaskMemAlloc
0x18004ab3a  nop     dword ptr [rax+rax+00h]
0x18004ab3f  mov     [rbp+57h+pv], rax
0x18004ab43  test    rax, rax
0x18004ab46  jz      short loc_18004AB4C
0x18004ab48  mov     [rax], r12w
0x18004ab4c  test    rax, rax
0x18004ab4f  jnz     short loc_18004AB6A
0x18004ab51  mov     rcx, rax; pv
0x18004ab54  call    cs:__imp_CoTaskMemFree
0x18004ab5b  nop     dword ptr [rax+rax+00h]
0x18004ab60  mov     eax, 8007000Eh
0x18004ab65  jmp     loc_18004ACF7
0x18004ab6a  mov     [rdi], rbx
0x18004ab6d  mov     r13d, 25h ; '%'
0x18004ab73  cmp     [rbx], r12w
0x18004ab77  jz      loc_18004ACD0
0x18004ab7d  cmp     [rbx], r13w
0x18004ab81  jnz     loc_18004AC8B
0x18004ab87  mov     rcx, rbx; lpsz
0x18004ab8a  call    cs:__imp_CharNextW
0x18004ab91  nop     dword ptr [rax+rax+00h]
0x18004ab96  mov     [rdi], rax
0x18004ab99  cmp     [rax], r13w
0x18004ab9d  jnz     short loc_18004ABA7
0x18004ab9f  mov     rdx, rax
0x18004aba2  jmp     loc_18004AC8E
0x18004aba7  mov     edx, r13d; unsigned __int16
0x18004abaa  mov     rcx, rax; lpsz
0x18004abad  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18004abb2  mov     rsi, rax
0x18004abb5  test    rax, rax
0x18004abb8  jz      loc_18004ACC2
0x18004abbe  mov     rcx, rax
0x18004abc1  sub     rcx, [rdi]
0x18004abc4  sar     rcx, 1
0x18004abc7  cmp     rcx, 1Fh
0x18004abcb  jg      loc_18004ACBB
0x18004abd1  movsxd  r9, ecx
0x18004abd4  mov     r8, [rdi]
0x18004abd7  mov     edx, 20h ; ' '
0x18004abdc  lea     rcx, [rbp+57h+String2]
0x18004abe0  call    cs:__imp__o_wcsncpy_s
0x18004abe7  nop     dword ptr [rax+rax+00h]
0x18004abec  mov     ecx, eax; int
0x18004abee  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18004abf3  mov     r14, [rdi+8]
0x18004abf7  mov     ebx, r12d
0x18004abfa  cmp     ebx, [r14+18h]
0x18004abfe  jge     loc_18004ACC2
0x18004ac04  movsxd  rax, ebx
0x18004ac07  mov     rcx, [r14+8]
0x18004ac0b  lea     rdx, [rbp+57h+String2]; lpString2
0x18004ac0f  mov     rcx, [rcx+rax*8]; lpString1
0x18004ac13  call    cs:__imp_lstrcmpiW
0x18004ac1a  nop     dword ptr [rax+rax+00h]
0x18004ac1f  test    eax, eax
0x18004ac21  jz      short loc_18004AC27
0x18004ac23  inc     ebx
0x18004ac25  jmp     short loc_18004ABFA
0x18004ac27  cmp     ebx, 0FFFFFFFFh
0x18004ac2a  jz      loc_18004ACC2
0x18004ac30  mov     edx, ebx
0x18004ac32  lea     rcx, [r14+8]
0x18004ac36  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18004ac3b  mov     rdx, [rax]; unsigned __int16 *
0x18004ac3e  test    rdx, rdx
0x18004ac41  jz      short loc_18004ACC2
0x18004ac43  mov     [rbp+57h+var_90], r12
0x18004ac47  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004ac4b  inc     r8; int
0x18004ac4e  cmp     [rdx+r8*2], r12w
0x18004ac53  jnz     short loc_18004AC4B
0x18004ac55  lea     rcx, [rbp+57h+var_A0]; this
0x18004ac59  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18004ac5e  mov     ebx, eax
0x18004ac60  lea     rcx, [rbp+57h+var_90]
0x18004ac64  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18004ac69  test    ebx, ebx
0x18004ac6b  jz      short loc_18004ACC9
0x18004ac6d  mov     rax, [rdi]
0x18004ac70  jmp     short loc_18004AC84
0x18004ac72  mov     rcx, rax; lpsz
0x18004ac75  call    cs:__imp_CharNextW
0x18004ac7c  nop     dword ptr [rax+rax+00h]
0x18004ac81  mov     [rdi], rax
0x18004ac84  cmp     rax, rsi
0x18004ac87  jnz     short loc_18004AC72
0x18004ac89  jmp     short loc_18004ACA1
0x18004ac8b  mov     rdx, rbx; unsigned __int16 *
0x18004ac8e  mov     r8d, 1; int
0x18004ac94  lea     rcx, [rbp+57h+var_A0]; this
0x18004ac98  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18004ac9d  test    eax, eax
0x18004ac9f  jz      short loc_18004ACC9
0x18004aca1  mov     rcx, [rdi]; lpsz
0x18004aca4  call    cs:__imp_CharNextW
0x18004acab  nop     dword ptr [rax+rax+00h]
0x18004acb0  mov     rbx, rax
0x18004acb3  mov     [rdi], rax
0x18004acb6  jmp     loc_18004AB73
0x18004acbb  mov     ebx, 80004005h
0x18004acc0  jmp     short loc_18004ACDE
0x18004acc2  mov     ebx, 80020009h
0x18004acc7  jmp     short loc_18004ACDE
0x18004acc9  mov     ebx, 8007000Eh
0x18004acce  jmp     short loc_18004ACDE
0x18004acd0  mov     ebx, r12d
0x18004acd3  mov     rcx, [rbp+57h+pv]
0x18004acd7  mov     [rbp+57h+pv], r12
0x18004acdb  mov     [r15], rcx
0x18004acde  mov     rcx, [rbp+57h+pv]; pv
0x18004ace2  call    cs:__imp_CoTaskMemFree
0x18004ace9  nop     dword ptr [rax+rax+00h]
0x18004acee  mov     eax, ebx
0x18004acf0  jmp     short loc_18004ACF7
0x18004acf2  mov     eax, 80004003h
0x18004acf7  mov     rcx, [rbp+57h+var_40]
0x18004acfb  xor     rcx, rsp; StackCookie
0x18004acfe  call    __security_check_cookie
0x18004ad03  mov     rbx, [rsp+0C0h+arg_8]
0x18004ad0b  add     rsp, 90h
0x18004ad12  pop     r15
0x18004ad14  pop     r14
0x18004ad16  pop     r13
0x18004ad18  pop     r12
0x18004ad1a  pop     rdi
0x18004ad1b  pop     rsi
0x18004ad1c  pop     rbp
0x18004ad1d  retn
```
