# wil::last_error_context::last_error_context(void)

- ea: `0x18001724c`
- end: `0x18001726a`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180017d18`
- `0x1800196c8`
- `0x180019a9c`
- `0x18001b450`
- `0x18001b4f8`
- `0x18001b54c`
- `0x18001b5a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017255`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017255`

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
0x18001724c  push    rbx
0x18001724e  sub     rsp, 20h
0x180017252  mov     rbx, rcx
0x180017255  call    cs:__imp_GetLastError
0x18001725b  mov     [rbx+4], eax
0x18001725e  mov     rax, rbx
0x180017261  mov     byte ptr [rbx], 0
0x180017264  add     rsp, 20h
0x180017268  pop     rbx
0x180017269  retn
```
