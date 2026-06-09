# ComTaskMgrWnd::DestroyShutdownBlockMessage(void)

- ea: `0x140003e20`
- end: `0x140003e4d`
- name: `?DestroyShutdownBlockMessage@ComTaskMgrWnd@@AEBAJXZ`
- size: `45`
- prototype: `signed int __fastcall(HWND *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003b10`

## callees

- `0x140003e20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003e32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003e32`
- `ext-ms-win-ntuser-misc-l1-1-0!ShutdownBlockReasonDestroy` at `0x140003e28`
- `ext-ms-win-ntuser-misc-l1-1-0!ShutdownBlockReasonDestroy` at `0x140003e28`

## pseudocode

```c
signed int __fastcall ComTaskMgrWnd::DestroyShutdownBlockMessage(HWND *this)
{
  signed int result; // eax

  if ( ShutdownBlockReasonDestroy(this[3]) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140003e20  sub     rsp, 28h
0x140003e24  mov     rcx, [rcx+18h]; hWnd
0x140003e28  call    cs:__imp_ShutdownBlockReasonDestroy
0x140003e2e  test    eax, eax
0x140003e30  jnz     short loc_140003E46
0x140003e32  call    cs:__imp_GetLastError
0x140003e38  test    eax, eax
0x140003e3a  jle     short loc_140003E48
0x140003e3c  movzx   eax, ax
0x140003e3f  or      eax, 80070000h
0x140003e44  jmp     short loc_140003E48
0x140003e46  xor     eax, eax
0x140003e48  add     rsp, 28h
0x140003e4c  retn
```
