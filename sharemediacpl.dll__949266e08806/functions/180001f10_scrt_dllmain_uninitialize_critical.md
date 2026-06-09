# __scrt_dllmain_uninitialize_critical

- ea: `0x180001f10`
- end: `0x180001f24`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001b48`

## callees

- `0x18000bd40`

## pseudocode

```c

```

## disassembly

```asm
0x180001f10  sub     rsp, 28h
0x180001f14  xor     ecx, ecx; this
0x180001f16  call    ?OnListenedPropertyChanging@CShareWithListItemBase@@UEAA_NPEAVElement@DirectUI@@PEBUPropertyInfo@3@HPEAVValue@3@2@Z; CShareWithListItemBase::OnListenedPropertyChanging(DirectUI::Element *,DirectUI::PropertyInfo const *,int,DirectUI::Value *,DirectUI::Value *)
0x180001f1b  add     rsp, 28h
0x180001f1f  jmp     ?OnListenedPropertyChanging@CShareWithListItemBase@@UEAA_NPEAVElement@DirectUI@@PEBUPropertyInfo@3@HPEAVValue@3@2@Z; CShareWithListItemBase::OnListenedPropertyChanging(DirectUI::Element *,DirectUI::PropertyInfo const *,int,DirectUI::Value *,DirectUI::Value *)
```
