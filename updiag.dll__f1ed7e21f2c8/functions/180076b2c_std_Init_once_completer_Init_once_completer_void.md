# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x180076b2c`
- end: `0x180076b4e`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18009c899`

## callees

- `0x180076b2c`
- `0x18007e220`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180076b39`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180076b39`

## pseudocode

```c
void __fastcall std::_Init_once_completer::~_Init_once_completer(std::_Init_once_completer *this)
{
  __int64 v1; // rdx
  __int64 v2; // rcx

  if ( !InitOnceComplete(*(LPINIT_ONCE *)this, *((_DWORD *)this + 2), 0) )
    _std_init_once_link_alternate_names_and_abort(v2, v1);
}

```

## disassembly

```asm
0x180076b2c  sub     rsp, 28h
0x180076b30  mov     edx, [rcx+8]; dwFlags
0x180076b33  xor     r8d, r8d; lpContext
0x180076b36  mov     rcx, [rcx]; lpInitOnce
0x180076b39  call    cs:__imp_InitOnceComplete
0x180076b3f  test    eax, eax
0x180076b41  jz      short loc_180076B48
0x180076b43  add     rsp, 28h
0x180076b47  retn
0x180076b48  call    __std_init_once_link_alternate_names_and_abort
```
