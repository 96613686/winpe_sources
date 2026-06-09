# SubscriptionReadData::GetCommonPassword(std::vector<ushort,std::allocator<ushort>> &)

- ea: `0x18001ddec`
- end: `0x18001de25`
- name: `?GetCommonPassword@SubscriptionReadData@@QEBAXAEAV?$vector@GV?$allocator@G@std@@@std@@@Z`
- size: `57`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009170`
- `0x1800165c0`

## callees

- `0x180012ddc`
- `0x18001ddec`
- `0x18001e8f0`

## pseudocode

```c
__int64 __fastcall SubscriptionReadData::GetCommonPassword(_QWORD *a1, _QWORD *a2)
{
  __int64 result; // rax
  __int16 v4; // [rsp+30h] [rbp+8h] BYREF

  a2[1] = *a2;
  result = ReadMetadataProp(*a1, a2, a2);
  if ( !(_BYTE)result )
  {
    v4 = 0;
    return std::vector<unsigned short>::push_back(a2, &v4);
  }
  return result;
}

```

## disassembly

```asm
0x18001ddec  push    rbx
0x18001ddee  sub     rsp, 20h
0x18001ddf2  mov     rax, [rdx]
0x18001ddf5  mov     r8, rdx
0x18001ddf8  mov     [rdx+8], rax
0x18001ddfc  mov     rbx, rdx
0x18001ddff  mov     rcx, [rcx]
0x18001de02  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$vector@GV?$allocator@G@std@@@std@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::vector<ushort> &)
0x18001de07  test    al, al
0x18001de09  jnz     short loc_18001DE1F
0x18001de0b  xor     eax, eax
0x18001de0d  lea     rdx, [rsp+28h+arg_0]
0x18001de12  mov     rcx, rbx
0x18001de15  mov     [rsp+28h+arg_0], ax
0x18001de1a  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x18001de1f  add     rsp, 20h
0x18001de23  pop     rbx
0x18001de24  retn
```
