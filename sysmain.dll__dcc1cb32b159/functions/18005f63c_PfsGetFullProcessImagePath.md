# PfsGetFullProcessImagePath

- ea: `0x18005f63c`
- end: `0x18005f701`
- name: `PfsGetFullProcessImagePath`
- size: `197`
- prototype: `__int64 __fastcall(DWORD dwProcessId, LPWSTR lpExeName)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18003b650`

## callees

- `0x18005ae4c`
- `0x18005f63c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f67c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f6a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f67c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f6a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f6e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f6e9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005f66e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005f66e`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18005f69e`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18005f69e`

## pseudocode

```c
__int64 __fastcall PfsGetFullProcessImagePath(DWORD dwProcessId, LPWSTR lpExeName, __int64 a3, wchar_t *a4)
{
  HANDLE v6; // rax
  void *v7; // rdi
  DWORD ProcessCMDLine; // ebx
  DWORD dwSize; // [rsp+50h] [rbp+18h] BYREF

  dwSize = 0;
  v6 = OpenProcess(0x1000u, 0, dwProcessId);
  v7 = v6;
  if ( v6 )
  {
    dwSize = 260;
    if ( QueryFullProcessImageNameW(v6, 1u, lpExeName, &dwSize) )
    {
      if ( dwSize )
      {
        lpExeName[259] = 0;
        if ( !a4 || (ProcessCMDLine = PfsExtractProcessCMDLineEx(v7, a4)) == 0 )
          ProcessCMDLine = 0;
      }
      else
      {
        ProcessCMDLine = 123;
      }
    }
    else
    {
      ProcessCMDLine = GetLastError();
    }
    CloseHandle(v7);
  }
  else
  {
    return GetLastError();
  }
  return ProcessCMDLine;
}

```

## disassembly

```asm
0x18005f63c  mov     rax, rsp
0x18005f63f  mov     [rax+8], rbx
0x18005f643  mov     [rax+10h], rsi
0x18005f647  mov     [rax+18h], r8d
0x18005f64b  push    rdi
0x18005f64c  sub     rsp, 30h
0x18005f650  mov     rsi, rdx
0x18005f653  mov     dword ptr [rax-18h], 208h
0x18005f65a  mov     r8d, ecx; dwProcessId
0x18005f65d  mov     dword ptr [rax+18h], 0
0x18005f664  xor     edx, edx; bInheritHandle
0x18005f666  mov     ecx, 1000h; dwDesiredAccess
0x18005f66b  mov     rbx, r9
0x18005f66e  call    cs:__imp_OpenProcess
0x18005f674  mov     rdi, rax
0x18005f677  test    rax, rax
0x18005f67a  jnz     short loc_18005F686
0x18005f67c  call    cs:__imp_GetLastError
0x18005f682  mov     ebx, eax
0x18005f684  jmp     short loc_18005F6EF
0x18005f686  lea     r9, [rsp+38h+dwSize]; lpdwSize
0x18005f68b  mov     [rsp+38h+dwSize], 104h
0x18005f693  mov     r8, rsi; lpExeName
0x18005f696  mov     edx, 1; dwFlags
0x18005f69b  mov     rcx, rdi; hProcess
0x18005f69e  call    cs:__imp_QueryFullProcessImageNameW
0x18005f6a4  test    eax, eax
0x18005f6a6  jnz     short loc_18005F6B2
0x18005f6a8  call    cs:__imp_GetLastError
0x18005f6ae  mov     ebx, eax
0x18005f6b0  jmp     short loc_18005F6E6
0x18005f6b2  cmp     [rsp+38h+dwSize], 0
0x18005f6b7  jnz     short loc_18005F6C0
0x18005f6b9  mov     ebx, 7Bh ; '{'
0x18005f6be  jmp     short loc_18005F6E6
0x18005f6c0  xor     eax, eax
0x18005f6c2  mov     [rsi+206h], ax
0x18005f6c9  test    rbx, rbx
0x18005f6cc  jz      short loc_18005F6E4
0x18005f6ce  lea     r8, [rsp+38h+var_18]
0x18005f6d3  mov     rdx, rbx; pszDest
0x18005f6d6  mov     rcx, rdi; ProcessHandle
0x18005f6d9  call    PfsExtractProcessCMDLineEx
0x18005f6de  mov     ebx, eax
0x18005f6e0  test    eax, eax
0x18005f6e2  jnz     short loc_18005F6E6
0x18005f6e4  xor     ebx, ebx
0x18005f6e6  mov     rcx, rdi; hObject
0x18005f6e9  call    cs:__imp_CloseHandle
0x18005f6ef  mov     rsi, [rsp+38h+arg_8]
0x18005f6f4  mov     eax, ebx
0x18005f6f6  mov     rbx, [rsp+38h+arg_0]
0x18005f6fb  add     rsp, 30h
0x18005f6ff  pop     rdi
0x18005f700  retn
```
