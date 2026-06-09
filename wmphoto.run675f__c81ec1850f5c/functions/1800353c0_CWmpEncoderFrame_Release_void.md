# CWmpEncoderFrame::Release(void)

- ea: `0x1800353c0`
- end: `0x1800353c5`
- name: `?Release@CWmpEncoderFrame@@UEAAKXZ`
- size: `5`
- prototype: `unsigned int __fastcall(CWmpEncoderFrame *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180038c90`
- `0x180038ca0`
- `0x18003b3c0`
- `0x18003b3e0`

## callees

- `0x1800323c0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CWmpEncoderFrame::Release(CWmpCOMBase *this)
{
  return CWmpCOMBase::InternalRelease(this);
}

```

## disassembly

```asm
0x1800353c0  jmp     ?InternalRelease@CWmpCOMBase@@UEAAKXZ; CWmpCOMBase::InternalRelease(void)
```
