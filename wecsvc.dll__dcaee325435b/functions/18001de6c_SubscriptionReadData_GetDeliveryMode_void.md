# SubscriptionReadData::GetDeliveryMode(void)

- ea: `0x18001de6c`
- end: `0x18001debb`
- name: `?GetDeliveryMode@SubscriptionReadData@@QEBA?AW4_EC_SUBSCRIPTION_DELIVERY_MODE@@XZ`
- size: `79`
- prototype: `__int64 __fastcall(const struct tag_EcRpcMetadataPropertyList **this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008828`
- `0x1800165c0`
- `0x180017b8c`

## callees

- `0x18001e660`

## pseudocode

```c
__int64 __fastcall SubscriptionReadData::GetDeliveryMode(const struct tag_EcRpcMetadataPropertyList **this)
{
  const struct tag_EcRpcMetadataPropertyList *v2; // rcx
  unsigned int v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 1;
  ReadMetadataProp(*this, 0x1Bu, &v4);
  v2 = *this;
  v4 = (v4 != 1) + 1;
  ReadMetadataProp(v2, 0xDu, &v4);
  return v4;
}

```

## disassembly

```asm
0x18001de6c  push    rbx
0x18001de6e  sub     rsp, 20h
0x18001de72  mov     rbx, rcx
0x18001de75  mov     [rsp+28h+arg_0], 1
0x18001de7d  mov     rcx, [rcx]; struct tag_EcRpcMetadataPropertyList *
0x18001de80  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x18001de85  mov     edx, 1Bh; unsigned int
0x18001de8a  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAK@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,ulong &)
0x18001de8f  mov     rcx, [rbx]; struct tag_EcRpcMetadataPropertyList *
0x18001de92  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x18001de97  xor     eax, eax
0x18001de99  mov     edx, 0Dh; unsigned int
0x18001de9e  cmp     [rsp+28h+arg_0], 1
0x18001dea3  setnz   al
0x18001dea6  inc     eax
0x18001dea8  mov     [rsp+28h+arg_0], eax
0x18001deac  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAK@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,ulong &)
0x18001deb1  mov     eax, [rsp+28h+arg_0]
0x18001deb5  add     rsp, 20h
0x18001deb9  pop     rbx
0x18001deba  retn
```
