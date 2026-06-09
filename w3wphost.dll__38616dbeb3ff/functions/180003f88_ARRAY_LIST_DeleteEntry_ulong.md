# ARRAY_LIST::DeleteEntry(ulong)

- ea: `0x180003f88`
- end: `0x180003fe4`
- name: `?DeleteEntry@ARRAY_LIST@@QEAAJK@Z`
- size: `92`
- prototype: `__int64 __fastcall(ARRAY_LIST *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006bb0`

## callees

- `0x180003f88`
- `0x18000d2b2`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ARRAY_LIST::DeleteEntry(ARRAY_LIST *this, unsigned int a2)
{
  __int64 v3; // rdi
  unsigned int v4; // ebp
  void (__fastcall ***v5)(_QWORD); // rcx

  v3 = a2;
  if ( a2 < *((_DWORD *)this + 2) )
  {
    v4 = 0;
    _mm_lfence();
    v5 = *(void (__fastcall ****)(_QWORD))(*(_QWORD *)this + 8LL * a2);
    (**v5)(v5);
    memmove_0(
      (void *)(*(_QWORD *)this + 8 * v3),
      (const void *)(*(_QWORD *)this + 8 * v3 + 8),
      8LL * (unsigned int)(*((_DWORD *)this + 2) + ~(_DWORD)v3));
    --*((_DWORD *)this + 2);
  }
  else
  {
    return (unsigned int)-2147023483;
  }
  return v4;
}

```

## disassembly

```asm
0x180003f88  push    rbx
0x180003f8a  push    rbp
0x180003f8b  push    rsi
0x180003f8c  push    rdi
0x180003f8d  sub     rsp, 28h
0x180003f91  mov     rsi, rcx
0x180003f94  mov     edi, edx
0x180003f96  cmp     edx, [rcx+8]
0x180003f99  jb      short loc_180003FA2
0x180003f9b  mov     ebp, 80070585h
0x180003fa0  jmp     short loc_180003FD8
0x180003fa2  xor     ebp, ebp
0x180003fa4  lfence
0x180003fa7  mov     rax, [rcx]
0x180003faa  mov     rcx, [rax+rdi*8]
0x180003fae  mov     rax, [rcx]
0x180003fb1  mov     rax, [rax]
0x180003fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fb9  mov     rcx, [rsi]
0x180003fbc  lea     rcx, [rcx+rdi*8]; void *
0x180003fc0  not     edi
0x180003fc2  add     edi, [rsi+8]
0x180003fc5  lea     rdx, [rcx+8]; Src
0x180003fc9  mov     r8d, edi
0x180003fcc  shl     r8, 3; Size
0x180003fd0  call    memmove_0
0x180003fd5  dec     dword ptr [rsi+8]
0x180003fd8  mov     eax, ebp
0x180003fda  add     rsp, 28h
0x180003fde  pop     rdi
0x180003fdf  pop     rsi
0x180003fe0  pop     rbp
0x180003fe1  pop     rbx
0x180003fe2  retn
```
