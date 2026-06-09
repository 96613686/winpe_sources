# ARRAY_LIST::DeleteEntry(ulong)

- ea: `0x180003c88`
- end: `0x180003ce3`
- name: `?DeleteEntry@ARRAY_LIST@@QEAAJK@Z`
- size: `91`
- prototype: `__int64 __fastcall(ARRAY_LIST *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006560`

## callees

- `0x180003c88`
- `0x18000c392`
- `0x18000d010`

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
0x180003c88  push    rbx
0x180003c8a  push    rbp
0x180003c8b  push    rsi
0x180003c8c  push    rdi
0x180003c8d  sub     rsp, 28h
0x180003c91  mov     rsi, rcx
0x180003c94  mov     edi, edx
0x180003c96  cmp     edx, [rcx+8]
0x180003c99  jb      short loc_180003CA2
0x180003c9b  mov     ebp, 80070585h
0x180003ca0  jmp     short loc_180003CD8
0x180003ca2  xor     ebp, ebp
0x180003ca4  lfence
0x180003ca7  mov     rax, [rcx]
0x180003caa  mov     rcx, [rax+rdi*8]
0x180003cae  mov     rax, [rcx]
0x180003cb1  mov     rax, [rax]
0x180003cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cb9  mov     rcx, [rsi]
0x180003cbc  lea     rcx, [rcx+rdi*8]; void *
0x180003cc0  not     edi
0x180003cc2  add     edi, [rsi+8]
0x180003cc5  lea     rdx, [rcx+8]; Src
0x180003cc9  mov     r8d, edi
0x180003ccc  shl     r8, 3; Size
0x180003cd0  call    memmove_0
0x180003cd5  dec     dword ptr [rsi+8]
0x180003cd8  mov     eax, ebp
0x180003cda  add     rsp, 28h
0x180003cde  pop     rdi
0x180003cdf  pop     rsi
0x180003ce0  pop     rbp
0x180003ce1  pop     rbx
0x180003ce2  retn
```
