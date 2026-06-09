# CWmpEncoderFrame::Release(void)

- ea: `0x180034dc0`
- end: `0x180034dc5`
- name: `?Release@CWmpEncoderFrame@@UEAAKXZ`
- size: `5`
- prototype: `unsigned int __fastcall(CWmpEncoderFrame *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180038640`
- `0x180038650`
- `0x18003ac10`
- `0x18003ac30`

## callees

- `0x1800320a0`

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
0x180034dc0  jmp     ?InternalRelease@CWmpCOMBase@@UEAAKXZ; CWmpCOMBase::InternalRelease(void)
```
