# wil::last_error_context::last_error_context(void)

- ea: `0x180018570`
- end: `0x180018595`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `37`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800190e0`
- `0x18001ab7c`
- `0x18001af74`
- `0x18001c904`
- `0x18001c9b8`
- `0x18001ca0c`
- `0x18001ca60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018579`

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
0x180018570  push    rbx
0x180018572  sub     rsp, 20h
0x180018576  mov     rbx, rcx
0x180018579  call    cs:__imp_GetLastError
0x180018580  nop     dword ptr [rax+rax+00h]
0x180018585  mov     [rbx+4], eax
0x180018588  mov     rax, rbx
0x18001858b  mov     byte ptr [rbx], 0
0x18001858e  add     rsp, 20h
0x180018592  pop     rbx
0x180018593  retn
```
