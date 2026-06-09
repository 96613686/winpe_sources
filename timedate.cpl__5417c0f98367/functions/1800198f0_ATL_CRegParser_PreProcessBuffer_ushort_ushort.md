# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800198f0`
- end: `0x180019b02`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `530`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019c9c`

## callees

- `0x180017fa4`
- `0x1800188e0`
- `0x180018b24`
- `0x1800198f0`
- `0x18001a8e0`
- `0x18001a938`
- `0x180028f60`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180019a0b`
- `msvcrt!wcsncpy_s` at `0x180019a0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019983`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019983`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019971`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019ab6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019971`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019ab6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800199bb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019a63`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019a8c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800199bb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019a63`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019a8c`

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
  void *v9; // rcx
  _WORD *v11; // rax
  WCHAR v12; // ax
  LPWSTR v13; // rax
  const unsigned __int16 *v14; // rdx
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rsi
  __int64 v17; // rcx
  errno_t v18; // eax
  const unsigned __int16 *v19; // rax
  __int64 v20; // r8
  int v21; // ebx
  const WCHAR *i; // rax
  unsigned int v23; // ebx
  _DWORD v24[2]; // [rsp+20h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v26; // [rsp+30h] [rbp-29h] BYREF
  wchar_t Destination[32]; // [rsp+40h] [rbp-19h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  v24[0] = 0;
  if ( v7 < 100 )
    v7 = 1000;
  v24[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = 0;
LABEL_9:
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  v11 = CoTaskMemAlloc((unsigned int)v8);
  pv = v11;
  v9 = v11;
  if ( !v11 )
    goto LABEL_9;
  *v11 = 0;
  *(_QWORD *)this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_29:
    v23 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_30;
  }
  while ( v12 != 37 )
  {
    v14 = v4;
LABEL_26:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v14, 1) )
      goto LABEL_33;
LABEL_27:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v9 = pv;
      goto LABEL_29;
    }
  }
  v13 = CharNextW(v4);
  *(_QWORD *)this = v13;
  if ( *v13 == 37 )
  {
    v14 = v13;
    goto LABEL_26;
  }
  v15 = ATL::CRegParser::StrChrW(v13, 0x25u);
  v16 = v15;
  if ( !v15 )
    goto LABEL_32;
  v17 = ((__int64)v15 - *(_QWORD *)this) >> 1;
  if ( v17 > 31 )
  {
    v23 = -2147467259;
    goto LABEL_30;
  }
  v18 = wcsncpy_s(Destination, 0x20u, *(const wchar_t **)this, (int)v17);
  ATL::AtlCrtErrorCheck(v18);
  v19 = ATL::CRegObject::StrFromMap(*((ATL::CRegObject **)this + 1), Destination);
  if ( !v19 )
  {
LABEL_32:
    v23 = -2147352567;
    goto LABEL_30;
  }
  v26 = 0;
  v20 = -1;
  do
    ++v20;
  while ( v19[v20] );
  v21 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v19, v20);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v26);
  if ( v21 )
  {
    for ( i = *(const WCHAR **)this; i != v16; *(_QWORD *)this = i )
      i = CharNextW(i);
    goto LABEL_27;
  }
LABEL_33:
  v23 = -2147024882;
LABEL_30:
  CoTaskMemFree(pv);
  return v23;
}

```

## disassembly

```asm
0x1800198f0  mov     [rsp-8+arg_8], rbx
0x1800198f5  mov     [rsp-8+arg_18], rsi
0x1800198fa  push    rbp
0x1800198fb  push    rdi
0x1800198fc  push    r12
0x1800198fe  push    r14
0x180019900  push    r15
0x180019902  lea     rbp, [rsp-37h]
0x180019907  sub     rsp, 90h
0x18001990e  mov     rax, cs:__security_cookie
0x180019915  xor     rax, rsp
0x180019918  mov     [rbp+57h+var_30], rax
0x18001991c  xor     r15d, r15d
0x18001991f  mov     r14, r8
0x180019922  mov     rbx, rdx
0x180019925  mov     rdi, rcx
0x180019928  test    rdx, rdx
0x18001992b  jz      loc_180019AD5
0x180019931  test    r8, r8
0x180019934  jz      loc_180019AD5
0x18001993a  mov     [r8], r15
0x18001993d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019941  inc     rax
0x180019944  cmp     [rdx+rax*2], r15w
0x180019949  jnz     short loc_180019941
0x18001994b  add     eax, eax
0x18001994d  mov     [rbp+57h+var_90], r15d
0x180019951  cmp     eax, 64h ; 'd'
0x180019954  mov     ecx, 3E8h
0x180019959  cmovl   eax, ecx
0x18001995c  mov     ecx, eax
0x18001995e  mov     [rbp+57h+var_8C], eax
0x180019961  add     rcx, rcx
0x180019964  mov     eax, 0FFFFFFFFh
0x180019969  cmp     rcx, rax
0x18001996c  jbe     short loc_180019981
0x18001996e  mov     rcx, r15; pv
0x180019971  call    cs:__imp_CoTaskMemFree
0x180019977  mov     eax, 8007000Eh
0x18001997c  jmp     loc_180019ADA
0x180019981  mov     ecx, ecx; cb
0x180019983  call    cs:__imp_CoTaskMemAlloc
0x180019989  mov     [rbp+57h+pv], rax
0x18001998d  mov     rcx, rax
0x180019990  test    rax, rax
0x180019993  jz      short loc_180019971
0x180019995  mov     [rax], r15w
0x180019999  mov     [rdi], rbx
0x18001999c  movzx   eax, word ptr [rbx]
0x18001999f  test    ax, ax
0x1800199a2  jz      loc_180019AA8
0x1800199a8  mov     r12d, 25h ; '%'
0x1800199ae  cmp     ax, r12w
0x1800199b2  jnz     loc_180019A73
0x1800199b8  mov     rcx, rbx; lpsz
0x1800199bb  call    cs:__imp_CharNextW
0x1800199c1  mov     [rdi], rax
0x1800199c4  cmp     [rax], r12w
0x1800199c8  jnz     short loc_1800199D2
0x1800199ca  mov     rdx, rax
0x1800199cd  jmp     loc_180019A76
0x1800199d2  mov     edx, r12d; unsigned __int16
0x1800199d5  mov     rcx, rax; lpsz
0x1800199d8  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800199dd  mov     rsi, rax
0x1800199e0  test    rax, rax
0x1800199e3  jz      loc_180019AC7
0x1800199e9  mov     rcx, rax
0x1800199ec  sub     rcx, [rdi]
0x1800199ef  sar     rcx, 1
0x1800199f2  cmp     rcx, 1Fh
0x1800199f6  jg      loc_180019AC0
0x1800199fc  mov     r8, [rdi]; Source
0x1800199ff  mov     edx, 20h ; ' '; SizeInWords
0x180019a04  movsxd  r9, ecx; MaxCount
0x180019a07  lea     rcx, [rbp+57h+Destination]; Destination
0x180019a0b  call    cs:__imp_wcsncpy_s
0x180019a11  mov     ecx, eax; int
0x180019a13  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180019a18  mov     rcx, [rdi+8]; this
0x180019a1c  lea     rdx, [rbp+57h+Destination]; unsigned __int16 *
0x180019a20  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x180019a25  test    rax, rax
0x180019a28  jz      loc_180019AC7
0x180019a2e  mov     [rbp+57h+var_80], r15
0x180019a32  or      r8, 0FFFFFFFFFFFFFFFFh
0x180019a36  inc     r8; int
0x180019a39  cmp     [rax+r8*2], r15w
0x180019a3e  jnz     short loc_180019A36
0x180019a40  mov     rdx, rax; unsigned __int16 *
0x180019a43  lea     rcx, [rbp+57h+var_90]; this
0x180019a47  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180019a4c  lea     rcx, [rbp+57h+var_80]
0x180019a50  mov     ebx, eax
0x180019a52  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180019a57  test    ebx, ebx
0x180019a59  jz      short loc_180019ACE
0x180019a5b  mov     rax, [rdi]
0x180019a5e  jmp     short loc_180019A6C
0x180019a60  mov     rcx, rax; lpsz
0x180019a63  call    cs:__imp_CharNextW
0x180019a69  mov     [rdi], rax
0x180019a6c  cmp     rax, rsi
0x180019a6f  jnz     short loc_180019A60
0x180019a71  jmp     short loc_180019A89
0x180019a73  mov     rdx, rbx; unsigned __int16 *
0x180019a76  mov     r8d, 1; int
0x180019a7c  lea     rcx, [rbp+57h+var_90]; this
0x180019a80  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180019a85  test    eax, eax
0x180019a87  jz      short loc_180019ACE
0x180019a89  mov     rcx, [rdi]; lpsz
0x180019a8c  call    cs:__imp_CharNextW
0x180019a92  mov     rbx, rax
0x180019a95  mov     [rdi], rax
0x180019a98  movzx   eax, word ptr [rax]
0x180019a9b  test    ax, ax
0x180019a9e  jnz     loc_1800199AE
0x180019aa4  mov     rcx, [rbp+57h+pv]
0x180019aa8  mov     ebx, r15d
0x180019aab  mov     [rbp+57h+pv], r15
0x180019aaf  mov     [r14], rcx
0x180019ab2  mov     rcx, [rbp+57h+pv]; pv
0x180019ab6  call    cs:__imp_CoTaskMemFree
0x180019abc  mov     eax, ebx
0x180019abe  jmp     short loc_180019ADA
0x180019ac0  mov     ebx, 80004005h
0x180019ac5  jmp     short loc_180019AB2
0x180019ac7  mov     ebx, 80020009h
0x180019acc  jmp     short loc_180019AB2
0x180019ace  mov     ebx, 8007000Eh
0x180019ad3  jmp     short loc_180019AB2
0x180019ad5  mov     eax, 80004003h
0x180019ada  mov     rcx, [rbp+57h+var_30]
0x180019ade  xor     rcx, rsp; StackCookie
0x180019ae1  call    __security_check_cookie
0x180019ae6  lea     r11, [rsp+0B0h+var_20]
0x180019aee  mov     rbx, [r11+38h]
0x180019af2  mov     rsi, [r11+48h]
0x180019af6  mov     rsp, r11
0x180019af9  pop     r15
0x180019afb  pop     r14
0x180019afd  pop     r12
0x180019aff  pop     rdi
0x180019b00  pop     rbp
0x180019b01  retn
```
