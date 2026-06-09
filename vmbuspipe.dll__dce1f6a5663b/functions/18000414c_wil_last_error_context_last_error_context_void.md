# wil::last_error_context::~last_error_context(void)

- ea: `0x18000414c`
- end: `0x180004163`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001f84`
- `0x180002064`
- `0x180006a10`
- `0x180006eac`

## callees

- `0x18000414c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004158`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004158`

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
0x18000414c  sub     rsp, 28h
0x180004150  cmp     byte ptr [rcx], 0
0x180004153  jnz     short loc_18000415E
0x180004155  mov     ecx, [rcx+4]; dwErrCode
0x180004158  call    cs:__imp_SetLastError
0x18000415e  add     rsp, 28h
0x180004162  retn
```
