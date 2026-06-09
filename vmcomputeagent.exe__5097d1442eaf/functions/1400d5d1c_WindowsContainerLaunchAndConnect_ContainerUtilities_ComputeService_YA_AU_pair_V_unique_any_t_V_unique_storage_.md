# ?WindowsContainerLaunchAndConnect@ContainerUtilities@ComputeService@@YA?AU?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_WC_CONTAINER_NOTIFICATION@@P6AJPEAU1@@_E$1?WcReleaseContainerTerminationNotification@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@@std@@PEAXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@4@AEBVCancellationToken@Management@2@_NP6AX0W4_WC_CONTAINER_TERMINATION_REASON@@PEAU_WC_CONTAINER_NOTIFICATION@@0@Z0@Z

- ea: `0x1400d5d1c`
- end: `0x1400d5f2b`
- name: `?WindowsContainerLaunchAndConnect@ContainerUtilities@ComputeService@@YA?AU?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_WC_CONTAINER_NOTIFICATION@@P6AJPEAU1@@_E$1?WcReleaseContainerTerminationNotification@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@@std@@PEAXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@4@AEBVCancellationToken@Management@2@_NP6AX0W4_WC_CONTAINER_TERMINATION_REASON@@PEAU_WC_CONTAINER_NOTIFICATION@@0@Z0@Z`
- size: `527`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14008dd70`
- `0x14009d780`

## callees

- `0x140005360`
- `0x140008760`
- `0x14000ea44`
- `0x14000ea60`
- `0x14004fc5c`
- `0x1400d4de0`
- `0x1400d5c40`
- `0x1400d5d1c`
- `0x1400e6a64`
- `0x1400e6b98`
- `0x1400f4eb8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d5e80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d5e80`
- `container!WcRegisterForContainerTerminationNotification` at `0x1400d5d80`
- `container!WcRegisterForContainerTerminationNotification` at `0x1400d5d80`
- `container!WcSetRegistryFlushState` at `0x1400d5e66`
- `container!WcSetRegistryFlushState` at `0x1400d5e66`
- `container!WcLaunchContainer` at `0x1400d5de7`
- `container!WcLaunchContainer` at `0x1400d5de7`

## string_xrefs

- `0x1400d5ec2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400d5eef`: `onecore\vm\compute\management\computeSystem\ComputeSystem.h`
- `0x1400d5ed7`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1400d5f04`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1400d5f19`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall ComputeService::ContainerUtilities::WindowsContainerLaunchAndConnect(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        ComputeService::Management::CancellationToken *a4,
        char a5)
{
  __int64 v8; // r8
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  _QWORD *v12; // rcx
  HANDLE v13; // rbx
  __int64 v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  int v17; // eax
  const char *v18; // r9
  int v20; // [rsp+20h] [rbp-61h]
  __int64 v21; // [rsp+30h] [rbp-51h] BYREF
  HANDLE hObject[4]; // [rsp+38h] [rbp-49h] BYREF
  char v23; // [rsp+58h] [rbp-29h]
  __int64 v24; // [rsp+60h] [rbp-21h] BYREF
  __int64 v25; // [rsp+68h] [rbp-19h] BYREF
  _QWORD Src[3]; // [rsp+70h] [rbp-11h] BYREF
  unsigned __int64 v27; // [rsp+88h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]

  v24 = a2;
  v25 = 0;
  v21 = 0;
  v8 = *(_QWORD *)(*(_QWORD *)a3 + 8LL);
  v25 = 0;
  v9 = WcRegisterForContainerTerminationNotification(
         a2,
         &ComputeService::ContainerUtilities::Details::ContainerTerminationCallback,
         v8 + 72,
         &v25);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x336,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
      (const char *)(unsigned int)v9,
      v20);
  v10 = _RTDynamicCast_0(
          *(_QWORD *)(*(_QWORD *)a3 + 8LL),
          0,
          &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
          &ComputeService::Management::BaseContainerState `RTTI Type Descriptor');
  if ( !v10 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computeSystem\\ComputeSystem.h",
      (const char *)0x80004001LL,
      0);
  if ( !*(_BYTE *)(v10 + 49) )
  {
    hObject[2] = &v24;
    hObject[3] = &v25;
    v23 = 1;
    v11 = WcLaunchContainer(v24, 0);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x344,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
        (const char *)(unsigned int)v11,
        0);
    ComputeService::ContainerUtilities::QueryContainerNamespacePath(Src, v24);
    hObject[0] = 0;
    v12 = Src;
    if ( v27 > 7 )
      v12 = (_QWORD *)Src[0];
    ContainerGetServiceStartEvent(v12, hObject);
    v13 = hObject[0];
    ComputeService::Management::CancellationToken::Wait(a4, hObject[0], 0x36EE80u);
    v14 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator&(&v21);
    v15 = Src;
    if ( v27 > 7 )
      v15 = (_QWORD *)Src[0];
    ContainerGetServiceBinding(v15, v14);
    if ( a5 )
    {
      LOBYTE(v16) = 1;
      v17 = WcSetRegistryFlushState(v24, v16);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x352,
          (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
          (const char *)(unsigned int)v17,
          0);
    }
    if ( v13 && !CloseHandle(v13) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v18);
    std::wstring::~wstring(Src);
  }
  *a1 = v25;
  a1[1] = v21;
  return a1;
}

```

## disassembly

```asm
0x1400d5d1c  push    rbp
0x1400d5d1e  push    rbx
0x1400d5d1f  push    rsi
0x1400d5d20  push    rdi
0x1400d5d21  lea     rbp, [rsp-27h]
0x1400d5d26  sub     rsp, 0A8h
0x1400d5d2d  mov     rax, cs:__security_cookie
0x1400d5d34  xor     rax, rsp
0x1400d5d37  mov     [rbp+3Fh+var_30], rax
0x1400d5d3b  mov     rsi, r9
0x1400d5d3e  mov     rbx, r8
0x1400d5d41  mov     r10, rdx
0x1400d5d44  mov     rdi, rcx
0x1400d5d47  mov     [rbp+3Fh+var_90], rcx
0x1400d5d4b  mov     [rbp+3Fh+var_60], rdx
0x1400d5d4f  mov     [rbp+3Fh+var_58], 0
0x1400d5d57  mov     [rbp+3Fh+var_90], 0
0x1400d5d5f  mov     rax, [r8]
0x1400d5d62  mov     r8, [rax+8]
0x1400d5d66  mov     [rbp+3Fh+var_58], 0
0x1400d5d6e  add     r8, 48h ; 'H'
0x1400d5d72  lea     r9, [rbp+3Fh+var_58]
0x1400d5d76  lea     rdx, ?ContainerTerminationCallback@Details@ContainerUtilities@ComputeService@@YAXPEAXW4_WC_CONTAINER_TERMINATION_REASON@@PEAU_WC_CONTAINER_NOTIFICATION@@0@Z; ComputeService::ContainerUtilities::Details::ContainerTerminationCallback(void *,_WC_CONTAINER_TERMINATION_REASON,_WC_CONTAINER_NOTIFICATION *,void *)
0x1400d5d7d  mov     rcx, r10
0x1400d5d80  call    cs:__imp_WcRegisterForContainerTerminationNotification
0x1400d5d86  mov     rcx, [rbp+47h]; this
0x1400d5d8a  test    eax, eax
0x1400d5d8c  js      loc_1400D5ED4
0x1400d5d92  mov     rcx, [rbx]
0x1400d5d95  mov     [rsp+0C0h+var_A0], 0; int
0x1400d5d9d  lea     r9, ??_R0?AUBaseContainerState@Management@ComputeService@@@8; ComputeService::Management::BaseContainerState `RTTI Type Descriptor'
0x1400d5da4  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x1400d5dab  xor     edx, edx
0x1400d5dad  mov     rcx, [rcx+8]
0x1400d5db1  call    __RTDynamicCast_0
0x1400d5db6  mov     rcx, [rbp+47h]; this
0x1400d5dba  test    rax, rax
0x1400d5dbd  jz      loc_1400D5EE9
0x1400d5dc3  cmp     byte ptr [rax+31h], 0
0x1400d5dc7  jnz     loc_1400D5E98
0x1400d5dcd  lea     rax, [rbp+3Fh+var_60]
0x1400d5dd1  mov     [rbp+3Fh+var_78], rax
0x1400d5dd5  lea     rax, [rbp+3Fh+var_58]
0x1400d5dd9  mov     [rbp+3Fh+var_70], rax
0x1400d5ddd  mov     [rbp+3Fh+var_68], 1
0x1400d5de1  xor     edx, edx
0x1400d5de3  mov     rcx, [rbp+3Fh+var_60]
0x1400d5de7  call    cs:__imp_WcLaunchContainer
0x1400d5ded  mov     rcx, [rbp+47h]; this
0x1400d5df1  test    eax, eax
0x1400d5df3  js      loc_1400D5F01
0x1400d5df9  mov     rdx, [rbp+3Fh+var_60]
0x1400d5dfd  lea     rcx, [rbp+3Fh+Src]; Src
0x1400d5e01  call    ?QueryContainerNamespacePath@ContainerUtilities@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; ComputeService::ContainerUtilities::QueryContainerNamespacePath(void *)
0x1400d5e06  nop
0x1400d5e07  mov     [rbp+3Fh+hObject], 0
0x1400d5e0f  lea     rcx, [rbp+3Fh+Src]
0x1400d5e13  cmp     [rbp+3Fh+var_38], 7
0x1400d5e18  cmova   rcx, [rbp+3Fh+Src]
0x1400d5e1d  lea     rdx, [rbp+3Fh+hObject]
0x1400d5e21  call    ContainerGetServiceStartEvent
0x1400d5e26  mov     r8d, 36EE80h; unsigned int
0x1400d5e2c  mov     rbx, [rbp+3Fh+hObject]
0x1400d5e30  mov     rdx, rbx; void *
0x1400d5e33  mov     rcx, rsi; this
0x1400d5e36  call    ?Wait@CancellationToken@Management@ComputeService@@QEBAXPEAXK@Z; ComputeService::Management::CancellationToken::Wait(void *,ulong)
0x1400d5e3b  lea     rcx, [rbp+3Fh+var_90]
0x1400d5e3f  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator&(void)
0x1400d5e44  lea     rcx, [rbp+3Fh+Src]
0x1400d5e48  cmp     [rbp+3Fh+var_38], 7
0x1400d5e4d  cmova   rcx, [rbp+3Fh+Src]
0x1400d5e52  mov     rdx, rax
0x1400d5e55  call    ContainerGetServiceBinding
0x1400d5e5a  cmp     [rbp+3Fh+arg_20], 0
0x1400d5e5e  jz      short loc_1400D5E78
0x1400d5e60  mov     dl, 1
0x1400d5e62  mov     rcx, [rbp+3Fh+var_60]
0x1400d5e66  call    cs:__imp_WcSetRegistryFlushState
0x1400d5e6c  mov     rcx, [rbp+47h]; this
0x1400d5e70  test    eax, eax
0x1400d5e72  js      loc_1400D5F16
0x1400d5e78  test    rbx, rbx
0x1400d5e7b  jz      short loc_1400D5E8E
0x1400d5e7d  mov     rcx, rbx; hObject
0x1400d5e80  call    cs:__imp_CloseHandle
0x1400d5e86  mov     rcx, [rbp+47h]; this
0x1400d5e8a  test    eax, eax
0x1400d5e8c  jz      short loc_1400D5EC2
0x1400d5e8e  lea     rcx, [rbp+3Fh+Src]; void *
0x1400d5e92  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400d5e97  nop
0x1400d5e98  mov     rcx, [rbp+3Fh+var_58]
0x1400d5e9c  mov     [rdi], rcx
0x1400d5e9f  mov     rcx, [rbp+3Fh+var_90]
0x1400d5ea3  mov     [rdi+8], rcx
0x1400d5ea7  mov     rax, rdi
0x1400d5eaa  mov     rcx, [rbp+3Fh+var_30]
0x1400d5eae  xor     rcx, rsp; StackCookie
0x1400d5eb1  call    __security_check_cookie
0x1400d5eb6  add     rsp, 0A8h
0x1400d5ebd  pop     rdi
0x1400d5ebe  pop     rsi
0x1400d5ebf  pop     rbx
0x1400d5ec0  pop     rbp
0x1400d5ec1  retn
0x1400d5ec2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400d5ec9  mov     edx, 0A0Bh; void *
0x1400d5ece  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400d5ed4  mov     r9d, eax; char *
0x1400d5ed7  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\management\\share"...
0x1400d5ede  mov     edx, 336h; void *
0x1400d5ee3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400d5ee9  mov     r9d, 80004001h; char *
0x1400d5eef  lea     r8, aOnecoreVmCompu_32; "onecore\\vm\\compute\\management\\compu"...
0x1400d5ef6  mov     edx, 5Dh ; ']'; void *
0x1400d5efb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400d5f01  mov     r9d, eax; char *
0x1400d5f04  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\management\\share"...
0x1400d5f0b  mov     edx, 344h; void *
0x1400d5f10  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400d5f16  mov     r9d, eax; char *
0x1400d5f19  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\management\\share"...
0x1400d5f20  mov     edx, 352h; void *
0x1400d5f25  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
