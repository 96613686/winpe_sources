# SubscriptionReadData::GetAllowedIssuerCAs(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001dd2c`
- end: `0x18001dd65`
- name: `?GetAllowedIssuerCAs@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `57`
- prototype: `char __fastcall(__int64 *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009a10`
- `0x1800165c0`

## callees

- `0x18000669c`
- `0x18001e808`

## pseudocode

```c
char __fastcall SubscriptionReadData::GetAllowedIssuerCAs(__int64 *a1, __int64 a2)
{
  std::wstring::assign(a2, (__int64)&word_180026AD8);
  return ReadMetadataProp(*a1, 0x1Cu, a2);
}

```

## disassembly

```asm
0x18001dd2c  mov     [rsp+arg_0], rbx
0x18001dd31  push    rdi
0x18001dd32  sub     rsp, 20h
0x18001dd36  mov     rbx, rdx
0x18001dd39  mov     rdi, rcx
0x18001dd3c  mov     rcx, rbx
0x18001dd3f  lea     rdx, word_180026AD8
0x18001dd46  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001dd4b  mov     rcx, [rdi]
0x18001dd4e  mov     r8, rbx
0x18001dd51  mov     edx, 1Ch
0x18001dd56  mov     rbx, [rsp+28h+arg_0]
0x18001dd5b  add     rsp, 20h
0x18001dd5f  pop     rdi
0x18001dd60  jmp     ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::wstring &)
```
