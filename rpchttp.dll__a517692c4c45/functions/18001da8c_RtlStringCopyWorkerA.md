# RtlStringCopyWorkerA

- ea: `0x18001da8c`
- end: `0x18001dad5`
- name: `RtlStringCopyWorkerA`
- size: `73`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18001d2b8`
- `0x18001d380`
- `0x18001da1c`

## callees

- `0x18001da8c`

## pseudocode

```c
__int64 __fastcall RtlStringCopyWorkerA(_BYTE *a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  __int64 i; // rax
  _BYTE *v6; // rcx
  __int64 result; // rax

  for ( i = 2147483646; a2; --a2 )
  {
    if ( !i )
      break;
    if ( !*a4 )
      break;
    *a1++ = *a4++;
    --i;
  }
  v6 = a1 - 1;
  result = a2 == 0 ? 0x80000005 : 0;
  if ( a2 )
    v6 = a1;
  *v6 = 0;
  return result;
}

```

## disassembly

```asm
0x18001da8c  mov     r8, rcx
0x18001da8f  mov     eax, 7FFFFFFEh
0x18001da94  test    rdx, rdx
0x18001da97  jz      short loc_18001DAB7
0x18001da99  test    rax, rax
0x18001da9c  jz      short loc_18001DAB7
0x18001da9e  mov     cl, [r9]
0x18001daa1  test    cl, cl
0x18001daa3  jz      short loc_18001DAB7
0x18001daa5  mov     [r8], cl
0x18001daa8  inc     r9
0x18001daab  inc     r8
0x18001daae  dec     rax
0x18001dab1  sub     rdx, 1
0x18001dab5  jnz     short loc_18001DA99
0x18001dab7  mov     rax, rdx
0x18001daba  lea     rcx, [r8-1]
0x18001dabe  neg     rax
0x18001dac1  sbb     eax, eax
0x18001dac3  not     eax
0x18001dac5  and     eax, 80000005h
0x18001daca  test    rdx, rdx
0x18001dacd  cmovnz  rcx, r8
0x18001dad1  mov     byte ptr [rcx], 0
0x18001dad4  retn
```
