# Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::ShouldCacheToken(void)

- ea: `0x1801cd68c`
- end: `0x1801cd807`
- name: `?ShouldCacheToken@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAA_NXZ`
- size: `379`
- prototype: `bool __fastcall(Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b1a8`

## callees

- `0x180021944`
- `0x1800b6dc8`
- `0x1801ca9c0`
- `0x1801cd4b8`
- `0x1801cd68c`
- `0x18028b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801cd7bb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801cd7bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801cd751`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801cd751`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801cd776`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801cd776`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801cd6e1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801cd6e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cd725`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cd7d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cd7e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cd725`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cd7d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cd7e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801cd7a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801cd7af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801cd7a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801cd7af`

## string_xrefs

- `0x1801cd6cc`: `ShouldCacheToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::ShouldCacheToken(
        Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication *this)
{
  bool result; // al
  __int64 v3; // [rsp+48h] [rbp-18h] BYREF
  int v4; // [rsp+88h] [rbp+28h] BYREF
  DWORD v5; // [rsp+90h] [rbp+30h] BYREF
  HSTRING string; // [rsp+98h] [rbp+38h]

  v5 = 4;
  v4 = 0;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"Software\\Microsoft\\Speech_OneCore\\Settings",
    L"ShouldCacheToken",
    0x18u,
    0,
    &v4,
    &v5);
  result = 0;
  if ( v4 )
  {
    string = 0;
    v3 = 0;
    Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetActiveSystemUser(this);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v3);
    WindowsDeleteString(string);
    if ( v4 )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1801cd68c  mov     r11, rsp
0x1801cd68f  mov     [r11+8], rbx
0x1801cd693  push    rbp
0x1801cd694  push    rsi
0x1801cd695  push    rdi
0x1801cd696  mov     rbp, rsp
0x1801cd699  sub     rsp, 60h
0x1801cd69d  mov     rsi, rcx
0x1801cd6a0  mov     [rbp+arg_10], 4
0x1801cd6a7  mov     [rbp+arg_8], 0
0x1801cd6ae  lea     rax, [rbp+arg_10]
0x1801cd6b2  mov     [r11-48h], rax
0x1801cd6b6  lea     rax, [rbp+arg_8]
0x1801cd6ba  mov     [r11-50h], rax
0x1801cd6be  mov     qword ptr [r11-58h], 0
0x1801cd6c6  mov     r9d, 18h; dwFlags
0x1801cd6cc  lea     r8, aShouldcachetok; "ShouldCacheToken"
0x1801cd6d3  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Speech_OneCore\\Se"...
0x1801cd6da  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1801cd6e1  call    cs:__imp_RegGetValueW
0x1801cd6e7  cmp     [rbp+arg_8], 0
0x1801cd6eb  jz      loc_1801CD7F5
0x1801cd6f1  mov     [rbp+string], 0
0x1801cd6f9  mov     [rbp+var_18], 0
0x1801cd701  lea     rdx, [rbp+var_18]
0x1801cd705  mov     rcx, rsi
0x1801cd708  call    ?GetActiveSystemUser@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJAEAV?$ComPtr@UIUser@System@Windows@@@WRL@6@@Z; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetActiveSystemUser(Microsoft::WRL::ComPtr<Windows::System::IUser> &)
0x1801cd70d  mov     rbx, [rbp+var_18]
0x1801cd711  test    rbx, rbx
0x1801cd714  jz      loc_1801CD7D7
0x1801cd71a  mov     rax, [rbx]
0x1801cd71d  mov     rdi, [rax+30h]
0x1801cd721  mov     rcx, [rbp+string]; string
0x1801cd725  call    cs:__imp_WindowsDeleteString
0x1801cd72b  mov     [rbp+string], 0
0x1801cd733  lea     rdx, [rbp+string]
0x1801cd737  mov     rcx, rbx
0x1801cd73a  mov     rax, rdi
0x1801cd73d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cd742  mov     [rbp+newString], 0
0x1801cd74a  lea     rdi, [rsi+18h]
0x1801cd74e  mov     rcx, rdi; lpCriticalSection
0x1801cd751  call    cs:__imp_EnterCriticalSection
0x1801cd757  mov     rax, [rsi+78h]
0x1801cd75b  mov     [rbp+var_10], rax
0x1801cd75f  lea     rdx, [rbp+var_10]; HSTRING *
0x1801cd763  lea     rcx, [rbp+newString]; newString
0x1801cd767  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1801cd76c  mov     ebx, eax
0x1801cd76e  test    rdi, rdi
0x1801cd771  jz      short loc_1801CD77C
0x1801cd773  mov     rcx, rdi; lpCriticalSection
0x1801cd776  call    cs:__imp_LeaveCriticalSection
0x1801cd77c  mov     rcx, [rbp+18h]; this
0x1801cd780  test    ebx, ebx
0x1801cd782  jns     short loc_1801CD79A
0x1801cd784  mov     r9d, ebx; char *
0x1801cd787  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801cd78e  mov     edx, 28Bh; void *
0x1801cd793  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801cd798  jmp     short loc_1801CD7C5
0x1801cd79a  xor     edx, edx; length
0x1801cd79c  mov     rcx, [rbp+newString]; string
0x1801cd7a0  call    cs:__imp_WindowsGetStringRawBuffer
0x1801cd7a6  mov     rbx, rax
0x1801cd7a9  xor     edx, edx; length
0x1801cd7ab  mov     rcx, [rbp+string]; string
0x1801cd7af  call    cs:__imp_WindowsGetStringRawBuffer
0x1801cd7b5  mov     rdx, rbx
0x1801cd7b8  mov     rcx, rax
0x1801cd7bb  call    cs:__imp__o__wcsicmp
0x1801cd7c1  test    eax, eax
0x1801cd7c3  jz      short loc_1801CD7CC
0x1801cd7c5  mov     [rbp+arg_8], 0
0x1801cd7cc  mov     rcx, [rbp+newString]; string
0x1801cd7d0  call    cs:__imp_WindowsDeleteString
0x1801cd7d6  nop
0x1801cd7d7  lea     rcx, [rbp+var_18]
0x1801cd7db  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801cd7e0  nop
0x1801cd7e1  mov     rcx, [rbp+string]; string
0x1801cd7e5  call    cs:__imp_WindowsDeleteString
0x1801cd7eb  cmp     [rbp+arg_8], 0
0x1801cd7ef  jz      short loc_1801CD7F5
0x1801cd7f1  mov     al, 1
0x1801cd7f3  jmp     short loc_1801CD7F7
0x1801cd7f5  xor     al, al
0x1801cd7f7  mov     rbx, [rsp+60h+arg_0]
0x1801cd7ff  add     rsp, 60h
0x1801cd803  pop     rdi
0x1801cd804  pop     rsi
0x1801cd805  pop     rbp
0x1801cd806  retn
```
