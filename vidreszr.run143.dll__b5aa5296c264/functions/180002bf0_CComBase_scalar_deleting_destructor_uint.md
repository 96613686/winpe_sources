# CComBase::`scalar deleting destructor'(uint)

- ea: `0x180002bf0`
- end: `0x180002c22`
- name: `??_GCComBase@@UEAAPEAXI@Z`
- size: `50`
- prototype: `void *__fastcall(CComBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001968`
- `0x180002bf0`

## pseudocode

```c
CComBase *__fastcall CComBase::`scalar deleting destructor'(CComBase *this, char a2)
{
  *(_QWORD *)this = &CComBase::`vftable';
  _InterlockedDecrement(&g_cActiveObjects);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002bf0  push    rbx
0x180002bf2  sub     rsp, 20h
0x180002bf6  lea     rax, ??_7CComBase@@6B@; const CComBase::`vftable'
0x180002bfd  mov     rbx, rcx
0x180002c00  mov     [rcx], rax
0x180002c03  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x180002c0a  test    dl, 1
0x180002c0d  jz      short loc_180002C19
0x180002c0f  mov     edx, 18h; unsigned __int64
0x180002c14  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002c19  mov     rax, rbx
0x180002c1c  add     rsp, 20h
0x180002c20  pop     rbx
0x180002c21  retn
```
