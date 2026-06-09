# SubscriptionReadData::GetLocale(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001e0cc`
- end: `0x18001e105`
- name: `?GetLocale@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
char __fastcall SubscriptionReadData::GetLocale(__int64 *a1, __int64 a2)
{
  std::wstring::assign(a2, (__int64)&word_180026AD8);
  return ReadMetadataProp(*a1, 0x11u, a2);
}

```

## disassembly

```asm
0x18001e0cc  mov     [rsp+arg_0], rbx
0x18001e0d1  push    rdi
0x18001e0d2  sub     rsp, 20h
0x18001e0d6  mov     rbx, rdx
0x18001e0d9  mov     rdi, rcx
0x18001e0dc  mov     rcx, rbx
0x18001e0df  lea     rdx, word_180026AD8
0x18001e0e6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001e0eb  mov     rcx, [rdi]
0x18001e0ee  mov     r8, rbx
0x18001e0f1  mov     edx, 11h
0x18001e0f6  mov     rbx, [rsp+28h+arg_0]
0x18001e0fb  add     rsp, 20h
0x18001e0ff  pop     rdi
0x18001e100  jmp     ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::wstring &)
```
