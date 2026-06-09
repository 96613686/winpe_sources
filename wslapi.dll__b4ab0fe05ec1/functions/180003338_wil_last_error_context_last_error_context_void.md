# wil::last_error_context::last_error_context(void)

- ea: `0x180003338`
- end: `0x180003356`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180004cfc`
- `0x180005acc`
- `0x180007520`
- `0x180007590`
- `0x180009130`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003341`

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
0x180003338  push    rbx
0x18000333a  sub     rsp, 20h
0x18000333e  mov     rbx, rcx
0x180003341  call    cs:__imp_GetLastError
0x180003347  mov     [rbx+4], eax
0x18000334a  mov     rax, rbx
0x18000334d  mov     byte ptr [rbx], 0
0x180003350  add     rsp, 20h
0x180003354  pop     rbx
0x180003355  retn
```
