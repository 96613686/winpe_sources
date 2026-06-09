# wil::last_error_context::last_error_context(void)

- ea: `0x18000d650`
- end: `0x18000d66e`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e388`
- `0x18000ffbc`
- `0x18001038c`
- `0x18001261c`
- `0x1800126c4`
- `0x180012718`
- `0x18001276c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d659`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d659`

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
0x18000d650  push    rbx
0x18000d652  sub     rsp, 20h
0x18000d656  mov     rbx, rcx
0x18000d659  call    cs:__imp_GetLastError
0x18000d65f  mov     [rbx+4], eax
0x18000d662  mov     rax, rbx
0x18000d665  mov     byte ptr [rbx], 0
0x18000d668  add     rsp, 20h
0x18000d66c  pop     rbx
0x18000d66d  retn
```
