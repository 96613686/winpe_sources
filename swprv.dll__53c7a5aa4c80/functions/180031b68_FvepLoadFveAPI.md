# FvepLoadFveAPI

- ea: `0x180031b68`
- end: `0x180031e7e`
- name: `FvepLoadFveAPI`
- size: `790`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003195c`

## callees

- `0x180001580`
- `0x18000212c`
- `0x180031b68`
- `0x180031e84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031be4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031be4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d89`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180031c28`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180031c28`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031c40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031c5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031c7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031c9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031cb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031cd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031cf5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031d13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031d2d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031d46`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031d60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031d79`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031db6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031dcb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031ddf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031c40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031c5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031c7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031c9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031cb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031cd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031cf5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031d13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031d2d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031d46`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031d60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031d79`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031db6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031dcb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031ddf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031da1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031da1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180031bda`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180031bda`

## string_xrefs

- `0x180031c02`: `\FVEAPI.DLL`
- `0x180031c36`: `FveOpenVolumeW`
- `0x180031d56`: `FveDeleteAuthMethod`
- `0x180031d6f`: `FveCommitChanges`
- `0x180031dac`: `FveCommitChangesEx`

## pseudocode

```c
__int64 __fastcall FvepLoadFveAPI(HMODULE *a1, __int64 a2)
{
  signed int v4; // eax
  unsigned int v5; // ebx
  HMODULE Library; // rax
  HMODULE v7; // rdi
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v21; // [rsp+20h] [rbp-E0h]
  __int128 v22; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v23; // [rsp+40h] [rbp-C0h]
  __int128 v24; // [rsp+50h] [rbp-B0h]
  __int128 v25; // [rsp+60h] [rbp-A0h]
  __int128 v26; // [rsp+70h] [rbp-90h]
  __int128 v27; // [rsp+80h] [rbp-80h]
  __int128 v28; // [rsp+90h] [rbp-70h]
  __int128 v29; // [rsp+A0h] [rbp-60h]
  __int128 v30; // [rsp+B0h] [rbp-50h]
  __int128 v31; // [rsp+C0h] [rbp-40h]
  INT_PTR (__stdcall *v32)(); // [rsp+D0h] [rbp-30h]
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(&v22, 0, 0xA8u);
  *a1 = 0;
  *(_QWORD *)&v21 = -1;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    goto LABEL_2;
  v5 = StringCchCatW(Buffer, 0x104u, L"\\FVEAPI.DLL");
  if ( (v5 & 0x80000000) != 0 )
    return v5;
  Library = LoadLibraryExW(Buffer, 0, 0);
  v7 = Library;
  if ( Library )
  {
    *((_QWORD *)&v21 + 1) = GetProcAddress(Library, "FveOpenVolumeW");
    if ( *((_QWORD *)&v21 + 1) )
    {
      *(_QWORD *)&v22 = GetProcAddress(v7, "FveCloseVolume");
      if ( (_QWORD)v22 )
      {
        *(_QWORD *)&v24 = GetProcAddress(v7, "FveGetStatus");
        if ( (_QWORD)v24 )
        {
          *(_QWORD *)&v27 = GetProcAddress(v7, "FveAddAuthMethodInformation");
          if ( (_QWORD)v27 )
          {
            *((_QWORD *)&v26 + 1) = GetProcAddress(v7, "FveGetAuthMethodInformation");
            if ( *((_QWORD *)&v26 + 1) )
            {
              *((_QWORD *)&v27 + 1) = GetProcAddress(v7, "FveDeleteAuthMethod");
              if ( *((_QWORD *)&v27 + 1) )
              {
                *((_QWORD *)&v22 + 1) = GetProcAddress(v7, "FveCommitChanges");
                if ( *((_QWORD *)&v22 + 1) )
                {
                  *(_QWORD *)&v23 = GetProcAddress(v7, "FveCommitChangesEx");
                  *(_QWORD *)&v28 = GetProcAddress(v7, "FveGetSecureBootBindingState");
                  ProcAddress = GetProcAddress(v7, "FveControl");
                  goto LABEL_23;
                }
              }
            }
          }
        }
      }
    }
    else
    {
      *((_QWORD *)&v24 + 1) = GetProcAddress(v7, "FveGetStatusBasicW");
      if ( *((_QWORD *)&v24 + 1) )
      {
        *(_QWORD *)&v25 = GetProcAddress(v7, "FveSetFipsAllowDisabled");
        if ( (_QWORD)v25 )
        {
          if ( GetProcAddress(v7, "FveDisableAuthenticationW") )
          {
            *((_QWORD *)&v25 + 1) = GetProcAddress(v7, "FveDisableAuthenticationW");
            if ( *((_QWORD *)&v25 + 1) )
            {
              *(_QWORD *)&v26 = GetProcAddress(v7, "FveEnableAuthenticationW");
              if ( (_QWORD)v26 )
              {
                ProcAddress = v32;
LABEL_23:
                v10 = v22;
                *a1 = v7;
                *(_OWORD *)a2 = v21;
                v11 = v23;
                *(_OWORD *)(a2 + 16) = v10;
                v12 = v24;
                *(_OWORD *)(a2 + 32) = v11;
                v13 = v25;
                *(_OWORD *)(a2 + 48) = v12;
                v14 = v26;
                *(_OWORD *)(a2 + 64) = v13;
                v15 = v27;
                *(_OWORD *)(a2 + 80) = v14;
                v16 = v28;
                *(_OWORD *)(a2 + 96) = v15;
                v17 = v29;
                *(_OWORD *)(a2 + 112) = v16;
                v18 = v30;
                *(_OWORD *)(a2 + 128) = v17;
                v19 = v31;
                *(_OWORD *)(a2 + 144) = v18;
                *(_OWORD *)(a2 + 160) = v19;
                *(_QWORD *)(a2 + 176) = ProcAddress;
                return v5;
              }
            }
          }
        }
      }
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    FreeLibrary(v7);
  }
  else
  {
LABEL_2:
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  return v5;
}

```

## disassembly

```asm
0x180031b68  mov     [rsp-8+arg_10], rbx
0x180031b6d  mov     [rsp-8+arg_18], rsi
0x180031b72  push    rbp
0x180031b73  push    rdi
0x180031b74  push    r14
0x180031b76  lea     rbp, [rsp-200h]
0x180031b7e  sub     rsp, 300h
0x180031b85  mov     rax, cs:__security_cookie
0x180031b8c  xor     rax, rsp
0x180031b8f  mov     [rbp+210h+var_20], rax
0x180031b96  mov     rsi, rdx
0x180031b99  mov     r14, rcx
0x180031b9c  xor     edx, edx; Val
0x180031b9e  lea     rcx, [rbp+210h+Buffer]; void *
0x180031ba2  mov     r8d, 208h; Size
0x180031ba8  call    memset_0
0x180031bad  xor     edx, edx; Val
0x180031baf  lea     rcx, [rsp+310h+var_2E0]; void *
0x180031bb4  mov     r8d, 0A8h; Size
0x180031bba  call    memset_0
0x180031bbf  mov     ebx, 104h
0x180031bc4  mov     qword ptr [r14], 0
0x180031bcb  mov     edx, ebx; uSize
0x180031bcd  mov     qword ptr [rsp+310h+var_2F0], 0FFFFFFFFFFFFFFFFh
0x180031bd6  lea     rcx, [rbp+210h+Buffer]; lpBuffer
0x180031bda  call    cs:__imp_GetSystemDirectoryW
0x180031be0  test    eax, eax
0x180031be2  jnz     short loc_180031C02
0x180031be4  call    cs:__imp_GetLastError
0x180031bea  mov     ebx, eax
0x180031bec  test    eax, eax
0x180031bee  jle     loc_180031E55
0x180031bf4  movzx   ebx, ax
0x180031bf7  or      ebx, 80070000h
0x180031bfd  jmp     loc_180031E55
0x180031c02  lea     r8, aFveapiDll; "\\FVEAPI.DLL"
0x180031c09  mov     rdx, rbx; cchDest
0x180031c0c  lea     rcx, [rbp+210h+Buffer]; pszDest
0x180031c10  call    StringCchCatW
0x180031c15  mov     ebx, eax
0x180031c17  test    eax, eax
0x180031c19  js      loc_180031E55
0x180031c1f  xor     r8d, r8d; dwFlags
0x180031c22  lea     rcx, [rbp+210h+Buffer]; lpLibFileName
0x180031c26  xor     edx, edx; hFile
0x180031c28  call    cs:__imp_LoadLibraryExW
0x180031c2e  mov     rdi, rax
0x180031c31  test    rax, rax
0x180031c34  jz      short loc_180031BE4
0x180031c36  lea     rdx, aFveopenvolumew; "FveOpenVolumeW"
0x180031c3d  mov     rcx, rax; hModule
0x180031c40  call    cs:__imp_GetProcAddress
0x180031c46  mov     qword ptr [rsp+310h+var_2F0+8], rax
0x180031c4b  mov     rcx, rdi; hModule
0x180031c4e  test    rax, rax
0x180031c51  jnz     loc_180031CEE
0x180031c57  lea     rdx, aFvegetstatusba; "FveGetStatusBasicW"
0x180031c5e  call    cs:__imp_GetProcAddress
0x180031c64  mov     qword ptr [rsp+310h+var_2C0+8], rax
0x180031c69  test    rax, rax
0x180031c6c  jz      loc_180031D89
0x180031c72  lea     rdx, aFvesetfipsallo; "FveSetFipsAllowDisabled"
0x180031c79  mov     rcx, rdi; hModule
0x180031c7c  call    cs:__imp_GetProcAddress
0x180031c82  mov     qword ptr [rsp+310h+var_2B0], rax
0x180031c87  test    rax, rax
0x180031c8a  jz      loc_180031D89
0x180031c90  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x180031c97  mov     rcx, rdi; hModule
0x180031c9a  call    cs:__imp_GetProcAddress
0x180031ca0  test    rax, rax
0x180031ca3  jz      loc_180031D89
0x180031ca9  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x180031cb0  mov     rcx, rdi; hModule
0x180031cb3  call    cs:__imp_GetProcAddress
0x180031cb9  mov     qword ptr [rsp+310h+var_2B0+8], rax
0x180031cbe  test    rax, rax
0x180031cc1  jz      loc_180031D89
0x180031cc7  lea     rdx, aFveenableauthe; "FveEnableAuthenticationW"
0x180031cce  mov     rcx, rdi; hModule
0x180031cd1  call    cs:__imp_GetProcAddress
0x180031cd7  mov     qword ptr [rsp+310h+var_2A0], rax
0x180031cdc  test    rax, rax
0x180031cdf  jz      loc_180031D89
0x180031ce5  mov     rax, [rbp+210h+var_240]
0x180031ce9  jmp     loc_180031DE5
0x180031cee  lea     rdx, aFveclosevolume; "FveCloseVolume"
0x180031cf5  call    cs:__imp_GetProcAddress
0x180031cfb  mov     qword ptr [rsp+310h+var_2E0], rax
0x180031d00  test    rax, rax
0x180031d03  jz      loc_180031D89
0x180031d09  lea     rdx, aFvegetstatus; "FveGetStatus"
0x180031d10  mov     rcx, rdi; hModule
0x180031d13  call    cs:__imp_GetProcAddress
0x180031d19  mov     qword ptr [rsp+310h+var_2C0], rax
0x180031d1e  test    rax, rax
0x180031d21  jz      short loc_180031D89
0x180031d23  lea     rdx, aFveaddauthmeth; "FveAddAuthMethodInformation"
0x180031d2a  mov     rcx, rdi; hModule
0x180031d2d  call    cs:__imp_GetProcAddress
0x180031d33  mov     qword ptr [rbp+210h+var_290], rax
0x180031d37  test    rax, rax
0x180031d3a  jz      short loc_180031D89
0x180031d3c  lea     rdx, aFvegetauthmeth; "FveGetAuthMethodInformation"
0x180031d43  mov     rcx, rdi; hModule
0x180031d46  call    cs:__imp_GetProcAddress
0x180031d4c  mov     qword ptr [rsp+310h+var_2A0+8], rax
0x180031d51  test    rax, rax
0x180031d54  jz      short loc_180031D89
0x180031d56  lea     rdx, aFvedeleteauthm; "FveDeleteAuthMethod"
0x180031d5d  mov     rcx, rdi; hModule
0x180031d60  call    cs:__imp_GetProcAddress
0x180031d66  mov     qword ptr [rbp+210h+var_290+8], rax
0x180031d6a  test    rax, rax
0x180031d6d  jz      short loc_180031D89
0x180031d6f  lea     rdx, aFvecommitchang_0; "FveCommitChanges"
0x180031d76  mov     rcx, rdi; hModule
0x180031d79  call    cs:__imp_GetProcAddress
0x180031d7f  mov     qword ptr [rsp+310h+var_2E0+8], rax
0x180031d84  test    rax, rax
0x180031d87  jnz     short loc_180031DAC
0x180031d89  call    cs:__imp_GetLastError
0x180031d8f  mov     ebx, eax
0x180031d91  test    eax, eax
0x180031d93  jle     short loc_180031D9E
0x180031d95  movzx   ebx, ax
0x180031d98  or      ebx, 80070000h
0x180031d9e  mov     rcx, rdi; hLibModule
0x180031da1  call    cs:__imp_FreeLibrary
0x180031da7  jmp     loc_180031E55
0x180031dac  lea     rdx, aFvecommitchang; "FveCommitChangesEx"
0x180031db3  mov     rcx, rdi; hModule
0x180031db6  call    cs:__imp_GetProcAddress
0x180031dbc  lea     rdx, aFvegetsecurebo; "FveGetSecureBootBindingState"
0x180031dc3  mov     rcx, rdi; hModule
0x180031dc6  mov     qword ptr [rsp+310h+var_2D0], rax
0x180031dcb  call    cs:__imp_GetProcAddress
0x180031dd1  lea     rdx, aFvecontrol; "FveControl"
0x180031dd8  mov     rcx, rdi; hModule
0x180031ddb  mov     qword ptr [rbp+210h+var_280], rax
0x180031ddf  call    cs:__imp_GetProcAddress
0x180031de5  movaps  xmm0, [rsp+310h+var_2F0]
0x180031dea  movaps  xmm1, [rsp+310h+var_2E0]
0x180031def  mov     [r14], rdi
0x180031df2  movups  xmmword ptr [rsi], xmm0
0x180031df5  movaps  xmm0, [rsp+310h+var_2D0]
0x180031dfa  movups  xmmword ptr [rsi+10h], xmm1
0x180031dfe  movaps  xmm1, [rsp+310h+var_2C0]
0x180031e03  movups  xmmword ptr [rsi+20h], xmm0
0x180031e07  movaps  xmm0, [rsp+310h+var_2B0]
0x180031e0c  movups  xmmword ptr [rsi+30h], xmm1
0x180031e10  movaps  xmm1, [rsp+310h+var_2A0]
0x180031e15  movups  xmmword ptr [rsi+40h], xmm0
0x180031e19  movaps  xmm0, [rbp+210h+var_290]
0x180031e1d  movups  xmmword ptr [rsi+50h], xmm1
0x180031e21  movaps  xmm1, [rbp+210h+var_280]
0x180031e25  movups  xmmword ptr [rsi+60h], xmm0
0x180031e29  movaps  xmm0, [rbp+210h+var_270]
0x180031e2d  movups  xmmword ptr [rsi+70h], xmm1
0x180031e31  movaps  xmm1, [rbp+210h+var_260]
0x180031e35  movups  xmmword ptr [rsi+80h], xmm0
0x180031e3c  movaps  xmm0, [rbp+210h+var_250]
0x180031e40  movups  xmmword ptr [rsi+90h], xmm1
0x180031e47  movups  xmmword ptr [rsi+0A0h], xmm0
0x180031e4e  mov     [rsi+0B0h], rax
0x180031e55  mov     eax, ebx
0x180031e57  mov     rcx, [rbp+210h+var_20]
0x180031e5e  xor     rcx, rsp; StackCookie
0x180031e61  call    __security_check_cookie
0x180031e66  lea     r11, [rsp+310h+var_10]
0x180031e6e  mov     rbx, [r11+30h]
0x180031e72  mov     rsi, [r11+38h]
0x180031e76  mov     rsp, r11
0x180031e79  pop     r14
0x180031e7b  pop     rdi
0x180031e7c  pop     rbp
0x180031e7d  retn
```
