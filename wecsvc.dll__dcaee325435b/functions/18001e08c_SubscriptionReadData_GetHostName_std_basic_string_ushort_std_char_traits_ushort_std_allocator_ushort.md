# SubscriptionReadData::GetHostName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001e08c`
- end: `0x18001e0c5`
- name: `?GetHostName@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
char __fastcall SubscriptionReadData::GetHostName(__int64 *a1, __int64 a2)
{
  std::wstring::assign(a2, (__int64)&word_180026AD8);
  return ReadMetadataProp(*a1, 0x18u, a2);
}

```

## disassembly

```asm
0x18001e08c  mov     [rsp+arg_0], rbx
0x18001e091  push    rdi
0x18001e092  sub     rsp, 20h
0x18001e096  mov     rbx, rdx
0x18001e099  mov     rdi, rcx
0x18001e09c  mov     rcx, rbx
0x18001e09f  lea     rdx, word_180026AD8
0x18001e0a6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001e0ab  mov     rcx, [rdi]
0x18001e0ae  mov     r8, rbx
0x18001e0b1  mov     edx, 18h
0x18001e0b6  mov     rbx, [rsp+28h+arg_0]
0x18001e0bb  add     rsp, 20h
0x18001e0bf  pop     rdi
0x18001e0c0  jmp     ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::wstring &)
```
