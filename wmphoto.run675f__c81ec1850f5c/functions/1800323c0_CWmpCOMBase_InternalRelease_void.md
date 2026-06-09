# CWmpCOMBase::InternalRelease(void)

- ea: `0x1800323c0`
- end: `0x1800323f0`
- name: `?InternalRelease@CWmpCOMBase@@UEAAKXZ`
- size: `48`
- prototype: `unsigned int __fastcall(CWmpCOMBase *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002e5c8`
- `0x1800323a0`
- `0x1800353c0`
- `0x180038a70`
- `0x18003b920`

## callees

- `0x1800323c0`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall CWmpCOMBase::InternalRelease(CWmpCOMBase *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
    (*(void (__fastcall **)(CWmpCOMBase *, __int64))(*(_QWORD *)this + 24LL))(this, 1);
  return v1;
}

```

## disassembly

```asm
0x1800323c0  push    rbx
0x1800323c2  sub     rsp, 20h
0x1800323c6  or      ebx, 0FFFFFFFFh
0x1800323c9  lock xadd [rcx+8], ebx
0x1800323ce  sub     ebx, 1
0x1800323d1  jnz     short loc_1800323E7
0x1800323d3  test    rcx, rcx
0x1800323d6  jz      short loc_1800323E7
0x1800323d8  mov     rdx, [rcx]
0x1800323db  mov     rax, [rdx+18h]
0x1800323df  lea     edx, [rbx+1]
0x1800323e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323e7  mov     eax, ebx
0x1800323e9  add     rsp, 20h
0x1800323ed  pop     rbx
0x1800323ee  retn
```
