# CWmpDecoderFrame::Release(void)

- ea: `0x180032080`
- end: `0x18003208c`
- name: `?Release@CWmpDecoderFrame@@UEAAKXZ`
- size: `12`
- prototype: `unsigned int __fastcall(CWmpDecoderFrame *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180039f90`
- `0x180039fb0`
- `0x180039fd0`
- `0x180039ff0`
- `0x18003a010`
- `0x18003a030`
- `0x18003a050`

## callees

- `0x1800320a0`

## pseudocode

```c
__int64 __fastcall CWmpDecoderFrame::Release(CWmpCOMBase **this)
{
  return CWmpCOMBase::InternalRelease(this[8343]);
}

```

## disassembly

```asm
0x180032080  mov     rcx, [rcx+104B8h]; this
0x180032087  jmp     ?InternalRelease@CWmpCOMBase@@UEAAKXZ; CWmpCOMBase::InternalRelease(void)
```
