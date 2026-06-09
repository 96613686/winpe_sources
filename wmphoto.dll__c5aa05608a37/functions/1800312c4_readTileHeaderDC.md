# readTileHeaderDC

- ea: `0x1800312c4`
- end: `0x180031339`
- name: `readTileHeaderDC`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800093ac`

## callees

- `0x180011738`
- `0x1800312c4`
- `0x18003ef7c`

## pseudocode

```c
__int64 __fastcall readTileHeaderDC(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  char Quantizer; // al
  int v6; // edx

  if ( (*(_BYTE *)(a1 + 34284) & 1) != 0 )
  {
    v4 = *(_QWORD *)(a1 + 34464) + 432LL * *(_QWORD *)(a1 + 34392);
    Quantizer = readQuantizer((_QWORD *)v4, a2, *(_QWORD *)(a1 + 34240), 0);
    *(_BYTE *)(v4 + 396) = Quantizer;
    v6 = *(_DWORD *)(a1 + 34224);
    LOBYTE(v6) = Quantizer;
    formatQuantizer(v4, v6, *(_QWORD *)(a1 + 34240), 0, 1, *(_DWORD *)(a1 + 34224));
  }
  return 0;
}

```

## disassembly

```asm
0x1800312c4  mov     [rsp+arg_0], rbx
0x1800312c9  push    rdi
0x1800312ca  sub     rsp, 30h
0x1800312ce  test    byte ptr [rcx+85ECh], 1
0x1800312d5  mov     rdi, rcx
0x1800312d8  jnz     short loc_1800312E7
0x1800312da  mov     rbx, [rsp+38h+arg_0]
0x1800312df  xor     eax, eax
0x1800312e1  add     rsp, 30h
0x1800312e5  pop     rdi
0x1800312e6  retn
0x1800312e7  imul    rbx, [rcx+8658h], 1B0h
0x1800312f2  mov     r8, [rcx+85C0h]
0x1800312f9  xor     r9d, r9d
0x1800312fc  add     rbx, [rcx+86A0h]
0x180031303  mov     rcx, rbx
0x180031306  call    readQuantizer
0x18003130b  mov     [rbx+18Ch], al
0x180031311  xor     r9d, r9d
0x180031314  mov     edx, [rdi+85B0h]
0x18003131a  mov     rcx, rbx
0x18003131d  mov     r8, [rdi+85C0h]
0x180031324  mov     [rsp+38h+var_10], edx
0x180031328  mov     dl, al
0x18003132a  mov     [rsp+38h+var_18], 1
0x180031332  call    formatQuantizer
0x180031337  jmp     short loc_1800312DA
```
