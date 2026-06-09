# Windows::Internal::Security::Authentication::Web::CWebAccountDeletedEventArgs::RuntimeClassInitialize(HSTRING__ *,HSTRING__ *,HSTRING__ *)

- ea: `0x1800cbad8`
- end: `0x1800cbc51`
- name: `?RuntimeClassInitialize@CWebAccountDeletedEventArgs@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@00@Z`
- size: `377`
- prototype: `int(Windows::Internal::Security::Authentication::Web::CWebAccountDeletedEventArgs *__hidden this, HSTRING, HSTRING, HSTRING)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004eefc`

## callees

- `0x18000bd40`
- `0x18003fa60`
- `0x180040cc0`
- `0x1800cbad8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cbb36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cbb7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cbbde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cbbee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cbc00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cbc2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cbc3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cbb36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cbb7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cbbde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cbbee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cbc00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cbc2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cbc3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800cbba0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800cbc11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800cbba0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800cbc11`

## string_xrefs

- `0x1800cbb19`: `onecore\ds\security\tokenbroker\broker\lib\events.cpp`
- `0x1800cbb62`: `onecore\ds\security\tokenbroker\broker\lib\events.cpp`
- `0x1800cbbc1`: `onecore\ds\security\tokenbroker\broker\lib\events.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CWebAccountDeletedEventArgs::RuntimeClassInitialize(
        HSTRING *this,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v9; // eax
  unsigned int v10; // edi
  HSTRING v11; // rcx
  HSTRING v12; // rbx
  int v13; // eax
  HSTRING string; // [rsp+20h] [rbp-20h] BYREF
  HSTRING v15; // [rsp+28h] [rbp-18h] BYREF
  HSTRING v16[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  HSTRING v18; // [rsp+78h] [rbp+38h] BYREF
  HSTRING v19; // [rsp+80h] [rbp+40h] BYREF
  HSTRING v20; // [rsp+88h] [rbp+48h] BYREF

  v20 = a4;
  v19 = a3;
  v18 = a2;
  string = 0;
  v6 = Windows::Internal::String::Initialize((Windows::Internal::String *)&string, &v18);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v15 = 0;
    v9 = Windows::Internal::String::Initialize((Windows::Internal::String *)&v15, &v19);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x290,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\events.cpp",
        (const char *)(unsigned int)v9,
        (int)string);
      goto LABEL_7;
    }
    v12 = 0;
    v16[0] = 0;
    if ( !WindowsIsStringEmpty(a4) )
    {
      v13 = Windows::Internal::String::Initialize((Windows::Internal::String *)v16, &v20);
      v10 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x294,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\events.cpp",
          (const char *)(unsigned int)v13,
          (int)string);
        if ( v16[0] )
          WindowsDeleteString(v16[0]);
LABEL_7:
        if ( v15 )
          WindowsDeleteString(v15);
        v11 = string;
        if ( !string )
          return v10;
        goto LABEL_21;
      }
      v12 = v16[0];
    }
    WindowsDeleteString(this[8]);
    this[8] = string;
    WindowsDeleteString(this[9]);
    this[9] = v15;
    if ( WindowsIsStringEmpty(v12) )
    {
      Windows::Internal::String::Release((Windows::Internal::String *)(this + 10));
    }
    else
    {
      WindowsDeleteString(this[10]);
      this[10] = v12;
      v12 = 0;
    }
    if ( !v12 )
      return v10;
    v11 = v12;
LABEL_21:
    WindowsDeleteString(v11);
    return v10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x28E,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\events.cpp",
    (const char *)(unsigned int)v6,
    (int)string);
  if ( string )
    WindowsDeleteString(string);
  return v7;
}

```

## disassembly

```asm
0x1800cbad8  mov     [rsp-28h+arg_18], r9
0x1800cbadd  mov     [rsp-28h+arg_10], r8
0x1800cbae2  mov     [rsp-28h+arg_8], rdx
0x1800cbae7  push    rbp
0x1800cbae8  push    rbx
0x1800cbae9  push    rsi
0x1800cbaea  push    rdi
0x1800cbaeb  push    r14
0x1800cbaed  mov     rbp, rsp
0x1800cbaf0  sub     rsp, 40h
0x1800cbaf4  mov     rsi, rcx
0x1800cbaf7  mov     [rbp+string], 0
0x1800cbaff  lea     rcx, [rbp+string]; this
0x1800cbb03  mov     r14, r9
0x1800cbb06  lea     rdx, [rbp+arg_8]; HSTRING *
0x1800cbb0a  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x1800cbb0f  mov     ebx, eax
0x1800cbb11  test    eax, eax
0x1800cbb13  jns     short loc_1800CBB43
0x1800cbb15  mov     rcx, [rbp+28h]; this
0x1800cbb19  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800cbb20  mov     r9d, eax; char *
0x1800cbb23  mov     edx, 28Eh; void *
0x1800cbb28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cbb2d  mov     rcx, [rbp+string]; string
0x1800cbb31  test    rcx, rcx
0x1800cbb34  jz      short loc_1800CBB3C
0x1800cbb36  call    cs:__imp_WindowsDeleteString
0x1800cbb3c  mov     eax, ebx
0x1800cbb3e  jmp     loc_1800CBC46
0x1800cbb43  lea     rdx, [rbp+arg_10]; HSTRING *
0x1800cbb47  mov     [rbp+var_18], 0
0x1800cbb4f  lea     rcx, [rbp+var_18]; this
0x1800cbb53  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x1800cbb58  mov     edi, eax
0x1800cbb5a  test    eax, eax
0x1800cbb5c  jns     short loc_1800CBB97
0x1800cbb5e  mov     rcx, [rbp+28h]; this
0x1800cbb62  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800cbb69  mov     r9d, eax; char *
0x1800cbb6c  mov     edx, 290h; void *
0x1800cbb71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cbb76  mov     rcx, [rbp+var_18]; string
0x1800cbb7a  test    rcx, rcx
0x1800cbb7d  jz      short loc_1800CBB85
0x1800cbb7f  call    cs:__imp_WindowsDeleteString
0x1800cbb85  mov     rcx, [rbp+string]
0x1800cbb89  test    rcx, rcx
0x1800cbb8c  jz      loc_1800CBC44
0x1800cbb92  jmp     loc_1800CBC3E
0x1800cbb97  xor     ebx, ebx
0x1800cbb99  mov     rcx, r14; string
0x1800cbb9c  mov     [rbp+var_10], rbx
0x1800cbba0  call    cs:__imp_WindowsIsStringEmpty
0x1800cbba6  test    eax, eax
0x1800cbba8  jnz     short loc_1800CBBEA
0x1800cbbaa  lea     rdx, [rbp+arg_18]; HSTRING *
0x1800cbbae  lea     rcx, [rbp+var_10]; this
0x1800cbbb2  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x1800cbbb7  mov     edi, eax
0x1800cbbb9  test    eax, eax
0x1800cbbbb  jns     short loc_1800CBBE6
0x1800cbbbd  mov     rcx, [rbp+28h]; this
0x1800cbbc1  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800cbbc8  mov     r9d, eax; char *
0x1800cbbcb  mov     edx, 294h; void *
0x1800cbbd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cbbd5  mov     rcx, [rbp+var_10]; string
0x1800cbbd9  test    rcx, rcx
0x1800cbbdc  jz      short loc_1800CBB76
0x1800cbbde  call    cs:__imp_WindowsDeleteString
0x1800cbbe4  jmp     short loc_1800CBB76
0x1800cbbe6  mov     rbx, [rbp+var_10]
0x1800cbbea  mov     rcx, [rsi+40h]; string
0x1800cbbee  call    cs:__imp_WindowsDeleteString
0x1800cbbf4  mov     rax, [rbp+string]
0x1800cbbf8  mov     [rsi+40h], rax
0x1800cbbfc  mov     rcx, [rsi+48h]; string
0x1800cbc00  call    cs:__imp_WindowsDeleteString
0x1800cbc06  mov     rax, [rbp+var_18]
0x1800cbc0a  mov     rcx, rbx; string
0x1800cbc0d  mov     [rsi+48h], rax
0x1800cbc11  call    cs:__imp_WindowsIsStringEmpty
0x1800cbc17  test    eax, eax
0x1800cbc19  jz      short loc_1800CBC26
0x1800cbc1b  lea     rcx, [rsi+50h]; this
0x1800cbc1f  call    ?Release@String@Internal@Windows@@QEAAXXZ; Windows::Internal::String::Release(void)
0x1800cbc24  jmp     short loc_1800CBC36
0x1800cbc26  mov     rcx, [rsi+50h]; string
0x1800cbc2a  call    cs:__imp_WindowsDeleteString
0x1800cbc30  mov     [rsi+50h], rbx
0x1800cbc34  xor     ebx, ebx
0x1800cbc36  test    rbx, rbx
0x1800cbc39  jz      short loc_1800CBC44
0x1800cbc3b  mov     rcx, rbx; string
0x1800cbc3e  call    cs:__imp_WindowsDeleteString
0x1800cbc44  mov     eax, edi
0x1800cbc46  add     rsp, 40h
0x1800cbc4a  pop     r14
0x1800cbc4c  pop     rdi
0x1800cbc4d  pop     rsi
0x1800cbc4e  pop     rbx
0x1800cbc4f  pop     rbp
0x1800cbc50  retn
```
