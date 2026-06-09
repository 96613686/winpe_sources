# CAttributeString::CompareStringW(ushort const *,ushort const *)

- ea: `0x18000e59c`
- end: `0x18000e5d5`
- name: `?CompareStringW@CAttributeString@@SAHPEBG0@Z`
- size: `57`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009a44`
- `0x18000e5dc`

## callees

- `0x18000e59c`

## pseudocode

```c
_BOOL8 __fastcall CAttributeString::CompareStringW(char *a1, char *a2)
{
  signed __int64 v2; // rdx
  int v3; // eax
  int v4; // r8d

  if ( a1 == a2 )
    return 1;
  if ( !a1 || !a2 )
    return 0;
  v2 = a2 - a1;
  do
  {
    v3 = *(unsigned __int16 *)&a1[v2];
    v4 = *(unsigned __int16 *)a1 - v3;
    if ( v4 )
      break;
    a1 += 2;
  }
  while ( v3 );
  return v4 == 0;
}

```

## disassembly

```asm
0x18000e59c  cmp     rcx, rdx
0x18000e59f  jz      short loc_18000E5CF
0x18000e5a1  test    rcx, rcx
0x18000e5a4  jz      short loc_18000E5CC
0x18000e5a6  test    rdx, rdx
0x18000e5a9  jz      short loc_18000E5CC
0x18000e5ab  sub     rdx, rcx
0x18000e5ae  movzx   r8d, word ptr [rcx]
0x18000e5b2  movzx   eax, word ptr [rcx+rdx]
0x18000e5b6  sub     r8d, eax
0x18000e5b9  jnz     short loc_18000E5C3
0x18000e5bb  add     rcx, 2
0x18000e5bf  test    eax, eax
0x18000e5c1  jnz     short loc_18000E5AE
0x18000e5c3  xor     eax, eax
0x18000e5c5  test    r8d, r8d
0x18000e5c8  setz    al
0x18000e5cb  retn
0x18000e5cc  xor     eax, eax
0x18000e5ce  retn
0x18000e5cf  mov     eax, 1
0x18000e5d4  retn
```
