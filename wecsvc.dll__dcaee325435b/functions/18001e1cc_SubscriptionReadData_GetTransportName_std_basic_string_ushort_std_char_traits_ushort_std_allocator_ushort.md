# SubscriptionReadData::GetTransportName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001e1cc`
- end: `0x18001e205`
- name: `?GetTransportName@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
char __fastcall SubscriptionReadData::GetTransportName(__int64 *a1, __int64 a2)
{
  std::wstring::assign(a2, (__int64)&word_180026AD8);
  return ReadMetadataProp(*a1, 0xBu, a2);
}

```

## disassembly

```asm
0x18001e1cc  mov     [rsp+arg_0], rbx
0x18001e1d1  push    rdi
0x18001e1d2  sub     rsp, 20h
0x18001e1d6  mov     rbx, rdx
0x18001e1d9  mov     rdi, rcx
0x18001e1dc  mov     rcx, rbx
0x18001e1df  lea     rdx, word_180026AD8
0x18001e1e6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001e1eb  mov     rcx, [rdi]
0x18001e1ee  mov     r8, rbx
0x18001e1f1  mov     edx, 0Bh
0x18001e1f6  mov     rbx, [rsp+28h+arg_0]
0x18001e1fb  add     rsp, 20h
0x18001e1ff  pop     rdi
0x18001e200  jmp     ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::wstring &)
```
