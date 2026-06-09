# FvepLoadFveAPI

- ea: `0x18006ea58`
- end: `0x18006ed6e`
- name: `FvepLoadFveAPI`
- size: `790`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006e84c`

## callees

- `0x18006ea58`
- `0x18006ed74`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18006eb18`
- `KERNEL32!LoadLibraryExW` at `0x18006eb18`
- `KERNEL32!FreeLibrary` at `0x18006ec91`
- `KERNEL32!FreeLibrary` at `0x18006ec91`
- `KERNEL32!GetSystemDirectoryW` at `0x18006eaca`
- `KERNEL32!GetSystemDirectoryW` at `0x18006eaca`
- `KERNEL32!GetProcAddress` at `0x18006eb30`
- `KERNEL32!GetProcAddress` at `0x18006eb4e`
- `KERNEL32!GetProcAddress` at `0x18006eb6c`
- `KERNEL32!GetProcAddress` at `0x18006eb8a`
- `KERNEL32!GetProcAddress` at `0x18006eba3`
- `KERNEL32!GetProcAddress` at `0x18006ebc1`
- `KERNEL32!GetProcAddress` at `0x18006ebe5`
- `KERNEL32!GetProcAddress` at `0x18006ec03`
- `KERNEL32!GetProcAddress` at `0x18006ec1d`
- `KERNEL32!GetProcAddress` at `0x18006ec36`
- `KERNEL32!GetProcAddress` at `0x18006ec50`
- `KERNEL32!GetProcAddress` at `0x18006ec69`
- `KERNEL32!GetProcAddress` at `0x18006eca6`
- `KERNEL32!GetProcAddress` at `0x18006ecbb`
- `KERNEL32!GetProcAddress` at `0x18006eccf`
- `KERNEL32!GetProcAddress` at `0x18006eb30`
- `KERNEL32!GetProcAddress` at `0x18006eb4e`
- `KERNEL32!GetProcAddress` at `0x18006eb6c`
- `KERNEL32!GetProcAddress` at `0x18006eb8a`
- `KERNEL32!GetProcAddress` at `0x18006eba3`
- `KERNEL32!GetProcAddress` at `0x18006ebc1`
- `KERNEL32!GetProcAddress` at `0x18006ebe5`
- `KERNEL32!GetProcAddress` at `0x18006ec03`
- `KERNEL32!GetProcAddress` at `0x18006ec1d`
- `KERNEL32!GetProcAddress` at `0x18006ec36`
- `KERNEL32!GetProcAddress` at `0x18006ec50`
- `KERNEL32!GetProcAddress` at `0x18006ec69`
- `KERNEL32!GetProcAddress` at `0x18006eca6`
- `KERNEL32!GetProcAddress` at `0x18006ecbb`
- `KERNEL32!GetProcAddress` at `0x18006eccf`
- `KERNEL32!GetLastError` at `0x18006ead4`
- `KERNEL32!GetLastError` at `0x18006ec79`
- `KERNEL32!GetLastError` at `0x18006ead4`
- `KERNEL32!GetLastError` at `0x18006ec79`

## string_xrefs

- `0x18006eaf2`: `\FVEAPI.DLL`
- `0x18006eb26`: `FveOpenVolumeW`
- `0x18006ec46`: `FveDeleteAuthMethod`
- `0x18006ec5f`: `FveCommitChanges`
- `0x18006ec9c`: `FveCommitChangesEx`

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
0x18006ea58  mov     [rsp-8+arg_10], rbx
0x18006ea5d  mov     [rsp-8+arg_18], rsi
0x18006ea62  push    rbp
0x18006ea63  push    rdi
0x18006ea64  push    r14
0x18006ea66  lea     rbp, [rsp-200h]
0x18006ea6e  sub     rsp, 300h
0x18006ea75  mov     rax, cs:__security_cookie
0x18006ea7c  xor     rax, rsp
0x18006ea7f  mov     [rbp+210h+var_20], rax
0x18006ea86  mov     rsi, rdx
0x18006ea89  mov     r14, rcx
0x18006ea8c  xor     edx, edx; Val
0x18006ea8e  lea     rcx, [rbp+210h+Buffer]; void *
0x18006ea92  mov     r8d, 208h; Size
0x18006ea98  call    memset_0
0x18006ea9d  xor     edx, edx; Val
0x18006ea9f  lea     rcx, [rsp+310h+var_2E0]; void *
0x18006eaa4  mov     r8d, 0A8h; Size
0x18006eaaa  call    memset_0
0x18006eaaf  mov     ebx, 104h
0x18006eab4  mov     qword ptr [r14], 0
0x18006eabb  mov     edx, ebx; uSize
0x18006eabd  mov     qword ptr [rsp+310h+var_2F0], 0FFFFFFFFFFFFFFFFh
0x18006eac6  lea     rcx, [rbp+210h+Buffer]; lpBuffer
0x18006eaca  call    cs:__imp_GetSystemDirectoryW
0x18006ead0  test    eax, eax
0x18006ead2  jnz     short loc_18006EAF2
0x18006ead4  call    cs:__imp_GetLastError
0x18006eada  mov     ebx, eax
0x18006eadc  test    eax, eax
0x18006eade  jle     loc_18006ED45
0x18006eae4  movzx   ebx, ax
0x18006eae7  or      ebx, 80070000h
0x18006eaed  jmp     loc_18006ED45
0x18006eaf2  lea     r8, aFveapiDll_0; "\\FVEAPI.DLL"
0x18006eaf9  mov     rdx, rbx; cchDest
0x18006eafc  lea     rcx, [rbp+210h+Buffer]; pszDest
0x18006eb00  call    StringCchCatW
0x18006eb05  mov     ebx, eax
0x18006eb07  test    eax, eax
0x18006eb09  js      loc_18006ED45
0x18006eb0f  xor     r8d, r8d; dwFlags
0x18006eb12  lea     rcx, [rbp+210h+Buffer]; lpLibFileName
0x18006eb16  xor     edx, edx; hFile
0x18006eb18  call    cs:__imp_LoadLibraryExW
0x18006eb1e  mov     rdi, rax
0x18006eb21  test    rax, rax
0x18006eb24  jz      short loc_18006EAD4
0x18006eb26  lea     rdx, aFveopenvolumew; "FveOpenVolumeW"
0x18006eb2d  mov     rcx, rax; hModule
0x18006eb30  call    cs:__imp_GetProcAddress
0x18006eb36  mov     qword ptr [rsp+310h+var_2F0+8], rax
0x18006eb3b  mov     rcx, rdi; hModule
0x18006eb3e  test    rax, rax
0x18006eb41  jnz     loc_18006EBDE
0x18006eb47  lea     rdx, aFvegetstatusba; "FveGetStatusBasicW"
0x18006eb4e  call    cs:__imp_GetProcAddress
0x18006eb54  mov     qword ptr [rsp+310h+var_2C0+8], rax
0x18006eb59  test    rax, rax
0x18006eb5c  jz      loc_18006EC79
0x18006eb62  lea     rdx, aFvesetfipsallo; "FveSetFipsAllowDisabled"
0x18006eb69  mov     rcx, rdi; hModule
0x18006eb6c  call    cs:__imp_GetProcAddress
0x18006eb72  mov     qword ptr [rsp+310h+var_2B0], rax
0x18006eb77  test    rax, rax
0x18006eb7a  jz      loc_18006EC79
0x18006eb80  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x18006eb87  mov     rcx, rdi; hModule
0x18006eb8a  call    cs:__imp_GetProcAddress
0x18006eb90  test    rax, rax
0x18006eb93  jz      loc_18006EC79
0x18006eb99  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x18006eba0  mov     rcx, rdi; hModule
0x18006eba3  call    cs:__imp_GetProcAddress
0x18006eba9  mov     qword ptr [rsp+310h+var_2B0+8], rax
0x18006ebae  test    rax, rax
0x18006ebb1  jz      loc_18006EC79
0x18006ebb7  lea     rdx, aFveenableauthe; "FveEnableAuthenticationW"
0x18006ebbe  mov     rcx, rdi; hModule
0x18006ebc1  call    cs:__imp_GetProcAddress
0x18006ebc7  mov     qword ptr [rsp+310h+var_2A0], rax
0x18006ebcc  test    rax, rax
0x18006ebcf  jz      loc_18006EC79
0x18006ebd5  mov     rax, [rbp+210h+var_240]
0x18006ebd9  jmp     loc_18006ECD5
0x18006ebde  lea     rdx, aFveclosevolume; "FveCloseVolume"
0x18006ebe5  call    cs:__imp_GetProcAddress
0x18006ebeb  mov     qword ptr [rsp+310h+var_2E0], rax
0x18006ebf0  test    rax, rax
0x18006ebf3  jz      loc_18006EC79
0x18006ebf9  lea     rdx, aFvegetstatus; "FveGetStatus"
0x18006ec00  mov     rcx, rdi; hModule
0x18006ec03  call    cs:__imp_GetProcAddress
0x18006ec09  mov     qword ptr [rsp+310h+var_2C0], rax
0x18006ec0e  test    rax, rax
0x18006ec11  jz      short loc_18006EC79
0x18006ec13  lea     rdx, aFveaddauthmeth; "FveAddAuthMethodInformation"
0x18006ec1a  mov     rcx, rdi; hModule
0x18006ec1d  call    cs:__imp_GetProcAddress
0x18006ec23  mov     qword ptr [rbp+210h+var_290], rax
0x18006ec27  test    rax, rax
0x18006ec2a  jz      short loc_18006EC79
0x18006ec2c  lea     rdx, aFvegetauthmeth; "FveGetAuthMethodInformation"
0x18006ec33  mov     rcx, rdi; hModule
0x18006ec36  call    cs:__imp_GetProcAddress
0x18006ec3c  mov     qword ptr [rsp+310h+var_2A0+8], rax
0x18006ec41  test    rax, rax
0x18006ec44  jz      short loc_18006EC79
0x18006ec46  lea     rdx, aFvedeleteauthm; "FveDeleteAuthMethod"
0x18006ec4d  mov     rcx, rdi; hModule
0x18006ec50  call    cs:__imp_GetProcAddress
0x18006ec56  mov     qword ptr [rbp+210h+var_290+8], rax
0x18006ec5a  test    rax, rax
0x18006ec5d  jz      short loc_18006EC79
0x18006ec5f  lea     rdx, aFvecommitchang_0; "FveCommitChanges"
0x18006ec66  mov     rcx, rdi; hModule
0x18006ec69  call    cs:__imp_GetProcAddress
0x18006ec6f  mov     qword ptr [rsp+310h+var_2E0+8], rax
0x18006ec74  test    rax, rax
0x18006ec77  jnz     short loc_18006EC9C
0x18006ec79  call    cs:__imp_GetLastError
0x18006ec7f  mov     ebx, eax
0x18006ec81  test    eax, eax
0x18006ec83  jle     short loc_18006EC8E
0x18006ec85  movzx   ebx, ax
0x18006ec88  or      ebx, 80070000h
0x18006ec8e  mov     rcx, rdi; hLibModule
0x18006ec91  call    cs:__imp_FreeLibrary
0x18006ec97  jmp     loc_18006ED45
0x18006ec9c  lea     rdx, aFvecommitchang; "FveCommitChangesEx"
0x18006eca3  mov     rcx, rdi; hModule
0x18006eca6  call    cs:__imp_GetProcAddress
0x18006ecac  lea     rdx, aFvegetsecurebo; "FveGetSecureBootBindingState"
0x18006ecb3  mov     rcx, rdi; hModule
0x18006ecb6  mov     qword ptr [rsp+310h+var_2D0], rax
0x18006ecbb  call    cs:__imp_GetProcAddress
0x18006ecc1  lea     rdx, aFvecontrol; "FveControl"
0x18006ecc8  mov     rcx, rdi; hModule
0x18006eccb  mov     qword ptr [rbp+210h+var_280], rax
0x18006eccf  call    cs:__imp_GetProcAddress
0x18006ecd5  movaps  xmm0, [rsp+310h+var_2F0]
0x18006ecda  movaps  xmm1, [rsp+310h+var_2E0]
0x18006ecdf  mov     [r14], rdi
0x18006ece2  movups  xmmword ptr [rsi], xmm0
0x18006ece5  movaps  xmm0, [rsp+310h+var_2D0]
0x18006ecea  movups  xmmword ptr [rsi+10h], xmm1
0x18006ecee  movaps  xmm1, [rsp+310h+var_2C0]
0x18006ecf3  movups  xmmword ptr [rsi+20h], xmm0
0x18006ecf7  movaps  xmm0, [rsp+310h+var_2B0]
0x18006ecfc  movups  xmmword ptr [rsi+30h], xmm1
0x18006ed00  movaps  xmm1, [rsp+310h+var_2A0]
0x18006ed05  movups  xmmword ptr [rsi+40h], xmm0
0x18006ed09  movaps  xmm0, [rbp+210h+var_290]
0x18006ed0d  movups  xmmword ptr [rsi+50h], xmm1
0x18006ed11  movaps  xmm1, [rbp+210h+var_280]
0x18006ed15  movups  xmmword ptr [rsi+60h], xmm0
0x18006ed19  movaps  xmm0, [rbp+210h+var_270]
0x18006ed1d  movups  xmmword ptr [rsi+70h], xmm1
0x18006ed21  movaps  xmm1, [rbp+210h+var_260]
0x18006ed25  movups  xmmword ptr [rsi+80h], xmm0
0x18006ed2c  movaps  xmm0, [rbp+210h+var_250]
0x18006ed30  movups  xmmword ptr [rsi+90h], xmm1
0x18006ed37  movups  xmmword ptr [rsi+0A0h], xmm0
0x18006ed3e  mov     [rsi+0B0h], rax
0x18006ed45  mov     eax, ebx
0x18006ed47  mov     rcx, [rbp+210h+var_20]
0x18006ed4e  xor     rcx, rsp; StackCookie
0x18006ed51  call    __security_check_cookie
0x18006ed56  lea     r11, [rsp+310h+var_10]
0x18006ed5e  mov     rbx, [r11+30h]
0x18006ed62  mov     rsi, [r11+38h]
0x18006ed66  mov     rsp, r11
0x18006ed69  pop     r14
0x18006ed6b  pop     rdi
0x18006ed6c  pop     rbp
0x18006ed6d  retn
```
