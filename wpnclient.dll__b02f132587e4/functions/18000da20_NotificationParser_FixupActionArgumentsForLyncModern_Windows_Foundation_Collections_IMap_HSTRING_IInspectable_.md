# NotificationParser::FixupActionArgumentsForLyncModern(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *)

- ea: `0x18000da20`
- end: `0x18000dc1c`
- name: `?FixupActionArgumentsForLyncModern@NotificationParser@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG@Z`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002d280`

## callees

- `0x180005670`
- `0x18000da20`
- `0x18000dc30`
- `0x18001b848`
- `0x18001ff00`
- `0x1800307b4`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000db25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000db25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dafa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dbd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dafa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dbd2`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabledForPackage` at `0x18000da68`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabledForPackage` at `0x18000da68`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall NotificationParser::FixupActionArgumentsForLyncModern(__int64 *a1, __int64 a2, __int64 a3)
{
  int (__fastcall *v5)(__int64, _QWORD, __int64 *); // rbx
  __int64 v6; // rbx
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rdi
  int v8; // eax
  const wchar_t *StringRawBuffer; // rax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64 *); // rbx
  int v12; // eax
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v14; // rbx
  int v15; // eax
  int v16; // [rsp+20h] [rbp-60h]
  _BYTE v17[4]; // [rsp+30h] [rbp-50h] BYREF
  int v18; // [rsp+34h] [rbp-4Ch] BYREF
  __int64 v19; // [rsp+38h] [rbp-48h] BYREF
  HSTRING string; // [rsp+40h] [rbp-40h] BYREF
  __int64 v21; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v22[4]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  if ( a3 )
  {
    v18 = 0;
    if ( (int)QuirkIsEnabledForPackage(a3, 0, 1114118, &v18) >= 0 )
    {
      if ( v18 )
      {
        v21 = 0;
        v5 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a2 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
        Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v22, L"arguments");
        if ( v5(a2, v22[0], &v21) >= 0 )
        {
          v6 = v21;
          if ( v21 )
          {
            string = 0;
            v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v21 + 152LL);
            WindowsDeleteString(0);
            string = 0;
            v8 = v7(v6, &string);
            if ( v8 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x64C,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\not"
                              "ificationparser.cpp",
                (const char *)(unsigned int)v8,
                v16);
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            if ( !wcscmp_0(StringRawBuffer, L"decline") )
            {
              v19 = 0;
              v10 = *a1;
              v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*a1 + 144LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
              Windows::Internal::StringReference::_ConstructorHelper(
                (Windows::Internal::StringReference *)v22,
                L"decline ");
              v12 = v11(v10, v22[0], &v19);
              if ( v12 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x651,
                  (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\n"
                                "otificationparser.cpp",
                  (const char *)(unsigned int)v12,
                  v16);
              v17[0] = 0;
              v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)a2 + 80LL);
              v14 = v19;
              Windows::Internal::StringReference::_ConstructorHelper(
                (Windows::Internal::StringReference *)v22,
                L"arguments");
              v15 = v13(a2, v22[0], v14, v17);
              if ( v15 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x654,
                  (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\n"
                                "otificationparser.cpp",
                  (const char *)(unsigned int)v15,
                  v16);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
            }
            WindowsDeleteString(string);
          }
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
      }
    }
  }
}

```

## disassembly

```asm
0x18000da20  test    r8, r8
0x18000da23  jz      short locret_18000DA94
0x18000da25  mov     [rsp-28h+arg_18], rbx
0x18000da2a  push    rbp
0x18000da2b  push    rsi
0x18000da2c  push    rdi
0x18000da2d  push    r14
0x18000da2f  push    r15
0x18000da31  mov     rbp, rsp
0x18000da34  sub     rsp, 80h
0x18000da3b  mov     rax, cs:__security_cookie
0x18000da42  xor     rax, rsp
0x18000da45  mov     [rbp+var_10], rax
0x18000da49  mov     rax, r8
0x18000da4c  mov     rsi, rdx
0x18000da4f  mov     r14, rcx
0x18000da52  xor     r15d, r15d
0x18000da55  mov     [rbp+var_4C], r15d
0x18000da59  lea     r9, [rbp+var_4C]
0x18000da5d  xor     edx, edx
0x18000da5f  mov     r8d, 110006h
0x18000da65  mov     rcx, rax
0x18000da68  call    cs:__imp_QuirkIsEnabledForPackage
0x18000da6e  test    eax, eax
0x18000da70  jns     short loc_18000DA95
0x18000da72  mov     rcx, [rbp+var_10]
0x18000da76  xor     rcx, rsp; StackCookie
0x18000da79  call    __security_check_cookie
0x18000da7e  mov     rbx, [rsp+80h+arg_18]
0x18000da86  add     rsp, 80h
0x18000da8d  pop     r15
0x18000da8f  pop     r14
0x18000da91  pop     rdi
0x18000da92  pop     rsi
0x18000da93  pop     rbp
0x18000da94  retn
0x18000da95  cmp     [rbp+var_4C], r15d
0x18000da99  jz      short loc_18000DA72
0x18000da9b  mov     [rbp+var_38], r15
0x18000da9f  mov     rax, [rsi]
0x18000daa2  mov     rbx, [rax+30h]
0x18000daa6  lea     rcx, [rbp+var_38]
0x18000daaa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000daaf  lea     rdx, aArguments; "arguments"
0x18000dab6  lea     rcx, [rbp+var_30]; this
0x18000daba  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18000dabf  lea     r8, [rbp+var_38]
0x18000dac3  mov     rdx, [rbp+var_30]
0x18000dac7  mov     rcx, rsi
0x18000daca  mov     rax, rbx
0x18000dacd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dad2  test    eax, eax
0x18000dad4  js      short loc_18000DADF
0x18000dad6  mov     rbx, [rbp+var_38]
0x18000dada  test    rbx, rbx
0x18000dadd  jnz     short loc_18000DAEA
0x18000dadf  lea     rcx, [rbp+var_38]
0x18000dae3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000dae8  jmp     short loc_18000DA72
0x18000daea  mov     [rbp+string], r15
0x18000daee  mov     rax, [rbx]
0x18000daf1  mov     rdi, [rax+98h]
0x18000daf8  xor     ecx, ecx; string
0x18000dafa  call    cs:__imp_WindowsDeleteString
0x18000db00  mov     [rbp+string], r15
0x18000db04  lea     rdx, [rbp+string]
0x18000db08  mov     rcx, rbx
0x18000db0b  mov     rax, rdi
0x18000db0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db13  mov     rcx, [rbp+28h]; this
0x18000db17  test    eax, eax
0x18000db19  js      loc_18000DBDD
0x18000db1f  xor     edx, edx; length
0x18000db21  mov     rcx, [rbp+string]; string
0x18000db25  call    cs:__imp_WindowsGetStringRawBuffer
0x18000db2b  lea     rdx, aDecline; "decline"
0x18000db32  mov     rcx, rax; String1
0x18000db35  call    wcscmp_0
0x18000db3a  test    eax, eax
0x18000db3c  jnz     loc_18000DBCE
0x18000db42  mov     [rbp+var_48], r15
0x18000db46  mov     rdi, [r14]
0x18000db49  mov     rax, [rdi]
0x18000db4c  mov     rbx, [rax+90h]
0x18000db53  lea     rcx, [rbp+var_48]
0x18000db57  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000db5c  lea     rdx, aDecline_0; "decline "
0x18000db63  lea     rcx, [rbp+var_30]; this
0x18000db67  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18000db6c  lea     r8, [rbp+var_48]
0x18000db70  mov     rdx, [rbp+var_30]
0x18000db74  mov     rcx, rdi
0x18000db77  mov     rax, rbx
0x18000db7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db7f  mov     rcx, [rbp+28h]; this
0x18000db83  test    eax, eax
0x18000db85  js      short loc_18000DBF2
0x18000db87  mov     [rbp+var_50], 0
0x18000db8b  mov     rax, [rsi]
0x18000db8e  mov     rdi, [rax+50h]
0x18000db92  mov     rbx, [rbp+var_48]
0x18000db96  lea     rdx, aArguments; "arguments"
0x18000db9d  lea     rcx, [rbp+var_30]; this
0x18000dba1  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18000dba6  lea     r9, [rbp+var_50]
0x18000dbaa  mov     r8, rbx
0x18000dbad  mov     rdx, [rbp+var_30]
0x18000dbb1  mov     rcx, rsi
0x18000dbb4  mov     rax, rdi
0x18000dbb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbbc  mov     rcx, [rbp+28h]; this
0x18000dbc0  test    eax, eax
0x18000dbc2  js      short loc_18000DC07
0x18000dbc4  lea     rcx, [rbp+var_48]
0x18000dbc8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000dbcd  nop
0x18000dbce  mov     rcx, [rbp+string]; string
0x18000dbd2  call    cs:__imp_WindowsDeleteString
0x18000dbd8  jmp     loc_18000DADF
0x18000dbdd  mov     r9d, eax; char *
0x18000dbe0  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000dbe7  mov     edx, 64Ch; void *
0x18000dbec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000dbf2  mov     r9d, eax; char *
0x18000dbf5  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000dbfc  mov     edx, 651h; void *
0x18000dc01  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000dc07  mov     r9d, eax; char *
0x18000dc0a  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000dc11  mov     edx, 654h; void *
0x18000dc16  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
