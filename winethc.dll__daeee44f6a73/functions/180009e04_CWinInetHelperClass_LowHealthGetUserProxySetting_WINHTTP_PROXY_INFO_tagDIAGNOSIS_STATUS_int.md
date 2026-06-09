# CWinInetHelperClass::LowHealthGetUserProxySetting(_WINHTTP_PROXY_INFO *,tagDIAGNOSIS_STATUS *,int *)

- ea: `0x180009e04`
- end: `0x18000a224`
- name: `?LowHealthGetUserProxySetting@CWinInetHelperClass@@AEAAJPEAU_WINHTTP_PROXY_INFO@@PEAW4tagDIAGNOSIS_STATUS@@PEAH@Z`
- size: `1056`
- prototype: `__int64 __fastcall(CWinInetHelperClass *__hidden this, struct _WINHTTP_PROXY_INFO *, enum tagDIAGNOSIS_STATUS *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180008ec0`

## callees

- `0x1800048cc`
- `0x180009ae4`
- `0x180009e04`
- `0x18000dfe8`
- `0x18000e230`
- `0x180012d6e`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a010`
- `KERNEL32!GetLastError` at `0x18000a010`
- `KERNEL32!GetProcAddress` at `0x18000a0ad`
- `KERNEL32!GetProcAddress` at `0x18000a0ad`
- `KERNEL32!GetModuleHandleW` at `0x180009ffb`
- `KERNEL32!GetModuleHandleW` at `0x180009ffb`

## string_xrefs

- `0x180009ff4`: `winhttp.dll`
- `0x180009ef6`: `The user has no proxy configured.`
- `0x18000a1d4`: `The user has no manual proxy configured and proxy auto-detection failed.`

## pseudocode

```c
__int64 __fastcall CWinInetHelperClass::LowHealthGetUserProxySetting(
        CWinInetHelperClass *this,
        struct _WINHTTP_PROXY_INFO *a2,
        enum tagDIAGNOSIS_STATUS *a3,
        int *a4)
{
  int UserProxyConfig; // edi
  __int64 v8; // r12
  __int64 v9; // rcx
  char *v10; // r14
  enum tagDIAGNOSIS_STATUS *v11; // r8
  unsigned int (*v12)(const struct _WINHTTP_PROXY_INFO *, const unsigned __int16 *, int, unsigned __int16, int *); // r10
  unsigned __int16 v13; // di
  unsigned int v14; // r14d
  HMODULE ModuleHandleW; // rax
  signed int LastError; // eax
  char *v17; // r14
  __int64 v18; // rcx
  char *v19; // rax
  enum tagDIAGNOSIS_STATUS *v20; // r8
  bool v21; // zf
  unsigned int (*ProcAddress)(const struct _WINHTTP_PROXY_INFO *, const unsigned __int16 *, int, unsigned __int16, int *); // rax
  __int64 v23; // r8
  bool v24; // sf
  __int64 v25; // rax
  __int64 v26; // r9
  __int64 v27; // r8
  __int64 v28; // rcx
  __int64 v29; // rbx
  __int64 v30; // rcx
  int v32[4]; // [rsp+30h] [rbp-79h] BYREF
  char v33[192]; // [rsp+40h] [rbp-69h] BYREF
  __int64 v34; // [rsp+110h] [rbp+67h] BYREF
  enum tagDIAGNOSIS_STATUS *v35; // [rsp+120h] [rbp+77h]

  v35 = a3;
  LODWORD(v34) = 1;
  memset_0(v33, 0, 0x90u);
  v32[0] = 0;
  *(_OWORD *)a2 = 0;
  *((_QWORD *)a2 + 2) = 0;
  UserProxyConfig = GetUserProxyConfig((WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *)((char *)this + 4856));
  if ( UserProxyConfig < 0 )
    return (unsigned int)UserProxyConfig;
  UserProxyConfig = GetDirectAccessInfo(
                      (PCWSTR)this + 60,
                      *((struct INDFEtw **)this + 602),
                      (DNS_PROXY_INFORMATION **)this + 639,
                      v32,
                      a2);
  if ( UserProxyConfig < 0 )
    return (unsigned int)UserProxyConfig;
  if ( v32[0] )
  {
    *((_DWORD *)this + 790) = *(_DWORD *)(*((_QWORD *)this + 639) + 4LL) != 0;
    return (unsigned int)UserProxyConfig;
  }
  v8 = 32;
  if ( *((_DWORD *)this + 1214) )
  {
    v10 = (char *)this + 4920;
    v18 = 32;
    v19 = (char *)this + 4920;
    do
    {
      *v19++ = 0;
      --v18;
    }
    while ( v18 );
    v20 = v35;
    *(_DWORD *)v10 = 1;
    *((_DWORD *)this + 1231) = 3;
    *((_DWORD *)this + 1237) = 1;
    UserProxyConfig = CWinInetHelperClass::LowHealthGetUserAutoProxyConfig(this, a2, v20, (int *)&v34, a4);
    if ( UserProxyConfig < 0 || *((_DWORD *)this + 1275) || *a4 )
      return (unsigned int)UserProxyConfig;
    if ( (_DWORD)v34 )
    {
LABEL_27:
      v21 = *(_DWORD *)a2 == 1;
      goto LABEL_43;
    }
  }
  else
  {
    if ( !*((_QWORD *)this + 608) && !*((_QWORD *)this + 609) )
    {
      v9 = *((_QWORD *)this + 602);
      *((_DWORD *)this + 790) = 0;
      if ( v9 )
        (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v9 + 24LL))(
          v9,
          2,
          0,
          L"WinInetHelperClass",
          L"The user has no proxy configured.");
      return (unsigned int)UserProxyConfig;
    }
    v10 = (char *)this + 4920;
  }
  *((_DWORD *)this + 1222) = 1;
  if ( *((_QWORD *)this + 608) )
  {
    do
    {
      *v10++ = 0;
      --v8;
    }
    while ( v8 );
    v11 = v35;
    *((_QWORD *)this + 616) = *((_QWORD *)this + 608);
    *((_QWORD *)this + 615) = 2;
    *((_DWORD *)this + 1237) = 1;
    UserProxyConfig = CWinInetHelperClass::LowHealthGetUserAutoProxyConfig(this, a2, v11, (int *)&v34, a4);
    if ( UserProxyConfig < 0 || *((_DWORD *)this + 1275) || *a4 )
      return (unsigned int)UserProxyConfig;
    if ( (_DWORD)v34 )
      goto LABEL_27;
  }
  if ( *((_QWORD *)this + 609) )
  {
    v12 = g_pfnWinHttpIsHostInProxyBypassList;
    *(_DWORD *)a2 = 3;
    *((_QWORD *)a2 + 1) = *((_QWORD *)this + 609);
    *((_QWORD *)a2 + 2) = *((_QWORD *)this + 610);
    v13 = *((_WORD *)this + 572);
    v14 = *((_DWORD *)this + 287);
    if ( !v12 )
    {
      ModuleHandleW = GetModuleHandleW(L"winhttp.dll");
      if ( !ModuleHandleW
        || (ProcAddress = (unsigned int (*)(const struct _WINHTTP_PROXY_INFO *, const unsigned __int16 *, int, unsigned __int16, int *))GetProcAddress(ModuleHandleW, "Private1"),
            (v12 = ProcAddress) == 0) )
      {
        LastError = GetLastError();
        v17 = (char *)this + 120;
LABEL_31:
        UserProxyConfig = LastError;
        v24 = LastError < 0;
        if ( LastError > 0 )
        {
          UserProxyConfig = (unsigned __int16)LastError | 0x80070000;
          v24 = 1;
        }
        if ( !v24 )
        {
          v21 = *((_QWORD *)this + 602) == 0;
          *((_DWORD *)this + 790) = *((_DWORD *)this + 789) == 0;
          if ( !v21 )
          {
            v25 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
            v26 = *((_QWORD *)a2 + 2);
            v27 = *((_QWORD *)a2 + 1);
            v21 = *((_DWORD *)this + 789) == 0;
            v34 = v25 + 24;
            if ( v21 )
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                &v34,
                L"User's manual proxy string: '%s';  Bypass list: '%s'",
                v27,
                v26);
            else
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                &v34,
                L"User's manual proxy string: '%s'; Bypass list: '%s'; Host %s is on bypass list",
                v27,
                v26,
                v17);
            v28 = *((_QWORD *)this + 602);
            v29 = v34;
            (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, __int64))(*(_QWORD *)v28 + 24LL))(
              v28,
              2,
              0,
              L"WinInetHelperClass",
              v34);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v29 - 24 + 16), 0xFFFFFFFF) <= 1 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v29 - 24) + 8LL))(*(_QWORD *)(v29 - 24));
          }
        }
        return (unsigned int)UserProxyConfig;
      }
      g_pfnWinHttpIsHostInProxyBypassList = ProcAddress;
    }
    v23 = v14;
    v17 = (char *)this + 120;
    LastError = ((__int64 (__fastcall *)(struct _WINHTTP_PROXY_INFO *, char *, __int64, _QWORD, char *))v12)(
                  a2,
                  (char *)this + 120,
                  v23,
                  v13,
                  (char *)this + 3156);
    goto LABEL_31;
  }
  v30 = *((_QWORD *)this + 602);
  if ( v30 )
    (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v30 + 24LL))(
      v30,
      2,
      0,
      L"WinInetHelperClass",
      L"The user has no manual proxy configured and proxy auto-detection failed.");
  v21 = *((_DWORD *)this + 793) == 0;
LABEL_43:
  if ( v21 )
    *((_DWORD *)this + 790) = 0;
  return (unsigned int)UserProxyConfig;
}

```

## disassembly

```asm
0x180009e04  mov     [rsp-8+arg_8], rbx
0x180009e09  mov     [rsp-8+arg_10], r8
0x180009e0e  push    rbp
0x180009e0f  push    rsi
0x180009e10  push    rdi
0x180009e11  push    r12
0x180009e13  push    r13
0x180009e15  push    r14
0x180009e17  push    r15
0x180009e19  lea     rbp, [rsp-27h]
0x180009e1e  sub     rsp, 0D0h
0x180009e25  mov     rsi, rdx
0x180009e28  mov     dword ptr [rbp+57h+arg_0], 1
0x180009e2f  mov     rbx, rcx
0x180009e32  xor     edx, edx; Val
0x180009e34  lea     rcx, [rbp+57h+var_C0]; void *
0x180009e38  mov     r8d, 90h; Size
0x180009e3e  mov     r13, r9
0x180009e41  call    memset_0
0x180009e46  xorps   xmm0, xmm0
0x180009e49  mov     [rbp+57h+var_D0], 0
0x180009e50  xor     eax, eax
0x180009e52  lea     r15, [rbx+12F8h]
0x180009e59  movups  xmmword ptr [rsi], xmm0
0x180009e5c  mov     rcx, r15; struct _WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *
0x180009e5f  mov     [rsi+10h], rax
0x180009e63  call    ?GetUserProxyConfig@@YAJPEAU_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG@@@Z; GetUserProxyConfig(_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *)
0x180009e68  mov     edi, eax
0x180009e6a  test    eax, eax
0x180009e6c  js      loc_18000A206
0x180009e72  mov     rdx, [rbx+12D0h]; struct INDFEtw *
0x180009e79  lea     r14, [rbx+13F8h]
0x180009e80  mov     r8, r14; struct DIRECT_ACCESS_QUERY **
0x180009e83  mov     [rsp+100h+var_E0], rsi; struct _WINHTTP_PROXY_INFO *
0x180009e88  lea     rcx, [rbx+78h]; hostName
0x180009e8c  lea     r9, [rbp+57h+var_D0]; int *
0x180009e90  call    ?GetDirectAccessInfo@@YAJPEBGPEAUINDFEtw@@PEAPEAVDIRECT_ACCESS_QUERY@@PEAHPEAU_WINHTTP_PROXY_INFO@@@Z; GetDirectAccessInfo(ushort const *,INDFEtw *,DIRECT_ACCESS_QUERY * *,int *,_WINHTTP_PROXY_INFO *)
0x180009e95  xor     edx, edx
0x180009e97  mov     edi, eax
0x180009e99  test    eax, eax
0x180009e9b  js      loc_18000A206
0x180009ea1  cmp     [rbp+57h+var_D0], edx
0x180009ea4  jz      short loc_180009EBC
0x180009ea6  mov     rax, [r14]
0x180009ea9  mov     ecx, edx
0x180009eab  cmp     [rax+4], edx
0x180009eae  setnz   cl
0x180009eb1  mov     [rbx+0C58h], ecx
0x180009eb7  jmp     loc_18000A206
0x180009ebc  mov     r12d, 20h ; ' '
0x180009ec2  cmp     [r15], edx
0x180009ec5  jnz     loc_18000A025
0x180009ecb  cmp     [rbx+1300h], rdx
0x180009ed2  jnz     short loc_180009F1F
0x180009ed4  cmp     [rbx+1308h], rdx
0x180009edb  jnz     short loc_180009F1F
0x180009edd  mov     rcx, [rbx+12D0h]
0x180009ee4  mov     [rbx+0C58h], edx
0x180009eea  test    rcx, rcx
0x180009eed  jz      loc_18000A206
0x180009ef3  mov     rax, [rcx]
0x180009ef6  lea     rdx, aTheUserHasNoPr; "The user has no proxy configured."
0x180009efd  mov     [rsp+100h+var_E0], rdx
0x180009f02  lea     r9, aWininethelperc; "WinInetHelperClass"
0x180009f09  xor     r8d, r8d
0x180009f0c  lea     edx, [r12-1Eh]
0x180009f11  mov     rax, [rax+18h]
0x180009f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f1a  jmp     loc_18000A206
0x180009f1f  lea     r14, [rbx+1338h]
0x180009f26  mov     r15d, 2
0x180009f2c  mov     dword ptr [rbx+1318h], 1
0x180009f36  cmp     [rbx+1300h], rdx
0x180009f3d  jz      short loc_180009FAD
0x180009f3f  mov     [r14], dl
0x180009f42  inc     r14
0x180009f45  sub     r12, 1
0x180009f49  jnz     short loc_180009F3F
0x180009f4b  mov     rax, [rbx+1300h]
0x180009f52  lea     r9, [rbp+57h+arg_0]; int *
0x180009f56  mov     r8, [rbp+57h+arg_10]; enum tagDIAGNOSIS_STATUS *
0x180009f5a  mov     rdx, rsi; struct _WINHTTP_PROXY_INFO *
0x180009f5d  mov     rcx, rbx; this
0x180009f60  mov     [rbx+1340h], rax
0x180009f67  mov     [rbx+1338h], r15
0x180009f6e  mov     dword ptr [rbx+1354h], 1
0x180009f78  mov     [rsp+100h+var_E0], r13; int *
0x180009f7d  call    ?LowHealthGetUserAutoProxyConfig@CWinInetHelperClass@@AEAAJPEAU_WINHTTP_PROXY_INFO@@PEAW4tagDIAGNOSIS_STATUS@@PEAH2@Z; CWinInetHelperClass::LowHealthGetUserAutoProxyConfig(_WINHTTP_PROXY_INFO *,tagDIAGNOSIS_STATUS *,int *,int *)
0x180009f82  xor     edx, edx
0x180009f84  mov     edi, eax
0x180009f86  test    eax, eax
0x180009f88  js      loc_18000A206
0x180009f8e  cmp     [rbx+13ECh], edx
0x180009f94  jnz     loc_18000A206
0x180009f9a  cmp     [r13+0], edx
0x180009f9e  jnz     loc_18000A206
0x180009fa4  cmp     dword ptr [rbp+57h+arg_0], edx
0x180009fa7  jnz     loc_18000A09B
0x180009fad  cmp     [rbx+1308h], rdx
0x180009fb4  jz      loc_18000A1C5
0x180009fba  mov     r10, cs:?g_pfnWinHttpIsHostInProxyBypassList@@3P6AKPEBU_WINHTTP_PROXY_INFO@@PEBGHGPEAH@ZEA; ulong (*g_pfnWinHttpIsHostInProxyBypassList)(_WINHTTP_PROXY_INFO const *,ushort const *,int,ushort,int *)
0x180009fc1  mov     dword ptr [rsi], 3
0x180009fc7  mov     rax, [rbx+1308h]
0x180009fce  mov     [rsi+8], rax
0x180009fd2  mov     rax, [rbx+1310h]
0x180009fd9  mov     [rsi+10h], rax
0x180009fdd  movzx   edi, word ptr [rbx+478h]
0x180009fe4  mov     r14d, [rbx+47Ch]
0x180009feb  test    r10, r10
0x180009fee  jnz     loc_18000A0CC
0x180009ff4  lea     rcx, aWinhttpDll_0; "winhttp.dll"
0x180009ffb  call    cs:__imp_GetModuleHandleW
0x18000a002  nop     dword ptr [rax+rax+00h]
0x18000a007  test    rax, rax
0x18000a00a  jnz     loc_18000A0A3
0x18000a010  call    cs:__imp_GetLastError
0x18000a017  nop     dword ptr [rax+rax+00h]
0x18000a01c  lea     r14, [rbx+78h]
0x18000a020  jmp     loc_18000A0F1
0x18000a025  lea     r14, [rbx+1338h]
0x18000a02c  mov     rcx, r12
0x18000a02f  mov     rax, r14
0x18000a032  mov     [rax], dl
0x18000a034  inc     rax
0x18000a037  sub     rcx, 1
0x18000a03b  jnz     short loc_18000A032
0x18000a03d  mov     r8, [rbp+57h+arg_10]; enum tagDIAGNOSIS_STATUS *
0x18000a041  lea     r9, [rbp+57h+arg_0]; int *
0x18000a045  mov     rdx, rsi; struct _WINHTTP_PROXY_INFO *
0x18000a048  mov     dword ptr [r14], 1
0x18000a04f  mov     rcx, rbx; this
0x18000a052  mov     dword ptr [rbx+133Ch], 3
0x18000a05c  mov     dword ptr [rbx+1354h], 1
0x18000a066  mov     [rsp+100h+var_E0], r13; int *
0x18000a06b  call    ?LowHealthGetUserAutoProxyConfig@CWinInetHelperClass@@AEAAJPEAU_WINHTTP_PROXY_INFO@@PEAW4tagDIAGNOSIS_STATUS@@PEAH2@Z; CWinInetHelperClass::LowHealthGetUserAutoProxyConfig(_WINHTTP_PROXY_INFO *,tagDIAGNOSIS_STATUS *,int *,int *)
0x18000a070  xor     edx, edx
0x18000a072  mov     edi, eax
0x18000a074  test    eax, eax
0x18000a076  js      loc_18000A206
0x18000a07c  cmp     [rbx+13ECh], edx
0x18000a082  jnz     loc_18000A206
0x18000a088  cmp     [r13+0], edx
0x18000a08c  jnz     loc_18000A206
0x18000a092  cmp     dword ptr [rbp+57h+arg_0], edx
0x18000a095  jz      loc_180009F26
0x18000a09b  cmp     dword ptr [rsi], 1
0x18000a09e  jmp     loc_18000A1FE
0x18000a0a3  lea     rdx, aPrivate1; "Private1"
0x18000a0aa  mov     rcx, rax; hModule
0x18000a0ad  call    cs:__imp_GetProcAddress
0x18000a0b4  nop     dword ptr [rax+rax+00h]
0x18000a0b9  mov     r10, rax
0x18000a0bc  test    rax, rax
0x18000a0bf  jz      loc_18000A010
0x18000a0c5  mov     cs:?g_pfnWinHttpIsHostInProxyBypassList@@3P6AKPEBU_WINHTTP_PROXY_INFO@@PEBGHGPEAH@ZEA, rax; ulong (*g_pfnWinHttpIsHostInProxyBypassList)(_WINHTTP_PROXY_INFO const *,ushort const *,int,ushort,int *)
0x18000a0cc  lea     rax, [rbx+0C54h]
0x18000a0d3  mov     r8d, r14d
0x18000a0d6  mov     [rsp+100h+var_E0], rax
0x18000a0db  lea     r14, [rbx+78h]
0x18000a0df  mov     rdx, r14
0x18000a0e2  mov     rax, r10
0x18000a0e5  movzx   r9d, di
0x18000a0e9  mov     rcx, rsi
0x18000a0ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0f1  mov     edi, eax
0x18000a0f3  test    eax, eax
0x18000a0f5  jle     short loc_18000A102
0x18000a0f7  movzx   edi, di
0x18000a0fa  or      edi, 80070000h
0x18000a100  test    edi, edi
0x18000a102  js      loc_18000A206
0x18000a108  xor     eax, eax
0x18000a10a  cmp     [rbx+0C54h], eax
0x18000a110  setz    al
0x18000a113  cmp     qword ptr [rbx+12D0h], 0
0x18000a11b  mov     [rbx+0C58h], eax
0x18000a121  jz      loc_18000A206
0x18000a127  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000a12e  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000a135  mov     rax, [rax+18h]
0x18000a139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a13e  mov     r9, [rsi+10h]
0x18000a142  lea     rcx, [rbp+57h+arg_0]
0x18000a146  mov     r8, [rsi+8]
0x18000a14a  add     rax, 18h
0x18000a14e  cmp     dword ptr [rbx+0C54h], 0
0x18000a155  mov     [rbp+57h+arg_0], rax
0x18000a159  jz      short loc_18000A16E
0x18000a15b  lea     rdx, aUserSManualPro; "User's manual proxy string: '%s'; Bypas"...
0x18000a162  mov     [rsp+100h+var_E0], r14
0x18000a167  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000a16c  jmp     short loc_18000A17A
0x18000a16e  lea     rdx, aUserSManualPro_0; "User's manual proxy string: '%s';  Bypa"...
0x18000a175  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000a17a  mov     rcx, [rbx+12D0h]
0x18000a181  lea     r9, aWininethelperc; "WinInetHelperClass"
0x18000a188  mov     rbx, [rbp+57h+arg_0]
0x18000a18c  xor     r8d, r8d
0x18000a18f  mov     edx, r15d
0x18000a192  mov     [rsp+100h+var_E0], rbx
0x18000a197  mov     rax, [rcx]
0x18000a19a  mov     rax, [rax+18h]
0x18000a19e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1a3  lea     rdx, [rbx-18h]
0x18000a1a7  or      eax, 0FFFFFFFFh
0x18000a1aa  lock xadd [rdx+10h], eax
0x18000a1af  sub     eax, 1
0x18000a1b2  jg      short loc_18000A206
0x18000a1b4  mov     rcx, [rdx]
0x18000a1b7  mov     rax, [rcx]
0x18000a1ba  mov     rax, [rax+8]
0x18000a1be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1c3  jmp     short loc_18000A206
0x18000a1c5  mov     rcx, [rbx+12D0h]
0x18000a1cc  test    rcx, rcx
0x18000a1cf  jz      short loc_18000A1F8
0x18000a1d1  mov     rax, [rcx]
0x18000a1d4  lea     rdx, aTheUserHasNoMa; "The user has no manual proxy configured"...
0x18000a1db  mov     [rsp+100h+var_E0], rdx
0x18000a1e0  lea     r9, aWininethelperc; "WinInetHelperClass"
0x18000a1e7  xor     r8d, r8d
0x18000a1ea  mov     edx, r15d
0x18000a1ed  mov     rax, [rax+18h]
0x18000a1f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1f6  xor     edx, edx
0x18000a1f8  cmp     [rbx+0C64h], edx
0x18000a1fe  jnz     short loc_18000A206
0x18000a200  mov     [rbx+0C58h], edx
0x18000a206  mov     rbx, [rsp+100h+arg_8]
0x18000a20e  mov     eax, edi
0x18000a210  add     rsp, 0D0h
0x18000a217  pop     r15
0x18000a219  pop     r14
0x18000a21b  pop     r13
0x18000a21d  pop     r12
0x18000a21f  pop     rdi
0x18000a220  pop     rsi
0x18000a221  pop     rbp
0x18000a222  retn
```
