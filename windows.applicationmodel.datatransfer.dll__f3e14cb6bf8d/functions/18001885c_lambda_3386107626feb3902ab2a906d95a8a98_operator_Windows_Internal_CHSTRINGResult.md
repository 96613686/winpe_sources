# _lambda_3386107626feb3902ab2a906d95a8a98_::operator()(Windows::Internal::CHSTRINGResult &)

- ea: `0x18001885c`
- end: `0x180018a4a`
- name: `??R_lambda_3386107626feb3902ab2a906d95a8a98_@@QEBAJAEAVCHSTRINGResult@Internal@Windows@@@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180049190`

## callees

- `0x180002ad0`
- `0x18001885c`
- `0x180048954`
- `0x18004eb30`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180018971`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180018971`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018925`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018962`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800189c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800189dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018a1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018925`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018962`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800189c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800189dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018a1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001893c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800189f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001893c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800189f6`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetClipboardAccessDeniedData` at `0x1800188a6`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetClipboardAccessDeniedData` at `0x1800188a6`

## string_xrefs

- `0x1800188c7`: `{\rtf1\ansi\ansicpg1252\deff0\nouicompat\deflang1033{\fonttbl{\f0\fnil\fcharset0 Calibri;}} \uc1 \pard\sa200\sl276\slmult1\f0\fs22\lang9 %s}`

## pseudocode

```c
__int64 __fastcall _lambda_3386107626feb3902ab2a906d95a8a98_::operator()(_DWORD *a1, __int64 a2)
{
  HRESULT ClipboardAccessDeniedData; // eax
  HRESULT v5; // ebx
  __int64 v6; // rdx
  unsigned __int64 v7; // r9
  unsigned __int64 v8; // rbx
  HSTRING v9; // rdi
  HSTRING *v10; // rbx
  const WCHAR *v11; // rdi
  unsigned __int64 v12; // rbx
  UINT32 v13; // edx
  const WCHAR *v14; // rcx
  HSTRING string; // [rsp+20h] [rbp-E0h] BYREF
  const WCHAR *v17; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR sourceString[1024]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+858h] [rbp+758h]

  string = 0;
  v17 = 0;
  ClipboardAccessDeniedData = EdpGetClipboardAccessDeniedData(13, &v17);
  v5 = ClipboardAccessDeniedData;
  if ( ClipboardAccessDeniedData >= 0 )
  {
    if ( *a1 )
    {
      ClipboardAccessDeniedData = StringCchPrintfW(
                                    sourceString,
                                    0x400u,
                                    L"{\\rtf1\\ansi\\ansicpg1252\\deff0\\nouicompat\\deflang1033{\\fonttbl{\\f0\\fnil\\fch"
                                     "arset0 Calibri;}} \\uc1 \\pard\\sa200\\sl276\\slmult1\\f0\\fs22\\lang9 %s}",
                                    v17);
      v5 = ClipboardAccessDeniedData;
      if ( ClipboardAccessDeniedData < 0 )
      {
        v6 = 5174;
        goto LABEL_6;
      }
      v8 = -1;
      do
        ++v8;
      while ( sourceString[v8] );
      if ( v8 > 0xFFFFFFFF )
      {
        v5 = -2147024362;
      }
      else
      {
        WindowsDeleteString(string);
        string = 0;
        v5 = WindowsCreateString(sourceString, v8, &string);
        if ( v5 >= 0 )
        {
LABEL_12:
          v9 = string;
          v10 = (HSTRING *)(a2 + 16);
          if ( string && string == *v10
            || (WindowsDeleteString(*v10),
                *v10 = 0,
                ClipboardAccessDeniedData = WindowsDuplicateString(v9, (HSTRING *)(a2 + 16)),
                v5 = ClipboardAccessDeniedData,
                ClipboardAccessDeniedData >= 0) )
          {
            v5 = 0;
            goto LABEL_29;
          }
          v6 = 5182;
          goto LABEL_6;
        }
      }
      v7 = (unsigned int)v5;
      v6 = 5175;
      goto LABEL_7;
    }
    v11 = v17;
    if ( v17 )
    {
      v12 = -1;
      do
        ++v12;
      while ( v17[v12] );
      if ( v12 > 0xFFFFFFFF )
      {
        v5 = -2147024362;
        goto LABEL_26;
      }
      WindowsDeleteString(string);
      v13 = v12;
      v14 = v11;
    }
    else
    {
      WindowsDeleteString(string);
      v13 = 0;
      v14 = &::sourceString;
    }
    string = 0;
    v5 = WindowsCreateString(v14, v13, &string);
LABEL_26:
    if ( v5 < 0 )
    {
      v7 = (unsigned int)v5;
      v6 = 5180;
      goto LABEL_7;
    }
    goto LABEL_12;
  }
  v6 = 5169;
LABEL_6:
  v7 = (unsigned int)ClipboardAccessDeniedData;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
    (const char *)v7,
    (int)string);
LABEL_29:
  WindowsDeleteString(string);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001885c  mov     [rsp-8+arg_0], rbx
0x180018861  mov     [rsp-8+arg_10], rsi
0x180018866  push    rbp
0x180018867  push    rdi
0x180018868  push    r14
0x18001886a  lea     rbp, [rsp-740h]
0x180018872  sub     rsp, 840h
0x180018879  mov     rax, cs:__security_cookie
0x180018880  xor     rax, rsp
0x180018883  mov     [rbp+750h+var_20], rax
0x18001888a  xor     r14d, r14d
0x18001888d  mov     rsi, rdx
0x180018890  mov     rdi, rcx
0x180018893  mov     [rsp+850h+string], r14; int
0x180018898  lea     rdx, [rsp+850h+var_828]
0x18001889d  mov     [rsp+850h+var_828], r14
0x1800188a2  lea     ecx, [r14+0Dh]
0x1800188a6  call    cs:__imp_EdpGetClipboardAccessDeniedData
0x1800188ac  mov     ebx, eax
0x1800188ae  test    eax, eax
0x1800188b0  jns     short loc_1800188B9
0x1800188b2  mov     edx, 1431h
0x1800188b7  jmp     short loc_1800188E8
0x1800188b9  cmp     [rdi], r14d
0x1800188bc  jz      loc_18001899D
0x1800188c2  mov     r9, [rsp+850h+var_828]
0x1800188c7  lea     r8, aRtf1AnsiAnsicp; "{\\rtf1\\ansi\\ansicpg1252\\deff0\\noui"...
0x1800188ce  mov     edx, 400h; unsigned __int64
0x1800188d3  lea     rcx, [rsp+850h+sourceString]; unsigned __int16 *
0x1800188d8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800188dd  mov     ebx, eax
0x1800188df  test    eax, eax
0x1800188e1  jns     short loc_180018903
0x1800188e3  mov     edx, 1436h; void *
0x1800188e8  mov     r9d, eax; char *
0x1800188eb  mov     rcx, [rbp+758h]; this
0x1800188f2  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x1800188f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800188fe  jmp     loc_180018A16
0x180018903  lea     rax, [rsp+850h+sourceString]
0x180018908  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001890c  inc     rbx
0x18001890f  cmp     [rax+rbx*2], r14w
0x180018914  jnz     short loc_18001890C
0x180018916  mov     eax, 0FFFFFFFFh
0x18001891b  cmp     rbx, rax
0x18001891e  ja      short loc_18001898B
0x180018920  mov     rcx, [rsp+850h+string]; string
0x180018925  call    cs:__imp_WindowsDeleteString
0x18001892b  mov     edx, ebx; length
0x18001892d  mov     [rsp+850h+string], r14
0x180018932  lea     r8, [rsp+850h+string]; string
0x180018937  lea     rcx, [rsp+850h+sourceString]; sourceString
0x18001893c  call    cs:__imp_WindowsCreateString
0x180018942  mov     ebx, eax
0x180018944  test    eax, eax
0x180018946  js      short loc_180018990
0x180018948  mov     rdi, [rsp+850h+string]
0x18001894d  lea     rbx, [rsi+10h]
0x180018951  test    rdi, rdi
0x180018954  jz      short loc_18001895F
0x180018956  cmp     rdi, [rbx]
0x180018959  jz      loc_180018A13
0x18001895f  mov     rcx, [rbx]; string
0x180018962  call    cs:__imp_WindowsDeleteString
0x180018968  mov     rdx, rbx; newString
0x18001896b  mov     [rbx], r14
0x18001896e  mov     rcx, rdi; string
0x180018971  call    cs:__imp_WindowsDuplicateString
0x180018977  mov     ebx, eax
0x180018979  test    eax, eax
0x18001897b  jns     loc_180018A13
0x180018981  mov     edx, 143Eh
0x180018986  jmp     loc_1800188E8
0x18001898b  mov     ebx, 80070216h
0x180018990  mov     r9d, ebx
0x180018993  mov     edx, 1437h
0x180018998  jmp     loc_1800188EB
0x18001899d  mov     rdi, [rsp+850h+var_828]
0x1800189a2  test    rdi, rdi
0x1800189a5  jz      short loc_1800189D8
0x1800189a7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800189ab  inc     rbx
0x1800189ae  cmp     [rdi+rbx*2], r14w
0x1800189b3  jnz     short loc_1800189AB
0x1800189b5  mov     eax, 0FFFFFFFFh
0x1800189ba  cmp     rbx, rax
0x1800189bd  ja      short loc_1800189D1
0x1800189bf  mov     rcx, [rsp+850h+string]; string
0x1800189c4  call    cs:__imp_WindowsDeleteString
0x1800189ca  mov     edx, ebx
0x1800189cc  mov     rcx, rdi
0x1800189cf  jmp     short loc_1800189EC
0x1800189d1  mov     ebx, 80070216h
0x1800189d6  jmp     short loc_1800189FE
0x1800189d8  mov     rcx, [rsp+850h+string]; string
0x1800189dd  call    cs:__imp_WindowsDeleteString
0x1800189e3  xor     edx, edx; length
0x1800189e5  lea     rcx, sourceString; sourceString
0x1800189ec  lea     r8, [rsp+850h+string]; string
0x1800189f1  mov     [rsp+850h+string], r14
0x1800189f6  call    cs:__imp_WindowsCreateString
0x1800189fc  mov     ebx, eax
0x1800189fe  test    ebx, ebx
0x180018a00  jns     loc_180018948
0x180018a06  mov     r9d, ebx
0x180018a09  mov     edx, 143Ch
0x180018a0e  jmp     loc_1800188EB
0x180018a13  mov     ebx, r14d
0x180018a16  mov     rcx, [rsp+850h+string]; string
0x180018a1b  call    cs:__imp_WindowsDeleteString
0x180018a21  mov     eax, ebx
0x180018a23  mov     rcx, [rbp+750h+var_20]
0x180018a2a  xor     rcx, rsp; StackCookie
0x180018a2d  call    __security_check_cookie
0x180018a32  lea     r11, [rsp+850h+var_10]
0x180018a3a  mov     rbx, [r11+20h]
0x180018a3e  mov     rsi, [r11+30h]
0x180018a42  mov     rsp, r11
0x180018a45  pop     r14
0x180018a47  pop     rdi
0x180018a48  pop     rbp
0x180018a49  retn
```
