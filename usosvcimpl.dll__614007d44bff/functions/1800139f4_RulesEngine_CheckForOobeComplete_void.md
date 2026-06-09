# RulesEngine::CheckForOobeComplete(void)

- ea: `0x1800139f4`
- end: `0x180013bc9`
- name: `?CheckForOobeComplete@RulesEngine@@AEAAXXZ`
- size: `469`
- prototype: `void __fastcall(RulesEngine *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180013d84`

## callees

- `0x180012b10`
- `0x180012f38`
- `0x1800139f4`
- `0x18001afb8`
- `0x18001c2b0`
- `0x18002e168`
- `0x18006ea28`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b6e`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x180013a1c`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x180013a1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall RulesEngine::CheckForOobeComplete(RulesEngine *this)
{
  int v2; // esi
  __int64 *System; // rax
  _QWORD *v4; // rax
  char v5; // di
  volatile signed __int32 *v6; // rbx
  volatile signed __int32 *v7; // rbx
  _QWORD *v8; // rax
  signed int LastError; // eax
  unsigned __int64 v10; // r9
  void (__fastcall ***v11)(_QWORD, __int64); // [rsp+20h] [rbp-B8h] BYREF
  volatile signed __int32 *v12; // [rsp+28h] [rbp-B0h]
  __int64 v13; // [rsp+30h] [rbp-A8h] BYREF
  volatile signed __int32 *v14; // [rsp+38h] [rbp-A0h]
  _BYTE v15[8]; // [rsp+40h] [rbp-98h] BYREF
  __int64 (__fastcall **v16)(); // [rsp+48h] [rbp-90h] BYREF
  __int64 (__fastcall ***v17)(); // [rsp+B0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v2 = RegisterWaitUntilOOBECompleted(anonymous_namespace_::OobeCompleteCallback, 0, &qword_1801500D8);
  System = SystemInterface::Service::GetSystem(&v13);
  v4 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)*System + 64LL))(*System, &v11);
  v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 72LL))(*v4);
  v6 = v12;
  if ( v12 )
  {
    if ( !_InterlockedDecrement(v12 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( !_InterlockedDecrement(v6 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  v7 = v14;
  if ( v14 )
  {
    if ( !_InterlockedDecrement(v14 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( !_InterlockedDecrement(v7 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  if ( !v2 )
  {
    LastError = GetLastError();
    if ( LastError != 5023 && LastError != 50 )
    {
      v10 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v10 = (unsigned int)LastError;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x128,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
        (const char *)v10,
        (int)v11);
    }
    goto LABEL_21;
  }
  if ( v5 )
  {
LABEL_21:
    anonymous_namespace_::OobeCompleteCallback(0);
    return;
  }
  if ( (unsigned __int8)anonymous_namespace_::IsFirstRunConfigurationNeeded() )
  {
    v16 = off_1800F5F70;
    v17 = &v16;
    v8 = wil::make_wnf_subscription_nothrow<wil::details::empty_wnf_state>(
           &v11,
           (__int64)&WNF_DEP_OOBE_COMPLETE,
           (__int64)v15,
           0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
      (char *)this + 16,
      v8);
    if ( v11 )
      (**v11)(v11, 1);
    if ( v17 )
      ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v17)[3])(v17);
  }
}

```

## disassembly

```asm
0x1800139f4  mov     [rsp+arg_8], rbx
0x1800139f9  mov     [rsp+arg_10], rbp
0x1800139fe  push    rsi
0x1800139ff  push    rdi
0x180013a00  push    r14
0x180013a02  sub     rsp, 0C0h
0x180013a09  mov     rbp, rcx
0x180013a0c  lea     r8, qword_1801500D8
0x180013a13  xor     edx, edx
0x180013a15  lea     rcx, _anonymous_namespace___OobeCompleteCallback
0x180013a1c  call    cs:__imp_RegisterWaitUntilOOBECompleted
0x180013a22  mov     esi, eax
0x180013a24  lea     rcx, [rsp+0D8h+var_A8]
0x180013a29  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180013a2e  nop
0x180013a2f  mov     rcx, [rax]
0x180013a32  mov     rdx, [rcx]
0x180013a35  mov     rax, [rdx+40h]
0x180013a39  lea     rdx, [rsp+0D8h+var_B8]
0x180013a3e  call    _guard_dispatch_icall
0x180013a43  nop
0x180013a44  mov     rcx, [rax]
0x180013a47  mov     rax, [rcx]
0x180013a4a  mov     rax, [rax+48h]
0x180013a4e  call    _guard_dispatch_icall
0x180013a53  mov     dil, al
0x180013a56  or      r14d, 0FFFFFFFFh
0x180013a5a  mov     rbx, [rsp+0D8h+var_B0]
0x180013a5f  test    rbx, rbx
0x180013a62  jz      short loc_180013A9C
0x180013a64  mov     ecx, r14d
0x180013a67  lock xadd [rbx+8], ecx
0x180013a6c  add     ecx, r14d
0x180013a6f  jnz     short loc_180013A9C
0x180013a71  mov     rax, [rbx]
0x180013a74  mov     rcx, rbx
0x180013a77  mov     rax, [rax]
0x180013a7a  call    _guard_dispatch_icall
0x180013a7f  mov     eax, r14d
0x180013a82  lock xadd [rbx+0Ch], eax
0x180013a87  add     eax, r14d
0x180013a8a  jnz     short loc_180013A9C
0x180013a8c  mov     rax, [rbx]
0x180013a8f  mov     rcx, rbx
0x180013a92  mov     rax, [rax+8]
0x180013a96  call    _guard_dispatch_icall
0x180013a9b  nop
0x180013a9c  mov     rbx, [rsp+0D8h+var_A0]
0x180013aa1  test    rbx, rbx
0x180013aa4  jz      short loc_180013ADD
0x180013aa6  mov     eax, r14d
0x180013aa9  lock xadd [rbx+8], eax
0x180013aae  add     eax, r14d
0x180013ab1  jnz     short loc_180013ADD
0x180013ab3  mov     rax, [rbx]
0x180013ab6  mov     rcx, rbx
0x180013ab9  mov     rax, [rax]
0x180013abc  call    _guard_dispatch_icall
0x180013ac1  mov     eax, r14d
0x180013ac4  lock xadd [rbx+0Ch], eax
0x180013ac9  add     eax, r14d
0x180013acc  jnz     short loc_180013ADD
0x180013ace  mov     rax, [rbx]
0x180013ad1  mov     rcx, rbx
0x180013ad4  mov     rax, [rax+8]
0x180013ad8  call    _guard_dispatch_icall
0x180013add  test    esi, esi
0x180013adf  jz      loc_180013B6E
0x180013ae5  test    dil, dil
0x180013ae8  jnz     loc_180013BAA
0x180013aee  call    _anonymous_namespace___IsFirstRunConfigurationNeeded
0x180013af3  test    al, al
0x180013af5  jz      loc_180013BB1
0x180013afb  lea     rax, off_1800F5F70
0x180013b02  mov     [rsp+0D8h+var_90], rax
0x180013b07  lea     rax, [rsp+0D8h+var_90]
0x180013b0c  mov     [rsp+0D8h+var_28], rax
0x180013b14  xor     r9d, r9d
0x180013b17  lea     r8, [rsp+0D8h+var_98]
0x180013b1c  lea     rdx, WNF_DEP_OOBE_COMPLETE
0x180013b23  lea     rcx, [rsp+0D8h+var_B8]
0x180013b28  call    ??$make_wnf_subscription_nothrow@Uempty_wnf_state@details@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@K@Z; wil::make_wnf_subscription_nothrow<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong)
0x180013b2d  lea     rcx, [rbp+10h]
0x180013b31  mov     rdx, rax
0x180013b34  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x180013b39  mov     rcx, [rsp+0D8h+var_B8]
0x180013b3e  test    rcx, rcx
0x180013b41  jz      short loc_180013B53
0x180013b43  mov     rax, [rcx]
0x180013b46  mov     edx, 1
0x180013b4b  mov     rax, [rax]
0x180013b4e  call    _guard_dispatch_icall
0x180013b53  mov     rcx, [rsp+0D8h+var_28]
0x180013b5b  test    rcx, rcx
0x180013b5e  jz      short loc_180013BB1
0x180013b60  mov     rax, [rcx]
0x180013b63  mov     rax, [rax+18h]
0x180013b67  call    _guard_dispatch_icall
0x180013b6c  jmp     short loc_180013BB1
0x180013b6e  call    cs:__imp_GetLastError
0x180013b74  cmp     eax, 139Fh
0x180013b79  jz      short loc_180013BAA
0x180013b7b  cmp     eax, 32h ; '2'
0x180013b7e  jz      short loc_180013BAA
0x180013b80  movzx   r9d, ax
0x180013b84  or      r9d, 80070000h
0x180013b8b  test    eax, eax
0x180013b8d  cmovle  r9d, eax; char *
0x180013b91  mov     rcx, [rsp+0D8h]; this
0x180013b99  lea     r8, aCW1SSrcOrchest_42; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180013ba0  mov     edx, 128h; void *
0x180013ba5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180013baa  xor     ecx, ecx
0x180013bac  call    _anonymous_namespace___OobeCompleteCallback
0x180013bb1  lea     r11, [rsp+0D8h+var_18]
0x180013bb9  mov     rbx, [r11+28h]
0x180013bbd  mov     rbp, [r11+30h]
0x180013bc1  mov     rsp, r11
0x180013bc4  pop     r14
0x180013bc6  pop     rdi
0x180013bc7  pop     rsi
0x180013bc8  retn
```
