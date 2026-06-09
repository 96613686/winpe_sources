# std::unique_ptr__SharedDataManager::QueuePersonalizationUpdate_::_2_::PersonalizationTaskContext_std::default_delete__SharedDataManager::QueuePersonalizationUpdate_::_2_::PersonalizationTaskContext___::_unique_ptr__SharedDataManager::QueuePersonalizationUpdate_::_2_::PersonalizationTaskContext_std::default_delete__SharedDataManager::QueuePersonalizationUpdate_::_2_::PersonalizationTaskContext___

- ea: `0x18000493c`
- end: `0x180004961`
- name: `std::unique_ptr__SharedDataManager::QueuePersonalizationUpdate_::_2_::PersonalizationTaskContext_std::default_delete__SharedDataManager::QueuePersonalizationUpdate_::_2_::PersonalizationTaskContext___::_unique_ptr__SharedDataManager::QueuePersonalizationUpdate_::_2_::PersonalizationTaskContext_std::default_delete__SharedDataManager::QueuePersonalizationUpdate_::_2_::PersonalizationTaskContext___`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18000efc7`

## callees

- `0x18000493c`
- `0x180004db8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004955`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004955`

## pseudocode

```c
void __fastcall std::unique_ptr__SharedDataManager::QueuePersonalizationUpdate_::_2_::PersonalizationTaskContext_std::default_delete__SharedDataManager::QueuePersonalizationUpdate_::_2_::PersonalizationTaskContext___::_unique_ptr__SharedDataManager::QueuePersonalizationUpdate_::_2_::PersonalizationTaskContext_std::default_delete__SharedDataManager::QueuePersonalizationUpdate_::_2_::PersonalizationTaskContext___(
        __int64 *a1)
{
  void *v1; // rbx

  v1 = (void *)*a1;
  if ( *a1 )
  {
    SharedDataManager::QueuePersonalizationUpdate_::_2_::PersonalizationTaskContext::_PersonalizationTaskContext(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18000493c  push    rbx
0x18000493e  sub     rsp, 20h
0x180004942  mov     rbx, [rcx]
0x180004945  test    rbx, rbx
0x180004948  jz      short loc_18000495B
0x18000494a  mov     rcx, rbx
0x18000494d  call    _SharedDataManager__QueuePersonalizationUpdate____2___PersonalizationTaskContext___PersonalizationTaskContext
0x180004952  mov     rcx, rbx
0x180004955  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000495b  add     rsp, 20h
0x18000495f  pop     rbx
0x180004960  retn
```
