# wil::last_error_context::last_error_context(void)

- ea: `0x18000d334`
- end: `0x18000d352`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x1800097ac`
- `0x18000a268`
- `0x18000ca00`
- `0x18000ca7c`
- `0x18000dc28`
- `0x180010a7c`
- `0x180010b24`
- `0x180010b78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d33d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d33d`

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
0x18000d334  push    rbx
0x18000d336  sub     rsp, 20h
0x18000d33a  mov     rbx, rcx
0x18000d33d  call    cs:__imp_GetLastError
0x18000d343  mov     [rbx+4], eax
0x18000d346  mov     rax, rbx
0x18000d349  mov     byte ptr [rbx], 0
0x18000d34c  add     rsp, 20h
0x18000d350  pop     rbx
0x18000d351  retn
```
