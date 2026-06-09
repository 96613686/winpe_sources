# SlbNatFindExternalAddress

- ea: `0x140035948`
- end: `0x14003597e`
- name: `SlbNatFindExternalAddress`
- size: `54`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140007bb0`
- `0x14000975c`
- `0x140014dcc`
- `0x140032118`
- `0x140033444`
- `0x1400338a0`

## callees

- `0x140035948`

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
  for ( result = (PVOID *)qword_140027358; result != &qword_140027358; result = (PVOID *)*result )
  {
    if ( *((_DWORD *)result + 12) == a2 )
      return result;
  }
  return 0;
}

```

## disassembly

```asm
0x140035948  add     rcx, 18h
0x14003594c  mov     rax, [rcx]
0x14003594f  cmp     rax, rcx
0x140035952  jz      short loc_14003595E
0x140035954  cmp     [rax+30h], edx
0x140035957  jz      short locret_14003597D
0x140035959  mov     rax, [rax]
0x14003595c  jmp     short loc_14003594F
0x14003595e  mov     rax, cs:qword_140027358
0x140035965  lea     rcx, qword_140027358
0x14003596c  cmp     rax, rcx
0x14003596f  jz      short loc_14003597B
0x140035971  cmp     [rax+30h], edx
0x140035974  jz      short locret_14003597D
0x140035976  mov     rax, [rax]
0x140035979  jmp     short loc_140035965
0x14003597b  xor     eax, eax
0x14003597d  retn
```
