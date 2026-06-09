# wil::last_error_context::last_error_context(void)

- ea: `0x180013938`
- end: `0x180013956`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ff6c`
- `0x180012f5c`
- `0x1800156e0`
- `0x1800166ec`
- `0x180016794`
- `0x1800167e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013941`

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
0x180013938  push    rbx
0x18001393a  sub     rsp, 20h
0x18001393e  mov     rbx, rcx
0x180013941  call    cs:__imp_GetLastError
0x180013947  mov     [rbx+4], eax
0x18001394a  mov     rax, rbx
0x18001394d  mov     byte ptr [rbx], 0
0x180013950  add     rsp, 20h
0x180013954  pop     rbx
0x180013955  retn
```
