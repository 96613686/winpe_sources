# CWmpCOMBase::InternalRelease(void)

- ea: `0x1800320a0`
- end: `0x1800320cf`
- name: `?InternalRelease@CWmpCOMBase@@UEAAKXZ`
- size: `47`
- prototype: `unsigned int __fastcall(CWmpCOMBase *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002e298`
- `0x180032080`
- `0x180034dc0`
- `0x180038420`
- `0x18003b160`

## callees

- `0x1800320a0`
- `0x180044010`

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
0x1800320a0  push    rbx
0x1800320a2  sub     rsp, 20h
0x1800320a6  or      ebx, 0FFFFFFFFh
0x1800320a9  lock xadd [rcx+8], ebx
0x1800320ae  sub     ebx, 1
0x1800320b1  jnz     short loc_1800320C7
0x1800320b3  test    rcx, rcx
0x1800320b6  jz      short loc_1800320C7
0x1800320b8  mov     rdx, [rcx]
0x1800320bb  mov     rax, [rdx+18h]
0x1800320bf  lea     edx, [rbx+1]
0x1800320c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800320c7  mov     eax, ebx
0x1800320c9  add     rsp, 20h
0x1800320cd  pop     rbx
0x1800320ce  retn
```
