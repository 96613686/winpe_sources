# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x140003924`
- end: `0x140003bf2`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `718`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140003e1c`

## callees

- `0x1400014f0`
- `0x140002ecc`
- `0x140003004`
- `0x140003924`
- `0x14000539c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140003a58`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140003a58`
- `KERNEL32!EnterCriticalSection` at `0x140003a8e`
- `KERNEL32!EnterCriticalSection` at `0x140003a8e`
- `KERNEL32!LeaveCriticalSection` at `0x140003ac5`
- `KERNEL32!LeaveCriticalSection` at `0x140003ac5`
- `KERNEL32!lstrcmpiW` at `0x140003aad`
- `KERNEL32!lstrcmpiW` at `0x140003aad`
- `USER32!CharNextW` at `0x1400039e8`
- `USER32!CharNextW` at `0x140003a19`
- `USER32!CharNextW` at `0x140003b22`
- `USER32!CharNextW` at `0x140003b4c`
- `USER32!CharNextW` at `0x1400039e8`
- `USER32!CharNextW` at `0x140003a19`
- `USER32!CharNextW` at `0x140003b22`
- `USER32!CharNextW` at `0x140003b4c`
- `ole32!CoTaskMemAlloc` at `0x1400039b5`
- `ole32!CoTaskMemAlloc` at `0x1400039b5`
- `ole32!CoTaskMemFree` at `0x1400039a3`
- `ole32!CoTaskMemFree` at `0x140003b79`
- `ole32!CoTaskMemFree` at `0x1400039a3`
- `ole32!CoTaskMemFree` at `0x140003b79`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  void *v9; // rcx
  _WORD *v11; // rax
  WCHAR v12; // ax
  LPWSTR v13; // rax
  WCHAR v14; // cx
  const unsigned __int16 *v15; // rdx
  const WCHAR *v16; // rdi
  __int64 v17; // rax
  int v18; // eax
  LPCWSTR v19; // rsi
  int v20; // ebx
  unsigned int v21; // edx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  const WCHAR *i; // rax
  unsigned int v25; // ebx
  _DWORD v26[2]; // [rsp+20h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-80h]
  WCHAR String2[32]; // [rsp+30h] [rbp-78h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  v26[0] = 0;
  if ( v7 < 100 )
    v7 = 1000;
  v26[1] = v7;
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
  *this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_49:
    v25 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_50;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_46:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v15, 1) )
      goto LABEL_53;
LABEL_47:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v9 = pv;
      goto LABEL_49;
    }
  }
  v13 = CharNextW(v4);
  *this = v13;
  v14 = *v13;
  if ( *v13 == 37 )
  {
    v15 = v13;
    goto LABEL_46;
  }
  if ( !v13 )
    goto LABEL_52;
  v16 = 0;
  while ( v14 )
  {
    if ( v14 == 37 )
    {
      v16 = v13;
      break;
    }
    v13 = CharNextW(v13);
    v14 = *v13;
  }
  if ( !v16 )
    goto LABEL_52;
  v17 = v16 - *this;
  if ( v17 > 31 )
  {
    v25 = -2147467259;
    goto LABEL_50;
  }
  v18 = _o_wcsncpy_s(String2, 32, *this, (int)v17);
  if ( v18 )
  {
    if ( v18 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v18 == 22 || v18 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v18 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  v19 = this[1];
  EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  v20 = 0;
  if ( *((int *)v19 + 6) <= 0 )
    goto LABEL_32;
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), String2) )
  {
    if ( ++v20 >= *((_DWORD *)v19 + 6) )
      goto LABEL_32;
  }
  if ( v20 == -1 )
  {
LABEL_32:
    v22 = 0;
  }
  else
  {
    if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
    {
      ATL::_AtlRaiseException(0xC000008C, v21);
      __debugbreak();
    }
    v22 = *(const unsigned __int16 **)(*((_QWORD *)v19 + 2) + 8LL * v20);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  if ( !v22 )
  {
LABEL_52:
    v25 = -2147352567;
    goto LABEL_50;
  }
  v23 = -1;
  do
    ++v23;
  while ( v22[v23] );
  if ( ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v22, v23) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_47;
  }
LABEL_53:
  v25 = -2147024882;
LABEL_50:
  CoTaskMemFree(pv);
  return v25;
}

```

## disassembly

```asm
0x140003924  mov     [rsp+arg_8], rbx
0x140003929  mov     [rsp+arg_18], rbp
0x14000392e  push    rsi
0x14000392f  push    rdi
0x140003930  push    r12
0x140003932  push    r14
0x140003934  push    r15
0x140003936  sub     rsp, 80h
0x14000393d  mov     rax, cs:__security_cookie
0x140003944  xor     rax, rsp
0x140003947  mov     [rsp+0A8h+var_38], rax
0x14000394c  xor     r12d, r12d
0x14000394f  mov     r15, r8
0x140003952  mov     rbx, rdx
0x140003955  mov     r14, rcx
0x140003958  test    rdx, rdx
0x14000395b  jz      loc_140003B98
0x140003961  test    r8, r8
0x140003964  jz      loc_140003B98
0x14000396a  mov     [r8], r12
0x14000396d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003971  inc     rax
0x140003974  cmp     [rdx+rax*2], r12w
0x140003979  jnz     short loc_140003971
0x14000397b  add     eax, eax
0x14000397d  mov     [rsp+0A8h+var_88], r12d
0x140003982  cmp     eax, 64h ; 'd'
0x140003985  mov     ecx, 3E8h
0x14000398a  cmovl   eax, ecx
0x14000398d  mov     ecx, eax
0x14000398f  mov     [rsp+0A8h+var_84], eax
0x140003993  add     rcx, rcx
0x140003996  mov     eax, 0FFFFFFFFh
0x14000399b  cmp     rcx, rax
0x14000399e  jbe     short loc_1400039B3
0x1400039a0  mov     rcx, r12; pv
0x1400039a3  call    cs:__imp_CoTaskMemFree
0x1400039a9  mov     eax, 8007000Eh
0x1400039ae  jmp     loc_140003B9D
0x1400039b3  mov     ecx, ecx; cb
0x1400039b5  call    cs:__imp_CoTaskMemAlloc
0x1400039bb  mov     [rsp+0A8h+pv], rax
0x1400039c0  mov     rcx, rax
0x1400039c3  test    rax, rax
0x1400039c6  jz      short loc_1400039A3
0x1400039c8  mov     [rax], r12w
0x1400039cc  mov     [r14], rbx
0x1400039cf  movzx   eax, word ptr [rbx]
0x1400039d2  test    ax, ax
0x1400039d5  jz      loc_140003B69
0x1400039db  cmp     ax, 25h ; '%'
0x1400039df  jnz     loc_140003B32
0x1400039e5  mov     rcx, rbx; lpsz
0x1400039e8  call    cs:__imp_CharNextW
0x1400039ee  mov     [r14], rax
0x1400039f1  movzx   ecx, word ptr [rax]
0x1400039f4  cmp     cx, 25h ; '%'
0x1400039f8  jnz     short loc_140003A02
0x1400039fa  mov     rdx, rax
0x1400039fd  jmp     loc_140003B35
0x140003a02  test    rax, rax
0x140003a05  jz      loc_140003B8A
0x140003a0b  mov     rdi, r12
0x140003a0e  jmp     short loc_140003A22
0x140003a10  cmp     cx, 25h ; '%'
0x140003a14  jz      short loc_140003A29
0x140003a16  mov     rcx, rax; lpsz
0x140003a19  call    cs:__imp_CharNextW
0x140003a1f  movzx   ecx, word ptr [rax]
0x140003a22  test    cx, cx
0x140003a25  jnz     short loc_140003A10
0x140003a27  jmp     short loc_140003A2C
0x140003a29  mov     rdi, rax
0x140003a2c  test    rdi, rdi
0x140003a2f  jz      loc_140003B8A
0x140003a35  mov     rax, rdi
0x140003a38  sub     rax, [r14]
0x140003a3b  sar     rax, 1
0x140003a3e  cmp     rax, 1Fh
0x140003a42  jg      loc_140003B83
0x140003a48  mov     r8, [r14]
0x140003a4b  lea     rcx, [rsp+0A8h+String2]
0x140003a50  movsxd  r9, eax
0x140003a53  mov     edx, 20h ; ' '
0x140003a58  call    cs:__imp__o_wcsncpy_s
0x140003a5e  test    eax, eax
0x140003a60  jz      short loc_140003A86
0x140003a62  cmp     eax, 0Ch
0x140003a65  jz      loc_140003BE7
0x140003a6b  cmp     eax, 16h
0x140003a6e  jz      loc_140003BDC
0x140003a74  cmp     eax, 22h ; '"'
0x140003a77  jz      loc_140003BDC
0x140003a7d  cmp     eax, 50h ; 'P'
0x140003a80  jnz     loc_140003BD1
0x140003a86  mov     rsi, [r14+8]
0x140003a8a  lea     rcx, [rsi+20h]; lpCriticalSection
0x140003a8e  call    cs:__imp_EnterCriticalSection
0x140003a94  mov     ebx, r12d
0x140003a97  cmp     [rsi+18h], r12d
0x140003a9b  jle     short loc_140003ABE
0x140003a9d  mov     rcx, [rsi+8]
0x140003aa1  lea     rdx, [rsp+0A8h+String2]; lpString2
0x140003aa6  movsxd  rax, ebx
0x140003aa9  mov     rcx, [rcx+rax*8]; lpString1
0x140003aad  call    cs:__imp_lstrcmpiW
0x140003ab3  test    eax, eax
0x140003ab5  jz      short loc_140003AFC
0x140003ab7  inc     ebx
0x140003ab9  cmp     ebx, [rsi+18h]
0x140003abc  jl      short loc_140003A9D
0x140003abe  mov     rbx, r12
0x140003ac1  lea     rcx, [rsi+20h]; lpCriticalSection
0x140003ac5  call    cs:__imp_LeaveCriticalSection
0x140003acb  test    rbx, rbx
0x140003ace  jz      loc_140003B8A
0x140003ad4  or      r8, 0FFFFFFFFFFFFFFFFh
0x140003ad8  inc     r8; int
0x140003adb  cmp     [rbx+r8*2], r12w
0x140003ae0  jnz     short loc_140003AD8
0x140003ae2  mov     rdx, rbx; unsigned __int16 *
0x140003ae5  lea     rcx, [rsp+0A8h+var_88]; this
0x140003aea  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x140003aef  test    eax, eax
0x140003af1  jz      loc_140003B91
0x140003af7  mov     rax, [r14]
0x140003afa  jmp     short loc_140003B2B
0x140003afc  cmp     ebx, 0FFFFFFFFh
0x140003aff  jz      short loc_140003ABE
0x140003b01  test    ebx, ebx
0x140003b03  js      loc_140003BC6
0x140003b09  cmp     ebx, [rsi+18h]
0x140003b0c  jge     loc_140003BC6
0x140003b12  mov     rax, [rsi+10h]
0x140003b16  movsxd  rcx, ebx
0x140003b19  mov     rbx, [rax+rcx*8]
0x140003b1d  jmp     short loc_140003AC1
0x140003b1f  mov     rcx, rax; lpsz
0x140003b22  call    cs:__imp_CharNextW
0x140003b28  mov     [r14], rax
0x140003b2b  cmp     rax, rdi
0x140003b2e  jnz     short loc_140003B1F
0x140003b30  jmp     short loc_140003B49
0x140003b32  mov     rdx, rbx; unsigned __int16 *
0x140003b35  mov     r8d, 1; int
0x140003b3b  lea     rcx, [rsp+0A8h+var_88]; this
0x140003b40  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x140003b45  test    eax, eax
0x140003b47  jz      short loc_140003B91
0x140003b49  mov     rcx, [r14]; lpsz
0x140003b4c  call    cs:__imp_CharNextW
0x140003b52  mov     rbx, rax
0x140003b55  mov     [r14], rax
0x140003b58  movzx   eax, word ptr [rax]
0x140003b5b  test    ax, ax
0x140003b5e  jnz     loc_1400039DB
0x140003b64  mov     rcx, [rsp+0A8h+pv]
0x140003b69  mov     ebx, r12d
0x140003b6c  mov     [rsp+0A8h+pv], r12
0x140003b71  mov     [r15], rcx
0x140003b74  mov     rcx, [rsp+0A8h+pv]; pv
0x140003b79  call    cs:__imp_CoTaskMemFree
0x140003b7f  mov     eax, ebx
0x140003b81  jmp     short loc_140003B9D
0x140003b83  mov     ebx, 80004005h
0x140003b88  jmp     short loc_140003B74
0x140003b8a  mov     ebx, 80020009h
0x140003b8f  jmp     short loc_140003B74
0x140003b91  mov     ebx, 8007000Eh
0x140003b96  jmp     short loc_140003B74
0x140003b98  mov     eax, 80004003h
0x140003b9d  mov     rcx, [rsp+0A8h+var_38]
0x140003ba2  xor     rcx, rsp; StackCookie
0x140003ba5  call    __security_check_cookie
0x140003baa  lea     r11, [rsp+0A8h+var_28]
0x140003bb2  mov     rbx, [r11+38h]
0x140003bb6  mov     rbp, [r11+48h]
0x140003bba  mov     rsp, r11
0x140003bbd  pop     r15
0x140003bbf  pop     r14
0x140003bc1  pop     r12
0x140003bc3  pop     rdi
0x140003bc4  pop     rsi
0x140003bc5  retn
0x140003bc6  mov     ecx, 0C000008Ch; unsigned int
0x140003bcb  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x140003bd0  int     3; Trap to Debugger
0x140003bd1  mov     ecx, 80004005h; int
0x140003bd6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140003bdc  mov     ecx, 80070057h; int
0x140003be1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140003be7  mov     ecx, 8007000Eh; int
0x140003bec  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
