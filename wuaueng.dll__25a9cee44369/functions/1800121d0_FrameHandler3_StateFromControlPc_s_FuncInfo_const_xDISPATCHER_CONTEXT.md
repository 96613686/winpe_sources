# __FrameHandler3::StateFromControlPc(_s_FuncInfo const *,_xDISPATCHER_CONTEXT *)

- ea: `0x1800121d0`
- end: `0x1800121d8`
- name: `?StateFromControlPc@__FrameHandler3@@SAHPEBU_s_FuncInfo@@PEAU_xDISPATCHER_CONTEXT@@@Z`
- size: `8`
- prototype: `__int64 __fastcall(const struct _s_FuncInfo *, struct _xDISPATCHER_CONTEXT *)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180010edc`
- `0x180010f18`
- `0x180010fc4`
- `0x1800110e4`
- `0x180014f84`

## callees

- `0x1800121f0`

## pseudocode

```c
__int64 __fastcall __FrameHandler3::StateFromControlPc(const struct _s_FuncInfo *a1, struct _xDISPATCHER_CONTEXT *a2)
{
  return __FrameHandler3::StateFromIp(a1, a2, a2->ControlPc);
}

```

## disassembly

```asm
0x1800121d0  mov     r8, [rdx]; unsigned __int64
0x1800121d3  jmp     ?StateFromIp@__FrameHandler3@@SAHPEBU_s_FuncInfo@@PEAU_xDISPATCHER_CONTEXT@@_K@Z; __FrameHandler3::StateFromIp(_s_FuncInfo const *,_xDISPATCHER_CONTEXT *,unsigned __int64)
```
