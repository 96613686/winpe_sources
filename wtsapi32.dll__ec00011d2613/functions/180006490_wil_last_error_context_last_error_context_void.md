# wil::last_error_context::~last_error_context(void)

- ea: `0x180006490`
- end: `0x1800064a7`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800063f4`
- `0x1800064d4`
- `0x18000dd5c`
- `0x18000ebc4`
- `0x180012040`

## callees

- `0x180006490`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000649c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000649c`

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
0x180006490  sub     rsp, 28h
0x180006494  cmp     byte ptr [rcx], 0
0x180006497  jnz     short loc_1800064A2
0x180006499  mov     ecx, [rcx+4]; dwErrCode
0x18000649c  call    cs:__imp_SetLastError
0x1800064a2  add     rsp, 28h
0x1800064a6  retn
```
