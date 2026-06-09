# __scrt_dllmain_crt_thread_attach

- ea: `0x180001e3c`
- end: `0x180001e64`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800019f0`

## callees

- `0x180001e3c`
- `0x18000bd40`

## pseudocode

```c

```

## disassembly

```asm
0x180001e3c  sub     rsp, 28h
0x180001e40  call    ?OnListenedPropertyChanging@CShareWithListItemBase@@UEAA_NPEAVElement@DirectUI@@PEBUPropertyInfo@3@HPEAVValue@3@2@Z; CShareWithListItemBase::OnListenedPropertyChanging(DirectUI::Element *,DirectUI::PropertyInfo const *,int,DirectUI::Value *,DirectUI::Value *)
0x180001e45  test    al, al
0x180001e47  jnz     short loc_180001E4D
0x180001e49  xor     al, al
0x180001e4b  jmp     short loc_180001E5F
0x180001e4d  call    ?OnListenedPropertyChanging@CShareWithListItemBase@@UEAA_NPEAVElement@DirectUI@@PEBUPropertyInfo@3@HPEAVValue@3@2@Z; CShareWithListItemBase::OnListenedPropertyChanging(DirectUI::Element *,DirectUI::PropertyInfo const *,int,DirectUI::Value *,DirectUI::Value *)
0x180001e52  test    al, al
0x180001e54  jnz     short loc_180001E5D
0x180001e56  call    ?OnListenedPropertyChanging@CShareWithListItemBase@@UEAA_NPEAVElement@DirectUI@@PEBUPropertyInfo@3@HPEAVValue@3@2@Z; CShareWithListItemBase::OnListenedPropertyChanging(DirectUI::Element *,DirectUI::PropertyInfo const *,int,DirectUI::Value *,DirectUI::Value *)
0x180001e5b  jmp     short loc_180001E49
0x180001e5d  mov     al, 1
0x180001e5f  add     rsp, 28h
0x180001e63  retn
```
