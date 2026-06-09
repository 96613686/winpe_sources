# tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)

- ea: `0x140031234`
- end: `0x14003127b`
- name: `?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z`
- size: `71`
- prototype: `int(tpm12class::TPMW82B_BUFFER *__hidden this, const unsigned __int8 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140031284`
- `0x140033154`
- `0x140035ac4`

## callees

- `0x140031234`
- `0x140031574`
- `0x140039840`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW82B_BUFFER::CopyFrom(void **this, const unsigned __int8 *a2, unsigned __int64 a3)
{
  int v5; // edi

  v5 = tpm12class::TPMW82B_BUFFER::Resize((tpm12class::TPMW82B_BUFFER *)this, a3);
  if ( v5 >= 0 )
    memmove(this[8], a2, *((unsigned __int16 *)this + 28));
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140031234  mov     [rsp+arg_0], rbx
0x140031239  mov     [rsp+arg_8], rsi
0x14003123e  push    rdi
0x14003123f  sub     rsp, 20h
0x140031243  mov     rsi, rdx
0x140031246  mov     rbx, rcx
0x140031249  mov     rdx, r8; unsigned __int64
0x14003124c  call    ?Resize@TPMW82B_BUFFER@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW82B_BUFFER::Resize(unsigned __int64)
0x140031251  mov     edi, eax
0x140031253  test    eax, eax
0x140031255  js      short loc_140031268
0x140031257  movzx   r8d, word ptr [rbx+38h]; Size
0x14003125c  mov     rdx, rsi; Src
0x14003125f  mov     rcx, [rbx+40h]; void *
0x140031263  call    memmove
0x140031268  mov     rbx, [rsp+28h+arg_0]
0x14003126d  mov     eax, edi
0x14003126f  mov     rsi, [rsp+28h+arg_8]
0x140031274  add     rsp, 20h
0x140031278  pop     rdi
0x140031279  retn
```
