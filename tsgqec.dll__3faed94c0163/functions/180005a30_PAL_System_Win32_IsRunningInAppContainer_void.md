# PAL_System_Win32_IsRunningInAppContainer(void)

- ea: `0x180005a30`
- end: `0x180005da5`
- name: `?PAL_System_Win32_IsRunningInAppContainer@@YAHXZ`
- size: `885`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000aac4`

## callees

- `0x180001008`
- `0x180001120`
- `0x180001344`
- `0x180003970`
- `0x1800053ec`
- `0x180005a30`
- `0x18000ae79`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005d14`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005d14`
- `KERNEL32!FreeLibrary` at `0x180005d92`
- `KERNEL32!FreeLibrary` at `0x180005d92`
- `KERNEL32!GetProcAddress` at `0x180005ac9`
- `KERNEL32!GetProcAddress` at `0x180005ac9`
- `KERNEL32!GetLastError` at `0x180005a77`
- `KERNEL32!GetLastError` at `0x180005ab4`
- `KERNEL32!GetLastError` at `0x180005af6`
- `KERNEL32!GetLastError` at `0x180005b26`
- `KERNEL32!GetLastError` at `0x180005a77`
- `KERNEL32!GetLastError` at `0x180005ab4`
- `KERNEL32!GetLastError` at `0x180005af6`
- `KERNEL32!GetLastError` at `0x180005b26`
- `KERNEL32!LoadLibraryW` at `0x180005a4a`
- `KERNEL32!LoadLibraryW` at `0x180005a4a`

## string_xrefs

- `0x180005b80`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x180005c13`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x180005c7f`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x180005d40`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x180005a40`: `kernel32.dll`
- `0x180005b92`: `GetCurrentPackageFamilyName(1st attempt) failed, we are likely loaded in a classic process: 0x%x`

## pseudocode

```c
__int64 PAL_System_Win32_IsRunningInAppContainer(void)
{
  unsigned int v0; // edi
  HMODULE LibraryW; // rax
  HMODULE v2; // rsi
  signed int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v7)(unsigned int *, void *); // rbx
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v10; // eax
  int v11; // r8d
  int v12; // r9d
  unsigned int v13; // ecx
  __int16 *v14; // rdx
  const char *v15; // rax
  void *v16; // rax
  void *v17; // r14
  int v18; // ebx
  unsigned int v19; // eax
  const char *v21; // [rsp+50h] [rbp-20h] BYREF
  const char *v22; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v23[2]; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v24; // [rsp+A0h] [rbp+30h] BYREF
  int v25; // [rsp+A8h] [rbp+38h] BYREF
  int v26; // [rsp+B0h] [rbp+40h] BYREF
  const char *v27; // [rsp+B8h] [rbp+48h] BYREF

  v0 = 0;
  v24 = 0;
  LibraryW = LoadLibraryW(L"kernel32.dll");
  v2 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "GetCurrentPackageFamilyName");
    v7 = (__int64 (__fastcall *)(unsigned int *, void *))ProcAddress;
    if ( !ProcAddress )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
          CurrentThreadActivityIdPrefix,
          LastError);
      }
      GetLastError();
      goto LABEL_37;
    }
    v10 = ((__int64 (__fastcall *)(unsigned int *, _QWORD))ProcAddress)(&v24, 0);
    v13 = v10;
    if ( v10 )
    {
      if ( v10 != 122 )
      {
        if ( v10 > 0 )
          v13 = (unsigned __int16)v10 | 0x80070000;
        if ( (unsigned int)dword_180013020 > 2 )
        {
          v25 = v13;
          v21 = "PAL_System_Win32_IsRunningInAppContainer";
          v26 = 1634;
          v22 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
          v23[0] = "GetCurrentPackageFamilyName(1st attempt) failed, we are likely loaded in a classic process: 0x%x";
          LODWORD(v27) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v13,
            (unsigned int)byte_180010E8B,
            v11,
            v12,
            (__int64)v23,
            (__int64)&v27,
            (__int64)&v22,
            (__int64)&v26,
            (__int64)&v21,
            (__int64)&v25);
        }
        goto LABEL_37;
      }
      if ( v24 )
      {
        v16 = operator new(saturated_mul(v24, 2u));
        v17 = v16;
        if ( v16 )
        {
          memset_0(v16, 0, 2LL * v24);
          v18 = v7(&v24, v17);
          if ( v18 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v19 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                33,
                WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
                v19,
                v18);
            }
          }
          else
          {
            v0 = 1;
          }
          operator delete(v17);
          goto LABEL_37;
        }
        if ( (unsigned int)dword_180013020 > 2 )
        {
          v25 = 1657;
          v27 = "PAL_System_Win32_IsRunningInAppContainer";
          v14 = (__int16 *)&dword_180010ED4;
          v26 = -2147024882;
          v23[0] = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
          v15 = "Could not allocate space for the package family name";
          goto LABEL_36;
        }
      }
      else if ( (unsigned int)dword_180013020 > 2 )
      {
        v25 = 1647;
        v27 = "PAL_System_Win32_IsRunningInAppContainer";
        v14 = &word_180010E46;
        v26 = -2147467259;
        v23[0] = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
        v15 = "Null package family monikor name size.Quitting.";
LABEL_36:
        v22 = v15;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v13,
          (_DWORD)v14,
          v11,
          v12,
          (__int64)&v22,
          (__int64)&v26,
          (__int64)v23,
          (__int64)&v25,
          (__int64)&v27);
      }
    }
    else if ( (unsigned int)dword_180013020 > 2 )
    {
      v25 = 1642;
      v27 = "PAL_System_Win32_IsRunningInAppContainer";
      v14 = (__int16 *)byte_180010E01;
      v26 = -2147418113;
      v23[0] = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
      v15 = "GetCurrentPackageFamilyName returned success, expected INSUFFICIENT_BUFFER";
      goto LABEL_36;
    }
LABEL_37:
    FreeLibrary(v2);
    return v0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v5 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_c585fe5194613b5687849eb156704f7c_Traceguids, v5, v4);
  }
  GetLastError();
  return v0;
}

```

## disassembly

```asm
0x180005a30  push    rbp
0x180005a32  push    rbx
0x180005a33  push    rsi
0x180005a34  push    rdi
0x180005a35  push    r14
0x180005a37  mov     rbp, rsp
0x180005a3a  sub     rsp, 70h
0x180005a3e  xor     edi, edi
0x180005a40  lea     rcx, LibFileName; "kernel32.dll"
0x180005a47  mov     [rbp+arg_0], edi
0x180005a4a  call    cs:__imp_LoadLibraryW
0x180005a50  mov     rsi, rax
0x180005a53  test    rax, rax
0x180005a56  jnz     short loc_180005ABF
0x180005a58  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a5f  lea     rax, WPP_GLOBAL_Control
0x180005a66  cmp     rcx, rax
0x180005a69  jz      short loc_180005AB4
0x180005a6b  test    byte ptr [rcx+1Ch], 8
0x180005a6f  jz      short loc_180005AB4
0x180005a71  cmp     byte ptr [rcx+19h], 2
0x180005a75  jb      short loc_180005AB4
0x180005a77  call    cs:__imp_GetLastError
0x180005a7d  mov     ebx, eax
0x180005a7f  test    eax, eax
0x180005a81  jle     short loc_180005A8C
0x180005a83  movzx   ebx, ax
0x180005a86  or      ebx, 80070000h
0x180005a8c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180005a91  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a98  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x180005a9f  mov     edx, 1Fh
0x180005aa4  mov     dword ptr [rsp+70h+var_50], ebx
0x180005aa8  mov     r9d, eax
0x180005aab  mov     rcx, [rcx+10h]
0x180005aaf  call    WPP_SF_Dd
0x180005ab4  call    cs:__imp_GetLastError
0x180005aba  jmp     loc_180005D98
0x180005abf  lea     rdx, aGetcurrentpack_0; "GetCurrentPackageFamilyName"
0x180005ac6  mov     rcx, rsi; hModule
0x180005ac9  call    cs:__imp_GetProcAddress
0x180005acf  mov     rbx, rax
0x180005ad2  test    rax, rax
0x180005ad5  jnz     short loc_180005B31
0x180005ad7  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ade  lea     rax, WPP_GLOBAL_Control
0x180005ae5  cmp     rcx, rax
0x180005ae8  jz      short loc_180005B26
0x180005aea  test    byte ptr [rcx+1Ch], 8
0x180005aee  jz      short loc_180005B26
0x180005af0  cmp     byte ptr [rcx+19h], 2
0x180005af4  jb      short loc_180005B26
0x180005af6  call    cs:__imp_GetLastError
0x180005afc  mov     ebx, eax
0x180005afe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180005b03  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b0a  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x180005b11  mov     edx, 20h ; ' '
0x180005b16  mov     dword ptr [rsp+70h+var_50], ebx
0x180005b1a  mov     r9d, eax
0x180005b1d  mov     rcx, [rcx+10h]
0x180005b21  call    WPP_SF_Dd
0x180005b26  call    cs:__imp_GetLastError
0x180005b2c  jmp     loc_180005D8F
0x180005b31  xor     edx, edx
0x180005b33  lea     rcx, [rbp+arg_0]
0x180005b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b3c  mov     ecx, eax
0x180005b3e  test    eax, eax
0x180005b40  jz      loc_180005D1C
0x180005b46  cmp     eax, 7Ah ; 'z'
0x180005b49  jz      loc_180005BE4
0x180005b4f  test    eax, eax
0x180005b51  jle     short loc_180005B5C
0x180005b53  movzx   ecx, ax
0x180005b56  or      ecx, 80070000h
0x180005b5c  mov     eax, cs:dword_180013020
0x180005b62  cmp     eax, 2
0x180005b65  jbe     loc_180005D8F
0x180005b6b  lea     rax, aPalSystemWin32; "PAL_System_Win32_IsRunningInAppContaine"...
0x180005b72  mov     [rbp+arg_8], ecx
0x180005b75  mov     [rbp+var_20], rax
0x180005b79  lea     rdx, byte_180010E8B
0x180005b80  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180005b87  mov     [rbp+arg_10], 662h
0x180005b8e  mov     [rbp+var_18], rax
0x180005b92  lea     rax, aGetcurrentpack; "GetCurrentPackageFamilyName(1st attempt"...
0x180005b99  mov     [rbp+var_10], rax
0x180005b9d  lea     rax, [rbp+arg_8]
0x180005ba1  mov     [rsp+70h+var_28], rax
0x180005ba6  lea     rax, [rbp+var_20]
0x180005baa  mov     [rsp+70h+var_30], rax
0x180005baf  lea     rax, [rbp+arg_10]
0x180005bb3  mov     [rsp+70h+var_38], rax
0x180005bb8  lea     rax, [rbp+var_18]
0x180005bbc  mov     [rsp+70h+var_40], rax
0x180005bc1  lea     rax, [rbp+arg_18]
0x180005bc5  mov     [rsp+70h+var_48], rax
0x180005bca  lea     rax, [rbp+var_10]
0x180005bce  mov     [rsp+70h+var_50], rax
0x180005bd3  mov     dword ptr [rbp+arg_18], 80004005h
0x180005bda  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180005bdf  jmp     loc_180005D8F
0x180005be4  mov     eax, [rbp+arg_0]
0x180005be7  test    eax, eax
0x180005be9  jnz     short loc_180005C31
0x180005beb  mov     eax, cs:dword_180013020
0x180005bf1  cmp     eax, 2
0x180005bf4  jbe     loc_180005D8F
0x180005bfa  lea     rax, aPalSystemWin32; "PAL_System_Win32_IsRunningInAppContaine"...
0x180005c01  mov     [rbp+arg_8], 66Fh
0x180005c08  mov     [rbp+arg_18], rax
0x180005c0c  lea     rdx, word_180010E46
0x180005c13  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180005c1a  mov     [rbp+arg_10], 80004005h
0x180005c21  mov     [rbp+var_10], rax
0x180005c25  lea     rax, aNullPackageFam; "Null package family monikor name size.Q"...
0x180005c2c  jmp     loc_180005D59
0x180005c31  mov     rcx, rax
0x180005c34  mov     eax, 2
0x180005c39  mul     rcx
0x180005c3c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005c43  cmovb   rax, rcx
0x180005c47  mov     rcx, rax; Size
0x180005c4a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005c4f  mov     r14, rax
0x180005c52  test    rax, rax
0x180005c55  jnz     short loc_180005C9D
0x180005c57  mov     eax, cs:dword_180013020
0x180005c5d  cmp     eax, 2
0x180005c60  jbe     loc_180005D8F
0x180005c66  lea     rax, aPalSystemWin32; "PAL_System_Win32_IsRunningInAppContaine"...
0x180005c6d  mov     [rbp+arg_8], 679h
0x180005c74  mov     [rbp+arg_18], rax
0x180005c78  lea     rdx, dword_180010ED4
0x180005c7f  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180005c86  mov     [rbp+arg_10], 8007000Eh
0x180005c8d  mov     [rbp+var_10], rax
0x180005c91  lea     rax, aCouldNotAlloca; "Could not allocate space for the packag"...
0x180005c98  jmp     loc_180005D59
0x180005c9d  mov     r8d, [rbp+arg_0]
0x180005ca1  xor     edx, edx; Val
0x180005ca3  add     r8, r8; Size
0x180005ca6  mov     rcx, r14; void *
0x180005ca9  call    memset_0
0x180005cae  mov     rdx, r14
0x180005cb1  lea     rcx, [rbp+arg_0]
0x180005cb5  mov     rax, rbx
0x180005cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cbd  mov     ebx, eax
0x180005cbf  test    eax, eax
0x180005cc1  jz      short loc_180005D0C
0x180005cc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180005cca  lea     rax, WPP_GLOBAL_Control
0x180005cd1  cmp     rcx, rax
0x180005cd4  jz      short loc_180005D11
0x180005cd6  test    byte ptr [rcx+1Ch], 8
0x180005cda  jz      short loc_180005D11
0x180005cdc  cmp     byte ptr [rcx+19h], 2
0x180005ce0  jb      short loc_180005D11
0x180005ce2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180005ce7  mov     rcx, cs:WPP_GLOBAL_Control
0x180005cee  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x180005cf5  mov     edx, 21h ; '!'
0x180005cfa  mov     dword ptr [rsp+70h+var_50], ebx
0x180005cfe  mov     r9d, eax
0x180005d01  mov     rcx, [rcx+10h]
0x180005d05  call    WPP_SF_Dd
0x180005d0a  jmp     short loc_180005D11
0x180005d0c  mov     edi, 1
0x180005d11  mov     rcx, r14
0x180005d14  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005d1a  jmp     short loc_180005D8F
0x180005d1c  mov     eax, cs:dword_180013020
0x180005d22  cmp     eax, 2
0x180005d25  jbe     short loc_180005D8F
0x180005d27  lea     rax, aPalSystemWin32; "PAL_System_Win32_IsRunningInAppContaine"...
0x180005d2e  mov     [rbp+arg_8], 66Ah
0x180005d35  mov     [rbp+arg_18], rax
0x180005d39  lea     rdx, byte_180010E01
0x180005d40  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180005d47  mov     [rbp+arg_10], 8000FFFFh
0x180005d4e  mov     [rbp+var_10], rax
0x180005d52  lea     rax, aGetcurrentpack_1; "GetCurrentPackageFamilyName returned su"...
0x180005d59  mov     [rbp+var_18], rax
0x180005d5d  lea     rax, [rbp+arg_18]
0x180005d61  mov     [rsp+70h+var_30], rax
0x180005d66  lea     rax, [rbp+arg_8]
0x180005d6a  mov     [rsp+70h+var_38], rax
0x180005d6f  lea     rax, [rbp+var_10]
0x180005d73  mov     [rsp+70h+var_40], rax
0x180005d78  lea     rax, [rbp+arg_10]
0x180005d7c  mov     [rsp+70h+var_48], rax
0x180005d81  lea     rax, [rbp+var_18]
0x180005d85  mov     [rsp+70h+var_50], rax
0x180005d8a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180005d8f  mov     rcx, rsi; hLibModule
0x180005d92  call    cs:__imp_FreeLibrary
0x180005d98  mov     eax, edi
0x180005d9a  add     rsp, 70h
0x180005d9e  pop     r14
0x180005da0  pop     rdi
0x180005da1  pop     rsi
0x180005da2  pop     rbx
0x180005da3  pop     rbp
0x180005da4  retn
```
