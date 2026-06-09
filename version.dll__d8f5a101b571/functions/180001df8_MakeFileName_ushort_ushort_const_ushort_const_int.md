# MakeFileName(ushort *,ushort const *,ushort const *,int)

- ea: `0x180001df8`
- end: `0x180001ea8`
- name: `?MakeFileName@@YA_KPEAGPEBG1H@Z`
- size: `176`
- prototype: `unsigned __int64 __fastcall(unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002b00`

## callees

- `0x180001df8`
- `0x180001eb0`

## pseudocode

```c
__int64 __fastcall MakeFileName(unsigned __int16 *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 v5; // r9
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // r11

  v5 = -1;
  v6 = 0;
  do
    ++v5;
  while ( a2[v5] );
  v7 = -1;
  do
    ++v7;
  while ( a3[v7] );
  *a1 = 0;
  if ( (unsigned __int64)(v7 + v5 + 2) <= 0x104 )
  {
    StringCchCopyW(a1, 0x104u, a2);
    a1[259] = 0;
    v6 = -1;
    do
      ++v6;
    while ( a1[v6] );
    if ( v6 && a1[v6 - 1] != 92 && a1[v6 - 1] != 58 )
      a1[v6++] = 92;
    StringCchCopyW(&a1[v6], v8 - v6, a3);
    a1[259] = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180001df8  push    rbx
0x180001dfa  push    rbp
0x180001dfb  push    rsi
0x180001dfc  push    rdi
0x180001dfd  push    r14
0x180001dff  sub     rsp, 20h
0x180001e03  xor     ebp, ebp
0x180001e05  mov     rsi, r8
0x180001e08  or      r14, 0FFFFFFFFFFFFFFFFh
0x180001e0c  mov     rdi, rcx
0x180001e0f  mov     r9, r14
0x180001e12  mov     ebx, ebp
0x180001e14  inc     r9
0x180001e17  cmp     [rdx+r9*2], bp
0x180001e1c  jnz     short loc_180001E14
0x180001e1e  mov     rcx, r14
0x180001e21  inc     rcx
0x180001e24  cmp     [r8+rcx*2], bp
0x180001e29  jnz     short loc_180001E21
0x180001e2b  lea     rax, [r9+2]
0x180001e2f  mov     [rdi], bp
0x180001e32  add     rax, rcx
0x180001e35  mov     r11d, 104h
0x180001e3b  cmp     rax, r11
0x180001e3e  ja      short loc_180001E9A
0x180001e40  mov     r8, rdx; unsigned __int16 *
0x180001e43  mov     rcx, rdi; unsigned __int16 *
0x180001e46  mov     edx, r11d; unsigned __int64
0x180001e49  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001e4e  mov     [rdi+206h], bp
0x180001e55  mov     rbx, r14
0x180001e58  inc     rbx
0x180001e5b  cmp     [rdi+rbx*2], bp
0x180001e5f  jnz     short loc_180001E58
0x180001e61  test    rbx, rbx
0x180001e64  jz      short loc_180001E81
0x180001e66  mov     eax, 5Ch ; '\'
0x180001e6b  cmp     [rdi+rbx*2-2], ax
0x180001e70  jz      short loc_180001E81
0x180001e72  cmp     word ptr [rdi+rbx*2-2], 3Ah ; ':'
0x180001e78  jz      short loc_180001E81
0x180001e7a  mov     [rdi+rbx*2], ax
0x180001e7e  inc     rbx
0x180001e81  sub     r11, rbx
0x180001e84  lea     rcx, [rdi+rbx*2]; unsigned __int16 *
0x180001e88  mov     rdx, r11; unsigned __int64
0x180001e8b  mov     r8, rsi; unsigned __int16 *
0x180001e8e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001e93  mov     [rdi+206h], bp
0x180001e9a  mov     rax, rbx
0x180001e9d  add     rsp, 20h
0x180001ea1  pop     r14
0x180001ea3  pop     rdi
0x180001ea4  pop     rsi
0x180001ea5  pop     rbp
0x180001ea6  pop     rbx
0x180001ea7  retn
```
