# SubscriptionReadData::~SubscriptionReadData(void)

- ea: `0x18000a3e0`
- end: `0x18000a443`
- name: `??1SubscriptionReadData@@QEAA@XZ`
- size: `99`
- prototype: `void __fastcall(SubscriptionReadData *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006298`
- `0x1800062b0`

## callees

- `0x18000a3e0`
- `0x18000a640`

## pseudocode

```c
void __fastcall SubscriptionReadData::~SubscriptionReadData(struct tag_EcRpcMetadataPropertyList **this)
{
  __int64 v1; // r9
  unsigned int i; // r8d
  _BYTE *v3; // rdx
  __int64 v4; // rax
  __int64 j; // rax

  if ( *((_BYTE *)this + 8) )
  {
    CleanupMetadataPropList(*this);
  }
  else
  {
    v1 = *((_QWORD *)*this + 1);
    for ( i = 0; i < *(_DWORD *)(v1 + 128); ++i )
    {
      v3 = *(_BYTE **)(*(_QWORD *)(v1 + 136) + 8LL * i);
      if ( v3 )
      {
        v4 = -1;
        do
          ++v4;
        while ( *(_WORD *)&v3[2 * v4] );
        for ( j = 2 * v4; j; --j )
          *v3++ = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x18000a3e0  mov     rax, [rcx]
0x18000a3e3  xor     r10d, r10d
0x18000a3e6  cmp     [rcx+8], r10b
0x18000a3ea  jz      short loc_18000A3F4
0x18000a3ec  mov     rcx, rax; struct tag_EcRpcMetadataPropertyList *
0x18000a3ef  jmp     ?CleanupMetadataPropList@@YAXPEAUtag_EcRpcMetadataPropertyList@@@Z; CleanupMetadataPropList(tag_EcRpcMetadataPropertyList *)
0x18000a3f4  mov     r9, [rax+8]
0x18000a3f8  mov     r8d, r10d
0x18000a3fb  cmp     [r9+80h], r10d
0x18000a402  jbe     short locret_18000A442
0x18000a404  mov     rax, [r9+88h]
0x18000a40b  mov     ecx, r8d
0x18000a40e  mov     rdx, [rax+rcx*8]
0x18000a412  test    rdx, rdx
0x18000a415  jz      short loc_18000A436
0x18000a417  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a41b  inc     rax
0x18000a41e  cmp     [rdx+rax*2], r10w
0x18000a423  jnz     short loc_18000A41B
0x18000a425  add     rax, rax
0x18000a428  jz      short loc_18000A436
0x18000a42a  mov     [rdx], r10b
0x18000a42d  inc     rdx
0x18000a430  sub     rax, 1
0x18000a434  jnz     short loc_18000A42A
0x18000a436  inc     r8d
0x18000a439  cmp     r8d, [r9+80h]
0x18000a440  jb      short loc_18000A404
0x18000a442  retn
```
