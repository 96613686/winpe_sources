# UdfComputeCrc16Uni

- ea: `0x140056398`
- end: `0x1400563e8`
- name: `UdfComputeCrc16Uni`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400401a0`
- `0x140040d34`

## callees

- `0x140056398`

## pseudocode

```c
__int64 __fastcall UdfComputeCrc16Uni(unsigned __int16 *a1, int a2)
{
  int v3; // r10d
  unsigned __int16 i; // cx
  unsigned int v5; // r9d
  __int16 v6; // cx

  v3 = a2;
  for ( i = 0; v3; --v3 )
  {
    v5 = *a1++;
    v6 = *((_WORD *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink->Flink + ((i ^ (unsigned __int64)v5) >> 8))
       ^ (i << 8);
    i = *((_WORD *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink->Flink + (unsigned __int8)(v5 ^ HIBYTE(v6)))
      ^ (v6 << 8);
  }
  return i;
}

```

## disassembly

```asm
0x140056398  mov     r11, rcx
0x14005639b  mov     r10d, edx
0x14005639e  xor     ecx, ecx
0x1400563a0  test    edx, edx
0x1400563a2  jz      short loc_1400563E4
0x1400563a4  movzx   r9d, word ptr [r11]
0x1400563a8  lea     r11, [r11+2]
0x1400563ac  mov     rdx, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x1400563b3  mov     r8d, r9d
0x1400563b6  movzx   eax, cx
0x1400563b9  xor     r8, rax
0x1400563bc  shl     cx, 8
0x1400563c0  shr     r8, 8
0x1400563c4  xor     cx, [rdx+r8*2]
0x1400563c9  mov     rax, rcx
0x1400563cc  shl     cx, 8
0x1400563d0  shr     rax, 8
0x1400563d4  xor     rax, r9
0x1400563d7  movzx   eax, al
0x1400563da  xor     cx, [rdx+rax*2]
0x1400563de  add     r10d, 0FFFFFFFFh
0x1400563e2  jnz     short loc_1400563A4
0x1400563e4  movzx   eax, cx
0x1400563e7  retn
```
