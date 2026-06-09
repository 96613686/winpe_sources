# WTSUnRegisterSessionNotificationEx

- ea: `0x18000d150`
- end: `0x18000d1f8`
- name: `WTSUnRegisterSessionNotificationEx`
- size: `168`
- prototype: `BOOL __stdcall(HANDLE hServer, HWND hWnd)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x18000b64c`
- `0x18000d150`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d1d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d1ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d1d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d1ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d18f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d18f`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000d183`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000d183`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000d16b`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000d16b`

## pseudocode

```c
BOOL __stdcall WTSUnRegisterSessionNotificationEx(HANDLE hServer, HWND hWnd)
{
  int v4; // eax
  int v5; // ebx
  DWORD v7; // ecx
  DWORD dwProcessId; // [rsp+40h] [rbp+18h] BYREF

  dwProcessId = 0;
  if ( !IsWindow(hWnd) )
  {
    v7 = 87;
LABEL_8:
    SetLastError(v7);
    return 0;
  }
  GetWindowThreadProcessId(hWnd, &dwProcessId);
  if ( dwProcessId != GetCurrentProcessId() )
  {
    v7 = 1408;
    goto LABEL_8;
  }
  v4 = CWindowNotification::DeleteWindowNotification(hServer, hWnd, 1);
  v5 = v4;
  if ( v4 < 0 )
    SetLastError((unsigned __int16)v4);
  return v5 >= 0;
}

```

## disassembly

```asm
0x18000d150  mov     [rsp+arg_0], rbx
0x18000d155  push    rdi
0x18000d156  sub     rsp, 20h
0x18000d15a  mov     rdi, rcx
0x18000d15d  mov     [rsp+28h+dwProcessId], 0
0x18000d165  mov     rcx, rdx; hWnd
0x18000d168  mov     rbx, rdx
0x18000d16b  call    cs:__imp_IsWindow
0x18000d172  nop     dword ptr [rax+rax+00h]
0x18000d177  test    eax, eax
0x18000d179  jz      short loc_18000D1CB
0x18000d17b  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x18000d180  mov     rcx, rbx; hWnd
0x18000d183  call    cs:__imp_GetWindowThreadProcessId
0x18000d18a  nop     dword ptr [rax+rax+00h]
0x18000d18f  call    cs:__imp_GetCurrentProcessId
0x18000d196  nop     dword ptr [rax+rax+00h]
0x18000d19b  cmp     [rsp+28h+dwProcessId], eax
0x18000d19f  jnz     short loc_18000D1D2
0x18000d1a1  mov     r8d, 1; int
0x18000d1a7  mov     rdx, rbx; HWND
0x18000d1aa  mov     rcx, rdi; void *
0x18000d1ad  call    ?DeleteWindowNotification@CWindowNotification@@SAJPEAXPEAUHWND__@@H@Z; CWindowNotification::DeleteWindowNotification(void *,HWND__ *,int)
0x18000d1b2  mov     ebx, eax
0x18000d1b4  test    eax, eax
0x18000d1b6  js      short loc_18000D1E7
0x18000d1b8  not     ebx
0x18000d1ba  shr     ebx, 1Fh
0x18000d1bd  mov     eax, ebx
0x18000d1bf  mov     rbx, [rsp+28h+arg_0]
0x18000d1c4  add     rsp, 20h
0x18000d1c8  pop     rdi
0x18000d1c9  retn
0x18000d1cb  mov     ecx, 57h ; 'W'
0x18000d1d0  jmp     short loc_18000D1D7
0x18000d1d2  mov     ecx, 580h; dwErrCode
0x18000d1d7  call    cs:__imp_SetLastError
0x18000d1de  nop     dword ptr [rax+rax+00h]
0x18000d1e3  xor     eax, eax
0x18000d1e5  jmp     short loc_18000D1BF
0x18000d1e7  movzx   ecx, bx; dwErrCode
0x18000d1ea  call    cs:__imp_SetLastError
0x18000d1f1  nop     dword ptr [rax+rax+00h]
0x18000d1f6  jmp     short loc_18000D1B8
```
