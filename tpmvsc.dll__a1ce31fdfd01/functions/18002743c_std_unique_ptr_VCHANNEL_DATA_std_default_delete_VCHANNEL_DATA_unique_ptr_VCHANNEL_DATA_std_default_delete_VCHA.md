# std::unique_ptr<VCHANNEL_DATA,std::default_delete<VCHANNEL_DATA>>::~unique_ptr<VCHANNEL_DATA,std::default_delete<VCHANNEL_DATA>>(void)

- ea: `0x18002743c`
- end: `0x180027452`
- name: `??1?$unique_ptr@UVCHANNEL_DATA@@U?$default_delete@UVCHANNEL_DATA@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void *__fastcall(VCHANNEL_DATA **, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800297cc`

## callees

- `0x18002743c`
- `0x180027e80`

## pseudocode

```c
void *__fastcall std::unique_ptr<VCHANNEL_DATA>::~unique_ptr<VCHANNEL_DATA>(VCHANNEL_DATA **a1, unsigned int a2)
{
  VCHANNEL_DATA *v2; // rcx
  void *result; // rax

  v2 = *a1;
  if ( v2 )
    return VCHANNEL_DATA::`scalar deleting destructor'(v2, a2);
  return result;
}

```

## disassembly

```asm
0x18002743c  sub     rsp, 28h
0x180027440  mov     rcx, [rcx]; this
0x180027443  test    rcx, rcx
0x180027446  jz      short loc_18002744D
0x180027448  call    ??_GVCHANNEL_DATA@@QEAAPEAXI@Z; VCHANNEL_DATA::`scalar deleting destructor'(uint)
0x18002744d  add     rsp, 28h
0x180027451  retn
```
