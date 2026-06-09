# FvepLoadFveAPI

- ea: `0x140051610`
- end: `0x140051926`
- name: `FvepLoadFveAPI`
- size: `790`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140051500`

## callees

- `0x14002e123`
- `0x140051610`
- `0x14005192c`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400516d0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400516d0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140051849`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140051849`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400516e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051706`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051724`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051742`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005175b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051779`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005179d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400517bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400517d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400517ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051808`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051821`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005185e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051873`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051887`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400516e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051706`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051724`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051742`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005175b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051779`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005179d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400517bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400517d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400517ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051808`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051821`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005185e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051873`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005168c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005168c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051831`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140051682`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140051682`

## string_xrefs

- `0x1400516aa`: `\FVEAPI.DLL`
- `0x1400516de`: `FveOpenVolumeW`
- `0x1400517fe`: `FveDeleteAuthMethod`
- `0x140051817`: `FveCommitChanges`
- `0x140051854`: `FveCommitChangesEx`

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
0x140051610  mov     [rsp-8+arg_10], rbx
0x140051615  mov     [rsp-8+arg_18], rsi
0x14005161a  push    rbp
0x14005161b  push    rdi
0x14005161c  push    r14
0x14005161e  lea     rbp, [rsp-200h]
0x140051626  sub     rsp, 300h
0x14005162d  mov     rax, cs:__security_cookie
0x140051634  xor     rax, rsp
0x140051637  mov     [rbp+210h+var_20], rax
0x14005163e  mov     rsi, rdx
0x140051641  mov     r14, rcx
0x140051644  xor     edx, edx; Val
0x140051646  lea     rcx, [rbp+210h+Buffer]; void *
0x14005164a  mov     r8d, 208h; Size
0x140051650  call    memset_0
0x140051655  xor     edx, edx; Val
0x140051657  lea     rcx, [rsp+310h+var_2E0]; void *
0x14005165c  mov     r8d, 0A8h; Size
0x140051662  call    memset_0
0x140051667  mov     ebx, 104h
0x14005166c  mov     qword ptr [r14], 0
0x140051673  mov     edx, ebx; uSize
0x140051675  mov     qword ptr [rsp+310h+var_2F0], 0FFFFFFFFFFFFFFFFh
0x14005167e  lea     rcx, [rbp+210h+Buffer]; lpBuffer
0x140051682  call    cs:__imp_GetSystemDirectoryW
0x140051688  test    eax, eax
0x14005168a  jnz     short loc_1400516AA
0x14005168c  call    cs:__imp_GetLastError
0x140051692  mov     ebx, eax
0x140051694  test    eax, eax
0x140051696  jle     loc_1400518FD
0x14005169c  movzx   ebx, ax
0x14005169f  or      ebx, 80070000h
0x1400516a5  jmp     loc_1400518FD
0x1400516aa  lea     r8, aFveapiDll; "\\FVEAPI.DLL"
0x1400516b1  mov     rdx, rbx; cchDest
0x1400516b4  lea     rcx, [rbp+210h+Buffer]; pszDest
0x1400516b8  call    StringCchCatW
0x1400516bd  mov     ebx, eax
0x1400516bf  test    eax, eax
0x1400516c1  js      loc_1400518FD
0x1400516c7  xor     r8d, r8d; dwFlags
0x1400516ca  lea     rcx, [rbp+210h+Buffer]; lpLibFileName
0x1400516ce  xor     edx, edx; hFile
0x1400516d0  call    cs:__imp_LoadLibraryExW
0x1400516d6  mov     rdi, rax
0x1400516d9  test    rax, rax
0x1400516dc  jz      short loc_14005168C
0x1400516de  lea     rdx, aFveopenvolumew; "FveOpenVolumeW"
0x1400516e5  mov     rcx, rax; hModule
0x1400516e8  call    cs:__imp_GetProcAddress
0x1400516ee  mov     qword ptr [rsp+310h+var_2F0+8], rax
0x1400516f3  mov     rcx, rdi; hModule
0x1400516f6  test    rax, rax
0x1400516f9  jnz     loc_140051796
0x1400516ff  lea     rdx, aFvegetstatusba; "FveGetStatusBasicW"
0x140051706  call    cs:__imp_GetProcAddress
0x14005170c  mov     qword ptr [rsp+310h+var_2C0+8], rax
0x140051711  test    rax, rax
0x140051714  jz      loc_140051831
0x14005171a  lea     rdx, aFvesetfipsallo; "FveSetFipsAllowDisabled"
0x140051721  mov     rcx, rdi; hModule
0x140051724  call    cs:__imp_GetProcAddress
0x14005172a  mov     qword ptr [rsp+310h+var_2B0], rax
0x14005172f  test    rax, rax
0x140051732  jz      loc_140051831
0x140051738  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x14005173f  mov     rcx, rdi; hModule
0x140051742  call    cs:__imp_GetProcAddress
0x140051748  test    rax, rax
0x14005174b  jz      loc_140051831
0x140051751  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x140051758  mov     rcx, rdi; hModule
0x14005175b  call    cs:__imp_GetProcAddress
0x140051761  mov     qword ptr [rsp+310h+var_2B0+8], rax
0x140051766  test    rax, rax
0x140051769  jz      loc_140051831
0x14005176f  lea     rdx, aFveenableauthe; "FveEnableAuthenticationW"
0x140051776  mov     rcx, rdi; hModule
0x140051779  call    cs:__imp_GetProcAddress
0x14005177f  mov     qword ptr [rsp+310h+var_2A0], rax
0x140051784  test    rax, rax
0x140051787  jz      loc_140051831
0x14005178d  mov     rax, [rbp+210h+var_240]
0x140051791  jmp     loc_14005188D
0x140051796  lea     rdx, aFveclosevolume; "FveCloseVolume"
0x14005179d  call    cs:__imp_GetProcAddress
0x1400517a3  mov     qword ptr [rsp+310h+var_2E0], rax
0x1400517a8  test    rax, rax
0x1400517ab  jz      loc_140051831
0x1400517b1  lea     rdx, aFvegetstatus; "FveGetStatus"
0x1400517b8  mov     rcx, rdi; hModule
0x1400517bb  call    cs:__imp_GetProcAddress
0x1400517c1  mov     qword ptr [rsp+310h+var_2C0], rax
0x1400517c6  test    rax, rax
0x1400517c9  jz      short loc_140051831
0x1400517cb  lea     rdx, aFveaddauthmeth; "FveAddAuthMethodInformation"
0x1400517d2  mov     rcx, rdi; hModule
0x1400517d5  call    cs:__imp_GetProcAddress
0x1400517db  mov     qword ptr [rbp+210h+var_290], rax
0x1400517df  test    rax, rax
0x1400517e2  jz      short loc_140051831
0x1400517e4  lea     rdx, aFvegetauthmeth; "FveGetAuthMethodInformation"
0x1400517eb  mov     rcx, rdi; hModule
0x1400517ee  call    cs:__imp_GetProcAddress
0x1400517f4  mov     qword ptr [rsp+310h+var_2A0+8], rax
0x1400517f9  test    rax, rax
0x1400517fc  jz      short loc_140051831
0x1400517fe  lea     rdx, aFvedeleteauthm; "FveDeleteAuthMethod"
0x140051805  mov     rcx, rdi; hModule
0x140051808  call    cs:__imp_GetProcAddress
0x14005180e  mov     qword ptr [rbp+210h+var_290+8], rax
0x140051812  test    rax, rax
0x140051815  jz      short loc_140051831
0x140051817  lea     rdx, aFvecommitchang_0; "FveCommitChanges"
0x14005181e  mov     rcx, rdi; hModule
0x140051821  call    cs:__imp_GetProcAddress
0x140051827  mov     qword ptr [rsp+310h+var_2E0+8], rax
0x14005182c  test    rax, rax
0x14005182f  jnz     short loc_140051854
0x140051831  call    cs:__imp_GetLastError
0x140051837  mov     ebx, eax
0x140051839  test    eax, eax
0x14005183b  jle     short loc_140051846
0x14005183d  movzx   ebx, ax
0x140051840  or      ebx, 80070000h
0x140051846  mov     rcx, rdi; hLibModule
0x140051849  call    cs:__imp_FreeLibrary
0x14005184f  jmp     loc_1400518FD
0x140051854  lea     rdx, aFvecommitchang; "FveCommitChangesEx"
0x14005185b  mov     rcx, rdi; hModule
0x14005185e  call    cs:__imp_GetProcAddress
0x140051864  lea     rdx, aFvegetsecurebo; "FveGetSecureBootBindingState"
0x14005186b  mov     rcx, rdi; hModule
0x14005186e  mov     qword ptr [rsp+310h+var_2D0], rax
0x140051873  call    cs:__imp_GetProcAddress
0x140051879  lea     rdx, aFvecontrol; "FveControl"
0x140051880  mov     rcx, rdi; hModule
0x140051883  mov     qword ptr [rbp+210h+var_280], rax
0x140051887  call    cs:__imp_GetProcAddress
0x14005188d  movaps  xmm0, [rsp+310h+var_2F0]
0x140051892  movaps  xmm1, [rsp+310h+var_2E0]
0x140051897  mov     [r14], rdi
0x14005189a  movups  xmmword ptr [rsi], xmm0
0x14005189d  movaps  xmm0, [rsp+310h+var_2D0]
0x1400518a2  movups  xmmword ptr [rsi+10h], xmm1
0x1400518a6  movaps  xmm1, [rsp+310h+var_2C0]
0x1400518ab  movups  xmmword ptr [rsi+20h], xmm0
0x1400518af  movaps  xmm0, [rsp+310h+var_2B0]
0x1400518b4  movups  xmmword ptr [rsi+30h], xmm1
0x1400518b8  movaps  xmm1, [rsp+310h+var_2A0]
0x1400518bd  movups  xmmword ptr [rsi+40h], xmm0
0x1400518c1  movaps  xmm0, [rbp+210h+var_290]
0x1400518c5  movups  xmmword ptr [rsi+50h], xmm1
0x1400518c9  movaps  xmm1, [rbp+210h+var_280]
0x1400518cd  movups  xmmword ptr [rsi+60h], xmm0
0x1400518d1  movaps  xmm0, [rbp+210h+var_270]
0x1400518d5  movups  xmmword ptr [rsi+70h], xmm1
0x1400518d9  movaps  xmm1, [rbp+210h+var_260]
0x1400518dd  movups  xmmword ptr [rsi+80h], xmm0
0x1400518e4  movaps  xmm0, [rbp+210h+var_250]
0x1400518e8  movups  xmmword ptr [rsi+90h], xmm1
0x1400518ef  movups  xmmword ptr [rsi+0A0h], xmm0
0x1400518f6  mov     [rsi+0B0h], rax
0x1400518fd  mov     eax, ebx
0x1400518ff  mov     rcx, [rbp+210h+var_20]
0x140051906  xor     rcx, rsp; StackCookie
0x140051909  call    __security_check_cookie
0x14005190e  lea     r11, [rsp+310h+var_10]
0x140051916  mov     rbx, [r11+30h]
0x14005191a  mov     rsi, [r11+38h]
0x14005191e  mov     rsp, r11
0x140051921  pop     r14
0x140051923  pop     rdi
0x140051924  pop     rbp
0x140051925  retn
```
