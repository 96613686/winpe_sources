# WTSRegisterSessionNotificationEx

- ea: `0x180010b90`
- end: `0x180010c14`
- name: `WTSRegisterSessionNotificationEx`
- size: `132`
- prototype: `BOOL __stdcall(HANDLE hServer, HWND hWnd, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180010b90`
- `0x180010c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010bc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010bc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010be8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010be8`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180010be2`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180010be2`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180010bb3`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180010bb3`

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
0x180010b90  mov     [rsp+arg_0], rbx
0x180010b95  mov     [rsp+arg_8], rsi
0x180010b9a  push    rdi
0x180010b9b  sub     rsp, 20h
0x180010b9f  mov     rsi, rcx
0x180010ba2  mov     [rsp+28h+dwProcessId], 0
0x180010baa  mov     rcx, rdx; hWnd
0x180010bad  mov     edi, r8d
0x180010bb0  mov     rbx, rdx
0x180010bb3  call    cs:__imp_IsWindow
0x180010bb9  test    eax, eax
0x180010bbb  jnz     short loc_180010BDA
0x180010bbd  mov     ecx, 57h ; 'W'; dwErrCode
0x180010bc2  call    cs:__imp_SetLastError
0x180010bc8  xor     eax, eax
0x180010bca  mov     rbx, [rsp+28h+arg_0]
0x180010bcf  mov     rsi, [rsp+28h+arg_8]
0x180010bd4  add     rsp, 20h
0x180010bd8  pop     rdi
0x180010bd9  retn
0x180010bda  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x180010bdf  mov     rcx, rbx; hWnd
0x180010be2  call    cs:__imp_GetWindowThreadProcessId
0x180010be8  call    cs:__imp_GetCurrentProcessId
0x180010bee  cmp     [rsp+28h+dwProcessId], eax
0x180010bf2  jnz     short loc_180010C0D
0x180010bf4  cmp     edi, 2
0x180010bf7  jnb     short loc_180010BBD
0x180010bf9  or      r9d, 0FFFFFFFFh; unsigned int
0x180010bfd  mov     r8d, edi; unsigned int
0x180010c00  mov     rdx, rbx; HWND
0x180010c03  mov     rcx, rsi; void *
0x180010c06  call    ?_tsrpcRegisterForSessionNotifications@@YAHPEAXPEAUHWND__@@KK@Z; _tsrpcRegisterForSessionNotifications(void *,HWND__ *,ulong,ulong)
0x180010c0b  jmp     short loc_180010BCA
0x180010c0d  mov     ecx, 580h
0x180010c12  jmp     short loc_180010BC2
```
