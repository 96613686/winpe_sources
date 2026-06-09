# DllMain

- ea: `0x180019ae8`
- end: `0x180019d17`
- name: `DllMain`
- size: `559`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180053174`

## callees

- `0x180019ae8`
- `0x180019d20`
- `0x180019d4c`
- `0x180019ddc`
- `0x18002c30c`
- `0x18002cf04`
- `0x18002eb70`
- `0x180031c20`
- `0x180049be8`
- `0x180053300`
- `0x180053d3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019c49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019c49`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180019bc5`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180019bc5`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180019cfa`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180019cfa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019c68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019c68`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180019b8c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180019b8c`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180019bb2`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180019bb2`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v5; // rdx
  __int64 v6; // rdx
  DWORD CurrentProcessId; // eax
  const struct wil::FailureInfo *v8; // rdx
  _BYTE v9[160]; // [rsp+30h] [rbp-2C8h] BYREF
  WCHAR Filename[264]; // [rsp+D0h] [rbp-228h] BYREF

  if ( fdwReason == 1 )
  {
    qword_1800DE740 = 1;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_InfraTracingGuid;
    qword_1800DE738 = 0;
    WPP_GLOBAL_Control = (wchar_t *)&WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    WppInitUm(hinstDLL, fdwReason, lpvReserved);
    GetModuleFileNameW(0, Filename, 0x104u);
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      CurrentProcessId = GetCurrentProcessId();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_cd3774252c5c3693a3c8a9662b2dc847_Traceguids,
        CurrentProcessId,
        (__int64)Filename);
    }
    DisableThreadLibraryCalls(hinstDLL);
    g_hWerheap = HeapCreate(0, 0, 0);
    if ( g_hWerheap )
    {
      byte_1800DE758 = 1;
    }
    else
    {
      byte_1800DE758 = 0;
      g_hWerheap = GetProcessHeap();
    }
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1800DE000);
    McGenEventRegister_EventRegister(
      EventProviderWindows_Error_Reporting,
      v5,
      EventProviderWindows_Error_Reporting_Context,
      EventProviderWindows_Error_Reporting_Context);
    McGenEventRegister_EventRegister(
      S_MICROSOFT_WINDOWS_WER_PAYLOAD_HEALTH,
      v6,
      S_MICROSOFT_WINDOWS_WER_PAYLOAD_HEALTH_Context,
      S_MICROSOFT_WINDOWS_WER_PAYLOAD_HEALTH_Context);
    if ( wil::details::g_pfnLoggingCallback
      && (void (__fastcall *)(const struct wil::FailureInfo *))wil::details::g_pfnLoggingCallback != ResultLoggingCallback )
    {
      memset_0(v9, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v9, v8);
    }
    wil::details::g_pfnLoggingCallback = (__int64)ResultLoggingCallback;
  }
  else if ( !fdwReason )
  {
    TraceLoggingUnregister_EventUnregister(&dword_1800DE000, fdwReason, lpvReserved);
    McGenEventUnregister_EventUnregister(EventProviderWindows_Error_Reporting_Context);
    McGenEventUnregister_EventUnregister(S_MICROSOFT_WINDOWS_WER_PAYLOAD_HEALTH_Context);
    if ( byte_1800DE758 )
      HeapDestroy(g_hWerheap);
    g_hWerheap = 0;
    WppCleanupUm();
  }
  return 1;
}

```

## disassembly

```asm
0x180019ae8  mov     [rsp+arg_8], rbx
0x180019aed  push    rdi
0x180019aee  sub     rsp, 2F0h
0x180019af5  mov     rax, cs:__security_cookie
0x180019afc  xor     rax, rsp
0x180019aff  mov     [rsp+2F8h+var_18], rax
0x180019b07  mov     rdi, rcx
0x180019b0a  cmp     edx, 1
0x180019b0d  jz      short loc_180019B40
0x180019b0f  xor     ebx, ebx
0x180019b11  test    edx, edx
0x180019b13  jz      loc_180019CC7
0x180019b19  mov     eax, 1
0x180019b1e  mov     rcx, [rsp+2F8h+var_18]
0x180019b26  xor     rcx, rsp; StackCookie
0x180019b29  call    __security_check_cookie
0x180019b2e  mov     rbx, [rsp+2F8h+arg_8]
0x180019b36  add     rsp, 2F0h
0x180019b3d  pop     rdi
0x180019b3e  retn
0x180019b40  lea     rax, WPP_ThisDir_CTLGUID_InfraTracingGuid
0x180019b47  mov     cs:qword_1800DE740, 1
0x180019b52  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180019b59  xor     ebx, ebx
0x180019b5b  lea     rax, WPP_MAIN_CB
0x180019b62  mov     cs:qword_1800DE738, rbx
0x180019b69  mov     cs:WPP_GLOBAL_Control, rax
0x180019b70  mov     cs:WPP_MAIN_CB, rbx
0x180019b77  call    WppInitUm
0x180019b7c  mov     r8d, 104h; nSize
0x180019b82  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x180019b8a  xor     ecx, ecx; hModule
0x180019b8c  call    cs:__imp_GetModuleFileNameW
0x180019b93  nop     dword ptr [rax+rax+00h]
0x180019b98  mov     rax, cs:WPP_GLOBAL_Control
0x180019b9f  lea     rcx, WPP_GLOBAL_Control
0x180019ba6  cmp     rax, rcx
0x180019ba9  jnz     loc_180019C5E
0x180019baf  mov     rcx, rdi; hLibModule
0x180019bb2  call    cs:__imp_DisableThreadLibraryCalls
0x180019bb9  nop     dword ptr [rax+rax+00h]
0x180019bbe  xor     r8d, r8d; dwMaximumSize
0x180019bc1  xor     edx, edx; dwInitialSize
0x180019bc3  xor     ecx, ecx; flOptions
0x180019bc5  call    cs:__imp_HeapCreate
0x180019bcc  nop     dword ptr [rax+rax+00h]
0x180019bd1  mov     cs:?g_hWerheap@@3PEAXEA, rax; void * g_hWerheap
0x180019bd8  test    rax, rax
0x180019bdb  jz      short loc_180019C43
0x180019bdd  mov     cs:byte_1800DE758, 1
0x180019be4  lea     rcx, dword_1800DE000; CallbackContext
0x180019beb  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180019bf0  lea     r9, EventProviderWindows_Error_Reporting_Context
0x180019bf7  lea     r8, EventProviderWindows_Error_Reporting_Context
0x180019bfe  lea     rcx, EventProviderWindows_Error_Reporting
0x180019c05  call    McGenEventRegister_EventRegister
0x180019c0a  lea     r9, S_MICROSOFT_WINDOWS_WER_PAYLOAD_HEALTH_Context
0x180019c11  lea     r8, S_MICROSOFT_WINDOWS_WER_PAYLOAD_HEALTH_Context
0x180019c18  lea     rcx, S_MICROSOFT_WINDOWS_WER_PAYLOAD_HEALTH
0x180019c1f  call    McGenEventRegister_EventRegister
0x180019c24  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180019c2b  lea     rcx, ?ResultLoggingCallback@@YAXAEBUFailureInfo@wil@@@Z; ResultLoggingCallback(wil::FailureInfo const &)
0x180019c32  test    rax, rax
0x180019c35  jnz     short loc_180019CA5
0x180019c37  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x180019c3e  jmp     loc_180019B19
0x180019c43  mov     cs:byte_1800DE758, bl
0x180019c49  call    cs:__imp_GetProcessHeap
0x180019c50  nop     dword ptr [rax+rax+00h]
0x180019c55  mov     cs:?g_hWerheap@@3PEAXEA, rax; void * g_hWerheap
0x180019c5c  jmp     short loc_180019BE4
0x180019c5e  test    byte ptr [rax+1Ch], 4
0x180019c62  jz      loc_180019BAF
0x180019c68  call    cs:__imp_GetCurrentProcessId
0x180019c6f  nop     dword ptr [rax+rax+00h]
0x180019c74  lea     rcx, [rsp+2F8h+Filename]
0x180019c7c  mov     edx, 0Bh
0x180019c81  mov     [rsp+2F8h+var_2D8], rcx
0x180019c86  lea     r8, WPP_cd3774252c5c3693a3c8a9662b2dc847_Traceguids
0x180019c8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c94  mov     r9d, eax
0x180019c97  mov     rcx, [rcx+10h]
0x180019c9b  call    WPP_SF_DS
0x180019ca0  jmp     loc_180019BAF
0x180019ca5  cmp     rax, rcx
0x180019ca8  jz      short loc_180019C37
0x180019caa  xor     edx, edx; Val
0x180019cac  lea     rcx, [rsp+2F8h+var_2C8]; void *
0x180019cb1  mov     r8d, 98h; Size
0x180019cb7  call    memset_0
0x180019cbc  lea     rcx, [rsp+2F8h+var_2C8]; this
0x180019cc1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180019cc7  lea     rcx, dword_1800DE000
0x180019cce  call    TraceLoggingUnregister_EventUnregister
0x180019cd3  lea     rcx, EventProviderWindows_Error_Reporting_Context
0x180019cda  call    McGenEventUnregister_EventUnregister
0x180019cdf  lea     rcx, S_MICROSOFT_WINDOWS_WER_PAYLOAD_HEALTH_Context
0x180019ce6  call    McGenEventUnregister_EventUnregister
0x180019ceb  cmp     cs:byte_1800DE758, bl
0x180019cf1  jz      short loc_180019D06
0x180019cf3  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180019cfa  call    cs:__imp_HeapDestroy
0x180019d01  nop     dword ptr [rax+rax+00h]
0x180019d06  mov     cs:?g_hWerheap@@3PEAXEA, rbx; void * g_hWerheap
0x180019d0d  call    WppCleanupUm
0x180019d12  jmp     loc_180019B19
```
