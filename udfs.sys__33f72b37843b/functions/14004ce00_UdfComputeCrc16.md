# UdfComputeCrc16

- ea: `0x14004ce00`
- end: `0x14004ce3a`
- name: `UdfComputeCrc16`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140005e80`
- `0x140009450`

## callees

- `0x14004ce00`

## pseudocode

```c
unsigned __int16 __fastcall UdfComputeCrc16(unsigned __int8 *a1, int a2)
{
  unsigned __int16 result; // ax
  int i; // r9d
  __int64 v5; // rdx

  result = 0;
  for ( i = a2; i; --i )
  {
    v5 = *a1++;
    result = *((_WORD *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink->Flink + (v5 ^ ((unsigned __int64)result >> 8)))
           ^ (result << 8);
  }
  return result;
}

```

## disassembly

```asm
0x14004ce00  xor     eax, eax
0x14004ce02  mov     r9d, edx
0x14004ce05  mov     r10, rcx
0x14004ce08  test    edx, edx
0x14004ce0a  jz      short locret_14004CE39
0x14004ce0c  nop     dword ptr [rax+00h]
0x14004ce10  movzx   edx, byte ptr [r10]
0x14004ce14  lea     r10, [r10+1]
0x14004ce18  mov     rcx, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x14004ce1f  movzx   r8d, ax
0x14004ce23  shr     r8, 8
0x14004ce27  xor     r8, rdx
0x14004ce2a  shl     ax, 8
0x14004ce2e  xor     ax, [rcx+r8*2]
0x14004ce33  add     r9d, 0FFFFFFFFh
0x14004ce37  jnz     short loc_14004CE10
0x14004ce39  retn
```
