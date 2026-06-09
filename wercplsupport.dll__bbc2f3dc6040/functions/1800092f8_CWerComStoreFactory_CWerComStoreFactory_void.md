# CWerComStoreFactory::~CWerComStoreFactory(void)

- ea: `0x1800092f8`
- end: `0x180009346`
- name: `??1CWerComStoreFactory@@UEAA@XZ`
- size: `78`
- prototype: `void __fastcall(CWerComStoreFactory *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009b40`

## callees

- `0x180007624`
- `0x1800092f8`
- `0x180013010`

## pseudocode

```c
void __fastcall CWerComStoreFactory::~CWerComStoreFactory(CWerComStoreFactory *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CWerComStoreFactory::`vftable'{for `CManagedObj'};
  *((_QWORD *)this + 3) = &CWerComStoreFactory::`vftable'{for `IWerStoreFactory'};
  v2 = *((_QWORD *)this + 4);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  *(_QWORD *)this = &CManagedObj::`vftable';
  CObjectManager::UnLockServer((CObjectManager *)&CObjectManager::ms_instance);
}

```

## disassembly

```asm
0x1800092f8  push    rbx
0x1800092fa  sub     rsp, 20h
0x1800092fe  lea     rax, ??_7CWerComStoreFactory@@6BCManagedObj@@@; const CWerComStoreFactory::`vftable'{for `CManagedObj'}
0x180009305  mov     rbx, rcx
0x180009308  mov     [rcx], rax
0x18000930b  lea     rax, ??_7CWerComStoreFactory@@6BIWerStoreFactory@@@; const CWerComStoreFactory::`vftable'{for `IWerStoreFactory'}
0x180009312  mov     [rcx+18h], rax
0x180009316  mov     rcx, [rcx+20h]
0x18000931a  test    rcx, rcx
0x18000931d  jz      short loc_18000932B
0x18000931f  mov     rax, [rcx]
0x180009322  mov     rax, [rax+10h]
0x180009326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000932b  lea     rax, ??_7CManagedObj@@6B@; const CManagedObj::`vftable'
0x180009332  lea     rcx, ?ms_instance@CObjectManager@@1V1@A; this
0x180009339  mov     [rbx], rax
0x18000933c  add     rsp, 20h
0x180009340  pop     rbx
0x180009341  jmp     ?UnLockServer@CObjectManager@@QEAAXXZ; CObjectManager::UnLockServer(void)
```
