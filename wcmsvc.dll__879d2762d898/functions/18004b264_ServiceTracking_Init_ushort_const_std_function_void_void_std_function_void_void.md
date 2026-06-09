# ServiceTracking::Init(ushort const *,std::function<void (void)> &&,std::function<void (void)> &&)

- ea: `0x18004b264`
- end: `0x18004b39e`
- name: `?Init@ServiceTracking@@QEAAJPEBG$$QEAV?$function@$$A6AXXZ@std@@1@Z`
- size: `314`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18009aa14`

## callees

- `0x180027250`
- `0x18004b264`
- `0x18006124c`
- `0x180061ddc`
- `0x18007039c`
- `0x18007397c`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004b37a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004b383`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004b37a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004b383`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004b2bd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004b2bd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004b281`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004b281`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18004b33a`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18004b33a`

## string_xrefs

- `0x18004b299`: `onecore\private\net\inc\ServiceTracking.h`
- `0x18004b2d5`: `onecore\private\net\inc\ServiceTracking.h`
- `0x18004b34c`: `onecore\private\net\inc\ServiceTracking.h`

## pseudocode

```c
__int64 __fastcall ServiceTracking::Init(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  SC_HANDLE v7; // rax
  const char *v8; // r9
  SC_HANDLE v9; // rbx
  SC_HANDLE v11; // rdi
  const char *v12; // r9
  unsigned int LastError; // ebx
  unsigned int v14; // eax
  unsigned int v15; // ebx
  SC_HANDLE v16; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v17[6]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v7 = OpenSCManagerW(0, 0, 1u);
  v9 = v7;
  v17[0] = v7;
  if ( !v7 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x16,
             (unsigned int)"onecore\\private\\net\\inc\\ServiceTracking.h",
             v8);
  v11 = OpenServiceW(v7, L"nsi", 4u);
  v16 = v11;
  if ( v11 )
  {
    std::function<void (void)>::operator=(a1 + 8, a3);
    std::function<void (void)>::operator=(a1 + 72, a4);
    wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&void UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(
      a1,
      0);
    v14 = SubscribeServiceChangeNotifications(
            v11,
            2,
            `ServiceTracking::Init'::`15'::_lambda_1_::_lambda_invoker_cdecl_,
            a1);
    if ( v14 )
    {
      v15 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x37,
              (unsigned int)"onecore\\private\\net\\inc\\ServiceTracking.h",
              (const char *)v14,
              a1);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v16);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v17);
      return v15;
    }
    else
    {
      CloseServiceHandle(v11);
      CloseServiceHandle(v9);
      return 0;
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x19,
                  (unsigned int)"onecore\\private\\net\\inc\\ServiceTracking.h",
                  v12);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v16);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v17);
    return LastError;
  }
}

```

## disassembly

```asm
0x18004b264  push    rbx
0x18004b266  push    rsi
0x18004b267  push    rdi
0x18004b268  push    r14
0x18004b26a  push    r15
0x18004b26c  sub     rsp, 40h
0x18004b270  mov     r15, r9
0x18004b273  mov     r14, r8
0x18004b276  mov     rsi, rcx
0x18004b279  xor     edx, edx; lpDatabaseName
0x18004b27b  xor     ecx, ecx; lpMachineName
0x18004b27d  lea     r8d, [rdx+1]; dwDesiredAccess
0x18004b281  call    cs:__imp_OpenSCManagerW
0x18004b287  mov     rbx, rax
0x18004b28a  mov     [rsp+68h+var_30], rax
0x18004b28f  test    rax, rax
0x18004b292  jnz     short loc_18004B2AD
0x18004b294  mov     rcx, [rsp+68h]; this
0x18004b299  lea     r8, aOnecorePrivate_2; "onecore\\private\\net\\inc\\ServiceTrac"...
0x18004b2a0  lea     edx, [rax+16h]; void *
0x18004b2a3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004b2a8  jmp     loc_18004B391
0x18004b2ad  mov     r8d, 4; dwDesiredAccess
0x18004b2b3  lea     rdx, ServiceName; "nsi"
0x18004b2ba  mov     rcx, rbx; hSCManager
0x18004b2bd  call    cs:__imp_OpenServiceW
0x18004b2c3  mov     rdi, rax
0x18004b2c6  mov     [rsp+68h+var_38], rax
0x18004b2cb  test    rax, rax
0x18004b2ce  jnz     short loc_18004B301
0x18004b2d0  mov     rcx, [rsp+68h]; this
0x18004b2d5  lea     r8, aOnecorePrivate_2; "onecore\\private\\net\\inc\\ServiceTrac"...
0x18004b2dc  lea     edx, [rax+19h]; void *
0x18004b2df  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004b2e4  mov     ebx, eax
0x18004b2e6  lea     rcx, [rsp+68h+var_38]
0x18004b2eb  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18004b2f0  lea     rcx, [rsp+68h+var_30]
0x18004b2f5  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18004b2fa  mov     eax, ebx
0x18004b2fc  jmp     loc_18004B391
0x18004b301  lea     rcx, [rsi+8]
0x18004b305  mov     rdx, r14
0x18004b308  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x18004b30d  lea     rcx, [rsi+48h]
0x18004b311  mov     rdx, r15
0x18004b314  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x18004b319  xor     edx, edx
0x18004b31b  mov     rcx, rsi
0x18004b31e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SC_NOTIFICATION_REGISTRATION@@P6AXPEAU1@@Z$1?UnsubscribeServiceChangeNotifications@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SC_NOTIFICATION_REGISTRATION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(_SC_NOTIFICATION_REGISTRATION *)
0x18004b323  mov     qword ptr [rsp+68h+var_48], rsi; unsigned int
0x18004b328  mov     r9, rsi
0x18004b32b  lea     r8, ?_lambda_invoker_cdecl_@_lambda_1_@?P@??Init@ServiceTracking@@QEAAJPEBG$$QEAV?$function@$$A6AXXZ@std@@1@Z@SA@KPEAX@Z; `ServiceTracking::Init(ushort const *,std::function<void (void)> &&,std::function<void (void)> &&)'::`15'::_lambda_1_::_lambda_invoker_cdecl_(ulong,void *)
0x18004b332  mov     edx, 2
0x18004b337  mov     rcx, rdi
0x18004b33a  call    cs:__imp_SubscribeServiceChangeNotifications
0x18004b340  test    eax, eax
0x18004b342  jz      short loc_18004B377
0x18004b344  mov     rcx, [rsp+68h]; this
0x18004b349  mov     r9d, eax; char *
0x18004b34c  lea     r8, aOnecorePrivate_2; "onecore\\private\\net\\inc\\ServiceTrac"...
0x18004b353  mov     edx, 37h ; '7'; void *
0x18004b358  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004b35d  mov     ebx, eax
0x18004b35f  lea     rcx, [rsp+68h+var_38]
0x18004b364  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18004b369  lea     rcx, [rsp+68h+var_30]
0x18004b36e  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18004b373  mov     eax, ebx
0x18004b375  jmp     short loc_18004B391
0x18004b377  mov     rcx, rdi; hSCObject
0x18004b37a  call    cs:__imp_CloseServiceHandle
0x18004b380  mov     rcx, rbx; hSCObject
0x18004b383  call    cs:__imp_CloseServiceHandle
0x18004b389  xor     eax, eax
0x18004b38b  jmp     short loc_18004B391
0x18004b38d  mov     eax, dword ptr [rsp+68h+var_38]
0x18004b391  add     rsp, 40h
0x18004b395  pop     r15
0x18004b397  pop     r14
0x18004b399  pop     rdi
0x18004b39a  pop     rsi
0x18004b39b  pop     rbx
0x18004b39c  retn
```
