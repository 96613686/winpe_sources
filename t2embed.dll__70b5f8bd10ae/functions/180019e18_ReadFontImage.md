# ReadFontImage

- ea: `0x180019e18`
- end: `0x180019ee4`
- name: `ReadFontImage`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800190a4`

## callees

- `0x180017ee0`
- `0x180019dc0`
- `0x180019e18`
- `0x18001ac80`
- `0x18001bff0`
- `0x18002a54e`

## pseudocode

```c
__int64 __fastcall ReadFontImage(__int64 a1, unsigned int a2, int a3, __int64 a4, __int64 a5)
{
  void *v8; // rbx
  int i; // edi
  unsigned int v11; // ebp

  if ( !a3 )
    return a2 != (unsigned int)T2OSSvcReadFontData(a4, a5, a1, a2) ? 0x107 : 0;
  v8 = (void *)T2malloc(0xFFFFu);
  if ( !v8 )
    return 266;
  for ( i = a2; i; i -= v11 )
  {
    v11 = 0xFFFF;
    if ( i < 0xFFFF )
      v11 = i;
    if ( (unsigned int)T2OSSvcReadFontData(a4, a5, v8, v11) != v11 )
    {
      T2free(v8);
      return 263;
    }
    XORBufferData(v8, v11);
    memcpy_0((void *)(a1 + a2 - i), v8, v11);
  }
  T2free(v8);
  return 0;
}

```

## disassembly

```asm
0x180019e18  push    rbx
0x180019e1a  push    rbp
0x180019e1b  push    rsi
0x180019e1c  push    rdi
0x180019e1d  push    r14
0x180019e1f  push    r15
0x180019e21  sub     rsp, 38h
0x180019e25  mov     r15, r9
0x180019e28  mov     esi, edx
0x180019e2a  mov     r14, rcx
0x180019e2d  test    r8d, r8d
0x180019e30  jz      loc_180019EB6
0x180019e36  xor     edx, edx
0x180019e38  mov     ecx, 0FFFFh; dwBytes
0x180019e3d  call    T2malloc
0x180019e42  mov     rbx, rax
0x180019e45  test    rax, rax
0x180019e48  jnz     short loc_180019E54
0x180019e4a  mov     eax, 10Ah
0x180019e4f  jmp     loc_180019ED7
0x180019e54  mov     edi, esi
0x180019e56  test    edi, edi
0x180019e58  jz      short loc_180019EAA
0x180019e5a  mov     rdx, [rsp+68h+arg_20]
0x180019e62  mov     ebp, 0FFFFh
0x180019e67  cmp     edi, ebp
0x180019e69  mov     r8, rbx
0x180019e6c  mov     rcx, r15
0x180019e6f  cmovl   ebp, edi
0x180019e72  mov     r9d, ebp
0x180019e75  call    T2OSSvcReadFontData
0x180019e7a  mov     rcx, rbx; lpMem
0x180019e7d  cmp     eax, ebp
0x180019e7f  jnz     short loc_180019E9E
0x180019e81  mov     edx, ebp
0x180019e83  call    XORBufferData
0x180019e88  mov     ecx, esi
0x180019e8a  mov     r8d, ebp; Size
0x180019e8d  sub     ecx, edi
0x180019e8f  mov     rdx, rbx; Src
0x180019e92  add     rcx, r14; void *
0x180019e95  call    memcpy_0
0x180019e9a  sub     edi, ebp
0x180019e9c  jmp     short loc_180019E56
0x180019e9e  call    T2free
0x180019ea3  mov     eax, 107h
0x180019ea8  jmp     short loc_180019ED7
0x180019eaa  mov     rcx, rbx; lpMem
0x180019ead  call    T2free
0x180019eb2  xor     eax, eax
0x180019eb4  jmp     short loc_180019ED7
0x180019eb6  mov     rdx, [rsp+68h+arg_20]
0x180019ebe  mov     r9d, esi
0x180019ec1  mov     r8, r14
0x180019ec4  mov     rcx, r15
0x180019ec7  call    T2OSSvcReadFontData
0x180019ecc  sub     eax, esi
0x180019ece  neg     eax
0x180019ed0  sbb     eax, eax
0x180019ed2  and     eax, 107h
0x180019ed7  add     rsp, 38h
0x180019edb  pop     r15
0x180019edd  pop     r14
0x180019edf  pop     rdi
0x180019ee0  pop     rsi
0x180019ee1  pop     rbp
0x180019ee2  pop     rbx
0x180019ee3  retn
```
