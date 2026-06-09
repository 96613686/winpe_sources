# XMLScrServProv::Release(void)

- ea: `0x14000c690`
- end: `0x14000c6c9`
- name: `?Release@XMLScrServProv@@UEAAKXZ`
- size: `57`
- prototype: `unsigned int __fastcall(XMLScrServProv *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x140001048`
- `0x14000bd04`
- `0x14000c690`

## pseudocode

```c
__int64 __fastcall XMLScrServProv::Release(XMLScrServProv *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 4);
  if ( !v2 && this )
  {
    XMLScrServProv::~XMLScrServProv(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x14000c690  mov     [rsp+arg_0], rbx
0x14000c695  push    rdi
0x14000c696  sub     rsp, 20h
0x14000c69a  mov     rbx, rcx
0x14000c69d  or      edi, 0FFFFFFFFh
0x14000c6a0  lock xadd [rcx+10h], edi
0x14000c6a5  sub     edi, 1
0x14000c6a8  jnz     short loc_14000C6BC
0x14000c6aa  test    rcx, rcx
0x14000c6ad  jz      short loc_14000C6BC
0x14000c6af  call    ??1XMLScrServProv@@AEAA@XZ; XMLScrServProv::~XMLScrServProv(void)
0x14000c6b4  mov     rcx, rbx; Block
0x14000c6b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000c6bc  mov     rbx, [rsp+28h+arg_0]
0x14000c6c1  mov     eax, edi
0x14000c6c3  add     rsp, 20h
0x14000c6c7  pop     rdi
0x14000c6c8  retn
```
