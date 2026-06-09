# DeletePathDirectoryCallback

- ea: `0x18003a800`
- end: `0x18003aa90`
- name: `DeletePathDirectoryCallback`
- size: `656`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, reparse_path`

## callees

- `0x180038c34`
- `0x180039394`
- `0x180039a58`
- `0x18003a800`
- `0x18003b04c`
- `0x18003bae4`
- `0x18003bb64`
- `0x18003db20`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003a944`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003a944`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a9f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a9f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003aa06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003aa06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a828`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a86b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a8cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a998`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a9ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a9eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a828`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a86b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a8cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a998`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a9ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a9eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a971`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a98d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a971`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a98d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a97e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a97e`

## string_xrefs

- `0x18003a9c4`: `DeletePathDirectoryCallback: Spoofing detected deleting [%s] -> [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall DeletePathDirectoryCallback(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 (__fastcall *v6)(_QWORD, _QWORD); // rax
  unsigned int v7; // r15d
  DWORD v8; // ecx
  __int64 v9; // rcx
  DWORD v10; // edi
  BOOL v11; // esi
  int v12; // eax
  int v13; // eax
  __int64 v14; // rcx
  int v15; // edx
  BOOL v16; // eax
  const WCHAR *v17; // rcx
  int v18; // r13d
  DWORD LastError; // eax
  bool v20; // zf
  void *v21; // r13
  HANDLE ProcessHeap; // rax
  __int64 v23; // rcx
  int v24; // edx
  int v25; // eax
  LPVOID lpMem; // [rsp+40h] [rbp-20h] BYREF
  const WCHAR *v27; // [rsp+48h] [rbp-18h]
  HANDLE hObject; // [rsp+50h] [rbp-10h]
  DWORD dwErrCode; // [rsp+B0h] [rbp+50h] BYREF
  int v30; // [rsp+B8h] [rbp+58h] BYREF

  if ( !a3 )
  {
    SetLastError(0x57u);
    return 0;
  }
  v6 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(a3 + 16);
  v7 = 1;
  if ( v6 )
  {
    v7 = v6(*(_QWORD *)(a1 + 40), *(_QWORD *)(a3 + 24));
    if ( !v7 )
    {
      if ( GetLastError() )
        goto LABEL_47;
      v8 = 1223;
      goto LABEL_7;
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
        || (v13 = ShouldEnumerateReparsePoint(*(_QWORD *)(a1 + 40), &dwErrCode), v10 = dwErrCode, !v13)
        || !dwErrCode )
      {
        v14 = *(_QWORD *)(a1 + 40);
        if ( v14 )
        {
          v15 = *(_DWORD *)(a3 + 12) & 0x21;
          v16 = v15 ? DeleteFileEx2(v14, v15) : WdsRemoveDirectory();
          v11 = v16;
        }
        else
        {
          SetLastError(0x57u);
          v11 = 0;
        }
        if ( !v10 )
          goto LABEL_46;
      }
    }
  }
  if ( (*(_DWORD *)(a3 + 12) & 0x20) != 0 )
  {
    v17 = *(const WCHAR **)(a1 + 40);
    v18 = 0;
    v30 = 0;
    lpMem = 0;
    v27 = v17;
    if ( v17 && *v17 )
    {
      hObject = CreateFileW(v17, 0, 7u, 0, 3u, 0x2200000u, 0);
      if ( hObject == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        dwErrCode = LastError;
      }
      else
      {
        dwErrCode = 0;
        if ( !(unsigned int)VerifyPathRedirectionByHandle(hObject, v27, &v30, &lpMem) )
          dwErrCode = GetLastError();
        CloseHandle(hObject);
        LastError = dwErrCode;
        v18 = v30;
      }
      SetLastError(LastError);
      if ( !dwErrCode )
        goto LABEL_32;
    }
    else
    {
      SetLastError(0x57u);
    }
    v18 = 1;
LABEL_32:
    v20 = v18 == 0;
    v21 = lpMem;
    if ( v20 )
    {
      LibLog(
        &g_WdsLibLog,
        50331648,
        L"DeletePathDirectoryCallback: Spoofing detected deleting [%s] -> [%s]",
        *(_QWORD *)(a1 + 40),
        lpMem);
      v10 = 0;
      v7 = 0;
      SetLastError(0x2A9u);
      v11 = 0;
    }
    if ( v21 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v21);
    }
  }
  if ( v10 )
  {
    if ( (unsigned int)EnumeratePathEx(*(LPCWSTR *)(a1 + 40), *(_DWORD *)(a3 + 8)) == 1 )
    {
      v23 = *(_QWORD *)(a1 + 40);
      v7 = 1;
      if ( v23 )
      {
        v24 = *(_DWORD *)(a3 + 12) & 0x21;
        if ( v24 )
          v25 = DeleteFileEx2(v23, v24);
        else
          v25 = WdsRemoveDirectory();
        if ( v25 == 1 )
          return v7;
        goto LABEL_47;
      }
      v8 = 87;
LABEL_7:
      SetLastError(v8);
      goto LABEL_47;
    }
    v7 = 0;
LABEL_47:
    ++*(_DWORD *)(a3 + 4);
    if ( !*(_DWORD *)a3 )
      *(_DWORD *)a3 = GetLastError();
    return v7;
  }
LABEL_46:
  if ( !v11 )
    goto LABEL_47;
  return v7;
}

```

## disassembly

```asm
0x18003a800  mov     [rsp-38h+arg_8], rdx
0x18003a805  push    rbp
0x18003a806  push    rbx
0x18003a807  push    rsi
0x18003a808  push    rdi
0x18003a809  push    r13
0x18003a80b  push    r14
0x18003a80d  push    r15
0x18003a80f  mov     rbp, rsp
0x18003a812  sub     rsp, 60h
0x18003a816  mov     rbx, r8
0x18003a819  mov     r13, rdx
0x18003a81c  mov     r14, rcx
0x18003a81f  test    r8, r8
0x18003a822  jnz     short loc_18003A835
0x18003a824  lea     ecx, [r8+57h]; dwErrCode
0x18003a828  call    cs:__imp_SetLastError
0x18003a82e  xor     eax, eax
0x18003a830  jmp     loc_18003AA81
0x18003a835  mov     rax, [r8+10h]
0x18003a839  mov     r15d, 1
0x18003a83f  test    rax, rax
0x18003a842  jz      short loc_18003A876
0x18003a844  mov     rdx, [r8+18h]
0x18003a848  mov     rcx, [rcx+28h]
0x18003a84c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a851  mov     r15d, eax
0x18003a854  test    eax, eax
0x18003a856  jnz     short loc_18003A876
0x18003a858  call    cs:__imp_GetLastError
0x18003a85e  test    eax, eax
0x18003a860  jnz     loc_18003AA6E
0x18003a866  mov     ecx, 4C7h; dwErrCode
0x18003a86b  call    cs:__imp_SetLastError
0x18003a871  jmp     loc_18003AA6E
0x18003a876  mov     rcx, [r14+28h]
0x18003a87a  lea     rdx, [rbp+dwErrCode]
0x18003a87e  mov     [rbp+dwErrCode], 0
0x18003a885  mov     edi, 1
0x18003a88a  xor     esi, esi
0x18003a88c  call    ReparsePointExists
0x18003a891  test    eax, eax
0x18003a893  jz      short loc_18003A8F4
0x18003a895  cmp     [rbp+dwErrCode], esi
0x18003a898  jz      short loc_18003A8F4
0x18003a89a  mov     eax, [rbx+8]
0x18003a89d  xor     edi, edi
0x18003a89f  mov     [rbp+dwErrCode], edi
0x18003a8a2  test    al, 2
0x18003a8a4  jnz     short loc_18003A8BE
0x18003a8a6  mov     rcx, [r14+28h]
0x18003a8aa  lea     rdx, [rbp+dwErrCode]
0x18003a8ae  call    ShouldEnumerateReparsePoint
0x18003a8b3  mov     edi, [rbp+dwErrCode]
0x18003a8b6  test    eax, eax
0x18003a8b8  jz      short loc_18003A8BE
0x18003a8ba  test    edi, edi
0x18003a8bc  jnz     short loc_18003A8F4
0x18003a8be  mov     rcx, [r14+28h]
0x18003a8c2  test    rcx, rcx
0x18003a8c5  jnz     short loc_18003A8D6
0x18003a8c7  mov     ecx, 57h ; 'W'; dwErrCode
0x18003a8cc  call    cs:__imp_SetLastError
0x18003a8d2  xor     esi, esi
0x18003a8d4  jmp     short loc_18003A8EC
0x18003a8d6  mov     edx, [rbx+0Ch]
0x18003a8d9  and     edx, 21h
0x18003a8dc  jnz     short loc_18003A8E5
0x18003a8de  call    WdsRemoveDirectory
0x18003a8e3  jmp     short loc_18003A8EA
0x18003a8e5  call    DeleteFileEx2
0x18003a8ea  mov     esi, eax
0x18003a8ec  test    edi, edi
0x18003a8ee  jz      loc_18003AA6A
0x18003a8f4  mov     eax, [rbx+0Ch]
0x18003a8f7  test    al, 20h
0x18003a8f9  jz      loc_18003AA10
0x18003a8ff  mov     rcx, [r14+28h]; lpFileName
0x18003a903  xor     r13d, r13d
0x18003a906  mov     [rbp+arg_18], r13d
0x18003a90a  mov     [rbp+lpMem], r13
0x18003a90e  mov     [rbp+var_18], rcx
0x18003a912  test    rcx, rcx
0x18003a915  jz      loc_18003A9A6
0x18003a91b  xor     eax, eax
0x18003a91d  cmp     ax, [rcx]
0x18003a920  jz      loc_18003A9A6
0x18003a926  mov     [rsp+60h+hTemplateFile], rax; hTemplateFile
0x18003a92b  lea     r8d, [r13+7]; dwShareMode
0x18003a92f  mov     [rsp+60h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18003a937  xor     r9d, r9d; lpSecurityAttributes
0x18003a93a  xor     edx, edx; dwDesiredAccess
0x18003a93c  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x18003a944  call    cs:__imp_CreateFileW
0x18003a94a  mov     [rbp+hObject], rax
0x18003a94e  mov     rcx, rax
0x18003a951  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003a955  jz      short loc_18003A98D
0x18003a957  mov     rdx, [rbp+var_18]
0x18003a95b  lea     r9, [rbp+lpMem]
0x18003a95f  xor     eax, eax
0x18003a961  lea     r8, [rbp+arg_18]
0x18003a965  mov     [rbp+dwErrCode], eax
0x18003a968  call    VerifyPathRedirectionByHandle
0x18003a96d  test    eax, eax
0x18003a96f  jnz     short loc_18003A97A
0x18003a971  call    cs:__imp_GetLastError
0x18003a977  mov     [rbp+dwErrCode], eax
0x18003a97a  mov     rcx, [rbp+hObject]; hObject
0x18003a97e  call    cs:__imp_CloseHandle
0x18003a984  mov     eax, [rbp+dwErrCode]
0x18003a987  mov     r13d, [rbp+arg_18]
0x18003a98b  jmp     short loc_18003A996
0x18003a98d  call    cs:__imp_GetLastError
0x18003a993  mov     [rbp+dwErrCode], eax
0x18003a996  mov     ecx, eax; dwErrCode
0x18003a998  call    cs:__imp_SetLastError
0x18003a99e  cmp     [rbp+dwErrCode], 0
0x18003a9a2  jz      short loc_18003A9B7
0x18003a9a4  jmp     short loc_18003A9B1
0x18003a9a6  mov     ecx, 57h ; 'W'; dwErrCode
0x18003a9ab  call    cs:__imp_SetLastError
0x18003a9b1  mov     r13d, 1
0x18003a9b7  test    r13d, r13d
0x18003a9ba  mov     r13, [rbp+lpMem]
0x18003a9be  jnz     short loc_18003A9F3
0x18003a9c0  mov     r9, [r14+28h]
0x18003a9c4  lea     r8, aDeletepathdire; "DeletePathDirectoryCallback: Spoofing d"...
0x18003a9cb  mov     edx, 3000000h
0x18003a9d0  mov     qword ptr [rsp+60h+dwCreationDisposition], r13
0x18003a9d5  lea     rcx, g_WdsLibLog
0x18003a9dc  call    LibLog
0x18003a9e1  mov     ecx, 2A9h; dwErrCode
0x18003a9e6  xor     edi, edi
0x18003a9e8  xor     r15d, r15d
0x18003a9eb  call    cs:__imp_SetLastError
0x18003a9f1  xor     esi, esi
0x18003a9f3  test    r13, r13
0x18003a9f6  jz      short loc_18003AA0C
0x18003a9f8  call    cs:__imp_GetProcessHeap
0x18003a9fe  mov     r8, r13; lpMem
0x18003aa01  xor     edx, edx; dwFlags
0x18003aa03  mov     rcx, rax; hHeap
0x18003aa06  call    cs:__imp_HeapFree
0x18003aa0c  mov     r13, [rbp+arg_8]
0x18003aa10  test    edi, edi
0x18003aa12  jz      short loc_18003AA6A
0x18003aa14  mov     eax, [rbx+8]
0x18003aa17  lea     rdx, DeletePathDirectoryCallback
0x18003aa1e  mov     rcx, [r14+28h]; lpFileName
0x18003aa22  mov     r9, rbx
0x18003aa25  mov     r8, r13
0x18003aa28  mov     [rsp+60h+dwCreationDisposition], eax; int
0x18003aa2c  call    EnumeratePathEx
0x18003aa31  cmp     eax, 1
0x18003aa34  jnz     short loc_18003AA65
0x18003aa36  mov     rcx, [r14+28h]
0x18003aa3a  mov     r15d, eax
0x18003aa3d  test    rcx, rcx
0x18003aa40  jnz     short loc_18003AA4A
0x18003aa42  lea     ecx, [rax+56h]
0x18003aa45  jmp     loc_18003A86B
0x18003aa4a  mov     edx, [rbx+0Ch]
0x18003aa4d  and     edx, 21h
0x18003aa50  jnz     short loc_18003AA59
0x18003aa52  call    WdsRemoveDirectory
0x18003aa57  jmp     short loc_18003AA5E
0x18003aa59  call    DeleteFileEx2
0x18003aa5e  cmp     eax, r15d
0x18003aa61  jnz     short loc_18003AA6E
0x18003aa63  jmp     short loc_18003AA7E
0x18003aa65  xor     r15d, r15d
0x18003aa68  jmp     short loc_18003AA6E
0x18003aa6a  test    esi, esi
0x18003aa6c  jnz     short loc_18003AA7E
0x18003aa6e  inc     dword ptr [rbx+4]
0x18003aa71  cmp     dword ptr [rbx], 0
0x18003aa74  jnz     short loc_18003AA7E
0x18003aa76  call    cs:__imp_GetLastError
0x18003aa7c  mov     [rbx], eax
0x18003aa7e  mov     eax, r15d
0x18003aa81  add     rsp, 60h
0x18003aa85  pop     r15
0x18003aa87  pop     r14
0x18003aa89  pop     r13
0x18003aa8b  pop     rdi
0x18003aa8c  pop     rsi
0x18003aa8d  pop     rbx
0x18003aa8e  pop     rbp
0x18003aa8f  retn
```
