# IsWindowOnCurrentThread(HWND__ *)

- ea: `0x180039de4`
- end: `0x180039e2a`
- name: `?IsWindowOnCurrentThread@@YA_NPEAUHWND__@@@Z`
- size: `70`
- prototype: `bool __fastcall(HWND hWnd)`
- caller_count: `9`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180039674`
- `0x180039860`
- `0x180039a30`
- `0x180039b70`
- `0x18008d458`
- `0x18008d538`
- `0x18008dcbc`
- `0x18008f110`
- `0x18008f240`

## callees

- `0x180039de4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039e0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039e0b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x180039df4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x180039df4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180039e03`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180039e03`

## pseudocode

```c
char __fastcall IsWindowOnCurrentThread(HWND hWnd)
{
  char v2; // di
  DWORD WindowThreadProcessId; // ebx

  v2 = 1;
  if ( IsWindow(hWnd) )
  {
    WindowThreadProcessId = GetWindowThreadProcessId(hWnd, 0);
    return GetCurrentThreadId() == WindowThreadProcessId;
  }
  return v2;
}

```

## disassembly

```asm
0x180039de4  mov     [rsp+arg_0], rbx
0x180039de9  push    rdi
0x180039dea  sub     rsp, 20h
0x180039dee  mov     rbx, rcx
0x180039df1  mov     dil, 1
0x180039df4  call    cs:__imp_IsWindow
0x180039dfa  test    eax, eax
0x180039dfc  jz      short loc_180039E1C
0x180039dfe  xor     edx, edx; lpdwProcessId
0x180039e00  mov     rcx, rbx; hWnd
0x180039e03  call    cs:__imp_GetWindowThreadProcessId
0x180039e09  mov     ebx, eax
0x180039e0b  call    cs:__imp_GetCurrentThreadId
0x180039e11  xor     ecx, ecx
0x180039e13  movzx   edi, dil
0x180039e17  cmp     eax, ebx
0x180039e19  cmovnz  edi, ecx
0x180039e1c  mov     rbx, [rsp+28h+arg_0]
0x180039e21  mov     al, dil
0x180039e24  add     rsp, 20h
0x180039e28  pop     rdi
0x180039e29  retn
```
