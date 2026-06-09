# Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::NormalizePFN(HSTRING__ * const,HSTRING__ * *)

- ea: `0x180009be0`
- end: `0x180009e35`
- name: `?NormalizePFN@ApplicationCallbackUri@Web@Authentication@Security@Internal@Windows@@SAJQEAUHSTRING__@@PEAPEAU7@@Z`
- size: `597`
- prototype: `__int64 __fastcall(HSTRING, HSTRING *)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180071b10`
- `0x180111d50`

## callees

- `0x18000730c`
- `0x180009be0`
- `0x180009e80`
- `0x18000bd40`
- `0x18007ad10`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180009c9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180009c17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180009c17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009c3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009c3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009c31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009d46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009d94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009df2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009e01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009c31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009d46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009d94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009df2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009e01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180009d82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180009d82`

## string_xrefs

- `0x180009dce`: `onecore\ds\security\tokenbroker\inc\appcallbackuri.h`
- `0x180009e1c`: `onecore\ds\security\tokenbroker\inc\appcallbackuri.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::NormalizePFN(
        HSTRING a1,
        HSTRING *a2)
{
  HSTRING v2; // rdi
  HRESULT v3; // eax
  unsigned int v4; // ebx
  HSTRING v5; // rbx
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v7; // r13
  __int64 v8; // r8
  __int64 v9; // rdx
  PCNZWCH v10; // r8
  PCNZWCH *v11; // r14
  const WCHAR *v12; // r15
  PCNZWCH *v13; // rsi
  PCNZWCH *v14; // rcx
  HRESULT v15; // esi
  HSTRING newString; // [rsp+20h] [rbp-50h] BYREF
  HSTRING *v18; // [rsp+28h] [rbp-48h]
  __int64 v19; // [rsp+30h] [rbp-40h]
  HSTRING v20; // [rsp+38h] [rbp-38h]
  PCNZWCH sourceString[2]; // [rsp+40h] [rbp-30h] BYREF
  __m128i si128; // [rsp+50h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v18 = a2;
  v2 = 0;
  v19 = 0;
  newString = 0;
  v3 = WindowsDuplicateString(a1, &newString);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = newString;
    v20 = newString;
    WindowsDeleteString(0);
    StringRawBuffer = WindowsGetStringRawBuffer(v5, 0);
    *(_OWORD *)sourceString = 0;
    si128 = 0;
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( StringRawBuffer[v8] );
    std::wstring::_Construct<1,unsigned short const *>(sourceString, StringRawBuffer);
    v10 = sourceString[0];
    if ( si128.m128i_i64[1] > 7uLL )
    {
      v11 = (PCNZWCH *)sourceString[0];
      v12 = &sourceString[0][si128.m128i_i64[0]];
      v13 = (PCNZWCH *)sourceString[0];
    }
    else
    {
      v11 = sourceString;
      v12 = (const WCHAR *)sourceString + si128.m128i_i64[0];
      v13 = sourceString;
    }
    if ( v13 != (PCNZWCH *)v12 )
    {
      do
      {
        *(_WORD *)v11 = ((__int64 (__fastcall *)(_QWORD, __int64, PCNZWCH))_o_towlower)(
                          *(unsigned __int16 *)v13,
                          v9,
                          v10);
        v11 = (PCNZWCH *)((char *)v11 + 2);
        v13 = (PCNZWCH *)((char *)v13 + 2);
      }
      while ( v13 != (PCNZWCH *)v12 );
      v10 = sourceString[0];
    }
    if ( si128.m128i_i64[1] <= 7uLL )
    {
      v14 = sourceString;
    }
    else
    {
      v14 = (PCNZWCH *)v10;
      if ( !v10 )
      {
        v15 = -2147467261;
        goto LABEL_25;
      }
    }
    newString = 0;
    do
      ++v7;
    while ( *((_WORD *)v14 + v7) );
    if ( v7 <= 0xFFFFFFFF )
    {
      v15 = WindowsCreateString((PCNZWCH)v14, v7, &newString);
      if ( v15 >= 0 )
      {
        v2 = newString;
        WindowsDeleteString(0);
      }
      v10 = sourceString[0];
    }
    else
    {
      v15 = -2147024362;
    }
    if ( v15 >= 0 )
    {
      *v18 = v2;
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(v10, 2 * si128.m128i_i64[1] + 2);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(sourceString[0]) = 0;
      if ( v5 )
      {
        WindowsDeleteString(v5);
        return (unsigned int)v15;
      }
      return (unsigned int)v15;
    }
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11E,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\appcallbackuri.h",
      (const char *)(unsigned int)v15,
      (int)newString);
    std::wstring::_Tidy_deallocate(sourceString);
    if ( v2 )
      WindowsDeleteString(v2);
    if ( v5 )
      WindowsDeleteString(v5);
    return (unsigned int)v15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x11B,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\appcallbackuri.h",
    (const char *)(unsigned int)v3,
    (int)newString);
  return v4;
}

```

## disassembly

```asm
0x180009be0  mov     [rsp-38h+arg_10], rbx
0x180009be5  push    rbp
0x180009be6  push    rsi
0x180009be7  push    rdi
0x180009be8  push    r12
0x180009bea  push    r13
0x180009bec  push    r14
0x180009bee  push    r15
0x180009bf0  mov     rbp, rsp
0x180009bf3  sub     rsp, 70h
0x180009bf7  mov     rax, cs:__security_cookie
0x180009bfe  xor     rax, rsp
0x180009c01  mov     [rbp+var_10], rax
0x180009c05  mov     [rbp+var_48], rdx
0x180009c09  xor     edi, edi
0x180009c0b  mov     [rbp+var_40], rdi
0x180009c0f  mov     [rbp+newString], rdi
0x180009c13  lea     rdx, [rbp+newString]; newString
0x180009c17  call    cs:__imp_WindowsDuplicateString
0x180009c1d  mov     ebx, eax
0x180009c1f  test    eax, eax
0x180009c21  js      loc_180009E15
0x180009c27  mov     rbx, [rbp+newString]
0x180009c2b  mov     [rbp+var_38], rbx
0x180009c2f  xor     ecx, ecx; string
0x180009c31  call    cs:__imp_WindowsDeleteString
0x180009c37  xor     edx, edx; length
0x180009c39  mov     rcx, rbx; string
0x180009c3c  call    cs:__imp_WindowsGetStringRawBuffer
0x180009c42  xorps   xmm0, xmm0
0x180009c45  movups  xmmword ptr [rbp+sourceString], xmm0
0x180009c49  xorps   xmm1, xmm1
0x180009c4c  movdqu  [rbp+var_20], xmm1
0x180009c51  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180009c58  mov     r8, r13
0x180009c5b  nop     dword ptr [rax+rax+00h]
0x180009c60  inc     r8
0x180009c63  cmp     word ptr [rax+r8*2], 0
0x180009c69  jnz     short loc_180009C60
0x180009c6b  mov     rdx, rax
0x180009c6e  lea     rcx, [rbp+sourceString]
0x180009c72  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180009c77  nop
0x180009c78  mov     r8, [rbp+sourceString]
0x180009c7c  mov     rax, qword ptr [rbp+var_20]
0x180009c80  cmp     qword ptr [rbp+var_20+8], 7
0x180009c85  ja      loc_180009DA3
0x180009c8b  lea     r14, [rbp+sourceString]
0x180009c8f  lea     rcx, [rbp+sourceString]
0x180009c93  lea     r15, [rcx+rax*2]
0x180009c97  lea     rsi, [rbp+sourceString]
0x180009c9b  mov     r12, cs:__imp__o_towlower
0x180009ca2  cmp     rsi, r15
0x180009ca5  jz      short loc_180009CD0
0x180009ca7  nop     word ptr [rax+rax+00000000h]
0x180009cb0  movzx   ecx, word ptr [rsi]
0x180009cb3  mov     rax, r12
0x180009cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cbb  mov     [r14], ax
0x180009cbf  lea     r14, [r14+2]
0x180009cc3  add     rsi, 2
0x180009cc7  cmp     rsi, r15
0x180009cca  jnz     short loc_180009CB0
0x180009ccc  mov     r8, [rbp+sourceString]
0x180009cd0  cmp     qword ptr [rbp+var_20+8], 7
0x180009cd5  jbe     loc_180009D72
0x180009cdb  mov     rcx, r8; sourceString
0x180009cde  test    r8, r8
0x180009ce1  jz      loc_180009E0E
0x180009ce7  mov     [rbp+newString], 0
0x180009cef  nop
0x180009cf0  inc     r13
0x180009cf3  cmp     word ptr [rcx+r13*2], 0
0x180009cf9  jnz     short loc_180009CF0
0x180009cfb  mov     eax, 0FFFFFFFFh
0x180009d00  cmp     r13, rax
0x180009d03  jbe     short loc_180009D7B
0x180009d05  mov     esi, 80070216h
0x180009d0a  test    esi, esi
0x180009d0c  js      loc_180009DC7
0x180009d12  mov     rax, [rbp+var_48]
0x180009d16  mov     [rax], rdi
0x180009d19  mov     rdx, qword ptr [rbp+var_20+8]
0x180009d1d  cmp     rdx, 7
0x180009d21  ja      loc_180009DB2
0x180009d27  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180009d2f  movdqu  [rbp+var_20], xmm0
0x180009d34  xor     eax, eax
0x180009d36  mov     word ptr [rbp+sourceString], ax
0x180009d3a  test    rbx, rbx
0x180009d3d  jz      loc_180009E07
0x180009d43  mov     rcx, rbx; string
0x180009d46  call    cs:__imp_WindowsDeleteString
0x180009d4c  mov     eax, esi
0x180009d4e  mov     rcx, [rbp+var_10]
0x180009d52  xor     rcx, rsp; StackCookie
0x180009d55  call    __security_check_cookie
0x180009d5a  mov     rbx, [rsp+70h+arg_10]
0x180009d62  add     rsp, 70h
0x180009d66  pop     r15
0x180009d68  pop     r14
0x180009d6a  pop     r13
0x180009d6c  pop     r12
0x180009d6e  pop     rdi
0x180009d6f  pop     rsi
0x180009d70  pop     rbp
0x180009d71  retn
0x180009d72  lea     rcx, [rbp+sourceString]
0x180009d76  jmp     loc_180009CE7
0x180009d7b  mov     edx, r13d; length
0x180009d7e  lea     r8, [rbp+newString]; string
0x180009d82  call    cs:__imp_WindowsCreateString
0x180009d88  mov     esi, eax
0x180009d8a  test    eax, eax
0x180009d8c  js      short loc_180009D9A
0x180009d8e  mov     rdi, [rbp+newString]
0x180009d92  xor     ecx, ecx; string
0x180009d94  call    cs:__imp_WindowsDeleteString
0x180009d9a  mov     r8, [rbp+sourceString]
0x180009d9e  jmp     loc_180009D0A
0x180009da3  mov     r14, r8
0x180009da6  lea     r15, [r8+rax*2]
0x180009daa  mov     rsi, r8
0x180009dad  jmp     loc_180009C9B
0x180009db2  lea     rdx, ds:2[rdx*2]
0x180009dba  mov     rcx, r8
0x180009dbd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180009dc2  jmp     loc_180009D27
0x180009dc7  mov     rcx, [rbp+38h]; this
0x180009dcb  mov     r9d, esi; char *
0x180009dce  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\tokenbroker\\inc"...
0x180009dd5  mov     edx, 11Eh; void *
0x180009dda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ddf  nop
0x180009de0  lea     rcx, [rbp+sourceString]
0x180009de4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009de9  nop
0x180009dea  test    rdi, rdi
0x180009ded  jz      short loc_180009DF9
0x180009def  mov     rcx, rdi; string
0x180009df2  call    cs:__imp_WindowsDeleteString
0x180009df8  nop
0x180009df9  test    rbx, rbx
0x180009dfc  jz      short loc_180009E07
0x180009dfe  mov     rcx, rbx; string
0x180009e01  call    cs:__imp_WindowsDeleteString
0x180009e07  mov     eax, esi
0x180009e09  jmp     loc_180009D4E
0x180009e0e  mov     esi, 80004003h
0x180009e13  jmp     short loc_180009DC7
0x180009e15  mov     rcx, [rbp+38h]; this
0x180009e19  mov     r9d, ebx; char *
0x180009e1c  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\tokenbroker\\inc"...
0x180009e23  mov     edx, 11Bh; void *
0x180009e28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009e2d  nop
0x180009e2e  mov     eax, ebx
0x180009e30  jmp     loc_180009D4E
```
