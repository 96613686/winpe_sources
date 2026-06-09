# ServiceWorkerStorageClient::~ServiceWorkerStorageClient(void)

- ea: `0x180066a5c`
- end: `0x180066ad2`
- name: `??1ServiceWorkerStorageClient@@UEAA@XZ`
- size: `118`
- prototype: `void __fastcall(ServiceWorkerStorageClient *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009b980`

## callees

- `0x18000e1c0`
- `0x18001c800`
- `0x180032a04`
- `0x180065350`
- `0x180066a5c`
- `0x180066ad8`
- `0x180066b40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066a82`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066ab8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066a82`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066ab8`

## pseudocode

```c
void __fastcall ServiceWorkerStorageClient::~ServiceWorkerStorageClient(ServiceWorkerStorageClient *this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx

  *(_QWORD *)this = &ServiceWorkerStorageClient::`vftable';
  std::_Hash<std::_Uset_traits<std::shared_ptr<ServiceWorkerStorageSession>,std::_Uhash_compare<std::shared_ptr<ServiceWorkerStorageSession>,std::hash<std::shared_ptr<ServiceWorkerStorageSession>>,std::equal_to<std::shared_ptr<ServiceWorkerStorageSession>>>,std::allocator<std::shared_ptr<ServiceWorkerStorageSession>>,0>>::~_Hash<std::_Uset_traits<std::shared_ptr<ServiceWorkerStorageSession>,std::_Uhash_compare<std::shared_ptr<ServiceWorkerStorageSession>,std::hash<std::shared_ptr<ServiceWorkerStorageSession>>,std::equal_to<std::shared_ptr<ServiceWorkerStorageSession>>>,std::allocator<std::shared_ptr<ServiceWorkerStorageSession>>,0>>((char *)this + 296);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 256));
  ActiveReferenceList<ServiceWorkerRegistrationActiveReference>::~ActiveReferenceList<ServiceWorkerRegistrationActiveReference>((LPCRITICAL_SECTION)((char *)this + 168));
  ServiceWorkerDeleteQueue::~ServiceWorkerDeleteQueue((ServiceWorkerStorageClient *)((char *)this + 120));
  std::wstring::~wstring((char *)this + 88);
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 10);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 2);
  if ( v3 )
    std::_Ref_count_base::_Decwref(v3);
}

```

## disassembly

```asm
0x180066a5c  push    rbx
0x180066a5e  sub     rsp, 20h
0x180066a62  lea     rax, ??_7ServiceWorkerStorageClient@@6B@; const ServiceWorkerStorageClient::`vftable'
0x180066a69  mov     rbx, rcx
0x180066a6c  mov     [rcx], rax
0x180066a6f  add     rcx, 128h
0x180066a76  call    ??1?$_Hash@V?$_Uset_traits@V?$shared_ptr@VServiceWorkerStorageSession@@@std@@V?$_Uhash_compare@V?$shared_ptr@VServiceWorkerStorageSession@@@std@@U?$hash@V?$shared_ptr@VServiceWorkerStorageSession@@@std@@@2@U?$equal_to@V?$shared_ptr@VServiceWorkerStorageSession@@@std@@@2@@2@V?$allocator@V?$shared_ptr@VServiceWorkerStorageSession@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::shared_ptr<ServiceWorkerStorageSession>,std::_Uhash_compare<std::shared_ptr<ServiceWorkerStorageSession>,std::hash<std::shared_ptr<ServiceWorkerStorageSession>>,std::equal_to<std::shared_ptr<ServiceWorkerStorageSession>>>,std::allocator<std::shared_ptr<ServiceWorkerStorageSession>>,0>>::~_Hash<std::_Uset_traits<std::shared_ptr<ServiceWorkerStorageSession>,std::_Uhash_compare<std::shared_ptr<ServiceWorkerStorageSession>,std::hash<std::shared_ptr<ServiceWorkerStorageSession>>,std::equal_to<std::shared_ptr<ServiceWorkerStorageSession>>>,std::allocator<std::shared_ptr<ServiceWorkerStorageSession>>,0>>(void)
0x180066a7b  lea     rcx, [rbx+100h]; lpCriticalSection
0x180066a82  call    cs:__imp_DeleteCriticalSection
0x180066a88  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x180066a8f  call    ??1?$ActiveReferenceList@VServiceWorkerRegistrationActiveReference@@@@QEAA@XZ; ActiveReferenceList<ServiceWorkerRegistrationActiveReference>::~ActiveReferenceList<ServiceWorkerRegistrationActiveReference>(void)
0x180066a94  lea     rcx, [rbx+78h]; this
0x180066a98  call    ??1ServiceWorkerDeleteQueue@@QEAA@XZ; ServiceWorkerDeleteQueue::~ServiceWorkerDeleteQueue(void)
0x180066a9d  lea     rcx, [rbx+58h]; void *
0x180066aa1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180066aa6  mov     rcx, [rbx+50h]; this
0x180066aaa  test    rcx, rcx
0x180066aad  jz      short loc_180066AB4
0x180066aaf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180066ab4  lea     rcx, [rbx+18h]; lpCriticalSection
0x180066ab8  call    cs:__imp_DeleteCriticalSection
0x180066abe  mov     rcx, [rbx+10h]; this
0x180066ac2  test    rcx, rcx
0x180066ac5  jz      short loc_180066ACC
0x180066ac7  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180066acc  add     rsp, 20h
0x180066ad0  pop     rbx
0x180066ad1  retn
```
