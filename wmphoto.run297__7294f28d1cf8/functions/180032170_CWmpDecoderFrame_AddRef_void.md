# CWmpDecoderFrame::AddRef(void)

- ea: `0x180032170`
- end: `0x180032184`
- name: `?AddRef@CWmpDecoderFrame@@UEAAKXZ`
- size: `20`
- prototype: `unsigned int __fastcall(CWmpDecoderFrame *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180038840`
- `0x180038860`
- `0x180038880`
- `0x1800388a0`
- `0x1800388c0`
- `0x1800388e0`
- `0x180038900`

## pseudocode

```c
__int64 __fastcall CWmpDecoderFrame::AddRef(CWmpDecoderFrame *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 8343) + 8LL));
}

```

## disassembly

```asm
0x180032170  mov     rdx, [rcx+104B8h]
0x180032177  mov     eax, 1
0x18003217c  lock xadd [rdx+8], eax
0x180032181  inc     eax
0x180032183  retn
```
