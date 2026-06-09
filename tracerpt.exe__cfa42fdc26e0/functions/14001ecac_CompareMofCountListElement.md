# CompareMofCountListElement

- ea: `0x14001ecac`
- end: `0x14001ed34`
- name: `CompareMofCountListElement`
- size: `136`
- prototype: `__int64 __fastcall(_QWORD **, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400273e0`

## callees

- `0x14001ecac`

## pseudocode

```c
__int64 __fastcall CompareMofCountListElement(_QWORD **a1, int a2, int a3)
{
  _QWORD *v3; // r9
  int v5; // ecx
  unsigned int v6; // r10d
  _QWORD *v8; // rax
  _QWORD *v9; // r8
  __int64 result; // rax
  int v11; // edx
  _QWORD *v12; // rcx

  v3 = *a1;
  v5 = 0;
  v6 = 0;
  v8 = v3;
  if ( a1 == v3 )
    goto LABEL_6;
  do
  {
    v9 = v8;
    if ( v5 == a2 )
      break;
    v8 = (_QWORD *)*v8;
    ++v5;
  }
  while ( a1 != v8 );
  if ( !v9 )
  {
LABEL_6:
    result = 0;
    v11 = 0;
    if ( a1 == v3 )
      return result;
  }
  else
  {
    v6 = *((unsigned __int8 *)v9 + 26) + (*((unsigned __int16 *)v9 + 12) << 8);
    LODWORD(result) = 0;
    v11 = 0;
  }
  do
  {
    v12 = v3;
    if ( v11 == a3 )
      break;
    v3 = (_QWORD *)*v3;
    ++v11;
  }
  while ( a1 != v3 );
  if ( v12 )
    LODWORD(result) = *((unsigned __int8 *)v12 + 26) + (*((unsigned __int16 *)v12 + 12) << 8);
  if ( v6 <= (unsigned int)result )
    return (unsigned int)-(v6 < (unsigned int)result);
  else
    return 1;
}

```

## disassembly

```asm
0x14001ecac  mov     [rsp+arg_0], rbx
0x14001ecb1  mov     r9, [rcx]
0x14001ecb4  mov     r11, rcx
0x14001ecb7  xor     ecx, ecx
0x14001ecb9  xor     r10d, r10d
0x14001ecbc  mov     ebx, r8d
0x14001ecbf  mov     rax, r9
0x14001ecc2  cmp     r11, r9
0x14001ecc5  jz      short loc_14001ECF4
0x14001ecc7  mov     r8, rax
0x14001ecca  cmp     ecx, edx
0x14001eccc  jz      short loc_14001ECD8
0x14001ecce  mov     rax, [rax]
0x14001ecd1  inc     ecx
0x14001ecd3  cmp     r11, rax
0x14001ecd6  jnz     short loc_14001ECC7
0x14001ecd8  test    r8, r8
0x14001ecdb  jz      short loc_14001ECF4
0x14001ecdd  movzx   eax, byte ptr [r8+1Ah]
0x14001ece2  movzx   r10d, word ptr [r8+18h]
0x14001ece7  shl     r10d, 8
0x14001eceb  add     r10d, eax
0x14001ecee  xor     eax, eax
0x14001ecf0  xor     edx, edx
0x14001ecf2  jmp     short loc_14001ECFD
0x14001ecf4  xor     eax, eax
0x14001ecf6  xor     edx, edx
0x14001ecf8  cmp     r11, r9
0x14001ecfb  jz      short loc_14001ED2E
0x14001ecfd  mov     rcx, r9
0x14001ed00  cmp     edx, ebx
0x14001ed02  jz      short loc_14001ED0E
0x14001ed04  mov     r9, [r9]
0x14001ed07  inc     edx
0x14001ed09  cmp     r11, r9
0x14001ed0c  jnz     short loc_14001ECFD
0x14001ed0e  test    rcx, rcx
0x14001ed11  jz      short loc_14001ED20
0x14001ed13  movzx   eax, word ptr [rcx+18h]
0x14001ed17  movzx   ecx, byte ptr [rcx+1Ah]
0x14001ed1b  shl     eax, 8
0x14001ed1e  add     eax, ecx
0x14001ed20  cmp     r10d, eax
0x14001ed23  jbe     short loc_14001ED2C
0x14001ed25  mov     eax, 1
0x14001ed2a  jmp     short loc_14001ED2E
0x14001ed2c  sbb     eax, eax
0x14001ed2e  mov     rbx, [rsp+arg_0]
0x14001ed33  retn
```
