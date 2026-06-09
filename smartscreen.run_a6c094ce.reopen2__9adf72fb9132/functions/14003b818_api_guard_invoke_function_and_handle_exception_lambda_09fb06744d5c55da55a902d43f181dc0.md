# api_guard::invoke_function_and_handle_exception__lambda_09fb06744d5c55da55a902d43f181dc0__&_

- ea: `0x14003b818`
- end: `0x14003b83b`
- name: `api_guard::invoke_function_and_handle_exception__lambda_09fb06744d5c55da55a902d43f181dc0__&_`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14003d780`

## callees

- `0x14003b818`

## import_xrefs

- `SmartScreen!ClearCache` at `0x14003b821`
- `SmartScreen!ClearCache` at `0x14003b821`

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
0x14003b818  mov     [rsp+arg_8], rdx
0x14003b81d  sub     rsp, 28h
0x14003b821  call    cs:__imp_ClearCache
0x14003b828  nop     dword ptr [rax+rax+00h]
0x14003b82d  xor     eax, eax
0x14003b82f  jmp     short loc_14003B835
0x14003b831  mov     eax, dword ptr [rsp+28h+arg_8]
0x14003b835  add     rsp, 28h
0x14003b839  retn
```
