# SaveStreamToSystemDataFolder(void *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS,ushort const *,ushort const *,IStream *,SAVE_STREAM_MODE,ushort * *)

- ea: `0x18001720c`
- end: `0x180017359`
- name: `?SaveStreamToSystemDataFolder@@YAJPEAXW4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@PEBG3PEAUIStream@@W4SAVE_STREAM_MODE@@PEAPEAG@Z`
- size: `333`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18000ad34`

## callees

- `0x180002610`
- `0x1800092b8`
- `0x18000a1c8`
- `0x180016180`
- `0x1800165c8`
- `0x1800170b0`
- `0x18001720c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800172a3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800172a3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001731a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001731a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180017282`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180017282`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017336`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017336`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800172da`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800172da`

## pseudocode

```c
__int64 __fastcall SaveStreamToSystemDataFolder(void *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  HRESULT SystemDataFolderForUser; // ebx
  void *ppv; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v12[264]; // [rsp+250h] [rbp+150h] BYREF

  SystemDataFolderForUser = GetSystemDataFolderForUser(a1, a2, a3, v12);
  if ( SystemDataFolderForUser >= 0 )
  {
    SystemDataFolderForUser = StringCchCopyW(pszPath, 0x104u, v12);
    if ( SystemDataFolderForUser >= 0 )
    {
      SystemDataFolderForUser = PathCchAppend(pszPath, 0x104u, L"background.png");
      if ( SystemDataFolderForUser >= 0 )
      {
        StringSid = 0;
        if ( ConvertSidToStringSidW(a1, &StringSid)
          || (SystemDataFolderForUser = ResultFromKnownLastError(), SystemDataFolderForUser >= 0) )
        {
          ppv = 0;
          SystemDataFolderForUser = SHCreateItemFromParsingName(
                                      v12,
                                      0,
                                      &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                      &ppv);
          if ( SystemDataFolderForUser >= 0 )
          {
            SystemDataFolderForUser = SaveStreamToFolder(ppv, a6);
            if ( SystemDataFolderForUser < 0
              || (SystemDataFolderForUser = _SetSecurityOnFileOrFolder(pszPath, StringSid, 1),
                  SystemDataFolderForUser < 0) )
            {
              DeleteFileW(pszPath);
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
          }
          LocalFree(StringSid);
        }
      }
    }
  }
  return (unsigned int)SystemDataFolderForUser;
}

```

## disassembly

```asm
0x18001720c  push    rbp
0x18001720e  push    rbx
0x18001720f  push    rsi
0x180017210  push    rdi
0x180017211  lea     rbp, [rsp-378h]
0x180017219  sub     rsp, 478h
0x180017220  mov     rax, cs:__security_cookie
0x180017227  xor     rax, rsp
0x18001722a  mov     [rbp+390h+var_30], rax
0x180017231  mov     rsi, [rbp+390h+arg_28]
0x180017238  lea     r9, [rbp+390h+var_240]
0x18001723f  mov     rdi, rcx
0x180017242  call    ?GetSystemDataFolderForUser@@YAJPEAXPEBGW4SYSTEM_DATA_FOLDER_USER_ACCESS@@PEAGI_N@Z; GetSystemDataFolderForUser(void *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,ushort *,uint,bool)
0x180017247  mov     ebx, eax
0x180017249  test    eax, eax
0x18001724b  js      loc_18001733C
0x180017251  lea     r8, [rbp+390h+var_240]; unsigned __int16 *
0x180017258  mov     edx, 104h; unsigned __int64
0x18001725d  lea     rcx, [rsp+490h+pszPath]; unsigned __int16 *
0x180017262  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017267  mov     ebx, eax
0x180017269  test    eax, eax
0x18001726b  js      loc_18001733C
0x180017271  lea     r8, pszMore; "background.png"
0x180017278  mov     edx, 104h; cchPath
0x18001727d  lea     rcx, [rsp+490h+pszPath]; pszPath
0x180017282  call    cs:__imp_PathCchAppend
0x180017288  mov     ebx, eax
0x18001728a  test    eax, eax
0x18001728c  js      loc_18001733C
0x180017292  lea     rdx, [rsp+490h+StringSid]; StringSid
0x180017297  mov     [rsp+490h+StringSid], 0
0x1800172a0  mov     rcx, rdi; Sid
0x1800172a3  call    cs:__imp_ConvertSidToStringSidW
0x1800172a9  test    eax, eax
0x1800172ab  jnz     short loc_1800172BC
0x1800172ad  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800172b2  mov     ebx, eax
0x1800172b4  test    eax, eax
0x1800172b6  js      loc_18001733C
0x1800172bc  lea     r9, [rsp+490h+ppv]; ppv
0x1800172c1  mov     [rsp+490h+ppv], 0
0x1800172ca  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800172d1  xor     edx, edx; pbc
0x1800172d3  lea     rcx, [rbp+390h+var_240]; pszPath
0x1800172da  call    cs:__imp_SHCreateItemFromParsingName
0x1800172e0  mov     ebx, eax
0x1800172e2  test    eax, eax
0x1800172e4  js      short loc_180017331
0x1800172e6  mov     rcx, [rsp+490h+ppv]
0x1800172eb  mov     rdx, rsi
0x1800172ee  call    ?SaveStreamToFolder@@YAJPEAUIShellItem@@PEAUIStream@@PEBGW4SAVE_STREAM_MODE@@@Z; SaveStreamToFolder(IShellItem *,IStream *,ushort const *,SAVE_STREAM_MODE)
0x1800172f3  mov     ebx, eax
0x1800172f5  test    eax, eax
0x1800172f7  js      short loc_180017315
0x1800172f9  mov     rdx, [rsp+490h+StringSid]
0x1800172fe  lea     rcx, [rsp+490h+pszPath]
0x180017303  xor     r9d, r9d
0x180017306  lea     r8d, [r9+1]
0x18001730a  call    ?_SetSecurityOnFileOrFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@@Z; _SetSecurityOnFileOrFolder(ushort const *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS)
0x18001730f  mov     ebx, eax
0x180017311  test    eax, eax
0x180017313  jns     short loc_180017320
0x180017315  lea     rcx, [rsp+490h+pszPath]; lpFileName
0x18001731a  call    cs:__imp_DeleteFileW
0x180017320  mov     rcx, [rsp+490h+ppv]
0x180017325  mov     rax, [rcx]
0x180017328  mov     rax, [rax+10h]
0x18001732c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017331  mov     rcx, [rsp+490h+StringSid]; hMem
0x180017336  call    cs:__imp_LocalFree
0x18001733c  mov     eax, ebx
0x18001733e  mov     rcx, [rbp+390h+var_30]
0x180017345  xor     rcx, rsp; StackCookie
0x180017348  call    __security_check_cookie
0x18001734d  add     rsp, 478h
0x180017354  pop     rdi
0x180017355  pop     rsi
0x180017356  pop     rbx
0x180017357  pop     rbp
0x180017358  retn
```
