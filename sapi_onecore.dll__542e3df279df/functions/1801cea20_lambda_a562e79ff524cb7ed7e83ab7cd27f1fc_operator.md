# _lambda_a562e79ff524cb7ed7e83ab7cd27f1fc_::operator()

- ea: `0x1801cea20`
- end: `0x1801ceb95`
- name: `_lambda_a562e79ff524cb7ed7e83ab7cd27f1fc_::operator()`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b510`

## callees

- `0x18001ce70`
- `0x180021944`
- `0x180026508`
- `0x18003812c`
- `0x180079e30`
- `0x1801cea20`
- `0x18028b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1801ceb28`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1801ceb28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ceac4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ceb04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ceb5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ceac4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ceb04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ceb5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ceb12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ceb38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ceb44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ceb12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ceb38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ceb44`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801cea9f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801cea9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 lambda_a562e79ff524cb7ed7e83ab7cd27f1fc_::operator()()
{
  __int64 v1; // rbx
  int ActivationFactory; // ebx
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rbx
  int v5; // eax
  PCWSTR StringRawBuffer; // rax
  const unsigned __int16 *v7; // rax
  HSTRING string; // [rsp+20h] [rbp-40h] BYREF
  __int64 v9; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  __int64 v11; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  if ( qword_1803B8D40 && *(_QWORD *)(qword_1803B8D40 + 16) )
    return 0;
  v9 = 0;
  v11 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Cortana.Speech.SpeechSettings",
    0x26u,
    0x25u);
  v1 = v11;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  ActivationFactory = RoGetActivationFactory(v1, &GUID_701a24fe_b373_4a89_a2ea_d34eed4dcbe2, &v9);
  if ( ActivationFactory >= 0 )
  {
    string = 0;
    v3 = v9;
    v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v9 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v5 = v4(v3, &string);
    ActivationFactory = v5;
    if ( v5 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( (unsigned int)_o__wcsnicmp(StringRawBuffer) )
        v7 = WindowsGetStringRawBuffer(string, 0);
      else
        v7 = WindowsGetStringRawBuffer(string, 0) + 5;
      Halsey::swstring::assign((Halsey::swstring *)&qword_1803B8D40, v7);
      WindowsDeleteString(string);
      ActivationFactory = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\ipelogginghelper.cpp",
        (const char *)(unsigned int)v5,
        (int)string);
      WindowsDeleteString(string);
    }
    string = 0;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1801cea20  mov     [rsp-8+arg_0], rbx
0x1801cea25  mov     [rsp-8+arg_8], rdi
0x1801cea2a  push    rbp
0x1801cea2b  mov     rbp, rsp
0x1801cea2e  sub     rsp, 60h
0x1801cea32  mov     rax, cs:__security_cookie
0x1801cea39  xor     rax, rsp
0x1801cea3c  mov     [rbp+var_10], rax
0x1801cea40  mov     rax, cs:qword_1803B8D40
0x1801cea47  test    rax, rax
0x1801cea4a  jz      short loc_1801CEA5A
0x1801cea4c  cmp     qword ptr [rax+10h], 0
0x1801cea51  jbe     short loc_1801CEA5A
0x1801cea53  xor     eax, eax
0x1801cea55  jmp     loc_1801CEB79
0x1801cea5a  mov     [rbp+var_38], 0
0x1801cea62  mov     [rbp+var_18], 0
0x1801cea6a  mov     r9d, 25h ; '%'; unsigned int
0x1801cea70  lea     r8d, [r9+1]; unsigned int
0x1801cea74  lea     rdx, ?RuntimeClass_Windows_Cortana_Speech_SpeechSettings@@3QBGB; "Windows.Cortana.Speech.SpeechSettings"
0x1801cea7b  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1801cea7f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801cea84  mov     rbx, [rbp+var_18]
0x1801cea88  lea     rcx, [rbp+var_38]
0x1801cea8c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801cea91  lea     r8, [rbp+var_38]
0x1801cea95  lea     rdx, _GUID_701a24fe_b373_4a89_a2ea_d34eed4dcbe2
0x1801cea9c  mov     rcx, rbx
0x1801cea9f  call    cs:__imp_RoGetActivationFactory
0x1801ceaa5  mov     ebx, eax
0x1801ceaa7  test    eax, eax
0x1801ceaa9  js      loc_1801CEB6E
0x1801ceaaf  mov     [rbp+string], 0
0x1801ceab7  mov     rdi, [rbp+var_38]
0x1801ceabb  mov     rax, [rdi]
0x1801ceabe  mov     rbx, [rax+30h]
0x1801ceac2  xor     ecx, ecx; string
0x1801ceac4  call    cs:__imp_WindowsDeleteString
0x1801ceaca  mov     [rbp+string], 0
0x1801cead2  lea     rdx, [rbp+string]
0x1801cead6  mov     rcx, rdi
0x1801cead9  mov     rax, rbx
0x1801ceadc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ceae1  mov     ebx, eax
0x1801ceae3  test    eax, eax
0x1801ceae5  jns     short loc_1801CEB0C
0x1801ceae7  mov     rcx, [rbp+8]; this
0x1801ceaeb  mov     r9d, eax; char *
0x1801ceaee  lea     r8, aOnecoreuapEndu_271; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801ceaf5  mov     edx, 46h ; 'F'; void *
0x1801ceafa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ceaff  nop
0x1801ceb00  mov     rcx, [rbp+string]; string
0x1801ceb04  call    cs:__imp_WindowsDeleteString
0x1801ceb0a  jmp     short loc_1801CEB66
0x1801ceb0c  xor     edx, edx; length
0x1801ceb0e  mov     rcx, [rbp+string]; string
0x1801ceb12  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ceb18  mov     r8d, 5
0x1801ceb1e  lea     rdx, aMuid_0; "MUID="
0x1801ceb25  mov     rcx, rax
0x1801ceb28  call    cs:__imp__o__wcsnicmp
0x1801ceb2e  xor     edx, edx; length
0x1801ceb30  mov     rcx, [rbp+string]; string
0x1801ceb34  test    eax, eax
0x1801ceb36  jnz     short loc_1801CEB44
0x1801ceb38  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ceb3e  add     rax, 0Ah
0x1801ceb42  jmp     short loc_1801CEB4A
0x1801ceb44  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ceb4a  mov     rdx, rax; unsigned __int16 *
0x1801ceb4d  lea     rcx, qword_1803B8D40; this
0x1801ceb54  call    ?assign@swstring@Halsey@@QEAAJPEBG@Z; Halsey::swstring::assign(ushort const *)
0x1801ceb59  nop
0x1801ceb5a  mov     rcx, [rbp+string]; string
0x1801ceb5e  call    cs:__imp_WindowsDeleteString
0x1801ceb64  xor     ebx, ebx
0x1801ceb66  mov     [rbp+string], 0
0x1801ceb6e  lea     rcx, [rbp+var_38]
0x1801ceb72  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ceb77  mov     eax, ebx
0x1801ceb79  mov     rcx, [rbp+var_10]
0x1801ceb7d  xor     rcx, rsp; StackCookie
0x1801ceb80  call    __security_check_cookie
0x1801ceb85  mov     rbx, [rsp+60h+arg_0]
0x1801ceb8a  mov     rdi, [rsp+60h+arg_8]
0x1801ceb8f  add     rsp, 60h
0x1801ceb93  pop     rbp
0x1801ceb94  retn
```
