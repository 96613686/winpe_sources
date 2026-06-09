# GetSystemDataFolderForUser(void *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,ushort *,uint,bool)

- ea: `0x180016180`
- end: `0x18001630b`
- name: `?GetSystemDataFolderForUser@@YAJPEAXPEBGW4SYSTEM_DATA_FOLDER_USER_ACCESS@@PEAGI_N@Z`
- size: `395`
- prototype: `__int64 __fastcall(void *, __int64, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000ad34`
- `0x18001720c`

## callees

- `0x180002610`
- `0x1800092b8`
- `0x18000a1c8`
- `0x180016180`
- `0x180016314`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001621b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001621b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800161bb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800161bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800162e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800162e1`
- `SHELL32!SHGetKnownFolderPath` at `0x1800161f2`
- `SHELL32!SHGetKnownFolderPath` at `0x1800161f2`

## pseudocode

```c
__int64 __fastcall GetSystemDataFolderForUser(void *a1, __int64 a2, __int64 a3, unsigned __int16 *a4)
{
  int Error; // edi
  int v6; // ebx
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR ppszPath; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v10[264]; // [rsp+50h] [rbp-B0h] BYREF

  *a4 = 0;
  StringSid = 0;
  if ( ConvertSidToStringSidW(a1, &StringSid) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      return (unsigned int)Error;
  }
  ppszPath = 0;
  if ( SHGetKnownFolderPath(&FOLDERID_ProgramData, 0, 0, &ppszPath) >= 0 )
  {
    v6 = StringCchCopyW(v10, 0x104u, ppszPath);
    CoTaskMemFree(ppszPath);
    ppszPath = 0;
    if ( v6 >= 0
      && (int)_AppendPathAndCreateFolder(L"Microsoft\\Windows\\SystemData", StringSid, 0, 0) >= 0
      && (int)_AppendPathAndCreateFolder(StringSid, StringSid, 0, 0) >= 0
      && (int)_AppendPathAndCreateFolder(L"ReadOnly", StringSid, 1, 0) >= 0
      && (int)_AppendPathAndCreateFolder(L"PicturePassword", StringSid, 1, 0) >= 0 )
    {
      StringCchCopyW(a4, 0x104u, v10);
    }
  }
  LocalFree(StringSid);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180016180  mov     [rsp-8+arg_8], rbx
0x180016185  push    rbp
0x180016186  push    rsi
0x180016187  push    rdi
0x180016188  lea     rbp, [rsp-170h]
0x180016190  sub     rsp, 270h
0x180016197  mov     rax, cs:__security_cookie
0x18001619e  xor     rax, rsp
0x1800161a1  mov     [rbp+180h+var_20], rax
0x1800161a8  xor     eax, eax
0x1800161aa  lea     rdx, [rsp+280h+StringSid]; StringSid
0x1800161af  mov     [r9], ax
0x1800161b3  mov     rsi, r9
0x1800161b6  mov     [rsp+280h+StringSid], rax
0x1800161bb  call    cs:__imp_ConvertSidToStringSidW
0x1800161c1  test    eax, eax
0x1800161c3  jz      short loc_1800161C9
0x1800161c5  xor     edi, edi
0x1800161c7  jmp     short loc_1800161D8
0x1800161c9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800161ce  mov     edi, eax
0x1800161d0  test    eax, eax
0x1800161d2  js      loc_1800162E7
0x1800161d8  lea     r9, [rsp+280h+ppszPath]; ppszPath
0x1800161dd  mov     [rsp+280h+ppszPath], 0
0x1800161e6  xor     r8d, r8d; hToken
0x1800161e9  lea     rcx, FOLDERID_ProgramData; rfid
0x1800161f0  xor     edx, edx; dwFlags
0x1800161f2  call    cs:__imp_SHGetKnownFolderPath
0x1800161f8  test    eax, eax
0x1800161fa  js      loc_1800162DC
0x180016200  mov     r8, [rsp+280h+ppszPath]; unsigned __int16 *
0x180016205  lea     rcx, [rsp+280h+var_230]; unsigned __int16 *
0x18001620a  mov     edx, 104h; unsigned __int64
0x18001620f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016214  mov     rcx, [rsp+280h+ppszPath]; pv
0x180016219  mov     ebx, eax
0x18001621b  call    cs:__imp_CoTaskMemFree
0x180016221  mov     [rsp+280h+ppszPath], 0
0x18001622a  test    ebx, ebx
0x18001622c  js      loc_1800162DC
0x180016232  mov     rdx, [rsp+280h+StringSid]
0x180016237  lea     rax, [rsp+280h+var_230]
0x18001623c  xor     r9d, r9d
0x18001623f  mov     [rsp+280h+var_258], rax
0x180016244  xor     r8d, r8d
0x180016247  lea     rcx, aMicrosoftWindo_0; "Microsoft\\Windows\\SystemData"
0x18001624e  call    ?_AppendPathAndCreateFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@_NPEAGI@Z; _AppendPathAndCreateFolder(ushort const *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS,bool,ushort *,uint)
0x180016253  test    eax, eax
0x180016255  js      loc_1800162DC
0x18001625b  mov     rcx, [rsp+280h+StringSid]
0x180016260  lea     rax, [rsp+280h+var_230]
0x180016265  mov     rdx, rcx
0x180016268  mov     [rsp+280h+var_258], rax
0x18001626d  xor     r9d, r9d
0x180016270  xor     r8d, r8d
0x180016273  call    ?_AppendPathAndCreateFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@_NPEAGI@Z; _AppendPathAndCreateFolder(ushort const *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS,bool,ushort *,uint)
0x180016278  test    eax, eax
0x18001627a  js      short loc_1800162DC
0x18001627c  mov     rdx, [rsp+280h+StringSid]
0x180016281  lea     rax, [rsp+280h+var_230]
0x180016286  mov     rcx, cs:off_180020CE0; "ReadOnly"
0x18001628d  xor     r9d, r9d
0x180016290  mov     [rsp+280h+var_258], rax
0x180016295  lea     ebx, [r9+1]
0x180016299  mov     r8d, ebx
0x18001629c  call    ?_AppendPathAndCreateFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@_NPEAGI@Z; _AppendPathAndCreateFolder(ushort const *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS,bool,ushort *,uint)
0x1800162a1  test    eax, eax
0x1800162a3  js      short loc_1800162DC
0x1800162a5  mov     rdx, [rsp+280h+StringSid]
0x1800162aa  lea     rax, [rsp+280h+var_230]
0x1800162af  xor     r9d, r9d
0x1800162b2  mov     [rsp+280h+var_258], rax
0x1800162b7  mov     r8d, ebx
0x1800162ba  lea     rcx, aPicturepasswor_0; "PicturePassword"
0x1800162c1  call    ?_AppendPathAndCreateFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@_NPEAGI@Z; _AppendPathAndCreateFolder(ushort const *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS,bool,ushort *,uint)
0x1800162c6  test    eax, eax
0x1800162c8  js      short loc_1800162DC
0x1800162ca  lea     r8, [rsp+280h+var_230]; unsigned __int16 *
0x1800162cf  mov     edx, 104h; unsigned __int64
0x1800162d4  mov     rcx, rsi; unsigned __int16 *
0x1800162d7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800162dc  mov     rcx, [rsp+280h+StringSid]; hMem
0x1800162e1  call    cs:__imp_LocalFree
0x1800162e7  mov     eax, edi
0x1800162e9  mov     rcx, [rbp+180h+var_20]
0x1800162f0  xor     rcx, rsp; StackCookie
0x1800162f3  call    __security_check_cookie
0x1800162f8  mov     rbx, [rsp+280h+arg_8]
0x180016300  add     rsp, 270h
0x180016307  pop     rdi
0x180016308  pop     rsi
0x180016309  pop     rbp
0x18001630a  retn
```
