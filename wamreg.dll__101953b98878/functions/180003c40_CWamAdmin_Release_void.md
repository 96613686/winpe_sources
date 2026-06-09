# CWamAdmin::Release(void)

- ea: `0x180003c40`
- end: `0x180003c6f`
- name: `?Release@CWamAdmin@@UEAAKXZ`
- size: `47`
- prototype: `unsigned int __fastcall(CWamAdmin *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003c80`
- `0x180003c90`

## callees

- `0x180003c40`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall CWamAdmin::Release(CWamAdmin *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 6);
  if ( !v1 && this )
    (*(void (__fastcall **)(CWamAdmin *, __int64))(*(_QWORD *)this + 80LL))(this, 1);
  return v1;
}

```

## disassembly

```asm
0x180003c40  push    rbx
0x180003c42  sub     rsp, 20h
0x180003c46  or      ebx, 0FFFFFFFFh
0x180003c49  lock xadd [rcx+18h], ebx
0x180003c4e  sub     ebx, 1
0x180003c51  jnz     short loc_180003C67
0x180003c53  test    rcx, rcx
0x180003c56  jz      short loc_180003C67
0x180003c58  mov     rdx, [rcx]
0x180003c5b  mov     rax, [rdx+50h]
0x180003c5f  lea     edx, [rbx+1]
0x180003c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c67  mov     eax, ebx
0x180003c69  add     rsp, 20h
0x180003c6d  pop     rbx
0x180003c6e  retn
```
