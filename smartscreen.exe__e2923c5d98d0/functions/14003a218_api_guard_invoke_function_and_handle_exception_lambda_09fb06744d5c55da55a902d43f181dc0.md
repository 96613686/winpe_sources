# api_guard::invoke_function_and_handle_exception__lambda_09fb06744d5c55da55a902d43f181dc0__&_

- ea: `0x14003a218`
- end: `0x14003a235`
- name: `api_guard::invoke_function_and_handle_exception__lambda_09fb06744d5c55da55a902d43f181dc0__&_`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14003c0c0`

## callees

- `0x14003a218`

## import_xrefs

- `SmartScreen!ClearCache` at `0x14003a221`
- `SmartScreen!ClearCache` at `0x14003a221`

## pseudocode

```c
__int64 api_guard::invoke_function_and_handle_exception__lambda_09fb06744d5c55da55a902d43f181dc0____()
{
  ClearCache();
  return 0;
}

```

## disassembly

```asm
0x14003a218  mov     [rsp+arg_8], rdx
0x14003a21d  sub     rsp, 28h
0x14003a221  call    cs:__imp_ClearCache
0x14003a227  xor     eax, eax
0x14003a229  jmp     short loc_14003A22F
0x14003a22b  mov     eax, dword ptr [rsp+28h+arg_8]
0x14003a22f  add     rsp, 28h
0x14003a233  retn
```
