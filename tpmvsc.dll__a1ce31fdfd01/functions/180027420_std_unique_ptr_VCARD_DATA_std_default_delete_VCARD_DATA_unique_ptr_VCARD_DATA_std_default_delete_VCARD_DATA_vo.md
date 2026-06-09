# std::unique_ptr<VCARD_DATA,std::default_delete<VCARD_DATA>>::~unique_ptr<VCARD_DATA,std::default_delete<VCARD_DATA>>(void)

- ea: `0x180027420`
- end: `0x180027436`
- name: `??1?$unique_ptr@UVCARD_DATA@@U?$default_delete@UVCARD_DATA@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void *__fastcall(VCARD_DATA **, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800291ec`

## callees

- `0x180027420`
- `0x180027e54`

## pseudocode

```c
void *__fastcall std::unique_ptr<VCARD_DATA>::~unique_ptr<VCARD_DATA>(VCARD_DATA **a1, unsigned int a2)
{
  VCARD_DATA *v2; // rcx
  void *result; // rax

  v2 = *a1;
  if ( v2 )
    return VCARD_DATA::`scalar deleting destructor'(v2, a2);
  return result;
}

```

## disassembly

```asm
0x180027420  sub     rsp, 28h
0x180027424  mov     rcx, [rcx]; this
0x180027427  test    rcx, rcx
0x18002742a  jz      short loc_180027431
0x18002742c  call    ??_GVCARD_DATA@@QEAAPEAXI@Z; VCARD_DATA::`scalar deleting destructor'(uint)
0x180027431  add     rsp, 28h
0x180027435  retn
```
