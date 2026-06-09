# ComputeSmallestSafeVirtualSize

- ea: `0x180007378`
- end: `0x1800073c7`
- name: `ComputeSmallestSafeVirtualSize`
- size: `79`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006f48`
- `0x180007a40`
- `0x180009480`

## callees

- `0x180007378`
- `0x180007f2c`

## pseudocode

```c
__int64 __fastcall ComputeSmallestSafeVirtualSize(void *a1)
{
  __int64 result; // rax
  __int64 v2; // [rsp+30h] [rbp-18h] BYREF
  __int64 v3; // [rsp+38h] [rbp-10h] BYREF

  v2 = 0;
  result = ParseVirtualDiskPartitionTable(a1, (__int64)&v2, (__int64)&v3);
  if ( !(_DWORD)result )
    return 3225026598LL;
  return result;
}

```

## disassembly

```asm
0x180007378  mov     r11, rsp
0x18000737b  sub     rsp, 48h
0x18000737f  lea     rax, [r11-10h]
0x180007383  mov     [rsp+48h+arg_18], 0
0x18000738b  mov     [r11-20h], rax
0x18000738f  mov     r9, r8
0x180007392  lea     rax, [r11-18h]
0x180007396  mov     qword ptr [r11-18h], 0
0x18000739e  mov     r8, rdx
0x1800073a1  mov     [r11-28h], rax
0x1800073a5  lea     rdx, [r11+20h]
0x1800073a9  call    ParseVirtualDiskPartitionTable
0x1800073ae  test    eax, eax
0x1800073b0  jnz     short loc_1800073C1
0x1800073b2  mov     eax, [rsp+48h+arg_18]
0x1800073b6  neg     eax
0x1800073b8  sbb     eax, eax
0x1800073ba  not     eax
0x1800073bc  and     eax, 0C03A0026h
0x1800073c1  add     rsp, 48h
0x1800073c5  retn
```
