# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x180032600`
- end: `0x180032622`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004a613`

## callees

- `0x180032600`
- `0x180041cb0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003260d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003260d`

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
0x180032600  sub     rsp, 28h
0x180032604  mov     edx, [rcx+8]; dwFlags
0x180032607  xor     r8d, r8d; lpContext
0x18003260a  mov     rcx, [rcx]; lpInitOnce
0x18003260d  call    cs:__imp_InitOnceComplete
0x180032613  test    eax, eax
0x180032615  jz      short loc_18003261C
0x180032617  add     rsp, 28h
0x18003261b  retn
0x18003261c  call    __std_init_once_link_alternate_names_and_abort
```
