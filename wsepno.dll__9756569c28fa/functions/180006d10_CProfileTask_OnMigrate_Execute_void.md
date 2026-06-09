# CProfileTask_OnMigrate::Execute(void)

- ea: `0x180006d10`
- end: `0x180006d1d`
- name: `?Execute@CProfileTask_OnMigrate@@UEAAJXZ`
- size: `13`
- prototype: `__int64 __fastcall(CProfileTask_OnMigrate *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006040`

## pseudocode

```c
__int64 __fastcall CProfileTask_OnMigrate::Execute(const wchar_t **this)
{
  return CProfileTask::DeletePerUserSearchRootsAndScopeRules((CProfileTask *)this, this[1], this[3]);
}

```

## disassembly

```asm
0x180006d10  mov     r8, [rcx+18h]; wchar_t *
0x180006d14  mov     rdx, [rcx+8]; wchar_t *
0x180006d18  jmp     ?DeletePerUserSearchRootsAndScopeRules@CProfileTask@@QEAAJPEB_W0@Z; CProfileTask::DeletePerUserSearchRootsAndScopeRules(wchar_t const *,wchar_t const *)
```
