# FvepLoadFveAPI

- ea: `0x1800427f0`
- end: `0x180042b06`
- name: `FvepLoadFveAPI`
- size: `790`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800425a4`

## callees

- `0x1800323e0`
- `0x1800427f0`
- `0x18007ec9a`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180042862`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180042862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004286c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004286c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a11`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800428b0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800428b0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042a29`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042a29`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800428c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800428e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042904`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042922`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004293b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042959`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004297d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004299b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800429b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800429ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800429e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042a01`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042a3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042a53`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042a67`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800428c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800428e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042904`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042922`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004293b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042959`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004297d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004299b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800429b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800429ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800429e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042a01`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042a3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042a53`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042a67`

## string_xrefs

- `0x1800428be`: `FveOpenVolumeW`
- `0x180042a34`: `FveCommitChangesEx`
- `0x1800429f7`: `FveCommitChanges`
- `0x18004288a`: `\FVEAPI.DLL`
- `0x1800429de`: `FveDeleteAuthMethod`

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
0x1800427f0  mov     [rsp-8+arg_10], rbx
0x1800427f5  mov     [rsp-8+arg_18], rsi
0x1800427fa  push    rbp
0x1800427fb  push    rdi
0x1800427fc  push    r14
0x1800427fe  lea     rbp, [rsp-200h]
0x180042806  sub     rsp, 300h
0x18004280d  mov     rax, cs:__security_cookie
0x180042814  xor     rax, rsp
0x180042817  mov     [rbp+210h+var_20], rax
0x18004281e  mov     rsi, rdx
0x180042821  mov     r14, rcx
0x180042824  xor     edx, edx; Val
0x180042826  lea     rcx, [rbp+210h+Buffer]; void *
0x18004282a  mov     r8d, 208h; Size
0x180042830  call    memset_0
0x180042835  xor     edx, edx; Val
0x180042837  lea     rcx, [rsp+310h+var_2E0]; void *
0x18004283c  mov     r8d, 0A8h; Size
0x180042842  call    memset_0
0x180042847  mov     ebx, 104h
0x18004284c  mov     qword ptr [r14], 0
0x180042853  mov     edx, ebx; uSize
0x180042855  mov     qword ptr [rsp+310h+var_2F0], 0FFFFFFFFFFFFFFFFh
0x18004285e  lea     rcx, [rbp+210h+Buffer]; lpBuffer
0x180042862  call    cs:__imp_GetSystemDirectoryW
0x180042868  test    eax, eax
0x18004286a  jnz     short loc_18004288A
0x18004286c  call    cs:__imp_GetLastError
0x180042872  mov     ebx, eax
0x180042874  test    eax, eax
0x180042876  jle     loc_180042ADD
0x18004287c  movzx   ebx, ax
0x18004287f  or      ebx, 80070000h
0x180042885  jmp     loc_180042ADD
0x18004288a  lea     r8, aFveapiDll; "\\FVEAPI.DLL"
0x180042891  mov     rdx, rbx; cchDest
0x180042894  lea     rcx, [rbp+210h+Buffer]; pszDest
0x180042898  call    StringCchCatW
0x18004289d  mov     ebx, eax
0x18004289f  test    eax, eax
0x1800428a1  js      loc_180042ADD
0x1800428a7  xor     r8d, r8d; dwFlags
0x1800428aa  lea     rcx, [rbp+210h+Buffer]; lpLibFileName
0x1800428ae  xor     edx, edx; hFile
0x1800428b0  call    cs:__imp_LoadLibraryExW
0x1800428b6  mov     rdi, rax
0x1800428b9  test    rax, rax
0x1800428bc  jz      short loc_18004286C
0x1800428be  lea     rdx, aFveopenvolumew; "FveOpenVolumeW"
0x1800428c5  mov     rcx, rax; hModule
0x1800428c8  call    cs:__imp_GetProcAddress
0x1800428ce  mov     qword ptr [rsp+310h+var_2F0+8], rax
0x1800428d3  mov     rcx, rdi; hModule
0x1800428d6  test    rax, rax
0x1800428d9  jnz     loc_180042976
0x1800428df  lea     rdx, aFvegetstatusba; "FveGetStatusBasicW"
0x1800428e6  call    cs:__imp_GetProcAddress
0x1800428ec  mov     qword ptr [rsp+310h+var_2C0+8], rax
0x1800428f1  test    rax, rax
0x1800428f4  jz      loc_180042A11
0x1800428fa  lea     rdx, aFvesetfipsallo; "FveSetFipsAllowDisabled"
0x180042901  mov     rcx, rdi; hModule
0x180042904  call    cs:__imp_GetProcAddress
0x18004290a  mov     qword ptr [rsp+310h+var_2B0], rax
0x18004290f  test    rax, rax
0x180042912  jz      loc_180042A11
0x180042918  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x18004291f  mov     rcx, rdi; hModule
0x180042922  call    cs:__imp_GetProcAddress
0x180042928  test    rax, rax
0x18004292b  jz      loc_180042A11
0x180042931  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x180042938  mov     rcx, rdi; hModule
0x18004293b  call    cs:__imp_GetProcAddress
0x180042941  mov     qword ptr [rsp+310h+var_2B0+8], rax
0x180042946  test    rax, rax
0x180042949  jz      loc_180042A11
0x18004294f  lea     rdx, aFveenableauthe; "FveEnableAuthenticationW"
0x180042956  mov     rcx, rdi; hModule
0x180042959  call    cs:__imp_GetProcAddress
0x18004295f  mov     qword ptr [rsp+310h+var_2A0], rax
0x180042964  test    rax, rax
0x180042967  jz      loc_180042A11
0x18004296d  mov     rax, [rbp+210h+var_240]
0x180042971  jmp     loc_180042A6D
0x180042976  lea     rdx, aFveclosevolume; "FveCloseVolume"
0x18004297d  call    cs:__imp_GetProcAddress
0x180042983  mov     qword ptr [rsp+310h+var_2E0], rax
0x180042988  test    rax, rax
0x18004298b  jz      loc_180042A11
0x180042991  lea     rdx, aFvegetstatus; "FveGetStatus"
0x180042998  mov     rcx, rdi; hModule
0x18004299b  call    cs:__imp_GetProcAddress
0x1800429a1  mov     qword ptr [rsp+310h+var_2C0], rax
0x1800429a6  test    rax, rax
0x1800429a9  jz      short loc_180042A11
0x1800429ab  lea     rdx, aFveaddauthmeth; "FveAddAuthMethodInformation"
0x1800429b2  mov     rcx, rdi; hModule
0x1800429b5  call    cs:__imp_GetProcAddress
0x1800429bb  mov     qword ptr [rbp+210h+var_290], rax
0x1800429bf  test    rax, rax
0x1800429c2  jz      short loc_180042A11
0x1800429c4  lea     rdx, aFvegetauthmeth; "FveGetAuthMethodInformation"
0x1800429cb  mov     rcx, rdi; hModule
0x1800429ce  call    cs:__imp_GetProcAddress
0x1800429d4  mov     qword ptr [rsp+310h+var_2A0+8], rax
0x1800429d9  test    rax, rax
0x1800429dc  jz      short loc_180042A11
0x1800429de  lea     rdx, aFvedeleteauthm; "FveDeleteAuthMethod"
0x1800429e5  mov     rcx, rdi; hModule
0x1800429e8  call    cs:__imp_GetProcAddress
0x1800429ee  mov     qword ptr [rbp+210h+var_290+8], rax
0x1800429f2  test    rax, rax
0x1800429f5  jz      short loc_180042A11
0x1800429f7  lea     rdx, aFvecommitchang_0; "FveCommitChanges"
0x1800429fe  mov     rcx, rdi; hModule
0x180042a01  call    cs:__imp_GetProcAddress
0x180042a07  mov     qword ptr [rsp+310h+var_2E0+8], rax
0x180042a0c  test    rax, rax
0x180042a0f  jnz     short loc_180042A34
0x180042a11  call    cs:__imp_GetLastError
0x180042a17  mov     ebx, eax
0x180042a19  test    eax, eax
0x180042a1b  jle     short loc_180042A26
0x180042a1d  movzx   ebx, ax
0x180042a20  or      ebx, 80070000h
0x180042a26  mov     rcx, rdi; hLibModule
0x180042a29  call    cs:__imp_FreeLibrary
0x180042a2f  jmp     loc_180042ADD
0x180042a34  lea     rdx, aFvecommitchang; "FveCommitChangesEx"
0x180042a3b  mov     rcx, rdi; hModule
0x180042a3e  call    cs:__imp_GetProcAddress
0x180042a44  lea     rdx, aFvegetsecurebo; "FveGetSecureBootBindingState"
0x180042a4b  mov     rcx, rdi; hModule
0x180042a4e  mov     qword ptr [rsp+310h+var_2D0], rax
0x180042a53  call    cs:__imp_GetProcAddress
0x180042a59  lea     rdx, aFvecontrol; "FveControl"
0x180042a60  mov     rcx, rdi; hModule
0x180042a63  mov     qword ptr [rbp+210h+var_280], rax
0x180042a67  call    cs:__imp_GetProcAddress
0x180042a6d  movaps  xmm0, [rsp+310h+var_2F0]
0x180042a72  movaps  xmm1, [rsp+310h+var_2E0]
0x180042a77  mov     [r14], rdi
0x180042a7a  movups  xmmword ptr [rsi], xmm0
0x180042a7d  movaps  xmm0, [rsp+310h+var_2D0]
0x180042a82  movups  xmmword ptr [rsi+10h], xmm1
0x180042a86  movaps  xmm1, [rsp+310h+var_2C0]
0x180042a8b  movups  xmmword ptr [rsi+20h], xmm0
0x180042a8f  movaps  xmm0, [rsp+310h+var_2B0]
0x180042a94  movups  xmmword ptr [rsi+30h], xmm1
0x180042a98  movaps  xmm1, [rsp+310h+var_2A0]
0x180042a9d  movups  xmmword ptr [rsi+40h], xmm0
0x180042aa1  movaps  xmm0, [rbp+210h+var_290]
0x180042aa5  movups  xmmword ptr [rsi+50h], xmm1
0x180042aa9  movaps  xmm1, [rbp+210h+var_280]
0x180042aad  movups  xmmword ptr [rsi+60h], xmm0
0x180042ab1  movaps  xmm0, [rbp+210h+var_270]
0x180042ab5  movups  xmmword ptr [rsi+70h], xmm1
0x180042ab9  movaps  xmm1, [rbp+210h+var_260]
0x180042abd  movups  xmmword ptr [rsi+80h], xmm0
0x180042ac4  movaps  xmm0, [rbp+210h+var_250]
0x180042ac8  movups  xmmword ptr [rsi+90h], xmm1
0x180042acf  movups  xmmword ptr [rsi+0A0h], xmm0
0x180042ad6  mov     [rsi+0B0h], rax
0x180042add  mov     eax, ebx
0x180042adf  mov     rcx, [rbp+210h+var_20]
0x180042ae6  xor     rcx, rsp; StackCookie
0x180042ae9  call    __security_check_cookie
0x180042aee  lea     r11, [rsp+310h+var_10]
0x180042af6  mov     rbx, [r11+30h]
0x180042afa  mov     rsi, [r11+38h]
0x180042afe  mov     rsp, r11
0x180042b01  pop     r14
0x180042b03  pop     rdi
0x180042b04  pop     rbp
0x180042b05  retn
```
