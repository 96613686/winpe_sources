# _guard_dispatch_icall

- ea: `0x180015430`
- end: `0x180015436`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `55`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180001520`
- `0x1800015ac`
- `0x1800017f8`
- `0x180002f78`
- `0x1800030c0`
- `0x180003128`
- `0x180003b40`
- `0x180003c70`
- `0x180003d20`
- `0x180003dd0`
- `0x180003e70`
- `0x180003f20`
- `0x180003fd0`
- `0x180004080`
- `0x1800043f8`
- `0x18000448c`
- `0x1800049c4`
- `0x180004ea4`
- `0x180005320`
- `0x180005b8c`
- `0x1800061d0`
- `0x180006560`
- `0x180006bec`
- `0x180006ea8`
- `0x1800071b4`
- `0x1800071d4`
- `0x180007200`
- `0x1800072b0`
- `0x180007d40`
- `0x180008060`
- `0x1800088d8`
- `0x180008a80`
- `0x180008cd0`
- `0x180008d40`
- `0x180009680`
- `0x180009c24`
- `0x18000eec4`
- `0x18000f238`
- `0x18000f3dc`
- `0x18000fcb4`
- `0x18000fcf8`
- `0x18000fd48`
- `0x18000fda4`
- `0x180010b00`
- `0x180010f24`
- `0x180011410`
- `0x180011608`
- `0x180012d80`
- `0x180012fb4`
- `0x1800162be`

## callees

- `0x180015450`

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
0x180015430  jmp     cs:__guard_dispatch_icall_fptr
```
