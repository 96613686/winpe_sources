# HwndUtils::GetImageName(HWND__ *,ushort *,int)

- ea: `0x1801b02c4`
- end: `0x1801b034c`
- name: `?GetImageName@HwndUtils@@SAXPEAUHWND__@@PEAGH@Z`
- size: `136`
- prototype: `void __fastcall(HWND hWnd, LPWSTR lpBaseName, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800922e0`

## callees

- `0x1801b02c4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b0334`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b0334`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x1801b0329`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x1801b0329`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801b030c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801b030c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowLongPtrW` at `0x1801b02dc`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowLongPtrW` at `0x1801b02dc`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x1801b02fa`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x1801b02fa`

## pseudocode

```c
void __fastcall HwndUtils::GetImageName(HWND hWnd, LPWSTR lpBaseName, DWORD a3)
{
  HMODULE WindowLongPtrW; // rbp
  HANDLE v6; // rax
  void *v7; // rsi
  DWORD ModuleBaseNameW; // ebx
  DWORD dwProcessId; // [rsp+60h] [rbp+18h] BYREF

  dwProcessId = a3;
  WindowLongPtrW = (HMODULE)GetWindowLongPtrW(hWnd, -6);
  if ( !WindowLongPtrW
    || (dwProcessId = 0,
        GetWindowThreadProcessId(hWnd, &dwProcessId),
        v6 = OpenProcess(0x410u, 0, dwProcessId),
        (v7 = v6) == 0)
    || (ModuleBaseNameW = K32GetModuleBaseNameW(v6, WindowLongPtrW, lpBaseName, 0x104u),
        CloseHandle(v7),
        !ModuleBaseNameW) )
  {
    *lpBaseName = 0;
  }
}

```

## disassembly

```asm
0x1801b02c4  mov     [rsp+dwProcessId], r8d
0x1801b02c9  push    rbx
0x1801b02ca  push    rbp
0x1801b02cb  push    rsi
0x1801b02cc  push    rdi
0x1801b02cd  sub     rsp, 28h
0x1801b02d1  mov     rdi, rdx
0x1801b02d4  mov     rbx, rcx
0x1801b02d7  mov     edx, 0FFFFFFFAh; nIndex
0x1801b02dc  call    cs:__imp_GetWindowLongPtrW
0x1801b02e2  mov     rbp, rax
0x1801b02e5  test    rax, rax
0x1801b02e8  jz      short loc_1801B033E
0x1801b02ea  lea     rdx, [rsp+48h+dwProcessId]; lpdwProcessId
0x1801b02ef  mov     [rsp+48h+dwProcessId], 0
0x1801b02f7  mov     rcx, rbx; hWnd
0x1801b02fa  call    cs:__imp_GetWindowThreadProcessId
0x1801b0300  mov     r8d, [rsp+48h+dwProcessId]; dwProcessId
0x1801b0305  xor     edx, edx; bInheritHandle
0x1801b0307  mov     ecx, 410h; dwDesiredAccess
0x1801b030c  call    cs:__imp_OpenProcess
0x1801b0312  mov     rsi, rax
0x1801b0315  test    rax, rax
0x1801b0318  jz      short loc_1801B033E
0x1801b031a  mov     r9d, 104h; nSize
0x1801b0320  mov     r8, rdi; lpBaseName
0x1801b0323  mov     rdx, rbp; hModule
0x1801b0326  mov     rcx, rax; hProcess
0x1801b0329  call    cs:__imp_K32GetModuleBaseNameW
0x1801b032f  mov     rcx, rsi; hObject
0x1801b0332  mov     ebx, eax
0x1801b0334  call    cs:__imp_CloseHandle
0x1801b033a  test    ebx, ebx
0x1801b033c  jnz     short loc_1801B0343
0x1801b033e  xor     eax, eax
0x1801b0340  mov     [rdi], ax
0x1801b0343  add     rsp, 28h
0x1801b0347  pop     rdi
0x1801b0348  pop     rsi
0x1801b0349  pop     rbp
0x1801b034a  pop     rbx
0x1801b034b  retn
```
