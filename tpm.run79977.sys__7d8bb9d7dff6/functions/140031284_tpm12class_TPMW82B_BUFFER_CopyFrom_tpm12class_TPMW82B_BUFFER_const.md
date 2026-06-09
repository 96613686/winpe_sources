# tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)

- ea: `0x140031284`
- end: `0x1400312a8`
- name: `?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z`
- size: `36`
- prototype: `__int64 __fastcall(tpm12class::TPMW82B_BUFFER *__hidden this, const struct tpm12class::TPMW82B_BUFFER *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140033154`
- `0x140034c74`
- `0x1400355c4`
- `0x1400357dc`
- `0x140035ac4`
- `0x140035c24`
- `0x140035f08`
- `0x140037588`

## callees

- `0x140031234`
- `0x140031284`

## pseudocode

```c
int __fastcall tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER *this, const unsigned __int8 **a2)
{
  if ( a2 )
    return tpm12class::TPMW82B_BUFFER::CopyFrom(this, a2[8], *((unsigned __int16 *)a2 + 28));
  else
    return -2147024809;
}

```

## disassembly

```asm
0x140031284  sub     rsp, 28h
0x140031288  test    rdx, rdx
0x14003128b  jnz     short loc_140031294
0x14003128d  mov     eax, 80070057h
0x140031292  jmp     short loc_1400312A2
0x140031294  movzx   r8d, word ptr [rdx+38h]; unsigned __int64
0x140031299  mov     rdx, [rdx+40h]; unsigned __int8 *
0x14003129d  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x1400312a2  add     rsp, 28h
0x1400312a6  retn
```
