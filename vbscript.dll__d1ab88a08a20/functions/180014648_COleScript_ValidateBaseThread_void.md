# COleScript::ValidateBaseThread(void)

- ea: `0x180014648`
- end: `0x180014673`
- name: `?ValidateBaseThread@COleScript@@AEAAJXZ`
- size: `43`
- prototype: `__int64 __fastcall(COleScript *__hidden this)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x180013ef0`
- `0x180014060`
- `0x1800142c0`
- `0x1800145a0`
- `0x18003bf60`
- `0x180041280`
- `0x18005370c`
- `0x180053b90`
- `0x180053d60`
- `0x180055c90`
- `0x1800566b4`
- `0x180056d30`
- `0x180056e90`
- `0x1800575d0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180014651`
- `KERNEL32!GetCurrentThreadId` at `0x180014651`

## pseudocode

```c
__int64 __fastcall COleScript::ValidateBaseThread(COleScript *this)
{
  return *((_DWORD *)this + 61) != GetCurrentThreadId() ? 0x8000FFFF : 0;
}

```

## disassembly

```asm
0x180014648  push    rbx
0x18001464a  sub     rsp, 20h
0x18001464e  mov     rbx, rcx
0x180014651  call    cs:__imp_GetCurrentThreadId
0x180014658  nop     dword ptr [rax+rax+00h]
0x18001465d  sub     eax, [rbx+0F4h]
0x180014663  neg     eax
0x180014665  sbb     eax, eax
0x180014667  and     eax, 8000FFFFh
0x18001466c  add     rsp, 20h
0x180014670  pop     rbx
0x180014671  retn
```
