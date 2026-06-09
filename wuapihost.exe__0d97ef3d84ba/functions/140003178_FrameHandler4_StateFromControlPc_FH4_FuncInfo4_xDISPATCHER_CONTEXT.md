# __FrameHandler4::StateFromControlPc(FH4::FuncInfo4 *,_xDISPATCHER_CONTEXT *)

- ea: `0x140003178`
- end: `0x140003180`
- name: `?StateFromControlPc@__FrameHandler4@@SAHPEAUFuncInfo4@FH4@@PEAU_xDISPATCHER_CONTEXT@@@Z`
- size: `8`
- prototype: `__int64 __fastcall(struct FH4::FuncInfo4 *, struct _xDISPATCHER_CONTEXT *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x140003624`
- `0x140004b20`

## callees

- `0x140003188`

## pseudocode

```c
__int64 __fastcall __FrameHandler4::StateFromControlPc(struct FH4::FuncInfo4 *a1, struct _xDISPATCHER_CONTEXT *a2)
{
  return __FrameHandler4::StateFromIp(a1, a2, a2->ControlPc);
}

```

## disassembly

```asm
0x140003178  mov     r8, [rdx]; unsigned __int64
0x14000317b  jmp     ?StateFromIp@__FrameHandler4@@SAHPEAUFuncInfo4@FH4@@PEAU_xDISPATCHER_CONTEXT@@_K@Z; __FrameHandler4::StateFromIp(FH4::FuncInfo4 *,_xDISPATCHER_CONTEXT *,unsigned __int64)
```
