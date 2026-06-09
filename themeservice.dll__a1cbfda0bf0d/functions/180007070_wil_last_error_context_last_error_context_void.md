# wil::last_error_context::last_error_context(void)

- ea: `0x180007070`
- end: `0x18000708e`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800060c0`
- `0x180006d88`
- `0x180006e30`
- `0x180006f24`
- `0x18000a334`
- `0x18000a388`
- `0x18000abfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007079`

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
0x180007070  push    rbx
0x180007072  sub     rsp, 20h
0x180007076  mov     rbx, rcx
0x180007079  call    cs:__imp_GetLastError
0x18000707f  mov     [rbx+4], eax
0x180007082  mov     rax, rbx
0x180007085  mov     byte ptr [rbx], 0
0x180007088  add     rsp, 20h
0x18000708c  pop     rbx
0x18000708d  retn
```
