# wil::last_error_context::~last_error_context(void)

- ea: `0x18000dbd4`
- end: `0x18000dbeb`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e388`
- `0x18000ffbc`
- `0x18001038c`
- `0x18001261c`
- `0x1800126c4`
- `0x180012718`
- `0x18001276c`

## callees

- `0x18000dbd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dbe0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dbe0`

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
0x18000dbd4  sub     rsp, 28h
0x18000dbd8  cmp     byte ptr [rcx], 0
0x18000dbdb  jnz     short loc_18000DBE6
0x18000dbdd  mov     ecx, [rcx+4]; dwErrCode
0x18000dbe0  call    cs:__imp_SetLastError
0x18000dbe6  add     rsp, 28h
0x18000dbea  retn
```
