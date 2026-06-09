# CProfileTask_OnDelete::LogFailure(long)

- ea: `0x1800079f0`
- end: `0x1800079fd`
- name: `?LogFailure@CProfileTask_OnDelete@@UEAAXJ@Z`
- size: `13`
- prototype: `void(CProfileTask_OnDelete *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180008648`

## pseudocode

```c
void __fastcall CProfileTask_OnDelete::LogFailure(const wchar_t **this, DWORD a2)
{
  Profile_LogDeleteFailure(a2, this[2]);
}

```

## disassembly

```asm
0x1800079f0  mov     eax, edx
0x1800079f2  mov     rdx, [rcx+10h]; wchar_t *
0x1800079f6  mov     ecx, eax; dwMessageId
0x1800079f8  jmp     ?Profile_LogDeleteFailure@@YAXJPEB_WK@Z; Profile_LogDeleteFailure(long,wchar_t const *,ulong)
```
