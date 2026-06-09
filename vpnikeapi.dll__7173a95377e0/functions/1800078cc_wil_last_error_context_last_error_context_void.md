# wil::last_error_context::last_error_context(void)

- ea: `0x1800078cc`
- end: `0x1800078ea`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180008438`
- `0x18000a0a4`
- `0x18000a4dc`
- `0x18000bf00`
- `0x18000bfa8`
- `0x18000bffc`
- `0x18000c050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078d5`

## pseudocode

```c
wil::last_error_context *__fastcall wil::last_error_context::last_error_context(wil::last_error_context *this)
{
  wil::last_error_context *result; // rax

  *((_DWORD *)this + 1) = GetLastError();
  result = this;
  *(_BYTE *)this = 0;
  return result;
}

```

## disassembly

```asm
0x1800078cc  push    rbx
0x1800078ce  sub     rsp, 20h
0x1800078d2  mov     rbx, rcx
0x1800078d5  call    cs:__imp_GetLastError
0x1800078db  mov     [rbx+4], eax
0x1800078de  mov     rax, rbx
0x1800078e1  mov     byte ptr [rbx], 0
0x1800078e4  add     rsp, 20h
0x1800078e8  pop     rbx
0x1800078e9  retn
```
