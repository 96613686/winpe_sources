# INI_STORE::Release(void)

- ea: `0x1800024e0`
- end: `0x18000250e`
- name: `?Release@INI_STORE@@UEAAKXZ`
- size: `46`
- prototype: `unsigned int __fastcall(INI_STORE *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800024e0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall INI_STORE::Release(INI_STORE *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
    (**(void (__fastcall ***)(INI_STORE *, __int64))this)(this, 1);
  return v1;
}

```

## disassembly

```asm
0x1800024e0  push    rbx
0x1800024e2  sub     rsp, 20h
0x1800024e6  or      ebx, 0FFFFFFFFh
0x1800024e9  lock xadd [rcx+8], ebx
0x1800024ee  sub     ebx, 1
0x1800024f1  jnz     short loc_180002506
0x1800024f3  test    rcx, rcx
0x1800024f6  jz      short loc_180002506
0x1800024f8  mov     rdx, [rcx]
0x1800024fb  mov     rax, [rdx]
0x1800024fe  lea     edx, [rbx+1]
0x180002501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002506  mov     eax, ebx
0x180002508  add     rsp, 20h
0x18000250c  pop     rbx
0x18000250d  retn
```
