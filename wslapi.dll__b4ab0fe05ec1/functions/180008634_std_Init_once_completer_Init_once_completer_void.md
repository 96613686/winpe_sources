# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x180008634`
- end: `0x180008656`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800083cc`
- `0x18000c077`

## callees

- `0x1800019a8`
- `0x180008634`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008641`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008641`

## pseudocode

```c
void __fastcall std::_Init_once_completer::~_Init_once_completer(std::_Init_once_completer *this)
{
  if ( !InitOnceComplete(*(LPINIT_ONCE *)this, *((_DWORD *)this + 2), 0) )
    _std_init_once_link_alternate_names_and_abort();
}

```

## disassembly

```asm
0x180008634  sub     rsp, 28h
0x180008638  mov     edx, [rcx+8]; dwFlags
0x18000863b  xor     r8d, r8d; lpContext
0x18000863e  mov     rcx, [rcx]; lpInitOnce
0x180008641  call    cs:__imp_InitOnceComplete
0x180008647  test    eax, eax
0x180008649  jnz     short loc_180008651
0x18000864b  call    __std_init_once_link_alternate_names_and_abort
0x180008651  add     rsp, 28h
0x180008655  retn
```
