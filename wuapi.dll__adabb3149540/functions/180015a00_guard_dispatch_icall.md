# _guard_dispatch_icall

- ea: `0x180015a00`
- end: `0x180015a06`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `55`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180001010`
- `0x180001e74`
- `0x18000215c`
- `0x180002354`
- `0x180002520`
- `0x180002fc8`
- `0x180002fe8`
- `0x180003190`
- `0x180003280`
- `0x18000358c`
- `0x180004010`
- `0x1800042a0`
- `0x180004310`
- `0x180004580`
- `0x180004b60`
- `0x180004ff8`
- `0x1800056e0`
- `0x18000576c`
- `0x1800059b8`
- `0x180007158`
- `0x1800072a0`
- `0x180007308`
- `0x180007fd0`
- `0x180008364`
- `0x180008a44`
- `0x180009064`
- `0x180009564`
- `0x180009bd0`
- `0x180009f70`
- `0x180009ff0`
- `0x18000a2b0`
- `0x18000a6c8`
- `0x18000ecfc`
- `0x18000ef30`
- `0x18000efc0`
- `0x18000eff4`
- `0x18000fde8`
- `0x1800101d8`
- `0x18001037c`
- `0x180010c48`
- `0x180010c8c`
- `0x180010cd8`
- `0x180010d34`
- `0x180011a90`
- `0x180011eb8`
- `0x1800123a0`
- `0x180012598`
- `0x180013d10`
- `0x180013f44`
- `0x1800164b3`

## callees

- `0x180015a20`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x180015a00  jmp     cs:__guard_dispatch_icall_fptr
```
