# wil::last_error_context::~last_error_context(void)

- ea: `0x180018a00`
- end: `0x180018a1e`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800190e0`
- `0x18001ab7c`
- `0x18001af74`
- `0x18001c904`
- `0x18001c9b8`
- `0x18001ca0c`
- `0x18001ca60`

## callees

- `0x180018a00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018a0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018a0c`

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
0x180018a00  sub     rsp, 28h
0x180018a04  cmp     byte ptr [rcx], 0
0x180018a07  jnz     short loc_180018A18
0x180018a09  mov     ecx, [rcx+4]; dwErrCode
0x180018a0c  call    cs:__imp_SetLastError
0x180018a13  nop     dword ptr [rax+rax+00h]
0x180018a18  add     rsp, 28h
0x180018a1c  retn
```
