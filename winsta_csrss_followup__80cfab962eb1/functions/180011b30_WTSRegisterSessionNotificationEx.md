# WTSRegisterSessionNotificationEx

- ea: `0x180011b30`
- end: `0x180011bcd`
- name: `WTSRegisterSessionNotificationEx`
- size: `157`
- prototype: `BOOL __stdcall(HANDLE hServer, HWND hWnd, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180011b30`
- `0x180011bf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011b9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011b9b`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180011b8f`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180011b8f`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180011b53`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180011b53`

## pseudocode

```c
BOOL __stdcall WTSRegisterSessionNotificationEx(HANDLE hServer, HWND hWnd, DWORD dwFlags)
{
  DWORD v6; // ecx
  DWORD dwProcessId; // [rsp+48h] [rbp+20h] BYREF

  dwProcessId = 0;
  if ( !IsWindow(hWnd) )
    goto LABEL_2;
  GetWindowThreadProcessId(hWnd, &dwProcessId);
  if ( dwProcessId != GetCurrentProcessId() )
  {
    v6 = 1408;
    goto LABEL_3;
  }
  if ( dwFlags >= 2 )
  {
LABEL_2:
    v6 = 87;
LABEL_3:
    SetLastError(v6);
    return 0;
  }
  return _tsrpcRegisterForSessionNotifications(hServer, hWnd, dwFlags, 0xFFFFFFFF);
}

```

## disassembly

```asm
0x180011b30  mov     [rsp+arg_0], rbx
0x180011b35  mov     [rsp+arg_8], rsi
0x180011b3a  push    rdi
0x180011b3b  sub     rsp, 20h
0x180011b3f  mov     rsi, rcx
0x180011b42  mov     [rsp+28h+dwProcessId], 0
0x180011b4a  mov     rcx, rdx; hWnd
0x180011b4d  mov     edi, r8d
0x180011b50  mov     rbx, rdx
0x180011b53  call    cs:__imp_IsWindow
0x180011b5a  nop     dword ptr [rax+rax+00h]
0x180011b5f  test    eax, eax
0x180011b61  jnz     short loc_180011B87
0x180011b63  mov     ecx, 57h ; 'W'; dwErrCode
0x180011b68  call    cs:__imp_SetLastError
0x180011b6f  nop     dword ptr [rax+rax+00h]
0x180011b74  xor     eax, eax
0x180011b76  mov     rbx, [rsp+28h+arg_0]
0x180011b7b  mov     rsi, [rsp+28h+arg_8]
0x180011b80  add     rsp, 20h
0x180011b84  pop     rdi
0x180011b85  retn
0x180011b87  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x180011b8c  mov     rcx, rbx; hWnd
0x180011b8f  call    cs:__imp_GetWindowThreadProcessId
0x180011b96  nop     dword ptr [rax+rax+00h]
0x180011b9b  call    cs:__imp_GetCurrentProcessId
0x180011ba2  nop     dword ptr [rax+rax+00h]
0x180011ba7  cmp     [rsp+28h+dwProcessId], eax
0x180011bab  jnz     short loc_180011BC6
0x180011bad  cmp     edi, 2
0x180011bb0  jnb     short loc_180011B63
0x180011bb2  or      r9d, 0FFFFFFFFh; unsigned int
0x180011bb6  mov     r8d, edi; unsigned int
0x180011bb9  mov     rdx, rbx; HWND
0x180011bbc  mov     rcx, rsi; void *
0x180011bbf  call    ?_tsrpcRegisterForSessionNotifications@@YAHPEAXPEAUHWND__@@KK@Z; _tsrpcRegisterForSessionNotifications(void *,HWND__ *,ulong,ulong)
0x180011bc4  jmp     short loc_180011B76
0x180011bc6  mov     ecx, 580h
0x180011bcb  jmp     short loc_180011B68
```
