# GetDirectorySizeFileCallback

- ea: `0x18003b890`
- end: `0x18003b991`
- name: `GetDirectorySizeFileCallback`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180039394`
- `0x18003b890`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003b91d`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003b91d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003b8fd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003b8fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b8a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b8a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b942`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b942`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b935`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b935`

## string_xrefs

- `0x18003b94b`: `Failed to create handle for %s. GLE = 0x%x`

## pseudocode

```c
__int64 __fastcall GetDirectorySizeFileCallback(__int64 a1, unsigned int *a2)
{
  unsigned int (__fastcall *v5)(LPCWSTR, _QWORD); // rax
  LPCWSTR *v6; // rbx
  HANDLE FileW; // rax
  void *v8; // rbp
  union _LARGE_INTEGER v9; // rdi
  LPCWSTR v10; // rbx
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-48h]
  union _LARGE_INTEGER FileSize; // [rsp+78h] [rbp+10h] BYREF

  if ( a2 )
  {
    v5 = (unsigned int (__fastcall *)(LPCWSTR, _QWORD))*((_QWORD *)a2 + 1);
    v6 = (LPCWSTR *)(a1 + 40);
    if ( !v5 || !v5(*v6, *((_QWORD *)a2 + 2)) )
    {
      FileW = CreateFileW(*v6, 0x80000000, 7u, 0, 3u, 0x8000000u, 0);
      v8 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        v10 = *v6;
        v9.QuadPart = 0;
        LODWORD(dwCreationDisposition) = GetLastError();
        LibLog(&g_WdsLibLog, 50331648, L"Failed to create handle for %s. GLE = 0x%x", v10, dwCreationDisposition);
      }
      else
      {
        FileSize.QuadPart = 0;
        if ( GetFileSizeEx(FileW, &FileSize) )
          v9 = FileSize;
        else
          v9 = *(union _LARGE_INTEGER *)(a1 + 32);
        CloseHandle(v8);
      }
      if ( *a2 )
        v9.QuadPart = *a2 + v9.QuadPart - 1 - ((unsigned __int64)*a2 + v9.QuadPart - 1) % *a2;
      *((_QWORD *)a2 + 3) += v9.QuadPart;
    }
    return 1;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18003b890  push    rbx
0x18003b892  push    rbp
0x18003b893  push    rsi
0x18003b894  push    rdi
0x18003b895  sub     rsp, 48h
0x18003b899  mov     rsi, rdx
0x18003b89c  mov     rdi, rcx
0x18003b89f  test    rdx, rdx
0x18003b8a2  jnz     short loc_18003B8B4
0x18003b8a4  lea     ecx, [rdx+57h]; dwErrCode
0x18003b8a7  call    cs:__imp_SetLastError
0x18003b8ad  xor     eax, eax
0x18003b8af  jmp     loc_18003B988
0x18003b8b4  mov     rax, [rdx+8]
0x18003b8b8  lea     rbx, [rcx+28h]
0x18003b8bc  test    rax, rax
0x18003b8bf  jz      short loc_18003B8D5
0x18003b8c1  mov     rdx, [rdx+10h]
0x18003b8c5  mov     rcx, [rbx]
0x18003b8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8cd  test    eax, eax
0x18003b8cf  jnz     loc_18003B983
0x18003b8d5  mov     rcx, [rbx]; lpFileName
0x18003b8d8  xor     r9d, r9d; lpSecurityAttributes
0x18003b8db  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18003b8e4  mov     edx, 80000000h; dwDesiredAccess
0x18003b8e9  mov     [rsp+68h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18003b8f1  mov     dword ptr [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18003b8f9  lea     r8d, [r9+7]; dwShareMode
0x18003b8fd  call    cs:__imp_CreateFileW
0x18003b903  mov     rbp, rax
0x18003b906  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003b90a  jz      short loc_18003B93D
0x18003b90c  lea     rdx, [rsp+68h+FileSize]; lpFileSize
0x18003b911  mov     qword ptr [rsp+68h+FileSize], 0
0x18003b91a  mov     rcx, rax; hFile
0x18003b91d  call    cs:__imp_GetFileSizeEx
0x18003b923  test    eax, eax
0x18003b925  jz      short loc_18003B92E
0x18003b927  mov     rdi, qword ptr [rsp+68h+FileSize]
0x18003b92c  jmp     short loc_18003B932
0x18003b92e  mov     rdi, [rdi+20h]
0x18003b932  mov     rcx, rbp; hObject
0x18003b935  call    cs:__imp_CloseHandle
0x18003b93b  jmp     short loc_18003B967
0x18003b93d  mov     rbx, [rbx]
0x18003b940  xor     edi, edi
0x18003b942  call    cs:__imp_GetLastError
0x18003b948  mov     r9, rbx
0x18003b94b  lea     r8, aFailedToCreate_1; "Failed to create handle for %s. GLE = 0"...
0x18003b952  lea     rcx, g_WdsLibLog
0x18003b959  mov     dword ptr [rsp+68h+dwCreationDisposition], eax
0x18003b95d  mov     edx, 3000000h
0x18003b962  call    LibLog
0x18003b967  cmp     dword ptr [rsi], 0
0x18003b96a  jz      short loc_18003B97F
0x18003b96c  mov     ecx, [rsi]
0x18003b96e  dec     rdi
0x18003b971  add     rdi, rcx
0x18003b974  xor     edx, edx
0x18003b976  mov     rax, rdi
0x18003b979  div     rcx
0x18003b97c  sub     rdi, rdx
0x18003b97f  add     [rsi+18h], rdi
0x18003b983  mov     eax, 1
0x18003b988  add     rsp, 48h
0x18003b98c  pop     rdi
0x18003b98d  pop     rsi
0x18003b98e  pop     rbp
0x18003b98f  pop     rbx
0x18003b990  retn
```
