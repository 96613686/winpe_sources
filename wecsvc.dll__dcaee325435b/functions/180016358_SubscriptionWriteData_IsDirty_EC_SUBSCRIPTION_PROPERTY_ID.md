# SubscriptionWriteData::IsDirty(_EC_SUBSCRIPTION_PROPERTY_ID)

- ea: `0x180016358`
- end: `0x180016375`
- name: `?IsDirty@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z`
- size: `29`
- prototype: `bool __fastcall(SubscriptionWriteData *this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800165c0`
- `0x180017b8c`

## callees

- `0x180016358`

## pseudocode

```c
bool __fastcall SubscriptionWriteData::IsDirty(SubscriptionWriteData *this, unsigned int a2)
{
  if ( a2 < **(_DWORD **)this )
    return *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 24LL * (int)a2 + 4) & 1;
  else
    return 0;
}

```

## disassembly

```asm
0x180016358  mov     r8, [rcx]
0x18001635b  cmp     edx, [r8]
0x18001635e  jb      short loc_180016363
0x180016360  xor     al, al
0x180016362  retn
0x180016363  movsxd  rax, edx
0x180016366  lea     rcx, [rax+rax*2]
0x18001636a  mov     rax, [r8+8]
0x18001636e  mov     eax, [rax+rcx*8+4]
0x180016372  and     al, 1
0x180016374  retn
```
