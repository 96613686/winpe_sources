# wil::details::init_once_completer::~init_once_completer(void)

- ea: `0x14005368c`
- end: `0x14005369c`
- name: `??1init_once_completer@details@wil@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(wil::details::init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140063dd8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140053695`

## pseudocode

```c
void __fastcall wil::details::init_once_completer::~init_once_completer(wil::details::init_once_completer *this)
{
  InitOnceComplete(*(LPINIT_ONCE *)this, *((_DWORD *)this + 2), 0);
}

```

## disassembly

```asm
0x14005368c  mov     edx, [rcx+8]
0x14005368f  xor     r8d, r8d
0x140053692  mov     rcx, [rcx]
0x140053695  jmp     cs:__imp_InitOnceComplete
```
