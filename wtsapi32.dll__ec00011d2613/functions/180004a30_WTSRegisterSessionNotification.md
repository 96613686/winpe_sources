# WTSRegisterSessionNotification

- ea: `0x180004a30`
- end: `0x180004aa8`
- name: `WTSRegisterSessionNotification`
- size: `120`
- prototype: `BOOL __stdcall(HWND hWnd, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180004a30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004a56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004a56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004a77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004a77`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180004a71`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180004a71`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180004a47`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180004a47`
- `WINSTA!WinStationRegisterSessionNotification` at `0x180004a90`
- `WINSTA!WinStationRegisterSessionNotification` at `0x180004a90`

## pseudocode

```c
BOOL __stdcall WTSRegisterSessionNotification(HWND hWnd, DWORD dwFlags)
{
  DWORD v4; // ecx
  DWORD dwProcessId; // [rsp+40h] [rbp+18h] BYREF

  dwProcessId = 0;
  if ( !IsWindow(hWnd) )
    goto LABEL_2;
  GetWindowThreadProcessId(hWnd, &dwProcessId);
  if ( dwProcessId != GetCurrentProcessId() )
  {
    v4 = 1408;
    goto LABEL_3;
  }
  if ( dwFlags >= 2 )
  {
LABEL_2:
    v4 = 87;
LABEL_3:
    SetLastError(v4);
    return 0;
  }
  return WinStationRegisterSessionNotification(0, hWnd, dwFlags);
}

```

## disassembly

```asm
0x180004a30  mov     [rsp+arg_0], rbx
0x180004a35  push    rdi
0x180004a36  sub     rsp, 20h
0x180004a3a  mov     edi, edx
0x180004a3c  mov     [rsp+28h+dwProcessId], 0
0x180004a44  mov     rbx, rcx
0x180004a47  call    cs:__imp_IsWindow
0x180004a4d  test    eax, eax
0x180004a4f  jnz     short loc_180004A69
0x180004a51  mov     ecx, 57h ; 'W'; dwErrCode
0x180004a56  call    cs:__imp_SetLastError
0x180004a5c  xor     eax, eax
0x180004a5e  mov     rbx, [rsp+28h+arg_0]
0x180004a63  add     rsp, 20h
0x180004a67  pop     rdi
0x180004a68  retn
0x180004a69  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x180004a6e  mov     rcx, rbx; hWnd
0x180004a71  call    cs:__imp_GetWindowThreadProcessId
0x180004a77  call    cs:__imp_GetCurrentProcessId
0x180004a7d  cmp     [rsp+28h+dwProcessId], eax
0x180004a81  jnz     short loc_180004AA1
0x180004a83  cmp     edi, 2
0x180004a86  jnb     short loc_180004A51
0x180004a88  mov     r8d, edi
0x180004a8b  mov     rdx, rbx
0x180004a8e  xor     ecx, ecx
0x180004a90  call    cs:__imp_WinStationRegisterSessionNotification
0x180004a96  mov     rbx, [rsp+28h+arg_0]
0x180004a9b  add     rsp, 20h
0x180004a9f  pop     rdi
0x180004aa0  retn
0x180004aa1  mov     ecx, 580h
0x180004aa6  jmp     short loc_180004A56
```
