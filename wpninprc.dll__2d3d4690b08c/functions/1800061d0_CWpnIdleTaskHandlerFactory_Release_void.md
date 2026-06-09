# CWpnIdleTaskHandlerFactory::Release(void)

- ea: `0x1800061d0`
- end: `0x1800061ff`
- name: `?Release@CWpnIdleTaskHandlerFactory@@UEAAKXZ`
- size: `47`
- prototype: `unsigned int __fastcall(CWpnIdleTaskHandlerFactory *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800061d0`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall CWpnIdleTaskHandlerFactory::Release(CWpnIdleTaskHandlerFactory *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
    (*(void (__fastcall **)(CWpnIdleTaskHandlerFactory *, __int64))(*(_QWORD *)this + 40LL))(this, 1);
  return v1;
}

```

## disassembly

```asm
0x1800061d0  push    rbx
0x1800061d2  sub     rsp, 20h
0x1800061d6  or      ebx, 0FFFFFFFFh
0x1800061d9  lock xadd [rcx+8], ebx
0x1800061de  sub     ebx, 1
0x1800061e1  jnz     short loc_1800061F7
0x1800061e3  test    rcx, rcx
0x1800061e6  jz      short loc_1800061F7
0x1800061e8  mov     rdx, [rcx]
0x1800061eb  mov     rax, [rdx+28h]
0x1800061ef  lea     edx, [rbx+1]
0x1800061f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061f7  mov     eax, ebx
0x1800061f9  add     rsp, 20h
0x1800061fd  pop     rbx
0x1800061fe  retn
```
