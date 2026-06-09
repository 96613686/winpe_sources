# IsGameManager::GetPathProcessNameFromProcessId(ulong,Windows::Internal::String *)

- ea: `0x180053150`
- end: `0x18005337d`
- name: `?GetPathProcessNameFromProcessId@IsGameManager@@UEAAJKPEAVString@Internal@Windows@@@Z`
- size: `557`
- prototype: `int(IsGameManager *__hidden this, unsigned int, struct Windows::Internal::String *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800237c8`
- `0x180051b40`
- `0x180051b5c`
- `0x180053150`
- `0x1802bbaf8`
- `0x180356360`
- `0x180356edc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180053228`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180053228`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800531e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800532b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800531e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800532b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053200`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800532cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800532df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053338`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053200`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800532cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800532df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053338`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005321a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180053347`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005321a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180053347`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005320f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005328f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005320f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005328f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800531a0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800531a0`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800531c6`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800531c6`

## string_xrefs

- `0x180053273`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x18005331c`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x18005335a`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`

## pseudocode

```c
__int64 __fastcall IsGameManager::GetPathProcessNameFromProcessId(IsGameManager *this, DWORD a2, HSTRING *a3)
{
  HANDLE v5; // rax
  wil::details *v6; // rcx
  void *v7; // rdi
  const char *v8; // r9
  HRESULT v9; // eax
  int LastErrorFailHr; // ebp
  HSTRING v11; // rbx
  const wchar_t *StringRawBuffer; // rax
  wchar_t *v13; // rax
  const WCHAR *v14; // rax
  unsigned __int64 v15; // rdx
  HRESULT v16; // edi
  HSTRING v18; // rcx
  DWORD dwSize; // [rsp+20h] [rbp-868h] BYREF
  HSTRING string; // [rsp+28h] [rbp-860h] BYREF
  HANDLE v21[2]; // [rsp+30h] [rbp-858h] BYREF
  WCHAR ExeName[1040]; // [rsp+40h] [rbp-848h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+888h] [rbp+0h]

  memset_0(ExeName, 0, sizeof(ExeName));
  dwSize = 1040;
  v5 = OpenProcess(0x1000u, 0, a2);
  v21[0] = v5;
  v7 = v5;
  if ( !v5 )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v6);
    goto LABEL_16;
  }
  if ( !QueryFullProcessImageNameW(v5, 0, ExeName, &dwSize) )
  {
    LastErrorFailHr = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xA04,
                        (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
                        v8);
    if ( v7 != (void *)-1LL )
      CloseHandle(v7);
LABEL_16:
    v11 = 0;
    if ( LastErrorFailHr >= 0 )
      goto LABEL_6;
    return (unsigned int)LastErrorFailHr;
  }
  string = 0;
  v9 = WindowsCreateString(ExeName, dwSize, &string);
  LastErrorFailHr = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA06,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)(unsigned int)v9,
      dwSize);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v21);
    return (unsigned int)LastErrorFailHr;
  }
  v11 = string;
  WindowsDeleteString(0);
  if ( v7 != (void *)-1LL )
    CloseHandle(v7);
LABEL_6:
  StringRawBuffer = WindowsGetStringRawBuffer(v11, 0);
  v13 = wcsrchr(StringRawBuffer, 0x5Cu);
  if ( v13 )
    v14 = v13 + 1;
  else
    v14 = WindowsGetStringRawBuffer(v11, 0);
  if ( v14 )
  {
    string = 0;
    v15 = -1;
    do
      ++v15;
    while ( v14[v15] );
    if ( v15 <= 0xFFFFFFFF )
    {
      v16 = WindowsCreateString(v14, v15, &string);
      if ( v16 >= 0 )
      {
        v18 = *a3;
        *a3 = string;
        WindowsDeleteString(v18);
      }
    }
    else
    {
      v16 = -2147024362;
    }
    if ( v16 >= 0 )
    {
      if ( v11 )
        WindowsDeleteString(v11);
      return 0;
    }
  }
  else
  {
    v16 = -2147467261;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x830,
    (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
    (const char *)(unsigned int)v16,
    dwSize);
  if ( v11 )
    WindowsDeleteString(v11);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180053150  mov     [rsp+arg_0], rbx
0x180053155  mov     [rsp+arg_18], rbp
0x18005315a  push    rsi
0x18005315b  push    rdi
0x18005315c  push    r14
0x18005315e  sub     rsp, 870h
0x180053165  mov     rax, cs:__security_cookie
0x18005316c  xor     rax, rsp
0x18005316f  mov     [rsp+888h+var_28], rax
0x180053177  mov     r14, r8
0x18005317a  lea     rcx, [rsp+888h+ExeName]; void *
0x18005317f  mov     ebx, edx
0x180053181  mov     r8d, 820h; Size
0x180053187  xor     edx, edx; Val
0x180053189  call    memset_0
0x18005318e  mov     r8d, ebx; dwProcessId
0x180053191  mov     [rsp+888h+dwSize], 410h; int
0x180053199  xor     edx, edx; bInheritHandle
0x18005319b  mov     ecx, 1000h; dwDesiredAccess
0x1800531a0  call    cs:__imp_OpenProcess
0x1800531a6  mov     [rsp+888h+var_858], rax
0x1800531ab  mov     rdi, rax
0x1800531ae  test    rax, rax
0x1800531b1  jz      loc_180053297
0x1800531b7  lea     r9, [rsp+888h+dwSize]; lpdwSize
0x1800531bc  xor     edx, edx; dwFlags
0x1800531be  lea     r8, [rsp+888h+ExeName]; lpExeName
0x1800531c3  mov     rcx, rax; hProcess
0x1800531c6  call    cs:__imp_QueryFullProcessImageNameW
0x1800531cc  test    eax, eax
0x1800531ce  jz      loc_18005326B
0x1800531d4  mov     edx, [rsp+888h+dwSize]; length
0x1800531d8  lea     r8, [rsp+888h+string]; string
0x1800531dd  xor     esi, esi
0x1800531df  lea     rcx, [rsp+888h+ExeName]; sourceString
0x1800531e4  mov     [rsp+888h+string], rsi
0x1800531e9  call    cs:__imp_WindowsCreateString
0x1800531ef  mov     ebp, eax
0x1800531f1  test    eax, eax
0x1800531f3  js      loc_180053352
0x1800531f9  mov     rbx, [rsp+888h+string]
0x1800531fe  xor     ecx, ecx; string
0x180053200  call    cs:__imp_WindowsDeleteString
0x180053206  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18005320a  jz      short loc_180053215
0x18005320c  mov     rcx, rdi; hObject
0x18005320f  call    cs:__imp_CloseHandle
0x180053215  xor     edx, edx; length
0x180053217  mov     rcx, rbx; string
0x18005321a  call    cs:__imp_WindowsGetStringRawBuffer
0x180053220  mov     rcx, rax; Str
0x180053223  mov     edx, 5Ch ; '\'; Ch
0x180053228  call    cs:__imp_wcsrchr
0x18005322e  test    rax, rax
0x180053231  jz      loc_180053342
0x180053237  add     rax, 2
0x18005323b  test    rax, rax
0x18005323e  jz      loc_18005330F
0x180053244  mov     [rsp+888h+string], rsi
0x180053249  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180053250  inc     rdx; length
0x180053253  cmp     word ptr [rax+rdx*2], 0
0x180053258  jnz     short loc_180053250
0x18005325a  mov     ecx, 0FFFFFFFFh
0x18005325f  cmp     rdx, rcx
0x180053262  jbe     short loc_1800532AE
0x180053264  mov     edi, 80070216h
0x180053269  jmp     short loc_1800532D3
0x18005326b  mov     rcx, [rsp+888h]; this
0x180053273  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x18005327a  mov     edx, 0A04h; void *
0x18005327f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180053284  mov     ebp, eax
0x180053286  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18005328a  jz      short loc_18005329E
0x18005328c  mov     rcx, rdi; hObject
0x18005328f  call    cs:__imp_CloseHandle
0x180053295  jmp     short loc_18005329E
0x180053297  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005329c  mov     ebp, eax
0x18005329e  xor     esi, esi
0x1800532a0  mov     ebx, esi
0x1800532a2  test    ebp, ebp
0x1800532a4  jns     loc_180053215
0x1800532aa  mov     eax, ebp
0x1800532ac  jmp     short loc_1800532E7
0x1800532ae  lea     r8, [rsp+888h+string]; string
0x1800532b3  mov     rcx, rax; sourceString
0x1800532b6  call    cs:__imp_WindowsCreateString
0x1800532bc  mov     edi, eax
0x1800532be  test    eax, eax
0x1800532c0  js      short loc_1800532D3
0x1800532c2  mov     rax, [rsp+888h+string]
0x1800532c7  mov     rcx, [r14]; string
0x1800532ca  mov     [r14], rax
0x1800532cd  call    cs:__imp_WindowsDeleteString
0x1800532d3  test    edi, edi
0x1800532d5  js      short loc_180053314
0x1800532d7  test    rbx, rbx
0x1800532da  jz      short loc_1800532E5
0x1800532dc  mov     rcx, rbx; string
0x1800532df  call    cs:__imp_WindowsDeleteString
0x1800532e5  xor     eax, eax
0x1800532e7  mov     rcx, [rsp+888h+var_28]
0x1800532ef  xor     rcx, rsp; StackCookie
0x1800532f2  call    __security_check_cookie
0x1800532f7  lea     r11, [rsp+888h+var_18]
0x1800532ff  mov     rbx, [r11+20h]
0x180053303  mov     rbp, [r11+38h]
0x180053307  mov     rsp, r11
0x18005330a  pop     r14
0x18005330c  pop     rdi
0x18005330d  pop     rsi
0x18005330e  retn
0x18005330f  mov     edi, 80004003h
0x180053314  mov     rcx, [rsp+888h]; this
0x18005331c  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x180053323  mov     r9d, edi; char *
0x180053326  mov     edx, 830h; void *
0x18005332b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053330  test    rbx, rbx
0x180053333  jz      short loc_18005333E
0x180053335  mov     rcx, rbx; string
0x180053338  call    cs:__imp_WindowsDeleteString
0x18005333e  mov     eax, edi
0x180053340  jmp     short loc_1800532E7
0x180053342  xor     edx, edx; length
0x180053344  mov     rcx, rbx; string
0x180053347  call    cs:__imp_WindowsGetStringRawBuffer
0x18005334d  jmp     loc_18005323B
0x180053352  mov     rcx, [rsp+888h]; this
0x18005335a  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x180053361  mov     r9d, eax; char *
0x180053364  mov     edx, 0A06h; void *
0x180053369  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005336e  lea     rcx, [rsp+888h+var_858]
0x180053373  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180053378  jmp     loc_1800532AA
```
