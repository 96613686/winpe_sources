# SubscriptionReadData::GetCommonUserName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001de2c`
- end: `0x18001de65`
- name: `?GetCommonUserName@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `57`
- prototype: `char __fastcall(__int64 *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009170`
- `0x1800165c0`

## callees

- `0x18000669c`
- `0x18001e808`

## pseudocode

```c
char __fastcall SubscriptionReadData::GetCommonUserName(__int64 *a1, __int64 a2)
{
  std::wstring::assign(a2, &word_180026AD8);
  return ReadMetadataProp(*a1, 0x16u, a2);
}

```

## disassembly

```asm
0x18001de2c  mov     [rsp+arg_0], rbx
0x18001de31  push    rdi
0x18001de32  sub     rsp, 20h
0x18001de36  mov     rbx, rdx
0x18001de39  mov     rdi, rcx
0x18001de3c  mov     rcx, rbx
0x18001de3f  lea     rdx, word_180026AD8
0x18001de46  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001de4b  mov     rcx, [rdi]
0x18001de4e  mov     r8, rbx
0x18001de51  mov     edx, 16h
0x18001de56  mov     rbx, [rsp+28h+arg_0]
0x18001de5b  add     rsp, 20h
0x18001de5f  pop     rdi
0x18001de60  jmp     ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::wstring &)
```
