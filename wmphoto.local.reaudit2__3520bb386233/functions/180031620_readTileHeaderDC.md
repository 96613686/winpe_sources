# readTileHeaderDC

- ea: `0x180031620`
- end: `0x180031696`
- name: `readTileHeaderDC`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800094bc`

## callees

- `0x18001190c`
- `0x180031620`
- `0x18003f748`

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
0x180031620  mov     [rsp+arg_0], rbx
0x180031625  push    rdi
0x180031626  sub     rsp, 30h
0x18003162a  test    byte ptr [rcx+85ECh], 1
0x180031631  mov     rdi, rcx
0x180031634  jnz     short loc_180031644
0x180031636  mov     rbx, [rsp+38h+arg_0]
0x18003163b  xor     eax, eax
0x18003163d  add     rsp, 30h
0x180031641  pop     rdi
0x180031642  retn
0x180031644  imul    rbx, [rcx+8658h], 1B0h
0x18003164f  mov     r8, [rcx+85C0h]
0x180031656  xor     r9d, r9d
0x180031659  add     rbx, [rcx+86A0h]
0x180031660  mov     rcx, rbx
0x180031663  call    readQuantizer
0x180031668  mov     [rbx+18Ch], al
0x18003166e  xor     r9d, r9d
0x180031671  mov     edx, [rdi+85B0h]
0x180031677  mov     rcx, rbx
0x18003167a  mov     r8, [rdi+85C0h]
0x180031681  mov     [rsp+38h+var_10], edx
0x180031685  mov     dl, al
0x180031687  mov     [rsp+38h+var_18], 1
0x18003168f  call    formatQuantizer
0x180031694  jmp     short loc_180031636
```
