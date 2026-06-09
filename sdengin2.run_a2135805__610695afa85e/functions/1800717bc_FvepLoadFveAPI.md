# FvepLoadFveAPI

- ea: `0x1800717bc`
- end: `0x180071b4b`
- name: `FvepLoadFveAPI`
- size: `911`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800715a8`

## callees

- `0x1800717bc`
- `0x180071b54`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180071888`
- `KERNEL32!LoadLibraryExW` at `0x180071888`
- `KERNEL32!FreeLibrary` at `0x180071a55`
- `KERNEL32!FreeLibrary` at `0x180071a55`
- `KERNEL32!GetSystemDirectoryW` at `0x18007182e`
- `KERNEL32!GetSystemDirectoryW` at `0x18007182e`
- `KERNEL32!GetProcAddress` at `0x1800718a6`
- `KERNEL32!GetProcAddress` at `0x1800718ca`
- `KERNEL32!GetProcAddress` at `0x1800718ee`
- `KERNEL32!GetProcAddress` at `0x180071912`
- `KERNEL32!GetProcAddress` at `0x180071931`
- `KERNEL32!GetProcAddress` at `0x180071955`
- `KERNEL32!GetProcAddress` at `0x18007197f`
- `KERNEL32!GetProcAddress` at `0x1800719a3`
- `KERNEL32!GetProcAddress` at `0x1800719c3`
- `KERNEL32!GetProcAddress` at `0x1800719e2`
- `KERNEL32!GetProcAddress` at `0x180071a02`
- `KERNEL32!GetProcAddress` at `0x180071a21`
- `KERNEL32!GetProcAddress` at `0x180071a70`
- `KERNEL32!GetProcAddress` at `0x180071a8b`
- `KERNEL32!GetProcAddress` at `0x180071aa5`
- `KERNEL32!GetProcAddress` at `0x1800718a6`
- `KERNEL32!GetProcAddress` at `0x1800718ca`
- `KERNEL32!GetProcAddress` at `0x1800718ee`
- `KERNEL32!GetProcAddress` at `0x180071912`
- `KERNEL32!GetProcAddress` at `0x180071931`
- `KERNEL32!GetProcAddress` at `0x180071955`
- `KERNEL32!GetProcAddress` at `0x18007197f`
- `KERNEL32!GetProcAddress` at `0x1800719a3`
- `KERNEL32!GetProcAddress` at `0x1800719c3`
- `KERNEL32!GetProcAddress` at `0x1800719e2`
- `KERNEL32!GetProcAddress` at `0x180071a02`
- `KERNEL32!GetProcAddress` at `0x180071a21`
- `KERNEL32!GetProcAddress` at `0x180071a70`
- `KERNEL32!GetProcAddress` at `0x180071a8b`
- `KERNEL32!GetProcAddress` at `0x180071aa5`
- `KERNEL32!GetLastError` at `0x18007183e`
- `KERNEL32!GetLastError` at `0x180071a37`
- `KERNEL32!GetLastError` at `0x18007183e`
- `KERNEL32!GetLastError` at `0x180071a37`

## string_xrefs

- `0x180071862`: `\FVEAPI.DLL`
- `0x18007189c`: `FveOpenVolumeW`
- `0x1800719f8`: `FveDeleteAuthMethod`
- `0x180071a17`: `FveCommitChanges`
- `0x180071a66`: `FveCommitChangesEx`

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
0x1800717bc  mov     [rsp-8+arg_10], rbx
0x1800717c1  mov     [rsp-8+arg_18], rsi
0x1800717c6  push    rbp
0x1800717c7  push    rdi
0x1800717c8  push    r14
0x1800717ca  lea     rbp, [rsp-200h]
0x1800717d2  sub     rsp, 300h
0x1800717d9  mov     rax, cs:__security_cookie
0x1800717e0  xor     rax, rsp
0x1800717e3  mov     [rbp+210h+var_20], rax
0x1800717ea  mov     rsi, rdx
0x1800717ed  mov     r14, rcx
0x1800717f0  xor     edx, edx; Val
0x1800717f2  lea     rcx, [rbp+210h+Buffer]; void *
0x1800717f6  mov     r8d, 208h; Size
0x1800717fc  call    memset_0
0x180071801  xor     edx, edx; Val
0x180071803  lea     rcx, [rsp+310h+var_2E0]; void *
0x180071808  mov     r8d, 0A8h; Size
0x18007180e  call    memset_0
0x180071813  mov     ebx, 104h
0x180071818  mov     qword ptr [r14], 0
0x18007181f  mov     edx, ebx; uSize
0x180071821  mov     qword ptr [rsp+310h+var_2F0], 0FFFFFFFFFFFFFFFFh
0x18007182a  lea     rcx, [rbp+210h+Buffer]; lpBuffer
0x18007182e  call    cs:__imp_GetSystemDirectoryW
0x180071835  nop     dword ptr [rax+rax+00h]
0x18007183a  test    eax, eax
0x18007183c  jnz     short loc_180071862
0x18007183e  call    cs:__imp_GetLastError
0x180071845  nop     dword ptr [rax+rax+00h]
0x18007184a  mov     ebx, eax
0x18007184c  test    eax, eax
0x18007184e  jle     loc_180071B21
0x180071854  movzx   ebx, ax
0x180071857  or      ebx, 80070000h
0x18007185d  jmp     loc_180071B21
0x180071862  lea     r8, aFveapiDll_0; "\\FVEAPI.DLL"
0x180071869  mov     rdx, rbx; cchDest
0x18007186c  lea     rcx, [rbp+210h+Buffer]; pszDest
0x180071870  call    StringCchCatW
0x180071875  mov     ebx, eax
0x180071877  test    eax, eax
0x180071879  js      loc_180071B21
0x18007187f  xor     r8d, r8d; dwFlags
0x180071882  lea     rcx, [rbp+210h+Buffer]; lpLibFileName
0x180071886  xor     edx, edx; hFile
0x180071888  call    cs:__imp_LoadLibraryExW
0x18007188f  nop     dword ptr [rax+rax+00h]
0x180071894  mov     rdi, rax
0x180071897  test    rax, rax
0x18007189a  jz      short loc_18007183E
0x18007189c  lea     rdx, aFveopenvolumew; "FveOpenVolumeW"
0x1800718a3  mov     rcx, rax; hModule
0x1800718a6  call    cs:__imp_GetProcAddress
0x1800718ad  nop     dword ptr [rax+rax+00h]
0x1800718b2  mov     qword ptr [rsp+310h+var_2F0+8], rax
0x1800718b7  mov     rcx, rdi; hModule
0x1800718ba  test    rax, rax
0x1800718bd  jnz     loc_180071978
0x1800718c3  lea     rdx, aFvegetstatusba; "FveGetStatusBasicW"
0x1800718ca  call    cs:__imp_GetProcAddress
0x1800718d1  nop     dword ptr [rax+rax+00h]
0x1800718d6  mov     qword ptr [rsp+310h+var_2C0+8], rax
0x1800718db  test    rax, rax
0x1800718de  jz      loc_180071A37
0x1800718e4  lea     rdx, aFvesetfipsallo; "FveSetFipsAllowDisabled"
0x1800718eb  mov     rcx, rdi; hModule
0x1800718ee  call    cs:__imp_GetProcAddress
0x1800718f5  nop     dword ptr [rax+rax+00h]
0x1800718fa  mov     qword ptr [rsp+310h+var_2B0], rax
0x1800718ff  test    rax, rax
0x180071902  jz      loc_180071A37
0x180071908  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x18007190f  mov     rcx, rdi; hModule
0x180071912  call    cs:__imp_GetProcAddress
0x180071919  nop     dword ptr [rax+rax+00h]
0x18007191e  test    rax, rax
0x180071921  jz      loc_180071A37
0x180071927  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x18007192e  mov     rcx, rdi; hModule
0x180071931  call    cs:__imp_GetProcAddress
0x180071938  nop     dword ptr [rax+rax+00h]
0x18007193d  mov     qword ptr [rsp+310h+var_2B0+8], rax
0x180071942  test    rax, rax
0x180071945  jz      loc_180071A37
0x18007194b  lea     rdx, aFveenableauthe; "FveEnableAuthenticationW"
0x180071952  mov     rcx, rdi; hModule
0x180071955  call    cs:__imp_GetProcAddress
0x18007195c  nop     dword ptr [rax+rax+00h]
0x180071961  mov     qword ptr [rsp+310h+var_2A0], rax
0x180071966  test    rax, rax
0x180071969  jz      loc_180071A37
0x18007196f  mov     rax, [rbp+210h+var_240]
0x180071973  jmp     loc_180071AB1
0x180071978  lea     rdx, aFveclosevolume; "FveCloseVolume"
0x18007197f  call    cs:__imp_GetProcAddress
0x180071986  nop     dword ptr [rax+rax+00h]
0x18007198b  mov     qword ptr [rsp+310h+var_2E0], rax
0x180071990  test    rax, rax
0x180071993  jz      loc_180071A37
0x180071999  lea     rdx, aFvegetstatus; "FveGetStatus"
0x1800719a0  mov     rcx, rdi; hModule
0x1800719a3  call    cs:__imp_GetProcAddress
0x1800719aa  nop     dword ptr [rax+rax+00h]
0x1800719af  mov     qword ptr [rsp+310h+var_2C0], rax
0x1800719b4  test    rax, rax
0x1800719b7  jz      short loc_180071A37
0x1800719b9  lea     rdx, aFveaddauthmeth; "FveAddAuthMethodInformation"
0x1800719c0  mov     rcx, rdi; hModule
0x1800719c3  call    cs:__imp_GetProcAddress
0x1800719ca  nop     dword ptr [rax+rax+00h]
0x1800719cf  mov     qword ptr [rbp+210h+var_290], rax
0x1800719d3  test    rax, rax
0x1800719d6  jz      short loc_180071A37
0x1800719d8  lea     rdx, aFvegetauthmeth; "FveGetAuthMethodInformation"
0x1800719df  mov     rcx, rdi; hModule
0x1800719e2  call    cs:__imp_GetProcAddress
0x1800719e9  nop     dword ptr [rax+rax+00h]
0x1800719ee  mov     qword ptr [rsp+310h+var_2A0+8], rax
0x1800719f3  test    rax, rax
0x1800719f6  jz      short loc_180071A37
0x1800719f8  lea     rdx, aFvedeleteauthm; "FveDeleteAuthMethod"
0x1800719ff  mov     rcx, rdi; hModule
0x180071a02  call    cs:__imp_GetProcAddress
0x180071a09  nop     dword ptr [rax+rax+00h]
0x180071a0e  mov     qword ptr [rbp+210h+var_290+8], rax
0x180071a12  test    rax, rax
0x180071a15  jz      short loc_180071A37
0x180071a17  lea     rdx, aFvecommitchang_0; "FveCommitChanges"
0x180071a1e  mov     rcx, rdi; hModule
0x180071a21  call    cs:__imp_GetProcAddress
0x180071a28  nop     dword ptr [rax+rax+00h]
0x180071a2d  mov     qword ptr [rsp+310h+var_2E0+8], rax
0x180071a32  test    rax, rax
0x180071a35  jnz     short loc_180071A66
0x180071a37  call    cs:__imp_GetLastError
0x180071a3e  nop     dword ptr [rax+rax+00h]
0x180071a43  mov     ebx, eax
0x180071a45  test    eax, eax
0x180071a47  jle     short loc_180071A52
0x180071a49  movzx   ebx, ax
0x180071a4c  or      ebx, 80070000h
0x180071a52  mov     rcx, rdi; hLibModule
0x180071a55  call    cs:__imp_FreeLibrary
0x180071a5c  nop     dword ptr [rax+rax+00h]
0x180071a61  jmp     loc_180071B21
0x180071a66  lea     rdx, aFvecommitchang; "FveCommitChangesEx"
0x180071a6d  mov     rcx, rdi; hModule
0x180071a70  call    cs:__imp_GetProcAddress
0x180071a77  nop     dword ptr [rax+rax+00h]
0x180071a7c  lea     rdx, aFvegetsecurebo; "FveGetSecureBootBindingState"
0x180071a83  mov     rcx, rdi; hModule
0x180071a86  mov     qword ptr [rsp+310h+var_2D0], rax
0x180071a8b  call    cs:__imp_GetProcAddress
0x180071a92  nop     dword ptr [rax+rax+00h]
0x180071a97  lea     rdx, aFvecontrol; "FveControl"
0x180071a9e  mov     rcx, rdi; hModule
0x180071aa1  mov     qword ptr [rbp+210h+var_280], rax
0x180071aa5  call    cs:__imp_GetProcAddress
0x180071aac  nop     dword ptr [rax+rax+00h]
0x180071ab1  movaps  xmm0, [rsp+310h+var_2F0]
0x180071ab6  movaps  xmm1, [rsp+310h+var_2E0]
0x180071abb  mov     [r14], rdi
0x180071abe  movups  xmmword ptr [rsi], xmm0
0x180071ac1  movaps  xmm0, [rsp+310h+var_2D0]
0x180071ac6  movups  xmmword ptr [rsi+10h], xmm1
0x180071aca  movaps  xmm1, [rsp+310h+var_2C0]
0x180071acf  movups  xmmword ptr [rsi+20h], xmm0
0x180071ad3  movaps  xmm0, [rsp+310h+var_2B0]
0x180071ad8  movups  xmmword ptr [rsi+30h], xmm1
0x180071adc  movaps  xmm1, [rsp+310h+var_2A0]
0x180071ae1  movups  xmmword ptr [rsi+40h], xmm0
0x180071ae5  movaps  xmm0, [rbp+210h+var_290]
0x180071ae9  movups  xmmword ptr [rsi+50h], xmm1
0x180071aed  movaps  xmm1, [rbp+210h+var_280]
0x180071af1  movups  xmmword ptr [rsi+60h], xmm0
0x180071af5  movaps  xmm0, [rbp+210h+var_270]
0x180071af9  movups  xmmword ptr [rsi+70h], xmm1
0x180071afd  movaps  xmm1, [rbp+210h+var_260]
0x180071b01  movups  xmmword ptr [rsi+80h], xmm0
0x180071b08  movaps  xmm0, [rbp+210h+var_250]
0x180071b0c  movups  xmmword ptr [rsi+90h], xmm1
0x180071b13  movups  xmmword ptr [rsi+0A0h], xmm0
0x180071b1a  mov     [rsi+0B0h], rax
0x180071b21  mov     eax, ebx
0x180071b23  mov     rcx, [rbp+210h+var_20]
0x180071b2a  xor     rcx, rsp; StackCookie
0x180071b2d  call    __security_check_cookie
0x180071b32  lea     r11, [rsp+310h+var_10]
0x180071b3a  mov     rbx, [r11+30h]
0x180071b3e  mov     rsi, [r11+38h]
0x180071b42  mov     rsp, r11
0x180071b45  pop     r14
0x180071b47  pop     rdi
0x180071b48  pop     rbp
0x180071b49  retn
```
