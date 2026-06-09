# WTSUnRegisterSessionNotification

- ea: `0x180004af0`
- end: `0x180004b50`
- name: `WTSUnRegisterSessionNotification`
- size: `96`
- prototype: `BOOL __stdcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180004af0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004b19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004b19`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180004b13`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180004b13`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180004b01`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180004b01`
- `WINSTA!WinStationUnRegisterSessionNotification` at `0x180004b2a`
- `WINSTA!WinStationUnRegisterSessionNotification` at `0x180004b2a`

## pseudocode

```c
BOOL __stdcall WTSUnRegisterSessionNotification(HWND hWnd)
{
  DWORD v3; // ecx
  DWORD dwProcessId; // [rsp+38h] [rbp+10h] BYREF

  dwProcessId = 0;
  if ( IsWindow(hWnd) )
  {
    GetWindowThreadProcessId(hWnd, &dwProcessId);
    if ( dwProcessId == GetCurrentProcessId() )
      return WinStationUnRegisterSessionNotification(0, hWnd);
    v3 = 1408;
  }
  else
  {
    v3 = 87;
  }
  SetLastError(v3);
  return 0;
}

```

## disassembly

```asm
0x180004af0  push    rbx
0x180004af2  sub     rsp, 20h
0x180004af6  mov     rbx, rcx
0x180004af9  mov     [rsp+28h+dwProcessId], 0
0x180004b01  call    cs:__imp_IsWindow
0x180004b07  test    eax, eax
0x180004b09  jz      short loc_180004B36
0x180004b0b  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x180004b10  mov     rcx, rbx; hWnd
0x180004b13  call    cs:__imp_GetWindowThreadProcessId
0x180004b19  call    cs:__imp_GetCurrentProcessId
0x180004b1f  cmp     [rsp+28h+dwProcessId], eax
0x180004b23  jnz     short loc_180004B49
0x180004b25  mov     rdx, rbx
0x180004b28  xor     ecx, ecx
0x180004b2a  call    cs:__imp_WinStationUnRegisterSessionNotification
0x180004b30  add     rsp, 20h
0x180004b34  pop     rbx
0x180004b35  retn
0x180004b36  mov     ecx, 57h ; 'W'; dwErrCode
0x180004b3b  call    cs:__imp_SetLastError
0x180004b41  xor     eax, eax
0x180004b43  add     rsp, 20h
0x180004b47  pop     rbx
0x180004b48  retn
0x180004b49  mov     ecx, 580h
0x180004b4e  jmp     short loc_180004B3B
```
