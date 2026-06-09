# SubscriptionWriteData::IsCleared(_EC_SUBSCRIPTION_PROPERTY_ID)

- ea: `0x18001632c`
- end: `0x180016350`
- name: `?IsCleared@SubscriptionWriteData@@QEAA_NW4_EC_SUBSCRIPTION_PROPERTY_ID@@@Z`
- size: `36`
- prototype: `bool __fastcall(SubscriptionWriteData *this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800165c0`
- `0x180017b8c`

## callees

- `0x18001632c`

## pseudocode

```c
bool __fastcall SubscriptionWriteData::IsCleared(SubscriptionWriteData *this, unsigned int a2)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  bool result; // al

  if ( a2 >= **(_DWORD **)this )
    return 0;
  v2 = (int)a2;
  v3 = *(_QWORD *)(*(_QWORD *)this + 8LL);
  v4 = 3 * v2;
  result = 1;
  if ( (*(_BYTE *)(v3 + 8 * v4 + 4) & 1) == 0 || *(_DWORD *)(v3 + 8 * v4) )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18001632c  mov     r8, [rcx]
0x18001632f  cmp     edx, [r8]
0x180016332  jnb     short loc_18001634D
0x180016334  movsxd  rax, edx
0x180016337  mov     rdx, [r8+8]
0x18001633b  lea     rcx, [rax+rax*2]
0x18001633f  mov     al, 1
0x180016341  test    [rdx+rcx*8+4], al
0x180016345  jz      short loc_18001634D
0x180016347  cmp     dword ptr [rdx+rcx*8], 0
0x18001634b  jz      short locret_18001634F
0x18001634d  xor     al, al
0x18001634f  retn
```
