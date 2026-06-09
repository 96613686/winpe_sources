# SubscriptionReadData::GetLogFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001e10c`
- end: `0x18001e145`
- name: `?GetLogFile@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `57`
- prototype: `char __fastcall(__int64 *, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180009170`
- `0x180009a10`
- `0x1800165c0`

## callees

- `0x18000669c`
- `0x18001e808`

## pseudocode

```c
char __fastcall SubscriptionReadData::GetLogFile(__int64 *a1, __int64 a2)
{
  std::wstring::assign(a2, (__int64)&word_180026AD8);
  return ReadMetadataProp(*a1, 0x13u, a2);
}

```

## disassembly

```asm
0x18001e10c  mov     [rsp+arg_0], rbx
0x18001e111  push    rdi
0x18001e112  sub     rsp, 20h
0x18001e116  mov     rbx, rdx
0x18001e119  mov     rdi, rcx
0x18001e11c  mov     rcx, rbx
0x18001e11f  lea     rdx, word_180026AD8
0x18001e126  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001e12b  mov     rcx, [rdi]
0x18001e12e  mov     r8, rbx
0x18001e131  mov     edx, 13h
0x18001e136  mov     rbx, [rsp+28h+arg_0]
0x18001e13b  add     rsp, 20h
0x18001e13f  pop     rdi
0x18001e140  jmp     ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::wstring &)
```
