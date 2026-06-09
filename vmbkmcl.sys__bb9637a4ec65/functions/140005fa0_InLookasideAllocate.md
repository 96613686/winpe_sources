# InLookasideAllocate

- ea: `0x140005fa0`
- end: `0x140005fc4`
- name: `InLookasideAllocate`
- size: `36`
- prototype: `ALLOCATE_FUNCTION`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140005fa0`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140005fa9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140005fa9`

## pseudocode

```c
_DWORD *__fastcall InLookasideAllocate(POOL_TYPE PoolType, SIZE_T NumberOfBytes, ULONG Tag)
{
  int v3; // ebx
  _DWORD *result; // rax

  v3 = NumberOfBytes;
  result = ExAllocatePoolWithTag(PoolType, NumberOfBytes, Tag);
  if ( result )
    result[2] = v3;
  return result;
}

```

## disassembly

```asm
0x140005fa0  push    rbx
0x140005fa2  sub     rsp, 20h
0x140005fa6  mov     rbx, rdx
0x140005fa9  call    cs:__imp_ExAllocatePoolWithTag
0x140005fb0  nop     dword ptr [rax+rax+00h]
0x140005fb5  test    rax, rax
0x140005fb8  jz      short loc_140005FBD
0x140005fba  mov     [rax+8], ebx
0x140005fbd  add     rsp, 20h
0x140005fc1  pop     rbx
0x140005fc2  retn
```
