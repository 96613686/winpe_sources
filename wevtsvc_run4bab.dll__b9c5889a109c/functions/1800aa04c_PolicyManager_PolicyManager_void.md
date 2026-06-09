# PolicyManager::~PolicyManager(void)

- ea: `0x1800aa04c`
- end: `0x1800aa126`
- name: `??1PolicyManager@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(PolicyManager *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a1ea4`
- `0x1800d98d6`

## callees

- `0x18000bc0c`
- `0x18003435c`
- `0x1800660ac`
- `0x1800a9ef4`
- `0x1800a9f34`
- `0x1800a9f90`
- `0x1800aa04c`
- `0x1800aa42c`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800aa0a7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800aa0c0`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800aa0d9`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800aa0a7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800aa0c0`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800aa0d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800aa060`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800aa060`

## pseudocode

```c
void __fastcall PolicyManager::~PolicyManager(RTL_SRWLOCK *this)
{
  PVOID Ptr; // rcx
  PVOID v3; // rcx
  PVOID v4; // rcx
  PVOID v5; // rcx
  RTL_SRWLOCK *v6; // [rsp+20h] [rbp-38h] BYREF
  char v7; // [rsp+28h] [rbp-30h]

  v6 = this;
  AcquireSRWLockExclusive(this);
  v7 = 1;
  BYTE4(this[16].Ptr) = 1;
  utl::unique_lock<utl::shared_mutex>::unlock(&v6);
  Ptr = this[5].Ptr;
  this[5].Ptr = 0;
  if ( Ptr )
    PolicyManager::CloseGPNotification(Ptr);
  v3 = this[3].Ptr;
  this[3].Ptr = 0;
  if ( v3 )
    RtlUnsubscribeWnfNotificationWaitForCompletion(v3);
  v4 = this[4].Ptr;
  this[4].Ptr = 0;
  if ( v4 )
    RtlUnsubscribeWnfNotificationWaitForCompletion(v4);
  v5 = this[1].Ptr;
  this[1].Ptr = 0;
  if ( v5 )
    RtlUnsubscribeWnfNotificationWaitForCompletion(v5);
  utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(&v6);
  PolicyManager::ChannelPolicyCache::~ChannelPolicyCache((PolicyManager::ChannelPolicyCache *)&this[7]);
  tlx::unique_any<tlx::handle_traits<_TP_WAIT *,void (_TP_WAIT *),&void CloseThreadpoolWait(_TP_WAIT *),0>>::~unique_any<tlx::handle_traits<_TP_WAIT *,void (_TP_WAIT *),&void CloseThreadpoolWait(_TP_WAIT *),0>>(&this[6]);
  tlx::unique_any<tlx::handle_traits<void *,void (void *),&private: static void PolicyManager::CloseGPNotification(void *),0>>::~unique_any<tlx::handle_traits<void *,void (void *),&private: static void PolicyManager::CloseGPNotification(void *),0>>(&this[5]);
  tlx::unique_any<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&long RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>>::~unique_any<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&long RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>>(&this[4]);
  tlx::unique_any<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&long RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>>::~unique_any<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&long RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>>(&this[3]);
  tlx::unique_any<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&long RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>>::~unique_any<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&long RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>>(&this[1]);
}

```

## disassembly

```asm
0x1800aa04c  push    rbx
0x1800aa04e  push    rsi
0x1800aa04f  push    rdi
0x1800aa050  push    r14
0x1800aa052  push    r15
0x1800aa054  sub     rsp, 30h
0x1800aa058  mov     rbx, rcx
0x1800aa05b  mov     [rsp+58h+var_38], rcx
0x1800aa060  call    cs:__imp_AcquireSRWLockExclusive
0x1800aa066  lea     rcx, [rsp+58h+var_38]
0x1800aa06b  mov     [rsp+58h+var_30], 1
0x1800aa070  mov     byte ptr [rbx+84h], 1
0x1800aa077  call    ?unlock@?$unique_lock@Vshared_mutex@utl@@@utl@@QEAAXXZ; utl::unique_lock<utl::shared_mutex>::unlock(void)
0x1800aa07c  lea     r15, [rbx+28h]
0x1800aa080  mov     rcx, [r15]; void *
0x1800aa083  mov     qword ptr [r15], 0
0x1800aa08a  test    rcx, rcx
0x1800aa08d  jz      short loc_1800AA094
0x1800aa08f  call    ?CloseGPNotification@PolicyManager@@CAXPEAX@Z; PolicyManager::CloseGPNotification(void *)
0x1800aa094  lea     rdi, [rbx+18h]
0x1800aa098  mov     rcx, [rdi]
0x1800aa09b  mov     qword ptr [rdi], 0
0x1800aa0a2  test    rcx, rcx
0x1800aa0a5  jz      short loc_1800AA0AD
0x1800aa0a7  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800aa0ad  lea     rsi, [rbx+20h]
0x1800aa0b1  mov     rcx, [rsi]
0x1800aa0b4  mov     qword ptr [rsi], 0
0x1800aa0bb  test    rcx, rcx
0x1800aa0be  jz      short loc_1800AA0C6
0x1800aa0c0  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800aa0c6  lea     r14, [rbx+8]
0x1800aa0ca  mov     rcx, [r14]
0x1800aa0cd  mov     qword ptr [r14], 0
0x1800aa0d4  test    rcx, rcx
0x1800aa0d7  jz      short loc_1800AA0DF
0x1800aa0d9  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800aa0df  lea     rcx, [rsp+58h+var_38]
0x1800aa0e4  call    ??1?$unique_lock@Vshared_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(void)
0x1800aa0e9  lea     rcx, [rbx+38h]; this
0x1800aa0ed  call    ??1ChannelPolicyCache@PolicyManager@@QEAA@XZ; PolicyManager::ChannelPolicyCache::~ChannelPolicyCache(void)
0x1800aa0f2  lea     rcx, [rbx+30h]
0x1800aa0f6  call    ??1?$unique_any@U?$handle_traits@PEAU_TP_WAIT@@$$A6AXPEAU1@@Z$1?CloseThreadpoolWait@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<_TP_WAIT *,void (_TP_WAIT *),&CloseThreadpoolWait(_TP_WAIT *),0>>::~unique_any<tlx::handle_traits<_TP_WAIT *,void (_TP_WAIT *),&CloseThreadpoolWait(_TP_WAIT *),0>>(void)
0x1800aa0fb  mov     rcx, r15
0x1800aa0fe  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AXPEAX@Z$1?CloseGPNotification@PolicyManager@@CAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,void (void *),&PolicyManager::CloseGPNotification(void *),0>>::~unique_any<tlx::handle_traits<void *,void (void *),&PolicyManager::CloseGPNotification(void *),0>>(void)
0x1800aa103  mov     rcx, rsi
0x1800aa106  call    ??1?$unique_any@U?$handle_traits@PEAU_WNF_USER_SUBSCRIPTION@@$$A6AJPEAU1@@Z$1?RtlUnsubscribeWnfNotificationWaitForCompletion@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>>::~unique_any<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>>(void)
0x1800aa10b  mov     rcx, rdi
0x1800aa10e  call    ??1?$unique_any@U?$handle_traits@PEAU_WNF_USER_SUBSCRIPTION@@$$A6AJPEAU1@@Z$1?RtlUnsubscribeWnfNotificationWaitForCompletion@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>>::~unique_any<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>>(void)
0x1800aa113  mov     rcx, r14
0x1800aa116  add     rsp, 30h
0x1800aa11a  pop     r15
0x1800aa11c  pop     r14
0x1800aa11e  pop     rdi
0x1800aa11f  pop     rsi
0x1800aa120  pop     rbx
0x1800aa121  jmp     ??1?$unique_any@U?$handle_traits@PEAU_WNF_USER_SUBSCRIPTION@@$$A6AJPEAU1@@Z$1?RtlUnsubscribeWnfNotificationWaitForCompletion@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>>::~unique_any<tlx::handle_traits<_WNF_USER_SUBSCRIPTION *,long (_WNF_USER_SUBSCRIPTION *),&RtlUnsubscribeWnfNotificationWaitForCompletion(_WNF_USER_SUBSCRIPTION *),0>>(void)
```
