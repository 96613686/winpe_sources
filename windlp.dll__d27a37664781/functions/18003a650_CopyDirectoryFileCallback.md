# CopyDirectoryFileCallback

- ea: `0x18003a650`
- end: `0x18003a7ee`
- name: `CopyDirectoryFileCallback`
- size: `414`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x180038b44`
- `0x180038c34`
- `0x180039394`
- `0x18003a650`
- `0x18003d694`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a7c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a7c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a7d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a7d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a7db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a7db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a779`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a779`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a66c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a66c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003a737`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003a737`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003a771`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003a771`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a74f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a74f`

## string_xrefs

- `0x18003a72e`: `user32.dll`
- `0x18003a679`: `CopyDirectoryFileCallback: The copy was canceled by the user.`
- `0x18003a78c`: `CopyDirectoryFileCallback: Unable to %s file from [%s] to [%s]; GLE = 0x%x`

## pseudocode

```c
__int64 __fastcall CopyDirectoryFileCallback(__int64 a1, __int64 a2)
{
  void *v4; // rcx
  unsigned int v5; // edi
  DWORD v6; // ecx
  unsigned int (__fastcall *v7)(_QWORD, _QWORD); // rax
  __int64 v8; // rax
  void *v9; // rbp
  DWORD LastError; // r14d
  HMODULE Library; // rax
  HMODULE v12; // rsi
  FARPROC ProcAddress; // rax
  DWORD v14; // eax
  const wchar_t *v15; // r9
  HANDLE ProcessHeap; // rax
  DWORD v18; // [rsp+30h] [rbp-38h]

  v4 = *(void **)(a2 + 24);
  if ( v4 && WaitForSingleObject(v4, 0) != 258 )
  {
    LibLog(&g_WdsLibLog, 0x4000000, L"CopyDirectoryFileCallback: The copy was canceled by the user.");
    v5 = 0;
    v6 = 1223;
LABEL_20:
    SetLastError(v6);
    return v5;
  }
  v7 = *(unsigned int (__fastcall **)(_QWORD, _QWORD))(a2 + 32);
  if ( v7 && v7(*(_QWORD *)(a1 + 40), *(_QWORD *)(a2 + 40)) )
  {
    return 1;
  }
  else
  {
    v5 = 0;
    v8 = BuildPath(*(STRSAFE_PCNZWCH *)(a2 + 8), *(STRSAFE_PCNZWCH *)(a1 + 48));
    v9 = (void *)v8;
    if ( v8 )
    {
      v5 = 1;
      if ( (unsigned int)CopyFileWithAttributesEx2(
                           *(_QWORD *)(a1 + 40),
                           v8,
                           *(unsigned int *)(a2 + 20),
                           *(_QWORD *)(a2 + 56),
                           *(_QWORD *)(a2 + 64)) == 1
        && (!*(_DWORD *)(a2 + 16) || DeleteFileEx2(*(_QWORD *)(a1 + 40), 0)) )
      {
        LastError = GetLastError();
        if ( *(_QWORD *)(a2 + 48) )
        {
          Library = LoadLibraryExW(L"user32.dll", 0, 0);
          v12 = Library;
          if ( Library )
          {
            ProcAddress = GetProcAddress(Library, "SendMessageW");
            if ( ProcAddress )
              ((void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))ProcAddress)(*(_QWORD *)(a2 + 48), 1029, 0, 0);
            FreeLibrary(v12);
          }
        }
      }
      else
      {
        v14 = GetLastError();
        v15 = L"move";
        LastError = v14;
        v18 = v14;
        if ( *(_DWORD *)(a2 + 16) != 1 )
          v15 = L"copy";
        LibLog(
          &g_WdsLibLog,
          0x2000000,
          L"CopyDirectoryFileCallback: Unable to %s file from [%s] to [%s]; GLE = 0x%x",
          v15,
          *(_QWORD *)(a1 + 40),
          v9,
          v18);
        v5 = 0;
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v9);
      v6 = LastError;
      goto LABEL_20;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18003a650  push    rbx
0x18003a652  push    rbp
0x18003a653  push    rsi
0x18003a654  push    rdi
0x18003a655  push    r14
0x18003a657  sub     rsp, 40h
0x18003a65b  mov     rsi, rcx
0x18003a65e  mov     rbx, rdx
0x18003a661  mov     rcx, [rdx+18h]; hHandle
0x18003a665  test    rcx, rcx
0x18003a668  jz      short loc_18003A69D
0x18003a66a  xor     edx, edx; dwMilliseconds
0x18003a66c  call    cs:__imp_WaitForSingleObject
0x18003a672  cmp     eax, 102h
0x18003a677  jz      short loc_18003A69D
0x18003a679  lea     r8, aCopydirectoryf_0; "CopyDirectoryFileCallback: The copy was"...
0x18003a680  mov     edx, 4000000h
0x18003a685  lea     rcx, g_WdsLibLog
0x18003a68c  call    LibLog
0x18003a691  xor     edi, edi
0x18003a693  mov     ecx, 4C7h
0x18003a698  jmp     loc_18003A7DB
0x18003a69d  mov     rax, [rbx+20h]
0x18003a6a1  test    rax, rax
0x18003a6a4  jz      short loc_18003A6C1
0x18003a6a6  mov     rdx, [rbx+28h]
0x18003a6aa  mov     rcx, [rsi+28h]
0x18003a6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a6b3  test    eax, eax
0x18003a6b5  jz      short loc_18003A6C1
0x18003a6b7  mov     edi, 1
0x18003a6bc  jmp     loc_18003A7E1
0x18003a6c1  mov     rdx, [rsi+30h]; STRSAFE_PCNZWCH
0x18003a6c5  xor     edi, edi
0x18003a6c7  mov     rcx, [rbx+8]; pszSrc
0x18003a6cb  call    BuildPath
0x18003a6d0  mov     rbp, rax
0x18003a6d3  test    rax, rax
0x18003a6d6  jz      loc_18003A7E1
0x18003a6dc  mov     rcx, [rbx+40h]
0x18003a6e0  mov     rdx, rax
0x18003a6e3  mov     r9, [rbx+38h]
0x18003a6e7  mov     r8d, [rbx+14h]
0x18003a6eb  mov     [rsp+68h+var_48], rcx
0x18003a6f0  mov     rcx, [rsi+28h]
0x18003a6f4  call    CopyFileWithAttributesEx2
0x18003a6f9  mov     edi, 1
0x18003a6fe  cmp     eax, edi
0x18003a700  jnz     short loc_18003A779
0x18003a702  cmp     dword ptr [rbx+10h], 0
0x18003a706  jz      short loc_18003A717
0x18003a708  mov     rcx, [rsi+28h]
0x18003a70c  xor     edx, edx
0x18003a70e  call    DeleteFileEx2
0x18003a713  cmp     eax, edi
0x18003a715  jnz     short loc_18003A779
0x18003a717  call    cs:__imp_GetLastError
0x18003a71d  cmp     qword ptr [rbx+30h], 0
0x18003a722  mov     r14d, eax
0x18003a725  jz      loc_18003A7C4
0x18003a72b  xor     r8d, r8d; dwFlags
0x18003a72e  lea     rcx, aUser32Dll; "user32.dll"
0x18003a735  xor     edx, edx; hFile
0x18003a737  call    cs:__imp_LoadLibraryExW
0x18003a73d  mov     rsi, rax
0x18003a740  test    rax, rax
0x18003a743  jz      short loc_18003A7C4
0x18003a745  lea     rdx, aSendmessagew; "SendMessageW"
0x18003a74c  mov     rcx, rax; hModule
0x18003a74f  call    cs:__imp_GetProcAddress
0x18003a755  test    rax, rax
0x18003a758  jz      short loc_18003A76E
0x18003a75a  mov     rcx, [rbx+30h]
0x18003a75e  xor     r9d, r9d
0x18003a761  xor     r8d, r8d
0x18003a764  mov     edx, 405h
0x18003a769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a76e  mov     rcx, rsi; hLibModule
0x18003a771  call    cs:__imp_FreeLibrary
0x18003a777  jmp     short loc_18003A7C4
0x18003a779  call    cs:__imp_GetLastError
0x18003a77f  cmp     [rbx+10h], edi
0x18003a782  lea     r9, aMove; "move"
0x18003a789  mov     r14d, eax
0x18003a78c  lea     r8, aCopydirectoryf; "CopyDirectoryFileCallback: Unable to %s"...
0x18003a793  lea     rax, aCopy; "copy"
0x18003a79a  mov     [rsp+68h+var_38], r14d
0x18003a79f  cmovnz  r9, rax
0x18003a7a3  mov     [rsp+68h+var_40], rbp
0x18003a7a8  mov     rax, [rsi+28h]
0x18003a7ac  lea     rcx, g_WdsLibLog
0x18003a7b3  mov     edx, 2000000h
0x18003a7b8  mov     [rsp+68h+var_48], rax
0x18003a7bd  call    LibLog
0x18003a7c2  xor     edi, edi
0x18003a7c4  call    cs:__imp_GetProcessHeap
0x18003a7ca  mov     r8, rbp; lpMem
0x18003a7cd  xor     edx, edx; dwFlags
0x18003a7cf  mov     rcx, rax; hHeap
0x18003a7d2  call    cs:__imp_HeapFree
0x18003a7d8  mov     ecx, r14d; dwErrCode
0x18003a7db  call    cs:__imp_SetLastError
0x18003a7e1  mov     eax, edi
0x18003a7e3  add     rsp, 40h
0x18003a7e7  pop     r14
0x18003a7e9  pop     rdi
0x18003a7ea  pop     rsi
0x18003a7eb  pop     rbp
0x18003a7ec  pop     rbx
0x18003a7ed  retn
```
