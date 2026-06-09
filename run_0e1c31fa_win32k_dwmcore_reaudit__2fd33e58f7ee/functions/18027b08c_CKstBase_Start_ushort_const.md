# CKstBase::Start(ushort const *)

- ea: `0x18027b08c`
- end: `0x18027b192`
- name: `?Start@CKstBase@@AEAAJPEBG@Z`
- size: `262`
- prototype: `__int64 __fastcall(CKstBase *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18027b028`

## callees

- `0x1800088dc`
- `0x180008934`
- `0x1800096c4`
- `0x18000a7f4`
- `0x180042854`
- `0x1801d4140`
- `0x18027b08c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18027b168`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18027b168`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18027b12e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18027b12e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18027b0c9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18027b0c9`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18027b120`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18027b120`

## string_xrefs

- `0x18027b119`: `DWM Kernel Sensor Thread`

## pseudocode

```c
__int64 __fastcall CKstBase::Start(CKstBase *this, const unsigned __int16 *a2)
{
  HANDLE *v3; // rsi
  char *v5; // rbx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v7; // edi
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HANDLE v10; // [rsp+40h] [rbp+8h] BYREF
  DWORD lpThreadId; // [rsp+48h] [rbp+10h] BYREF
  int v12; // [rsp+4Ch] [rbp+14h]

  v12 = HIDWORD(a2);
  lpThreadId = 0;
  v3 = (HANDLE *)((char *)this + 16);
  v10 = CreateThread(0, 0, CKstBase::RunKernelThreadStatic, this, 4u, &lpThreadId);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    v3,
    &v10);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v10);
  if ( *v3 )
  {
    SetThreadDescription(*v3, L"DWM Kernel Sensor Thread");
    SetThreadPriority(*v3, 16);
    v5 = (char *)this + 40;
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v5, 0);
    v7 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
    {
      ResumeThread(*v3);
      _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_NKH_Z(v5);
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        v5,
        0);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\input\\kstbase.cpp",
        (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
        dwCreationFlags);
      return v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\input\\kstbase.cpp",
      (const char *)0x8007000ELL,
      dwCreationFlags);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18027b08c  mov     rax, rsp
0x18027b08f  mov     [rax+18h], rbx
0x18027b093  mov     [rax+20h], rsi
0x18027b097  mov     [rax+10h], rdx
0x18027b09b  push    rdi
0x18027b09c  sub     rsp, 30h
0x18027b0a0  mov     dword ptr [rax+10h], 0
0x18027b0a7  lea     rax, [rax+10h]
0x18027b0ab  mov     rbx, rcx
0x18027b0ae  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18027b0b3  mov     r9, rcx; lpParameter
0x18027b0b6  mov     [rsp+38h+dwCreationFlags], 4; int
0x18027b0be  lea     r8, ?RunKernelThreadStatic@CKstBase@@CAKPEAX@Z; lpStartAddress
0x18027b0c5  xor     edx, edx; dwStackSize
0x18027b0c7  xor     ecx, ecx; lpThreadAttributes
0x18027b0c9  call    cs:__imp_CreateThread
0x18027b0cf  lea     rsi, [rbx+10h]
0x18027b0d3  mov     [rsp+38h+arg_0], rax
0x18027b0d8  mov     rcx, rsi
0x18027b0db  lea     rdx, [rsp+38h+arg_0]
0x18027b0e0  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18027b0e5  lea     rcx, [rsp+38h+arg_0]
0x18027b0ea  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18027b0ef  mov     rcx, [rsi]; hThread
0x18027b0f2  test    rcx, rcx
0x18027b0f5  jnz     short loc_18027B119
0x18027b0f7  mov     rcx, [rsp+38h]; this
0x18027b0fc  lea     r8, aOnecoreuapWind_65; "onecoreuap\\windows\\dwm\\dwmcore\\inpu"...
0x18027b103  mov     ebx, 8007000Eh
0x18027b108  mov     edx, 44h ; 'D'; void *
0x18027b10d  mov     r9d, ebx; char *
0x18027b110  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027b115  mov     eax, ebx
0x18027b117  jmp     short loc_18027B182
0x18027b119  lea     rdx, aDwmKernelSenso; "DWM Kernel Sensor Thread"
0x18027b120  call    cs:__imp_SetThreadDescription
0x18027b126  mov     rcx, [rsi]; hThread
0x18027b129  mov     edx, 10h; nPriority
0x18027b12e  call    cs:__imp_SetThreadPriority
0x18027b134  add     rbx, 28h ; '('
0x18027b138  xor     edx, edx
0x18027b13a  mov     rcx, rbx
0x18027b13d  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18027b142  mov     edi, eax
0x18027b144  test    eax, eax
0x18027b146  jns     short loc_18027B165
0x18027b148  mov     rcx, [rsp+38h]; this
0x18027b14d  lea     r8, aOnecoreuapWind_65; "onecoreuap\\windows\\dwm\\dwmcore\\inpu"...
0x18027b154  mov     r9d, eax; char *
0x18027b157  mov     edx, 52h ; 'R'; void *
0x18027b15c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027b161  mov     eax, edi
0x18027b163  jmp     short loc_18027B182
0x18027b165  mov     rcx, [rsi]; hThread
0x18027b168  call    cs:__imp_ResumeThread
0x18027b16e  mov     rcx, rbx
0x18027b171  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA_NKH@Z
0x18027b176  xor     edx, edx
0x18027b178  mov     rcx, rbx
0x18027b17b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18027b180  xor     eax, eax
0x18027b182  mov     rbx, [rsp+38h+arg_10]
0x18027b187  mov     rsi, [rsp+38h+arg_18]
0x18027b18c  add     rsp, 30h
0x18027b190  pop     rdi
0x18027b191  retn
```
