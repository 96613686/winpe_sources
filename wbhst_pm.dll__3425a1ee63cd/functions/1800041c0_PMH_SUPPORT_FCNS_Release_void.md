# PMH_SUPPORT_FCNS::Release(void)

- ea: `0x1800041c0`
- end: `0x1800041f9`
- name: `?Release@PMH_SUPPORT_FCNS@@UEAAKXZ`
- size: `57`
- prototype: `unsigned int __fastcall(PMH_SUPPORT_FCNS *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800025d0`

## callees

- `0x180001048`
- `0x1800037e8`
- `0x1800041c0`

## pseudocode

```c
__int64 __fastcall PMH_SUPPORT_FCNS::Release(PMH_SUPPORT_FCNS *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 5);
  if ( !v2 && this )
  {
    PMH_SUPPORT_FCNS::~PMH_SUPPORT_FCNS(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x1800041c0  mov     [rsp+arg_0], rbx
0x1800041c5  push    rdi
0x1800041c6  sub     rsp, 20h
0x1800041ca  mov     rbx, rcx
0x1800041cd  or      edi, 0FFFFFFFFh
0x1800041d0  lock xadd [rcx+14h], edi
0x1800041d5  sub     edi, 1
0x1800041d8  jnz     short loc_1800041EC
0x1800041da  test    rcx, rcx
0x1800041dd  jz      short loc_1800041EC
0x1800041df  call    ??1PMH_SUPPORT_FCNS@@AEAA@XZ; PMH_SUPPORT_FCNS::~PMH_SUPPORT_FCNS(void)
0x1800041e4  mov     rcx, rbx; Block
0x1800041e7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800041ec  mov     rbx, [rsp+28h+arg_0]
0x1800041f1  mov     eax, edi
0x1800041f3  add     rsp, 20h
0x1800041f7  pop     rdi
0x1800041f8  retn
```
