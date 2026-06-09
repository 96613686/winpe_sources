# SHDeleteDataFileForUser

- ea: `0x18000855c`
- end: `0x180008684`
- name: `SHDeleteDataFileForUser`
- size: `296`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180006890`
- `0x18000834c`

## callees

- `0x180002230`
- `0x180005830`
- `0x180007ce8`
- `0x180007f18`
- `0x180008108`
- `0x18000855c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008618`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008618`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008642`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000860e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180008638`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000860e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180008638`

## pseudocode

```c
__int64 __fastcall SHDeleteDataFileForUser(const unsigned __int16 *a1, __int64 a2, unsigned int a3)
{
  signed int UserPicturePath; // ebx
  unsigned int v4; // edx
  signed int LastError; // eax
  WCHAR FileName[264]; // [rsp+20h] [rbp-438h] BYREF
  unsigned __int16 v8[264]; // [rsp+230h] [rbp-228h] BYREF

  UserPicturePath = -2147024809;
  if ( a1 )
  {
    UserPicturePath = SHAcctAccountName2DataFileName(a1, v8, a3);
    if ( UserPicturePath >= 0 )
    {
      UserPicturePath = SHAcctGetUserPicturePath(FileName, v4);
      if ( UserPicturePath >= 0 )
      {
        UserPicturePath = StringCchCatW(FileName, 0x104u, L"\\");
        if ( UserPicturePath >= 0 )
        {
          UserPicturePath = StringCchCatW(FileName, 0x104u, v8);
          if ( UserPicturePath >= 0 )
          {
            UserPicturePath = StringCchCatW(FileName, 0x104u, L".dat");
            if ( UserPicturePath >= 0 && !DeleteFileW(FileName) && GetLastError() != 2 )
            {
              UserPicturePath = _TakeDeletePrivilegeOnFile(FileName);
              if ( UserPicturePath >= 0 && !DeleteFileW(FileName) )
              {
                LastError = GetLastError();
                UserPicturePath = LastError;
                if ( LastError > 0 )
                  UserPicturePath = (unsigned __int16)LastError | 0x80070000;
                if ( UserPicturePath >= 0 )
                  return (unsigned int)-2147467259;
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)UserPicturePath;
}

```

## disassembly

```asm
0x18000855c  mov     [rsp+arg_8], rbx
0x180008561  push    rdi
0x180008562  sub     rsp, 450h
0x180008569  mov     rax, cs:__security_cookie
0x180008570  xor     rax, rsp
0x180008573  mov     [rsp+458h+var_18], rax
0x18000857b  mov     ebx, 80070057h
0x180008580  test    rcx, rcx
0x180008583  jz      loc_180008661
0x180008589  lea     rdx, [rsp+458h+var_228]; unsigned __int16 *
0x180008591  call    ?SHAcctAccountName2DataFileName@@YAJPEBGPEAGK@Z; SHAcctAccountName2DataFileName(ushort const *,ushort *,ulong)
0x180008596  mov     ebx, eax
0x180008598  test    eax, eax
0x18000859a  js      loc_180008661
0x1800085a0  lea     rcx, [rsp+458h+FileName]; unsigned __int16 *
0x1800085a5  call    ?SHAcctGetUserPicturePath@@YAJPEAGK@Z; SHAcctGetUserPicturePath(ushort *,ulong)
0x1800085aa  mov     ebx, eax
0x1800085ac  test    eax, eax
0x1800085ae  js      loc_180008661
0x1800085b4  mov     edi, 104h
0x1800085b9  lea     r8, asc_18000BDF8; "\\"
0x1800085c0  mov     edx, edi; unsigned __int64
0x1800085c2  lea     rcx, [rsp+458h+FileName]; unsigned __int16 *
0x1800085c7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800085cc  mov     ebx, eax
0x1800085ce  test    eax, eax
0x1800085d0  js      loc_180008661
0x1800085d6  lea     r8, [rsp+458h+var_228]; unsigned __int16 *
0x1800085de  mov     edx, edi; unsigned __int64
0x1800085e0  lea     rcx, [rsp+458h+FileName]; unsigned __int16 *
0x1800085e5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800085ea  mov     ebx, eax
0x1800085ec  test    eax, eax
0x1800085ee  js      short loc_180008661
0x1800085f0  lea     r8, aDat; ".dat"
0x1800085f7  mov     edx, edi; unsigned __int64
0x1800085f9  lea     rcx, [rsp+458h+FileName]; unsigned __int16 *
0x1800085fe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008603  mov     ebx, eax
0x180008605  test    eax, eax
0x180008607  js      short loc_180008661
0x180008609  lea     rcx, [rsp+458h+FileName]; lpFileName
0x18000860e  call    cs:__imp_DeleteFileW
0x180008614  test    eax, eax
0x180008616  jnz     short loc_180008661
0x180008618  call    cs:__imp_GetLastError
0x18000861e  cmp     eax, 2
0x180008621  jz      short loc_180008661
0x180008623  lea     rcx, [rsp+458h+FileName]; lpFileName
0x180008628  call    ?_TakeDeletePrivilegeOnFile@@YAJPEBG@Z; _TakeDeletePrivilegeOnFile(ushort const *)
0x18000862d  mov     ebx, eax
0x18000862f  test    eax, eax
0x180008631  js      short loc_180008661
0x180008633  lea     rcx, [rsp+458h+FileName]; lpFileName
0x180008638  call    cs:__imp_DeleteFileW
0x18000863e  test    eax, eax
0x180008640  jnz     short loc_180008661
0x180008642  call    cs:__imp_GetLastError
0x180008648  mov     ebx, eax
0x18000864a  test    eax, eax
0x18000864c  jle     short loc_180008657
0x18000864e  movzx   ebx, ax
0x180008651  or      ebx, 80070000h
0x180008657  test    ebx, ebx
0x180008659  mov     eax, 80004005h
0x18000865e  cmovns  ebx, eax
0x180008661  mov     eax, ebx
0x180008663  mov     rcx, [rsp+458h+var_18]
0x18000866b  xor     rcx, rsp; StackCookie
0x18000866e  call    __security_check_cookie
0x180008673  mov     rbx, [rsp+458h+arg_8]
0x18000867b  add     rsp, 450h
0x180008682  pop     rdi
0x180008683  retn
```
