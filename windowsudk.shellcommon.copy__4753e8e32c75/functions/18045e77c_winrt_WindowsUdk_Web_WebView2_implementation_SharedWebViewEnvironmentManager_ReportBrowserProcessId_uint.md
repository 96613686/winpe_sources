# winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager::ReportBrowserProcessId(uint)

- ea: `0x18045e77c`
- end: `0x18045e970`
- name: `?ReportBrowserProcessId@SharedWebViewEnvironmentManager@implementation@WebView2@Web@WindowsUdk@winrt@@QEAAXI@Z`
- size: `500`
- prototype: `void __fastcall(PVOID Context, DWORD dwProcessId)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18045e338`
- `0x18045e750`

## callees

- `0x180045100`
- `0x180094cac`
- `0x1801588c4`
- `0x18045c77c`
- `0x18045e77c`
- `0x18045f8e8`
- `0x18045fe1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18045e7f4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18045e8bd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18045e7f4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18045e8bd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18045e839`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18045e902`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18045e839`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18045e902`

## string_xrefs

- `0x18045e947`: `shellcommon\undockeddevkit\libs\windowsudk.web.webview2\sharedwebviewenvironmentmanager.cpp`
- `0x18045e95e`: `shellcommon\undockeddevkit\libs\windowsudk.web.webview2\sharedwebviewenvironmentmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager::ReportBrowserProcessId(
        char *Context,
        DWORD dwProcessId)
{
  _DWORD *v4; // r15
  HANDLE v5; // rax
  void *v6; // rbx
  const char *v7; // r9
  HANDLE v8; // rax
  void *v9; // rbx
  const char *v10; // r9
  const char *v11; // r9
  __int64 *v12; // rdx
  __int64 v13; // [rsp+0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  _DWORD *v15; // [rsp+60h] [rbp+8h]
  DWORD v16; // [rsp+68h] [rbp+10h]
  char v17; // [rsp+70h] [rbp+18h] BYREF

  if ( !Context[176] )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58649637>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58649637>::GetImpl'::`2'::impl) )
    {
      winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager::AcquireProcessHandleMutex(
        Context,
        &v17);
      if ( dwProcessId )
      {
        v4 = Context + 144;
        if ( *((_DWORD *)Context + 36) != dwProcessId )
        {
          v5 = OpenProcess(0x100001u, 0, dwProcessId);
          wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            Context + 136,
            v5);
          v6 = (void *)*((_QWORD *)Context + 17);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int UnregisterWait(void *)>>::reset(
            Context + 128,
            0);
          if ( !RegisterWaitForSingleObject(
                  (PHANDLE)Context + 16,
                  v6,
                  winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager::OnBrowserProcessExit,
                  Context,
                  0xFFFFFFFF,
                  8u) )
          {
            try
            {
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x183,
                (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.web.webview2\\sharedwebviewenvironmentmanager.cpp",
                v7);
            }
            catch ( ... )
            {
              v12 = &v13;
              wil::details::in1diag3::Log_CaughtException(
                (wil::details::in1diag3 *)v12[11],
                (void *)0x185,
                (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.web.webview2\\sharedwebviewenvironmentmanager.cpp",
                v11);
              dwProcessId = v16;
              v4 = v15;
            }
          }
          *v4 = dwProcessId;
        }
      }
      else
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int UnregisterWait(void *)>>::reset(
          Context + 128,
          0);
        wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          Context + 136,
          0);
        *((_DWORD *)Context + 36) = 0;
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
    }
    else if ( dwProcessId )
    {
      if ( *((_DWORD *)Context + 36) != dwProcessId )
      {
        v8 = OpenProcess(0x100001u, 0, dwProcessId);
        wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          Context + 136,
          v8);
        v9 = (void *)*((_QWORD *)Context + 17);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int UnregisterWait(void *)>>::reset(
          Context + 128,
          0);
        if ( !RegisterWaitForSingleObject(
                (PHANDLE)Context + 16,
                v9,
                winrt::WindowsUdk::Web::WebView2::implementation::SharedWebViewEnvironmentManager::OnBrowserProcessExit,
                Context,
                0xFFFFFFFF,
                8u) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x19F,
            (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.web.webview2\\sharedwebviewenvironmentmanager.cpp",
            v10);
        *((_DWORD *)Context + 36) = dwProcessId;
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int UnregisterWait(void *)>>::reset(
        Context + 128,
        0);
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        Context + 136,
        0);
      *((_DWORD *)Context + 36) = 0;
    }
  }
}

```

## disassembly

```asm
0x18045e77c  mov     [rsp+arg_8], edx
0x18045e780  mov     [rsp+arg_0], rcx
0x18045e785  push    rbx
0x18045e786  push    rsi
0x18045e787  push    rdi
0x18045e788  push    r14
0x18045e78a  push    r15
0x18045e78c  sub     rsp, 30h
0x18045e790  mov     r14d, edx
0x18045e793  mov     rsi, rcx
0x18045e796  cmp     byte ptr [rcx+0B0h], 0
0x18045e79d  jnz     loc_18045E93B
0x18045e7a3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58649637@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58649637@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58649637> `wil::Feature<__WilFeatureTraits_Feature_58649637>::GetImpl(void)'::`2'::impl
0x18045e7aa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58649637@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58649637>::__private_IsEnabled(void)
0x18045e7af  test    al, al
0x18045e7b1  jz      loc_18045E89A
0x18045e7b7  lea     rdx, [rsp+58h+arg_10]
0x18045e7bc  mov     rcx, rsi
0x18045e7bf  call    ?AcquireProcessHandleMutex@SharedWebViewEnvironmentManager@implementation@WebView2@Web@WindowsUdk@winrt@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@XZ
0x18045e7c4  nop
0x18045e7c5  test    r14d, r14d
0x18045e7c8  jz      loc_18045E85D
0x18045e7ce  lea     r15, [rsi+90h]
0x18045e7d5  mov     [rsp+58h+arg_0], r15
0x18045e7da  cmp     [r15], r14d
0x18045e7dd  jz      loc_18045E88B
0x18045e7e3  lea     rbx, [rsi+88h]
0x18045e7ea  mov     r8d, r14d; dwProcessId
0x18045e7ed  xor     edx, edx; bInheritHandle
0x18045e7ef  mov     ecx, 100001h; dwDesiredAccess
0x18045e7f4  call    cs:__imp_OpenProcess
0x18045e7fa  mov     rdx, rax
0x18045e7fd  mov     rcx, rbx
0x18045e800  call    ?reset@?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18045e805  mov     rbx, [rbx]
0x18045e808  lea     rdi, [rsi+80h]
0x18045e80f  xor     edx, edx
0x18045e811  mov     rcx, rdi
0x18045e814  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?UnregisterWait@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&UnregisterWait(void *)>>::reset(void *)
0x18045e819  mov     [rsp+58h+dwFlags], 8; dwFlags
0x18045e821  mov     [rsp+58h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18045e829  mov     r9, rsi; Context
0x18045e82c  lea     r8, ?OnBrowserProcessExit@SharedWebViewEnvironmentManager@implementation@WebView2@Web@WindowsUdk@winrt@@CAXPEAXE@Z; Callback
0x18045e833  mov     rdx, rbx; hObject
0x18045e836  mov     rcx, rdi; phNewWaitObject
0x18045e839  call    cs:__imp_RegisterWaitForSingleObject
0x18045e83f  mov     rcx, [rsp+58h]; this
0x18045e844  test    eax, eax
0x18045e846  jz      loc_18045E947
0x18045e84c  jmp     short loc_18045E858
0x18045e84e  mov     r14d, [rsp+58h+arg_8]
0x18045e853  mov     r15, [rsp+58h+arg_0]
0x18045e858  mov     [r15], r14d
0x18045e85b  jmp     short loc_18045E88B
0x18045e85d  lea     rcx, [rsi+80h]
0x18045e864  xor     edx, edx
0x18045e866  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?UnregisterWait@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&UnregisterWait(void *)>>::reset(void *)
0x18045e86b  lea     rcx, [rsi+88h]
0x18045e872  xor     edx, edx
0x18045e874  call    ?reset@?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18045e879  nop
0x18045e87a  jmp     short loc_18045E881
0x18045e87c  mov     rsi, [rsp+58h+arg_0]
0x18045e881  mov     dword ptr [rsi+90h], 0
0x18045e88b  lea     rcx, [rsp+58h+arg_10]
0x18045e890  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18045e895  jmp     loc_18045E93B
0x18045e89a  test    r14d, r14d
0x18045e89d  jz      short loc_18045E915
0x18045e89f  cmp     [rsi+90h], r14d
0x18045e8a6  jz      loc_18045E93B
0x18045e8ac  lea     rbx, [rsi+88h]
0x18045e8b3  mov     r8d, r14d; dwProcessId
0x18045e8b6  xor     edx, edx; bInheritHandle
0x18045e8b8  mov     ecx, 100001h; dwDesiredAccess
0x18045e8bd  call    cs:__imp_OpenProcess
0x18045e8c3  mov     rdx, rax
0x18045e8c6  mov     rcx, rbx
0x18045e8c9  call    ?reset@?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18045e8ce  mov     rbx, [rbx]
0x18045e8d1  lea     rdi, [rsi+80h]
0x18045e8d8  xor     edx, edx
0x18045e8da  mov     rcx, rdi
0x18045e8dd  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?UnregisterWait@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&UnregisterWait(void *)>>::reset(void *)
0x18045e8e2  mov     [rsp+58h+dwFlags], 8; dwFlags
0x18045e8ea  mov     [rsp+58h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18045e8f2  mov     r9, rsi; Context
0x18045e8f5  lea     r8, ?OnBrowserProcessExit@SharedWebViewEnvironmentManager@implementation@WebView2@Web@WindowsUdk@winrt@@CAXPEAXE@Z; Callback
0x18045e8fc  mov     rdx, rbx; hObject
0x18045e8ff  mov     rcx, rdi; phNewWaitObject
0x18045e902  call    cs:__imp_RegisterWaitForSingleObject
0x18045e908  test    eax, eax
0x18045e90a  jz      short loc_18045E959
0x18045e90c  mov     [rsi+90h], r14d
0x18045e913  jmp     short loc_18045E93B
0x18045e915  lea     rcx, [rsi+80h]
0x18045e91c  xor     edx, edx
0x18045e91e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?UnregisterWait@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&UnregisterWait(void *)>>::reset(void *)
0x18045e923  lea     rcx, [rsi+88h]
0x18045e92a  xor     edx, edx
0x18045e92c  call    ?reset@?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18045e931  mov     dword ptr [rsi+90h], 0
0x18045e93b  add     rsp, 30h
0x18045e93f  pop     r15
0x18045e941  pop     r14
0x18045e943  pop     rdi
0x18045e944  pop     rsi
0x18045e945  pop     rbx
0x18045e946  retn
0x18045e947  lea     r8, aShellcommonUnd_123; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18045e94e  mov     edx, 183h; void *
0x18045e953  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18045e959  mov     rcx, [rsp+58h]; this
0x18045e95e  lea     r8, aShellcommonUnd_123; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18045e965  mov     edx, 19Fh; void *
0x18045e96a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
