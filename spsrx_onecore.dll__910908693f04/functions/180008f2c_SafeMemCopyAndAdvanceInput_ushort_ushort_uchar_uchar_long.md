# SafeMemCopyAndAdvanceInput<ushort>(ushort *,uchar * &,uchar *,long)

- ea: `0x180008f2c`
- end: `0x180008f9d`
- name: `??$SafeMemCopyAndAdvanceInput@G@@YAJPEAGAEAPEAEPEAEJ@Z`
- size: `113`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b208`
- `0x18000e9a0`
- `0x18000ea18`
- `0x18000ecd4`

## callees

- `0x180002fb0`
- `0x180008f2c`

## pseudocode

```c
int __fastcall SafeMemCopyAndAdvanceInput<unsigned short>(void *a1, const void *const *a2, const void *a3, int a4)
{
  rsize_t v5; // rbx
  int result; // eax
  bool v7; // sf

  if ( a4 < 1 )
    return -2147024809;
  if ( a3 <= *a2 )
    return -2147024809;
  if ( !a1 )
    return -2147024809;
  if ( !*a2 )
    return -2147024809;
  if ( !a3 )
    return -2147024809;
  v5 = 2LL * a4;
  if ( !v5 || (unsigned __int64)a3 - (unsigned __int64)*a2 < v5 )
    return -2147024809;
  result = memcpy_s(a1, v5, *a2, 2LL * a4);
  v7 = result < 0;
  if ( !result )
  {
    result = 0;
LABEL_14:
    *a2 = (char *)*a2 + v5;
    return result;
  }
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v7 = result < 0;
  }
  if ( !v7 )
    goto LABEL_14;
  return result;
}

```

## disassembly

```asm
0x180008f2c  mov     [rsp+arg_0], rbx
0x180008f31  push    rdi
0x180008f32  sub     rsp, 20h
0x180008f36  mov     rdi, rdx
0x180008f39  cmp     r9d, 1
0x180008f3d  jl      short loc_180008F8D
0x180008f3f  cmp     r8, [rdx]
0x180008f42  jbe     short loc_180008F8D
0x180008f44  test    rcx, rcx
0x180008f47  jz      short loc_180008F8D
0x180008f49  cmp     qword ptr [rdx], 0
0x180008f4d  jz      short loc_180008F8D
0x180008f4f  test    r8, r8
0x180008f52  jz      short loc_180008F8D
0x180008f54  movsxd  rbx, r9d
0x180008f57  add     rbx, rbx
0x180008f5a  jz      short loc_180008F8D
0x180008f5c  sub     r8, [rdx]
0x180008f5f  cmp     r8, rbx
0x180008f62  jb      short loc_180008F8D
0x180008f64  mov     r8, [rdx]; Source
0x180008f67  mov     r9, rbx; SourceSize
0x180008f6a  mov     rdx, rbx; DestinationSize
0x180008f6d  call    memcpy_s
0x180008f72  test    eax, eax
0x180008f74  jz      short loc_180008F86
0x180008f76  jle     short loc_180008F82
0x180008f78  movzx   eax, ax
0x180008f7b  or      eax, 80070000h
0x180008f80  test    eax, eax
0x180008f82  js      short loc_180008F92
0x180008f84  jmp     short loc_180008F88
0x180008f86  xor     eax, eax
0x180008f88  add     [rdi], rbx
0x180008f8b  jmp     short loc_180008F92
0x180008f8d  mov     eax, 80070057h
0x180008f92  mov     rbx, [rsp+28h+arg_0]
0x180008f97  add     rsp, 20h
0x180008f9b  pop     rdi
0x180008f9c  retn
```
