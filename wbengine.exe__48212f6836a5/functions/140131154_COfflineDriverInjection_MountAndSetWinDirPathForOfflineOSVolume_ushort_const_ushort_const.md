# COfflineDriverInjection::MountAndSetWinDirPathForOfflineOSVolume(ushort const *,ushort const *)

- ea: `0x140131154`
- end: `0x140131413`
- name: `?MountAndSetWinDirPathForOfflineOSVolume@COfflineDriverInjection@@CAJPEBG0@Z`
- size: `703`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, service_task`

## callers

- `0x140130e1c`

## callees

- `0x1400063b4`
- `0x14000bb24`
- `0x14008863c`
- `0x1400889f0`
- `0x140131154`

## import_xrefs

- `KERNEL32!SetVolumeMountPointW` at `0x140131365`
- `KERNEL32!SetVolumeMountPointW` at `0x140131365`
- `KERNEL32!GetLogicalDrives` at `0x1401311ba`
- `KERNEL32!GetLogicalDrives` at `0x1401311ba`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14013123f`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14013129c`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14013123f`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14013129c`
- `KERNEL32!GetLastError` at `0x1401311c7`
- `KERNEL32!GetLastError` at `0x140131249`
- `KERNEL32!GetLastError` at `0x1401312a6`
- `KERNEL32!GetLastError` at `0x1401311c7`
- `KERNEL32!GetLastError` at `0x140131249`
- `KERNEL32!GetLastError` at `0x1401312a6`
- `ole32!CoTaskMemAlloc` at `0x140131274`
- `ole32!CoTaskMemAlloc` at `0x1401312db`
- `ole32!CoTaskMemAlloc` at `0x140131274`
- `ole32!CoTaskMemAlloc` at `0x1401312db`
- `ole32!CoTaskMemFree` at `0x140131311`
- `ole32!CoTaskMemFree` at `0x14013137f`
- `ole32!CoTaskMemFree` at `0x1401313a3`
- `ole32!CoTaskMemFree` at `0x1401313b1`
- `ole32!CoTaskMemFree` at `0x1401313bf`
- `ole32!CoTaskMemFree` at `0x140131311`
- `ole32!CoTaskMemFree` at `0x14013137f`
- `ole32!CoTaskMemFree` at `0x1401313a3`
- `ole32!CoTaskMemFree` at `0x1401313b1`
- `ole32!CoTaskMemFree` at `0x1401313bf`

## pseudocode

```c
__int64 __fastcall COfflineDriverInjection::MountAndSetWinDirPathForOfflineOSVolume(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2)
{
  unsigned __int16 *v3; // rsi
  DWORD LogicalDrives; // r12d
  signed int LastError; // eax
  int v7; // ebx
  __int64 v8; // rdi
  __int64 v9; // rax
  int appended; // eax
  WCHAR *v11; // r14
  signed int v12; // eax
  WCHAR *v13; // rax
  WCHAR *v14; // r15
  signed int v15; // eax
  unsigned __int16 *v16; // rax
  void *v17; // r11
  int v18; // ecx
  unsigned int i; // eax
  int v20; // eax
  DWORD v22; // [rsp+20h] [rbp-20h] BYREF
  LPCWSTR lpszVolumeName; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int16 *v24; // [rsp+30h] [rbp-10h] BYREF
  DWORD cchReturnLength; // [rsp+90h] [rbp+50h] BYREF
  unsigned __int16 v26; // [rsp+98h] [rbp+58h] BYREF
  __int16 v27; // [rsp+9Ah] [rbp+5Ah]

  v3 = 0;
  v24 = 0;
  lpszVolumeName = 0;
  cchReturnLength = 0;
  v22 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_d3373a8c9910345b1e2264c86067e59a_Traceguids);
  }
  LogicalDrives = GetLogicalDrives();
  if ( !LogicalDrives )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_44;
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( a1[v9] );
  if ( a1[(unsigned int)(v9 - 1)] == 92 )
    appended = BlbutilDuplicateString(a1, (unsigned __int16 **)&lpszVolumeName, 0);
  else
    appended = BlbutilAppendString(a1, L"\\", (unsigned __int16 **)&lpszVolumeName);
  v11 = (WCHAR *)lpszVolumeName;
  v7 = appended;
  if ( appended >= 0 )
  {
    v26 = 0;
    if ( !GetVolumePathNamesForVolumeNameW(lpszVolumeName, 0, 0, &cchReturnLength) )
    {
      v12 = GetLastError();
      v7 = v12;
      if ( v12 != 234 )
      {
        if ( v12 > 0 )
          v7 = (unsigned __int16)v12 | 0x80070000;
        goto LABEL_40;
      }
    }
    v13 = (WCHAR *)CoTaskMemAlloc(2LL * cchReturnLength);
    v14 = v13;
    if ( !v13 )
    {
      v7 = -2147024882;
      goto LABEL_40;
    }
    if ( !GetVolumePathNamesForVolumeNameW(v11, v13, cchReturnLength, &v22) )
      goto LABEL_21;
    do
      ++v8;
    while ( v14[v8] );
    if ( (_DWORD)v8 )
    {
      v16 = (unsigned __int16 *)CoTaskMemAlloc(2LL * (unsigned int)(v8 + 1));
      if ( !v16 )
      {
        v7 = -2147024882;
LABEL_39:
        CoTaskMemFree(v14);
        goto LABEL_40;
      }
      v7 = StringCchCopyW(v16, (unsigned int)(v8 + 1), v14);
      if ( v7 < 0 )
      {
        CoTaskMemFree(v17);
        goto LABEL_39;
      }
      v3 = (unsigned __int16 *)v17;
    }
    else
    {
      v18 = 1;
      for ( i = 0; i < 0x1A; ++i )
      {
        if ( (v18 & LogicalDrives) == 0 )
        {
          v27 = 0;
          v26 = i + 65;
          v20 = BlbutilAppendString(&v26, L":\\", &v24);
          v3 = v24;
          v7 = v20;
          if ( v20 < 0 )
            goto LABEL_39;
          break;
        }
        v18 *= 2;
      }
      if ( !SetVolumeMountPointW(v3, v11) )
      {
LABEL_21:
        v15 = GetLastError();
        v7 = v15;
        if ( v15 > 0 )
          v7 = (unsigned __int16)v15 | 0x80070000;
        goto LABEL_39;
      }
    }
    if ( COfflineDriverInjection::s_pwszWindowsDirectoryPathForOfflineOS )
      CoTaskMemFree(COfflineDriverInjection::s_pwszWindowsDirectoryPathForOfflineOS);
    COfflineDriverInjection::s_pwszWindowsDirectoryPathForOfflineOS = 0;
    v7 = BlbutilAppendString(v3, a2, &COfflineDriverInjection::s_pwszWindowsDirectoryPathForOfflineOS);
    goto LABEL_39;
  }
LABEL_40:
  if ( v11 )
    CoTaskMemFree(v11);
  if ( v3 )
    CoTaskMemFree(v3);
LABEL_44:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_d3373a8c9910345b1e2264c86067e59a_Traceguids);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140131154  mov     [rsp-38h+arg_0], rbx
0x140131159  push    rbp
0x14013115a  push    rsi
0x14013115b  push    rdi
0x14013115c  push    r12
0x14013115e  push    r13
0x140131160  push    r14
0x140131162  push    r15
0x140131164  mov     rbp, rsp
0x140131167  sub     rsp, 40h
0x14013116b  xor     r15d, r15d
0x14013116e  mov     r13, rdx
0x140131171  mov     esi, r15d
0x140131174  mov     [rbp+var_10], r15
0x140131178  mov     [rbp+lpszVolumeName], r15
0x14013117c  mov     rbx, rcx
0x14013117f  mov     [rbp+cchReturnLength], r15d
0x140131183  mov     [rbp+var_20], r15d
0x140131187  mov     rcx, cs:WPP_GLOBAL_Control
0x14013118e  lea     rax, WPP_GLOBAL_Control
0x140131195  cmp     rcx, rax
0x140131198  jz      short loc_1401311BA
0x14013119a  test    byte ptr [rcx+1Ch], 20h
0x14013119e  jz      short loc_1401311BA
0x1401311a0  cmp     byte ptr [rcx+19h], 4
0x1401311a4  jb      short loc_1401311BA
0x1401311a6  mov     rcx, [rcx+10h]
0x1401311aa  lea     edx, [r15+16h]
0x1401311ae  lea     r8, WPP_d3373a8c9910345b1e2264c86067e59a_Traceguids
0x1401311b5  call    WPP_SF_
0x1401311ba  call    cs:__imp_GetLogicalDrives
0x1401311c0  mov     r12d, eax
0x1401311c3  test    eax, eax
0x1401311c5  jnz     short loc_1401311E5
0x1401311c7  call    cs:__imp_GetLastError
0x1401311cd  mov     ebx, eax
0x1401311cf  test    eax, eax
0x1401311d1  jle     loc_1401313C5
0x1401311d7  movzx   ebx, ax
0x1401311da  or      ebx, 80070000h
0x1401311e0  jmp     loc_1401313C5
0x1401311e5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1401311e9  mov     rax, rdi
0x1401311ec  inc     rax
0x1401311ef  cmp     [rbx+rax*2], r15w
0x1401311f4  jnz     short loc_1401311EC
0x1401311f6  dec     eax
0x1401311f8  mov     rcx, rbx; unsigned __int16 *
0x1401311fb  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x140131200  jz      short loc_140131214
0x140131202  lea     r8, [rbp+lpszVolumeName]; unsigned __int16 **
0x140131206  lea     rdx, asc_14013C090; "\\"
0x14013120d  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x140131212  jmp     short loc_140131220
0x140131214  xor     r8d, r8d; unsigned __int64
0x140131217  lea     rdx, [rbp+lpszVolumeName]; unsigned __int16 **
0x14013121b  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140131220  mov     r14, [rbp+lpszVolumeName]
0x140131224  mov     ebx, eax
0x140131226  test    eax, eax
0x140131228  js      loc_1401313A9
0x14013122e  lea     r9, [rbp+cchReturnLength]; lpcchReturnLength
0x140131232  mov     [rbp+arg_18], r15w
0x140131237  xor     r8d, r8d; cchBufferLength
0x14013123a  xor     edx, edx; lpszVolumePathNames
0x14013123c  mov     rcx, r14; lpszVolumeName
0x14013123f  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x140131245  test    eax, eax
0x140131247  jnz     short loc_14013126E
0x140131249  call    cs:__imp_GetLastError
0x14013124f  mov     ebx, eax
0x140131251  cmp     eax, 0EAh
0x140131256  jz      short loc_14013126E
0x140131258  test    eax, eax
0x14013125a  jle     loc_1401313A9
0x140131260  movzx   ebx, ax
0x140131263  or      ebx, 80070000h
0x140131269  jmp     loc_1401313A9
0x14013126e  mov     ecx, [rbp+cchReturnLength]
0x140131271  add     rcx, rcx; cb
0x140131274  call    cs:__imp_CoTaskMemAlloc
0x14013127a  xor     ebx, ebx
0x14013127c  mov     r15, rax
0x14013127f  test    rax, rax
0x140131282  jnz     short loc_14013128E
0x140131284  mov     ebx, 8007000Eh
0x140131289  jmp     loc_1401313A9
0x14013128e  mov     r8d, [rbp+cchReturnLength]; cchBufferLength
0x140131292  lea     r9, [rbp+var_20]; lpcchReturnLength
0x140131296  mov     rdx, r15; lpszVolumePathNames
0x140131299  mov     rcx, r14; lpszVolumeName
0x14013129c  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1401312a2  test    eax, eax
0x1401312a4  jnz     short loc_1401312C4
0x1401312a6  call    cs:__imp_GetLastError
0x1401312ac  mov     ebx, eax
0x1401312ae  test    eax, eax
0x1401312b0  jle     loc_1401313A0
0x1401312b6  movzx   ebx, ax
0x1401312b9  or      ebx, 80070000h
0x1401312bf  jmp     loc_1401313A0
0x1401312c4  inc     rdi
0x1401312c7  cmp     [r15+rdi*2], bx
0x1401312cc  jnz     short loc_1401312C4
0x1401312ce  test    edi, edi
0x1401312d0  jz      short loc_14013131C
0x1401312d2  lea     eax, [rdi+1]
0x1401312d5  lea     rcx, [rax+rax]; cb
0x1401312d9  mov     ebx, eax
0x1401312db  call    cs:__imp_CoTaskMemAlloc
0x1401312e1  mov     r11, rax
0x1401312e4  test    rax, rax
0x1401312e7  jnz     short loc_1401312F3
0x1401312e9  mov     ebx, 8007000Eh
0x1401312ee  jmp     loc_1401313A0
0x1401312f3  mov     r8, r15; unsigned __int16 *
0x1401312f6  mov     rdx, rbx; unsigned __int64
0x1401312f9  mov     rcx, r11; unsigned __int16 *
0x1401312fc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140131301  mov     ebx, eax
0x140131303  test    eax, eax
0x140131305  js      short loc_14013130E
0x140131307  mov     rsi, r11
0x14013130a  xor     ebx, ebx
0x14013130c  jmp     short loc_140131373
0x14013130e  mov     rcx, r11; pv
0x140131311  call    cs:__imp_CoTaskMemFree
0x140131317  jmp     loc_1401313A0
0x14013131c  mov     ecx, 1
0x140131321  mov     eax, ebx
0x140131323  cmp     eax, 1Ah
0x140131326  jnb     short loc_14013135F
0x140131328  test    r12d, ecx
0x14013132b  jz      short loc_140131333
0x14013132d  add     ecx, ecx
0x14013132f  inc     eax
0x140131331  jmp     short loc_140131323
0x140131333  add     ax, 41h ; 'A'
0x140131337  mov     [rbp+arg_1A], bx
0x14013133b  lea     r8, [rbp+var_10]; unsigned __int16 **
0x14013133f  mov     [rbp+arg_18], ax
0x140131343  lea     rdx, asc_14014F4EC; ":\\"
0x14013134a  lea     rcx, [rbp+arg_18]; unsigned __int16 *
0x14013134e  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x140131353  mov     rsi, [rbp+var_10]
0x140131357  mov     ebx, eax
0x140131359  test    eax, eax
0x14013135b  js      short loc_1401313A0
0x14013135d  xor     ebx, ebx
0x14013135f  mov     rdx, r14; lpszVolumeName
0x140131362  mov     rcx, rsi; lpszVolumeMountPoint
0x140131365  call    cs:__imp_SetVolumeMountPointW
0x14013136b  test    eax, eax
0x14013136d  jz      loc_1401312A6
0x140131373  mov     rcx, cs:?s_pwszWindowsDirectoryPathForOfflineOS@COfflineDriverInjection@@0PEAGEA; pv
0x14013137a  test    rcx, rcx
0x14013137d  jz      short loc_140131385
0x14013137f  call    cs:__imp_CoTaskMemFree
0x140131385  lea     r8, ?s_pwszWindowsDirectoryPathForOfflineOS@COfflineDriverInjection@@0PEAGEA; unsigned __int16 **
0x14013138c  mov     cs:?s_pwszWindowsDirectoryPathForOfflineOS@COfflineDriverInjection@@0PEAGEA, rbx; ushort * COfflineDriverInjection::s_pwszWindowsDirectoryPathForOfflineOS
0x140131393  mov     rdx, r13; unsigned __int16 *
0x140131396  mov     rcx, rsi; unsigned __int16 *
0x140131399  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x14013139e  mov     ebx, eax
0x1401313a0  mov     rcx, r15; pv
0x1401313a3  call    cs:__imp_CoTaskMemFree
0x1401313a9  test    r14, r14
0x1401313ac  jz      short loc_1401313B7
0x1401313ae  mov     rcx, r14; pv
0x1401313b1  call    cs:__imp_CoTaskMemFree
0x1401313b7  test    rsi, rsi
0x1401313ba  jz      short loc_1401313C5
0x1401313bc  mov     rcx, rsi; pv
0x1401313bf  call    cs:__imp_CoTaskMemFree
0x1401313c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1401313cc  lea     rax, WPP_GLOBAL_Control
0x1401313d3  cmp     rcx, rax
0x1401313d6  jz      short loc_1401313F9
0x1401313d8  test    byte ptr [rcx+1Ch], 20h
0x1401313dc  jz      short loc_1401313F9
0x1401313de  cmp     byte ptr [rcx+19h], 4
0x1401313e2  jb      short loc_1401313F9
0x1401313e4  mov     rcx, [rcx+10h]
0x1401313e8  lea     r8, WPP_d3373a8c9910345b1e2264c86067e59a_Traceguids
0x1401313ef  mov     edx, 17h
0x1401313f4  call    WPP_SF_
0x1401313f9  mov     eax, ebx
0x1401313fb  mov     rbx, [rsp+40h+arg_0]
0x140131403  add     rsp, 40h
0x140131407  pop     r15
0x140131409  pop     r14
0x14013140b  pop     r13
0x14013140d  pop     r12
0x14013140f  pop     rdi
0x140131410  pop     rsi
0x140131411  pop     rbp
0x140131412  retn
```
