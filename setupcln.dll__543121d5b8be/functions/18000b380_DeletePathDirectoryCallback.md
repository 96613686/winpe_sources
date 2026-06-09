# DeletePathDirectoryCallback

- ea: `0x18000b380`
- end: `0x18000b5ef`
- name: `DeletePathDirectoryCallback`
- size: `623`
- prototype: `__int64 __fastcall(__int64, __int64 (__fastcall *)(DWORD *, __int64), __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callees

- `0x180008f64`
- `0x18000b348`
- `0x18000b380`
- `0x18000bb18`
- `0x18000c17c`
- `0x18000c1fc`
- `0x18000c580`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b3ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b3f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b509`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b51c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b558`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b3ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b3f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b509`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b51c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b566`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b566`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b574`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b574`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4eb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b4b1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b4b1`

## string_xrefs

- `0x18000b531`: `DeletePathDirectoryCallback: Spoofing detected deleting [%s] -> [%s]`

## pseudocode

```c
__int64 __fastcall DeletePathDirectoryCallback(__int64 a1, __int64 (__fastcall *a2)(DWORD *, __int64), __int64 a3)
{
  __int64 (__fastcall *v4)(DWORD *, __int64); // r12
  __int64 (__fastcall *v7)(_QWORD, _QWORD); // rax
  unsigned int v8; // r14d
  __int64 v9; // rcx
  DWORD v10; // edi
  int v11; // r15d
  int v12; // eax
  int v13; // eax
  const WCHAR *v14; // rcx
  BOOL v15; // r13d
  void *v16; // r12
  DWORD LastError; // eax
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-18h]
  HANDLE hObject; // [rsp+50h] [rbp-10h]
  DWORD dwErrCode; // [rsp+B0h] [rbp+50h] BYREF
  BOOL v24; // [rsp+B8h] [rbp+58h] BYREF

  v4 = a2;
  if ( !a3 )
  {
    SetLastError(0x57u);
    return 0;
  }
  v7 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(a3 + 16);
  v8 = 1;
  if ( v7 )
  {
    v8 = v7(*(_QWORD *)(a1 + 40), *(_QWORD *)(a3 + 24));
    if ( !v8 )
    {
      if ( !GetLastError() )
        SetLastError(0x4C7u);
      goto LABEL_36;
    }
  }
  v9 = *(_QWORD *)(a1 + 40);
  dwErrCode = 0;
  v10 = 1;
  v11 = 0;
  if ( (unsigned int)ReparsePointExists(v9, &dwErrCode) )
  {
    if ( dwErrCode )
    {
      v12 = *(_DWORD *)(a3 + 8);
      v10 = 0;
      dwErrCode = 0;
      if ( (v12 & 2) != 0
        || (v13 = ShouldEnumerateReparsePoint(*(const WCHAR **)(a1 + 40), &dwErrCode), v10 = dwErrCode, !v13)
        || !dwErrCode )
      {
        v11 = WdsRemoveDirectoryWithFlags(*(_QWORD *)(a1 + 40), *(_DWORD *)(a3 + 12));
        if ( !v10 )
          goto LABEL_35;
      }
    }
  }
  if ( (*(_DWORD *)(a3 + 12) & 0x20) != 0 )
  {
    v14 = *(const WCHAR **)(a1 + 40);
    v15 = 0;
    v16 = 0;
    v24 = 0;
    lpMem = 0;
    lpFileName = v14;
    if ( v14 && *v14 )
    {
      hObject = CreateFileW(v14, 0, 7u, 0, 3u, 0x2200000u, 0);
      if ( hObject == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        dwErrCode = LastError;
      }
      else
      {
        dwErrCode = 0;
        if ( !VerifyPathRedirectionByHandle((char *)hObject, (WCHAR *)lpFileName, &v24, (wchar_t **)&lpMem) )
          dwErrCode = GetLastError();
        CloseHandle(hObject);
        LastError = dwErrCode;
        v15 = v24;
        v16 = lpMem;
      }
      SetLastError(LastError);
      if ( !dwErrCode )
        goto LABEL_25;
    }
    else
    {
      SetLastError(0x57u);
    }
    v15 = 1;
LABEL_25:
    if ( !v15 )
    {
      LibLog(
        &g_WdsLibLog,
        50331648,
        L"DeletePathDirectoryCallback: Spoofing detected deleting [%s] -> [%s]",
        *(_QWORD *)(a1 + 40),
        v16);
      v10 = 0;
      v8 = 0;
      SetLastError(0x2A9u);
      v11 = 0;
    }
    if ( v16 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v16);
    }
    v4 = a2;
  }
  if ( v10 )
  {
    if ( (unsigned int)EnumeratePathEx(
                         *(LPCWSTR *)(a1 + 40),
                         (__int64 (__fastcall *)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64))DeletePathDirectoryCallback,
                         v4,
                         a3,
                         *(_DWORD *)(a3 + 8)) == 1 )
    {
      v8 = 1;
      if ( (unsigned int)WdsRemoveDirectoryWithFlags(*(_QWORD *)(a1 + 40), *(_DWORD *)(a3 + 12)) == 1 )
        return v8;
    }
    else
    {
      v8 = 0;
    }
LABEL_36:
    ++*(_DWORD *)(a3 + 4);
    if ( !*(_DWORD *)a3 )
      *(_DWORD *)a3 = GetLastError();
    return v8;
  }
LABEL_35:
  if ( !v11 )
    goto LABEL_36;
  return v8;
}

```

## disassembly

```asm
0x18000b380  mov     [rsp-38h+arg_0], rbx
0x18000b385  mov     [rsp-38h+arg_8], rdx
0x18000b38a  push    rbp
0x18000b38b  push    rsi
0x18000b38c  push    rdi
0x18000b38d  push    r12
0x18000b38f  push    r13
0x18000b391  push    r14
0x18000b393  push    r15
0x18000b395  mov     rbp, rsp
0x18000b398  sub     rsp, 60h
0x18000b39c  mov     rbx, r8
0x18000b39f  mov     r12, rdx
0x18000b3a2  mov     rsi, rcx
0x18000b3a5  test    r8, r8
0x18000b3a8  jnz     short loc_18000B3BB
0x18000b3aa  lea     ecx, [r8+57h]; dwErrCode
0x18000b3ae  call    cs:__imp_SetLastError
0x18000b3b4  xor     eax, eax
0x18000b3b6  jmp     loc_18000B5D7
0x18000b3bb  mov     rax, [r8+10h]
0x18000b3bf  mov     r14d, 1
0x18000b3c5  test    rax, rax
0x18000b3c8  jz      short loc_18000B3FC
0x18000b3ca  mov     rdx, [r8+18h]
0x18000b3ce  mov     rcx, [rcx+28h]
0x18000b3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3d7  mov     r14d, eax
0x18000b3da  test    eax, eax
0x18000b3dc  jnz     short loc_18000B3FC
0x18000b3de  call    cs:__imp_GetLastError
0x18000b3e4  test    eax, eax
0x18000b3e6  jnz     loc_18000B5C4
0x18000b3ec  mov     ecx, 4C7h; dwErrCode
0x18000b3f1  call    cs:__imp_SetLastError
0x18000b3f7  jmp     loc_18000B5C4
0x18000b3fc  mov     rcx, [rsi+28h]
0x18000b400  lea     rdx, [rbp+dwErrCode]
0x18000b404  mov     [rbp+dwErrCode], 0
0x18000b40b  mov     edi, 1
0x18000b410  xor     r15d, r15d
0x18000b413  call    ReparsePointExists
0x18000b418  test    eax, eax
0x18000b41a  jz      short loc_18000B45D
0x18000b41c  cmp     [rbp+dwErrCode], r15d
0x18000b420  jz      short loc_18000B45D
0x18000b422  mov     eax, [rbx+8]
0x18000b425  xor     edi, edi
0x18000b427  mov     [rbp+dwErrCode], edi
0x18000b42a  test    al, 2
0x18000b42c  jnz     short loc_18000B446
0x18000b42e  mov     rcx, [rsi+28h]
0x18000b432  lea     rdx, [rbp+dwErrCode]
0x18000b436  call    ShouldEnumerateReparsePoint
0x18000b43b  mov     edi, [rbp+dwErrCode]
0x18000b43e  test    eax, eax
0x18000b440  jz      short loc_18000B446
0x18000b442  test    edi, edi
0x18000b444  jnz     short loc_18000B45D
0x18000b446  mov     edx, [rbx+0Ch]
0x18000b449  mov     rcx, [rsi+28h]
0x18000b44d  call    WdsRemoveDirectoryWithFlags
0x18000b452  mov     r15d, eax
0x18000b455  test    edi, edi
0x18000b457  jz      loc_18000B5BF
0x18000b45d  mov     ecx, [rbx+0Ch]
0x18000b460  test    cl, 20h
0x18000b463  jz      loc_18000B57E
0x18000b469  mov     rcx, [rsi+28h]; lpFileName
0x18000b46d  xor     r13d, r13d
0x18000b470  xor     r12d, r12d
0x18000b473  mov     [rbp+arg_18], r13d
0x18000b477  mov     [rbp+lpMem], r12
0x18000b47b  mov     [rbp+lpFileName], rcx
0x18000b47f  test    rcx, rcx
0x18000b482  jz      loc_18000B517
0x18000b488  xor     eax, eax
0x18000b48a  cmp     ax, [rcx]
0x18000b48d  jz      loc_18000B517
0x18000b493  mov     [rsp+60h+hTemplateFile], rax; hTemplateFile
0x18000b498  lea     r8d, [r13+7]; dwShareMode
0x18000b49c  mov     [rsp+60h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18000b4a4  xor     r9d, r9d; lpSecurityAttributes
0x18000b4a7  xor     edx, edx; dwDesiredAccess
0x18000b4a9  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x18000b4b1  call    cs:__imp_CreateFileW
0x18000b4b7  mov     [rbp+hObject], rax
0x18000b4bb  mov     rcx, rax; hFile
0x18000b4be  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b4c2  jz      short loc_18000B4FE
0x18000b4c4  mov     rdx, [rbp+lpFileName]; lpFileName
0x18000b4c8  lea     r9, [rbp+lpMem]
0x18000b4cc  xor     eax, eax
0x18000b4ce  lea     r8, [rbp+arg_18]
0x18000b4d2  mov     [rbp+dwErrCode], eax
0x18000b4d5  call    VerifyPathRedirectionByHandle
0x18000b4da  test    eax, eax
0x18000b4dc  jnz     short loc_18000B4E7
0x18000b4de  call    cs:__imp_GetLastError
0x18000b4e4  mov     [rbp+dwErrCode], eax
0x18000b4e7  mov     rcx, [rbp+hObject]; hObject
0x18000b4eb  call    cs:__imp_CloseHandle
0x18000b4f1  mov     eax, [rbp+dwErrCode]
0x18000b4f4  mov     r13d, [rbp+arg_18]
0x18000b4f8  mov     r12, [rbp+lpMem]
0x18000b4fc  jmp     short loc_18000B507
0x18000b4fe  call    cs:__imp_GetLastError
0x18000b504  mov     [rbp+dwErrCode], eax
0x18000b507  mov     ecx, eax; dwErrCode
0x18000b509  call    cs:__imp_SetLastError
0x18000b50f  cmp     [rbp+dwErrCode], 0
0x18000b513  jz      short loc_18000B528
0x18000b515  jmp     short loc_18000B522
0x18000b517  mov     ecx, 57h ; 'W'; dwErrCode
0x18000b51c  call    cs:__imp_SetLastError
0x18000b522  mov     r13d, 1
0x18000b528  test    r13d, r13d
0x18000b52b  jnz     short loc_18000B561
0x18000b52d  mov     r9, [rsi+28h]
0x18000b531  lea     r8, aDeletepathdire; "DeletePathDirectoryCallback: Spoofing d"...
0x18000b538  mov     edx, 3000000h
0x18000b53d  mov     qword ptr [rsp+60h+dwCreationDisposition], r12
0x18000b542  lea     rcx, g_WdsLibLog
0x18000b549  call    LibLog
0x18000b54e  mov     ecx, 2A9h; dwErrCode
0x18000b553  xor     edi, edi
0x18000b555  xor     r14d, r14d
0x18000b558  call    cs:__imp_SetLastError
0x18000b55e  xor     r15d, r15d
0x18000b561  test    r12, r12
0x18000b564  jz      short loc_18000B57A
0x18000b566  call    cs:__imp_GetProcessHeap
0x18000b56c  mov     r8, r12; lpMem
0x18000b56f  xor     edx, edx; dwFlags
0x18000b571  mov     rcx, rax; hHeap
0x18000b574  call    cs:__imp_HeapFree
0x18000b57a  mov     r12, [rbp+arg_8]
0x18000b57e  test    edi, edi
0x18000b580  jz      short loc_18000B5BF
0x18000b582  mov     eax, [rbx+8]
0x18000b585  lea     rdx, DeletePathDirectoryCallback
0x18000b58c  mov     rcx, [rsi+28h]; lpFileName
0x18000b590  mov     r9, rbx
0x18000b593  mov     r8, r12
0x18000b596  mov     [rsp+60h+dwCreationDisposition], eax; int
0x18000b59a  call    EnumeratePathEx
0x18000b59f  cmp     eax, 1
0x18000b5a2  jnz     short loc_18000B5BA
0x18000b5a4  mov     edx, [rbx+0Ch]
0x18000b5a7  mov     r14d, eax
0x18000b5aa  mov     rcx, [rsi+28h]
0x18000b5ae  call    WdsRemoveDirectoryWithFlags
0x18000b5b3  cmp     eax, r14d
0x18000b5b6  jnz     short loc_18000B5C4
0x18000b5b8  jmp     short loc_18000B5D4
0x18000b5ba  xor     r14d, r14d
0x18000b5bd  jmp     short loc_18000B5C4
0x18000b5bf  test    r15d, r15d
0x18000b5c2  jnz     short loc_18000B5D4
0x18000b5c4  inc     dword ptr [rbx+4]
0x18000b5c7  cmp     dword ptr [rbx], 0
0x18000b5ca  jnz     short loc_18000B5D4
0x18000b5cc  call    cs:__imp_GetLastError
0x18000b5d2  mov     [rbx], eax
0x18000b5d4  mov     eax, r14d
0x18000b5d7  mov     rbx, [rsp+60h+arg_0]
0x18000b5df  add     rsp, 60h
0x18000b5e3  pop     r15
0x18000b5e5  pop     r14
0x18000b5e7  pop     r13
0x18000b5e9  pop     r12
0x18000b5eb  pop     rdi
0x18000b5ec  pop     rsi
0x18000b5ed  pop     rbp
0x18000b5ee  retn
```
