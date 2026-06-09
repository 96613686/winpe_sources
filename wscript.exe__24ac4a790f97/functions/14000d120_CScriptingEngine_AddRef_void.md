# CScriptingEngine::AddRef(void)

- ea: `0x14000d120`
- end: `0x14000d130`
- name: `?AddRef@CScriptingEngine@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CScriptingEngine *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d140`
- `0x14000d150`
- `0x14000d160`
- `0x14000d170`
- `0x14000d180`

## callees

- `0x140018010`

## pseudocode

```c
__int64 __fastcall CScriptingEngine::AddRef(CScriptingEngine *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 8LL))(*((_QWORD *)this + 6));
}

```

## disassembly

```asm
0x14000d120  mov     rcx, [rcx+30h]
0x14000d124  mov     rax, [rcx]
0x14000d127  mov     rax, [rax+8]
0x14000d12b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
