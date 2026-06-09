# SclRegSetValue

- ea: `0x18000a334`
- end: `0x18000a38d`
- name: `SclRegSetValue`
- size: `89`
- prototype: `__int64 __fastcall(void *, __int64, __int64, void *, ULONG, ULONG Type)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002cc8`
- `0x180003408`
- `0x18000438c`
- `0x1800051d8`
- `0x18000540c`

## callees

- `0x18000a334`
- `0x18000a394`

## pseudocode

```c
__int64 __fastcall SclRegSetValue(void *a1, __int64 a2, __int64 a3, void *a4, ULONG a5, ULONG Type)
{
  __int64 v6; // rax

  if ( !a1 || !a4 && a5 )
    return 3221225485LL;
  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(a3 + 2 * v6) );
  }
  return SclRegSetValue_UStr(a1, a4, a5, Type);
}

```

## disassembly

```asm
0x18000a334  sub     rsp, 48h
0x18000a338  mov     r10, r9
0x18000a33b  xor     r9d, r9d
0x18000a33e  test    rcx, rcx
0x18000a341  jz      short loc_18000A383
0x18000a343  mov     edx, [rsp+48h+arg_20]
0x18000a347  test    r10, r10
0x18000a34a  jnz     short loc_18000A350
0x18000a34c  test    edx, edx
0x18000a34e  jnz     short loc_18000A383
0x18000a350  test    r8, r8
0x18000a353  jz      short loc_18000A36B
0x18000a355  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a359  inc     rax
0x18000a35c  cmp     [r8+rax*2], r9w
0x18000a361  jnz     short loc_18000A359
0x18000a363  lea     r9d, ds:2[rax*2]
0x18000a36b  mov     eax, [rsp+48h+arg_28]
0x18000a36f  mov     [rsp+48h+Type], eax; Type
0x18000a373  mov     [rsp+48h+var_20], edx; ULONG
0x18000a377  mov     [rsp+48h+var_28], r10; PVOID
0x18000a37c  call    SclRegSetValue_UStr
0x18000a381  jmp     short loc_18000A388
0x18000a383  mov     eax, 0C000000Dh
0x18000a388  add     rsp, 48h
0x18000a38c  retn
```
