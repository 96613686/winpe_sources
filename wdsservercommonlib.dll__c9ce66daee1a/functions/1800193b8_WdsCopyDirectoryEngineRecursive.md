# WdsCopyDirectoryEngineRecursive

- ea: `0x1800193b8`
- end: `0x1800197a2`
- name: `WdsCopyDirectoryEngineRecursive`
- size: `1002`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800192f8`
- `0x1800193b8`

## callees

- `0x180018d00`
- `0x1800193b8`
- `0x180019a40`
- `0x180019eb0`
- `0x18001a28c`
- `0x18001b1c0`
- `0x18001b750`
- `0x18002e468`
- `0x18002f3ba`
- `0x18002f3e0`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800194dc`
- `KERNEL32!GetLastError` at `0x1800196a3`
- `KERNEL32!GetLastError` at `0x1800196c7`
- `KERNEL32!GetLastError` at `0x1800196db`
- `KERNEL32!GetLastError` at `0x1800194dc`
- `KERNEL32!GetLastError` at `0x1800196a3`
- `KERNEL32!GetLastError` at `0x1800196c7`
- `KERNEL32!GetLastError` at `0x1800196db`
- `KERNEL32!FindFirstFileW` at `0x1800194c5`
- `KERNEL32!FindFirstFileW` at `0x1800194c5`
- `KERNEL32!CopyFileW` at `0x1800195ab`
- `KERNEL32!CopyFileW` at `0x1800195ab`
- `KERNEL32!SetFileAttributesW` at `0x1800195c6`
- `KERNEL32!SetFileAttributesW` at `0x1800195c6`
- `KERNEL32!FindNextFileW` at `0x18001968f`
- `KERNEL32!FindNextFileW` at `0x18001968f`
- `KERNEL32!FindClose` at `0x180019742`
- `KERNEL32!FindClose` at `0x180019742`

## pseudocode

```c
__int64 __fastcall WdsCopyDirectoryEngineRecursive(
        const WCHAR *a1,
        __int64 a2,
        __int64 (__fastcall *a3)(LPCWSTR, __int64),
        __int64 a4)
{
  WCHAR *v7; // rdi
  WCHAR *v8; // rsi
  WCHAR *v9; // r14
  signed int Path; // ebx
  int v11; // r14d
  __int64 v12; // rdx
  __int64 v13; // r8
  DWORD LastError; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // eax
  int v18; // edi
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  signed int v27; // eax
  DWORD v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  int v32; // eax
  int v33; // ebx
  LPCWSTR lpNewFileName; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpFileName; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF

  v38 = a4;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  lpNewFileName = 0;
  v7 = 0;
  lpExistingFileName = 0;
  v8 = 0;
  lpFileName = 0;
  v9 = 0;
  if ( !a2 || !a1 )
  {
    Path = -2147024809;
    goto LABEL_60;
  }
  if ( !(unsigned int)WdsDirectoryExists(a1) )
    return (unsigned int)-2147024809;
  Path = WdsCreatePath(a2, 0, 1);
  if ( Path >= 0 )
  {
    Path = CopyStreams(a1);
    if ( Path >= 0 )
    {
      v11 = ConcatenatePaths(a1, L"*", &lpFileName);
      if ( (unsigned int)ElValidateWin32_8((unsigned int)v11, v12, v13, 1610) )
      {
        if ( v11 > 0 )
          Path = (unsigned __int16)v11 | 0x80070000;
        else
          Path = v11;
        v9 = (WCHAR *)lpFileName;
        goto LABEL_60;
      }
      v9 = (WCHAR *)lpFileName;
      lpFileName = (LPCWSTR)FindFirstFileW(lpFileName, &FindFileData);
      if ( lpFileName == (LPCWSTR)-1LL )
      {
        LastError = GetLastError();
        v17 = ElValidateWin32_8(LastError, v15, v16, 1619);
        Path = v17;
        if ( v17 > 0 )
          Path = (unsigned __int16)v17 | 0x80070000;
        if ( Path >= 0 )
          Path = -2147467259;
        goto LABEL_60;
      }
      while ( 1 )
      {
        v18 = ConcatenatePaths(a2, FindFileData.cFileName, &lpNewFileName);
        if ( (unsigned int)ElValidateWin32_8((unsigned int)v18, v19, v20, 1631) )
        {
          if ( v18 > 0 )
          {
            v33 = (unsigned __int16)v18;
            v7 = (WCHAR *)lpNewFileName;
            goto LABEL_57;
          }
          goto LABEL_55;
        }
        v18 = ConcatenatePaths(a1, FindFileData.cFileName, &lpExistingFileName);
        v23 = ElValidateWin32_8((unsigned int)v18, v21, v22, 1640);
        v8 = (WCHAR *)lpExistingFileName;
        if ( v23 )
        {
          if ( v18 > 0 )
          {
            Path = (unsigned __int16)v18 | 0x80070000;
LABEL_53:
            v7 = (WCHAR *)lpNewFileName;
            goto LABEL_58;
          }
LABEL_55:
          Path = v18;
          goto LABEL_53;
        }
        v7 = (WCHAR *)lpNewFileName;
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          if ( FindFileData.cFileName[0] == 46
            && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
          {
            goto LABEL_35;
          }
          if ( !a3 )
            goto LABEL_33;
          v26 = a3(lpExistingFileName, v38);
          if ( v26 != 1 )
          {
            if ( v26 == 2 )
            {
LABEL_43:
              Path = 1223;
              goto LABEL_58;
            }
LABEL_33:
            v25 = WdsCopyDirectoryEngineRecursive(v8, v7, a3, v38, 0);
            goto LABEL_34;
          }
        }
        else
        {
          if ( !a3 )
            goto LABEL_23;
          v24 = a3(lpExistingFileName, v38);
          if ( v24 != 1 )
          {
            if ( v24 == 2 )
              goto LABEL_43;
LABEL_23:
            if ( !CopyFileW(v8, v7, 0) )
            {
              v28 = GetLastError();
              v31 = 1680;
              goto LABEL_46;
            }
            if ( !SetFileAttributesW(v7, FindFileData.dwFileAttributes) )
            {
              v28 = GetLastError();
              v31 = 1691;
LABEL_46:
              v32 = ElValidateWin32_8(v28, v29, v30, v31);
              Path = v32;
              if ( v32 > 0 )
                Path = (unsigned __int16)v32 | 0x80070000;
              if ( Path >= 0 )
                Path = -2147467259;
              goto LABEL_58;
            }
            v25 = CopySecurityInformation(v8, v7, 1);
LABEL_34:
            Path = v25;
            if ( v25 < 0 )
              goto LABEL_58;
LABEL_35:
            if ( v8 )
            {
              operator delete(v8);
              v8 = 0;
              lpExistingFileName = 0;
            }
            if ( v7 )
            {
              operator delete(v7);
              v7 = 0;
              lpNewFileName = 0;
            }
          }
        }
        if ( !FindNextFileW((HANDLE)lpFileName, &FindFileData) )
        {
          v27 = GetLastError();
          if ( v27 == 18 )
            goto LABEL_58;
          if ( v27 <= 0 )
          {
            Path = v27;
            goto LABEL_58;
          }
          v33 = (unsigned __int16)v27;
LABEL_57:
          Path = v33 | 0x80070000;
LABEL_58:
          FindClose((HANDLE)lpFileName);
LABEL_60:
          if ( v9 )
            operator delete(v9);
          if ( v8 )
            operator delete(v8);
          if ( v7 )
            operator delete(v7);
          return (unsigned int)Path;
        }
      }
    }
  }
  return (unsigned int)Path;
}

```

## disassembly

```asm
0x1800193b8  push    rbp
0x1800193ba  push    rbx
0x1800193bb  push    rsi
0x1800193bc  push    rdi
0x1800193bd  push    r12
0x1800193bf  push    r13
0x1800193c1  push    r14
0x1800193c3  push    r15
0x1800193c5  lea     rbp, [rsp-1B8h]
0x1800193cd  sub     rsp, 2B8h
0x1800193d4  mov     rax, cs:__security_cookie
0x1800193db  xor     rax, rsp
0x1800193de  mov     [rbp+1F0h+var_50], rax
0x1800193e5  mov     r12, r8
0x1800193e8  mov     [rsp+2F0h+var_2A8], r9
0x1800193ed  mov     r13, rdx
0x1800193f0  mov     r15, rcx
0x1800193f3  xor     edx, edx; Val
0x1800193f5  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x1800193fa  mov     r8d, 250h; Size
0x180019400  call    memset_0
0x180019405  xor     ebx, ebx
0x180019407  mov     [rsp+2F0h+lpNewFileName], rbx
0x18001940c  mov     edi, ebx
0x18001940e  mov     [rsp+2F0h+lpExistingFileName], rbx
0x180019413  mov     esi, ebx
0x180019415  mov     [rsp+2F0h+lpFileName], rbx
0x18001941a  mov     r14d, ebx
0x18001941d  test    r13, r13
0x180019420  jz      loc_180019750
0x180019426  test    r15, r15
0x180019429  jz      loc_180019750
0x18001942f  mov     rcx, r15
0x180019432  call    WdsDirectoryExists
0x180019437  test    eax, eax
0x180019439  jnz     short loc_180019445
0x18001943b  mov     ebx, 80070057h
0x180019440  jmp     loc_18001977C
0x180019445  xor     edx, edx
0x180019447  mov     rcx, r13
0x18001944a  lea     r8d, [rdx+1]
0x18001944e  call    WdsCreatePath
0x180019453  mov     ebx, eax
0x180019455  test    eax, eax
0x180019457  js      loc_18001977C
0x18001945d  mov     rdx, r13
0x180019460  mov     rcx, r15; lpFileName
0x180019463  call    CopyStreams
0x180019468  mov     ebx, eax
0x18001946a  test    eax, eax
0x18001946c  js      loc_18001977C
0x180019472  lea     r8, [rsp+2F0h+lpFileName]
0x180019477  mov     rcx, r15
0x18001947a  lea     rdx, asc_180034514; "*"
0x180019481  call    ConcatenatePaths
0x180019486  mov     r9d, 64Ah
0x18001948c  mov     ecx, eax
0x18001948e  mov     r14d, eax
0x180019491  call    ElValidateWin32_8
0x180019496  test    eax, eax
0x180019498  jz      short loc_1800194B8
0x18001949a  test    r14d, r14d
0x18001949d  jg      short loc_1800194AC
0x18001949f  mov     ebx, r14d
0x1800194a2  mov     r14, [rsp+2F0h+lpFileName]
0x1800194a7  jmp     loc_180019755
0x1800194ac  movzx   ebx, r14w
0x1800194b0  or      ebx, 80070000h
0x1800194b6  jmp     short loc_1800194A2
0x1800194b8  mov     r14, [rsp+2F0h+lpFileName]
0x1800194bd  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x1800194c2  mov     rcx, r14; lpFileName
0x1800194c5  call    cs:__imp_FindFirstFileW
0x1800194cc  nop     dword ptr [rax+rax+00h]
0x1800194d1  mov     [rsp+2F0h+lpFileName], rax
0x1800194d6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800194da  jnz     short loc_180019516
0x1800194dc  call    cs:__imp_GetLastError
0x1800194e3  nop     dword ptr [rax+rax+00h]
0x1800194e8  mov     ecx, eax
0x1800194ea  mov     r9d, 653h
0x1800194f0  call    ElValidateWin32_8
0x1800194f5  mov     ebx, eax
0x1800194f7  test    eax, eax
0x1800194f9  jle     short loc_180019504
0x1800194fb  movzx   ebx, ax
0x1800194fe  or      ebx, 80070000h
0x180019504  test    ebx, ebx
0x180019506  js      loc_180019755
0x18001950c  mov     ebx, 80004005h
0x180019511  jmp     loc_180019755
0x180019516  lea     r8, [rsp+2F0h+lpNewFileName]
0x18001951b  mov     rcx, r13
0x18001951e  lea     rdx, [rsp+2F0h+FindFileData.cFileName]
0x180019523  call    ConcatenatePaths
0x180019528  mov     r9d, 65Fh
0x18001952e  mov     ecx, eax
0x180019530  mov     edi, eax
0x180019532  call    ElValidateWin32_8
0x180019537  test    eax, eax
0x180019539  jnz     loc_180019727
0x18001953f  lea     r8, [rsp+2F0h+lpExistingFileName]
0x180019544  mov     rcx, r15
0x180019547  lea     rdx, [rsp+2F0h+FindFileData.cFileName]
0x18001954c  call    ConcatenatePaths
0x180019551  mov     r9d, 668h
0x180019557  mov     ecx, eax
0x180019559  mov     edi, eax
0x18001955b  call    ElValidateWin32_8
0x180019560  mov     rsi, [rsp+2F0h+lpExistingFileName]
0x180019565  xor     ecx, ecx
0x180019567  test    eax, eax
0x180019569  jnz     loc_180019713
0x18001956f  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x180019574  mov     rdi, [rsp+2F0h+lpNewFileName]
0x180019579  jnz     short loc_1800195ED
0x18001957b  test    r12, r12
0x18001957e  jz      short loc_1800195A2
0x180019580  mov     rdx, [rsp+2F0h+var_2A8]
0x180019585  mov     rcx, rsi
0x180019588  mov     rax, r12
0x18001958b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019590  cmp     eax, 1
0x180019593  jz      loc_180019685
0x180019599  cmp     eax, 2
0x18001959c  jz      loc_1800196C0
0x1800195a2  xor     r8d, r8d; bFailIfExists
0x1800195a5  mov     rdx, rdi; lpNewFileName
0x1800195a8  mov     rcx, rsi; lpExistingFileName
0x1800195ab  call    cs:__imp_CopyFileW
0x1800195b2  nop     dword ptr [rax+rax+00h]
0x1800195b7  test    eax, eax
0x1800195b9  jz      loc_1800196DB
0x1800195bf  mov     edx, [rsp+2F0h+FindFileData.dwFileAttributes]; dwFileAttributes
0x1800195c3  mov     rcx, rdi; lpFileName
0x1800195c6  call    cs:__imp_SetFileAttributesW
0x1800195cd  nop     dword ptr [rax+rax+00h]
0x1800195d2  test    eax, eax
0x1800195d4  jz      loc_1800196C7
0x1800195da  mov     r8d, 1
0x1800195e0  mov     rdx, rdi; LPWSTR
0x1800195e3  mov     rcx, rsi; pObjectName
0x1800195e6  call    CopySecurityInformation
0x1800195eb  jmp     short loc_18001964F
0x1800195ed  cmp     [rsp+2F0h+FindFileData.cFileName], 2Eh ; '.'
0x1800195f3  movzx   eax, [rsp+2F0h+FindFileData.cFileName+2]
0x1800195f8  jnz     short loc_180019613
0x1800195fa  test    ax, ax
0x1800195fd  jz      short loc_180019659
0x1800195ff  cmp     [rsp+2F0h+FindFileData.cFileName], 2Eh ; '.'
0x180019605  jnz     short loc_180019613
0x180019607  cmp     ax, 2Eh ; '.'
0x18001960b  jnz     short loc_180019613
0x18001960d  cmp     [rbp+1F0h+FindFileData.cFileName+4], cx
0x180019611  jz      short loc_180019659
0x180019613  test    r12, r12
0x180019616  jz      short loc_180019638
0x180019618  mov     rdx, [rsp+2F0h+var_2A8]
0x18001961d  mov     rcx, rsi
0x180019620  mov     rax, r12
0x180019623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019628  cmp     eax, 1
0x18001962b  jz      short loc_180019685
0x18001962d  cmp     eax, 2
0x180019630  jz      loc_1800196C0
0x180019636  xor     ecx, ecx
0x180019638  mov     r9, [rsp+2F0h+var_2A8]
0x18001963d  mov     r8, r12
0x180019640  mov     [rsp+2F0h+var_2D0], ecx
0x180019644  mov     rdx, rdi
0x180019647  mov     rcx, rsi
0x18001964a  call    WdsCopyDirectoryEngineRecursive
0x18001964f  mov     ebx, eax
0x180019651  test    eax, eax
0x180019653  js      loc_18001973D
0x180019659  test    rsi, rsi
0x18001965c  jz      short loc_18001966F
0x18001965e  mov     rcx, rsi; lpMem
0x180019661  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019666  xor     ecx, ecx
0x180019668  mov     esi, ecx
0x18001966a  mov     [rsp+2F0h+lpExistingFileName], rcx
0x18001966f  test    rdi, rdi
0x180019672  jz      short loc_180019685
0x180019674  mov     rcx, rdi; lpMem
0x180019677  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001967c  xor     eax, eax
0x18001967e  mov     edi, eax
0x180019680  mov     [rsp+2F0h+lpNewFileName], rax
0x180019685  mov     rcx, [rsp+2F0h+lpFileName]; hFindFile
0x18001968a  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x18001968f  call    cs:__imp_FindNextFileW
0x180019696  nop     dword ptr [rax+rax+00h]
0x18001969b  test    eax, eax
0x18001969d  jnz     loc_180019516
0x1800196a3  call    cs:__imp_GetLastError
0x1800196aa  nop     dword ptr [rax+rax+00h]
0x1800196af  cmp     eax, 12h
0x1800196b2  jz      loc_18001973D
0x1800196b8  test    eax, eax
0x1800196ba  jg      short loc_18001970E
0x1800196bc  mov     ebx, eax
0x1800196be  jmp     short loc_18001973D
0x1800196c0  mov     ebx, 4C7h
0x1800196c5  jmp     short loc_18001973D
0x1800196c7  call    cs:__imp_GetLastError
0x1800196ce  nop     dword ptr [rax+rax+00h]
0x1800196d3  mov     r9d, 69Bh
0x1800196d9  jmp     short loc_1800196ED
0x1800196db  call    cs:__imp_GetLastError
0x1800196e2  nop     dword ptr [rax+rax+00h]
0x1800196e7  mov     r9d, 690h
0x1800196ed  mov     ecx, eax
0x1800196ef  call    ElValidateWin32_8
0x1800196f4  mov     ebx, eax
0x1800196f6  test    eax, eax
0x1800196f8  jle     short loc_180019703
0x1800196fa  movzx   ebx, ax
0x1800196fd  or      ebx, 80070000h
0x180019703  test    ebx, ebx
0x180019705  js      short loc_18001973D
0x180019707  mov     ebx, 80004005h
0x18001970c  jmp     short loc_18001973D
0x18001970e  movzx   ebx, ax
0x180019711  jmp     short loc_180019737
0x180019713  test    edi, edi
0x180019715  jle     short loc_18001972B
0x180019717  movzx   ebx, di
0x18001971a  or      ebx, 80070000h
0x180019720  mov     rdi, [rsp+2F0h+lpNewFileName]
0x180019725  jmp     short loc_18001973D
0x180019727  test    edi, edi
0x180019729  jg      short loc_18001972F
0x18001972b  mov     ebx, edi
0x18001972d  jmp     short loc_180019720
0x18001972f  movzx   ebx, di
0x180019732  mov     rdi, [rsp+2F0h+lpNewFileName]
0x180019737  or      ebx, 80070000h
0x18001973d  mov     rcx, [rsp+2F0h+lpFileName]; hFindFile
0x180019742  call    cs:__imp_FindClose
0x180019749  nop     dword ptr [rax+rax+00h]
0x18001974e  jmp     short loc_180019755
0x180019750  mov     ebx, 80070057h
0x180019755  test    r14, r14
0x180019758  jz      short loc_180019762
0x18001975a  mov     rcx, r14; lpMem
0x18001975d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019762  test    rsi, rsi
0x180019765  jz      short loc_18001976F
0x180019767  mov     rcx, rsi; lpMem
0x18001976a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001976f  test    rdi, rdi
0x180019772  jz      short loc_18001977C
0x180019774  mov     rcx, rdi; lpMem
0x180019777  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001977c  mov     eax, ebx
0x18001977e  mov     rcx, [rbp+1F0h+var_50]
0x180019785  xor     rcx, rsp; StackCookie
0x180019788  call    __security_check_cookie
0x18001978d  add     rsp, 2B8h
0x180019794  pop     r15
0x180019796  pop     r14
0x180019798  pop     r13
0x18001979a  pop     r12
0x18001979c  pop     rdi
0x18001979d  pop     rsi
0x18001979e  pop     rbx
0x18001979f  pop     rbp
0x1800197a0  retn
```
