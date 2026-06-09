# std::_Init_once_completer::~_Init_once_completer(void)

- ea: `0x180053390`
- end: `0x1800533b9`
- name: `??1_Init_once_completer@std@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(std::_Init_once_completer *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18005277c`
- `0x18006a4b0`

## callees

- `0x18003ed18`
- `0x180053390`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18005339d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18005339d`

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
0x180053390  sub     rsp, 28h
0x180053394  mov     edx, [rcx+8]; dwFlags
0x180053397  xor     r8d, r8d; lpContext
0x18005339a  mov     rcx, [rcx]; lpInitOnce
0x18005339d  call    cs:__imp_InitOnceComplete
0x1800533a4  nop     dword ptr [rax+rax+00h]
0x1800533a9  test    eax, eax
0x1800533ab  jnz     short loc_1800533B3
0x1800533ad  call    __std_init_once_link_alternate_names_and_abort
0x1800533b3  add     rsp, 28h
0x1800533b7  retn
```
