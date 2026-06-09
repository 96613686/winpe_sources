# CWpnIdleTaskHandler::`vector deleting destructor'(uint)

- ea: `0x180006210`
- end: `0x180006242`
- name: `??_ECWpnIdleTaskHandler@@EEAAPEAXI@Z`
- size: `50`
- prototype: `void *__fastcall(CWpnIdleTaskHandler *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001534`
- `0x180006210`

## pseudocode

```c
CWpnIdleTaskHandler *__fastcall CWpnIdleTaskHandler::`vector deleting destructor'(CWpnIdleTaskHandler *this, char a2)
{
  *(_QWORD *)this = &CWpnIdleTaskHandler::`vftable';
  _InterlockedDecrement(&g_Count);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180006210  push    rbx
0x180006212  sub     rsp, 20h
0x180006216  lea     rax, ??_7CWpnIdleTaskHandler@@6B@; const CWpnIdleTaskHandler::`vftable'
0x18000621d  mov     rbx, rcx
0x180006220  mov     [rcx], rax
0x180006223  lock dec cs:?g_Count@@3JA; long g_Count
0x18000622a  test    dl, 1
0x18000622d  jz      short loc_180006239
0x18000622f  mov     edx, 10h; unsigned __int64
0x180006234  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006239  mov     rax, rbx
0x18000623c  add     rsp, 20h
0x180006240  pop     rbx
0x180006241  retn
```
