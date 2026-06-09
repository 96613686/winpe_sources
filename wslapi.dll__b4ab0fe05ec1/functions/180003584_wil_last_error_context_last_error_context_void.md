# wil::last_error_context::~last_error_context(void)

- ea: `0x180003584`
- end: `0x18000359b`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180004cfc`
- `0x180005acc`
- `0x180007520`
- `0x180007590`
- `0x180009130`

## callees

- `0x180003584`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003590`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003590`

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
0x180003584  sub     rsp, 28h
0x180003588  cmp     byte ptr [rcx], 0
0x18000358b  jnz     short loc_180003596
0x18000358d  mov     ecx, [rcx+4]; dwErrCode
0x180003590  call    cs:__imp_SetLastError
0x180003596  add     rsp, 28h
0x18000359a  retn
```
