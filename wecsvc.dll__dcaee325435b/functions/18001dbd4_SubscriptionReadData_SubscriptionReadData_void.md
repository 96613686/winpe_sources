# SubscriptionReadData::~SubscriptionReadData(void)

- ea: `0x18001dbd4`
- end: `0x18001dc37`
- name: `??1SubscriptionReadData@@QEAA@XZ`
- size: `99`
- prototype: `void __fastcall(struct tag_EcRpcMetadataPropertyList **this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003c94`
- `0x180003cbc`
- `0x1800154cc`

## callees

- `0x18001dbd4`
- `0x18001dc40`

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
0x18001dbd4  mov     rax, [rcx]
0x18001dbd7  xor     r10d, r10d
0x18001dbda  cmp     [rcx+8], r10b
0x18001dbde  jz      short loc_18001DBE8
0x18001dbe0  mov     rcx, rax; struct tag_EcRpcMetadataPropertyList *
0x18001dbe3  jmp     ?CleanupMetadataPropList@@YAXPEAUtag_EcRpcMetadataPropertyList@@@Z; CleanupMetadataPropList(tag_EcRpcMetadataPropertyList *)
0x18001dbe8  mov     r9, [rax+8]
0x18001dbec  mov     r8d, r10d
0x18001dbef  cmp     [r9+80h], r10d
0x18001dbf6  jbe     short locret_18001DC36
0x18001dbf8  mov     rax, [r9+88h]
0x18001dbff  mov     ecx, r8d
0x18001dc02  mov     rdx, [rax+rcx*8]
0x18001dc06  test    rdx, rdx
0x18001dc09  jz      short loc_18001DC2A
0x18001dc0b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001dc0f  inc     rax
0x18001dc12  cmp     [rdx+rax*2], r10w
0x18001dc17  jnz     short loc_18001DC0F
0x18001dc19  add     rax, rax
0x18001dc1c  jz      short loc_18001DC2A
0x18001dc1e  mov     [rdx], r10b
0x18001dc21  inc     rdx
0x18001dc24  sub     rax, 1
0x18001dc28  jnz     short loc_18001DC1E
0x18001dc2a  inc     r8d
0x18001dc2d  cmp     r8d, [r9+80h]
0x18001dc34  jb      short loc_18001DBF8
0x18001dc36  retn
```
