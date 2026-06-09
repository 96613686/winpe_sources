# SlbNatFindExternalAddress

- ea: `0x140034638`
- end: `0x14003466e`
- name: `SlbNatFindExternalAddress`
- size: `54`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140007bb0`
- `0x14000975c`
- `0x14001448c`
- `0x140030fe8`
- `0x140032314`
- `0x140032770`

## callees

- `0x140034638`

## pseudocode

```c
PVOID *__fastcall SlbNatFindExternalAddress(__int64 a1, int a2)
{
  PVOID *v2; // rcx
  PVOID *result; // rax

  v2 = (PVOID *)(a1 + 24);
  for ( result = (PVOID *)*v2; result != v2; result = (PVOID *)*result )
  {
    if ( *((_DWORD *)result + 12) == a2 )
      return result;
  }
  for ( result = (PVOID *)qword_140026358; result != &qword_140026358; result = (PVOID *)*result )
  {
    if ( *((_DWORD *)result + 12) == a2 )
      return result;
  }
  return 0;
}

```

## disassembly

```asm
0x140034638  add     rcx, 18h
0x14003463c  mov     rax, [rcx]
0x14003463f  cmp     rax, rcx
0x140034642  jz      short loc_14003464E
0x140034644  cmp     [rax+30h], edx
0x140034647  jz      short locret_14003466D
0x140034649  mov     rax, [rax]
0x14003464c  jmp     short loc_14003463F
0x14003464e  mov     rax, cs:qword_140026358
0x140034655  lea     rcx, qword_140026358
0x14003465c  cmp     rax, rcx
0x14003465f  jz      short loc_14003466B
0x140034661  cmp     [rax+30h], edx
0x140034664  jz      short locret_14003466D
0x140034666  mov     rax, [rax]
0x140034669  jmp     short loc_140034655
0x14003466b  xor     eax, eax
0x14003466d  retn
```
