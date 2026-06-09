# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180007d4c`
- end: `0x18000802b`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `735`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180008430`

## callees

- `0x180004bb0`
- `0x180004ec8`
- `0x180007d4c`
- `0x18000a0ec`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180007e8f`
- `msvcrt!wcsncpy_s` at `0x180007e8f`
- `USER32!CharNextW` at `0x180007e20`
- `USER32!CharNextW` at `0x180007e51`
- `USER32!CharNextW` at `0x180007f5c`
- `USER32!CharNextW` at `0x180007f85`
- `USER32!CharNextW` at `0x180007e20`
- `USER32!CharNextW` at `0x180007e51`
- `USER32!CharNextW` at `0x180007f5c`
- `USER32!CharNextW` at `0x180007f85`
- `ole32!CoTaskMemFree` at `0x180007df4`
- `ole32!CoTaskMemFree` at `0x180007fb4`
- `ole32!CoTaskMemFree` at `0x180007df4`
- `ole32!CoTaskMemFree` at `0x180007fb4`
- `ole32!CoTaskMemAlloc` at `0x180007dd6`
- `ole32!CoTaskMemAlloc` at `0x180007dd6`
- `KERNEL32!LeaveCriticalSection` at `0x180007efb`
- `KERNEL32!LeaveCriticalSection` at `0x180007efb`
- `KERNEL32!lstrcmpiW` at `0x180007ee3`
- `KERNEL32!lstrcmpiW` at `0x180007ee3`
- `KERNEL32!EnterCriticalSection` at `0x180007ec5`
- `KERNEL32!EnterCriticalSection` at `0x180007ec5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdx
  WCHAR v12; // ax
  LPWSTR v13; // rax
  WCHAR v14; // cx
  const unsigned __int16 *v15; // rdx
  const WCHAR *v16; // rdi
  __int64 v17; // rax
  errno_t v18; // eax
  LPCWSTR v19; // rsi
  int v20; // ebx
  unsigned int v21; // edx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  const WCHAR *i; // rax
  unsigned int v25; // ebx
  __int64 v26; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v28; // [rsp+30h] [rbp-39h]
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
  LODWORD(v26) = 0;
  HIDWORD(v26) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)v8);
    v10 = v9;
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    v10 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_51:
    v25 = 0;
    pv = 0;
    v26 = 0;
    *a3 = v10;
    goto LABEL_52;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_48:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v26, v15, 1) )
      goto LABEL_55;
LABEL_49:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v10 = (unsigned __int16 *)pv;
      goto LABEL_51;
    }
  }
  v13 = CharNextW(v4);
  *this = v13;
  v14 = *v13;
  if ( *v13 == 37 )
  {
    v15 = v13;
    goto LABEL_48;
  }
  if ( !v13 )
    goto LABEL_54;
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
    goto LABEL_54;
  v17 = v16 - *this;
  if ( v17 > 31 )
  {
    v25 = -2147467259;
    goto LABEL_52;
  }
  v18 = wcsncpy_s(Destination, 0x20u, *this, (int)v17);
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
    goto LABEL_34;
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), Destination) )
  {
    if ( ++v20 >= *((_DWORD *)v19 + 6) )
      goto LABEL_34;
  }
  if ( v20 == -1 )
  {
LABEL_34:
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
LABEL_54:
    v25 = -2147352567;
    goto LABEL_52;
  }
  v28 = 0;
  v23 = -1;
  do
    ++v23;
  while ( v22[v23] );
  if ( ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v26, v22, v23) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_49;
  }
LABEL_55:
  v25 = -2147024882;
LABEL_52:
  CoTaskMemFree(pv);
  return v25;
}

```

## disassembly

```asm
0x180007d4c  mov     [rsp-8+arg_8], rbx
0x180007d51  push    rbp
0x180007d52  push    rsi
0x180007d53  push    rdi
0x180007d54  push    r12
0x180007d56  push    r13
0x180007d58  push    r14
0x180007d5a  push    r15
0x180007d5c  lea     rbp, [rsp-27h]
0x180007d61  sub     rsp, 90h
0x180007d68  mov     rax, cs:__security_cookie
0x180007d6f  xor     rax, rsp
0x180007d72  mov     [rbp+57h+var_40], rax
0x180007d76  mov     r12, r8
0x180007d79  mov     rbx, rdx
0x180007d7c  mov     r14, rcx
0x180007d7f  xor     r13d, r13d
0x180007d82  test    rdx, rdx
0x180007d85  jz      loc_180007FD3
0x180007d8b  test    r8, r8
0x180007d8e  jz      loc_180007FD3
0x180007d94  mov     [r8], r13
0x180007d97  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007d9b  inc     rax
0x180007d9e  cmp     [rdx+rax*2], r13w
0x180007da3  jnz     short loc_180007D9B
0x180007da5  add     eax, eax
0x180007da7  mov     ecx, 3E8h
0x180007dac  cmp     eax, 64h ; 'd'
0x180007daf  cmovl   eax, ecx
0x180007db2  mov     dword ptr [rbp+57h+var_A0], r13d
0x180007db6  mov     dword ptr [rbp+57h+var_A0+4], eax
0x180007db9  mov     ecx, eax
0x180007dbb  add     rcx, rcx
0x180007dbe  mov     eax, 0FFFFFFFFh
0x180007dc3  cmp     rcx, rax
0x180007dc6  jbe     short loc_180007DD4
0x180007dc8  mov     rax, r13
0x180007dcb  mov     rdx, r13
0x180007dce  mov     [rbp+57h+pv], rdx
0x180007dd2  jmp     short loc_180007DEC
0x180007dd4  mov     ecx, ecx; cb
0x180007dd6  call    cs:__imp_CoTaskMemAlloc
0x180007ddc  mov     rdx, rax
0x180007ddf  mov     [rbp+57h+pv], rax
0x180007de3  test    rax, rax
0x180007de6  jz      short loc_180007DEC
0x180007de8  mov     [rax], r13w
0x180007dec  test    rax, rax
0x180007def  jnz     short loc_180007E04
0x180007df1  mov     rcx, rax; pv
0x180007df4  call    cs:__imp_CoTaskMemFree
0x180007dfa  mov     eax, 8007000Eh
0x180007dff  jmp     loc_180007FD8
0x180007e04  mov     [r14], rbx
0x180007e07  movzx   eax, word ptr [rbx]
0x180007e0a  test    ax, ax
0x180007e0d  jz      loc_180007FA1
0x180007e13  cmp     ax, 25h ; '%'
0x180007e17  jnz     loc_180007F6C
0x180007e1d  mov     rcx, rbx; lpsz
0x180007e20  call    cs:__imp_CharNextW
0x180007e26  mov     [r14], rax
0x180007e29  movzx   ecx, word ptr [rax]
0x180007e2c  cmp     cx, 25h ; '%'
0x180007e30  jnz     short loc_180007E3A
0x180007e32  mov     rdx, rax
0x180007e35  jmp     loc_180007F6F
0x180007e3a  test    rax, rax
0x180007e3d  jz      loc_180007FC5
0x180007e43  mov     rdi, r13
0x180007e46  jmp     short loc_180007E5A
0x180007e48  cmp     cx, 25h ; '%'
0x180007e4c  jz      short loc_180007E61
0x180007e4e  mov     rcx, rax; lpsz
0x180007e51  call    cs:__imp_CharNextW
0x180007e57  movzx   ecx, word ptr [rax]
0x180007e5a  test    cx, cx
0x180007e5d  jnz     short loc_180007E48
0x180007e5f  jmp     short loc_180007E64
0x180007e61  mov     rdi, rax
0x180007e64  test    rdi, rdi
0x180007e67  jz      loc_180007FC5
0x180007e6d  mov     rax, rdi
0x180007e70  sub     rax, [r14]
0x180007e73  sar     rax, 1
0x180007e76  cmp     rax, 1Fh
0x180007e7a  jg      loc_180007FBE
0x180007e80  movsxd  r9, eax; MaxCount
0x180007e83  mov     r8, [r14]; Source
0x180007e86  mov     edx, 20h ; ' '; SizeInWords
0x180007e8b  lea     rcx, [rbp+57h+Destination]; Destination
0x180007e8f  call    cs:__imp_wcsncpy_s
0x180007e95  test    eax, eax
0x180007e97  jz      short loc_180007EBD
0x180007e99  cmp     eax, 0Ch
0x180007e9c  jz      loc_180008020
0x180007ea2  cmp     eax, 16h
0x180007ea5  jz      loc_180008015
0x180007eab  cmp     eax, 22h ; '"'
0x180007eae  jz      loc_180008015
0x180007eb4  cmp     eax, 50h ; 'P'
0x180007eb7  jnz     loc_18000800A
0x180007ebd  mov     rsi, [r14+8]
0x180007ec1  lea     rcx, [rsi+20h]; lpCriticalSection
0x180007ec5  call    cs:__imp_EnterCriticalSection
0x180007ecb  mov     ebx, r13d
0x180007ece  cmp     [rsi+18h], r13d
0x180007ed2  jle     short loc_180007EF4
0x180007ed4  movsxd  rax, ebx
0x180007ed7  mov     rcx, [rsi+8]
0x180007edb  lea     rdx, [rbp+57h+Destination]; lpString2
0x180007edf  mov     rcx, [rcx+rax*8]; lpString1
0x180007ee3  call    cs:__imp_lstrcmpiW
0x180007ee9  test    eax, eax
0x180007eeb  jz      short loc_180007F36
0x180007eed  inc     ebx
0x180007eef  cmp     ebx, [rsi+18h]
0x180007ef2  jl      short loc_180007ED4
0x180007ef4  mov     rbx, r13
0x180007ef7  lea     rcx, [rsi+20h]; lpCriticalSection
0x180007efb  call    cs:__imp_LeaveCriticalSection
0x180007f01  test    rbx, rbx
0x180007f04  jz      loc_180007FC5
0x180007f0a  mov     [rbp+57h+var_90], r13
0x180007f0e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007f12  inc     r8; int
0x180007f15  cmp     [rbx+r8*2], r13w
0x180007f1a  jnz     short loc_180007F12
0x180007f1c  mov     rdx, rbx; unsigned __int16 *
0x180007f1f  lea     rcx, [rbp+57h+var_A0]; this
0x180007f23  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180007f28  nop
0x180007f29  test    eax, eax
0x180007f2b  jz      loc_180007FCC
0x180007f31  mov     rax, [r14]
0x180007f34  jmp     short loc_180007F65
0x180007f36  cmp     ebx, 0FFFFFFFFh
0x180007f39  jz      short loc_180007EF4
0x180007f3b  test    ebx, ebx
0x180007f3d  js      loc_180007FFF
0x180007f43  cmp     ebx, [rsi+18h]
0x180007f46  jge     loc_180007FFF
0x180007f4c  movsxd  rcx, ebx
0x180007f4f  mov     rax, [rsi+10h]
0x180007f53  mov     rbx, [rax+rcx*8]
0x180007f57  jmp     short loc_180007EF7
0x180007f59  mov     rcx, rax; lpsz
0x180007f5c  call    cs:__imp_CharNextW
0x180007f62  mov     [r14], rax
0x180007f65  cmp     rax, rdi
0x180007f68  jnz     short loc_180007F59
0x180007f6a  jmp     short loc_180007F82
0x180007f6c  mov     rdx, rbx; unsigned __int16 *
0x180007f6f  mov     r8d, 1; int
0x180007f75  lea     rcx, [rbp+57h+var_A0]; this
0x180007f79  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180007f7e  test    eax, eax
0x180007f80  jz      short loc_180007FCC
0x180007f82  mov     rcx, [r14]; lpsz
0x180007f85  call    cs:__imp_CharNextW
0x180007f8b  mov     rbx, rax
0x180007f8e  mov     [r14], rax
0x180007f91  movzx   eax, word ptr [rax]
0x180007f94  test    ax, ax
0x180007f97  jnz     loc_180007E13
0x180007f9d  mov     rdx, [rbp+57h+pv]
0x180007fa1  mov     ebx, r13d
0x180007fa4  mov     [rbp+57h+pv], r13
0x180007fa8  mov     [rbp+57h+var_A0], r13
0x180007fac  mov     [r12], rdx
0x180007fb0  mov     rcx, [rbp+57h+pv]; pv
0x180007fb4  call    cs:__imp_CoTaskMemFree
0x180007fba  mov     eax, ebx
0x180007fbc  jmp     short loc_180007FD8
0x180007fbe  mov     ebx, 80004005h
0x180007fc3  jmp     short loc_180007FB0
0x180007fc5  mov     ebx, 80020009h
0x180007fca  jmp     short loc_180007FB0
0x180007fcc  mov     ebx, 8007000Eh
0x180007fd1  jmp     short loc_180007FB0
0x180007fd3  mov     eax, 80004003h
0x180007fd8  mov     rcx, [rbp+57h+var_40]
0x180007fdc  xor     rcx, rsp; StackCookie
0x180007fdf  call    __security_check_cookie
0x180007fe4  mov     rbx, [rsp+0C0h+arg_8]
0x180007fec  add     rsp, 90h
0x180007ff3  pop     r15
0x180007ff5  pop     r14
0x180007ff7  pop     r13
0x180007ff9  pop     r12
0x180007ffb  pop     rdi
0x180007ffc  pop     rsi
0x180007ffd  pop     rbp
0x180007ffe  retn
0x180007fff  mov     ecx, 0C000008Ch; unsigned int
0x180008004  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180008009  int     3; Trap to Debugger
0x18000800a  mov     ecx, 80004005h; int
0x18000800f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008015  mov     ecx, 80070057h; int
0x18000801a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008020  mov     ecx, 8007000Eh; int
0x180008025  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
