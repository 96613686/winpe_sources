# VmbPacketSetCompletionRoutine

- ea: `0x1400056c0`
- end: `0x1400056dd`
- name: `VmbPacketSetCompletionRoutine`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400056c0`

## pseudocode

```c
__int64 __fastcall VmbPacketSetCompletionRoutine(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = (unsigned int)(*(_DWORD *)(a1 + 24) - 1);
  if ( (unsigned int)result > 4 )
    __fastfail(5u);
  if ( (*(_BYTE *)(a1 + 62) & 0x40) == 0 )
    *(_QWORD *)(a1 + 88) = a2;
  return result;
}

```

## disassembly

```asm
0x1400056c0  mov     eax, [rcx+18h]
0x1400056c3  dec     eax
0x1400056c5  cmp     eax, 4
0x1400056c8  ja      short loc_1400056D6
0x1400056ca  test    byte ptr [rcx+3Eh], 40h
0x1400056ce  jnz     short locret_1400056D4
0x1400056d0  mov     [rcx+58h], rdx
0x1400056d4  retn
0x1400056d6  mov     ecx, 5
0x1400056db  int     29h; Win8: RtlFailFast(ecx)
```
