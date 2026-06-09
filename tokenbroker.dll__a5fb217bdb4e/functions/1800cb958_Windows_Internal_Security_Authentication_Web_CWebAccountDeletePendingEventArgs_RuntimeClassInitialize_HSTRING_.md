# Windows::Internal::Security::Authentication::Web::CWebAccountDeletePendingEventArgs::RuntimeClassInitialize(HSTRING__ *,HSTRING__ *,HSTRING__ *)

- ea: `0x1800cb958`
- end: `0x1800cbad1`
- name: `?RuntimeClassInitialize@CWebAccountDeletePendingEventArgs@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@00@Z`
- size: `377`
- prototype: `int(Windows::Internal::Security::Authentication::Web::CWebAccountDeletePendingEventArgs *__hidden this, HSTRING, HSTRING, HSTRING)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800c88e4`

## callees

- `0x18000bd40`
- `0x18003fa60`
- `0x180040cc0`
- `0x1800cb958`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb9b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb9ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cba5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cba6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cba80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cbaaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cbabe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb9b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb9ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cba5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cba6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cba80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cbaaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cbabe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800cba20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800cba91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800cba20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800cba91`

## string_xrefs

- `0x1800cb999`: `onecore\ds\security\tokenbroker\broker\lib\events.cpp`
- `0x1800cb9e2`: `onecore\ds\security\tokenbroker\broker\lib\events.cpp`
- `0x1800cba41`: `onecore\ds\security\tokenbroker\broker\lib\events.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CWebAccountDeletePendingEventArgs::RuntimeClassInitialize(
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
        (void *)0x2DC,
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
          (void *)0x2E0,
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
    (void *)0x2DA,
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
0x1800cb958  mov     [rsp-28h+arg_18], r9
0x1800cb95d  mov     [rsp-28h+arg_10], r8
0x1800cb962  mov     [rsp-28h+arg_8], rdx
0x1800cb967  push    rbp
0x1800cb968  push    rbx
0x1800cb969  push    rsi
0x1800cb96a  push    rdi
0x1800cb96b  push    r14
0x1800cb96d  mov     rbp, rsp
0x1800cb970  sub     rsp, 40h
0x1800cb974  mov     rsi, rcx
0x1800cb977  mov     [rbp+string], 0
0x1800cb97f  lea     rcx, [rbp+string]; this
0x1800cb983  mov     r14, r9
0x1800cb986  lea     rdx, [rbp+arg_8]; HSTRING *
0x1800cb98a  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x1800cb98f  mov     ebx, eax
0x1800cb991  test    eax, eax
0x1800cb993  jns     short loc_1800CB9C3
0x1800cb995  mov     rcx, [rbp+28h]; this
0x1800cb999  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800cb9a0  mov     r9d, eax; char *
0x1800cb9a3  mov     edx, 2DAh; void *
0x1800cb9a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb9ad  mov     rcx, [rbp+string]; string
0x1800cb9b1  test    rcx, rcx
0x1800cb9b4  jz      short loc_1800CB9BC
0x1800cb9b6  call    cs:__imp_WindowsDeleteString
0x1800cb9bc  mov     eax, ebx
0x1800cb9be  jmp     loc_1800CBAC6
0x1800cb9c3  lea     rdx, [rbp+arg_10]; HSTRING *
0x1800cb9c7  mov     [rbp+var_18], 0
0x1800cb9cf  lea     rcx, [rbp+var_18]; this
0x1800cb9d3  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x1800cb9d8  mov     edi, eax
0x1800cb9da  test    eax, eax
0x1800cb9dc  jns     short loc_1800CBA17
0x1800cb9de  mov     rcx, [rbp+28h]; this
0x1800cb9e2  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800cb9e9  mov     r9d, eax; char *
0x1800cb9ec  mov     edx, 2DCh; void *
0x1800cb9f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb9f6  mov     rcx, [rbp+var_18]; string
0x1800cb9fa  test    rcx, rcx
0x1800cb9fd  jz      short loc_1800CBA05
0x1800cb9ff  call    cs:__imp_WindowsDeleteString
0x1800cba05  mov     rcx, [rbp+string]
0x1800cba09  test    rcx, rcx
0x1800cba0c  jz      loc_1800CBAC4
0x1800cba12  jmp     loc_1800CBABE
0x1800cba17  xor     ebx, ebx
0x1800cba19  mov     rcx, r14; string
0x1800cba1c  mov     [rbp+var_10], rbx
0x1800cba20  call    cs:__imp_WindowsIsStringEmpty
0x1800cba26  test    eax, eax
0x1800cba28  jnz     short loc_1800CBA6A
0x1800cba2a  lea     rdx, [rbp+arg_18]; HSTRING *
0x1800cba2e  lea     rcx, [rbp+var_10]; this
0x1800cba32  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x1800cba37  mov     edi, eax
0x1800cba39  test    eax, eax
0x1800cba3b  jns     short loc_1800CBA66
0x1800cba3d  mov     rcx, [rbp+28h]; this
0x1800cba41  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800cba48  mov     r9d, eax; char *
0x1800cba4b  mov     edx, 2E0h; void *
0x1800cba50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cba55  mov     rcx, [rbp+var_10]; string
0x1800cba59  test    rcx, rcx
0x1800cba5c  jz      short loc_1800CB9F6
0x1800cba5e  call    cs:__imp_WindowsDeleteString
0x1800cba64  jmp     short loc_1800CB9F6
0x1800cba66  mov     rbx, [rbp+var_10]
0x1800cba6a  mov     rcx, [rsi+40h]; string
0x1800cba6e  call    cs:__imp_WindowsDeleteString
0x1800cba74  mov     rax, [rbp+string]
0x1800cba78  mov     [rsi+40h], rax
0x1800cba7c  mov     rcx, [rsi+48h]; string
0x1800cba80  call    cs:__imp_WindowsDeleteString
0x1800cba86  mov     rax, [rbp+var_18]
0x1800cba8a  mov     rcx, rbx; string
0x1800cba8d  mov     [rsi+48h], rax
0x1800cba91  call    cs:__imp_WindowsIsStringEmpty
0x1800cba97  test    eax, eax
0x1800cba99  jz      short loc_1800CBAA6
0x1800cba9b  lea     rcx, [rsi+50h]; this
0x1800cba9f  call    ?Release@String@Internal@Windows@@QEAAXXZ; Windows::Internal::String::Release(void)
0x1800cbaa4  jmp     short loc_1800CBAB6
0x1800cbaa6  mov     rcx, [rsi+50h]; string
0x1800cbaaa  call    cs:__imp_WindowsDeleteString
0x1800cbab0  mov     [rsi+50h], rbx
0x1800cbab4  xor     ebx, ebx
0x1800cbab6  test    rbx, rbx
0x1800cbab9  jz      short loc_1800CBAC4
0x1800cbabb  mov     rcx, rbx; string
0x1800cbabe  call    cs:__imp_WindowsDeleteString
0x1800cbac4  mov     eax, edi
0x1800cbac6  add     rsp, 40h
0x1800cbaca  pop     r14
0x1800cbacc  pop     rdi
0x1800cbacd  pop     rsi
0x1800cbace  pop     rbx
0x1800cbacf  pop     rbp
0x1800cbad0  retn
```
