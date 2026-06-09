# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x140031d28`
- end: `0x140031d4b`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140017a6c`

## callees

- `0x140031d28`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x140031d3f`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x140031d3f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140031d35`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140031d35`

## pseudocode

```c
void __fastcall std::_Init_once_completer::~_Init_once_completer(std::_Init_once_completer *this)
{
  if ( !InitOnceComplete(*(LPINIT_ONCE *)this, *((_DWORD *)this + 2), 0) )
    abort();
}

```

## disassembly

```asm
0x140031d28  sub     rsp, 28h
0x140031d2c  mov     edx, [rcx+8]; dwFlags
0x140031d2f  xor     r8d, r8d; lpContext
0x140031d32  mov     rcx, [rcx]; lpInitOnce
0x140031d35  call    cs:__imp_InitOnceComplete
0x140031d3b  test    eax, eax
0x140031d3d  jnz     short loc_140031D46
0x140031d3f  call    cs:__imp_abort
0x140031d46  add     rsp, 28h
0x140031d4a  retn
```
