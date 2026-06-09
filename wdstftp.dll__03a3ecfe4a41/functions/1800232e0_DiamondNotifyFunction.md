# DiamondNotifyFunction

- ea: `0x1800232e0`
- end: `0x1800235fb`
- name: `DiamondNotifyFunction`
- size: `795`
- prototype: `INT_PTR __cdecl(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180022e24`
- `0x1800232e0`
- `0x180060e5a`
- `0x180060e70`

## import_xrefs

- `KERNEL32!LocalFileTimeToFileTime` at `0x1800233e1`
- `KERNEL32!LocalFileTimeToFileTime` at `0x1800234de`
- `KERNEL32!LocalFileTimeToFileTime` at `0x1800233e1`
- `KERNEL32!LocalFileTimeToFileTime` at `0x1800234de`
- `KERNEL32!DosDateTimeToFileTime` at `0x1800233c5`
- `KERNEL32!DosDateTimeToFileTime` at `0x1800234c6`
- `KERNEL32!DosDateTimeToFileTime` at `0x1800233c5`
- `KERNEL32!DosDateTimeToFileTime` at `0x1800234c6`
- `KERNEL32!SetFileTime` at `0x180023402`
- `KERNEL32!SetFileTime` at `0x180023402`
- `KERNEL32!HeapFree` at `0x18002335b`
- `KERNEL32!HeapFree` at `0x18002338e`
- `KERNEL32!HeapFree` at `0x18002335b`
- `KERNEL32!HeapFree` at `0x18002338e`
- `KERNEL32!GetLastError` at `0x180023461`
- `KERNEL32!GetLastError` at `0x1800234a2`
- `KERNEL32!GetLastError` at `0x180023557`
- `KERNEL32!GetLastError` at `0x1800235c3`
- `KERNEL32!GetLastError` at `0x180023461`
- `KERNEL32!GetLastError` at `0x1800234a2`
- `KERNEL32!GetLastError` at `0x180023557`
- `KERNEL32!GetLastError` at `0x1800235c3`
- `KERNEL32!CloseHandle` at `0x18002341a`
- `KERNEL32!CloseHandle` at `0x18002341a`
- `KERNEL32!CreateFileW` at `0x1800235ae`
- `KERNEL32!CreateFileW` at `0x1800235ae`
- `KERNEL32!GetProcessHeap` at `0x180023346`
- `KERNEL32!GetProcessHeap` at `0x18002337a`
- `KERNEL32!GetProcessHeap` at `0x180023346`
- `KERNEL32!GetProcessHeap` at `0x18002337a`

## pseudocode

```c
INT_PTR __fastcall DiamondNotifyFunction(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)
{
  char *pv; // rdi
  WCHAR *v5; // r14
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  __int64 v9; // rbx
  HANDLE ProcessHeap; // rax
  BOOL v11; // eax
  void *v12; // rcx
  HANDLE v13; // rax
  int v15; // eax
  DWORD LastError; // eax
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  DWORD v21; // eax
  HANDLE FileW; // rax
  WCHAR **v23; // rdi
  LPVOID lpMem; // [rsp+40h] [rbp-20h] BYREF
  int cb; // [rsp+48h] [rbp-18h]
  struct _FILETIME v26; // [rsp+4Ch] [rbp-14h] BYREF
  int v27; // [rsp+54h] [rbp-Ch]
  LPCWSTR lpFileName; // [rsp+58h] [rbp-8h]
  struct _FILETIME FileTime; // [rsp+98h] [rbp+38h] BYREF
  FILETIME LastWriteTime; // [rsp+A0h] [rbp+40h] BYREF

  memset_0(&lpMem, 0, 0x20u);
  pv = (char *)pfdin->pv;
  FileTime = 0;
  v5 = 0;
  LastWriteTime = 0;
  if ( fdint == fdintCABINET_INFO )
    goto LABEL_6;
  v6 = fdint - 1;
  if ( !v6 )
  {
LABEL_46:
    *((_DWORD *)pv + 8) = 50;
    goto LABEL_27;
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      if ( v8 != 1 )
      {
LABEL_6:
        v9 = 0;
        goto LABEL_7;
      }
      goto LABEL_46;
    }
    v5 = (WCHAR *)*((_QWORD *)pv + 1);
    *((_QWORD *)pv + 1) = 0;
    if ( DosDateTimeToFileTime(pfdin->date, pfdin->time, &FileTime)
      && LocalFileTimeToFileTime(&FileTime, &LastWriteTime)
      && SetFileTime((HANDLE)pfdin->hf, 0, 0, &LastWriteTime)
      && CloseHandle((HANDLE)pfdin->hf) )
    {
      v15 = (*((__int64 (__fastcall **)(__int64, WCHAR *, _QWORD, _QWORD))pv + 2))(1, v5, 0, *((_QWORD *)pv + 3));
      switch ( v15 )
      {
        case 2:
          goto LABEL_6;
        case 3:
          *((_DWORD *)pv + 8) = 1223;
          goto LABEL_6;
        case 4:
          LastError = GetLastError();
          *((_DWORD *)pv + 8) = LastError;
          if ( !LastError )
            *((_DWORD *)pv + 8) = 995;
          goto LABEL_6;
      }
      v9 = 1;
      goto LABEL_7;
    }
LABEL_26:
    *((_DWORD *)pv + 8) = GetLastError();
LABEL_27:
    v9 = -1;
    goto LABEL_7;
  }
  lpMem = (LPVOID)WimStrUnicode(pfdin->psz1);
  if ( !lpMem
    || !DosDateTimeToFileTime(pfdin->date, pfdin->time, &FileTime)
    || !LocalFileTimeToFileTime(&FileTime, &v26) )
  {
    goto LABEL_26;
  }
  cb = pfdin->cb;
  if ( pfdin->attribs )
    v27 = pfdin->attribs & 0x37;
  else
    v27 = 128;
  v17 = (*((__int64 (__fastcall **)(_QWORD, LPVOID *, _QWORD, _QWORD))pv + 2))(
          0,
          &lpMem,
          *(_QWORD *)pv,
          *((_QWORD *)pv + 3));
  if ( v17 )
  {
    v18 = v17 - 1;
    if ( !v18 )
      goto LABEL_6;
    v19 = v18 - 1;
    if ( !v19 )
      goto LABEL_27;
    v20 = v19 - 1;
    if ( v20 )
    {
      if ( v20 == 1 )
      {
        v21 = GetLastError();
        *((_DWORD *)pv + 8) = v21;
        if ( !v21 )
          *((_DWORD *)pv + 8) = 995;
        goto LABEL_27;
      }
      v9 = -1;
      *((_DWORD *)pv + 8) = 1;
    }
    else
    {
      v9 = -1;
      *((_DWORD *)pv + 8) = 1223;
    }
  }
  else
  {
    v5 = (WCHAR *)lpFileName;
    FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 2u, 0x80u, 0);
    v9 = -1;
    if ( FileW == (HANDLE)-1LL )
    {
      *((_DWORD *)pv + 8) = GetLastError();
    }
    else
    {
      v9 = (__int64)FileW;
      v23 = (WCHAR **)(pv + 8);
      if ( v23 )
      {
        *v23 = v5;
        v5 = 0;
      }
    }
  }
LABEL_7:
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    v11 = HeapFree(ProcessHeap, 0, lpMem);
    v12 = lpMem;
    if ( v11 )
      v12 = 0;
    lpMem = v12;
  }
  if ( v5 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v5);
  }
  return v9;
}

```

## disassembly

```asm
0x1800232e0  mov     [rsp-28h+arg_0], rbx
0x1800232e5  push    rbp
0x1800232e6  push    rsi
0x1800232e7  push    rdi
0x1800232e8  push    r14
0x1800232ea  push    r15
0x1800232ec  mov     rbp, rsp
0x1800232ef  sub     rsp, 60h
0x1800232f3  mov     rsi, rdx
0x1800232f6  mov     ebx, ecx
0x1800232f8  xor     edx, edx; Val
0x1800232fa  lea     rcx, [rbp+lpMem]; void *
0x1800232fe  lea     r8d, [rdx+20h]; Size
0x180023302  call    memset_0
0x180023307  mov     rdi, [rsi+20h]
0x18002330b  xor     r15d, r15d
0x18002330e  mov     qword ptr [rbp+FileTime.dwLowDateTime], r15
0x180023312  mov     r14d, r15d
0x180023315  mov     qword ptr [rbp+LastWriteTime.dwLowDateTime], r15
0x180023319  test    ebx, ebx
0x18002331b  jz      short loc_18002333D
0x18002331d  sub     ebx, 1
0x180023320  jz      loc_1800235EF
0x180023326  sub     ebx, 1
0x180023329  jz      loc_180023490
0x18002332f  sub     ebx, 1
0x180023332  jz      short loc_1800233B1
0x180023334  sub     ebx, 1
0x180023337  jz      loc_1800235EF
0x18002333d  mov     rbx, r15
0x180023340  cmp     [rbp+lpMem], r15
0x180023344  jz      short loc_180023375
0x180023346  call    cs:__imp_GetProcessHeap
0x18002334d  nop     dword ptr [rax+rax+00h]
0x180023352  mov     r8, [rbp+lpMem]; lpMem
0x180023356  xor     edx, edx; dwFlags
0x180023358  mov     rcx, rax; hHeap
0x18002335b  call    cs:__imp_HeapFree
0x180023362  nop     dword ptr [rax+rax+00h]
0x180023367  mov     rcx, [rbp+lpMem]
0x18002336b  test    eax, eax
0x18002336d  cmovnz  rcx, r15
0x180023371  mov     [rbp+lpMem], rcx
0x180023375  test    r14, r14
0x180023378  jz      short loc_18002339A
0x18002337a  call    cs:__imp_GetProcessHeap
0x180023381  nop     dword ptr [rax+rax+00h]
0x180023386  mov     r8, r14; lpMem
0x180023389  xor     edx, edx; dwFlags
0x18002338b  mov     rcx, rax; hHeap
0x18002338e  call    cs:__imp_HeapFree
0x180023395  nop     dword ptr [rax+rax+00h]
0x18002339a  mov     rax, rbx
0x18002339d  mov     rbx, [rsp+60h+arg_0]
0x1800233a5  add     rsp, 60h
0x1800233a9  pop     r15
0x1800233ab  pop     r14
0x1800233ad  pop     rdi
0x1800233ae  pop     rsi
0x1800233af  pop     rbp
0x1800233b0  retn
0x1800233b1  mov     r14, [rdi+8]
0x1800233b5  lea     r8, [rbp+FileTime]; lpFileTime
0x1800233b9  mov     [rdi+8], r15
0x1800233bd  movzx   edx, word ptr [rsi+32h]; wFatTime
0x1800233c1  movzx   ecx, word ptr [rsi+30h]; wFatDate
0x1800233c5  call    cs:__imp_DosDateTimeToFileTime
0x1800233cc  nop     dword ptr [rax+rax+00h]
0x1800233d1  test    eax, eax
0x1800233d3  jz      loc_1800234A2
0x1800233d9  lea     rdx, [rbp+LastWriteTime]; lpFileTime
0x1800233dd  lea     rcx, [rbp+FileTime]; lpLocalFileTime
0x1800233e1  call    cs:__imp_LocalFileTimeToFileTime
0x1800233e8  nop     dword ptr [rax+rax+00h]
0x1800233ed  test    eax, eax
0x1800233ef  jz      loc_1800234A2
0x1800233f5  mov     rcx, [rsi+28h]; hFile
0x1800233f9  lea     r9, [rbp+LastWriteTime]; lpLastWriteTime
0x1800233fd  xor     r8d, r8d; lpLastAccessTime
0x180023400  xor     edx, edx; lpCreationTime
0x180023402  call    cs:__imp_SetFileTime
0x180023409  nop     dword ptr [rax+rax+00h]
0x18002340e  test    eax, eax
0x180023410  jz      loc_1800234A2
0x180023416  mov     rcx, [rsi+28h]; hObject
0x18002341a  call    cs:__imp_CloseHandle
0x180023421  nop     dword ptr [rax+rax+00h]
0x180023426  test    eax, eax
0x180023428  jz      short loc_1800234A2
0x18002342a  mov     r9, [rdi+18h]
0x18002342e  xor     r8d, r8d
0x180023431  mov     rax, [rdi+10h]
0x180023435  mov     rdx, r14
0x180023438  lea     ecx, [r8+1]
0x18002343c  call    cs:__guard_dispatch_icall_fptr
0x180023442  mov     ecx, eax
0x180023444  sub     ecx, 2
0x180023447  jz      loc_18002333D
0x18002344d  sub     ecx, 1
0x180023450  jz      short loc_180023484
0x180023452  cmp     ecx, 1
0x180023455  jz      short loc_180023461
0x180023457  mov     ebx, 1
0x18002345c  jmp     loc_180023340
0x180023461  call    cs:__imp_GetLastError
0x180023468  nop     dword ptr [rax+rax+00h]
0x18002346d  mov     [rdi+20h], eax
0x180023470  test    eax, eax
0x180023472  jnz     loc_18002333D
0x180023478  mov     dword ptr [rdi+20h], 3E3h
0x18002347f  jmp     loc_18002333D
0x180023484  mov     dword ptr [rdi+20h], 4C7h
0x18002348b  jmp     loc_18002333D
0x180023490  mov     rcx, [rsi+8]; lpMultiByteStr
0x180023494  call    WimStrUnicode
0x180023499  mov     [rbp+lpMem], rax
0x18002349d  test    rax, rax
0x1800234a0  jnz     short loc_1800234BA
0x1800234a2  call    cs:__imp_GetLastError
0x1800234a9  nop     dword ptr [rax+rax+00h]
0x1800234ae  mov     [rdi+20h], eax
0x1800234b1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800234b5  jmp     loc_180023340
0x1800234ba  movzx   edx, word ptr [rsi+32h]; wFatTime
0x1800234be  lea     r8, [rbp+FileTime]; lpFileTime
0x1800234c2  movzx   ecx, word ptr [rsi+30h]; wFatDate
0x1800234c6  call    cs:__imp_DosDateTimeToFileTime
0x1800234cd  nop     dword ptr [rax+rax+00h]
0x1800234d2  test    eax, eax
0x1800234d4  jz      short loc_1800234A2
0x1800234d6  lea     rdx, [rbp+var_14]; lpFileTime
0x1800234da  lea     rcx, [rbp+FileTime]; lpLocalFileTime
0x1800234de  call    cs:__imp_LocalFileTimeToFileTime
0x1800234e5  nop     dword ptr [rax+rax+00h]
0x1800234ea  test    eax, eax
0x1800234ec  jz      short loc_1800234A2
0x1800234ee  mov     ebx, 80h
0x1800234f3  mov     eax, [rsi]
0x1800234f5  mov     [rbp+var_18], eax
0x1800234f8  cmp     [rsi+34h], r15w
0x1800234fd  jnz     short loc_180023504
0x1800234ff  mov     [rbp+var_C], ebx
0x180023502  jmp     short loc_18002350E
0x180023504  movzx   eax, word ptr [rsi+34h]
0x180023508  and     eax, 37h
0x18002350b  mov     [rbp+var_C], eax
0x18002350e  mov     r9, [rdi+18h]
0x180023512  lea     rdx, [rbp+lpMem]
0x180023516  mov     r8, [rdi]
0x180023519  xor     ecx, ecx
0x18002351b  mov     rax, [rdi+10h]
0x18002351f  call    cs:__guard_dispatch_icall_fptr
0x180023525  mov     ecx, eax
0x180023527  test    eax, eax
0x180023529  jz      short loc_18002358A
0x18002352b  sub     ecx, 1
0x18002352e  jz      loc_18002333D
0x180023534  sub     ecx, 1
0x180023537  jz      loc_1800234B1
0x18002353d  sub     ecx, 1
0x180023540  jz      short loc_18002357A
0x180023542  cmp     ecx, 1
0x180023545  jz      short loc_180023557
0x180023547  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002354b  mov     dword ptr [rdi+20h], 1
0x180023552  jmp     loc_180023340
0x180023557  call    cs:__imp_GetLastError
0x18002355e  nop     dword ptr [rax+rax+00h]
0x180023563  mov     [rdi+20h], eax
0x180023566  test    eax, eax
0x180023568  jnz     loc_1800234B1
0x18002356e  mov     dword ptr [rdi+20h], 3E3h
0x180023575  jmp     loc_1800234B1
0x18002357a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002357e  mov     dword ptr [rdi+20h], 4C7h
0x180023585  jmp     loc_180023340
0x18002358a  mov     r14, [rbp+lpFileName]
0x18002358e  xor     r9d, r9d; lpSecurityAttributes
0x180023591  mov     [rsp+60h+hTemplateFile], r15; hTemplateFile
0x180023596  mov     edx, 0C0000000h; dwDesiredAccess
0x18002359b  mov     [rsp+60h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18002359f  mov     rcx, r14; lpFileName
0x1800235a2  mov     [rsp+60h+dwCreationDisposition], 2; dwCreationDisposition
0x1800235aa  lea     r8d, [r9+3]; dwShareMode
0x1800235ae  call    cs:__imp_CreateFileW
0x1800235b5  nop     dword ptr [rax+rax+00h]
0x1800235ba  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800235be  cmp     rax, rbx
0x1800235c1  jnz     short loc_1800235D7
0x1800235c3  call    cs:__imp_GetLastError
0x1800235ca  nop     dword ptr [rax+rax+00h]
0x1800235cf  mov     [rdi+20h], eax
0x1800235d2  jmp     loc_180023340
0x1800235d7  mov     rbx, rax
0x1800235da  add     rdi, 8
0x1800235de  jz      loc_180023340
0x1800235e4  mov     [rdi], r14
0x1800235e7  mov     r14, r15
0x1800235ea  jmp     loc_180023340
0x1800235ef  mov     dword ptr [rdi+20h], 32h ; '2'
0x1800235f6  jmp     loc_1800234B1
```
