# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800088ac`
- end: `0x180008b34`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `648`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180008ce8`

## callees

- `0x180007a28`
- `0x1800088ac`
- `0x1800157f0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800089e0`
- `msvcrt!wcsncpy_s` at `0x1800089e0`
- `KERNEL32!lstrcmpiW` at `0x180008a0d`
- `KERNEL32!lstrcmpiW` at `0x180008a0d`
- `KERNEL32!LeaveCriticalSection` at `0x180008a25`
- `KERNEL32!LeaveCriticalSection` at `0x180008a25`
- `KERNEL32!RaiseException` at `0x180008aea`
- `KERNEL32!RaiseException` at `0x180008aea`
- `KERNEL32!EnterCriticalSection` at `0x1800089ee`
- `KERNEL32!EnterCriticalSection` at `0x1800089ee`
- `USER32!CharNextW` at `0x180008970`
- `USER32!CharNextW` at `0x1800089a1`
- `USER32!CharNextW` at `0x180008a7a`
- `USER32!CharNextW` at `0x180008aa4`
- `USER32!CharNextW` at `0x180008970`
- `USER32!CharNextW` at `0x1800089a1`
- `USER32!CharNextW` at `0x180008a7a`
- `USER32!CharNextW` at `0x180008aa4`
- `ole32!CoTaskMemAlloc` at `0x18000893d`
- `ole32!CoTaskMemAlloc` at `0x18000893d`
- `ole32!CoTaskMemFree` at `0x18000892b`
- `ole32!CoTaskMemFree` at `0x180008ad1`
- `ole32!CoTaskMemFree` at `0x18000892b`
- `ole32!CoTaskMemFree` at `0x180008ad1`

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
  LPCWSTR v18; // rbp
  int v19; // ebx
  const unsigned __int16 *v20; // rbx
  __int64 v21; // r8
  const WCHAR *i; // rax
  unsigned int v23; // ebx
  _DWORD v24[2]; // [rsp+20h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-80h]
  wchar_t Destination[32]; // [rsp+30h] [rbp-78h] BYREF

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
  *this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_44:
    v23 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_45;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_41:
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v15, 1) )
      goto LABEL_49;
LABEL_42:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v9 = pv;
      goto LABEL_44;
    }
  }
  v13 = CharNextW(v4);
  *this = v13;
  v14 = *v13;
  if ( *v13 == 37 )
  {
    v15 = v13;
    goto LABEL_41;
  }
  if ( !v13 )
    goto LABEL_48;
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
    goto LABEL_48;
  v17 = v16 - *this;
  if ( v17 > 31 )
  {
    v23 = -2147467259;
    goto LABEL_45;
  }
  wcsncpy_s(Destination, 0x20u, *this, (int)v17);
  v18 = this[1];
  EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
  v19 = 0;
  if ( *((int *)v18 + 6) <= 0 )
    goto LABEL_27;
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v18 + 1) + 8LL * v19), Destination) )
  {
    if ( ++v19 >= *((_DWORD *)v18 + 6) )
      goto LABEL_27;
  }
  if ( v19 == -1 )
  {
LABEL_27:
    v20 = 0;
  }
  else
  {
    if ( v19 < 0 || v19 >= *((_DWORD *)v18 + 6) )
    {
      RaiseException(0xC000008C, 1u, 0, 0);
      __debugbreak();
    }
    v20 = *(const unsigned __int16 **)(*((_QWORD *)v18 + 2) + 8LL * v19);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
  if ( !v20 )
  {
LABEL_48:
    v23 = -2147352567;
    goto LABEL_45;
  }
  v21 = -1;
  do
    ++v21;
  while ( v20[v21] );
  if ( (unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v20, v21) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_42;
  }
LABEL_49:
  v23 = -2147024882;
LABEL_45:
  CoTaskMemFree(pv);
  return v23;
}

```

## disassembly

```asm
0x1800088ac  mov     [rsp+arg_8], rbx
0x1800088b1  mov     [rsp+arg_18], rbp
0x1800088b6  push    rsi
0x1800088b7  push    rdi
0x1800088b8  push    r12
0x1800088ba  push    r14
0x1800088bc  push    r15
0x1800088be  sub     rsp, 80h
0x1800088c5  mov     rax, cs:__security_cookie
0x1800088cc  xor     rax, rsp
0x1800088cf  mov     [rsp+0A8h+var_38], rax
0x1800088d4  xor     r12d, r12d
0x1800088d7  mov     r14, r8
0x1800088da  mov     rbx, rdx
0x1800088dd  mov     rsi, rcx
0x1800088e0  test    rdx, rdx
0x1800088e3  jz      loc_180008B06
0x1800088e9  test    r8, r8
0x1800088ec  jz      loc_180008B06
0x1800088f2  mov     [r8], r12
0x1800088f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800088f9  inc     rax
0x1800088fc  cmp     [rdx+rax*2], r12w
0x180008901  jnz     short loc_1800088F9
0x180008903  add     eax, eax
0x180008905  mov     [rsp+0A8h+var_88], r12d
0x18000890a  cmp     eax, 64h ; 'd'
0x18000890d  mov     ecx, 3E8h
0x180008912  cmovl   eax, ecx
0x180008915  mov     ecx, eax
0x180008917  mov     [rsp+0A8h+var_84], eax
0x18000891b  add     rcx, rcx
0x18000891e  mov     eax, 0FFFFFFFFh
0x180008923  cmp     rcx, rax
0x180008926  jbe     short loc_18000893B
0x180008928  mov     rcx, r12; pv
0x18000892b  call    cs:__imp_CoTaskMemFree
0x180008931  mov     eax, 8007000Eh
0x180008936  jmp     loc_180008B0B
0x18000893b  mov     ecx, ecx; cb
0x18000893d  call    cs:__imp_CoTaskMemAlloc
0x180008943  mov     [rsp+0A8h+pv], rax
0x180008948  mov     rcx, rax
0x18000894b  test    rax, rax
0x18000894e  jz      short loc_18000892B
0x180008950  mov     [rax], r12w
0x180008954  mov     [rsi], rbx
0x180008957  movzx   eax, word ptr [rbx]
0x18000895a  test    ax, ax
0x18000895d  jz      loc_180008AC1
0x180008963  cmp     ax, 25h ; '%'
0x180008967  jnz     loc_180008A8A
0x18000896d  mov     rcx, rbx; lpsz
0x180008970  call    cs:__imp_CharNextW
0x180008976  mov     [rsi], rax
0x180008979  movzx   ecx, word ptr [rax]
0x18000897c  cmp     cx, 25h ; '%'
0x180008980  jnz     short loc_18000898A
0x180008982  mov     rdx, rax
0x180008985  jmp     loc_180008A8D
0x18000898a  test    rax, rax
0x18000898d  jz      loc_180008AF8
0x180008993  mov     rdi, r12
0x180008996  jmp     short loc_1800089AA
0x180008998  cmp     cx, 25h ; '%'
0x18000899c  jz      short loc_1800089B1
0x18000899e  mov     rcx, rax; lpsz
0x1800089a1  call    cs:__imp_CharNextW
0x1800089a7  movzx   ecx, word ptr [rax]
0x1800089aa  test    cx, cx
0x1800089ad  jnz     short loc_180008998
0x1800089af  jmp     short loc_1800089B4
0x1800089b1  mov     rdi, rax
0x1800089b4  test    rdi, rdi
0x1800089b7  jz      loc_180008AF8
0x1800089bd  mov     rax, rdi
0x1800089c0  sub     rax, [rsi]
0x1800089c3  sar     rax, 1
0x1800089c6  cmp     rax, 1Fh
0x1800089ca  jg      loc_180008AF1
0x1800089d0  mov     r8, [rsi]; Source
0x1800089d3  lea     rcx, [rsp+0A8h+Destination]; Destination
0x1800089d8  movsxd  r9, eax; MaxCount
0x1800089db  mov     edx, 20h ; ' '; SizeInWords
0x1800089e0  call    cs:__imp_wcsncpy_s
0x1800089e6  mov     rbp, [rsi+8]
0x1800089ea  lea     rcx, [rbp+20h]; lpCriticalSection
0x1800089ee  call    cs:__imp_EnterCriticalSection
0x1800089f4  mov     ebx, r12d
0x1800089f7  cmp     [rbp+18h], r12d
0x1800089fb  jle     short loc_180008A1E
0x1800089fd  mov     rcx, [rbp+8]
0x180008a01  lea     rdx, [rsp+0A8h+Destination]; lpString2
0x180008a06  movsxd  rax, ebx
0x180008a09  mov     rcx, [rcx+rax*8]; lpString1
0x180008a0d  call    cs:__imp_lstrcmpiW
0x180008a13  test    eax, eax
0x180008a15  jz      short loc_180008A5C
0x180008a17  inc     ebx
0x180008a19  cmp     ebx, [rbp+18h]
0x180008a1c  jl      short loc_1800089FD
0x180008a1e  mov     rbx, r12
0x180008a21  lea     rcx, [rbp+20h]; lpCriticalSection
0x180008a25  call    cs:__imp_LeaveCriticalSection
0x180008a2b  test    rbx, rbx
0x180008a2e  jz      loc_180008AF8
0x180008a34  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008a38  inc     r8; int
0x180008a3b  cmp     [rbx+r8*2], r12w
0x180008a40  jnz     short loc_180008A38
0x180008a42  mov     rdx, rbx; unsigned __int16 *
0x180008a45  lea     rcx, [rsp+0A8h+var_88]; this
0x180008a4a  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180008a4f  test    eax, eax
0x180008a51  jz      loc_180008AFF
0x180008a57  mov     rax, [rsi]
0x180008a5a  jmp     short loc_180008A83
0x180008a5c  cmp     ebx, 0FFFFFFFFh
0x180008a5f  jz      short loc_180008A1E
0x180008a61  test    ebx, ebx
0x180008a63  js      short loc_180008ADB
0x180008a65  cmp     ebx, [rbp+18h]
0x180008a68  jge     short loc_180008ADB
0x180008a6a  mov     rax, [rbp+10h]
0x180008a6e  movsxd  rcx, ebx
0x180008a71  mov     rbx, [rax+rcx*8]
0x180008a75  jmp     short loc_180008A21
0x180008a77  mov     rcx, rax; lpsz
0x180008a7a  call    cs:__imp_CharNextW
0x180008a80  mov     [rsi], rax
0x180008a83  cmp     rax, rdi
0x180008a86  jnz     short loc_180008A77
0x180008a88  jmp     short loc_180008AA1
0x180008a8a  mov     rdx, rbx; unsigned __int16 *
0x180008a8d  mov     r8d, 1; int
0x180008a93  lea     rcx, [rsp+0A8h+var_88]; this
0x180008a98  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180008a9d  test    eax, eax
0x180008a9f  jz      short loc_180008AFF
0x180008aa1  mov     rcx, [rsi]; lpsz
0x180008aa4  call    cs:__imp_CharNextW
0x180008aaa  mov     rbx, rax
0x180008aad  mov     [rsi], rax
0x180008ab0  movzx   eax, word ptr [rax]
0x180008ab3  test    ax, ax
0x180008ab6  jnz     loc_180008963
0x180008abc  mov     rcx, [rsp+0A8h+pv]
0x180008ac1  mov     ebx, r12d
0x180008ac4  mov     [rsp+0A8h+pv], r12
0x180008ac9  mov     [r14], rcx
0x180008acc  mov     rcx, [rsp+0A8h+pv]; pv
0x180008ad1  call    cs:__imp_CoTaskMemFree
0x180008ad7  mov     eax, ebx
0x180008ad9  jmp     short loc_180008B0B
0x180008adb  xor     r9d, r9d; lpArguments
0x180008ade  xor     r8d, r8d; nNumberOfArguments
0x180008ae1  mov     ecx, 0C000008Ch; dwExceptionCode
0x180008ae6  lea     edx, [r9+1]; dwExceptionFlags
0x180008aea  call    cs:__imp_RaiseException
0x180008af0  int     3; Trap to Debugger
0x180008af1  mov     ebx, 80004005h
0x180008af6  jmp     short loc_180008ACC
0x180008af8  mov     ebx, 80020009h
0x180008afd  jmp     short loc_180008ACC
0x180008aff  mov     ebx, 8007000Eh
0x180008b04  jmp     short loc_180008ACC
0x180008b06  mov     eax, 80004003h
0x180008b0b  mov     rcx, [rsp+0A8h+var_38]
0x180008b10  xor     rcx, rsp; StackCookie
0x180008b13  call    __security_check_cookie
0x180008b18  lea     r11, [rsp+0A8h+var_28]
0x180008b20  mov     rbx, [r11+38h]
0x180008b24  mov     rbp, [r11+48h]
0x180008b28  mov     rsp, r11
0x180008b2b  pop     r15
0x180008b2d  pop     r14
0x180008b2f  pop     r12
0x180008b31  pop     rdi
0x180008b32  pop     rsi
0x180008b33  retn
```
