# ChannelNotificationContext::~ChannelNotificationContext(void)

- ea: `0x180004094`
- end: `0x1800040dd`
- name: `??1ChannelNotificationContext@@QEAA@XZ`
- size: `73`
- prototype: `void __fastcall(ChannelNotificationContext *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006e78`

## callees

- `0x180003fe0`
- `0x180004014`
- `0x180004074`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800040a4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800040c9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800040a4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800040c9`

## pseudocode

```c
void __fastcall ChannelNotificationContext::~ChannelNotificationContext(ChannelNotificationContext *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 17);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>((char *)this + 672);
  wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::~unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>((char *)this + 656);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 616));
  wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>((char *)this + 8);
}

```

## disassembly

```asm
0x180004094  push    rbx
0x180004096  sub     rsp, 20h
0x18000409a  mov     rbx, rcx
0x18000409d  add     rcx, 2A8h; lpCriticalSection
0x1800040a4  call    cs:__imp_DeleteCriticalSection
0x1800040aa  lea     rcx, [rbx+2A0h]
0x1800040b1  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x1800040b6  lea     rcx, [rbx+290h]
0x1800040bd  call    ??1?$unique_ptr@UChannelNotificationContext@@U?$default_delete@UChannelNotificationContext@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::~unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>(void)
0x1800040c2  lea     rcx, [rbx+268h]; lpCriticalSection
0x1800040c9  call    cs:__imp_DeleteCriticalSection
0x1800040cf  lea     rcx, [rbx+8]
0x1800040d3  add     rsp, 20h
0x1800040d7  pop     rbx
0x1800040d8  jmp     ??1?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>(void)
```
