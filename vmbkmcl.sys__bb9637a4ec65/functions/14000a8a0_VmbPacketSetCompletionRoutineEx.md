# VmbPacketSetCompletionRoutineEx

- ea: `0x14000a8a0`
- end: `0x14000a8be`
- name: `VmbPacketSetCompletionRoutineEx`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000a8a0`

## pseudocode

```c
__int64 __fastcall VmbPacketSetCompletionRoutineEx(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax

  result = (unsigned int)(*(_DWORD *)(a1 + 24) - 1);
  if ( (unsigned int)result > 4 )
    __fastfail(5u);
  *(_BYTE *)(a1 + 62) |= 0x40u;
  *(_QWORD *)(a1 + 88) = a3;
  *(_QWORD *)(a1 + 96) = a2;
  return result;
}

```

## disassembly

```asm
0x14000a8a0  mov     eax, [rcx+18h]
0x14000a8a3  dec     eax
0x14000a8a5  cmp     eax, 4
0x14000a8a8  jbe     short loc_14000A8B1
0x14000a8aa  mov     ecx, 5
0x14000a8af  int     29h; Win8: RtlFailFast(ecx)
0x14000a8b1  or      byte ptr [rcx+3Eh], 40h
0x14000a8b5  mov     [rcx+58h], r8
0x14000a8b9  mov     [rcx+60h], rdx
0x14000a8bd  retn
```
