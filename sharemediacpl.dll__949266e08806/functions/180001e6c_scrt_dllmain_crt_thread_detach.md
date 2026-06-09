# __scrt_dllmain_crt_thread_detach

- ea: `0x180001e6c`
- end: `0x180001e81`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800019f0`

## callees

- `0x18000bd40`

## pseudocode

```c

```

## disassembly

```asm
0x180001e6c  sub     rsp, 28h
0x180001e70  call    ?OnListenedPropertyChanging@CShareWithListItemBase@@UEAA_NPEAVElement@DirectUI@@PEBUPropertyInfo@3@HPEAVValue@3@2@Z; CShareWithListItemBase::OnListenedPropertyChanging(DirectUI::Element *,DirectUI::PropertyInfo const *,int,DirectUI::Value *,DirectUI::Value *)
0x180001e75  call    ?OnListenedPropertyChanging@CShareWithListItemBase@@UEAA_NPEAVElement@DirectUI@@PEBUPropertyInfo@3@HPEAVValue@3@2@Z; CShareWithListItemBase::OnListenedPropertyChanging(DirectUI::Element *,DirectUI::PropertyInfo const *,int,DirectUI::Value *,DirectUI::Value *)
0x180001e7a  mov     al, 1
0x180001e7c  add     rsp, 28h
0x180001e80  retn
```
