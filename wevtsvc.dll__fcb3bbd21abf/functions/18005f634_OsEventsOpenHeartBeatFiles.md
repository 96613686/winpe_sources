# OsEventsOpenHeartBeatFiles

- ea: `0x18005f634`
- end: `0x18005fc96`
- name: `OsEventsOpenHeartBeatFiles`
- size: `1634`
- prototype: `void()`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path`

## callers

- `0x18005f298`

## callees

- `0x180004a3c`
- `0x180006fb0`
- `0x180017b60`
- `0x18001c320`
- `0x18002de70`
- `0x18003420c`
- `0x18005f634`
- `0x18005fc9c`
- `0x180092008`
- `0x180098c50`
- `0x18009aee0`
- `0x18009b590`
- `0x18009bb88`
- `0x1800c1f64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f7f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f86b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f94c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005faae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fabd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fac8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fbe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fc34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f7f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f86b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f94c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005faae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fabd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fac8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fbe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fc34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f784`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f784`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18005f7c4`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18005f7c4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005f704`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005f8eb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005f9cd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005f704`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005f8eb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005f9cd`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18005f83e`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18005f83e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005f942`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005fa2f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005faa4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005fafd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005f942`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005fa2f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005faa4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005fafd`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void OsEventsOpenHeartBeatFiles()
{
  __int64 v0; // rdi
  HANDLE FileW; // r13
  __int64 v2; // r15
  void *v3; // rcx
  DWORD v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 v7; // rax
  HANDLE v8; // rax
  char *v9; // rdi
  _DWORD *v10; // rbx
  DWORD v11; // esi
  _DWORD *v12; // rax
  _DWORD *v13; // r14
  void *v14; // rcx
  char v15; // al
  char LastError; // al
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v18; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v19; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v20; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v22; // [rsp+70h] [rbp-90h] BYREF
  char *v23; // [rsp+80h] [rbp-80h] BYREF
  __int64 v24; // [rsp+88h] [rbp-78h] BYREF
  int InBuffer; // [rsp+90h] [rbp-70h] BYREF
  __int64 v26; // [rsp+94h] [rbp-6Ch]
  _OWORD v27[2]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD OutBuffer[2]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR szVolumeName[56]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR FileName[80]; // [rsp+150h] [rbp+50h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+1F0h] [rbp+F0h] BYREF

  if ( !g_bHeartBeatsDisabled )
  {
    v0 = (unsigned int)dword_18010F6B0;
    if ( (unsigned int)dword_18010F6B0 < 2 )
    {
      GetNameForHeartBeatFile(lpFileName, (unsigned int)dword_18010F6B0);
      if ( lpFileName[0] == lpFileName[1] )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids,
            (unsigned int)v0);
        }
        goto LABEL_75;
      }
      FileW = CreateFileW(lpFileName[0], 0x40100000u, 0, 0, 4u, 0xA0000006, 0);
      v18 = FileW;
      if ( (unsigned __int64)FileW + 1 <= 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            (unsigned int)WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids,
            lpFileName[0],
            LastError);
        }
        goto LABEL_74;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids,
          lpFileName[0]);
      }
      v18 = 0;
      v2 = 2 * v0;
      v3 = (void *)qword_180111578[2 * v0];
      qword_180111578[2 * v0] = (__int64)FileW;
      if ( (unsigned __int64)v3 + 1 > 1 )
        CloseHandle(v3);
      if ( !LODWORD(qword_180111578[2 * v0 + 1]) )
      {
        LODWORD(qword_180111578[2 * v0 + 1]) = 4096;
        memset_0(szVolumePathName, 0, 0x20Au);
        if ( !GetVolumePathNameW(lpFileName[0], szVolumePathName, 0x105u) )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
          {
            goto LABEL_74;
          }
          v4 = GetLastError();
          v5 = 31;
          goto LABEL_29;
        }
        v6 = -1;
        v7 = -1;
        do
          ++v7;
        while ( szVolumePathName[v7] );
        if ( !(_DWORD)v7 )
          goto LABEL_74;
        memset_0(szVolumeName, 0, 0x64u);
        if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x32u) )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
          {
            goto LABEL_74;
          }
          v4 = GetLastError();
          v5 = 32;
LABEL_29:
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids, v4);
LABEL_74:
          tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v18);
LABEL_75:
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
          return;
        }
        do
          ++v6;
        while ( szVolumeName[v6] );
        if ( !(_DWORD)v6 )
          goto LABEL_74;
        if ( szVolumeName[(unsigned int)(v6 - 1)] == 92 )
        {
          if ( 2 * (unsigned __int64)(unsigned int)(v6 - 1) >= 0x64 )
            _report_rangecheckfailure();
          szVolumeName[(unsigned int)(v6 - 1)] = 0;
        }
        v8 = CreateFileW(szVolumeName, 0, 7u, 0, 3u, 0x2000000u, 0);
        v19 = v8;
        if ( (unsigned __int64)v8 + 1 <= 1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = GetLastError();
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              33,
              (unsigned int)WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids,
              lpFileName[0],
              v15);
          }
          goto LABEL_56;
        }
        BytesReturned = 0;
        memset(OutBuffer, 0, sizeof(OutBuffer));
        if ( !DeviceIoControl(v8, 0x560000u, 0, 0, OutBuffer, 0x20u, &BytesReturned, 0) && GetLastError() != 234 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              34,
              WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids,
              lpFileName[0]);
          }
LABEL_56:
          tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v19);
          goto LABEL_74;
        }
        swprintf_s<80>(FileName, L"\\\\.\\PhysicalDrive%u", DWORD2(OutBuffer[0]));
        v9 = (char *)CreateFileW(FileName, 0, 7u, 0, 3u, 0x2000000u, 0);
        v23 = v9;
        if ( v9 == (char *)-1LL || v9 + 1 == (char *)1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              35,
              WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids,
              lpFileName[0]);
          }
LABEL_55:
          tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v23);
          goto LABEL_56;
        }
        v26 = 0;
        memset(v27, 0, 28);
        InBuffer = 6;
        if ( DeviceIoControl(v9, 0x2D1400u, &InBuffer, 0xCu, v27, 0x1Cu, &BytesReturned, 0) )
        {
          LODWORD(qword_180111578[v2 + 1]) = DWORD1(v27[1]);
        }
        else
        {
          v10 = 0;
          v11 = 40;
          while ( 1 )
          {
            v12 = MIDL_user_allocate(v11);
            v20 = 0;
            v13 = v12;
            utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v20);
            v14 = v10;
            v24 = 0;
            v10 = v13;
            v20 = v13;
            if ( v14 )
              operator delete(v14);
            utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v24);
            if ( DeviceIoControl(v9, 0x700A0u, 0, 0, v13, v11, &BytesReturned, 0) )
              break;
            if ( GetLastError() == 122 )
            {
              v11 *= 2;
            }
            else if ( GetLastError() == 21
                   || GetLastError() != 1
                   || !DeviceIoControl(v9, 0x70000u, 0, 0, v13, 0x18u, &BytesReturned, 0) )
            {
              utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v20);
              goto LABEL_55;
            }
          }
          LODWORD(qword_180111578[v2 + 1]) = v13[5];
          utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v20);
        }
        tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v23);
        tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v19);
      }
      if ( (char *)lpFileName[0] != &v22 )
        operator delete((void *)lpFileName[0]);
    }
  }
}

```

## disassembly

```asm
0x18005f634  push    rbp
0x18005f636  push    rbx
0x18005f637  push    rsi
0x18005f638  push    rdi
0x18005f639  push    r12
0x18005f63b  push    r13
0x18005f63d  push    r14
0x18005f63f  push    r15
0x18005f641  lea     rbp, [rsp-318h]
0x18005f649  sub     rsp, 418h
0x18005f650  mov     rax, cs:__security_cookie
0x18005f657  xor     rax, rsp
0x18005f65a  mov     [rbp+350h+var_50], rax
0x18005f661  xor     r12d, r12d
0x18005f664  cmp     cs:?g_bHeartBeatsDisabled@@3_NA, r12b; bool g_bHeartBeatsDisabled
0x18005f66b  jnz     loc_18005FC73
0x18005f671  mov     edi, cs:dword_18010F6B0
0x18005f677  cmp     edi, 2
0x18005f67a  jnb     loc_18005FC73
0x18005f680  mov     edx, edi
0x18005f682  lea     rcx, [rsp+450h+lpFileName]
0x18005f687  call    GetNameForHeartBeatFile
0x18005f68c  mov     rcx, [rsp+450h+lpFileName]; lpFileName
0x18005f691  cmp     rcx, [rsp+450h+var_3E8]
0x18005f696  jnz     short loc_18005F6E4
0x18005f698  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f69f  lea     rsi, WPP_GLOBAL_Control
0x18005f6a6  cmp     rcx, rsi
0x18005f6a9  jz      loc_18005FC69
0x18005f6af  mov     ebx, 4000h
0x18005f6b4  test    [rcx+1Ch], ebx
0x18005f6b7  jz      loc_18005FC69
0x18005f6bd  cmp     byte ptr [rcx+19h], 2
0x18005f6c1  jb      loc_18005FC69
0x18005f6c7  mov     rcx, [rcx+10h]
0x18005f6cb  lea     edx, [r12+1Ch]
0x18005f6d0  mov     r9d, edi
0x18005f6d3  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x18005f6da  call    WPP_SF_d
0x18005f6df  jmp     loc_18005FC69
0x18005f6e4  mov     [rsp+450h+hTemplateFile], r12; hTemplateFile
0x18005f6e9  xor     r9d, r9d; lpSecurityAttributes
0x18005f6ec  mov     [rsp+450h+dwFlagsAndAttributes], 0A0000006h; dwFlagsAndAttributes
0x18005f6f4  xor     r8d, r8d; dwShareMode
0x18005f6f7  mov     edx, 40100000h; dwDesiredAccess
0x18005f6fc  mov     [rsp+450h+dwCreationDisposition], 4; dwCreationDisposition
0x18005f704  call    cs:__imp_CreateFileW
0x18005f70a  mov     r13, rax
0x18005f70d  mov     [rsp+450h+var_408], rax
0x18005f712  lea     rcx, [rax+1]
0x18005f716  cmp     rcx, 1
0x18005f71a  jbe     loc_18005FC11
0x18005f720  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f727  lea     rsi, WPP_GLOBAL_Control
0x18005f72e  lea     r14, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x18005f735  mov     ebx, 4000h
0x18005f73a  cmp     rcx, rsi
0x18005f73d  jz      short loc_18005F760
0x18005f73f  test    [rcx+1Ch], ebx
0x18005f742  jz      short loc_18005F760
0x18005f744  cmp     byte ptr [rcx+19h], 4
0x18005f748  jb      short loc_18005F760
0x18005f74a  mov     r9, [rsp+450h+lpFileName]
0x18005f74f  mov     edx, 1Eh
0x18005f754  mov     rcx, [rcx+10h]
0x18005f758  mov     r8, r14
0x18005f75b  call    WPP_SF_S
0x18005f760  mov     r15, rdi
0x18005f763  mov     [rsp+450h+var_408], r12
0x18005f768  add     r15, r15
0x18005f76b  lea     rdi, qword_180111578
0x18005f772  mov     rcx, [rdi+r15*8]; hObject
0x18005f776  mov     [rdi+r15*8], r13
0x18005f77a  lea     rax, [rcx+1]
0x18005f77e  cmp     rax, 1
0x18005f782  jbe     short loc_18005F78A
0x18005f784  call    cs:__imp_CloseHandle
0x18005f78a  cmp     [rdi+r15*8+8], r12d
0x18005f78f  jnz     loc_18005FB6B
0x18005f795  xor     edx, edx; Val
0x18005f797  mov     dword ptr [rdi+r15*8+8], 1000h
0x18005f7a0  mov     r8d, 20Ah; Size
0x18005f7a6  lea     rcx, [rbp+350h+szVolumePathName]; void *
0x18005f7ad  call    memset_0
0x18005f7b2  mov     rcx, [rsp+450h+lpFileName]; lpszFileName
0x18005f7b7  lea     rdx, [rbp+350h+szVolumePathName]; lpszVolumePathName
0x18005f7be  mov     r8d, 105h; cchBufferLength
0x18005f7c4  call    cs:__imp_GetVolumePathNameW
0x18005f7ca  test    eax, eax
0x18005f7cc  jnz     short loc_18005F7FE
0x18005f7ce  mov     rax, cs:WPP_GLOBAL_Control
0x18005f7d5  cmp     rax, rsi
0x18005f7d8  jz      loc_18005FC5F
0x18005f7de  test    [rax+1Ch], ebx
0x18005f7e1  jz      loc_18005FC5F
0x18005f7e7  cmp     byte ptr [rax+19h], 3
0x18005f7eb  jb      loc_18005FC5F
0x18005f7f1  call    cs:__imp_GetLastError
0x18005f7f7  mov     edx, 1Fh
0x18005f7fc  jmp     short loc_18005F876
0x18005f7fe  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005f802  lea     rcx, [rbp+350h+szVolumePathName]
0x18005f809  mov     rax, rdi
0x18005f80c  inc     rax
0x18005f80f  cmp     [rcx+rax*2], r12w
0x18005f814  jnz     short loc_18005F80C
0x18005f816  test    eax, eax
0x18005f818  jz      loc_18005FC5F
0x18005f81e  xor     edx, edx; Val
0x18005f820  lea     rcx, [rbp+350h+szVolumeName]; void *
0x18005f824  lea     r8d, [rdx+64h]; Size
0x18005f828  call    memset_0
0x18005f82d  mov     r8d, 32h ; '2'; cchBufferLength
0x18005f833  lea     rdx, [rbp+350h+szVolumeName]; lpszVolumeName
0x18005f837  lea     rcx, [rbp+350h+szVolumePathName]; lpszVolumeMountPoint
0x18005f83e  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18005f844  test    eax, eax
0x18005f846  jnz     short loc_18005F891
0x18005f848  mov     rax, cs:WPP_GLOBAL_Control
0x18005f84f  cmp     rax, rsi
0x18005f852  jz      loc_18005FC5F
0x18005f858  test    [rax+1Ch], ebx
0x18005f85b  jz      loc_18005FC5F
0x18005f861  cmp     byte ptr [rax+19h], 3
0x18005f865  jb      loc_18005FC5F
0x18005f86b  call    cs:__imp_GetLastError
0x18005f871  mov     edx, 20h ; ' '
0x18005f876  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f87d  mov     r9d, eax
0x18005f880  mov     r8, r14
0x18005f883  mov     rcx, [rcx+10h]
0x18005f887  call    WPP_SF_d
0x18005f88c  jmp     loc_18005FC5F
0x18005f891  lea     rax, [rbp+350h+szVolumeName]
0x18005f895  inc     rdi
0x18005f898  cmp     [rax+rdi*2], r12w
0x18005f89d  jnz     short loc_18005F895
0x18005f89f  test    edi, edi
0x18005f8a1  jz      loc_18005FC5F
0x18005f8a7  lea     ecx, [rdi-1]
0x18005f8aa  add     rcx, rcx
0x18005f8ad  cmp     [rbp+rcx+350h+szVolumeName], 5Ch ; '\'
0x18005f8b3  jnz     short loc_18005F8C5
0x18005f8b5  cmp     rcx, 64h ; 'd'
0x18005f8b9  jnb     loc_18005F996
0x18005f8bf  mov     [rbp+rcx+350h+szVolumeName], r12w
0x18005f8c5  xor     r9d, r9d; lpSecurityAttributes
0x18005f8c8  mov     [rsp+450h+hTemplateFile], r12; hTemplateFile
0x18005f8cd  mov     edi, 2000000h
0x18005f8d2  lea     rcx, [rbp+350h+szVolumeName]; lpFileName
0x18005f8d6  mov     [rsp+450h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x18005f8da  xor     edx, edx; dwDesiredAccess
0x18005f8dc  mov     [rsp+450h+dwCreationDisposition], 3; dwCreationDisposition
0x18005f8e4  lea     r13d, [r9+7]
0x18005f8e8  mov     r8d, r13d; dwShareMode
0x18005f8eb  call    cs:__imp_CreateFileW
0x18005f8f1  mov     [rsp+450h+var_400], rax
0x18005f8f6  lea     rcx, [rax+1]
0x18005f8fa  cmp     rcx, 1
0x18005f8fe  jbe     loc_18005FBC2
0x18005f904  mov     [rsp+450h+lpOverlapped], r12; lpOverlapped
0x18005f909  lea     rcx, [rsp+450h+BytesReturned]
0x18005f90e  mov     [rsp+450h+hTemplateFile], rcx; lpBytesReturned
0x18005f913  xorps   xmm0, xmm0
0x18005f916  lea     rcx, [rbp+350h+OutBuffer]
0x18005f91a  mov     [rsp+450h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x18005f922  mov     qword ptr [rsp+450h+dwCreationDisposition], rcx; lpOutBuffer
0x18005f927  xor     r9d, r9d; nInBufferSize
0x18005f92a  mov     rcx, rax; hDevice
0x18005f92d  mov     [rsp+450h+BytesReturned], r12d
0x18005f932  xor     r8d, r8d; lpInBuffer
0x18005f935  mov     edx, 560000h; dwIoControlCode
0x18005f93a  movups  [rbp+350h+OutBuffer], xmm0
0x18005f93e  movups  [rbp+350h+var_380], xmm0
0x18005f942  call    cs:__imp_DeviceIoControl
0x18005f948  test    eax, eax
0x18005f94a  jnz     short loc_18005F99C
0x18005f94c  call    cs:__imp_GetLastError
0x18005f952  cmp     eax, 0EAh
0x18005f957  jz      short loc_18005F99C
0x18005f959  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f960  cmp     rcx, rsi
0x18005f963  jz      loc_18005FB1E
0x18005f969  test    [rcx+1Ch], ebx
0x18005f96c  jz      loc_18005FB1E
0x18005f972  cmp     byte ptr [rcx+19h], 2
0x18005f976  jb      loc_18005FB1E
0x18005f97c  mov     r9, [rsp+450h+lpFileName]
0x18005f981  lea     edx, [r13+1Bh]
0x18005f985  mov     rcx, [rcx+10h]
0x18005f989  mov     r8, r14
0x18005f98c  call    WPP_SF_S
0x18005f991  jmp     loc_18005FB1E
0x18005f996  call    __report_rangecheckfailure
0x18005f99c  mov     r8d, dword ptr [rbp+350h+OutBuffer+8]
0x18005f9a0  lea     rdx, aPhysicaldriveU; "\\\\.\\PhysicalDrive%u"
0x18005f9a7  lea     rcx, [rbp+350h+FileName]
0x18005f9ab  call    ??$swprintf_s@$0FA@@@YAHAEAY0FA@_WPEB_WZZ; swprintf_s<80>(wchar_t (&)[80],wchar_t const *,...)
0x18005f9b0  mov     [rsp+450h+hTemplateFile], r12; hTemplateFile
0x18005f9b5  lea     rcx, [rbp+350h+FileName]; lpFileName
0x18005f9b9  mov     [rsp+450h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x18005f9bd  xor     r9d, r9d; lpSecurityAttributes
0x18005f9c0  mov     r8d, r13d; dwShareMode
0x18005f9c3  mov     [rsp+450h+dwCreationDisposition], 3; dwCreationDisposition
0x18005f9cb  xor     edx, edx; dwDesiredAccess
0x18005f9cd  call    cs:__imp_CreateFileW
0x18005f9d3  mov     rdi, rax
0x18005f9d6  mov     [rbp+350h+var_3D0], rax
0x18005f9da  inc     rax
0x18005f9dd  cmp     rax, 1
0x18005f9e1  jbe     loc_18005FB88
0x18005f9e7  mov     [rsp+450h+lpOverlapped], r12; lpOverlapped
0x18005f9ec  lea     rax, [rsp+450h+BytesReturned]
0x18005f9f1  mov     [rsp+450h+hTemplateFile], rax; lpBytesReturned
0x18005f9f6  lea     r8, [rbp+350h+InBuffer]; lpInBuffer
0x18005f9fa  xorps   xmm0, xmm0
0x18005f9fd  mov     [rsp+450h+dwFlagsAndAttributes], 1Ch; nOutBufferSize
0x18005fa05  lea     rax, [rbp+350h+var_3B0]
0x18005fa09  mov     [rbp+350h+var_3BC], r12
0x18005fa0d  movups  [rbp+350h+var_3B0], xmm0
0x18005fa11  mov     r9d, 0Ch; nInBufferSize
0x18005fa17  mov     qword ptr [rsp+450h+dwCreationDisposition], rax; lpOutBuffer
0x18005fa1c  mov     edx, 2D1400h; dwIoControlCode
0x18005fa21  mov     [rbp+350h+InBuffer], 6
0x18005fa28  mov     rcx, rdi; hDevice
0x18005fa2b  movups  [rbp+350h+var_3B0+0Ch], xmm0
0x18005fa2f  call    cs:__imp_DeviceIoControl
0x18005fa35  test    eax, eax
0x18005fa37  jnz     loc_18005FB49
0x18005fa3d  mov     rbx, r12
0x18005fa40  lea     esi, [rax+28h]
0x18005fa43  mov     ecx, esi; size
0x18005fa45  call    MIDL_user_allocate
0x18005fa4a  lea     rcx, [rsp+450h+var_3F8]
0x18005fa4f  mov     [rsp+450h+var_3F8], r12
0x18005fa54  mov     r14, rax
0x18005fa57  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@utl@@@utl@@QEAA@XZ; utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(void)
0x18005fa5c  mov     rcx, rbx; void *
0x18005fa5f  mov     [rbp+350h+var_3C8], r12
0x18005fa63  mov     rbx, r14
0x18005fa66  mov     [rsp+450h+var_3F8], rbx
0x18005fa6b  test    rcx, rcx
0x18005fa6e  jz      short loc_18005FA75
0x18005fa70  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005fa75  lea     rcx, [rbp+350h+var_3C8]
0x18005fa79  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@utl@@@utl@@QEAA@XZ; utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(void)
0x18005fa7e  mov     [rsp+450h+lpOverlapped], r12; lpOverlapped
0x18005fa83  lea     rax, [rsp+450h+BytesReturned]
0x18005fa88  mov     [rsp+450h+hTemplateFile], rax; lpBytesReturned
0x18005fa8d  xor     r9d, r9d; nInBufferSize
0x18005fa90  mov     [rsp+450h+dwFlagsAndAttributes], esi; nOutBufferSize
0x18005fa94  xor     r8d, r8d; lpInBuffer
0x18005fa97  mov     edx, 700A0h; dwIoControlCode
0x18005fa9c  mov     qword ptr [rsp+450h+dwCreationDisposition], r14; lpOutBuffer
0x18005faa1  mov     rcx, rdi; hDevice
0x18005faa4  call    cs:__imp_DeviceIoControl
0x18005faaa  test    eax, eax
0x18005faac  jnz     short loc_18005FB2D
0x18005faae  call    cs:__imp_GetLastError
0x18005fab4  cmp     eax, 7Ah ; 'z'
0x18005fab7  jnz     short loc_18005FABD
0x18005fab9  add     esi, esi
0x18005fabb  jmp     short loc_18005FA43
0x18005fabd  call    cs:__imp_GetLastError
0x18005fac3  cmp     eax, 15h
0x18005fac6  jz      short loc_18005FB0B
0x18005fac8  call    cs:__imp_GetLastError
0x18005face  cmp     eax, 1
0x18005fad1  jnz     short loc_18005FB0B
0x18005fad3  mov     [rsp+450h+lpOverlapped], r12; lpOverlapped
0x18005fad8  lea     rax, [rsp+450h+BytesReturned]
0x18005fadd  mov     [rsp+450h+hTemplateFile], rax; lpBytesReturned
0x18005fae2  xor     r9d, r9d; nInBufferSize
0x18005fae5  mov     [rsp+450h+dwFlagsAndAttributes], 18h; nOutBufferSize
0x18005faed  xor     r8d, r8d; lpInBuffer
0x18005faf0  mov     edx, 70000h; dwIoControlCode
0x18005faf5  mov     qword ptr [rsp+450h+dwCreationDisposition], r14; lpOutBuffer
0x18005fafa  mov     rcx, rdi; hDevice
0x18005fafd  call    cs:__imp_DeviceIoControl
0x18005fb03  test    eax, eax
0x18005fb05  jnz     loc_18005FA43
0x18005fb0b  lea     rcx, [rsp+450h+var_3F8]
0x18005fb10  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@utl@@@utl@@QEAA@XZ; utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(void)
0x18005fb15  lea     rcx, [rbp+350h+var_3D0]
0x18005fb19  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18005fb1e  lea     rcx, [rsp+450h+var_400]
0x18005fb23  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18005fb28  jmp     loc_18005FC5F
0x18005fb2d  mov     eax, [r14+14h]
0x18005fb31  lea     rcx, qword_180111578
0x18005fb38  mov     [rcx+r15*8+8], eax
0x18005fb3d  lea     rcx, [rsp+450h+var_3F8]
0x18005fb42  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@utl@@@utl@@QEAA@XZ; utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(void)
0x18005fb47  jmp     short loc_18005FB58
0x18005fb49  mov     eax, [rbp+350h+var_39C]
0x18005fb4c  lea     rcx, qword_180111578
0x18005fb53  mov     [rcx+r15*8+8], eax
0x18005fb58  lea     rcx, [rbp+350h+var_3D0]
0x18005fb5c  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18005fb61  lea     rcx, [rsp+450h+var_400]
  ... truncated ...
```
