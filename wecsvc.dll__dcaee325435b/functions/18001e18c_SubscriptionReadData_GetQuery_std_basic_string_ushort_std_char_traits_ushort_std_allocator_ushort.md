# SubscriptionReadData::GetQuery(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001e18c`
- end: `0x18001e1c5`
- name: `?GetQuery@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `57`
- prototype: `char __fastcall(__int64 *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180008828`
- `0x180009a10`
- `0x1800165c0`
- `0x180017b8c`

## callees

- `0x18000669c`
- `0x18001e808`

## pseudocode

```c
char __fastcall SubscriptionReadData::GetQuery(__int64 *a1, __int64 a2)
{
  std::wstring::assign(a2, &word_180026AD8);
  return ReadMetadataProp(*a1, 0xAu, a2);
}

```

## disassembly

```asm
0x18001e18c  mov     [rsp+arg_0], rbx
0x18001e191  push    rdi
0x18001e192  sub     rsp, 20h
0x18001e196  mov     rbx, rdx
0x18001e199  mov     rdi, rcx
0x18001e19c  mov     rcx, rbx
0x18001e19f  lea     rdx, word_180026AD8
0x18001e1a6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001e1ab  mov     rcx, [rdi]
0x18001e1ae  mov     r8, rbx
0x18001e1b1  mov     edx, 0Ah
0x18001e1b6  mov     rbx, [rsp+28h+arg_0]
0x18001e1bb  add     rsp, 20h
0x18001e1bf  pop     rdi
0x18001e1c0  jmp     ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::wstring &)
```
