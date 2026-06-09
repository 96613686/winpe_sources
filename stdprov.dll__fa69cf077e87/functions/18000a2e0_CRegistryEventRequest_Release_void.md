# CRegistryEventRequest::Release(void)

- ea: `0x18000a2e0`
- end: `0x18000a312`
- name: `?Release@CRegistryEventRequest@@QEAAJXZ`
- size: `50`
- prototype: `__int64 __fastcall(CRegistryEventRequest *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008508`
- `0x18000b8e0`
- `0x180013f00`
- `0x180014000`
- `0x1800142e0`

## callees

- `0x18000a2e0`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CRegistryEventRequest::Release(CRegistryEventRequest *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
    (**(void (__fastcall ***)(CRegistryEventRequest *, __int64))this)(this, 1);
  return v1;
}

```

## disassembly

```asm
0x18000a2e0  push    rbx
0x18000a2e2  sub     rsp, 20h
0x18000a2e6  or      ebx, 0FFFFFFFFh
0x18000a2e9  lock xadd [rcx+8], ebx
0x18000a2ee  sub     ebx, 1
0x18000a2f1  jz      short loc_18000A2FB
0x18000a2f3  mov     eax, ebx
0x18000a2f5  add     rsp, 20h
0x18000a2f9  pop     rbx
0x18000a2fa  retn
0x18000a2fb  test    rcx, rcx
0x18000a2fe  jz      short loc_18000A2F3
0x18000a300  mov     rdx, [rcx]
0x18000a303  mov     rax, [rdx]
0x18000a306  mov     edx, 1
0x18000a30b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a310  jmp     short loc_18000A2F3
```
