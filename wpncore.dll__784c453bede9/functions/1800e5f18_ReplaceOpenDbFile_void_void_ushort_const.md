# ReplaceOpenDbFile(void *,void *,ushort const *)

- ea: `0x1800e5f18`
- end: `0x1800e61ec`
- name: `?ReplaceOpenDbFile@@YAJPEAX0PEBG@Z`
- size: `724`
- prototype: `__int64 __fastcall(HANDLE hFile, HANDLE, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800e55d0`

## callees

- `0x18002ee38`
- `0x1800516d0`
- `0x180061800`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x1800e5e04`
- `0x1800e5f18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e616d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e616d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800e6163`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800e6163`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800e5f57`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800e5f57`

## string_xrefs

- `0x1800e5f4d`: `MIGTemp`

## pseudocode

```c
__int64 __fastcall ReplaceOpenDbFile(HANDLE hFile, HANDLE a2, const unsigned __int16 *a3)
{
  signed int v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  int v10; // eax
  int v11; // eax
  unsigned __int64 v12; // r11
  int v13; // eax
  int v14; // eax
  signed int LastError; // eax
  int FileInformation[4]; // [rsp+20h] [rbp-458h] BYREF
  unsigned __int16 Src[264]; // [rsp+30h] [rbp-448h] BYREF
  WCHAR TempFileName[264]; // [rsp+240h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+478h] [rbp+0h]

  if ( GetTempFileNameW(a3, L"MIGTemp", 0, TempFileName) )
  {
    v10 = RenameOpenFile(hFile, TempFileName);
    v7 = v10;
    if ( v10 >= 0 )
    {
      v11 = StringCchCopyW(Src, 0x104u, a3);
      v7 = v11;
      if ( v11 >= 0 )
      {
        v13 = StringCchCatW(Src, v12, L"\\appdb.dat");
        v7 = v13;
        if ( v13 >= 0 )
        {
          v14 = RenameOpenFile(a2, Src);
          v7 = v14;
          if ( v14 >= 0 )
          {
            LOBYTE(FileInformation[0]) = 1;
            if ( SetFileInformationByHandle(hFile, FileDispositionInfo, FileInformation, 1u) )
              return 0;
            LastError = GetLastError();
            v7 = LastError;
            if ( LastError > 0 )
              v7 = (unsigned __int16)LastError | 0x80070000;
            if ( (v7 & 0x80000000) != 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x698,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\persistencemanager.cpp",
                (const char *)v7,
                FileInformation[0]);
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
              {
                v9 = 48;
                goto LABEL_9;
              }
            }
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x694,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\persistencemanager.cpp",
              (const char *)(unsigned int)v14,
              FileInformation[0]);
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            {
              v9 = 47;
              goto LABEL_9;
            }
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x691,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\persistencemanager.cpp",
            (const char *)(unsigned int)v13,
            FileInformation[0]);
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v9 = 46;
            goto LABEL_9;
          }
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x68E,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\persistencemanager.cpp",
          (const char *)(unsigned int)v11,
          FileInformation[0]);
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v9 = 45;
          goto LABEL_9;
        }
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x689,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\persistencemanager.cpp",
        (const char *)(unsigned int)v10,
        FileInformation[0]);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v9 = 44;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( (v7 & 0x80000000) != 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x684,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\persistencemanager.cpp",
        (const char *)v7,
        FileInformation[0]);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v9 = 43;
LABEL_9:
      WPP_SF_d(v8[2], v9, WPP_ac3d69826ca03a16ae3e9918ed4e7821_Traceguids, v7);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800e5f18  mov     [rsp+arg_18], rbx
0x1800e5f1d  push    rbp
0x1800e5f1e  push    rsi
0x1800e5f1f  push    rdi
0x1800e5f20  sub     rsp, 460h
0x1800e5f27  mov     rax, cs:__security_cookie
0x1800e5f2e  xor     rax, rsp
0x1800e5f31  mov     [rsp+478h+var_28], rax
0x1800e5f39  mov     rsi, r8
0x1800e5f3c  lea     r9, [rsp+478h+TempFileName]; lpTempFileName
0x1800e5f44  mov     rbp, rdx
0x1800e5f47  mov     rdi, rcx
0x1800e5f4a  mov     rcx, rsi; lpPathName
0x1800e5f4d  lea     rdx, aMigtemp; "MIGTemp"
0x1800e5f54  xor     r8d, r8d; uUnique
0x1800e5f57  call    cs:__imp_GetTempFileNameW
0x1800e5f5d  test    eax, eax
0x1800e5f5f  jnz     short loc_1800E5FD4
0x1800e5f61  call    cs:__imp_GetLastError
0x1800e5f67  mov     ebx, eax
0x1800e5f69  test    eax, eax
0x1800e5f6b  jle     short loc_1800E5F76
0x1800e5f6d  movzx   ebx, ax
0x1800e5f70  or      ebx, 80070000h
0x1800e5f76  test    ebx, ebx
0x1800e5f78  jns     short loc_1800E5F96
0x1800e5f7a  mov     rcx, [rsp+478h]; this
0x1800e5f82  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800e5f89  mov     r9d, ebx; char *
0x1800e5f8c  mov     edx, 684h; void *
0x1800e5f91  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e5f96  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5f9d  lea     rax, WPP_GLOBAL_Control
0x1800e5fa4  cmp     rcx, rax
0x1800e5fa7  jz      loc_1800E61C7
0x1800e5fad  test    byte ptr [rcx+1Ch], 80h
0x1800e5fb1  jz      loc_1800E61C7
0x1800e5fb7  mov     edx, 2Bh ; '+'
0x1800e5fbc  mov     rcx, [rcx+10h]
0x1800e5fc0  lea     r8, WPP_ac3d69826ca03a16ae3e9918ed4e7821_Traceguids
0x1800e5fc7  mov     r9d, ebx
0x1800e5fca  call    WPP_SF_d
0x1800e5fcf  jmp     loc_1800E61C7
0x1800e5fd4  lea     rdx, [rsp+478h+TempFileName]; Src
0x1800e5fdc  mov     rcx, rdi; hFile
0x1800e5fdf  call    ?RenameOpenFile@@YAJPEAXPEBG@Z; RenameOpenFile(void *,ushort const *)
0x1800e5fe4  mov     ebx, eax
0x1800e5fe6  test    eax, eax
0x1800e5fe8  jns     short loc_1800E602E
0x1800e5fea  mov     rcx, [rsp+478h]; this
0x1800e5ff2  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800e5ff9  mov     r9d, eax; char *
0x1800e5ffc  mov     edx, 689h; void *
0x1800e6001  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e6006  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e600d  lea     rax, WPP_GLOBAL_Control
0x1800e6014  cmp     rcx, rax
0x1800e6017  jz      loc_1800E61C7
0x1800e601d  test    byte ptr [rcx+1Ch], 80h
0x1800e6021  jz      loc_1800E61C7
0x1800e6027  mov     edx, 2Ch ; ','
0x1800e602c  jmp     short loc_1800E5FBC
0x1800e602e  mov     r11d, 104h
0x1800e6034  lea     rcx, [rsp+478h+Src]; unsigned __int16 *
0x1800e6039  mov     edx, r11d; unsigned __int64
0x1800e603c  mov     r8, rsi; unsigned __int16 *
0x1800e603f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800e6044  mov     ebx, eax
0x1800e6046  test    eax, eax
0x1800e6048  jns     short loc_1800E6091
0x1800e604a  mov     rcx, [rsp+478h]; this
0x1800e6052  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800e6059  mov     r9d, eax; char *
0x1800e605c  mov     edx, 68Eh; void *
0x1800e6061  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e6066  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e606d  lea     rax, WPP_GLOBAL_Control
0x1800e6074  cmp     rcx, rax
0x1800e6077  jz      loc_1800E61C7
0x1800e607d  test    byte ptr [rcx+1Ch], 80h
0x1800e6081  jz      loc_1800E61C7
0x1800e6087  mov     edx, 2Dh ; '-'
0x1800e608c  jmp     loc_1800E5FBC
0x1800e6091  lea     r8, aAppdbDat; "\\appdb.dat"
0x1800e6098  mov     rdx, r11; unsigned __int64
0x1800e609b  lea     rcx, [rsp+478h+Src]; unsigned __int16 *
0x1800e60a0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800e60a5  mov     ebx, eax
0x1800e60a7  test    eax, eax
0x1800e60a9  jns     short loc_1800E60F2
0x1800e60ab  mov     rcx, [rsp+478h]; this
0x1800e60b3  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800e60ba  mov     r9d, eax; char *
0x1800e60bd  mov     edx, 691h; void *
0x1800e60c2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e60c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e60ce  lea     rax, WPP_GLOBAL_Control
0x1800e60d5  cmp     rcx, rax
0x1800e60d8  jz      loc_1800E61C7
0x1800e60de  test    byte ptr [rcx+1Ch], 80h
0x1800e60e2  jz      loc_1800E61C7
0x1800e60e8  mov     edx, 2Eh ; '.'
0x1800e60ed  jmp     loc_1800E5FBC
0x1800e60f2  lea     rdx, [rsp+478h+Src]; Src
0x1800e60f7  mov     rcx, rbp; hFile
0x1800e60fa  call    ?RenameOpenFile@@YAJPEAXPEBG@Z; RenameOpenFile(void *,ushort const *)
0x1800e60ff  mov     ebx, eax
0x1800e6101  test    eax, eax
0x1800e6103  jns     short loc_1800E614C
0x1800e6105  mov     rcx, [rsp+478h]; this
0x1800e610d  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800e6114  mov     r9d, eax; char *
0x1800e6117  mov     edx, 694h; void *
0x1800e611c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e6121  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6128  lea     rax, WPP_GLOBAL_Control
0x1800e612f  cmp     rcx, rax
0x1800e6132  jz      loc_1800E61C7
0x1800e6138  test    byte ptr [rcx+1Ch], 80h
0x1800e613c  jz      loc_1800E61C7
0x1800e6142  mov     edx, 2Fh ; '/'
0x1800e6147  jmp     loc_1800E5FBC
0x1800e614c  mov     r9d, 1; dwBufferSize
0x1800e6152  mov     byte ptr [rsp+478h+FileInformation], 1; int
0x1800e6157  lea     r8, [rsp+478h+FileInformation]; lpFileInformation
0x1800e615c  mov     rcx, rdi; hFile
0x1800e615f  lea     edx, [r9+3]; FileInformationClass
0x1800e6163  call    cs:__imp_SetFileInformationByHandle
0x1800e6169  test    eax, eax
0x1800e616b  jnz     short loc_1800E61C5
0x1800e616d  call    cs:__imp_GetLastError
0x1800e6173  mov     ebx, eax
0x1800e6175  test    eax, eax
0x1800e6177  jle     short loc_1800E6182
0x1800e6179  movzx   ebx, ax
0x1800e617c  or      ebx, 80070000h
0x1800e6182  test    ebx, ebx
0x1800e6184  jns     short loc_1800E61C7
0x1800e6186  mov     rcx, [rsp+478h]; this
0x1800e618e  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800e6195  mov     r9d, ebx; char *
0x1800e6198  mov     edx, 698h; void *
0x1800e619d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e61a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e61a9  lea     rax, WPP_GLOBAL_Control
0x1800e61b0  cmp     rcx, rax
0x1800e61b3  jz      short loc_1800E61C7
0x1800e61b5  test    byte ptr [rcx+1Ch], 80h
0x1800e61b9  jz      short loc_1800E61C7
0x1800e61bb  mov     edx, 30h ; '0'
0x1800e61c0  jmp     loc_1800E5FBC
0x1800e61c5  xor     ebx, ebx
0x1800e61c7  mov     eax, ebx
0x1800e61c9  mov     rcx, [rsp+478h+var_28]
0x1800e61d1  xor     rcx, rsp; StackCookie
0x1800e61d4  call    __security_check_cookie
0x1800e61d9  mov     rbx, [rsp+478h+arg_18]
0x1800e61e1  add     rsp, 460h
0x1800e61e8  pop     rdi
0x1800e61e9  pop     rsi
0x1800e61ea  pop     rbp
0x1800e61eb  retn
```
