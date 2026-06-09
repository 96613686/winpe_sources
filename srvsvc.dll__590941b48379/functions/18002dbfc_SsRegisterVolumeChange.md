# SsRegisterVolumeChange

- ea: `0x18002dbfc`
- end: `0x18002dfa9`
- name: `SsRegisterVolumeChange`
- size: `941`
- prototype: `DWORD __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x1800036a0`
- `0x18002c750`

## callees

- `0x18000b940`
- `0x18001d230`
- `0x18001deb0`
- `0x18001e80c`
- `0x180020dc0`
- `0x180020de8`
- `0x1800214a4`
- `0x1800215e8`
- `0x18002dbfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dde5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002df35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dde5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002df35`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002dcdd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002dd3d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002dcdd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002dd3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dd83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ddd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dddf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002debd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dec6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002df41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002df4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dd83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ddd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dddf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002debd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dec6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002df41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002df4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002de69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002de69`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002de18`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002de18`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18002de76`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18002de76`
- `CFGMGR32!CMP_Register_Notification` at `0x18002de5e`
- `CFGMGR32!CMP_Register_Notification` at `0x18002de5e`

## pseudocode

```c
DWORD __fastcall SsRegisterVolumeChange(LPCWSTR lpFileName)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rdi
  size_t v5; // rbx
  wchar_t *v6; // rax
  HANDLE FileW; // rax
  void *v8; // rbp
  CONFIGRET v9; // ebx
  DWORD LastError; // ebx
  _QWORD *v11; // rax
  size_t pcchLength[2]; // [rsp+40h] [rbp-1E8h] BYREF
  _DWORD v13[4]; // [rsp+50h] [rbp-1D8h] BYREF
  HANDLE v14; // [rsp+60h] [rbp-1C8h]

  memset_0(v13, 0, 0x1A0u);
  pcchLength[0] = 0;
  if ( !SsVolumeResourceInitialized )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids);
    }
    return 1359;
  }
  if ( StringCchLengthW(lpFileName, 0x7FFFFFFFu, pcchLength) < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids);
    }
    return 13;
  }
  v3 = LocalAlloc(0x40u, 0x20u);
  v4 = v3;
  if ( !v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids);
    }
    return 1450;
  }
  v5 = pcchLength[0];
  v3[1] = v3;
  *v3 = v3;
  v6 = (wchar_t *)LocalAlloc(0x40u, 2 * v5 + 2);
  v4[3] = v6;
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids);
    }
    LocalFree(v4);
    return 1450;
  }
  if ( StringCchCopyW(v6, v5 + 1, lpFileName) >= 0 )
  {
    FileW = CreateFileW(lpFileName, 0x20000u, 3u, 0, 3u, 0x80u, 0);
    v8 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      LocalFree((HLOCAL)v4[3]);
      LocalFree(v4);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          94,
          (unsigned int)WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids,
          (_DWORD)lpFileName,
          LastError);
      }
    }
    else
    {
      v13[0] = 416;
      v13[2] = 1;
      v14 = FileW;
      v9 = CMP_Register_Notification(v13, 0, DeviceEventCallback, L"LanmanServer", v4 + 2);
      CloseHandle(v8);
      LastError = CM_MapCrToWin32Err(v9, 0xDu);
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids, LastError);
        }
        LocalFree((HLOCAL)v4[3]);
        LocalFree(v4);
      }
      else
      {
        v11 = (_QWORD *)qword_18005CBA8;
        if ( *(HLOCAL **)qword_18005CBA8 != &SsVolumeList )
          __fastfail(3u);
        *v4 = &SsVolumeList;
        v4[1] = v11;
        *v11 = v4;
        qword_18005CBA8 = (__int64)v4;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids, lpFileName);
        }
      }
    }
    return LastError;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids);
    }
    LocalFree((HLOCAL)v4[3]);
    LocalFree(v4);
    return GetLastError();
  }
}

```

## disassembly

```asm
0x18002dbfc  push    rbx
0x18002dbfe  push    rbp
0x18002dbff  push    rsi
0x18002dc00  push    rdi
0x18002dc01  sub     rsp, 208h
0x18002dc08  mov     rax, cs:__security_cookie
0x18002dc0f  xor     rax, rsp
0x18002dc12  mov     [rsp+228h+var_38], rax
0x18002dc1a  mov     rsi, rcx
0x18002dc1d  xor     edx, edx; Val
0x18002dc1f  lea     rcx, [rsp+228h+var_1D8]; void *
0x18002dc24  mov     r8d, 1A0h; Size
0x18002dc2a  call    memset_0
0x18002dc2f  cmp     cs:SsVolumeResourceInitialized, 0
0x18002dc36  mov     [rsp+228h+pcchLength], 0
0x18002dc3f  jnz     short loc_18002DC7F
0x18002dc41  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc48  lea     rax, WPP_GLOBAL_Control
0x18002dc4f  cmp     rcx, rax
0x18002dc52  jz      short loc_18002DC75
0x18002dc54  test    byte ptr [rcx+1Ch], 1
0x18002dc58  jz      short loc_18002DC75
0x18002dc5a  cmp     byte ptr [rcx+19h], 1
0x18002dc5e  jb      short loc_18002DC75
0x18002dc60  mov     rcx, [rcx+10h]
0x18002dc64  lea     r8, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids
0x18002dc6b  mov     edx, 57h ; 'W'
0x18002dc70  call    WPP_SF_
0x18002dc75  mov     eax, 54Fh
0x18002dc7a  jmp     loc_18002DF8D
0x18002dc7f  lea     r8, [rsp+228h+pcchLength]; pcchLength
0x18002dc84  mov     edx, 7FFFFFFFh; cchMax
0x18002dc89  mov     rcx, rsi; psz
0x18002dc8c  call    StringCchLengthW
0x18002dc91  test    eax, eax
0x18002dc93  jns     short loc_18002DCD3
0x18002dc95  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc9c  lea     rax, WPP_GLOBAL_Control
0x18002dca3  cmp     rcx, rax
0x18002dca6  jz      short loc_18002DCC9
0x18002dca8  test    byte ptr [rcx+1Ch], 1
0x18002dcac  jz      short loc_18002DCC9
0x18002dcae  cmp     byte ptr [rcx+19h], 1
0x18002dcb2  jb      short loc_18002DCC9
0x18002dcb4  mov     rcx, [rcx+10h]
0x18002dcb8  lea     r8, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids
0x18002dcbf  mov     edx, 58h ; 'X'
0x18002dcc4  call    WPP_SF_
0x18002dcc9  mov     eax, 0Dh
0x18002dcce  jmp     loc_18002DF8D
0x18002dcd3  mov     edx, 20h ; ' '; uBytes
0x18002dcd8  lea     ebp, [rdx+20h]
0x18002dcdb  mov     ecx, ebp; uFlags
0x18002dcdd  call    cs:__imp_LocalAlloc
0x18002dce3  mov     rdi, rax
0x18002dce6  test    rax, rax
0x18002dce9  jnz     short loc_18002DD27
0x18002dceb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dcf2  lea     rax, WPP_GLOBAL_Control
0x18002dcf9  cmp     rcx, rax
0x18002dcfc  jz      short loc_18002DD1D
0x18002dcfe  test    byte ptr [rcx+1Ch], 1
0x18002dd02  jz      short loc_18002DD1D
0x18002dd04  cmp     byte ptr [rcx+19h], 2
0x18002dd08  jb      short loc_18002DD1D
0x18002dd0a  mov     rcx, [rcx+10h]
0x18002dd0e  lea     edx, [rbp+19h]
0x18002dd11  lea     r8, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids
0x18002dd18  call    WPP_SF_
0x18002dd1d  mov     eax, 5AAh
0x18002dd22  jmp     loc_18002DF8D
0x18002dd27  mov     rbx, [rsp+228h+pcchLength]
0x18002dd2c  mov     ecx, ebp; uFlags
0x18002dd2e  mov     [rax+8], rdi
0x18002dd32  mov     [rax], rdi
0x18002dd35  lea     rdx, ds:2[rbx*2]; uBytes
0x18002dd3d  call    cs:__imp_LocalAlloc
0x18002dd43  mov     [rdi+18h], rax
0x18002dd47  test    rax, rax
0x18002dd4a  jnz     short loc_18002DD8B
0x18002dd4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd53  lea     rax, WPP_GLOBAL_Control
0x18002dd5a  cmp     rcx, rax
0x18002dd5d  jz      short loc_18002DD80
0x18002dd5f  test    byte ptr [rcx+1Ch], 1
0x18002dd63  jz      short loc_18002DD80
0x18002dd65  cmp     byte ptr [rcx+19h], 2
0x18002dd69  jb      short loc_18002DD80
0x18002dd6b  mov     rcx, [rcx+10h]
0x18002dd6f  lea     r8, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids
0x18002dd76  mov     edx, 5Ah ; 'Z'
0x18002dd7b  call    WPP_SF_
0x18002dd80  mov     rcx, rdi; hMem
0x18002dd83  call    cs:__imp_LocalFree
0x18002dd89  jmp     short loc_18002DD1D
0x18002dd8b  lea     rdx, [rbx+1]; cchDest
0x18002dd8f  mov     r8, rsi; pszSrc
0x18002dd92  mov     rcx, rax; pszDest
0x18002dd95  call    StringCchCopyW
0x18002dd9a  test    eax, eax
0x18002dd9c  jns     short loc_18002DDF0
0x18002dd9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dda5  lea     rax, WPP_GLOBAL_Control
0x18002ddac  cmp     rcx, rax
0x18002ddaf  jz      short loc_18002DDD2
0x18002ddb1  test    byte ptr [rcx+1Ch], 1
0x18002ddb5  jz      short loc_18002DDD2
0x18002ddb7  cmp     byte ptr [rcx+19h], 2
0x18002ddbb  jb      short loc_18002DDD2
0x18002ddbd  mov     rcx, [rcx+10h]
0x18002ddc1  lea     r8, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids
0x18002ddc8  mov     edx, 5Bh ; '['
0x18002ddcd  call    WPP_SF_
0x18002ddd2  mov     rcx, [rdi+18h]; hMem
0x18002ddd6  call    cs:__imp_LocalFree
0x18002dddc  mov     rcx, rdi; hMem
0x18002dddf  call    cs:__imp_LocalFree
0x18002dde5  call    cs:__imp_GetLastError
0x18002ddeb  jmp     loc_18002DF8D
0x18002ddf0  xor     r9d, r9d; lpSecurityAttributes
0x18002ddf3  mov     [rsp+228h+hTemplateFile], 0; hTemplateFile
0x18002ddfc  mov     [rsp+228h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002de04  mov     edx, 20000h; dwDesiredAccess
0x18002de09  mov     rcx, rsi; lpFileName
0x18002de0c  mov     [rsp+228h+dwCreationDisposition], 3; dwCreationDisposition
0x18002de14  lea     r8d, [r9+3]; dwShareMode
0x18002de18  call    cs:__imp_CreateFileW
0x18002de1e  mov     rbp, rax
0x18002de21  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002de25  jz      loc_18002DF35
0x18002de2b  lea     rcx, [rdi+10h]
0x18002de2f  mov     [rsp+228h+var_1D8], 1A0h
0x18002de37  mov     qword ptr [rsp+228h+dwCreationDisposition], rcx
0x18002de3c  lea     r9, Path; "LanmanServer"
0x18002de43  lea     rcx, [rsp+228h+var_1D8]
0x18002de48  mov     [rsp+228h+var_1D0], 1
0x18002de50  lea     r8, DeviceEventCallback
0x18002de57  mov     [rsp+228h+var_1C8], rax
0x18002de5c  xor     edx, edx
0x18002de5e  call    cs:__imp_CMP_Register_Notification
0x18002de64  mov     rcx, rbp; hObject
0x18002de67  mov     ebx, eax
0x18002de69  call    cs:__imp_CloseHandle
0x18002de6f  mov     edx, 0Dh; DefaultErr
0x18002de74  mov     ecx, ebx; CmReturnCode
0x18002de76  call    cs:__imp_CM_MapCrToWin32Err
0x18002de7c  mov     ebx, eax
0x18002de7e  test    eax, eax
0x18002de80  jz      short loc_18002DED1
0x18002de82  mov     rcx, cs:WPP_GLOBAL_Control
0x18002de89  lea     rax, WPP_GLOBAL_Control
0x18002de90  cmp     rcx, rax
0x18002de93  jz      short loc_18002DEB9
0x18002de95  test    byte ptr [rcx+1Ch], 1
0x18002de99  jz      short loc_18002DEB9
0x18002de9b  cmp     byte ptr [rcx+19h], 1
0x18002de9f  jb      short loc_18002DEB9
0x18002dea1  mov     rcx, [rcx+10h]
0x18002dea5  lea     r8, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids
0x18002deac  mov     edx, 5Ch ; '\'
0x18002deb1  mov     r9d, ebx
0x18002deb4  call    WPP_SF_d
0x18002deb9  mov     rcx, [rdi+18h]; hMem
0x18002debd  call    cs:__imp_LocalFree
0x18002dec3  mov     rcx, rdi; hMem
0x18002dec6  call    cs:__imp_LocalFree
0x18002decc  jmp     loc_18002DF8B
0x18002ded1  mov     rax, cs:qword_18005CBA8
0x18002ded8  lea     rcx, SsVolumeList
0x18002dedf  cmp     [rax], rcx
0x18002dee2  jz      short loc_18002DEEB
0x18002dee4  mov     ecx, 3
0x18002dee9  int     29h; Win8: RtlFailFast(ecx)
0x18002deeb  mov     [rdi], rcx
0x18002deee  mov     [rdi+8], rax
0x18002def2  mov     [rax], rdi
0x18002def5  mov     cs:qword_18005CBA8, rdi
0x18002defc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df03  lea     rax, WPP_GLOBAL_Control
0x18002df0a  cmp     rcx, rax
0x18002df0d  jz      short loc_18002DF8B
0x18002df0f  test    byte ptr [rcx+1Ch], 1
0x18002df13  jz      short loc_18002DF8B
0x18002df15  cmp     byte ptr [rcx+19h], 2
0x18002df19  jb      short loc_18002DF8B
0x18002df1b  mov     rcx, [rcx+10h]
0x18002df1f  lea     r8, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids
0x18002df26  mov     edx, 5Dh ; ']'
0x18002df2b  mov     r9, rsi
0x18002df2e  call    WPP_SF_S
0x18002df33  jmp     short loc_18002DF8B
0x18002df35  call    cs:__imp_GetLastError
0x18002df3b  mov     rcx, [rdi+18h]; hMem
0x18002df3f  mov     ebx, eax
0x18002df41  call    cs:__imp_LocalFree
0x18002df47  mov     rcx, rdi; hMem
0x18002df4a  call    cs:__imp_LocalFree
0x18002df50  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df57  lea     rax, WPP_GLOBAL_Control
0x18002df5e  cmp     rcx, rax
0x18002df61  jz      short loc_18002DF8B
0x18002df63  test    byte ptr [rcx+1Ch], 1
0x18002df67  jz      short loc_18002DF8B
0x18002df69  cmp     byte ptr [rcx+19h], 1
0x18002df6d  jb      short loc_18002DF8B
0x18002df6f  mov     rcx, [rcx+10h]
0x18002df73  lea     r8, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids
0x18002df7a  mov     edx, 5Eh ; '^'
0x18002df7f  mov     [rsp+228h+dwCreationDisposition], ebx
0x18002df83  mov     r9, rsi
0x18002df86  call    WPP_SF_Sd
0x18002df8b  mov     eax, ebx
0x18002df8d  mov     rcx, [rsp+228h+var_38]
0x18002df95  xor     rcx, rsp; StackCookie
0x18002df98  call    __security_check_cookie
0x18002df9d  add     rsp, 208h
0x18002dfa4  pop     rdi
0x18002dfa5  pop     rsi
0x18002dfa6  pop     rbp
0x18002dfa7  pop     rbx
0x18002dfa8  retn
```
