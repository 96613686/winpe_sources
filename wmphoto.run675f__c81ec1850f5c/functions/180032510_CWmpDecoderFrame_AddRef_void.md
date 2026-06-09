# CWmpDecoderFrame::AddRef(void)

- ea: `0x180032510`
- end: `0x180032524`
- name: `?AddRef@CWmpDecoderFrame@@UEAAKXZ`
- size: `20`
- prototype: `unsigned int __fastcall(CWmpDecoderFrame *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180038ea0`
- `0x180038ec0`
- `0x180038ee0`
- `0x180038f00`
- `0x180038f20`
- `0x180038f40`
- `0x180038f60`

## pseudocode

```c
__int64 __fastcall CWmpDecoderFrame::AddRef(CWmpDecoderFrame *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 8343) + 8LL));
}

```

## disassembly

```asm
0x180032510  mov     rdx, [rcx+104B8h]
0x180032517  mov     eax, 1
0x18003251c  lock xadd [rdx+8], eax
0x180032521  inc     eax
0x180032523  retn
```
