# SubscriptionReadData::GetAllowedSubjects(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001ddac`
- end: `0x18001dde5`
- name: `?GetAllowedSubjects@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
char __fastcall SubscriptionReadData::GetAllowedSubjects(__int64 *a1, __int64 a2)
{
  std::wstring::assign(a2, (__int64)&word_180026AD8);
  return ReadMetadataProp(*a1, 0x1Du, a2);
}

```

## disassembly

```asm
0x18001ddac  mov     [rsp+arg_0], rbx
0x18001ddb1  push    rdi
0x18001ddb2  sub     rsp, 20h
0x18001ddb6  mov     rbx, rdx
0x18001ddb9  mov     rdi, rcx
0x18001ddbc  mov     rcx, rbx
0x18001ddbf  lea     rdx, word_180026AD8
0x18001ddc6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001ddcb  mov     rcx, [rdi]
0x18001ddce  mov     r8, rbx
0x18001ddd1  mov     edx, 1Dh
0x18001ddd6  mov     rbx, [rsp+28h+arg_0]
0x18001dddb  add     rsp, 20h
0x18001dddf  pop     rdi
0x18001dde0  jmp     ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::wstring &)
```
