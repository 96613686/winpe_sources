# wil::last_error_context::~last_error_context(void)

- ea: `0x180006fec`
- end: `0x180007003`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800060c0`
- `0x180006d88`
- `0x180006e30`
- `0x180006f24`
- `0x18000a334`
- `0x18000a388`
- `0x18000abfc`

## callees

- `0x180006fec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ff8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ff8`

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
0x180006fec  sub     rsp, 28h
0x180006ff0  cmp     byte ptr [rcx], 0
0x180006ff3  jnz     short loc_180006FFE
0x180006ff5  mov     ecx, [rcx+4]; dwErrCode
0x180006ff8  call    cs:__imp_SetLastError
0x180006ffe  add     rsp, 28h
0x180007002  retn
```
