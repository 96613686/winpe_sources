# _GetProcFromComCtl32

- ea: `0x18000a150`
- end: `0x18000a190`
- name: `_GetProcFromComCtl32`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a0b0`

## callees

- `0x18000a03c`
- `0x18000a150`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a181`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a181`

## string_xrefs

- `0x18000a17a`: `TaskDialogIndirect`

## pseudocode

```c
FARPROC __fastcall GetProcFromComCtl32(FARPROC *a1)
{
  HMODULE v2; // rcx
  FARPROC result; // rax

  v2 = g_hinstCC;
  if ( g_hinstCC || (DelayLoadCC(), (v2 = g_hinstCC) != 0) )
    result = GetProcAddress(v2, "TaskDialogIndirect");
  else
    result = 0;
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x18000a150  push    rbx
0x18000a152  sub     rsp, 20h
0x18000a156  mov     rbx, rcx
0x18000a159  mov     rcx, cs:g_hinstCC; hModule
0x18000a160  test    rcx, rcx
0x18000a163  jnz     short loc_18000A17A
0x18000a165  call    DelayLoadCC
0x18000a16a  mov     rcx, cs:g_hinstCC
0x18000a171  test    rcx, rcx
0x18000a174  jnz     short loc_18000A17A
0x18000a176  xor     eax, eax
0x18000a178  jmp     short loc_18000A187
0x18000a17a  lea     rdx, ProcName; "TaskDialogIndirect"
0x18000a181  call    cs:__imp_GetProcAddress
0x18000a187  mov     [rbx], rax
0x18000a18a  add     rsp, 20h
0x18000a18e  pop     rbx
0x18000a18f  retn
```
