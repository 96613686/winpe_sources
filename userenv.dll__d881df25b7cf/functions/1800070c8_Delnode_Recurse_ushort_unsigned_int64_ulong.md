# _Delnode_Recurse(ushort *,unsigned __int64,ulong)

- ea: `0x1800070c8`
- end: `0x180007587`
- name: `?_Delnode_Recurse@@YAJPEAG_KK@Z`
- size: `1215`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800070c8`
- `0x18001aa00`

## callees

- `0x1800070c8`
- `0x180007590`
- `0x180007724`
- `0x18000778c`
- `0x180007834`
- `0x1800079f0`
- `0x180007a44`
- `0x18000dc50`
- `0x18001a3e0`
- `0x18001ac14`
- `0x18001b3b4`
- `0x18001b3e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007351`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007459`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000747d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007507`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007351`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007459`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000747d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007507`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007576`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007576`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800072ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800073c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800072ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800073c3`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800071a0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180007440`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800071a0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180007440`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000722c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800072da`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000722c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800072da`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180007219`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180007219`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslashEx` at `0x180007148`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslashEx` at `0x180007148`
- `cldapi!CfGetPlaceholderStateFromAttributeTag` at `0x180007543`
- `cldapi!CfGetPlaceholderStateFromAttributeTag` at `0x180007543`

## string_xrefs

- `0x1800072bc`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180007340`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180007373`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x1800073af`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x1800074a5`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x1800074ec`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _Delnode_Recurse(unsigned __int16 *a1, unsigned __int64 a2, unsigned int a3)
{
  char v3; // r13
  __int64 StringLengthHr; // rax
  unsigned int v7; // ebx
  struct _WIN32_FIND_DATAW *v8; // rdi
  unsigned __int16 *v9; // rsi
  HRESULT v10; // eax
  wil::details::in1diag3 *v11; // rcx
  struct _WIN32_FIND_DATAW *v12; // rax
  HANDLE FirstFileW; // r14
  int v14; // eax
  char *v16; // r13
  char v17; // bl
  __int64 v18; // rdx
  signed int v19; // eax
  int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  unsigned __int16 *v24; // rax
  __int64 v25; // rdx
  DWORD LastError; // eax
  int v27; // [rsp+20h] [rbp-30h]
  PWSTR ppszEnd; // [rsp+30h] [rbp-20h] BYREF
  size_t pcchRemaining; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int16 *v30; // [rsp+40h] [rbp-10h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  char *v34; // [rsp+A8h] [rbp+58h] BYREF

  v3 = a3;
  LODWORD(v34) = -2147467259;
  ppszEnd = 0;
  pcchRemaining = 0;
  StringLengthHr = anonymous_namespace_::_GetStringLengthHr(&v34, a1);
  v7 = (unsigned int)v34;
  if ( (int)v34 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xCC7,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
      (const char *)(unsigned int)v34,
      v27);
    return v7;
  }
  v8 = 0;
  if ( a2 >= StringLengthHr + 262 )
  {
    LODWORD(v34) = 0;
    v9 = a1;
    v30 = a1;
    goto LABEL_4;
  }
  a2 += 520LL;
  v24 = (unsigned __int16 *)ProfAlloc(2 * a2);
  v9 = v24;
  v30 = v24;
  if ( v24 )
  {
    LODWORD(v34) = 1;
    v20 = StringCchCopyW(v24, a2, a1);
    v7 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xCDB,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
        (const char *)(unsigned int)v20,
        v27);
LABEL_36:
      LocalFree(v9);
LABEL_17:
      if ( v8 )
        LocalFree(v8);
      return v7;
    }
LABEL_4:
    v10 = PathCchAddBackslashEx(v9, a2, &ppszEnd, &pcchRemaining);
    v7 = v10;
    v11 = retaddr;
    if ( v10 >= 0 )
    {
      v10 = StringCchCopyW(ppszEnd, pcchRemaining, L"*.*");
      v7 = v10;
      v11 = retaddr;
      if ( v10 < 0 )
      {
        v25 = 3314;
        goto LABEL_53;
      }
      v12 = (struct _WIN32_FIND_DATAW *)ProfAlloc(0x250u);
      v8 = v12;
      if ( v12 )
      {
        FirstFileW = FindFirstFileW(v9, v12);
        if ( FirstFileW != (HANDLE)-1LL )
        {
          while ( 1 )
          {
LABEL_8:
            if ( !StringIsEqual(v8->cFileName, L".") && !StringIsEqual(v8->cFileName, L"..") )
            {
              v14 = StringCchCopyW(ppszEnd, pcchRemaining, v8->cFileName);
              v7 = v14;
              if ( v14 < 0 )
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xD55,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
                  (const char *)(unsigned int)v14,
                  v27);
                FindClose(FirstFileW);
                goto LABEL_16;
              }
              if ( (v8->dwFileAttributes & 0x10) != 0 )
              {
                wil::TryCreateFileCanRecurseIntoDirectory(&hObject, v9, v8);
                v16 = (char *)hObject;
                if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                {
                  v17 = 0;
                  if ( (v8->dwFileAttributes & 0x400) != 0 && !byte_1800297B0 )
                  {
                    if ( (CfGetPlaceholderStateFromAttributeTag(v8->dwFileAttributes, v8->dwReserved0) & 2) != 0 )
                    {
                      v17 = 1;
                      byte_1800297B0 = 1;
                      UserenvTelemetry::EnterAndDeleteCloudFilesFolder();
                    }
                    else
                    {
                      UserenvTelemetry::EnterAndDeleteNotCloudFilesReparsePointsFolder<unsigned short * &>(&v30);
                    }
                  }
                  _Delnode_Recurse(v9, a2, a3);
                  StringCchCopyW(ppszEnd, pcchRemaining, v8->cFileName);
                  if ( v17 )
                    byte_1800297B0 = 0;
                }
                _TryBestToDelete(v9, v8->dwFileAttributes, a3);
                if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                  CloseHandle(v16);
                v3 = a3;
              }
              else
              {
                _TryBestToDelete(v9, v8->dwFileAttributes, v3);
              }
            }
            if ( !FindNextFileW(FirstFileW, v8) )
            {
              FindClose(FirstFileW);
              goto LABEL_15;
            }
          }
        }
        LastError = GetLastError();
        if ( LastError - 2 <= 1 )
        {
LABEL_15:
          v7 = 0;
          goto LABEL_16;
        }
        if ( LastError == 5 && (v3 & 2) != 0 )
        {
          *ppszEnd = 0;
          v10 = _TakeOwnerAndAddAccess(v9);
          v7 = v10;
          v11 = retaddr;
          if ( v10 < 0 )
          {
            v25 = 3357;
          }
          else
          {
            v10 = StringCchCopyW(ppszEnd, pcchRemaining, L"*.*");
            v7 = v10;
            v11 = retaddr;
            if ( v10 >= 0 )
            {
              FirstFileW = FindFirstFileW(v9, v8);
              if ( FirstFileW != (HANDLE)-1LL )
                goto LABEL_8;
              v22 = GetLastError();
              v7 = v22;
              if ( v22 > 0 )
                v7 = (unsigned __int16)v22 | 0x80070000;
              v18 = 3378;
              goto LABEL_30;
            }
            v25 = 3367;
          }
LABEL_53:
          wil::details::in1diag3::_Log_Hr(
            v11,
            (void *)v25,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
            (const char *)(unsigned int)v10,
            v27);
LABEL_16:
          if ( !(_DWORD)v34 )
            goto LABEL_17;
          goto LABEL_36;
        }
        v23 = GetLastError();
        v7 = v23;
        if ( v23 > 0 )
          v7 = (unsigned __int16)v23 | 0x80070000;
        v18 = 3386;
      }
      else
      {
        v21 = GetLastError();
        v7 = v21;
        if ( v21 > 0 )
          v7 = (unsigned __int16)v21 | 0x80070000;
        v18 = 3327;
      }
LABEL_30:
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
        (const char *)v7,
        v27);
      goto LABEL_16;
    }
    v25 = 3308;
    goto LABEL_53;
  }
  v19 = GetLastError();
  v7 = v19;
  if ( v19 > 0 )
    v7 = (unsigned __int16)v19 | 0x80070000;
  wil::details::in1diag3::Log_Hr(
    retaddr,
    (void *)0xCD4,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
    (const char *)v7,
    v27);
  return v7;
}

```

## disassembly

```asm
0x1800070c8  mov     [rsp-38h+arg_0], rbx
0x1800070cd  mov     [rsp-38h+arg_10], r8d
0x1800070d2  push    rbp
0x1800070d3  push    rsi
0x1800070d4  push    rdi
0x1800070d5  push    r12
0x1800070d7  push    r13
0x1800070d9  push    r14
0x1800070db  push    r15
0x1800070dd  mov     rbp, rsp
0x1800070e0  sub     rsp, 50h
0x1800070e4  mov     r13d, r8d
0x1800070e7  mov     r15, rdx
0x1800070ea  mov     r14, rcx
0x1800070ed  mov     dword ptr [rbp+arg_18], 80004005h
0x1800070f4  mov     [rbp+ppszEnd], 0
0x1800070fc  mov     [rbp+pcchRemaining], 0
0x180007104  mov     rdx, rcx
0x180007107  lea     rcx, [rbp+arg_18]
0x18000710b  call    _anonymous_namespace____GetStringLengthHr
0x180007110  mov     ebx, dword ptr [rbp+arg_18]
0x180007113  mov     rcx, [rbp+38h]; this
0x180007117  test    ebx, ebx
0x180007119  js      loc_1800074A2
0x18000711f  xor     edi, edi
0x180007121  add     rax, 106h
0x180007127  cmp     r15, rax
0x18000712a  jb      loc_1800074BB
0x180007130  mov     dword ptr [rbp+arg_18], edi
0x180007133  mov     rsi, r14
0x180007136  mov     [rbp+var_10], r14
0x18000713a  lea     r9, [rbp+pcchRemaining]; pcchRemaining
0x18000713e  lea     r8, [rbp+ppszEnd]; ppszEnd
0x180007142  mov     rdx, r15; cchPath
0x180007145  mov     rcx, rsi; pszPath
0x180007148  call    cs:__imp_PathCchAddBackslashEx
0x18000714f  nop     dword ptr [rax+rax+00h]
0x180007154  mov     ebx, eax
0x180007156  mov     rcx, [rbp+38h]
0x18000715a  test    eax, eax
0x18000715c  js      loc_1800074E0
0x180007162  lea     r8, asc_18001FAF8; "*.*"
0x180007169  mov     rdx, [rbp+pcchRemaining]; unsigned __int64
0x18000716d  mov     rcx, [rbp+ppszEnd]; unsigned __int16 *
0x180007171  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007176  mov     ebx, eax
0x180007178  mov     rcx, [rbp+38h]
0x18000717c  test    eax, eax
0x18000717e  js      loc_180007500
0x180007184  mov     ecx, 250h; dwBytes
0x180007189  call    ?ProfAlloc@@YAPEAX_K@Z; ProfAlloc(unsigned __int64)
0x18000718e  mov     rdi, rax
0x180007191  test    rax, rax
0x180007194  jz      loc_1800073D4
0x18000719a  mov     rdx, rax; lpFindFileData
0x18000719d  mov     rcx, rsi; lpFileName
0x1800071a0  call    cs:__imp_FindFirstFileW
0x1800071a7  nop     dword ptr [rax+rax+00h]
0x1800071ac  mov     r14, rax
0x1800071af  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800071b3  jz      loc_180007507
0x1800071b9  lea     r12, [rdi+2Ch]
0x1800071bd  lea     rdx, asc_18001FAE8; "."
0x1800071c4  mov     rcx, r12; unsigned __int16 *
0x1800071c7  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x1800071cc  test    eax, eax
0x1800071ce  jnz     short loc_180007213
0x1800071d0  lea     rdx, asc_18001FAEC; ".."
0x1800071d7  mov     rcx, r12; unsigned __int16 *
0x1800071da  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x1800071df  test    eax, eax
0x1800071e1  jnz     short loc_180007213
0x1800071e3  mov     r8, r12; unsigned __int16 *
0x1800071e6  mov     rdx, [rbp+pcchRemaining]; unsigned __int64
0x1800071ea  mov     rcx, [rbp+ppszEnd]; unsigned __int16 *
0x1800071ee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800071f3  mov     ebx, eax
0x1800071f5  mov     rcx, [rbp+38h]; this
0x1800071f9  test    eax, eax
0x1800071fb  js      loc_1800072B9
0x180007201  test    byte ptr [rdi], 10h
0x180007204  jnz     short loc_180007264
0x180007206  mov     r8d, r13d; unsigned int
0x180007209  mov     edx, [rdi]; unsigned int
0x18000720b  mov     rcx, rsi; lpFileName
0x18000720e  call    ?_TryBestToDelete@@YAJPEBGKK@Z; _TryBestToDelete(ushort const *,ulong,ulong)
0x180007213  mov     rdx, rdi; lpFindFileData
0x180007216  mov     rcx, r14; hFindFile
0x180007219  call    cs:__imp_FindNextFileW
0x180007220  nop     dword ptr [rax+rax+00h]
0x180007225  test    eax, eax
0x180007227  jnz     short loc_1800071BD
0x180007229  mov     rcx, r14; hFindFile
0x18000722c  call    cs:__imp_FindClose
0x180007233  nop     dword ptr [rax+rax+00h]
0x180007238  xor     ebx, ebx
0x18000723a  cmp     dword ptr [rbp+arg_18], 0
0x18000723e  jnz     loc_1800073C0
0x180007244  test    rdi, rdi
0x180007247  jnz     short loc_1800072A8
0x180007249  mov     eax, ebx
0x18000724b  mov     rbx, [rsp+50h+arg_0]
0x180007253  add     rsp, 50h
0x180007257  pop     r15
0x180007259  pop     r14
0x18000725b  pop     r13
0x18000725d  pop     r12
0x18000725f  pop     rdi
0x180007260  pop     rsi
0x180007261  pop     rbp
0x180007262  retn
0x180007264  mov     r8, rdi
0x180007267  mov     rdx, rsi
0x18000726a  lea     rcx, [rbp+hObject]
0x18000726e  call    ?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z; wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)
0x180007273  nop
0x180007274  mov     r13, [rbp+hObject]
0x180007278  lea     rax, [r13-1]
0x18000727c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007280  jbe     short loc_1800072EB
0x180007282  mov     r8d, [rbp+arg_10]; unsigned int
0x180007286  mov     edx, [rdi]; unsigned int
0x180007288  mov     rcx, rsi; lpFileName
0x18000728b  call    ?_TryBestToDelete@@YAJPEBGKK@Z; _TryBestToDelete(ushort const *,ulong,ulong)
0x180007290  nop
0x180007291  lea     rax, [r13-1]
0x180007295  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007299  jbe     loc_180007573
0x18000729f  mov     r13d, [rbp+arg_10]
0x1800072a3  jmp     loc_180007213
0x1800072a8  mov     rcx, rdi; hMem
0x1800072ab  call    cs:__imp_LocalFree
0x1800072b2  nop     dword ptr [rax+rax+00h]
0x1800072b7  jmp     short loc_180007249
0x1800072b9  mov     r9d, eax; char *
0x1800072bc  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800072c3  mov     edx, 0D55h; void *
0x1800072c8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800072cd  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800072d1  jz      loc_18000723A
0x1800072d7  mov     rcx, r14; hFindFile
0x1800072da  call    cs:__imp_FindClose
0x1800072e1  nop     dword ptr [rax+rax+00h]
0x1800072e6  jmp     loc_18000723A
0x1800072eb  xor     bl, bl
0x1800072ed  test    dword ptr [rdi], 400h
0x1800072f3  jz      short loc_180007301
0x1800072f5  cmp     cs:byte_1800297B0, bl
0x1800072fb  jz      loc_18000753E
0x180007301  mov     r8d, [rbp+arg_10]; unsigned int
0x180007305  mov     rdx, r15; unsigned __int64
0x180007308  mov     rcx, rsi; unsigned __int16 *
0x18000730b  call    ?_Delnode_Recurse@@YAJPEAG_KK@Z; _Delnode_Recurse(ushort *,unsigned __int64,ulong)
0x180007310  mov     r8, r12; unsigned __int16 *
0x180007313  mov     rdx, [rbp+pcchRemaining]; unsigned __int64
0x180007317  mov     rcx, [rbp+ppszEnd]; unsigned __int16 *
0x18000731b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007320  test    bl, bl
0x180007322  jz      loc_180007282
0x180007328  mov     cs:byte_1800297B0, 0
0x18000732f  jmp     loc_180007282
0x180007334  mov     edx, 0D32h; void *
0x180007339  mov     rcx, [rbp+38h]; this
0x18000733d  mov     r9d, ebx; char *
0x180007340  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180007347  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000734c  jmp     loc_18000723A
0x180007351  call    cs:__imp_GetLastError
0x180007358  nop     dword ptr [rax+rax+00h]
0x18000735d  mov     ebx, eax
0x18000735f  test    eax, eax
0x180007361  jle     short loc_18000736C
0x180007363  movzx   ebx, ax
0x180007366  or      ebx, 80070000h
0x18000736c  mov     rcx, [rbp+38h]; this
0x180007370  mov     r9d, ebx; char *
0x180007373  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000737a  mov     edx, 0CD4h; void *
0x18000737f  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180007384  jmp     loc_180007249
0x180007389  mov     dword ptr [rbp+arg_18], 1
0x180007390  mov     r8, r14; unsigned __int16 *
0x180007393  mov     rdx, r15; unsigned __int64
0x180007396  mov     rcx, rax; unsigned __int16 *
0x180007399  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000739e  mov     ebx, eax
0x1800073a0  mov     rcx, [rbp+38h]; this
0x1800073a4  test    eax, eax
0x1800073a6  jns     loc_18000713A
0x1800073ac  mov     r9d, eax; char *
0x1800073af  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800073b6  mov     edx, 0CDBh; void *
0x1800073bb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800073c0  mov     rcx, rsi; hMem
0x1800073c3  call    cs:__imp_LocalFree
0x1800073ca  nop     dword ptr [rax+rax+00h]
0x1800073cf  jmp     loc_180007244
0x1800073d4  call    cs:__imp_GetLastError
0x1800073db  nop     dword ptr [rax+rax+00h]
0x1800073e0  mov     ebx, eax
0x1800073e2  test    eax, eax
0x1800073e4  jle     short loc_1800073EF
0x1800073e6  movzx   ebx, ax
0x1800073e9  or      ebx, 80070000h
0x1800073ef  mov     edx, 0CFFh
0x1800073f4  jmp     loc_180007339
0x1800073f9  xor     ecx, ecx
0x1800073fb  mov     rax, [rbp+ppszEnd]
0x1800073ff  mov     [rax], cx
0x180007402  mov     rcx, rsi; pObjectName
0x180007405  call    ?_TakeOwnerAndAddAccess@@YAJPEBG@Z; _TakeOwnerAndAddAccess(ushort const *)
0x18000740a  mov     ebx, eax
0x18000740c  mov     rcx, [rbp+38h]
0x180007410  test    eax, eax
0x180007412  js      loc_180007537
0x180007418  lea     r8, asc_18001FAF8; "*.*"
0x18000741f  mov     rdx, [rbp+pcchRemaining]; unsigned __int64
0x180007423  mov     rcx, [rbp+ppszEnd]; unsigned __int16 *
0x180007427  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000742c  mov     ebx, eax
0x18000742e  mov     rcx, [rbp+38h]; this
0x180007432  test    eax, eax
0x180007434  js      loc_1800074E7
0x18000743a  mov     rdx, rdi; lpFindFileData
0x18000743d  mov     rcx, rsi; lpFileName
0x180007440  call    cs:__imp_FindFirstFileW
0x180007447  nop     dword ptr [rax+rax+00h]
0x18000744c  mov     r14, rax
0x18000744f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007453  jnz     loc_1800071B9
0x180007459  call    cs:__imp_GetLastError
0x180007460  nop     dword ptr [rax+rax+00h]
0x180007465  mov     ebx, eax
0x180007467  test    eax, eax
0x180007469  jle     loc_180007334
0x18000746f  movzx   ebx, ax
0x180007472  or      ebx, 80070000h
0x180007478  jmp     loc_180007334
0x18000747d  call    cs:__imp_GetLastError
0x180007484  nop     dword ptr [rax+rax+00h]
0x180007489  mov     ebx, eax
0x18000748b  test    eax, eax
0x18000748d  jle     short loc_180007498
0x18000748f  movzx   ebx, ax
0x180007492  or      ebx, 80070000h
0x180007498  mov     edx, 0D3Ah
0x18000749d  jmp     loc_180007339
0x1800074a2  mov     r9d, ebx; char *
0x1800074a5  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800074ac  mov     edx, 0CC7h; void *
0x1800074b1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800074b6  jmp     loc_180007249
0x1800074bb  add     r15, 208h
0x1800074c2  lea     rcx, [r15+r15]; dwBytes
0x1800074c6  call    ?ProfAlloc@@YAPEAX_K@Z; ProfAlloc(unsigned __int64)
0x1800074cb  mov     rsi, rax
0x1800074ce  mov     [rbp+var_10], rax
0x1800074d2  test    rax, rax
0x1800074d5  jnz     loc_180007389
0x1800074db  jmp     loc_180007351
0x1800074e0  mov     edx, 0CECh
0x1800074e5  jmp     short loc_1800074EC
0x1800074e7  mov     edx, 0D27h; void *
0x1800074ec  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800074f3  mov     r9d, eax; char *
0x1800074f6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800074fb  jmp     loc_18000723A
0x180007500  mov     edx, 0CF2h
0x180007505  jmp     short loc_1800074EC
0x180007507  call    cs:__imp_GetLastError
0x18000750e  nop     dword ptr [rax+rax+00h]
0x180007513  lea     ecx, [rax-2]
0x180007516  cmp     ecx, 1
0x180007519  jbe     loc_180007238
0x18000751f  cmp     eax, 5
0x180007522  jnz     loc_18000747D
0x180007528  test    r13b, 2
0x18000752c  jz      loc_18000747D
0x180007532  jmp     loc_1800073F9
0x180007537  mov     edx, 0D1Dh
0x18000753c  jmp     short loc_1800074EC
0x18000753e  mov     edx, [rdi+24h]
0x180007541  mov     ecx, [rdi]
0x180007543  call    cs:__imp_CfGetPlaceholderStateFromAttributeTag
0x18000754a  nop     dword ptr [rax+rax+00h]
0x18000754f  test    al, 2
0x180007551  jz      short loc_180007565
0x180007553  mov     bl, 1
0x180007555  mov     cs:byte_1800297B0, bl
0x18000755b  call    ?EnterAndDeleteCloudFilesFolder@UserenvTelemetry@@SAXXZ; UserenvTelemetry::EnterAndDeleteCloudFilesFolder(void)
0x180007560  jmp     loc_180007301
0x180007565  lea     rcx, [rbp+var_10]
0x180007569  call    ??$EnterAndDeleteNotCloudFilesReparsePointsFolder@AEAPEAG@UserenvTelemetry@@SAXAEAPEAG@Z; UserenvTelemetry::EnterAndDeleteNotCloudFilesReparsePointsFolder<ushort * &>(ushort * &)
0x18000756e  jmp     loc_180007301
0x180007573  mov     rcx, r13; hObject
0x180007576  call    cs:__imp_CloseHandle
0x18000757d  nop     dword ptr [rax+rax+00h]
0x180007582  jmp     loc_18000729F
```
