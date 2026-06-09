# wil::last_error_context::last_error_context(void)

- ea: `0x1800087dc`
- end: `0x1800087fa`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180008678`
- `0x180008720`
- `0x180008800`
- `0x18000ccf0`
- `0x18000d9e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087e5`

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
0x1800087dc  push    rbx
0x1800087de  sub     rsp, 20h
0x1800087e2  mov     rbx, rcx
0x1800087e5  call    cs:__imp_GetLastError
0x1800087eb  mov     [rbx+4], eax
0x1800087ee  mov     rax, rbx
0x1800087f1  mov     byte ptr [rbx], 0
0x1800087f4  add     rsp, 20h
0x1800087f8  pop     rbx
0x1800087f9  retn
```
