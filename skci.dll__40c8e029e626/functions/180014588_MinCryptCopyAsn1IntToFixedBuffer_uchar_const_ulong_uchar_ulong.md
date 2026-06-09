# MinCryptCopyAsn1IntToFixedBuffer(uchar const *,ulong,uchar *,ulong)

- ea: `0x180014588`
- end: `0x1800145eb`
- name: `?MinCryptCopyAsn1IntToFixedBuffer@@YAJPEBEKPEAEK@Z`
- size: `99`
- prototype: `__int64 __fastcall(const unsigned __int8 *Src, size_t MaxCount, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014748`

## callees

- `0x180014588`
- `0x18003392c`
- `0x180033950`

## pseudocode

```c
__int64 __fastcall MinCryptCopyAsn1IntToFixedBuffer(
        const unsigned __int8 *Src,
        size_t MaxCount,
        unsigned __int8 *a3,
        unsigned int a4)
{
  __int64 v4; // rbp
  unsigned int v6; // ebx
  unsigned int v8; // esi

  v4 = a4;
  v6 = MaxCount;
  v8 = 0;
  while ( v6 > a4 )
  {
    if ( *Src )
      return (unsigned int)-1073740760;
    ++Src;
    --v6;
  }
  if ( v6 < a4 )
    memset_0(a3, 0, a4 - v6);
  memcpy_0(&a3[v4 - v6], Src, v6);
  return v8;
}

```

## disassembly

```asm
0x180014588  push    rbx
0x18001458a  push    rbp
0x18001458b  push    rsi
0x18001458c  push    rdi
0x18001458d  push    r14
0x18001458f  sub     rsp, 20h
0x180014593  mov     ebp, r9d
0x180014596  mov     r14, r8
0x180014599  mov     ebx, edx
0x18001459b  mov     rdi, rcx
0x18001459e  xor     esi, esi
0x1800145a0  cmp     ebx, ebp
0x1800145a2  jbe     short loc_1800145B7
0x1800145a4  cmp     [rdi], sil
0x1800145a7  jnz     short loc_1800145B0
0x1800145a9  inc     rdi
0x1800145ac  dec     ebx
0x1800145ae  jmp     short loc_1800145A0
0x1800145b0  mov     esi, 0C0000428h
0x1800145b5  jmp     short loc_1800145DD
0x1800145b7  jnb     short loc_1800145C9
0x1800145b9  mov     r8d, ebp
0x1800145bc  xor     edx, edx; Val
0x1800145be  sub     r8d, ebx; Size
0x1800145c1  mov     rcx, r14; void *
0x1800145c4  call    memset_0
0x1800145c9  mov     r8d, ebx; MaxCount
0x1800145cc  mov     rcx, rbp
0x1800145cf  sub     rcx, r8
0x1800145d2  mov     rdx, rdi; Src
0x1800145d5  add     rcx, r14; void *
0x1800145d8  call    memcpy_0
0x1800145dd  mov     eax, esi
0x1800145df  add     rsp, 20h
0x1800145e3  pop     r14
0x1800145e5  pop     rdi
0x1800145e6  pop     rsi
0x1800145e7  pop     rbp
0x1800145e8  pop     rbx
0x1800145e9  retn
```
