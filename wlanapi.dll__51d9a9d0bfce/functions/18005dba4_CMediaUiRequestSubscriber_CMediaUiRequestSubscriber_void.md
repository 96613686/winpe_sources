# CMediaUiRequestSubscriber::~CMediaUiRequestSubscriber(void)

- ea: `0x18005dba4`
- end: `0x18005dbe8`
- name: `??1CMediaUiRequestSubscriber@@QEAA@XZ`
- size: `68`
- prototype: `void __fastcall(CMediaUiRequestSubscriber *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180032bcc`

## callees

- `0x18005db64`
- `0x18005e24c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005dbbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005dbbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005dbc6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005dbc6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005dbcf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005dbcf`

## pseudocode

```c
void __fastcall CMediaUiRequestSubscriber::~CMediaUiRequestSubscriber(CMediaUiRequestSubscriber *this)
{
  CMediaUiRequestSubscriber::Unsubscribe(this);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,_WNF_USER_SUBSCRIPTION *,WnfStateNameCompare,std::allocator<std::pair<_WNF_STATE_NAME const,_WNF_USER_SUBSCRIPTION *>>,0>>::~_Tree<std::_Tmap_traits<_WNF_STATE_NAME,_WNF_USER_SUBSCRIPTION *,WnfStateNameCompare,std::allocator<std::pair<_WNF_STATE_NAME const,_WNF_USER_SUBSCRIPTION *>>,0>>((char *)this + 96);
}

```

## disassembly

```asm
0x18005dba4  mov     [rsp+arg_0], rbx
0x18005dba9  push    rdi
0x18005dbaa  sub     rsp, 20h
0x18005dbae  mov     rdi, rcx
0x18005dbb1  call    ?Unsubscribe@CMediaUiRequestSubscriber@@QEAAJXZ; CMediaUiRequestSubscriber::Unsubscribe(void)
0x18005dbb6  lea     rbx, [rdi+20h]
0x18005dbba  mov     rcx, rbx; lpCriticalSection
0x18005dbbd  call    cs:__imp_EnterCriticalSection
0x18005dbc3  mov     rcx, rbx; lpCriticalSection
0x18005dbc6  call    cs:__imp_LeaveCriticalSection
0x18005dbcc  mov     rcx, rbx; lpCriticalSection
0x18005dbcf  call    cs:__imp_DeleteCriticalSection
0x18005dbd5  lea     rcx, [rdi+60h]
0x18005dbd9  mov     rbx, [rsp+28h+arg_0]
0x18005dbde  add     rsp, 20h
0x18005dbe2  pop     rdi
0x18005dbe3  jmp     ??1?$_Tree@V?$_Tmap_traits@U_WNF_STATE_NAME@@PEAU_WNF_USER_SUBSCRIPTION@@UWnfStateNameCompare@@V?$allocator@U?$pair@$$CBU_WNF_STATE_NAME@@PEAU_WNF_USER_SUBSCRIPTION@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,_WNF_USER_SUBSCRIPTION *,WnfStateNameCompare,std::allocator<std::pair<_WNF_STATE_NAME const,_WNF_USER_SUBSCRIPTION *>>,0>>::~_Tree<std::_Tmap_traits<_WNF_STATE_NAME,_WNF_USER_SUBSCRIPTION *,WnfStateNameCompare,std::allocator<std::pair<_WNF_STATE_NAME const,_WNF_USER_SUBSCRIPTION *>>,0>>(void)
```
