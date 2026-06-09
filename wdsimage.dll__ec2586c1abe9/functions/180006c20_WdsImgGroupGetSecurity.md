# WdsImgGroupGetSecurity

- ea: `0x180006c20`
- end: `0x180006c58`
- name: `WdsImgGroupGetSecurity`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006c20`

## pseudocode

```c
__int64 __fastcall WdsImgGroupGetSecurity(__int64 a1, _QWORD *a2)
{
  unsigned int v2; // r8d

  v2 = 0;
  if ( a1 && a2 )
  {
    if ( *(_DWORD *)(a1 + 16) == 2 || *(_DWORD *)(a1 + 16) == 3 )
      *a2 = *(_QWORD *)(a1 + 40);
    else
      return (unsigned int)-1056833019;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v2;
}

```

## disassembly

```asm
0x180006c20  xor     r8d, r8d
0x180006c23  test    rcx, rcx
0x180006c26  jz      short loc_180006C4E
0x180006c28  test    rdx, rdx
0x180006c2b  jz      short loc_180006C4E
0x180006c2d  mov     r9d, [rcx+10h]
0x180006c31  sub     r9d, 2
0x180006c35  jz      short loc_180006C45
0x180006c37  cmp     r9d, 1
0x180006c3b  jz      short loc_180006C45
0x180006c3d  mov     r8d, 0C1020205h
0x180006c43  jmp     short loc_180006C54
0x180006c45  mov     rax, [rcx+28h]
0x180006c49  mov     [rdx], rax
0x180006c4c  jmp     short loc_180006C54
0x180006c4e  mov     r8d, 80070057h
0x180006c54  mov     eax, r8d
0x180006c57  retn
```
