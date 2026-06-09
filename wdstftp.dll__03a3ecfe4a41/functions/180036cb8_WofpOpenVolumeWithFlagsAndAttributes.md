# WofpOpenVolumeWithFlagsAndAttributes

- ea: `0x180036cb8`
- end: `0x180036e22`
- name: `WofpOpenVolumeWithFlagsAndAttributes`
- size: `362`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path`

## callers

- `0x1800366b0`

## callees

- `0x180036cb8`

## import_xrefs

- `KERNEL32!GetVolumePathNameW` at `0x180036d19`
- `KERNEL32!GetVolumePathNameW` at `0x180036d19`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180036d64`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180036d64`
- `KERNEL32!HeapFree` at `0x180036dd3`
- `KERNEL32!HeapFree` at `0x180036df8`
- `KERNEL32!HeapFree` at `0x180036dd3`
- `KERNEL32!HeapFree` at `0x180036df8`
- `KERNEL32!HeapAlloc` at `0x180036cf5`
- `KERNEL32!HeapAlloc` at `0x180036d44`
- `KERNEL32!HeapAlloc` at `0x180036cf5`
- `KERNEL32!HeapAlloc` at `0x180036d44`
- `KERNEL32!CreateFileW` at `0x180036db0`
- `KERNEL32!CreateFileW` at `0x180036db0`
- `KERNEL32!GetProcessHeap` at `0x180036cde`
- `KERNEL32!GetProcessHeap` at `0x180036d2d`
- `KERNEL32!GetProcessHeap` at `0x180036dbf`
- `KERNEL32!GetProcessHeap` at `0x180036de4`
- `KERNEL32!GetProcessHeap` at `0x180036cde`
- `KERNEL32!GetProcessHeap` at `0x180036d2d`
- `KERNEL32!GetProcessHeap` at `0x180036dbf`
- `KERNEL32!GetProcessHeap` at `0x180036de4`

## pseudocode

```c
__int64 __fastcall WofpOpenVolumeWithFlagsAndAttributes(LPCWSTR lpszFileName)
{
  WCHAR *v2; // rbx
  __int64 FileW; // rdi
  HANDLE ProcessHeap; // rax
  WCHAR *v5; // rax
  WCHAR *v6; // rsi
  HANDLE v7; // rax
  WCHAR *v8; // rax
  __int64 v9; // rdi
  HANDLE v10; // rax
  HANDLE v11; // rax

  v2 = 0;
  FileW = -1;
  ProcessHeap = GetProcessHeap();
  v5 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x208u);
  v6 = v5;
  if ( v5 )
  {
    if ( GetVolumePathNameW(lpszFileName, v5, 0x104u) )
    {
      v7 = GetProcessHeap();
      v8 = (WCHAR *)HeapAlloc(v7, 0, 0x208u);
      v2 = v8;
      if ( v8 )
      {
        if ( GetVolumeNameForVolumeMountPointW(v6, v8, 0x104u) )
        {
          do
            ++FileW;
          while ( v2[FileW] );
          v9 = (unsigned int)(FileW - 1);
          if ( v2[v9] == 92 )
            v2[v9] = 0;
          FileW = (__int64)CreateFileW(v2, 0x80000000, 7u, 0, 3u, 0x80u, 0);
        }
      }
    }
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v6);
    if ( v2 )
    {
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v2);
    }
  }
  return FileW;
}

```

## disassembly

```asm
0x180036cb8  mov     rax, rsp
0x180036cbb  mov     [rax+8], rbx
0x180036cbf  mov     [rax+10h], rbp
0x180036cc3  mov     [rax+18h], rsi
0x180036cc7  mov     [rax+20h], rdi
0x180036ccb  push    r14
0x180036ccd  sub     rsp, 40h
0x180036cd1  xor     r14d, r14d
0x180036cd4  mov     rbp, rcx
0x180036cd7  mov     ebx, r14d
0x180036cda  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180036cde  call    cs:__imp_GetProcessHeap
0x180036ce5  nop     dword ptr [rax+rax+00h]
0x180036cea  xor     edx, edx; dwFlags
0x180036cec  mov     r8d, 208h; dwBytes
0x180036cf2  mov     rcx, rax; hHeap
0x180036cf5  call    cs:__imp_HeapAlloc
0x180036cfc  nop     dword ptr [rax+rax+00h]
0x180036d01  mov     rsi, rax
0x180036d04  test    rax, rax
0x180036d07  jz      loc_180036E04
0x180036d0d  mov     r8d, 104h; cchBufferLength
0x180036d13  mov     rdx, rax; lpszVolumePathName
0x180036d16  mov     rcx, rbp; lpszFileName
0x180036d19  call    cs:__imp_GetVolumePathNameW
0x180036d20  nop     dword ptr [rax+rax+00h]
0x180036d25  test    eax, eax
0x180036d27  jz      loc_180036DBF
0x180036d2d  call    cs:__imp_GetProcessHeap
0x180036d34  nop     dword ptr [rax+rax+00h]
0x180036d39  xor     edx, edx; dwFlags
0x180036d3b  mov     r8d, 208h; dwBytes
0x180036d41  mov     rcx, rax; hHeap
0x180036d44  call    cs:__imp_HeapAlloc
0x180036d4b  nop     dword ptr [rax+rax+00h]
0x180036d50  mov     rbx, rax
0x180036d53  test    rax, rax
0x180036d56  jz      short loc_180036DBF
0x180036d58  mov     r8d, 104h; cchBufferLength
0x180036d5e  mov     rdx, rax; lpszVolumeName
0x180036d61  mov     rcx, rsi; lpszVolumeMountPoint
0x180036d64  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180036d6b  nop     dword ptr [rax+rax+00h]
0x180036d70  test    eax, eax
0x180036d72  jz      short loc_180036DBF
0x180036d74  inc     rdi
0x180036d77  cmp     [rbx+rdi*2], r14w
0x180036d7c  jnz     short loc_180036D74
0x180036d7e  dec     edi
0x180036d80  cmp     word ptr [rbx+rdi*2], 5Ch ; '\'
0x180036d85  jnz     short loc_180036D8C
0x180036d87  mov     [rbx+rdi*2], r14w
0x180036d8c  xor     r9d, r9d; lpSecurityAttributes
0x180036d8f  mov     [rsp+48h+hTemplateFile], r14; hTemplateFile
0x180036d94  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180036d9c  mov     edx, 80000000h; dwDesiredAccess
0x180036da1  mov     rcx, rbx; lpFileName
0x180036da4  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180036dac  lea     r8d, [r9+7]; dwShareMode
0x180036db0  call    cs:__imp_CreateFileW
0x180036db7  nop     dword ptr [rax+rax+00h]
0x180036dbc  mov     rdi, rax
0x180036dbf  call    cs:__imp_GetProcessHeap
0x180036dc6  nop     dword ptr [rax+rax+00h]
0x180036dcb  mov     r8, rsi; lpMem
0x180036dce  xor     edx, edx; dwFlags
0x180036dd0  mov     rcx, rax; hHeap
0x180036dd3  call    cs:__imp_HeapFree
0x180036dda  nop     dword ptr [rax+rax+00h]
0x180036ddf  test    rbx, rbx
0x180036de2  jz      short loc_180036E04
0x180036de4  call    cs:__imp_GetProcessHeap
0x180036deb  nop     dword ptr [rax+rax+00h]
0x180036df0  mov     r8, rbx; lpMem
0x180036df3  xor     edx, edx; dwFlags
0x180036df5  mov     rcx, rax; hHeap
0x180036df8  call    cs:__imp_HeapFree
0x180036dff  nop     dword ptr [rax+rax+00h]
0x180036e04  mov     rbx, [rsp+48h+arg_0]
0x180036e09  mov     rax, rdi
0x180036e0c  mov     rdi, [rsp+48h+arg_18]
0x180036e11  mov     rbp, [rsp+48h+arg_8]
0x180036e16  mov     rsi, [rsp+48h+arg_10]
0x180036e1b  add     rsp, 40h
0x180036e1f  pop     r14
0x180036e21  retn
```
