# wil::last_error_context::last_error_context(void)

- ea: `0x180003e54`
- end: `0x180003e72`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001f84`
- `0x180002064`
- `0x180006a10`
- `0x180006eac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e5d`

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
0x180003e54  push    rbx
0x180003e56  sub     rsp, 20h
0x180003e5a  mov     rbx, rcx
0x180003e5d  call    cs:__imp_GetLastError
0x180003e63  mov     [rbx+4], eax
0x180003e66  mov     rax, rbx
0x180003e69  mov     byte ptr [rbx], 0
0x180003e6c  add     rsp, 20h
0x180003e70  pop     rbx
0x180003e71  retn
```
