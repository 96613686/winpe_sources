# RtlStringCbCopyW

- ea: `0x180013e20`
- end: `0x180013e8c`
- name: `RtlStringCbCopyW`
- size: `108`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int64, _WORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800024d0`

## callees

- `0x180013e20`

## pseudocode

```c
__int64 __fastcall RtlStringCbCopyW(_WORD *a1, unsigned __int64 a2, _WORD *a3)
{
  unsigned __int64 v3; // rdx
  __int64 result; // rax
  __int64 v5; // rax
  _WORD *v6; // rax

  v3 = a2 >> 1;
  if ( !v3 )
    return 3221225485LL;
  if ( v3 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *a1++ = *a3++;
      --v5;
      --v3;
    }
    while ( v3 );
    v6 = a1 - 1;
    if ( v3 )
      v6 = a1;
    *v6 = 0;
    return v3 == 0 ? 0x80000005 : 0;
  }
  else
  {
    result = 3221225485LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180013e20  xor     r9d, r9d
0x180013e23  shr     rdx, 1
0x180013e26  jz      short loc_180013E7D
0x180013e28  cmp     rdx, 7FFFFFFFh
0x180013e2f  jbe     short loc_180013E38
0x180013e31  mov     eax, 0C000000Dh
0x180013e36  jmp     short loc_180013E87
0x180013e38  mov     eax, 7FFFFFFEh
0x180013e3d  test    rax, rax
0x180013e40  jz      short loc_180013E61
0x180013e42  movzx   r10d, word ptr [r8]
0x180013e46  test    r10w, r10w
0x180013e4a  jz      short loc_180013E61
0x180013e4c  mov     [rcx], r10w
0x180013e50  add     r8, 2
0x180013e54  add     rcx, 2
0x180013e58  dec     rax
0x180013e5b  sub     rdx, 1
0x180013e5f  jnz     short loc_180013E3D
0x180013e61  test    rdx, rdx
0x180013e64  lea     rax, [rcx-2]
0x180013e68  cmovnz  rax, rcx
0x180013e6c  neg     rdx
0x180013e6f  mov     [rax], r9w
0x180013e73  sbb     eax, eax
0x180013e75  not     eax
0x180013e77  and     eax, 80000005h
0x180013e7c  retn
0x180013e7d  mov     eax, 0C000000Dh
0x180013e82  test    rdx, rdx
0x180013e85  jz      short locret_180013E8B
0x180013e87  mov     [rcx], r9w
0x180013e8b  retn
```
