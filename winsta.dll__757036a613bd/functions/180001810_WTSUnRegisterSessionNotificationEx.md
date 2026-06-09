# WTSUnRegisterSessionNotificationEx

- ea: `0x180001810`
- end: `0x180001899`
- name: `WTSUnRegisterSessionNotificationEx`
- size: `137`
- prototype: `BOOL __stdcall(HANDLE hServer, HWND hWnd)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180001810`
- `0x180001908`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001884`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001891`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001884`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001891`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001843`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001843`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000183d`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000183d`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000182b`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000182b`

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
0x180001810  mov     [rsp+arg_0], rbx
0x180001815  push    rdi
0x180001816  sub     rsp, 20h
0x18000181a  mov     rdi, rcx
0x18000181d  mov     [rsp+28h+dwProcessId], 0
0x180001825  mov     rcx, rdx; hWnd
0x180001828  mov     rbx, rdx
0x18000182b  call    cs:__imp_IsWindow
0x180001831  test    eax, eax
0x180001833  jz      short loc_180001878
0x180001835  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x18000183a  mov     rcx, rbx; hWnd
0x18000183d  call    cs:__imp_GetWindowThreadProcessId
0x180001843  call    cs:__imp_GetCurrentProcessId
0x180001849  cmp     [rsp+28h+dwProcessId], eax
0x18000184d  jnz     short loc_18000187F
0x18000184f  mov     r8d, 1; int
0x180001855  mov     rdx, rbx; HWND
0x180001858  mov     rcx, rdi; void *
0x18000185b  call    ?DeleteWindowNotification@CWindowNotification@@SAJPEAXPEAUHWND__@@H@Z; CWindowNotification::DeleteWindowNotification(void *,HWND__ *,int)
0x180001860  mov     ebx, eax
0x180001862  test    eax, eax
0x180001864  js      short loc_18000188E
0x180001866  not     ebx
0x180001868  shr     ebx, 1Fh
0x18000186b  mov     eax, ebx
0x18000186d  mov     rbx, [rsp+28h+arg_0]
0x180001872  add     rsp, 20h
0x180001876  pop     rdi
0x180001877  retn
0x180001878  mov     ecx, 57h ; 'W'
0x18000187d  jmp     short loc_180001884
0x18000187f  mov     ecx, 580h; dwErrCode
0x180001884  call    cs:__imp_SetLastError
0x18000188a  xor     eax, eax
0x18000188c  jmp     short loc_18000186D
0x18000188e  movzx   ecx, bx; dwErrCode
0x180001891  call    cs:__imp_SetLastError
0x180001897  jmp     short loc_180001866
```
