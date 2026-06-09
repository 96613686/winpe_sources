# Microsoft::Diagnostics::ApiServer::GetRpcCallerInformation(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800f6afc`
- end: `0x1800f6cfb`
- name: `?GetRpcCallerInformation@ApiServer@Diagnostics@Microsoft@@IEBAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800f68c0`

## callees

- `0x18001d0ec`
- `0x18001d160`
- `0x180026ecc`
- `0x180032718`
- `0x180034d94`
- `0x1800498f0`
- `0x180089d90`
- `0x18008bd1c`
- `0x1800bc300`
- `0x1800f6afc`
- `0x18012de40`
- `0x18012eb08`
- `0x1801bfab0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f6bc8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f6bc8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800f6b92`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800f6b92`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x1800f6c3e`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x1800f6c3e`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800f6b4b`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800f6b4b`

## string_xrefs

- `0x1800f6b71`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1800f6bdc`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1800f6c52`: `onecore\base\telemetry\utc\common\apiserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Diagnostics::ApiServer::GetRpcCallerInformation(__int64 a1, __int64 a2, __int64 a3)
{
  RPC_STATUS v5; // eax
  unsigned int LastError; // ebx
  HANDLE v7; // rbx
  const char *v8; // r9
  __int64 SidForToken; // rax
  WCHAR *v10; // rdx
  const char *v11; // r9
  unsigned __int64 last_of; // rax
  __int64 v13; // rax
  void *TokenHandle; // [rsp+20h] [rbp-99h] BYREF
  HANDLE v16; // [rsp+28h] [rbp-91h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+30h] [rbp-89h] BYREF
  _BYTE v18[56]; // [rsp+38h] [rbp-81h] BYREF
  DWORD dwProcessId; // [rsp+70h] [rbp-49h]
  LPWSTR lpImageFileName[4]; // [rsp+B0h] [rbp-9h] BYREF
  _BYTE v21[32]; // [rsp+D0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  memset_0(v18, 0, 0x70u);
  RpcCallAttributes[1] = 20;
  RpcCallAttributes[0] = 3;
  v5 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  LastError = v5;
  if ( v5 > 0 )
    LastError = (unsigned __int16)v5 | 0x80010000;
  if ( (LastError & 0x80000000) == 0 )
  {
    v7 = OpenProcess(0x1000u, 0, dwProcessId);
    v16 = v7;
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    if ( OpenProcessToken(v7, 8u, &TokenHandle) )
    {
      SidForToken = Microsoft::Diagnostics::Utils::Os::GetSidForToken(v21, &TokenHandle);
      std::wstring::operator=(a2, SidForToken);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v21);
      std::wstring::wstring(lpImageFileName, 260, 0);
      v10 = (WCHAR *)lpImageFileName;
      if ( lpImageFileName[3] > (LPWSTR)7 )
        v10 = lpImageFileName[0];
      if ( K32GetProcessImageFileNameW(v7, v10, 0x104u) )
      {
        last_of = std::wstring::find_last_of(lpImageFileName, 92);
        if ( last_of != -1 && (LPWSTR)last_of < (LPWSTR)((char *)lpImageFileName[2] - 1) )
        {
          v13 = std::wstring::substr(lpImageFileName, v21, last_of + 1, -1);
          std::wstring::operator=(a3, v13);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v21);
        }
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpImageFileName);
        LastError = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x1B0,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
                      v11);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpImageFileName);
      }
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1AA,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
                    v8);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A4,
      (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
      (const char *)LastError,
      (int)TokenHandle);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800f6afc  mov     [rsp-8+arg_0], rbx
0x1800f6b01  push    rbp
0x1800f6b02  push    rsi
0x1800f6b03  push    rdi
0x1800f6b04  lea     rbp, [rsp-47h]
0x1800f6b09  sub     rsp, 100h
0x1800f6b10  mov     rax, cs:__security_cookie
0x1800f6b17  xor     rax, rsp
0x1800f6b1a  mov     [rbp+57h+var_20], rax
0x1800f6b1e  mov     rdi, r8
0x1800f6b21  mov     rsi, rdx
0x1800f6b24  xor     edx, edx; Val
0x1800f6b26  lea     r8d, [rdx+70h]; Size
0x1800f6b2a  lea     rcx, [rsp+110h+var_D8]; void *
0x1800f6b2f  call    memset_0
0x1800f6b34  mov     [rsp+110h+var_DC], 14h
0x1800f6b3c  mov     [rsp+110h+RpcCallAttributes], 3
0x1800f6b44  lea     rdx, [rsp+110h+RpcCallAttributes]; RpcCallAttributes
0x1800f6b49  xor     ecx, ecx; ClientBinding
0x1800f6b4b  call    cs:__imp_RpcServerInqCallAttributesW
0x1800f6b52  nop     dword ptr [rax+rax+00h]
0x1800f6b57  mov     ebx, eax
0x1800f6b59  test    eax, eax
0x1800f6b5b  jle     short loc_1800F6B66
0x1800f6b5d  movzx   ebx, ax
0x1800f6b60  or      ebx, 80010000h
0x1800f6b66  test    ebx, ebx
0x1800f6b68  jns     short loc_1800F6B87
0x1800f6b6a  mov     rcx, [rbp+5Fh]; this
0x1800f6b6e  mov     r9d, ebx; char *
0x1800f6b71  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1800f6b78  mov     edx, 1A4h; void *
0x1800f6b7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6b82  jmp     loc_1800F6CD9
0x1800f6b87  mov     r8d, [rbp+57h+dwProcessId]; dwProcessId
0x1800f6b8b  xor     edx, edx; bInheritHandle
0x1800f6b8d  mov     ecx, 1000h; dwDesiredAccess
0x1800f6b92  call    cs:__imp_OpenProcess
0x1800f6b99  nop     dword ptr [rax+rax+00h]
0x1800f6b9e  mov     rbx, rax
0x1800f6ba1  mov     [rsp+110h+var_E8], rax
0x1800f6ba6  mov     [rsp+110h+TokenHandle], 0
0x1800f6baf  xor     edx, edx
0x1800f6bb1  lea     rcx, [rsp+110h+TokenHandle]
0x1800f6bb6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800f6bbb  lea     r8, [rsp+110h+TokenHandle]; TokenHandle
0x1800f6bc0  mov     edx, 8; DesiredAccess
0x1800f6bc5  mov     rcx, rbx; ProcessHandle
0x1800f6bc8  call    cs:__imp_OpenProcessToken
0x1800f6bcf  nop     dword ptr [rax+rax+00h]
0x1800f6bd4  test    eax, eax
0x1800f6bd6  jnz     short loc_1800F6BF4
0x1800f6bd8  mov     rcx, [rbp+5Fh]; this
0x1800f6bdc  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1800f6be3  mov     edx, 1AAh; void *
0x1800f6be8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f6bed  mov     ebx, eax
0x1800f6bef  jmp     loc_1800F6CC4
0x1800f6bf4  lea     rdx, [rsp+110h+TokenHandle]
0x1800f6bf9  lea     rcx, [rbp+57h+var_40]
0x1800f6bfd  call    ?GetSidForToken@Os@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Diagnostics::Utils::Os::GetSidForToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x1800f6c02  mov     rdx, rax
0x1800f6c05  mov     rcx, rsi
0x1800f6c08  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800f6c0d  lea     rcx, [rbp+57h+var_40]; this
0x1800f6c11  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800f6c16  xor     r8d, r8d
0x1800f6c19  mov     esi, 104h
0x1800f6c1e  mov     edx, esi
0x1800f6c20  lea     rcx, [rbp+57h+lpImageFileName]
0x1800f6c24  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x1800f6c29  nop
0x1800f6c2a  lea     rdx, [rbp+57h+lpImageFileName]
0x1800f6c2e  cmp     [rbp+57h+var_48], 7
0x1800f6c33  cmova   rdx, [rbp+57h+lpImageFileName]; lpImageFileName
0x1800f6c38  mov     r8d, esi; nSize
0x1800f6c3b  mov     rcx, rbx; hProcess
0x1800f6c3e  call    cs:__imp_K32GetProcessImageFileNameW
0x1800f6c45  nop     dword ptr [rax+rax+00h]
0x1800f6c4a  test    eax, eax
0x1800f6c4c  jnz     short loc_1800F6C70
0x1800f6c4e  mov     rcx, [rbp+5Fh]; this
0x1800f6c52  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1800f6c59  mov     edx, 1B0h; void *
0x1800f6c5e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f6c63  mov     ebx, eax
0x1800f6c65  lea     rcx, [rbp+57h+lpImageFileName]; this
0x1800f6c69  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800f6c6e  jmp     short loc_1800F6CC4
0x1800f6c70  mov     edx, 5Ch ; '\'
0x1800f6c75  lea     rcx, [rbp+57h+lpImageFileName]
0x1800f6c79  call    ?find_last_of@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_K_W_K@Z; std::wstring::find_last_of(wchar_t,unsigned __int64)
0x1800f6c7e  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800f6c82  cmp     rax, r9
0x1800f6c85  jz      short loc_1800F6CB9
0x1800f6c87  mov     rdx, [rbp+57h+var_50]
0x1800f6c8b  dec     rdx
0x1800f6c8e  cmp     rax, rdx
0x1800f6c91  jnb     short loc_1800F6CB9
0x1800f6c93  lea     r8, [rax+1]
0x1800f6c97  lea     rdx, [rbp+57h+var_40]
0x1800f6c9b  lea     rcx, [rbp+57h+lpImageFileName]
0x1800f6c9f  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800f6ca4  mov     rdx, rax
0x1800f6ca7  mov     rcx, rdi
0x1800f6caa  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800f6caf  lea     rcx, [rbp+57h+var_40]; this
0x1800f6cb3  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800f6cb8  nop
0x1800f6cb9  lea     rcx, [rbp+57h+lpImageFileName]; this
0x1800f6cbd  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800f6cc2  xor     ebx, ebx
0x1800f6cc4  lea     rcx, [rsp+110h+TokenHandle]
0x1800f6cc9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800f6cce  nop
0x1800f6ccf  lea     rcx, [rsp+110h+var_E8]
0x1800f6cd4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800f6cd9  mov     eax, ebx
0x1800f6cdb  mov     rcx, [rbp+57h+var_20]
0x1800f6cdf  xor     rcx, rsp; StackCookie
0x1800f6ce2  call    __security_check_cookie
0x1800f6ce7  mov     rbx, [rsp+110h+arg_0]
0x1800f6cef  add     rsp, 100h
0x1800f6cf6  pop     rdi
0x1800f6cf7  pop     rsi
0x1800f6cf8  pop     rbp
0x1800f6cf9  retn
```
