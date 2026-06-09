# CProfileTask_OnMigrate::LogFailure(long)

- ea: `0x180007a10`
- end: `0x180007a21`
- name: `?LogFailure@CProfileTask_OnMigrate@@UEAAXJ@Z`
- size: `17`
- prototype: `void(CProfileTask_OnMigrate *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800087a8`

## pseudocode

```c
void __fastcall CProfileTask_OnMigrate::LogFailure(const wchar_t **this, DWORD a2, __int64 a3, const wchar_t *a4)
{
  Profile_LogMigrateFailure(a2, this[1], this[2], a4);
}

```

## disassembly

```asm
0x180007a10  mov     r8, [rcx+10h]; wchar_t *
0x180007a14  mov     eax, edx
0x180007a16  mov     rdx, [rcx+8]; wchar_t *
0x180007a1a  mov     ecx, eax; dwMessageId
0x180007a1c  jmp     ?Profile_LogMigrateFailure@@YAXJPEB_W00@Z; Profile_LogMigrateFailure(long,wchar_t const *,wchar_t const *,wchar_t const *)
```
