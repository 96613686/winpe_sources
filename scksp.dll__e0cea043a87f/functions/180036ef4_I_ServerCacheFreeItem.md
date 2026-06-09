# I_ServerCacheFreeItem

- ea: `0x180036ef4`
- end: `0x180036f75`
- name: `I_ServerCacheFreeItem`
- size: `129`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180036e68`
- `0x180036f7c`
- `0x180037a4c`

## callees

- `0x180036ef4`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall I_ServerCacheFreeItem(__int64 a1, __int64 a2)
{
  void (**v4)(void); // rdi
  __int64 v5; // rbp
  void (__fastcall **v6)(_QWORD); // rax

  v4 = (void (**)(void))(a1 + 56);
  if ( *(_QWORD *)a2 )
    (*v4)();
  if ( *(_QWORD *)(a2 + 40) )
    (*v4)();
  if ( *(_QWORD *)(a2 + 64) )
  {
    v5 = 0;
    if ( *(_DWORD *)(a2 + 72) )
    {
      do
      {
        ((void (__fastcall *)(_QWORD))*v4)(*(_QWORD *)(*(_QWORD *)(a2 + 64) + 8 * v5));
        v5 = (unsigned int)(v5 + 1);
      }
      while ( (unsigned int)v5 < *(_DWORD *)(a2 + 72) );
      v6 = (void (__fastcall **)(_QWORD))(a1 + 56);
    }
    else
    {
      v6 = (void (__fastcall **)(_QWORD))(a1 + 56);
    }
    (*v6)(*(_QWORD *)(a2 + 64));
  }
  return ((__int64 (__fastcall *)(__int64))*v4)(a2);
}

```

## disassembly

```asm
0x180036ef4  push    rbx
0x180036ef6  push    rbp
0x180036ef7  push    rsi
0x180036ef8  push    rdi
0x180036ef9  sub     rsp, 28h
0x180036efd  mov     rsi, rcx
0x180036f00  mov     rbx, rdx
0x180036f03  mov     rcx, [rdx]
0x180036f06  lea     rdi, [rsi+38h]
0x180036f0a  test    rcx, rcx
0x180036f0d  jz      short loc_180036F17
0x180036f0f  mov     rax, [rdi]
0x180036f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f17  mov     rcx, [rbx+28h]
0x180036f1b  test    rcx, rcx
0x180036f1e  jz      short loc_180036F28
0x180036f20  mov     rax, [rdi]
0x180036f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f28  cmp     qword ptr [rbx+40h], 0
0x180036f2d  jz      short loc_180036F62
0x180036f2f  xor     ebp, ebp
0x180036f31  cmp     [rbx+48h], ebp
0x180036f34  jbe     short loc_180036F53
0x180036f36  mov     rcx, [rbx+40h]
0x180036f3a  mov     rax, [rdi]
0x180036f3d  mov     rcx, [rcx+rbp*8]
0x180036f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f46  inc     ebp
0x180036f48  cmp     ebp, [rbx+48h]
0x180036f4b  jb      short loc_180036F36
0x180036f4d  lea     rax, [rsi+38h]
0x180036f51  jmp     short loc_180036F56
0x180036f53  mov     rax, rdi
0x180036f56  mov     rcx, [rbx+40h]
0x180036f5a  mov     rax, [rax]
0x180036f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f62  mov     rax, [rdi]
0x180036f65  mov     rcx, rbx
0x180036f68  add     rsp, 28h
0x180036f6c  pop     rdi
0x180036f6d  pop     rsi
0x180036f6e  pop     rbp
0x180036f6f  pop     rbx
0x180036f70  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
