# wil::last_error_context::~last_error_context(void)

- ea: `0x180007e30`
- end: `0x180007e47`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180008438`
- `0x18000a0a4`
- `0x18000a4dc`
- `0x18000bf00`
- `0x18000bfa8`
- `0x18000bffc`
- `0x18000c050`

## callees

- `0x180007e30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007e3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007e3c`

## pseudocode

```c
void __fastcall wil::last_error_context::~last_error_context(wil::last_error_context *this)
{
  if ( !*(_BYTE *)this )
    SetLastError(*((_DWORD *)this + 1));
}

```

## disassembly

```asm
0x180007e30  sub     rsp, 28h
0x180007e34  cmp     byte ptr [rcx], 0
0x180007e37  jnz     short loc_180007E42
0x180007e39  mov     ecx, [rcx+4]; dwErrCode
0x180007e3c  call    cs:__imp_SetLastError
0x180007e42  add     rsp, 28h
0x180007e46  retn
```
