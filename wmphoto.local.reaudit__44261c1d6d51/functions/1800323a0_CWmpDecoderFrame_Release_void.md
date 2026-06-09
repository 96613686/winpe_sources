# CWmpDecoderFrame::Release(void)

- ea: `0x1800323a0`
- end: `0x1800323ac`
- name: `?Release@CWmpDecoderFrame@@UEAAKXZ`
- size: `12`
- prototype: `unsigned int __fastcall(CWmpDecoderFrame *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003a6c0`
- `0x18003a6e0`
- `0x18003a700`
- `0x18003a720`
- `0x18003a740`
- `0x18003a760`
- `0x18003a780`

## callees

- `0x1800323c0`

## pseudocode

```c
__int64 __fastcall CWmpDecoderFrame::Release(CWmpCOMBase **this)
{
  return CWmpCOMBase::InternalRelease(this[8343]);
}

```

## disassembly

```asm
0x1800323a0  mov     rcx, [rcx+104B8h]; this
0x1800323a7  jmp     ?InternalRelease@CWmpCOMBase@@UEAAKXZ; CWmpCOMBase::InternalRelease(void)
```
