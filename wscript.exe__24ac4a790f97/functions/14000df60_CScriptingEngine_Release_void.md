# CScriptingEngine::Release(void)

- ea: `0x14000df60`
- end: `0x14000df70`
- name: `?Release@CScriptingEngine@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CScriptingEngine *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000df80`
- `0x14000df90`
- `0x14000dfa0`
- `0x14000dfb0`
- `0x14000dfc0`

## callees

- `0x140018010`

## pseudocode

```c
__int64 __fastcall CScriptingEngine::Release(CScriptingEngine *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 16LL))(*((_QWORD *)this + 6));
}

```

## disassembly

```asm
0x14000df60  mov     rcx, [rcx+30h]
0x14000df64  mov     rax, [rcx]
0x14000df67  mov     rax, [rax+10h]
0x14000df6b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
