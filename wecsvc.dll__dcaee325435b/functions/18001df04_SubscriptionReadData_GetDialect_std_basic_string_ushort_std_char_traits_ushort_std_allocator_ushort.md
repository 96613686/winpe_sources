# SubscriptionReadData::GetDialect(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001df04`
- end: `0x18001df3d`
- name: `?GetDialect@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `57`
- prototype: `char __fastcall(__int64 *, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180008828`
- `0x180009a10`
- `0x1800165c0`

## callees

- `0x18000669c`
- `0x18001e808`

## pseudocode

```c
char __fastcall SubscriptionReadData::GetDialect(__int64 *a1, __int64 a2)
{
  std::wstring::assign(a2, (__int64)&word_180026AD8);
  return ReadMetadataProp(*a1, 0x1Au, a2);
}

```

## disassembly

```asm
0x18001df04  mov     [rsp+arg_0], rbx
0x18001df09  push    rdi
0x18001df0a  sub     rsp, 20h
0x18001df0e  mov     rbx, rdx
0x18001df11  mov     rdi, rcx
0x18001df14  mov     rcx, rbx
0x18001df17  lea     rdx, word_180026AD8
0x18001df1e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001df23  mov     rcx, [rdi]
0x18001df26  mov     r8, rbx
0x18001df29  mov     edx, 1Ah
0x18001df2e  mov     rbx, [rsp+28h+arg_0]
0x18001df33  add     rsp, 20h
0x18001df37  pop     rdi
0x18001df38  jmp     ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::wstring &)
```
