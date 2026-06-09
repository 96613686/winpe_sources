# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x140033114`
- end: `0x140033144`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140017a7c`

## callees

- `0x140033114`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x140033131`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x140033131`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140033121`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140033121`

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
0x140033114  sub     rsp, 28h
0x140033118  mov     edx, [rcx+8]; dwFlags
0x14003311b  xor     r8d, r8d; lpContext
0x14003311e  mov     rcx, [rcx]; lpInitOnce
0x140033121  call    cs:__imp_InitOnceComplete
0x140033128  nop     dword ptr [rax+rax+00h]
0x14003312d  test    eax, eax
0x14003312f  jnz     short loc_14003313E
0x140033131  call    cs:__imp_abort
0x14003313e  add     rsp, 28h
0x140033142  retn
```
