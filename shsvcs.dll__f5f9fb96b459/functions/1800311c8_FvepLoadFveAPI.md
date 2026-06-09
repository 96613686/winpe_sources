# FvepLoadFveAPI

- ea: `0x1800311c8`
- end: `0x1800314de`
- name: `FvepLoadFveAPI`
- size: `790`
- prototype: `__int64 __fastcall(HMODULE *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180030fbc`

## callees

- `0x1800311c8`
- `0x1800314e4`
- `0x180032c6a`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180031288`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180031288`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031401`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031401`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800312a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800312be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800312dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800312fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031313`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031331`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031355`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031373`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003138d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800313a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800313c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800313d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031416`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003142b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003143f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800312a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800312be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800312dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800312fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031313`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031331`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031355`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031373`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003138d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800313a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800313c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800313d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031416`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003142b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003143f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18003123a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18003123a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031244`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800313e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031244`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800313e9`

## string_xrefs

- `0x180031262`: `\FVEAPI.DLL`
- `0x180031296`: `FveOpenVolumeW`
- `0x1800313b6`: `FveDeleteAuthMethod`
- `0x1800313cf`: `FveCommitChanges`
- `0x18003140c`: `FveCommitChangesEx`

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
0x1800311c8  mov     [rsp-8+arg_10], rbx
0x1800311cd  mov     [rsp-8+arg_18], rsi
0x1800311d2  push    rbp
0x1800311d3  push    rdi
0x1800311d4  push    r14
0x1800311d6  lea     rbp, [rsp-200h]
0x1800311de  sub     rsp, 300h
0x1800311e5  mov     rax, cs:__security_cookie
0x1800311ec  xor     rax, rsp
0x1800311ef  mov     [rbp+210h+var_20], rax
0x1800311f6  mov     rsi, rdx
0x1800311f9  mov     r14, rcx
0x1800311fc  xor     edx, edx; Val
0x1800311fe  lea     rcx, [rbp+210h+Buffer]; void *
0x180031202  mov     r8d, 208h; Size
0x180031208  call    memset_0
0x18003120d  xor     edx, edx; Val
0x18003120f  lea     rcx, [rsp+310h+var_2E0]; void *
0x180031214  mov     r8d, 0A8h; Size
0x18003121a  call    memset_0
0x18003121f  mov     ebx, 104h
0x180031224  mov     qword ptr [r14], 0
0x18003122b  mov     edx, ebx; uSize
0x18003122d  mov     qword ptr [rsp+310h+var_2F0], 0FFFFFFFFFFFFFFFFh
0x180031236  lea     rcx, [rbp+210h+Buffer]; lpBuffer
0x18003123a  call    cs:__imp_GetSystemDirectoryW
0x180031240  test    eax, eax
0x180031242  jnz     short loc_180031262
0x180031244  call    cs:__imp_GetLastError
0x18003124a  mov     ebx, eax
0x18003124c  test    eax, eax
0x18003124e  jle     loc_1800314B5
0x180031254  movzx   ebx, ax
0x180031257  or      ebx, 80070000h
0x18003125d  jmp     loc_1800314B5
0x180031262  lea     r8, aFveapiDll; "\\FVEAPI.DLL"
0x180031269  mov     rdx, rbx; cchDest
0x18003126c  lea     rcx, [rbp+210h+Buffer]; pszDest
0x180031270  call    StringCchCatW
0x180031275  mov     ebx, eax
0x180031277  test    eax, eax
0x180031279  js      loc_1800314B5
0x18003127f  xor     r8d, r8d; dwFlags
0x180031282  lea     rcx, [rbp+210h+Buffer]; lpLibFileName
0x180031286  xor     edx, edx; hFile
0x180031288  call    cs:__imp_LoadLibraryExW
0x18003128e  mov     rdi, rax
0x180031291  test    rax, rax
0x180031294  jz      short loc_180031244
0x180031296  lea     rdx, aFveopenvolumew_0; "FveOpenVolumeW"
0x18003129d  mov     rcx, rax; hModule
0x1800312a0  call    cs:__imp_GetProcAddress
0x1800312a6  mov     qword ptr [rsp+310h+var_2F0+8], rax
0x1800312ab  mov     rcx, rdi; hModule
0x1800312ae  test    rax, rax
0x1800312b1  jnz     loc_18003134E
0x1800312b7  lea     rdx, aFvegetstatusba; "FveGetStatusBasicW"
0x1800312be  call    cs:__imp_GetProcAddress
0x1800312c4  mov     qword ptr [rsp+310h+var_2C0+8], rax
0x1800312c9  test    rax, rax
0x1800312cc  jz      loc_1800313E9
0x1800312d2  lea     rdx, aFvesetfipsallo; "FveSetFipsAllowDisabled"
0x1800312d9  mov     rcx, rdi; hModule
0x1800312dc  call    cs:__imp_GetProcAddress
0x1800312e2  mov     qword ptr [rsp+310h+var_2B0], rax
0x1800312e7  test    rax, rax
0x1800312ea  jz      loc_1800313E9
0x1800312f0  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x1800312f7  mov     rcx, rdi; hModule
0x1800312fa  call    cs:__imp_GetProcAddress
0x180031300  test    rax, rax
0x180031303  jz      loc_1800313E9
0x180031309  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x180031310  mov     rcx, rdi; hModule
0x180031313  call    cs:__imp_GetProcAddress
0x180031319  mov     qword ptr [rsp+310h+var_2B0+8], rax
0x18003131e  test    rax, rax
0x180031321  jz      loc_1800313E9
0x180031327  lea     rdx, aFveenableauthe; "FveEnableAuthenticationW"
0x18003132e  mov     rcx, rdi; hModule
0x180031331  call    cs:__imp_GetProcAddress
0x180031337  mov     qword ptr [rsp+310h+var_2A0], rax
0x18003133c  test    rax, rax
0x18003133f  jz      loc_1800313E9
0x180031345  mov     rax, [rbp+210h+var_240]
0x180031349  jmp     loc_180031445
0x18003134e  lea     rdx, aFveclosevolume_0; "FveCloseVolume"
0x180031355  call    cs:__imp_GetProcAddress
0x18003135b  mov     qword ptr [rsp+310h+var_2E0], rax
0x180031360  test    rax, rax
0x180031363  jz      loc_1800313E9
0x180031369  lea     rdx, aFvegetstatus_0; "FveGetStatus"
0x180031370  mov     rcx, rdi; hModule
0x180031373  call    cs:__imp_GetProcAddress
0x180031379  mov     qword ptr [rsp+310h+var_2C0], rax
0x18003137e  test    rax, rax
0x180031381  jz      short loc_1800313E9
0x180031383  lea     rdx, aFveaddauthmeth; "FveAddAuthMethodInformation"
0x18003138a  mov     rcx, rdi; hModule
0x18003138d  call    cs:__imp_GetProcAddress
0x180031393  mov     qword ptr [rbp+210h+var_290], rax
0x180031397  test    rax, rax
0x18003139a  jz      short loc_1800313E9
0x18003139c  lea     rdx, aFvegetauthmeth; "FveGetAuthMethodInformation"
0x1800313a3  mov     rcx, rdi; hModule
0x1800313a6  call    cs:__imp_GetProcAddress
0x1800313ac  mov     qword ptr [rsp+310h+var_2A0+8], rax
0x1800313b1  test    rax, rax
0x1800313b4  jz      short loc_1800313E9
0x1800313b6  lea     rdx, aFvedeleteauthm; "FveDeleteAuthMethod"
0x1800313bd  mov     rcx, rdi; hModule
0x1800313c0  call    cs:__imp_GetProcAddress
0x1800313c6  mov     qword ptr [rbp+210h+var_290+8], rax
0x1800313ca  test    rax, rax
0x1800313cd  jz      short loc_1800313E9
0x1800313cf  lea     rdx, aFvecommitchang_0; "FveCommitChanges"
0x1800313d6  mov     rcx, rdi; hModule
0x1800313d9  call    cs:__imp_GetProcAddress
0x1800313df  mov     qword ptr [rsp+310h+var_2E0+8], rax
0x1800313e4  test    rax, rax
0x1800313e7  jnz     short loc_18003140C
0x1800313e9  call    cs:__imp_GetLastError
0x1800313ef  mov     ebx, eax
0x1800313f1  test    eax, eax
0x1800313f3  jle     short loc_1800313FE
0x1800313f5  movzx   ebx, ax
0x1800313f8  or      ebx, 80070000h
0x1800313fe  mov     rcx, rdi; hLibModule
0x180031401  call    cs:__imp_FreeLibrary
0x180031407  jmp     loc_1800314B5
0x18003140c  lea     rdx, aFvecommitchang; "FveCommitChangesEx"
0x180031413  mov     rcx, rdi; hModule
0x180031416  call    cs:__imp_GetProcAddress
0x18003141c  lea     rdx, aFvegetsecurebo; "FveGetSecureBootBindingState"
0x180031423  mov     rcx, rdi; hModule
0x180031426  mov     qword ptr [rsp+310h+var_2D0], rax
0x18003142b  call    cs:__imp_GetProcAddress
0x180031431  lea     rdx, aFvecontrol; "FveControl"
0x180031438  mov     rcx, rdi; hModule
0x18003143b  mov     qword ptr [rbp+210h+var_280], rax
0x18003143f  call    cs:__imp_GetProcAddress
0x180031445  movaps  xmm0, [rsp+310h+var_2F0]
0x18003144a  movaps  xmm1, [rsp+310h+var_2E0]
0x18003144f  mov     [r14], rdi
0x180031452  movups  xmmword ptr [rsi], xmm0
0x180031455  movaps  xmm0, [rsp+310h+var_2D0]
0x18003145a  movups  xmmword ptr [rsi+10h], xmm1
0x18003145e  movaps  xmm1, [rsp+310h+var_2C0]
0x180031463  movups  xmmword ptr [rsi+20h], xmm0
0x180031467  movaps  xmm0, [rsp+310h+var_2B0]
0x18003146c  movups  xmmword ptr [rsi+30h], xmm1
0x180031470  movaps  xmm1, [rsp+310h+var_2A0]
0x180031475  movups  xmmword ptr [rsi+40h], xmm0
0x180031479  movaps  xmm0, [rbp+210h+var_290]
0x18003147d  movups  xmmword ptr [rsi+50h], xmm1
0x180031481  movaps  xmm1, [rbp+210h+var_280]
0x180031485  movups  xmmword ptr [rsi+60h], xmm0
0x180031489  movaps  xmm0, [rbp+210h+var_270]
0x18003148d  movups  xmmword ptr [rsi+70h], xmm1
0x180031491  movaps  xmm1, [rbp+210h+var_260]
0x180031495  movups  xmmword ptr [rsi+80h], xmm0
0x18003149c  movaps  xmm0, [rbp+210h+var_250]
0x1800314a0  movups  xmmword ptr [rsi+90h], xmm1
0x1800314a7  movups  xmmword ptr [rsi+0A0h], xmm0
0x1800314ae  mov     [rsi+0B0h], rax
0x1800314b5  mov     eax, ebx
0x1800314b7  mov     rcx, [rbp+210h+var_20]
0x1800314be  xor     rcx, rsp; StackCookie
0x1800314c1  call    __security_check_cookie
0x1800314c6  lea     r11, [rsp+310h+var_10]
0x1800314ce  mov     rbx, [r11+30h]
0x1800314d2  mov     rsi, [r11+38h]
0x1800314d6  mov     rsp, r11
0x1800314d9  pop     r14
0x1800314db  pop     rdi
0x1800314dc  pop     rbp
0x1800314dd  retn
```
