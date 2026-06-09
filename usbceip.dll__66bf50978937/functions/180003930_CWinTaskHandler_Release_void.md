# CWinTaskHandler::Release(void)

- ea: `0x180003930`
- end: `0x18000395f`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003930`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::Release(CWinTaskHandler *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( !v1 && this )
    (*(void (__fastcall **)(CWinTaskHandler *, __int64))(*(_QWORD *)this + 56LL))(this, 1);
  return v1;
}

```

## disassembly

```asm
0x180003930  push    rbx
0x180003932  sub     rsp, 20h
0x180003936  or      ebx, 0FFFFFFFFh
0x180003939  lock xadd [rcx+20h], ebx
0x18000393e  sub     ebx, 1
0x180003941  jnz     short loc_180003957
0x180003943  test    rcx, rcx
0x180003946  jz      short loc_180003957
0x180003948  mov     rdx, [rcx]
0x18000394b  mov     rax, [rdx+38h]
0x18000394f  lea     edx, [rbx+1]
0x180003952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003957  mov     eax, ebx
0x180003959  add     rsp, 20h
0x18000395d  pop     rbx
0x18000395e  retn
```
