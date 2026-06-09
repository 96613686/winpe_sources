# SubscriptionManager::~SubscriptionManager(void)

- ea: `0x180008330`
- end: `0x180008375`
- name: `??1SubscriptionManager@@UEAA@XZ`
- size: `69`
- prototype: `void __fastcall(SubscriptionManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800087f0`

## callees

- `0x180008014`
- `0x180010248`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008355`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000835f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008355`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000835f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SubscriptionManager::~SubscriptionManager(SubscriptionManager *this)
{
  *(_QWORD *)this = &SubscriptionManager::`vftable';
  SubscriptionManager::Shutdown(this);
  std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>,0>>((char *)this + 96);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *(_QWORD *)this = &wmi::RefBase::`vftable';
}

```

## disassembly

```asm
0x180008330  push    rbx
0x180008332  sub     rsp, 20h
0x180008336  lea     rax, ??_7SubscriptionManager@@6B@; const SubscriptionManager::`vftable'
0x18000833d  mov     rbx, rcx
0x180008340  mov     [rcx], rax
0x180008343  call    ?Shutdown@SubscriptionManager@@QEAAXXZ; SubscriptionManager::Shutdown(void)
0x180008348  lea     rcx, [rbx+60h]
0x18000834c  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@VCaseInsensitiveLess@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>,0>>(void)
0x180008351  lea     rcx, [rbx+38h]; lpCriticalSection
0x180008355  call    cs:__imp_DeleteCriticalSection
0x18000835b  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000835f  call    cs:__imp_DeleteCriticalSection
0x180008365  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x18000836c  mov     [rbx], rax
0x18000836f  add     rsp, 20h
0x180008373  pop     rbx
0x180008374  retn
```
