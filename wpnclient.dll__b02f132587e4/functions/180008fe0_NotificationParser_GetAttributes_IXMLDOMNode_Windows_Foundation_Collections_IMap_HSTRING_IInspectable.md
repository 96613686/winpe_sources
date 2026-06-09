# NotificationParser::GetAttributes(IXMLDOMNode *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)

- ea: `0x180008fe0`
- end: `0x180009378`
- name: `?GetAttributes@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z`
- size: `920`
- prototype: ``
- caller_count: `14`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800020d0`
- `0x180002b70`
- `0x1800089a0`
- `0x180009380`
- `0x18000cb68`
- `0x180016334`
- `0x18001780c`
- `0x180018d90`
- `0x1800199dc`
- `0x180019b4c`
- `0x18001dc28`
- `0x18002d280`
- `0x18002d370`
- `0x18002d73c`

## callees

- `0x180008fe0`
- `0x18001b848`
- `0x18001ff00`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800091ab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800091ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800091be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800091be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180009127`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180009127`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000913d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009216`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000913d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009216`
- `OLEAUT32!__imp_SysFreeString` at `0x180009221`
- `OLEAUT32!__imp_SysFreeString` at `0x18000922c`
- `OLEAUT32!__imp_SysFreeString` at `0x180009221`
- `OLEAUT32!__imp_SysFreeString` at `0x18000922c`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall NotificationParser::GetAttributes(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 *v4; // rsi
  int v5; // eax
  int v6; // eax
  unsigned int v7; // r15d
  int v8; // eax
  int v9; // eax
  int v10; // eax
  HSTRING v11; // rbx
  unsigned __int64 v12; // rdx
  HRESULT v13; // edi
  __int64 v14; // r14
  __int64 (__fastcall *v15)(__int64, HSTRING, __int64 *); // r12
  __int64 v16; // rcx
  const WCHAR *v17; // rsi
  unsigned __int64 v18; // rdi
  int v19; // eax
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24; // [rsp+20h] [rbp-59h]
  _BYTE v25[4]; // [rsp+30h] [rbp-49h] BYREF
  int v26; // [rsp+34h] [rbp-45h] BYREF
  __int64 v27; // [rsp+38h] [rbp-41h] BYREF
  __int64 v28; // [rsp+40h] [rbp-39h] BYREF
  __int64 v29; // [rsp+48h] [rbp-31h] BYREF
  PCWSTR v30; // [rsp+50h] [rbp-29h] BYREF
  PCNZWCH sourceString; // [rsp+58h] [rbp-21h] BYREF
  HSTRING string; // [rsp+60h] [rbp-19h] BYREF
  HSTRING v33; // [rsp+68h] [rbp-11h]
  __int64 *v34; // [rsp+70h] [rbp-9h]
  HSTRING v35; // [rsp+78h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v4 = a1;
  v34 = a1;
  v29 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 136LL))(a2, &v29);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x69A,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v5,
      v24);
  v26 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 88LL))(v29, &v26);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x69E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v6,
      v24);
  v7 = 0;
  if ( v26 > 0 )
  {
    while ( 1 )
    {
      v28 = 0;
      v27 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v29 + 80LL))(v29, v7, &v28);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6A6,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v8,
          v24);
      sourceString = 0;
      v30 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v28 + 56LL))(v28, &sourceString);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6AB,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v9,
          v24);
      v10 = (*(__int64 (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v28 + 208LL))(v28, &v30);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6AD,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v10,
          v24);
      v11 = 0;
      v33 = 0;
      if ( sourceString )
      {
        string = 0;
        v12 = -1;
        do
          ++v12;
        while ( sourceString[v12] );
        if ( v12 > 0xFFFFFFFF )
        {
          v13 = -2147024362;
        }
        else
        {
          v13 = WindowsCreateString(sourceString, v12, &string);
          if ( v13 >= 0 )
          {
            v11 = string;
            v33 = string;
            WindowsDeleteString(0);
          }
        }
      }
      else
      {
        v13 = -2147467261;
      }
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6B2,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v13,
          v24);
      v14 = *v4;
      v15 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)*v4 + 144LL);
      v16 = v27;
      if ( v27 )
      {
        v27 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      v17 = v30;
      v18 = -1;
      do
        ++v18;
      while ( v30[v18] );
      if ( v18 > 0xFFFFFFFF )
      {
        LODWORD(v18) = -1;
        RaiseException(0xC000000D, 1u, 0, 0);
      }
      WindowsCreateStringReference(v17, v18, &hstringHeader, &v35);
      v19 = v15(v14, v35, &v27);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6B6,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v19,
          v24);
      v25[0] = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)a3 + 80LL))(a3, v11, v27, v25);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6BB,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v20,
          v24);
      if ( v11 )
        WindowsDeleteString(v11);
      SysFreeString((BSTR)v30);
      SysFreeString((BSTR)sourceString);
      v21 = v27;
      if ( v27 )
      {
        v27 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      v22 = v28;
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      if ( (int)++v7 >= v26 )
        break;
      v4 = v34;
    }
  }
  v23 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
}

```

## disassembly

```asm
0x180008fe0  mov     [rsp-8+arg_18], rbx
0x180008fe5  push    rbp
0x180008fe6  push    rsi
0x180008fe7  push    rdi
0x180008fe8  push    r12
0x180008fea  push    r13
0x180008fec  push    r14
0x180008fee  push    r15
0x180008ff0  lea     rbp, [rsp-27h]
0x180008ff5  sub     rsp, 0A0h
0x180008ffc  mov     rax, cs:__security_cookie
0x180009003  xor     rax, rsp
0x180009006  mov     [rbp+57h+var_38], rax
0x18000900a  mov     r13, r8
0x18000900d  mov     r9, rdx
0x180009010  mov     rsi, rcx
0x180009013  mov     [rbp+57h+var_60], rcx
0x180009017  xor     edi, edi
0x180009019  mov     [rbp+57h+var_88], rdi
0x18000901d  mov     rax, [rdx]
0x180009020  lea     rdx, [rbp+57h+var_88]
0x180009024  mov     rcx, r9
0x180009027  mov     rax, [rax+88h]
0x18000902e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009033  mov     rcx, [rbp+5Fh]; this
0x180009037  test    eax, eax
0x180009039  js      loc_1800092D0
0x18000903f  mov     [rbp+57h+var_9C], edi
0x180009042  mov     rcx, [rbp+57h+var_88]
0x180009046  mov     rax, [rcx]
0x180009049  lea     rdx, [rbp+57h+var_9C]
0x18000904d  mov     rax, [rax+58h]
0x180009051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009056  mov     rcx, [rbp+5Fh]; this
0x18000905a  test    eax, eax
0x18000905c  js      loc_1800092E5
0x180009062  mov     r15d, edi
0x180009065  cmp     [rbp+57h+var_9C], edi
0x180009068  jle     loc_18000927B
0x18000906e  mov     r14d, 0FFFFFFFFh
0x180009074  mov     [rbp+57h+var_90], rdi
0x180009078  mov     [rbp+57h+var_98], rdi
0x18000907c  mov     rcx, [rbp+57h+var_88]
0x180009080  mov     rax, [rcx]
0x180009083  lea     r8, [rbp+57h+var_90]
0x180009087  mov     edx, r15d
0x18000908a  mov     rax, [rax+50h]
0x18000908e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009093  mov     rcx, [rbp+5Fh]; this
0x180009097  test    eax, eax
0x180009099  js      loc_180009363
0x18000909f  mov     [rbp+57h+sourceString], rdi
0x1800090a3  mov     [rbp+57h+var_80], rdi
0x1800090a7  mov     rcx, [rbp+57h+var_90]
0x1800090ab  mov     rax, [rcx]
0x1800090ae  lea     rdx, [rbp+57h+sourceString]
0x1800090b2  mov     rax, [rax+38h]
0x1800090b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090bb  mov     rcx, [rbp+5Fh]; this
0x1800090bf  test    eax, eax
0x1800090c1  js      loc_18000934E
0x1800090c7  mov     rcx, [rbp+57h+var_90]
0x1800090cb  mov     rax, [rcx]
0x1800090ce  lea     rdx, [rbp+57h+var_80]
0x1800090d2  mov     rax, [rax+0D0h]
0x1800090d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090de  mov     rcx, [rbp+5Fh]; this
0x1800090e2  test    eax, eax
0x1800090e4  js      loc_180009339
0x1800090ea  mov     rbx, rdi
0x1800090ed  mov     [rbp+57h+var_68], rbx
0x1800090f1  mov     rcx, [rbp+57h+sourceString]; sourceString
0x1800090f5  test    rcx, rcx
0x1800090f8  jz      loc_1800092C6
0x1800090fe  mov     [rbp+57h+string], rdi
0x180009102  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180009109  nop     dword ptr [rax+00000000h]
0x180009110  inc     rdx; length
0x180009113  cmp     word ptr [rcx+rdx*2], 0
0x180009118  jnz     short loc_180009110
0x18000911a  cmp     rdx, r14
0x18000911d  ja      loc_1800092BC
0x180009123  lea     r8, [rbp+57h+string]; string
0x180009127  call    cs:__imp_WindowsCreateString
0x18000912d  mov     edi, eax
0x18000912f  test    eax, eax
0x180009131  js      short loc_180009143
0x180009133  mov     rbx, [rbp+57h+string]
0x180009137  mov     [rbp+57h+var_68], rbx
0x18000913b  xor     ecx, ecx; string
0x18000913d  call    cs:__imp_WindowsDeleteString
0x180009143  mov     rcx, [rbp+5Fh]; this
0x180009147  test    edi, edi
0x180009149  js      loc_180009324
0x18000914f  mov     r14, [rsi]
0x180009152  mov     rax, [r14]
0x180009155  mov     r12, [rax+90h]
0x18000915c  mov     rcx, [rbp+57h+var_98]
0x180009160  test    rcx, rcx
0x180009163  jz      short loc_18000917A
0x180009165  mov     [rbp+57h+var_98], 0
0x18000916d  mov     rax, [rcx]
0x180009170  mov     rax, [rax+10h]
0x180009174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009179  nop
0x18000917a  mov     rsi, [rbp+57h+var_80]
0x18000917e  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180009185  inc     rdi
0x180009188  cmp     word ptr [rsi+rdi*2], 0
0x18000918d  jnz     short loc_180009185
0x18000918f  mov     eax, 0FFFFFFFFh
0x180009194  cmp     rdi, rax
0x180009197  jbe     short loc_1800091B1
0x180009199  mov     edi, eax
0x18000919b  xor     r9d, r9d; lpArguments
0x18000919e  xor     r8d, r8d; nNumberOfArguments
0x1800091a1  mov     edx, 1; dwExceptionFlags
0x1800091a6  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800091ab  call    cs:__imp_RaiseException
0x1800091b1  lea     r9, [rbp+57h+var_58]; string
0x1800091b5  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800091b9  mov     edx, edi; length
0x1800091bb  mov     rcx, rsi; sourceString
0x1800091be  call    cs:__imp_WindowsCreateStringReference
0x1800091c4  lea     r8, [rbp+57h+var_98]
0x1800091c8  mov     rdx, [rbp+57h+var_58]
0x1800091cc  mov     rcx, r14
0x1800091cf  mov     rax, r12
0x1800091d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091d7  mov     rcx, [rbp+5Fh]; this
0x1800091db  test    eax, eax
0x1800091dd  js      loc_18000930F
0x1800091e3  mov     [rbp+57h+var_A0], 0
0x1800091e7  mov     rax, [r13+0]
0x1800091eb  lea     r9, [rbp+57h+var_A0]
0x1800091ef  mov     r8, [rbp+57h+var_98]
0x1800091f3  mov     rdx, rbx
0x1800091f6  mov     rcx, r13
0x1800091f9  mov     rax, [rax+50h]
0x1800091fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009202  mov     rcx, [rbp+5Fh]; this
0x180009206  test    eax, eax
0x180009208  js      loc_1800092FA
0x18000920e  test    rbx, rbx
0x180009211  jz      short loc_18000921D
0x180009213  mov     rcx, rbx; string
0x180009216  call    cs:__imp_WindowsDeleteString
0x18000921c  nop
0x18000921d  mov     rcx, [rbp+57h+var_80]; bstrString
0x180009221  call    cs:__imp_SysFreeString
0x180009227  nop
0x180009228  mov     rcx, [rbp+57h+sourceString]; bstrString
0x18000922c  call    cs:__imp_SysFreeString
0x180009232  nop
0x180009233  mov     rcx, [rbp+57h+var_98]
0x180009237  xor     edi, edi
0x180009239  test    rcx, rcx
0x18000923c  jz      short loc_18000924F
0x18000923e  mov     [rbp+57h+var_98], rdi
0x180009242  mov     rax, [rcx]
0x180009245  mov     rax, [rax+10h]
0x180009249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000924e  nop
0x18000924f  mov     rcx, [rbp+57h+var_90]
0x180009253  test    rcx, rcx
0x180009256  jz      short loc_180009269
0x180009258  mov     [rbp+57h+var_90], rdi
0x18000925c  mov     rax, [rcx]
0x18000925f  mov     rax, [rax+10h]
0x180009263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009268  nop
0x180009269  inc     r15d
0x18000926c  cmp     r15d, [rbp+57h+var_9C]
0x180009270  jge     short loc_18000927B
0x180009272  mov     rsi, [rbp+57h+var_60]
0x180009276  jmp     loc_18000906E
0x18000927b  mov     rcx, [rbp+57h+var_88]
0x18000927f  test    rcx, rcx
0x180009282  jz      short loc_180009295
0x180009284  mov     [rbp+57h+var_88], rdi
0x180009288  mov     rax, [rcx]
0x18000928b  mov     rax, [rax+10h]
0x18000928f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009294  nop
0x180009295  mov     rcx, [rbp+57h+var_38]
0x180009299  xor     rcx, rsp; StackCookie
0x18000929c  call    __security_check_cookie
0x1800092a1  mov     rbx, [rsp+0D0h+arg_18]
0x1800092a9  add     rsp, 0A0h
0x1800092b0  pop     r15
0x1800092b2  pop     r14
0x1800092b4  pop     r13
0x1800092b6  pop     r12
0x1800092b8  pop     rdi
0x1800092b9  pop     rsi
0x1800092ba  pop     rbp
0x1800092bb  retn
0x1800092bc  mov     edi, 80070216h
0x1800092c1  jmp     loc_180009143
0x1800092c6  mov     edi, 80004003h
0x1800092cb  jmp     loc_180009143
0x1800092d0  mov     r9d, eax; char *
0x1800092d3  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800092da  mov     edx, 69Ah; void *
0x1800092df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800092e5  mov     r9d, eax; char *
0x1800092e8  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800092ef  mov     edx, 69Eh; void *
0x1800092f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800092fa  mov     r9d, eax; char *
0x1800092fd  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009304  mov     edx, 6BBh; void *
0x180009309  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000930f  mov     r9d, eax; char *
0x180009312  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009319  mov     edx, 6B6h; void *
0x18000931e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009324  mov     r9d, edi; char *
0x180009327  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000932e  mov     edx, 6B2h; void *
0x180009333  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009339  mov     r9d, eax; char *
0x18000933c  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009343  mov     edx, 6ADh; void *
0x180009348  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000934e  mov     r9d, eax; char *
0x180009351  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009358  mov     edx, 6ABh; void *
0x18000935d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009363  mov     r9d, eax; char *
0x180009366  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000936d  mov     edx, 6A6h; void *
0x180009372  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
