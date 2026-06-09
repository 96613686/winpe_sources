# ATL::ModuleLockHelper::ModuleLockHelper(void)

- ea: `0x180002af0`
- end: `0x180002b15`
- name: `??0ModuleLockHelper@ATL@@QEAA@XZ`
- size: `37`
- prototype: `__int64 __fastcall(ATL::ModuleLockHelper *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b80`
- `0x180005c10`
- `0x180005c80`
- `0x180005cf0`

## callees

- `0x180013010`

## pseudocode

```c
ATL::ModuleLockHelper *__fastcall ATL::ModuleLockHelper::ModuleLockHelper(ATL::ModuleLockHelper *this)
{
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return this;
}

```

## disassembly

```asm
0x180002af0  push    rbx
0x180002af2  sub     rsp, 20h
0x180002af6  mov     rbx, rcx
0x180002af9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002b00  mov     rax, [rcx]
0x180002b03  mov     rax, [rax+8]
0x180002b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b0c  mov     rax, rbx
0x180002b0f  add     rsp, 20h
0x180002b13  pop     rbx
0x180002b14  retn
```
