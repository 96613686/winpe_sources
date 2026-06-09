# wil::last_error_context::last_error_context(void)

- ea: `0x1800064b0`
- end: `0x1800064ce`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800063f4`
- `0x1800064d4`
- `0x18000dd5c`
- `0x18000ebc4`
- `0x180012040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064b9`

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
0x1800064b0  push    rbx
0x1800064b2  sub     rsp, 20h
0x1800064b6  mov     rbx, rcx
0x1800064b9  call    cs:__imp_GetLastError
0x1800064bf  mov     [rbx+4], eax
0x1800064c2  mov     rax, rbx
0x1800064c5  mov     byte ptr [rbx], 0
0x1800064c8  add     rsp, 20h
0x1800064cc  pop     rbx
0x1800064cd  retn
```
