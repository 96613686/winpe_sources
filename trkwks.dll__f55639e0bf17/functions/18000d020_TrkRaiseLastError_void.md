# TrkRaiseLastError(void)

- ea: `0x18000d020`
- end: `0x18000d032`
- name: `?TrkRaiseLastError@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d4c`
- `0x180001e28`
- `0x180002c90`
- `0x1800077b0`
- `0x180008718`
- `0x1800090c8`
- `0x18000a65c`
- `0x18000a880`
- `0x180010638`

## callees

- `0x18000d038`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d024`

## pseudocode

```c
void __noreturn TrkRaiseLastError(void)
{
  DWORD LastError; // eax

  LastError = GetLastError();
  TrkRaiseWin32Error(LastError);
}

```

## disassembly

```asm
0x18000d020  sub     rsp, 28h
0x18000d024  call    cs:__imp_GetLastError
0x18000d02a  mov     ecx, eax; int
0x18000d02c  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
```
