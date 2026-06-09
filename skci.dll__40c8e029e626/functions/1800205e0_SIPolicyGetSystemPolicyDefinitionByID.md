# SIPolicyGetSystemPolicyDefinitionByID

- ea: `0x1800205e0`
- end: `0x18002061c`
- name: `SIPolicyGetSystemPolicyDefinitionByID`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001a004`
- `0x180020624`

## callees

- `0x1800205e0`

## pseudocode

```c
__int64 *__fastcall SIPolicyGetSystemPolicyDefinitionByID(_QWORD *a1)
{
  unsigned __int64 i; // rdx
  __int64 *v3; // r8
  __int64 v4; // rcx

  for ( i = 0; i < 0xC; ++i )
  {
    v3 = &qword_1800367A0[9 * i];
    v4 = *a1 - *v3;
    if ( *a1 == *v3 )
      v4 = a1[1] - v3[1];
    if ( !v4 )
      return &qword_1800367A0[9 * i];
  }
  return 0;
}

```

## disassembly

```asm
0x1800205e0  mov     r9, rcx
0x1800205e3  xor     edx, edx
0x1800205e5  cmp     rdx, 0Ch
0x1800205e9  jnb     short loc_180020619
0x1800205eb  lea     rcx, qword_1800367A0
0x1800205f2  lea     rax, [rdx+rdx*8]
0x1800205f6  lea     r8, [rcx+rax*8]
0x1800205fa  mov     rcx, [r9]
0x1800205fd  sub     rcx, [r8]
0x180020600  jnz     short loc_18002060A
0x180020602  mov     rcx, [r9+8]
0x180020606  sub     rcx, [r8+8]
0x18002060a  test    rcx, rcx
0x18002060d  jz      short loc_180020614
0x18002060f  inc     rdx
0x180020612  jmp     short loc_1800205E5
0x180020614  mov     rax, r8
0x180020617  retn
0x180020619  xor     eax, eax
0x18002061b  retn
```
