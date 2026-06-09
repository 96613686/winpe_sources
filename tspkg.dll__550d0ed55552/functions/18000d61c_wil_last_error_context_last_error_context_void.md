# wil::last_error_context::~last_error_context(void)

- ea: `0x18000d61c`
- end: `0x18000d633`
- name: `??1last_error_context@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800097ac`
- `0x18000a268`
- `0x18000ca00`
- `0x18000ca7c`
- `0x18000dc28`
- `0x180010a7c`
- `0x180010b24`
- `0x180010b78`

## callees

- `0x18000d61c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d628`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d628`

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
0x18000d61c  sub     rsp, 28h
0x18000d620  cmp     byte ptr [rcx], 0
0x18000d623  jnz     short loc_18000D62E
0x18000d625  mov     ecx, [rcx+4]; dwErrCode
0x18000d628  call    cs:__imp_SetLastError
0x18000d62e  add     rsp, 28h
0x18000d632  retn
```
