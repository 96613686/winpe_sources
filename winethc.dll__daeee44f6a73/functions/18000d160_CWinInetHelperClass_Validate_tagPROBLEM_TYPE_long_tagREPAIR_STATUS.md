# CWinInetHelperClass::Validate(tagPROBLEM_TYPE,long *,tagREPAIR_STATUS *)

- ea: `0x18000d160`
- end: `0x18000d63c`
- name: `?Validate@CWinInetHelperClass@@UEAAJW4tagPROBLEM_TYPE@@PEAJPEAW4tagREPAIR_STATUS@@@Z`
- size: `1244`
- prototype: `__int64 __fastcall(CWinInetHelperClass *__hidden this, enum tagPROBLEM_TYPE, int *, enum tagREPAIR_STATUS *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x1800012c0`
- `0x1800048cc`
- `0x18000d160`
- `0x18000dd54`
- `0x18000ddac`
- `0x18000dfe8`
- `0x18000e230`
- `0x18000f91c`
- `0x18000fce8`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000d59e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000d5c1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000d59e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000d5c1`
- `DNSAPI!DnsFreeProxyName` at `0x18000d1d6`
- `DNSAPI!DnsFreeProxyName` at `0x18000d1ef`
- `DNSAPI!DnsFreeProxyName` at `0x18000d1d6`
- `DNSAPI!DnsFreeProxyName` at `0x18000d1ef`

## string_xrefs

- `0x18000d351`: `The proxy auto-detection thread timed out. Will try direct connection.`
- `0x18000d384`: `The proxy auto-detection thread timed out.`
- `0x18000d3ec`: `DNS query during proxy auto-detection failed with error 0x%x.`

## pseudocode

```c
__int64 __fastcall CWinInetHelperClass::Validate(
        CWinInetHelperClass *this,
        enum tagPROBLEM_TYPE a2,
        int *a3,
        enum tagREPAIR_STATUS *a4)
{
  enum WHCConnectionErrors *v4; // r13
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *v5; // r12
  _QWORD *v8; // rbx
  WCHAR *v9; // rcx
  WCHAR *v10; // rcx
  int UserProxyConfig; // esi
  _QWORD *v12; // rax
  __int64 v13; // rcx
  int v14; // eax
  int v15; // ecx
  unsigned int v16; // ebx
  __int64 v17; // rcx
  const wchar_t *v18; // rdx
  struct _FILETIME v19; // rbx
  __int64 v20; // xmm1_8
  __int64 v21; // rax
  const wchar_t *v22; // r8
  bool v23; // zf
  struct _FILETIME v24; // rbx
  int *v25; // rax
  struct _WINHTTP_PROXY_INFO *v27; // [rsp+20h] [rbp-50h]
  int v28; // [rsp+40h] [rbp-30h] BYREF
  int v29; // [rsp+44h] [rbp-2Ch] BYREF
  unsigned int v30; // [rsp+48h] [rbp-28h] BYREF
  DWORD dwLowDateTime; // [rsp+4Ch] [rbp-24h]
  __int128 v32; // [rsp+50h] [rbp-20h] BYREF
  __int64 v33; // [rsp+60h] [rbp-10h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp+40h] BYREF
  int *v35; // [rsp+C0h] [rbp+50h]
  int v36; // [rsp+C8h] [rbp+58h] BYREF

  v35 = a3;
  *a4 = RS_UNREPAIRED;
  v4 = (CWinInetHelperClass *)((char *)this + 3016);
  v28 = 0;
  v5 = (WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *)((char *)this + 4856);
  v30 = 0;
  *((_DWORD *)this + 754) = 0;
  v29 = 0;
  SystemTimeAsFileTime.dwLowDateTime = 0;
  v33 = 0;
  v32 = 0;
  FreeUserProxyConfig((CWinInetHelperClass *)((char *)this + 4856));
  v8 = (_QWORD *)*((_QWORD *)this + 639);
  if ( v8 )
  {
    v9 = (WCHAR *)v8[1];
    if ( v9 )
    {
      DnsFreeProxyName(v9);
      v8[1] = 0;
    }
    v10 = (WCHAR *)v8[3];
    if ( v10 )
    {
      DnsFreeProxyName(v10);
      v8[3] = 0;
    }
    operator delete(v8);
    *((_QWORD *)this + 639) = 0;
  }
  UserProxyConfig = GetUserProxyConfig(v5);
  if ( UserProxyConfig >= 0 )
  {
    UserProxyConfig = GetDirectAccessInfo(
                        (PCWSTR)this + 60,
                        *((struct INDFEtw **)this + 602),
                        (struct DIRECT_ACCESS_QUERY **)this + 639,
                        (int *)&SystemTimeAsFileTime,
                        (struct _WINHTTP_PROXY_INFO *)&v32);
    dwLowDateTime = SystemTimeAsFileTime.dwLowDateTime;
    if ( UserProxyConfig >= 0 )
    {
      if ( SystemTimeAsFileTime.dwLowDateTime )
        goto LABEL_36;
      v12 = (_QWORD *)((char *)this + 4864);
      if ( !v5->fAutoDetect && !*v12 )
      {
        v13 = *((_QWORD *)this + 609);
        v33 = *((_QWORD *)this + 610);
        *((_QWORD *)&v32 + 1) = v13;
        LODWORD(v32) = v13 != 0 ? 3 : 1;
        goto LABEL_36;
      }
      if ( *v12 )
      {
        *((_QWORD *)this + 616) = *v12;
        v14 = 0;
        v15 = 2;
      }
      else
      {
        v14 = 3;
        v15 = 1;
      }
      *((_DWORD *)this + 1230) = v15;
      *((_DWORD *)this + 1231) = v14;
      *((_DWORD *)this + 1237) = 1;
      FreeProxyInfo((CWinInetHelperClass *)((char *)this + 4896));
      v36 = 0;
      SystemTimeAsFileTime.dwLowDateTime = 0;
      UserProxyConfig = CWinInetHelperClass::ExecuteProxyAutodetectionThread(
                          this,
                          0,
                          &v36,
                          &v29,
                          (enum ThreadExternalHostResolveResult *)&SystemTimeAsFileTime);
      if ( UserProxyConfig >= 0 )
      {
        v16 = v36;
        if ( v36 >= 0 )
        {
          v20 = *((_QWORD *)this + 614);
          v32 = *((_OWORD *)this + 306);
          v33 = v20;
          goto LABEL_36;
        }
        if ( v36 == -2147012716 )
        {
          v17 = *((_QWORD *)this + 602);
          if ( !v17 )
            goto LABEL_36;
          v18 = L"Got ERROR_WINHTTP_AUTODETECTION_FAILED while detecting proxy. Will try direct connection.";
          goto LABEL_25;
        }
        if ( v36 == -2147024638 )
        {
          v17 = *((_QWORD *)this + 602);
          if ( SystemTimeAsFileTime.dwLowDateTime == 2 )
          {
            if ( v17 )
              (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v17 + 24LL))(
                v17,
                2,
                0,
                L"WinInetHelperClass",
                L"The proxy auto-detection thread timed out.");
            *a4 = RS_UNREPAIRED;
            goto LABEL_44;
          }
          if ( !v17 )
            goto LABEL_36;
          v18 = L"The proxy auto-detection thread timed out. Will try direct connection.";
LABEL_25:
          (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v17 + 24LL))(
            v17,
            2,
            0,
            L"WinInetHelperClass",
            v18);
          goto LABEL_36;
        }
        if ( SystemTimeAsFileTime.dwLowDateTime == 3 )
        {
          *a4 = RS_UNREPAIRED;
          if ( *((_QWORD *)this + 602) )
          {
            SystemTimeAsFileTime = (struct _FILETIME)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr)
                                                    + 24);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
              &SystemTimeAsFileTime,
              L"DNS query during proxy auto-detection failed with error 0x%x.",
              v16);
            v19 = SystemTimeAsFileTime;
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const wchar_t *, struct _FILETIME))(**((_QWORD **)this + 602)
                                                                                               + 24LL))(
              *((_QWORD *)this + 602),
              2,
              0,
              L"WinInetHelperClass",
              SystemTimeAsFileTime);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v19 - 24LL + 16), 0xFFFFFFFF) <= 1 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)&v19 - 24LL) + 8LL))(*(_QWORD *)(*(_QWORD *)&v19 - 24LL));
          }
          goto LABEL_36;
        }
        UserProxyConfig = v36;
        if ( v36 >= 0 )
        {
LABEL_36:
          UserProxyConfig = CWinInetHelperClass::ExecuteConnectionThread(
                              this,
                              0,
                              v4,
                              &v28,
                              &v30,
                              (struct _WINHTTP_PROXY_INFO *const)&v32,
                              0);
          if ( UserProxyConfig >= 0 )
          {
            if ( *(_DWORD *)v4 )
            {
              if ( *((_QWORD *)this + 602) )
              {
                v21 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
                v22 = L"WinHTTP";
                v23 = *((_DWORD *)this + 1202) == 0;
                SystemTimeAsFileTime = (struct _FILETIME)(v21 + 24);
                if ( v23 )
                  v22 = L"WinInet";
                LODWORD(v27) = *(_DWORD *)v4;
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                  &SystemTimeAsFileTime,
                  L"%s validation failed with error hr=0x%x [WHCError #%i].",
                  v22,
                  (unsigned int)v28,
                  v27);
                v24 = SystemTimeAsFileTime;
                (*(void (__fastcall **)(_QWORD, __int64, _QWORD, const wchar_t *, struct _FILETIME))(**((_QWORD **)this + 602) + 24LL))(
                  *((_QWORD *)this + 602),
                  2,
                  0,
                  L"WinInetHelperClass",
                  SystemTimeAsFileTime);
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v24 - 24LL + 16), 0xFFFFFFFF) <= 1 )
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)&v24 - 24LL) + 8LL))(*(_QWORD *)(*(_QWORD *)&v24 - 24LL));
              }
            }
            else
            {
              *a4 = RS_REPAIRED;
            }
          }
        }
      }
    }
LABEL_44:
    if ( dwLowDateTime )
      FreeProxyInfo((struct _WINHTTP_PROXY_INFO *)&v32);
  }
  if ( *a4 == RS_UNREPAIRED )
  {
    if ( !*((_QWORD *)this + 640) )
    {
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      *((struct _FILETIME *)this + 640) = SystemTimeAsFileTime;
    }
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( (unsigned int)((*(_QWORD *)&SystemTimeAsFileTime
                       - ((unsigned int)*((_QWORD *)this + 640) | *((_QWORD *)this + 640) & 0xFFFFFFFF00000000uLL))
                      / 0x989680) < 0xA )
    {
      v25 = v35;
      *a4 = RS_DEFERRED;
      *v25 = 1;
    }
  }
  return (unsigned int)UserProxyConfig;
}

```

## disassembly

```asm
0x18000d160  mov     [rsp-38h+arg_8], rbx
0x18000d165  mov     [rsp-38h+arg_10], r8
0x18000d16a  push    rbp
0x18000d16b  push    rsi
0x18000d16c  push    rdi
0x18000d16d  push    r12
0x18000d16f  push    r13
0x18000d171  push    r14
0x18000d173  push    r15
0x18000d175  mov     rbp, rsp
0x18000d178  sub     rsp, 70h
0x18000d17c  xor     esi, esi
0x18000d17e  mov     dword ptr [r9], 2
0x18000d185  lea     r13, [rcx+0BC8h]
0x18000d18c  mov     [rbp+var_30], esi
0x18000d18f  lea     r12, [rcx+12F8h]
0x18000d196  mov     [rbp+var_28], esi
0x18000d199  mov     rdi, rcx
0x18000d19c  mov     [r13+0], esi
0x18000d1a0  xorps   xmm0, xmm0
0x18000d1a3  mov     [rbp+var_2C], esi
0x18000d1a6  xor     eax, eax
0x18000d1a8  mov     [rbp+SystemTimeAsFileTime.dwLowDateTime], esi
0x18000d1ab  mov     rcx, r12; struct _WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *
0x18000d1ae  mov     [rbp+var_10], rax
0x18000d1b2  mov     r14, r9
0x18000d1b5  movups  [rbp+var_20], xmm0
0x18000d1b9  call    ?FreeUserProxyConfig@@YAXPEAU_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG@@@Z; FreeUserProxyConfig(_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *)
0x18000d1be  lea     r15, [rdi+13F8h]
0x18000d1c5  mov     rbx, [r15]
0x18000d1c8  test    rbx, rbx
0x18000d1cb  jz      short loc_18000D20A
0x18000d1cd  mov     rcx, [rbx+8]; proxyName
0x18000d1d1  test    rcx, rcx
0x18000d1d4  jz      short loc_18000D1E6
0x18000d1d6  call    cs:__imp_DnsFreeProxyName
0x18000d1dd  nop     dword ptr [rax+rax+00h]
0x18000d1e2  mov     [rbx+8], rsi
0x18000d1e6  mov     rcx, [rbx+18h]; proxyName
0x18000d1ea  test    rcx, rcx
0x18000d1ed  jz      short loc_18000D1FF
0x18000d1ef  call    cs:__imp_DnsFreeProxyName
0x18000d1f6  nop     dword ptr [rax+rax+00h]
0x18000d1fb  mov     [rbx+18h], rsi
0x18000d1ff  mov     rcx, rbx; Block
0x18000d202  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d207  mov     [r15], rsi
0x18000d20a  mov     rcx, r12; struct _WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *
0x18000d20d  call    ?GetUserProxyConfig@@YAJPEAU_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG@@@Z; GetUserProxyConfig(_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *)
0x18000d212  mov     esi, eax
0x18000d214  test    eax, eax
0x18000d216  js      loc_18000D577
0x18000d21c  mov     rdx, [rdi+12D0h]; struct INDFEtw *
0x18000d223  lea     rax, [rbp+var_20]
0x18000d227  lea     rcx, [rdi+78h]; hostName
0x18000d22b  mov     [rsp+70h+var_50], rax; struct _WINHTTP_PROXY_INFO *
0x18000d230  lea     r9, [rbp+SystemTimeAsFileTime]; int *
0x18000d234  mov     r8, r15; struct DIRECT_ACCESS_QUERY **
0x18000d237  call    ?GetDirectAccessInfo@@YAJPEBGPEAUINDFEtw@@PEAPEAVDIRECT_ACCESS_QUERY@@PEAHPEAU_WINHTTP_PROXY_INFO@@@Z; GetDirectAccessInfo(ushort const *,INDFEtw *,DIRECT_ACCESS_QUERY * *,int *,_WINHTTP_PROXY_INFO *)
0x18000d23c  mov     ebx, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000d23f  mov     esi, eax
0x18000d241  mov     [rbp+var_24], ebx
0x18000d244  test    eax, eax
0x18000d246  js      loc_18000D565
0x18000d24c  test    ebx, ebx
0x18000d24e  jnz     loc_18000D470
0x18000d254  lea     rax, [rdi+1300h]
0x18000d25b  cmp     [r12], ebx
0x18000d25f  jnz     short loc_18000D291
0x18000d261  xor     r12d, r12d
0x18000d264  cmp     [rax], r12
0x18000d267  jnz     short loc_18000D294
0x18000d269  mov     rcx, [rdi+1308h]
0x18000d270  mov     rax, [rdi+1310h]
0x18000d277  mov     [rbp+var_10], rax
0x18000d27b  mov     qword ptr [rbp+var_20+8], rcx
0x18000d27f  neg     rcx
0x18000d282  sbb     eax, eax
0x18000d284  and     eax, 2
0x18000d287  inc     eax
0x18000d289  mov     dword ptr [rbp+var_20], eax
0x18000d28c  jmp     loc_18000D473
0x18000d291  xor     r12d, r12d
0x18000d294  mov     rcx, [rax]
0x18000d297  test    rcx, rcx
0x18000d29a  jz      short loc_18000D2AD
0x18000d29c  mov     [rdi+1340h], rcx
0x18000d2a3  mov     eax, r12d
0x18000d2a6  mov     ecx, 2
0x18000d2ab  jmp     short loc_18000D2B5
0x18000d2ad  mov     eax, 3
0x18000d2b2  lea     ecx, [rax-2]
0x18000d2b5  mov     [rdi+1338h], ecx
0x18000d2bb  lea     r15, [rdi+1320h]
0x18000d2c2  mov     [rdi+133Ch], eax
0x18000d2c8  mov     rcx, r15; struct _WINHTTP_PROXY_INFO *
0x18000d2cb  mov     dword ptr [rdi+1354h], 1
0x18000d2d5  call    ?FreeProxyInfo@@YAXPEAU_WINHTTP_PROXY_INFO@@@Z; FreeProxyInfo(_WINHTTP_PROXY_INFO *)
0x18000d2da  lea     rax, [rbp+SystemTimeAsFileTime]
0x18000d2de  mov     [rbp+arg_18], r12d
0x18000d2e2  lea     r9, [rbp+var_2C]; int *
0x18000d2e6  mov     [rsp+70h+var_50], rax; enum ThreadExternalHostResolveResult *
0x18000d2eb  lea     r8, [rbp+arg_18]; int *
0x18000d2ef  mov     [rbp+SystemTimeAsFileTime.dwLowDateTime], r12d
0x18000d2f3  xor     edx, edx; int
0x18000d2f5  mov     rcx, rdi; this
0x18000d2f8  call    ?ExecuteProxyAutodetectionThread@CWinInetHelperClass@@AEAAJHPEAJPEAHPEAW4ThreadExternalHostResolveResult@@@Z; CWinInetHelperClass::ExecuteProxyAutodetectionThread(int,long *,int *,ThreadExternalHostResolveResult *)
0x18000d2fd  mov     esi, eax
0x18000d2ff  test    eax, eax
0x18000d301  js      loc_18000D568
0x18000d307  mov     ebx, [rbp+arg_18]
0x18000d30a  test    ebx, ebx
0x18000d30c  jns     loc_18000D45B
0x18000d312  cmp     ebx, 80072F94h
0x18000d318  jnz     short loc_18000D333
0x18000d31a  mov     rcx, [rdi+12D0h]
0x18000d321  test    rcx, rcx
0x18000d324  jz      loc_18000D473
0x18000d32a  lea     rdx, aGotErrorWinhtt_0; "Got ERROR_WINHTTP_AUTODETECTION_FAILED "...
0x18000d331  jmp     short loc_18000D358
0x18000d333  cmp     ebx, 80070102h
0x18000d339  jnz     short loc_18000D3B3
0x18000d33b  cmp     [rbp+SystemTimeAsFileTime.dwLowDateTime], 2
0x18000d33f  mov     rcx, [rdi+12D0h]
0x18000d346  jz      short loc_18000D37C
0x18000d348  test    rcx, rcx
0x18000d34b  jz      loc_18000D473
0x18000d351  lea     rdx, aTheProxyAutoDe; "The proxy auto-detection thread timed o"...
0x18000d358  mov     rax, [rcx]
0x18000d35b  lea     r9, aWininethelperc; "WinInetHelperClass"
0x18000d362  xor     r8d, r8d
0x18000d365  mov     [rsp+70h+var_50], rdx
0x18000d36a  mov     rax, [rax+18h]
0x18000d36e  lea     edx, [r8+2]
0x18000d372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d377  jmp     loc_18000D473
0x18000d37c  test    rcx, rcx
0x18000d37f  jz      short loc_18000D3A7
0x18000d381  mov     rax, [rcx]
0x18000d384  lea     rdx, aTheProxyAutoDe_0; "The proxy auto-detection thread timed o"...
0x18000d38b  xor     r8d, r8d
0x18000d38e  mov     [rsp+70h+var_50], rdx
0x18000d393  lea     r9, aWininethelperc; "WinInetHelperClass"
0x18000d39a  mov     rax, [rax+18h]
0x18000d39e  lea     edx, [r8+2]
0x18000d3a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3a7  mov     dword ptr [r14], 2
0x18000d3ae  jmp     loc_18000D568
0x18000d3b3  cmp     [rbp+SystemTimeAsFileTime.dwLowDateTime], 3
0x18000d3b7  jnz     loc_18000D44F
0x18000d3bd  mov     dword ptr [r14], 2
0x18000d3c4  cmp     [rdi+12D0h], r12
0x18000d3cb  jz      loc_18000D473
0x18000d3d1  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000d3d8  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000d3df  mov     rax, [rax+18h]
0x18000d3e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3e8  add     rax, 18h
0x18000d3ec  lea     rdx, aDnsQueryDuring; "DNS query during proxy auto-detection f"...
0x18000d3f3  mov     r8d, ebx
0x18000d3f6  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000d3fa  lea     rcx, [rbp+SystemTimeAsFileTime]
0x18000d3fe  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000d403  mov     rcx, [rdi+12D0h]
0x18000d40a  lea     r9, aWininethelperc; "WinInetHelperClass"
0x18000d411  mov     rbx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000d415  xor     r8d, r8d
0x18000d418  mov     [rsp+70h+var_50], rbx
0x18000d41d  mov     rax, [rcx]
0x18000d420  lea     edx, [r8+2]
0x18000d424  mov     rax, [rax+18h]
0x18000d428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d42d  lea     rdx, [rbx-18h]
0x18000d431  or      eax, 0FFFFFFFFh
0x18000d434  lock xadd [rdx+10h], eax
0x18000d439  sub     eax, 1
0x18000d43c  jg      short loc_18000D473
0x18000d43e  mov     rcx, [rdx]
0x18000d441  mov     rax, [rcx]
0x18000d444  mov     rax, [rax+8]
0x18000d448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d44d  jmp     short loc_18000D473
0x18000d44f  mov     esi, ebx
0x18000d451  test    ebx, ebx
0x18000d453  js      loc_18000D568
0x18000d459  jmp     short loc_18000D473
0x18000d45b  movups  xmm0, xmmword ptr [r15]
0x18000d45f  movsd   xmm1, qword ptr [r15+10h]
0x18000d465  movups  [rbp+var_20], xmm0
0x18000d469  movsd   [rbp+var_10], xmm1
0x18000d46e  jmp     short loc_18000D473
0x18000d470  xor     r12d, r12d
0x18000d473  lea     rax, [rbp+var_20]
0x18000d477  mov     [rsp+70h+var_40], r12; struct sockaddr_storage *
0x18000d47c  mov     [rsp+70h+var_48], rax; struct _WINHTTP_PROXY_INFO *
0x18000d481  lea     r9, [rbp+var_30]; int *
0x18000d485  lea     rax, [rbp+var_28]
0x18000d489  mov     r8, r13; enum WHCConnectionErrors *
0x18000d48c  xor     edx, edx; int
0x18000d48e  mov     [rsp+70h+var_50], rax; unsigned int *
0x18000d493  mov     rcx, rdi; this
0x18000d496  call    ?ExecuteConnectionThread@CWinInetHelperClass@@AEAAJHPEAW4WHCConnectionErrors@@PEAJPEAKQEAU_WINHTTP_PROXY_INFO@@PEAUsockaddr_storage@@@Z; CWinInetHelperClass::ExecuteConnectionThread(int,WHCConnectionErrors *,long *,ulong *,_WINHTTP_PROXY_INFO * const,sockaddr_storage *)
0x18000d49b  mov     esi, eax
0x18000d49d  test    eax, eax
0x18000d49f  js      loc_18000D568
0x18000d4a5  cmp     [r13+0], r12d
0x18000d4a9  jz      loc_18000D55C
0x18000d4af  cmp     [rdi+12D0h], r12
0x18000d4b6  jz      loc_18000D568
0x18000d4bc  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000d4c3  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000d4ca  mov     rax, [rax+18h]
0x18000d4ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4d3  mov     r9d, [rbp+var_30]
0x18000d4d7  lea     r8, aWinhttp; "WinHTTP"
0x18000d4de  add     rax, 18h
0x18000d4e2  lea     rdx, aSValidationFai; "%s validation failed with error hr=0x%x"...
0x18000d4e9  cmp     [rdi+12C8h], r12d
0x18000d4f0  lea     rcx, [rbp+SystemTimeAsFileTime]
0x18000d4f4  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000d4f8  lea     rax, aWininet; "WinInet"
0x18000d4ff  cmovz   r8, rax
0x18000d503  mov     eax, [r13+0]
0x18000d507  mov     dword ptr [rsp+70h+var_50], eax
0x18000d50b  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000d510  mov     rcx, [rdi+12D0h]
0x18000d517  lea     r9, aWininethelperc; "WinInetHelperClass"
0x18000d51e  mov     rbx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000d522  xor     r8d, r8d
0x18000d525  mov     [rsp+70h+var_50], rbx
0x18000d52a  mov     rax, [rcx]
0x18000d52d  lea     edx, [r8+2]
0x18000d531  mov     rax, [rax+18h]
0x18000d535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d53a  lea     rdx, [rbx-18h]
0x18000d53e  or      eax, 0FFFFFFFFh
0x18000d541  lock xadd [rdx+10h], eax
0x18000d546  sub     eax, 1
0x18000d549  jg      short loc_18000D568
0x18000d54b  mov     rcx, [rdx]
0x18000d54e  mov     rax, [rcx]
0x18000d551  mov     rax, [rax+8]
0x18000d555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d55a  jmp     short loc_18000D568
0x18000d55c  mov     dword ptr [r14], 1
0x18000d563  jmp     short loc_18000D568
0x18000d565  xor     r12d, r12d
0x18000d568  cmp     [rbp+var_24], r12d
0x18000d56c  jz      short loc_18000D577
0x18000d56e  lea     rcx, [rbp+var_20]; struct _WINHTTP_PROXY_INFO *
0x18000d572  call    ?FreeProxyInfo@@YAXPEAU_WINHTTP_PROXY_INFO@@@Z; FreeProxyInfo(_WINHTTP_PROXY_INFO *)
0x18000d577  cmp     dword ptr [r14], 2
0x18000d57b  jnz     loc_18000D621
0x18000d581  mov     ecx, [rdi+1404h]
0x18000d587  mov     eax, [rdi+1400h]
0x18000d58d  shl     rcx, 20h
0x18000d591  or      rcx, rax
0x18000d594  jnz     short loc_18000D5B5
0x18000d596  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rcx
0x18000d59a  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000d59e  call    cs:__imp_GetSystemTimeAsFileTime
0x18000d5a5  nop     dword ptr [rax+rax+00h]
0x18000d5aa  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000d5ae  mov     [rdi+1400h], rax
0x18000d5b5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000d5b9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000d5c1  call    cs:__imp_GetSystemTimeAsFileTime
0x18000d5c8  nop     dword ptr [rax+rax+00h]
0x18000d5cd  mov     rax, [rdi+1400h]
0x18000d5d4  mov     ecx, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000d5d7  mov     rdx, rax
0x18000d5da  mov     r8d, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x18000d5de  shl     r8, 20h
0x18000d5e2  or      r8, rcx
0x18000d5e5  mov     rcx, 0FFFFFFFF00000000h
0x18000d5ef  and     rdx, rcx
0x18000d5f2  mov     ecx, eax
0x18000d5f4  or      rdx, rcx
0x18000d5f7  mov     rax, 0D6BF94D5E57A42BDh
0x18000d601  sub     r8, rdx
0x18000d604  mul     r8
0x18000d607  shr     rdx, 17h
0x18000d60b  cmp     edx, 0Ah
0x18000d60e  jnb     short loc_18000D621
0x18000d610  mov     rax, [rbp+arg_10]
0x18000d614  mov     dword ptr [r14], 3
0x18000d61b  mov     dword ptr [rax], 1
0x18000d621  mov     rbx, [rsp+70h+arg_8]
0x18000d629  mov     eax, esi
0x18000d62b  add     rsp, 70h
0x18000d62f  pop     r15
0x18000d631  pop     r14
0x18000d633  pop     r13
0x18000d635  pop     r12
0x18000d637  pop     rdi
0x18000d638  pop     rsi
0x18000d639  pop     rbp
0x18000d63a  retn
```
