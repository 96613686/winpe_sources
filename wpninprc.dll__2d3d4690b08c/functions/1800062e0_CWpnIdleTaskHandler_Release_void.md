# CWpnIdleTaskHandler::Release(void)

- ea: `0x1800062e0`
- end: `0x18000630f`
- name: `?Release@CWpnIdleTaskHandler@@UEAAKXZ`
- size: `47`
- prototype: `unsigned int __fastcall(CWpnIdleTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800062e0`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall CWpnIdleTaskHandler::Release(CWpnIdleTaskHandler *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
    (*(void (__fastcall **)(CWpnIdleTaskHandler *, __int64))(*(_QWORD *)this + 56LL))(this, 1);
  return v1;
}

```

## disassembly

```asm
0x1800062e0  push    rbx
0x1800062e2  sub     rsp, 20h
0x1800062e6  or      ebx, 0FFFFFFFFh
0x1800062e9  lock xadd [rcx+8], ebx
0x1800062ee  sub     ebx, 1
0x1800062f1  jnz     short loc_180006307
0x1800062f3  test    rcx, rcx
0x1800062f6  jz      short loc_180006307
0x1800062f8  mov     rdx, [rcx]
0x1800062fb  mov     rax, [rdx+38h]
0x1800062ff  lea     edx, [rbx+1]
0x180006302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006307  mov     eax, ebx
0x180006309  add     rsp, 20h
0x18000630d  pop     rbx
0x18000630e  retn
```
