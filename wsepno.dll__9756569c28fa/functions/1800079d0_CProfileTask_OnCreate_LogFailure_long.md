# CProfileTask_OnCreate::LogFailure(long)

- ea: `0x1800079d0`
- end: `0x1800079dd`
- name: `?LogFailure@CProfileTask_OnCreate@@UEAAXJ@Z`
- size: `13`
- prototype: `void(CProfileTask_OnCreate *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180008510`

## pseudocode

```c
void __fastcall CProfileTask_OnCreate::LogFailure(const wchar_t **this, DWORD a2)
{
  Profile_LogCreateFailure(a2, this[1]);
}

```

## disassembly

```asm
0x1800079d0  mov     eax, edx
0x1800079d2  mov     rdx, [rcx+8]; wchar_t *
0x1800079d6  mov     ecx, eax; dwMessageId
0x1800079d8  jmp     ?Profile_LogCreateFailure@@YAXJPEB_W@Z; Profile_LogCreateFailure(long,wchar_t const *)
```
