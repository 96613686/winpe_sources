# DeleteSystemDataFolderForUser(void *,SYSTEM_DATA_FOLDER_USER_ACCESS,ushort const *,bool)

- ea: `0x18000868c`
- end: `0x180008822`
- name: `?DeleteSystemDataFolderForUser@@YAJPEAXW4SYSTEM_DATA_FOLDER_USER_ACCESS@@PEBG_N@Z`
- size: `406`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180006890`

## callees

- `0x180002230`
- `0x18000783c`
- `0x18000868c`
- `0x1800089a8`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800087fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800087fa`
- `SHELL32!SHGetFolderPathEx` at `0x180008707`
- `SHELL32!SHGetFolderPathEx` at `0x180008707`
- `SHELL32!SHCreateItemFromParsingName` at `0x180008771`
- `SHELL32!SHCreateItemFromParsingName` at `0x180008771`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800086c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800086c0`

## pseudocode

```c
__int64 __fastcall DeleteSystemDataFolderForUser(void *a1)
{
  signed int LastError; // eax
  int Folder; // ebx
  HWND v3; // rcx
  const struct _GUID *v4; // r8
  void *v6; // [rsp+40h] [rbp-C0h] BYREF
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+60h] [rbp-A0h] BYREF

  StringSid = 0;
  if ( ConvertSidToStringSidW(a1, &StringSid) )
  {
    Folder = SHGetFolderPathEx(&FOLDERID_ProgramData, 0, 0, pszPath, 260);
    if ( Folder >= 0 )
    {
      Folder = _AppendPathAndCreateFolder(L"Microsoft\\Windows\\SystemData");
      if ( Folder >= 0 )
      {
        Folder = _AppendPathAndCreateFolder(StringSid);
        if ( Folder >= 0 )
        {
          ppv = 0;
          Folder = SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
          if ( Folder >= 0 )
          {
            v6 = 0;
            Folder = SHCreateFileOperation(v3, 0x614u, v4, &v6);
            if ( Folder >= 0 )
            {
              Folder = (*(__int64 (__fastcall **)(void *, void *, _QWORD))(*(_QWORD *)v6 + 144LL))(v6, ppv, 0);
              if ( Folder >= 0 )
                Folder = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v6 + 168LL))(v6);
              (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
          }
        }
      }
    }
    LocalFree(StringSid);
  }
  else
  {
    LastError = GetLastError();
    Folder = LastError;
    if ( LastError > 0 )
      Folder = (unsigned __int16)LastError | 0x80070000;
    if ( Folder >= 0 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)Folder;
}

```

## disassembly

```asm
0x18000868c  mov     [rsp-8+arg_8], rbx
0x180008691  push    rbp
0x180008692  lea     rbp, [rsp-180h]
0x18000869a  sub     rsp, 280h
0x1800086a1  mov     rax, cs:__security_cookie
0x1800086a8  xor     rax, rsp
0x1800086ab  mov     [rbp+180h+var_10], rax
0x1800086b2  lea     rdx, [rsp+280h+StringSid]; StringSid
0x1800086b7  mov     [rsp+280h+StringSid], 0
0x1800086c0  call    cs:__imp_ConvertSidToStringSidW
0x1800086c6  test    eax, eax
0x1800086c8  jnz     short loc_1800086EE
0x1800086ca  call    cs:__imp_GetLastError
0x1800086d0  mov     ebx, eax
0x1800086d2  test    eax, eax
0x1800086d4  jle     short loc_1800086DF
0x1800086d6  movzx   ebx, ax
0x1800086d9  or      ebx, 80070000h
0x1800086df  test    ebx, ebx
0x1800086e1  mov     eax, 80004005h
0x1800086e6  cmovns  ebx, eax
0x1800086e9  jmp     loc_180008800
0x1800086ee  lea     r9, [rsp+280h+pszPath]
0x1800086f3  mov     [rsp+280h+var_260], 104h
0x1800086fb  xor     r8d, r8d
0x1800086fe  lea     rcx, FOLDERID_ProgramData
0x180008705  xor     edx, edx
0x180008707  call    cs:__imp_SHGetFolderPathEx
0x18000870d  mov     ebx, eax
0x18000870f  test    eax, eax
0x180008711  js      loc_1800087F5
0x180008717  lea     rax, [rsp+280h+pszPath]
0x18000871c  lea     rcx, aMicrosoftWindo; "Microsoft\\Windows\\SystemData"
0x180008723  mov     [rsp+280h+var_258], rax
0x180008728  call    ?_AppendPathAndCreateFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@_NPEAGI@Z; _AppendPathAndCreateFolder(ushort const *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS,bool,ushort *,uint)
0x18000872d  mov     ebx, eax
0x18000872f  test    eax, eax
0x180008731  js      loc_1800087F5
0x180008737  mov     rcx, [rsp+280h+StringSid]
0x18000873c  lea     rax, [rsp+280h+pszPath]
0x180008741  mov     [rsp+280h+var_258], rax
0x180008746  call    ?_AppendPathAndCreateFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@_NPEAGI@Z; _AppendPathAndCreateFolder(ushort const *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS,bool,ushort *,uint)
0x18000874b  mov     ebx, eax
0x18000874d  test    eax, eax
0x18000874f  js      loc_1800087F5
0x180008755  lea     r9, [rsp+280h+ppv]; ppv
0x18000875a  mov     [rsp+280h+ppv], 0
0x180008763  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18000876a  xor     edx, edx; pbc
0x18000876c  lea     rcx, [rsp+280h+pszPath]; pszPath
0x180008771  call    cs:__imp_SHCreateItemFromParsingName
0x180008777  mov     ebx, eax
0x180008779  test    eax, eax
0x18000877b  js      short loc_1800087F5
0x18000877d  lea     r9, [rsp+280h+var_240]; void **
0x180008782  mov     [rsp+280h+var_240], 0
0x18000878b  mov     edx, 614h; unsigned int
0x180008790  call    ?SHCreateFileOperation@@YAJPEAUHWND__@@KAEBU_GUID@@PEAPEAX@Z; SHCreateFileOperation(HWND__ *,ulong,_GUID const &,void * *)
0x180008795  mov     ebx, eax
0x180008797  test    eax, eax
0x180008799  js      short loc_1800087E4
0x18000879b  mov     rcx, [rsp+280h+var_240]
0x1800087a0  xor     r8d, r8d
0x1800087a3  mov     rdx, [rsp+280h+ppv]
0x1800087a8  mov     rax, [rcx]
0x1800087ab  mov     rax, [rax+90h]
0x1800087b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087b7  mov     ebx, eax
0x1800087b9  test    eax, eax
0x1800087bb  js      short loc_1800087D3
0x1800087bd  mov     rcx, [rsp+280h+var_240]
0x1800087c2  mov     rax, [rcx]
0x1800087c5  mov     rax, [rax+0A8h]
0x1800087cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087d1  mov     ebx, eax
0x1800087d3  mov     rcx, [rsp+280h+var_240]
0x1800087d8  mov     rax, [rcx]
0x1800087db  mov     rax, [rax+10h]
0x1800087df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087e4  mov     rcx, [rsp+280h+ppv]
0x1800087e9  mov     rax, [rcx]
0x1800087ec  mov     rax, [rax+10h]
0x1800087f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087f5  mov     rcx, [rsp+280h+StringSid]; hMem
0x1800087fa  call    cs:__imp_LocalFree
0x180008800  mov     eax, ebx
0x180008802  mov     rcx, [rbp+180h+var_10]
0x180008809  xor     rcx, rsp; StackCookie
0x18000880c  call    __security_check_cookie
0x180008811  mov     rbx, [rsp+280h+arg_8]
0x180008819  add     rsp, 280h
0x180008820  pop     rbp
0x180008821  retn
```
