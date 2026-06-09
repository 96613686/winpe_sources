# CBsString::Append(ushort const *)

- ea: `0x180014f38`
- end: `0x180014f80`
- name: `?Append@CBsString@@QEAAJPEBG@Z`
- size: `72`
- prototype: `__int64 __fastcall(CBsString *this, unsigned __int16 *)`
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x1800029d8`
- `0x180002e9c`
- `0x180003740`
- `0x180003854`
- `0x180003968`
- `0x180003b24`
- `0x180004928`
- `0x180004e20`
- `0x1800050dc`
- `0x18000572c`
- `0x18000b3b0`
- `0x18000bdd0`
- `0x18000c258`
- `0x18000c468`
- `0x18000c890`
- `0x18000cc20`
- `0x18000e7ec`
- `0x18000f310`
- `0x1800153c4`

## callees

- `0x180014f38`
- `0x1800154c8`

## pseudocode

```c
__int64 __fastcall CBsString::Append(CBsString *this, unsigned __int16 *a2)
{
  __int64 v3; // r8
  unsigned int v4; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int16 *v5; // [rsp+50h] [rbp+18h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  v5 = a2;
  v4 = v3;
  return CBsString::_Append(this, 1u, v3, &v4, (const unsigned __int16 **const)&v5);
}

```

## disassembly

```asm
0x180014f38  sub     rsp, 38h
0x180014f3c  xor     eax, eax
0x180014f3e  test    rdx, rdx
0x180014f41  jnz     short loc_180014F4A
0x180014f43  mov     eax, 80070057h
0x180014f48  jmp     short loc_180014F7B
0x180014f4a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180014f4e  inc     r8; unsigned int
0x180014f51  cmp     [rdx+r8*2], ax
0x180014f56  jnz     short loc_180014F4E
0x180014f58  mov     [rsp+38h+arg_10], rdx
0x180014f5d  lea     rax, [rsp+38h+arg_10]
0x180014f62  mov     edx, 1; unsigned int
0x180014f67  mov     [rsp+38h+var_18], rax; unsigned __int16 **
0x180014f6c  lea     r9, [rsp+38h+arg_8]; unsigned int *
0x180014f71  mov     [rsp+38h+arg_8], r8d
0x180014f76  call    ?_Append@CBsString@@AEAAJKKQEAKQEAPEBG@Z; CBsString::_Append(ulong,ulong,ulong * const,ushort const * * const)
0x180014f7b  add     rsp, 38h
0x180014f7f  retn
```
