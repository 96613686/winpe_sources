# tpm12class::TPMW8_COMMAND::Validate(uchar)

- ea: `0x1400378a0`
- end: `0x1400378dc`
- name: `?Validate@TPMW8_COMMAND@tpm12class@@MEAAJE@Z`
- size: `60`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_COMMAND *__hidden this, unsigned __int8)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400380a0`
- `0x140038250`
- `0x140038620`
- `0x140038a10`
- `0x140038bd0`
- `0x140038f60`

## callees

- `0x1400378a0`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_COMMAND::Validate(tpm12class::TPMW8_COMMAND *this, char a2)
{
  if ( a2 )
  {
    if ( (unsigned __int16)(*((_WORD *)this + 28) + 0x7FFF) <= 1u )
      return 0;
  }
  else if ( (unsigned __int16)(*((_WORD *)this + 29) + 0x7FFF) <= 1u )
  {
    return *((_DWORD *)this + 4) != *((_DWORD *)this + 16) ? 0x8007000D : 0;
  }
  return 2147942413LL;
}

```

## disassembly

```asm
0x1400378a0  mov     r8, rcx
0x1400378a3  mov     eax, 7FFFh
0x1400378a8  test    dl, dl
0x1400378aa  jz      short loc_1400378BA
0x1400378ac  add     ax, [rcx+38h]
0x1400378b0  cmp     ax, 1
0x1400378b4  ja      short loc_1400378D6
0x1400378b6  xor     eax, eax
0x1400378b8  retn
0x1400378ba  add     ax, [rcx+3Ah]
0x1400378be  cmp     ax, 1
0x1400378c2  ja      short loc_1400378D6
0x1400378c4  mov     ecx, [rcx+40h]
0x1400378c7  sub     ecx, [r8+10h]
0x1400378cb  neg     ecx
0x1400378cd  sbb     eax, eax
0x1400378cf  and     eax, 8007000Dh
0x1400378d4  retn
0x1400378d6  mov     eax, 8007000Dh
0x1400378db  retn
```
