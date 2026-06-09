# ComputeService::Client::NotificationCallbacks::CleanupNotificationContext(ComputeService::Client::NotificationCallbacks::NotificationContext *)

- ea: `0x1800392c8`
- end: `0x18003934b`
- name: `?CleanupNotificationContext@NotificationCallbacks@Client@ComputeService@@CAXPEAUNotificationContext@123@@Z`
- size: `131`
- prototype: `void __fastcall(struct ComputeService::Client::NotificationCallbacks::NotificationContext *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180039290`
- `0x1800399dc`

## callees

- `0x180039e00`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800392e1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180039317`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800392e1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180039317`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800392f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003932b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800392f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003932b`

## pseudocode

```c
void __fastcall ComputeService::Client::NotificationCallbacks::CleanupNotificationContext(PTP_WAIT *a1)
{
  PTP_WAIT *v1; // rbx

  v1 = a1 + 5;
  WaitForThreadpoolWaitCallbacks(a1[5], 1);
  SetThreadpoolWait(*v1, 0, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    v1,
    0);
  WaitForThreadpoolWaitCallbacks(a1[7], 1);
  SetThreadpoolWait(a1[7], 0, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    a1 + 7,
    0);
}

```

## disassembly

```asm
0x1800392c8  mov     [rsp+arg_0], rbx
0x1800392cd  push    rdi
0x1800392ce  sub     rsp, 20h
0x1800392d2  lea     rbx, [rcx+28h]
0x1800392d6  mov     rdi, rcx
0x1800392d9  mov     rcx, [rbx]; pwa
0x1800392dc  mov     edx, 1; fCancelPendingCallbacks
0x1800392e1  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800392e8  nop     dword ptr [rax+rax+00h]
0x1800392ed  mov     rcx, [rbx]; pwa
0x1800392f0  xor     r8d, r8d; pftTimeout
0x1800392f3  xor     edx, edx; h
0x1800392f5  call    cs:__imp_SetThreadpoolWait
0x1800392fc  nop     dword ptr [rax+rax+00h]
0x180039301  xor     edx, edx
0x180039303  mov     rcx, rbx
0x180039306  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18003930b  lea     rbx, [rdi+38h]
0x18003930f  mov     edx, 1; fCancelPendingCallbacks
0x180039314  mov     rcx, [rbx]; pwa
0x180039317  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18003931e  nop     dword ptr [rax+rax+00h]
0x180039323  mov     rcx, [rbx]; pwa
0x180039326  xor     r8d, r8d; pftTimeout
0x180039329  xor     edx, edx; h
0x18003932b  call    cs:__imp_SetThreadpoolWait
0x180039332  nop     dword ptr [rax+rax+00h]
0x180039337  xor     edx, edx
0x180039339  mov     rcx, rbx
0x18003933c  mov     rbx, [rsp+28h+arg_0]
0x180039341  add     rsp, 20h
0x180039345  pop     rdi
0x180039346  jmp     ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
```
