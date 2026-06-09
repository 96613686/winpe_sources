# Microsoft::Diagnostics::ApiServer::GetRpcImpersonationToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1802b4efc`
- end: `0x1802b5143`
- name: `?GetRpcImpersonationToken@ApiServer@Diagnostics@Microsoft@@IEBAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `583`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800eaaec`
- `0x18010cfc0`
- `0x1801165e8`
- `0x1801de970`
- `0x1801deafc`
- `0x1801e0980`
- `0x1801e0f90`
- `0x1801e58a0`

## callees

- `0x180002058`
- `0x18001d160`
- `0x180026ecc`
- `0x1800498f0`
- `0x18005d050`
- `0x18007fae8`
- `0x180089d90`
- `0x1800a0d08`
- `0x18012de40`
- `0x1801bfab0`
- `0x1802b4efc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b4f96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b4f96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802b4f6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802b4f6b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802b4f86`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802b4f86`
- `RPCRT4!RpcImpersonateClient` at `0x1802b4f27`
- `RPCRT4!RpcImpersonateClient` at `0x1802b4f27`
- `RPCRT4!RpcRevertToSelf` at `0x1802b4fc1`
- `RPCRT4!RpcRevertToSelf` at `0x1802b4fdc`
- `RPCRT4!RpcRevertToSelf` at `0x1802b5020`
- `RPCRT4!RpcRevertToSelf` at `0x1802b5088`
- `RPCRT4!RpcRevertToSelf` at `0x1802b509c`
- `RPCRT4!RpcRevertToSelf` at `0x1802b4fc1`
- `RPCRT4!RpcRevertToSelf` at `0x1802b4fdc`
- `RPCRT4!RpcRevertToSelf` at `0x1802b5020`
- `RPCRT4!RpcRevertToSelf` at `0x1802b5088`
- `RPCRT4!RpcRevertToSelf` at `0x1802b509c`

## string_xrefs

- `0x1802b4f44`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b4fae`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b50d4`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b50eb`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b5102`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b5119`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802b5130`: `onecore\base\telemetry\utc\common\apiserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=2
__int64 __fastcall Microsoft::Diagnostics::ApiServer::GetRpcImpersonationToken(__int64 a1, void **a2, _QWORD *a3)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  const char *v10; // r9
  __int64 SidForToken; // rax
  const char *v12; // r9
  int v13; // r8d
  int v14; // r9d
  const char *v15; // r9
  __int64 v16; // [rsp+20h] [rbp-48h]
  _QWORD *v17; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v18[32]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a2,
    0);
  if ( RpcImpersonateClient(0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
      (const char *)0x80070005LL,
      v16);
    return 2147942405LL;
  }
  else
  {
    BYTE1(v17) = 1;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a2,
      0);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xEu, 1, a2) )
    {
      SidForToken = Microsoft::Diagnostics::Utils::Os::GetSidForToken(v18, a2);
      std::wstring::operator=(a3, SidForToken);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v18);
      if ( a3[2] )
      {
        if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x2000) )
        {
          if ( a3[3] > 7u )
            a3 = (_QWORD *)*a3;
          v17 = a3;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
            (unsigned int)&dword_18042D328,
            (unsigned int)&unk_1803DBF77,
            v13,
            v14,
            (__int64)&v17);
        }
        if ( RpcRevertToSelf() )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x176,
            (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
            v15);
        return 0;
      }
      else
      {
        if ( RpcRevertToSelf() )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x176,
            (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
            v12);
        return 1168;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError )
      {
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x17D,
               (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
               (const char *)LastError,
               v16);
        if ( RpcRevertToSelf() )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x176,
            (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
            v9);
        return v8;
      }
      else
      {
        if ( RpcRevertToSelf() )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x176,
            (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
            v10);
        return 0;
      }
    }
  }
}

```

## disassembly

```asm
0x1802b4efc  mov     [rsp+arg_0], rbx
0x1802b4f01  push    rdi
0x1802b4f02  sub     rsp, 60h
0x1802b4f06  mov     rax, cs:__security_cookie
0x1802b4f0d  xor     rax, rsp
0x1802b4f10  mov     [rsp+68h+var_10], rax
0x1802b4f15  mov     rbx, r8
0x1802b4f18  mov     rdi, rdx
0x1802b4f1b  xor     edx, edx
0x1802b4f1d  mov     rcx, rdi
0x1802b4f20  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802b4f25  xor     ecx, ecx; BindingHandle
0x1802b4f27  call    cs:__imp_RpcImpersonateClient
0x1802b4f2e  nop     dword ptr [rax+rax+00h]
0x1802b4f33  test    eax, eax
0x1802b4f35  jz      short loc_1802B4F5C
0x1802b4f37  mov     rcx, [rsp+68h]; this
0x1802b4f3c  mov     ebx, 80070005h
0x1802b4f41  mov     r9d, ebx; char *
0x1802b4f44  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b4f4b  mov     edx, 16Bh; void *
0x1802b4f50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b4f55  mov     eax, ebx
0x1802b4f57  jmp     loc_1802B50B6
0x1802b4f5c  mov     byte ptr [rsp+68h+var_38+1], 1
0x1802b4f61  xor     edx, edx
0x1802b4f63  mov     rcx, rdi
0x1802b4f66  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802b4f6b  call    cs:__imp_GetCurrentThread
0x1802b4f72  nop     dword ptr [rax+rax+00h]
0x1802b4f77  mov     r9, rdi; TokenHandle
0x1802b4f7a  mov     edx, 0Eh; DesiredAccess
0x1802b4f7f  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1802b4f83  mov     rcx, rax; ThreadHandle
0x1802b4f86  call    cs:__imp_OpenThreadToken
0x1802b4f8d  nop     dword ptr [rax+rax+00h]
0x1802b4f92  test    eax, eax
0x1802b4f94  jnz     short loc_1802B4FF7
0x1802b4f96  call    cs:__imp_GetLastError
0x1802b4f9d  nop     dword ptr [rax+rax+00h]
0x1802b4fa2  test    eax, eax
0x1802b4fa4  jz      short loc_1802B4FDC
0x1802b4fa6  mov     rcx, [rsp+68h]; this
0x1802b4fab  mov     r9d, eax; char *
0x1802b4fae  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b4fb5  mov     edx, 17Dh; void *
0x1802b4fba  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1802b4fbf  mov     ebx, eax
0x1802b4fc1  call    cs:__imp_RpcRevertToSelf
0x1802b4fc8  nop     dword ptr [rax+rax+00h]
0x1802b4fcd  test    eax, eax
0x1802b4fcf  jnz     loc_1802B50CF
0x1802b4fd5  mov     eax, ebx
0x1802b4fd7  jmp     loc_1802B50B6
0x1802b4fdc  call    cs:__imp_RpcRevertToSelf
0x1802b4fe3  nop     dword ptr [rax+rax+00h]
0x1802b4fe8  test    eax, eax
0x1802b4fea  jnz     loc_1802B50E6
0x1802b4ff0  xor     eax, eax
0x1802b4ff2  jmp     loc_1802B50B6
0x1802b4ff7  mov     rdx, rdi
0x1802b4ffa  lea     rcx, [rsp+68h+var_30]
0x1802b4fff  call    ?GetSidForToken@Os@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Diagnostics::Utils::Os::GetSidForToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x1802b5004  mov     rdx, rax
0x1802b5007  mov     rcx, rbx
0x1802b500a  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1802b500f  lea     rcx, [rsp+68h+var_30]; this
0x1802b5014  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802b5019  cmp     qword ptr [rbx+10h], 0
0x1802b501e  jnz     short loc_1802B503B
0x1802b5020  call    cs:__imp_RpcRevertToSelf
0x1802b5027  nop     dword ptr [rax+rax+00h]
0x1802b502c  test    eax, eax
0x1802b502e  jnz     loc_1802B50FD
0x1802b5034  mov     eax, 490h
0x1802b5039  jmp     short loc_1802B50B6
0x1802b503b  mov     eax, cs:dword_18042D328
0x1802b5041  cmp     eax, 4
0x1802b5044  jbe     short loc_1802B5088
0x1802b5046  mov     edx, 2000h
0x1802b504b  lea     rcx, dword_18042D328
0x1802b5052  call    _tlgKeywordOn
0x1802b5057  test    al, al
0x1802b5059  jz      short loc_1802B5088
0x1802b505b  cmp     qword ptr [rbx+18h], 7
0x1802b5060  jbe     short loc_1802B5065
0x1802b5062  mov     rbx, [rbx]
0x1802b5065  mov     [rsp+30h], rbx
0x1802b506a  lea     rax, [rsp+68h+var_38]
0x1802b506f  mov     [rsp+68h+var_48], rax
0x1802b5074  lea     rdx, unk_1803DBF77
0x1802b507b  lea     rcx, dword_18042D328
0x1802b5082  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1802b5087  nop
0x1802b5088  call    cs:__imp_RpcRevertToSelf
0x1802b508f  nop     dword ptr [rax+rax+00h]
0x1802b5094  test    eax, eax
0x1802b5096  jnz     short loc_1802B5114
0x1802b5098  xor     eax, eax
0x1802b509a  jmp     short loc_1802B50B6
0x1802b509c  call    cs:__imp_RpcRevertToSelf
0x1802b50a3  nop     dword ptr [rax+rax+00h]
0x1802b50a8  test    eax, eax
0x1802b50aa  jnz     short loc_1802B512B
0x1802b50ac  mov     eax, dword ptr [rsp+68h+var_38]
0x1802b50b0  jmp     short loc_1802B50B6
0x1802b50b2  mov     eax, dword ptr [rsp+68h+var_38]
0x1802b50b6  mov     rcx, [rsp+68h+var_10]
0x1802b50bb  xor     rcx, rsp; StackCookie
0x1802b50be  call    __security_check_cookie
0x1802b50c3  mov     rbx, [rsp+68h+arg_0]
0x1802b50c8  add     rsp, 60h
0x1802b50cc  pop     rdi
0x1802b50cd  retn
0x1802b50cf  mov     rcx, [rsp+68h]; this
0x1802b50d4  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b50db  mov     edx, 176h; void *
0x1802b50e0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802b50e6  mov     rcx, [rsp+68h]; this
0x1802b50eb  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b50f2  mov     edx, 176h; void *
0x1802b50f7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802b50fd  mov     rcx, [rsp+68h]; this
0x1802b5102  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b5109  mov     edx, 176h; void *
0x1802b510e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802b5114  mov     rcx, [rsp+68h]; this
0x1802b5119  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b5120  mov     edx, 176h; void *
0x1802b5125  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802b512b  mov     rcx, [rsp+68h]; this
0x1802b5130  lea     r8, aOnecoreBaseTel_266; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802b5137  mov     edx, 176h; void *
0x1802b513c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
