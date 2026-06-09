# BlockCallerWithoutUserProfileInitOnceCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18002ce00`
- end: `0x18002d072`
- name: `?BlockCallerWithoutUserProfileInitOnceCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `626`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009cf0`
- `0x18002c2d0`
- `0x18002ce00`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e1b00`
- `0x1801e5350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002cfe8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002cfe8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cfb2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cfb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cf84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cf9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cf84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cf9b`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002cea8`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002cf30`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002cea8`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002cf30`

## pseudocode

```c
_BOOL8 __fastcall BlockCallerWithoutUserProfileInitOnceCallback(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  int v3; // edx
  int v4; // ecx
  HRESULT IsProcessAppContainer; // ebx
  int v6; // r8d
  int v7; // edx
  int v8; // ecx
  int v9; // r8d
  DWORD v10; // eax
  BOOL v12; // edi
  int v13; // [rsp+30h] [rbp-20h] BYREF
  int v14; // [rsp+34h] [rbp-1Ch]
  PWSTR v15; // [rsp+38h] [rbp-18h] BYREF
  PWSTR ppszPath; // [rsp+40h] [rbp-10h] BYREF

  v14 = 0;
  v15 = 0;
  ppszPath = 0;
  v13 = 0;
  g_fUserProfileLoaded = 0;
  IsProcessAppContainer = WxIsProcessAppContainer(&v13);
  if ( IsProcessAppContainer < 0 )
  {
    v14 = 59;
    goto LABEL_20;
  }
  if ( v13 )
  {
    v12 = 1;
LABEL_26:
    g_fUserProfileLoaded = v12;
    goto LABEL_20;
  }
  v14 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
    WPP_SF__guid_dq(v4, v3, v6, (unsigned int)&FOLDERID_LocalAppData, 0x4000, -1);
  IsProcessAppContainer = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0x4000u, (HANDLE)0xFFFFFFFFFFFFFFFFLL, &ppszPath);
  if ( IsProcessAppContainer < 0 )
  {
    v14 = 33;
LABEL_8:
    if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
      WPP_SF_d(1038, 12, WPP_399a03e428863a414a3dbf9528417340_Traceguids, (unsigned int)IsProcessAppContainer);
    goto LABEL_10;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
  {
    WPP_SF_S(1038, 11, WPP_399a03e428863a414a3dbf9528417340_Traceguids, ppszPath);
    goto LABEL_8;
  }
LABEL_10:
  if ( IsProcessAppContainer >= 0 )
  {
    v14 = 0;
    if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
      WPP_SF__guid_dq(v8, v7, v9, (unsigned int)&FOLDERID_LocalAppData, 0x4000, 0);
    IsProcessAppContainer = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0x4000u, 0, &v15);
    if ( IsProcessAppContainer < 0 )
    {
      v14 = 33;
    }
    else
    {
      if ( (BYTE1(xmmword_180266B60) & 0x40) == 0 )
      {
LABEL_18:
        if ( IsProcessAppContainer < 0 )
        {
          v14 = 67;
          goto LABEL_20;
        }
        v12 = _o__wcsicmp(ppszPath) != 0;
        goto LABEL_26;
      }
      WPP_SF_S(1038, 11, WPP_399a03e428863a414a3dbf9528417340_Traceguids, v15);
    }
    if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
      WPP_SF_d(1038, 12, WPP_399a03e428863a414a3dbf9528417340_Traceguids, (unsigned int)IsProcessAppContainer);
    goto LABEL_18;
  }
  v14 = 66;
LABEL_20:
  if ( v15 )
  {
    CoTaskMemFree(v15);
    v15 = 0;
  }
  if ( ppszPath )
  {
    CoTaskMemFree(ppszPath);
    ppszPath = 0;
  }
  v10 = WX_WIN32_FROM_HR((unsigned int)IsProcessAppContainer);
  SetLastError(v10);
  return IsProcessAppContainer >= 0;
}

```

## disassembly

```asm
0x18002ce00  mov     [rsp-8+arg_0], rbx
0x18002ce05  mov     [rsp-8+arg_8], rdi
0x18002ce0a  push    rbp
0x18002ce0b  mov     rbp, rsp
0x18002ce0e  sub     rsp, 50h
0x18002ce12  mov     rax, cs:__security_cookie
0x18002ce19  xor     rax, rsp
0x18002ce1c  mov     [rbp+var_8], rax
0x18002ce20  lea     rcx, [rbp+var_20]; int *
0x18002ce24  mov     [rbp+var_1C], 0
0x18002ce2b  mov     [rbp+var_18], 0
0x18002ce33  mov     [rbp+ppszPath], 0
0x18002ce3b  mov     [rbp+var_20], 0
0x18002ce42  mov     cs:?g_fUserProfileLoaded@@3HA, 0; int g_fUserProfileLoaded
0x18002ce4c  call    ?WxIsProcessAppContainer@@YAJPEAH@Z; WxIsProcessAppContainer(int *)
0x18002ce51  mov     ebx, eax
0x18002ce53  test    eax, eax
0x18002ce55  js      loc_18002D053
0x18002ce5b  cmp     [rbp+var_20], 0
0x18002ce5f  jnz     loc_18002D05F
0x18002ce65  mov     [rbp+var_1C], 0
0x18002ce6c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002ce70  mov     dil, 40h ; '@'
0x18002ce73  test    byte ptr cs:xmmword_180266B60+1, dil
0x18002ce7a  jz      short loc_18002CE95
0x18002ce7c  mov     [rsp+50h+var_28], rbx
0x18002ce81  lea     r9, FOLDERID_LocalAppData
0x18002ce88  mov     [rsp+50h+var_30], 4000h
0x18002ce90  call    WPP_SF__guid_dq
0x18002ce95  lea     r9, [rbp+ppszPath]; ppszPath
0x18002ce99  mov     r8, rbx; hToken
0x18002ce9c  mov     edx, 4000h; dwFlags
0x18002cea1  lea     rcx, FOLDERID_LocalAppData; rfid
0x18002cea8  call    cs:__imp_SHGetKnownFolderPath
0x18002ceae  mov     ebx, eax
0x18002ceb0  test    eax, eax
0x18002ceb2  js      loc_18002D03B
0x18002ceb8  test    byte ptr cs:xmmword_180266B60+1, dil
0x18002cebf  jz      short loc_18002CEE8
0x18002cec1  mov     r9, [rbp+ppszPath]
0x18002cec5  lea     r8, WPP_399a03e428863a414a3dbf9528417340_Traceguids
0x18002cecc  mov     edx, 0Bh
0x18002ced1  mov     ecx, 40Eh
0x18002ced6  call    WPP_SF_S
0x18002cedb  test    byte ptr cs:xmmword_180266B60+1, dil
0x18002cee2  jnz     loc_18002CFFF
0x18002cee8  test    ebx, ebx
0x18002ceea  js      loc_18002D066
0x18002cef0  mov     [rbp+var_1C], 0
0x18002cef7  test    byte ptr cs:xmmword_180266B60+1, dil
0x18002cefe  jz      short loc_18002CF1D
0x18002cf00  mov     [rsp+50h+var_28], 0
0x18002cf09  lea     r9, FOLDERID_LocalAppData
0x18002cf10  mov     [rsp+50h+var_30], 4000h
0x18002cf18  call    WPP_SF__guid_dq
0x18002cf1d  lea     r9, [rbp+var_18]; ppszPath
0x18002cf21  xor     r8d, r8d; hToken
0x18002cf24  mov     edx, 4000h; dwFlags
0x18002cf29  lea     rcx, FOLDERID_LocalAppData; rfid
0x18002cf30  call    cs:__imp_SHGetKnownFolderPath
0x18002cf36  mov     ebx, eax
0x18002cf38  test    eax, eax
0x18002cf3a  js      loc_18002D047
0x18002cf40  test    byte ptr cs:xmmword_180266B60+1, dil
0x18002cf47  jz      short loc_18002CF70
0x18002cf49  mov     r9, [rbp+var_18]
0x18002cf4d  lea     r8, WPP_399a03e428863a414a3dbf9528417340_Traceguids
0x18002cf54  mov     edx, 0Bh
0x18002cf59  mov     ecx, 40Eh
0x18002cf5e  call    WPP_SF_S
0x18002cf63  test    byte ptr cs:xmmword_180266B60+1, dil
0x18002cf6a  jnz     loc_18002D01D
0x18002cf70  test    ebx, ebx
0x18002cf72  jns     short loc_18002CFDB
0x18002cf74  mov     [rbp+var_1C], 43h ; 'C'
0x18002cf7b  mov     rcx, [rbp+var_18]; pv
0x18002cf7f  test    rcx, rcx
0x18002cf82  jz      short loc_18002CF92
0x18002cf84  call    cs:__imp_CoTaskMemFree
0x18002cf8a  mov     [rbp+var_18], 0
0x18002cf92  mov     rcx, [rbp+ppszPath]; pv
0x18002cf96  test    rcx, rcx
0x18002cf99  jz      short loc_18002CFA9
0x18002cf9b  call    cs:__imp_CoTaskMemFree
0x18002cfa1  mov     [rbp+ppszPath], 0
0x18002cfa9  mov     ecx, ebx
0x18002cfab  call    WX_WIN32_FROM_HR
0x18002cfb0  mov     ecx, eax; dwErrCode
0x18002cfb2  call    cs:__imp_SetLastError
0x18002cfb8  not     ebx
0x18002cfba  shr     ebx, 1Fh
0x18002cfbd  mov     eax, ebx
0x18002cfbf  mov     rcx, [rbp+var_8]
0x18002cfc3  xor     rcx, rsp; StackCookie
0x18002cfc6  call    __security_check_cookie
0x18002cfcb  mov     rbx, [rsp+50h+arg_0]
0x18002cfd0  mov     rdi, [rsp+50h+arg_8]
0x18002cfd5  add     rsp, 50h
0x18002cfd9  pop     rbp
0x18002cfda  retn
0x18002cfdb  mov     rdx, [rbp+var_18]
0x18002cfdf  mov     edi, 1
0x18002cfe4  mov     rcx, [rbp+ppszPath]
0x18002cfe8  call    cs:__imp__o__wcsicmp
0x18002cfee  test    eax, eax
0x18002cff0  jnz     short loc_18002CFF4
0x18002cff2  xor     edi, edi
0x18002cff4  mov     cs:?g_fUserProfileLoaded@@3HA, edi; int g_fUserProfileLoaded
0x18002cffa  jmp     loc_18002CF7B
0x18002cfff  mov     edx, 0Ch
0x18002d004  lea     r8, WPP_399a03e428863a414a3dbf9528417340_Traceguids
0x18002d00b  mov     ecx, 40Eh
0x18002d010  mov     r9d, ebx
0x18002d013  call    WPP_SF_d
0x18002d018  jmp     loc_18002CEE8
0x18002d01d  mov     edx, 0Ch
0x18002d022  lea     r8, WPP_399a03e428863a414a3dbf9528417340_Traceguids
0x18002d029  mov     ecx, 40Eh
0x18002d02e  mov     r9d, ebx
0x18002d031  call    WPP_SF_d
0x18002d036  jmp     loc_18002CF70
0x18002d03b  mov     [rbp+var_1C], 21h ; '!'
0x18002d042  jmp     loc_18002CEDB
0x18002d047  mov     [rbp+var_1C], 21h ; '!'
0x18002d04e  jmp     loc_18002CF63
0x18002d053  mov     [rbp+var_1C], 3Bh ; ';'
0x18002d05a  jmp     loc_18002CF7B
0x18002d05f  mov     edi, 1
0x18002d064  jmp     short loc_18002CFF4
0x18002d066  mov     [rbp+var_1C], 42h ; 'B'
0x18002d06d  jmp     loc_18002CF7B
```
