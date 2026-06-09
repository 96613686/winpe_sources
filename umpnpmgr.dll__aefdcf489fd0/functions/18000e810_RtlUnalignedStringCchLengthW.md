# RtlUnalignedStringCchLengthW

- ea: `0x18000e810`
- end: `0x18000e87e`
- name: `RtlUnalignedStringCchLengthW`
- size: `110`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int64, _QWORD *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180001190`
- `0x1800056d0`
- `0x1800126cc`
- `0x180014a84`
- `0x1800156c0`

## callees

- `0x18000e810`

## pseudocode

```c
__int64 __fastcall RtlUnalignedStringCchLengthW(_WORD *a1, unsigned __int64 a2, _QWORD *a3)
{
  int v3; // r9d
  unsigned __int64 v4; // rax

  if ( !a1 || a2 > 0x7FFFFFFF )
  {
    v3 = -1073741811;
LABEL_11:
    if ( a3 )
      *a3 = 0;
    return (unsigned int)v3;
  }
  v3 = 0;
  v4 = a2;
  if ( a2 )
  {
    while ( *a1 )
    {
      ++a1;
      if ( !--v4 )
        goto LABEL_6;
    }
  }
  else
  {
LABEL_6:
    v3 = -1073741811;
  }
  if ( a3 )
  {
    if ( v3 < 0 )
      *a3 = 0;
    else
      *a3 = a2 - v4;
  }
  if ( v3 < 0 )
    goto LABEL_11;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000e810  test    rcx, rcx
0x18000e813  jz      short loc_18000E854
0x18000e815  cmp     rdx, 7FFFFFFFh
0x18000e81c  ja      short loc_18000E854
0x18000e81e  xor     r9d, r9d
0x18000e821  mov     rax, rdx
0x18000e824  test    rdx, rdx
0x18000e827  jz      short loc_18000E840
0x18000e829  nop     dword ptr [rax+00000000h]
0x18000e830  cmp     [rcx], r9w
0x18000e834  jz      short loc_18000E846
0x18000e836  add     rcx, 2
0x18000e83a  sub     rax, 1
0x18000e83e  jnz     short loc_18000E830
0x18000e840  mov     r9d, 0C000000Dh
0x18000e846  test    r8, r8
0x18000e849  jnz     short loc_18000E868
0x18000e84b  test    r9d, r9d
0x18000e84e  js      short loc_18000E85A
0x18000e850  mov     eax, r9d
0x18000e853  retn
0x18000e854  mov     r9d, 0C000000Dh
0x18000e85a  test    r8, r8
0x18000e85d  jz      short loc_18000E850
0x18000e85f  mov     qword ptr [r8], 0
0x18000e866  jmp     short loc_18000E850
0x18000e868  test    r9d, r9d
0x18000e86b  js      short loc_18000E875
0x18000e86d  sub     rdx, rax
0x18000e870  mov     [r8], rdx
0x18000e873  jmp     short loc_18000E84B
0x18000e875  mov     qword ptr [r8], 0
0x18000e87c  jmp     short loc_18000E84B
```
