# WsUpdateStatus

- ea: `0x180006dbc`
- end: `0x180006e03`
- name: `WsUpdateStatus`
- size: `71`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x180006a98`
- `0x18000743c`
- `0x18000a920`
- `0x18002fe70`
- `0x180030544`

## callees

- `0x180006dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006dec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006dec`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006ddc`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006ddc`

## pseudocode

```c
__int64 WsUpdateStatus()
{
  unsigned int v1; // ebx

  if ( !hServiceStatus )
    return 6;
  v1 = 0;
  if ( !SetServiceStatus(hServiceStatus, &WsGlobalData) )
    return GetLastError();
  return v1;
}

```

## disassembly

```asm
0x180006dbc  push    rbx
0x180006dbe  sub     rsp, 20h
0x180006dc2  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180006dc9  test    rcx, rcx
0x180006dcc  jnz     short loc_180006DD3
0x180006dce  lea     eax, [rcx+6]
0x180006dd1  jmp     short loc_180006DFC
0x180006dd3  lea     rdx, WsGlobalData; lpServiceStatus
0x180006dda  xor     ebx, ebx
0x180006ddc  call    cs:__imp_SetServiceStatus
0x180006de3  nop     dword ptr [rax+rax+00h]
0x180006de8  test    eax, eax
0x180006dea  jnz     short loc_180006DFA
0x180006dec  call    cs:__imp_GetLastError
0x180006df3  nop     dword ptr [rax+rax+00h]
0x180006df8  mov     ebx, eax
0x180006dfa  mov     eax, ebx
0x180006dfc  add     rsp, 20h
0x180006e00  pop     rbx
0x180006e01  retn
```
