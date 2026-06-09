# WnpKaDetectorImpl::RegisterWithNCB(void)

- ea: `0x18008e570`
- end: `0x18008eaca`
- name: `?RegisterWithNCB@WnpKaDetectorImpl@@UEAAJXZ`
- size: `1370`
- prototype: `__int64 __fastcall(WnpKaDetectorImpl *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007440`
- `0x180008294`
- `0x18000c8f0`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001c06c`
- `0x18008e570`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e952`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e952`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008e8da`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008e8da`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008e7fa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008e7fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e6d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e83c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e86a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e6d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e83c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e86a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e964`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008e6ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008e6ad`

## string_xrefs

- `0x18008e764`: `\keepaliveprovider.dll`

## pseudocode

```c
__int64 __fastcall WnpKaDetectorImpl::RegisterWithNCB(WnpKaDetectorImpl *this)
{
  PVOID *v2; // rdi
  __int64 v3; // rcx
  signed int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r9
  signed int LastError; // eax
  signed int v8; // eax
  int v9; // eax
  HMODULE Library; // rax
  HMODULE v11; // rbp
  signed int v12; // eax
  bool v13; // sf
  signed int v14; // eax
  signed int v15; // eax
  FARPROC ProcAddress; // r14
  signed int v18; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  bool v21; // sf
  __int64 v22; // r9
  bool v23; // sf
  int v24; // [rsp+20h] [rbp-258h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  memset_0(Buffer, 0, 0x20Au);
  if ( !*((_QWORD *)this + 38) )
  {
    v4 = 0;
    if ( *((_DWORD *)this + 65) )
      goto LABEL_60;
    if ( *((_QWORD *)this + 52) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v3);
    Buffer[0] = 0;
    if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          54,
          &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids,
          (unsigned int)LastError);
      }
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147467259;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x204,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
        (const char *)(unsigned int)v4,
        v24);
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return (unsigned int)v4;
      if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_60;
      v5 = 55;
      goto LABEL_31;
    }
    v9 = StringCchCatW(Buffer, 0x105u, L"\\keepaliveprovider.dll");
    v4 = v9;
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          56,
          &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids,
          (unsigned int)v9);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x208,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
        (const char *)(unsigned int)v4,
        v24);
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return (unsigned int)v4;
      if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_60;
      v5 = 57;
LABEL_31:
      v6 = (unsigned int)v4;
      goto LABEL_13;
    }
    Library = LoadLibraryExW(Buffer, 0, 0);
    v11 = Library;
    if ( !Library )
    {
      v12 = GetLastError();
      v13 = v12 < 0;
      if ( v12 > 0 )
        v13 = 1;
      if ( v13
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = GetLastError();
        if ( v14 > 0 )
          v14 = (unsigned __int16)v14 | 0x80070000;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          58,
          &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids,
          (unsigned int)v14);
      }
LABEL_50:
      v15 = GetLastError();
      v4 = v15;
      if ( v15 > 0 )
        v4 = (unsigned __int16)v15 | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147467259;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x20F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
        (const char *)(unsigned int)v4,
        v24);
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          59,
          &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids,
          (unsigned int)v4);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !v11 )
        goto LABEL_60;
      goto LABEL_58;
    }
    if ( Library == (HMODULE)-1LL )
      goto LABEL_50;
    ProcAddress = GetProcAddress(Library, "KAMSS_RegisterProvider");
    if ( ProcAddress )
      goto LABEL_78;
    v18 = GetLastError();
    v4 = v18;
    if ( v18 > 0 )
      v4 = (unsigned __int16)v18 | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_78:
      v4 = ((__int64 (__fastcall *)(WnpKaDetectorImpl *, _QWORD, unsigned int (__fastcall *)(void *, void *), char *))ProcAddress)(
             this,
             WnpKaDetectorImpl::BeginKeepAliveMeasurement,
             WnpKaDetectorImpl::FinishKeepAliveMeasurement,
             (char *)this + 312);
      v21 = v4 < 0;
      if ( v4 > 0 )
        v21 = 1;
      if ( v21
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( v4 > 0 )
          v22 = (unsigned __int16)v4 | 0x80070000;
        else
          v22 = (unsigned int)v4;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, v22);
      }
      v23 = v4 < 0;
      if ( v4 > 0 )
      {
        v4 = (unsigned __int16)v4 | 0x80070000;
        v23 = v4 < 0;
      }
      if ( !v23 )
      {
        *((_QWORD *)this + 52) = v11;
        goto LABEL_59;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x220,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
        (const char *)(unsigned int)v4,
        (_DWORD)this + 304);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_58;
      v20 = 63;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids,
          (unsigned int)v4);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x217,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
        (const char *)(unsigned int)v4,
        v24);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_58;
      v20 = 61;
    }
    WPP_SF_d(v19[2], v20, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, (unsigned int)v4);
LABEL_58:
    FreeLibrary(v11);
    goto LABEL_59;
  }
  v4 = -2013002764;
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) >= 2u )
    WPP_SF_d(v2[2], 52, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, 2281964532LL);
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x1F4,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
    (const char *)0x880403F4LL,
    v24);
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v5 = 53;
      v6 = 2281964532LL;
LABEL_13:
      WPP_SF_d(v2[2], v5, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, v6);
LABEL_59:
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_60:
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) >= 6u )
      WPP_SF_d(v2[2], 64, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, (unsigned int)v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18008e570  mov     [rsp+arg_8], rbx
0x18008e575  mov     [rsp+arg_10], rbp
0x18008e57a  push    rsi
0x18008e57b  push    rdi
0x18008e57c  push    r13
0x18008e57e  push    r14
0x18008e580  push    r15
0x18008e582  sub     rsp, 250h
0x18008e589  mov     rax, cs:__security_cookie
0x18008e590  xor     rax, rsp
0x18008e593  mov     [rsp+278h+var_38], rax
0x18008e59b  mov     rsi, rcx
0x18008e59e  mov     rdi, cs:WPP_GLOBAL_Control
0x18008e5a5  lea     r13, WPP_GLOBAL_Control
0x18008e5ac  cmp     rdi, r13
0x18008e5af  jz      short loc_18008E5D9
0x18008e5b1  test    byte ptr [rdi+1Ch], 8
0x18008e5b5  jz      short loc_18008E5D9
0x18008e5b7  cmp     byte ptr [rdi+19h], 6
0x18008e5bb  jb      short loc_18008E5D9
0x18008e5bd  mov     rcx, [rdi+10h]
0x18008e5c1  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008e5c8  mov     edx, 33h ; '3'
0x18008e5cd  call    WPP_SF_
0x18008e5d2  mov     rdi, cs:WPP_GLOBAL_Control
0x18008e5d9  xor     edx, edx; Val
0x18008e5db  lea     rcx, [rsp+278h+Buffer]; void *
0x18008e5e0  mov     r8d, 20Ah; Size
0x18008e5e6  call    memset_0
0x18008e5eb  lea     r15, [rsi+130h]
0x18008e5f2  cmp     qword ptr [r15], 0
0x18008e5f6  jz      loc_18008E680
0x18008e5fc  mov     ebx, 880403F4h
0x18008e601  cmp     rdi, r13
0x18008e604  jz      short loc_18008E62A
0x18008e606  test    byte ptr [rdi+1Ch], 8
0x18008e60a  jz      short loc_18008E62A
0x18008e60c  cmp     byte ptr [rdi+19h], 2
0x18008e610  jb      short loc_18008E62A
0x18008e612  mov     rcx, [rdi+10h]
0x18008e616  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008e61d  mov     edx, 34h ; '4'
0x18008e622  mov     r9d, ebx
0x18008e625  call    WPP_SF_d
0x18008e62a  mov     rcx, [rsp+278h]; this
0x18008e632  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008e639  mov     r9d, ebx; char *
0x18008e63c  mov     edx, 1F4h; void *
0x18008e641  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e646  mov     rdi, cs:WPP_GLOBAL_Control
0x18008e64d  cmp     rdi, r13
0x18008e650  jz      loc_18008E910
0x18008e656  test    byte ptr [rdi+1Ch], 80h
0x18008e65a  jz      loc_18008E8E7
0x18008e660  mov     edx, 35h ; '5'
0x18008e665  mov     r9d, 880403F4h
0x18008e66b  mov     rcx, [rdi+10h]
0x18008e66f  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008e676  call    WPP_SF_d
0x18008e67b  jmp     loc_18008E8E0
0x18008e680  xor     ebx, ebx
0x18008e682  cmp     [rsi+104h], ebx
0x18008e688  jnz     loc_18008E8E7
0x18008e68e  cmp     [rsi+1A0h], rbx
0x18008e695  jz      short loc_18008E69C
0x18008e697  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008e69c  xor     eax, eax
0x18008e69e  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x18008e6a3  mov     edx, 104h; uSize
0x18008e6a8  mov     [rsp+278h+Buffer], ax
0x18008e6ad  call    cs:__imp_GetSystemDirectoryW
0x18008e6b3  test    eax, eax
0x18008e6b5  jnz     loc_18008E764
0x18008e6bb  mov     rax, cs:WPP_GLOBAL_Control
0x18008e6c2  mov     edi, 80070000h
0x18008e6c7  cmp     rax, r13
0x18008e6ca  jz      short loc_18008E706
0x18008e6cc  test    byte ptr [rax+1Ch], 8
0x18008e6d0  jz      short loc_18008E706
0x18008e6d2  cmp     byte ptr [rax+19h], 2
0x18008e6d6  jb      short loc_18008E706
0x18008e6d8  call    cs:__imp_GetLastError
0x18008e6de  test    eax, eax
0x18008e6e0  jle     short loc_18008E6E7
0x18008e6e2  movzx   eax, ax
0x18008e6e5  or      eax, edi
0x18008e6e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e6ee  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008e6f5  mov     edx, 36h ; '6'
0x18008e6fa  mov     r9d, eax
0x18008e6fd  mov     rcx, [rcx+10h]
0x18008e701  call    WPP_SF_d
0x18008e706  call    cs:__imp_GetLastError
0x18008e70c  mov     ebx, eax
0x18008e70e  test    eax, eax
0x18008e710  jle     short loc_18008E717
0x18008e712  movzx   ebx, ax
0x18008e715  or      ebx, edi
0x18008e717  mov     rcx, [rsp+278h]; this
0x18008e71f  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008e726  test    ebx, ebx
0x18008e728  mov     eax, 80004005h
0x18008e72d  mov     edx, 204h; void *
0x18008e732  cmovns  ebx, eax
0x18008e735  mov     r9d, ebx; char *
0x18008e738  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e73d  mov     rdi, cs:WPP_GLOBAL_Control
0x18008e744  cmp     rdi, r13
0x18008e747  jz      loc_18008E910
0x18008e74d  test    byte ptr [rdi+1Ch], 80h
0x18008e751  jz      loc_18008E8E7
0x18008e757  mov     edx, 37h ; '7'
0x18008e75c  mov     r9d, ebx
0x18008e75f  jmp     loc_18008E66B
0x18008e764  lea     r8, aKeepaliveprovi; "\\keepaliveprovider.dll"
0x18008e76b  mov     edx, 105h; unsigned __int64
0x18008e770  lea     rcx, [rsp+278h+Buffer]; unsigned __int16 *
0x18008e775  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008e77a  mov     ebx, eax
0x18008e77c  test    eax, eax
0x18008e77e  jns     short loc_18008E7F0
0x18008e780  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e787  cmp     rcx, r13
0x18008e78a  jz      short loc_18008E7B0
0x18008e78c  test    byte ptr [rcx+1Ch], 8
0x18008e790  jz      short loc_18008E7B0
0x18008e792  cmp     byte ptr [rcx+19h], 2
0x18008e796  jb      short loc_18008E7B0
0x18008e798  mov     rcx, [rcx+10h]
0x18008e79c  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008e7a3  mov     edx, 38h ; '8'
0x18008e7a8  mov     r9d, eax
0x18008e7ab  call    WPP_SF_d
0x18008e7b0  mov     rcx, [rsp+278h]; this
0x18008e7b8  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008e7bf  mov     r9d, ebx; char *
0x18008e7c2  mov     edx, 208h; void *
0x18008e7c7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e7cc  mov     rdi, cs:WPP_GLOBAL_Control
0x18008e7d3  cmp     rdi, r13
0x18008e7d6  jz      loc_18008E910
0x18008e7dc  test    byte ptr [rdi+1Ch], 80h
0x18008e7e0  jz      loc_18008E8E7
0x18008e7e6  mov     edx, 39h ; '9'
0x18008e7eb  jmp     loc_18008E75C
0x18008e7f0  xor     r8d, r8d; dwFlags
0x18008e7f3  lea     rcx, [rsp+278h+Buffer]; lpLibFileName
0x18008e7f8  xor     edx, edx; hFile
0x18008e7fa  call    cs:__imp_LoadLibraryExW
0x18008e800  mov     rbp, rax
0x18008e803  mov     edi, 80070000h
0x18008e808  test    rax, rax
0x18008e80b  jnz     loc_18008E93E
0x18008e811  call    cs:__imp_GetLastError
0x18008e817  test    eax, eax
0x18008e819  jle     short loc_18008E822
0x18008e81b  movzx   eax, ax
0x18008e81e  or      eax, edi
0x18008e820  test    eax, eax
0x18008e822  jns     short loc_18008E86A
0x18008e824  mov     rax, cs:WPP_GLOBAL_Control
0x18008e82b  cmp     rax, r13
0x18008e82e  jz      short loc_18008E86A
0x18008e830  test    byte ptr [rax+1Ch], 8
0x18008e834  jz      short loc_18008E86A
0x18008e836  cmp     byte ptr [rax+19h], 2
0x18008e83a  jb      short loc_18008E86A
0x18008e83c  call    cs:__imp_GetLastError
0x18008e842  test    eax, eax
0x18008e844  jle     short loc_18008E84B
0x18008e846  movzx   eax, ax
0x18008e849  or      eax, edi
0x18008e84b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e852  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008e859  mov     edx, 3Ah ; ':'
0x18008e85e  mov     r9d, eax
0x18008e861  mov     rcx, [rcx+10h]
0x18008e865  call    WPP_SF_d
0x18008e86a  call    cs:__imp_GetLastError
0x18008e870  mov     ebx, eax
0x18008e872  test    eax, eax
0x18008e874  jle     short loc_18008E87B
0x18008e876  movzx   ebx, ax
0x18008e879  or      ebx, edi
0x18008e87b  mov     rcx, [rsp+278h]; this
0x18008e883  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008e88a  test    ebx, ebx
0x18008e88c  mov     eax, 80004005h
0x18008e891  mov     edx, 20Fh; void *
0x18008e896  cmovns  ebx, eax
0x18008e899  mov     r9d, ebx; char *
0x18008e89c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e8a1  mov     rdi, cs:WPP_GLOBAL_Control
0x18008e8a8  cmp     rdi, r13
0x18008e8ab  jz      short loc_18008E8D2
0x18008e8ad  test    byte ptr [rdi+1Ch], 80h
0x18008e8b1  jz      short loc_18008E8D2
0x18008e8b3  mov     rcx, [rdi+10h]
0x18008e8b7  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008e8be  mov     edx, 3Bh ; ';'
0x18008e8c3  mov     r9d, ebx
0x18008e8c6  call    WPP_SF_d
0x18008e8cb  mov     rdi, cs:WPP_GLOBAL_Control
0x18008e8d2  test    rbp, rbp
0x18008e8d5  jz      short loc_18008E8E7
0x18008e8d7  mov     rcx, rbp; hLibModule
0x18008e8da  call    cs:__imp_FreeLibrary
0x18008e8e0  mov     rdi, cs:WPP_GLOBAL_Control
0x18008e8e7  cmp     rdi, r13
0x18008e8ea  jz      short loc_18008E910
0x18008e8ec  test    byte ptr [rdi+1Ch], 8
0x18008e8f0  jz      short loc_18008E910
0x18008e8f2  cmp     byte ptr [rdi+19h], 6
0x18008e8f6  jb      short loc_18008E910
0x18008e8f8  mov     rcx, [rdi+10h]
0x18008e8fc  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008e903  mov     edx, 40h ; '@'
0x18008e908  mov     r9d, ebx
0x18008e90b  call    WPP_SF_d
0x18008e910  mov     eax, ebx
0x18008e912  mov     rcx, [rsp+278h+var_38]
0x18008e91a  xor     rcx, rsp; StackCookie
0x18008e91d  call    __security_check_cookie
0x18008e922  lea     r11, [rsp+278h+var_28]
0x18008e92a  mov     rbx, [r11+38h]
0x18008e92e  mov     rbp, [r11+40h]
0x18008e932  mov     rsp, r11
0x18008e935  pop     r15
0x18008e937  pop     r14
0x18008e939  pop     r13
0x18008e93b  pop     rdi
0x18008e93c  pop     rsi
0x18008e93d  retn
0x18008e93e  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18008e942  jz      loc_18008E86A
0x18008e948  lea     rdx, aKamssRegisterp; "KAMSS_RegisterProvider"
0x18008e94f  mov     rcx, rbp; hModule
0x18008e952  call    cs:__imp_GetProcAddress
0x18008e958  mov     r14, rax
0x18008e95b  test    rax, rax
0x18008e95e  jnz     loc_18008EA00
0x18008e964  call    cs:__imp_GetLastError
0x18008e96a  mov     ebx, eax
0x18008e96c  test    eax, eax
0x18008e96e  jle     short loc_18008E975
0x18008e970  movzx   ebx, ax
0x18008e973  or      ebx, edi
0x18008e975  test    ebx, ebx
0x18008e977  jns     loc_18008EA00
0x18008e97d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e984  cmp     rcx, r13
0x18008e987  jz      short loc_18008E9AD
0x18008e989  test    byte ptr [rcx+1Ch], 8
0x18008e98d  jz      short loc_18008E9AD
0x18008e98f  cmp     byte ptr [rcx+19h], 2
0x18008e993  jb      short loc_18008E9AD
0x18008e995  mov     rcx, [rcx+10h]
0x18008e999  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008e9a0  mov     edx, 3Ch ; '<'
0x18008e9a5  mov     r9d, ebx
0x18008e9a8  call    WPP_SF_d
0x18008e9ad  mov     rcx, [rsp+278h]; this
0x18008e9b5  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008e9bc  mov     r9d, ebx; char *
0x18008e9bf  mov     edx, 217h; void *
0x18008e9c4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e9c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e9d0  cmp     rcx, r13
0x18008e9d3  jz      loc_18008E8D7
0x18008e9d9  test    byte ptr [rcx+1Ch], 80h
0x18008e9dd  jz      loc_18008E8D7
0x18008e9e3  mov     edx, 3Dh ; '='
0x18008e9e8  mov     rcx, [rcx+10h]
0x18008e9ec  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008e9f3  mov     r9d, ebx
0x18008e9f6  call    WPP_SF_d
0x18008e9fb  jmp     loc_18008E8D7
0x18008ea00  lea     r9, [rsi+138h]
0x18008ea07  mov     qword ptr [rsp+278h+var_258], r15; int
0x18008ea0c  lea     r8, ?FinishKeepAliveMeasurement@WnpKaDetectorImpl@@SAKPEAX0@Z; WnpKaDetectorImpl::FinishKeepAliveMeasurement(void *,void *)
0x18008ea13  mov     rcx, rsi
0x18008ea16  lea     rdx, ?BeginKeepAliveMeasurement@WnpKaDetectorImpl@@SAKPEAXPEAU_KAMSS_MEASUREMENT_HANDLE@@PEAU_KEEP_ALIVE_SAMPLE_SET@@PEAPEAX@Z; WnpKaDetectorImpl::BeginKeepAliveMeasurement(void *,_KAMSS_MEASUREMENT_HANDLE *,_KEEP_ALIVE_SAMPLE_SET *,void * *)
0x18008ea1d  mov     rax, r14
0x18008ea20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea25  mov     ebx, eax
0x18008ea27  test    eax, eax
0x18008ea29  jle     short loc_18008EA32
0x18008ea2b  movzx   eax, bx
0x18008ea2e  or      eax, edi
0x18008ea30  test    eax, eax
0x18008ea32  jns     short loc_18008EA71
0x18008ea34  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ea3b  cmp     rcx, r13
0x18008ea3e  jz      short loc_18008EA71
0x18008ea40  test    byte ptr [rcx+1Ch], 8
0x18008ea44  jz      short loc_18008EA71
0x18008ea46  cmp     byte ptr [rcx+19h], 2
0x18008ea4a  jb      short loc_18008EA71
0x18008ea4c  test    ebx, ebx
0x18008ea4e  jg      short loc_18008EA55
  ... truncated ...
```
