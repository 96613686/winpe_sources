# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180009c8c`
- end: `0x180009f5a`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `718`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a1b8`

## callees

- `0x180008b5c`
- `0x180008c94`
- `0x180009c8c`
- `0x18000c1d4`
- `0x18001a210`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180009dc0`
- `msvcrt!wcsncpy_s` at `0x180009dc0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009e2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009e2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009df6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009df6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009ee1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009ee1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009d1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009d1d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009d50`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009d81`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009e8a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009eb4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009d50`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009d81`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009e8a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009eb4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009e15`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009e15`

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
  errno_t v18; // eax
  __int64 v19; // rdx
  unsigned int v20; // r8d
  LPCWSTR v21; // rsi
  int v22; // ebx
  int v23; // edx
  unsigned int v24; // r8d
  const unsigned __int16 *v25; // rbx
  __int64 v26; // r8
  const WCHAR *i; // rax
  unsigned int v28; // ebx
  _DWORD v29[2]; // [rsp+20h] [rbp-88h] BYREF
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
  v29[0] = 0;
  if ( v7 < 100 )
    v7 = 1000;
  v29[1] = v7;
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
    v28 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_50;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_46:
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v29, v15, 1) )
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
    v28 = -2147467259;
    goto LABEL_50;
  }
  v18 = wcsncpy_s(Destination, 0x20u, *this, (int)v17);
  if ( v18 )
  {
    if ( v18 == 12 )
      ATL::AtlThrowImpl(-2147024882, v19, v20);
    if ( v18 == 22 || v18 == 34 )
      ATL::AtlThrowImpl(-2147024809, v19, v20);
    if ( v18 != 80 )
      ATL::AtlThrowImpl(-2147467259, v19, v20);
  }
  v21 = this[1];
  EnterCriticalSection((LPCRITICAL_SECTION)(v21 + 16));
  v22 = 0;
  if ( *((int *)v21 + 6) <= 0 )
    goto LABEL_32;
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v21 + 1) + 8LL * v22), Destination) )
  {
    if ( ++v22 >= *((_DWORD *)v21 + 6) )
      goto LABEL_32;
  }
  if ( v22 == -1 )
  {
LABEL_32:
    v25 = 0;
  }
  else
  {
    if ( v22 < 0 || v22 >= *((_DWORD *)v21 + 6) )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, v23, v24);
      __debugbreak();
    }
    v25 = *(const unsigned __int16 **)(*((_QWORD *)v21 + 2) + 8LL * v22);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v21 + 16));
  if ( !v25 )
  {
LABEL_52:
    v28 = -2147352567;
    goto LABEL_50;
  }
  v26 = -1;
  do
    ++v26;
  while ( v25[v26] );
  if ( (unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v29, v25, v26) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_47;
  }
LABEL_53:
  v28 = -2147024882;
LABEL_50:
  CoTaskMemFree(pv);
  return v28;
}

```

## disassembly

```asm
0x180009c8c  mov     [rsp+arg_8], rbx
0x180009c91  mov     [rsp+arg_18], rbp
0x180009c96  push    rsi
0x180009c97  push    rdi
0x180009c98  push    r12
0x180009c9a  push    r14
0x180009c9c  push    r15
0x180009c9e  sub     rsp, 80h
0x180009ca5  mov     rax, cs:__security_cookie
0x180009cac  xor     rax, rsp
0x180009caf  mov     [rsp+0A8h+var_38], rax
0x180009cb4  xor     r12d, r12d
0x180009cb7  mov     r15, r8
0x180009cba  mov     rbx, rdx
0x180009cbd  mov     r14, rcx
0x180009cc0  test    rdx, rdx
0x180009cc3  jz      loc_180009F00
0x180009cc9  test    r8, r8
0x180009ccc  jz      loc_180009F00
0x180009cd2  mov     [r8], r12
0x180009cd5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009cd9  inc     rax
0x180009cdc  cmp     [rdx+rax*2], r12w
0x180009ce1  jnz     short loc_180009CD9
0x180009ce3  add     eax, eax
0x180009ce5  mov     [rsp+0A8h+var_88], r12d
0x180009cea  cmp     eax, 64h ; 'd'
0x180009ced  mov     ecx, 3E8h
0x180009cf2  cmovl   eax, ecx
0x180009cf5  mov     ecx, eax
0x180009cf7  mov     [rsp+0A8h+var_84], eax
0x180009cfb  add     rcx, rcx
0x180009cfe  mov     eax, 0FFFFFFFFh
0x180009d03  cmp     rcx, rax
0x180009d06  jbe     short loc_180009D1B
0x180009d08  mov     rcx, r12; pv
0x180009d0b  call    cs:__imp_CoTaskMemFree
0x180009d11  mov     eax, 8007000Eh
0x180009d16  jmp     loc_180009F05
0x180009d1b  mov     ecx, ecx; cb
0x180009d1d  call    cs:__imp_CoTaskMemAlloc
0x180009d23  mov     [rsp+0A8h+pv], rax
0x180009d28  mov     rcx, rax
0x180009d2b  test    rax, rax
0x180009d2e  jz      short loc_180009D0B
0x180009d30  mov     [rax], r12w
0x180009d34  mov     [r14], rbx
0x180009d37  movzx   eax, word ptr [rbx]
0x180009d3a  test    ax, ax
0x180009d3d  jz      loc_180009ED1
0x180009d43  cmp     ax, 25h ; '%'
0x180009d47  jnz     loc_180009E9A
0x180009d4d  mov     rcx, rbx; lpsz
0x180009d50  call    cs:__imp_CharNextW
0x180009d56  mov     [r14], rax
0x180009d59  movzx   ecx, word ptr [rax]
0x180009d5c  cmp     cx, 25h ; '%'
0x180009d60  jnz     short loc_180009D6A
0x180009d62  mov     rdx, rax
0x180009d65  jmp     loc_180009E9D
0x180009d6a  test    rax, rax
0x180009d6d  jz      loc_180009EF2
0x180009d73  mov     rdi, r12
0x180009d76  jmp     short loc_180009D8A
0x180009d78  cmp     cx, 25h ; '%'
0x180009d7c  jz      short loc_180009D91
0x180009d7e  mov     rcx, rax; lpsz
0x180009d81  call    cs:__imp_CharNextW
0x180009d87  movzx   ecx, word ptr [rax]
0x180009d8a  test    cx, cx
0x180009d8d  jnz     short loc_180009D78
0x180009d8f  jmp     short loc_180009D94
0x180009d91  mov     rdi, rax
0x180009d94  test    rdi, rdi
0x180009d97  jz      loc_180009EF2
0x180009d9d  mov     rax, rdi
0x180009da0  sub     rax, [r14]
0x180009da3  sar     rax, 1
0x180009da6  cmp     rax, 1Fh
0x180009daa  jg      loc_180009EEB
0x180009db0  mov     r8, [r14]; Source
0x180009db3  lea     rcx, [rsp+0A8h+Destination]; Destination
0x180009db8  movsxd  r9, eax; MaxCount
0x180009dbb  mov     edx, 20h ; ' '; SizeInWords
0x180009dc0  call    cs:__imp_wcsncpy_s
0x180009dc6  test    eax, eax
0x180009dc8  jz      short loc_180009DEE
0x180009dca  cmp     eax, 0Ch
0x180009dcd  jz      loc_180009F4F
0x180009dd3  cmp     eax, 16h
0x180009dd6  jz      loc_180009F44
0x180009ddc  cmp     eax, 22h ; '"'
0x180009ddf  jz      loc_180009F44
0x180009de5  cmp     eax, 50h ; 'P'
0x180009de8  jnz     loc_180009F39
0x180009dee  mov     rsi, [r14+8]
0x180009df2  lea     rcx, [rsi+20h]; lpCriticalSection
0x180009df6  call    cs:__imp_EnterCriticalSection
0x180009dfc  mov     ebx, r12d
0x180009dff  cmp     [rsi+18h], r12d
0x180009e03  jle     short loc_180009E26
0x180009e05  mov     rcx, [rsi+8]
0x180009e09  lea     rdx, [rsp+0A8h+Destination]; lpString2
0x180009e0e  movsxd  rax, ebx
0x180009e11  mov     rcx, [rcx+rax*8]; lpString1
0x180009e15  call    cs:__imp_lstrcmpiW
0x180009e1b  test    eax, eax
0x180009e1d  jz      short loc_180009E64
0x180009e1f  inc     ebx
0x180009e21  cmp     ebx, [rsi+18h]
0x180009e24  jl      short loc_180009E05
0x180009e26  mov     rbx, r12
0x180009e29  lea     rcx, [rsi+20h]; lpCriticalSection
0x180009e2d  call    cs:__imp_LeaveCriticalSection
0x180009e33  test    rbx, rbx
0x180009e36  jz      loc_180009EF2
0x180009e3c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009e40  inc     r8; int
0x180009e43  cmp     [rbx+r8*2], r12w
0x180009e48  jnz     short loc_180009E40
0x180009e4a  mov     rdx, rbx; unsigned __int16 *
0x180009e4d  lea     rcx, [rsp+0A8h+var_88]; this
0x180009e52  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180009e57  test    eax, eax
0x180009e59  jz      loc_180009EF9
0x180009e5f  mov     rax, [r14]
0x180009e62  jmp     short loc_180009E93
0x180009e64  cmp     ebx, 0FFFFFFFFh
0x180009e67  jz      short loc_180009E26
0x180009e69  test    ebx, ebx
0x180009e6b  js      loc_180009F2E
0x180009e71  cmp     ebx, [rsi+18h]
0x180009e74  jge     loc_180009F2E
0x180009e7a  mov     rax, [rsi+10h]
0x180009e7e  movsxd  rcx, ebx
0x180009e81  mov     rbx, [rax+rcx*8]
0x180009e85  jmp     short loc_180009E29
0x180009e87  mov     rcx, rax; lpsz
0x180009e8a  call    cs:__imp_CharNextW
0x180009e90  mov     [r14], rax
0x180009e93  cmp     rax, rdi
0x180009e96  jnz     short loc_180009E87
0x180009e98  jmp     short loc_180009EB1
0x180009e9a  mov     rdx, rbx; unsigned __int16 *
0x180009e9d  mov     r8d, 1; int
0x180009ea3  lea     rcx, [rsp+0A8h+var_88]; this
0x180009ea8  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180009ead  test    eax, eax
0x180009eaf  jz      short loc_180009EF9
0x180009eb1  mov     rcx, [r14]; lpsz
0x180009eb4  call    cs:__imp_CharNextW
0x180009eba  mov     rbx, rax
0x180009ebd  mov     [r14], rax
0x180009ec0  movzx   eax, word ptr [rax]
0x180009ec3  test    ax, ax
0x180009ec6  jnz     loc_180009D43
0x180009ecc  mov     rcx, [rsp+0A8h+pv]
0x180009ed1  mov     ebx, r12d
0x180009ed4  mov     [rsp+0A8h+pv], r12
0x180009ed9  mov     [r15], rcx
0x180009edc  mov     rcx, [rsp+0A8h+pv]; pv
0x180009ee1  call    cs:__imp_CoTaskMemFree
0x180009ee7  mov     eax, ebx
0x180009ee9  jmp     short loc_180009F05
0x180009eeb  mov     ebx, 80004005h
0x180009ef0  jmp     short loc_180009EDC
0x180009ef2  mov     ebx, 80020009h
0x180009ef7  jmp     short loc_180009EDC
0x180009ef9  mov     ebx, 8007000Eh
0x180009efe  jmp     short loc_180009EDC
0x180009f00  mov     eax, 80004003h
0x180009f05  mov     rcx, [rsp+0A8h+var_38]
0x180009f0a  xor     rcx, rsp; StackCookie
0x180009f0d  call    __security_check_cookie
0x180009f12  lea     r11, [rsp+0A8h+var_28]
0x180009f1a  mov     rbx, [r11+38h]
0x180009f1e  mov     rbp, [r11+48h]
0x180009f22  mov     rsp, r11
0x180009f25  pop     r15
0x180009f27  pop     r14
0x180009f29  pop     r12
0x180009f2b  pop     rdi
0x180009f2c  pop     rsi
0x180009f2d  retn
0x180009f2e  mov     ecx, 0C000008Ch; this
0x180009f33  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180009f38  int     3; Trap to Debugger
0x180009f39  mov     ecx, 80004005h; int
0x180009f3e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009f44  mov     ecx, 80070057h; int
0x180009f49  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009f4f  mov     ecx, 8007000Eh; int
0x180009f54  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
