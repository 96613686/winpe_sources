# CWuaClassFactoryBase::Release(void)

- ea: `0x14000bf00`
- end: `0x14000bf2f`
- name: `?Release@CWuaClassFactoryBase@@UEAAKXZ`
- size: `47`
- prototype: `unsigned int __fastcall(CWuaClassFactoryBase *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140018fe0`

## callees

- `0x14000bf00`
- `0x1400206e0`

## pseudocode

```c
__int64 __fastcall CWuaClassFactoryBase::Release(CWuaClassFactoryBase *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 6);
  if ( !v1 && *((_DWORD *)this + 11) )
    (*(void (__fastcall **)(CWuaClassFactoryBase *, __int64))(*(_QWORD *)this + 40LL))(this, 1);
  return v1;
}

```

## disassembly

```asm
0x14000bf00  push    rbx
0x14000bf02  sub     rsp, 20h
0x14000bf06  or      ebx, 0FFFFFFFFh
0x14000bf09  lock xadd [rcx+18h], ebx
0x14000bf0e  sub     ebx, 1
0x14000bf11  jnz     short loc_14000BF27
0x14000bf13  cmp     [rcx+2Ch], ebx
0x14000bf16  jz      short loc_14000BF27
0x14000bf18  mov     rdx, [rcx]
0x14000bf1b  mov     rax, [rdx+28h]
0x14000bf1f  lea     edx, [rbx+1]
0x14000bf22  call    _guard_dispatch_icall
0x14000bf27  mov     eax, ebx
0x14000bf29  add     rsp, 20h
0x14000bf2d  pop     rbx
0x14000bf2e  retn
```
