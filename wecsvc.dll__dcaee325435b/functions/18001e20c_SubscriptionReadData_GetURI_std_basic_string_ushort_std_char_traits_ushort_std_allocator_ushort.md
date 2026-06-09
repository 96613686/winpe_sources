# SubscriptionReadData::GetURI(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001e20c`
- end: `0x18001e245`
- name: `?GetURI@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `57`
- prototype: `char __fastcall(__int64 *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

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
char __fastcall SubscriptionReadData::GetURI(__int64 *a1, __int64 a2)
{
  std::wstring::assign(a2, &word_180026AD8);
  return ReadMetadataProp(*a1, 7u, a2);
}

```

## disassembly

```asm
0x18001e20c  mov     [rsp+arg_0], rbx
0x18001e211  push    rdi
0x18001e212  sub     rsp, 20h
0x18001e216  mov     rbx, rdx
0x18001e219  mov     rdi, rcx
0x18001e21c  mov     rcx, rbx
0x18001e21f  lea     rdx, word_180026AD8
0x18001e226  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001e22b  mov     rcx, [rdi]
0x18001e22e  mov     r8, rbx
0x18001e231  mov     edx, 7
0x18001e236  mov     rbx, [rsp+28h+arg_0]
0x18001e23b  add     rsp, 20h
0x18001e23f  pop     rdi
0x18001e240  jmp     ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::wstring &)
```
