# CAutoImpersonateClient::GetTokenUser(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18001dfec`
- end: `0x18001e5ca`
- name: `?GetTokenUser@CAutoImpersonateClient@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1502`
- prototype: `__int64 __fastcall(CAutoImpersonateClient *this, _QWORD *)`
- caller_count: `27`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010290`
- `0x1800216f8`
- `0x180029088`
- `0x18003b550`
- `0x18003e73c`
- `0x180044a10`
- `0x18004d77c`
- `0x1800522d0`
- `0x1800563d0`
- `0x18007b260`
- `0x180081648`
- `0x1800834d8`
- `0x18009362c`
- `0x18009ef98`
- `0x1800b0bf4`
- `0x1800b1afc`
- `0x1800b4804`
- `0x1800b51f4`
- `0x1800b57d4`
- `0x1800b6310`
- `0x1800b67b0`
- `0x1800b7038`
- `0x1800b8b80`
- `0x1800b8ef4`
- `0x1800bc9a0`
- `0x1800d83f0`
- `0x1800f0c54`

## callees

- `0x18000c050`
- `0x180014680`
- `0x180019690`
- `0x18001a9c0`
- `0x18001b760`
- `0x18001d050`
- `0x18001dfec`
- `0x18001e5d0`
- `0x18001eae8`
- `0x18001ec18`
- `0x18007c408`
- `0x180089bc0`
- `0x1800a3b60`
- `0x1800a46be`
- `0x180116c40`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001e2bb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001e2bb`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e103`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e274`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e375`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e3c7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e419`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e46b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e4bd`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e103`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e274`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e375`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e3c7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e419`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e46b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e4bd`

## string_xrefs

- `0x18001e0ae`: `CAutoImpersonateClient::GetTokenUser`
- `0x18001e13f`: `CAutoImpersonateClient::GetTokenUser`
- `0x18001e5b5`: `CAutoImpersonateClient::GetTokenUser`
- `0x18001e0d4`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x18001e2e3`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x18001e2f2`: `sid='%s'`
- `0x18001e5a0`: `hr = GetTokenSid(sid)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAutoImpersonateClient::GetTokenUser(CAutoImpersonateClient *this, _QWORD *a2)
{
  __int64 v4; // rbx
  char *v5; // rax
  __int64 v6; // r8
  const char *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 *v10; // rdx
  int TokenSid; // eax
  const unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // r14
  unsigned __int64 v14; // r12
  unsigned __int64 v15; // rdi
  char *v16; // rcx
  __int64 v17; // rsi
  char *v18; // rax
  __int64 v19; // rcx
  unsigned int v20; // ebx
  char *v22; // rax
  __int64 v23; // rcx
  char *v24; // rax
  __int64 v25; // rcx
  char *v26; // rax
  __int64 v27; // rcx
  char *v28; // rax
  __int64 v29; // rcx
  char *v30; // rax
  __int64 v31; // rcx
  int v32; // [rsp+30h] [rbp-D0h] BYREF
  int v33; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v34[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v35[9]; // [rsp+60h] [rbp-A0h] BYREF
  char v36; // [rsp+ACh] [rbp-54h]
  int v37; // [rsp+B0h] [rbp-50h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  __int64 v39; // [rsp+C0h] [rbp-40h]
  __int64 v40; // [rsp+C8h] [rbp-38h]
  __int64 v41; // [rsp+D0h] [rbp-30h]
  char v42[16]; // [rsp+E0h] [rbp-20h] BYREF
  const char *v43; // [rsp+F0h] [rbp-10h]
  int v44; // [rsp+F8h] [rbp-8h]
  int v45; // [rsp+FCh] [rbp-4h]
  const char *v46; // [rsp+100h] [rbp+0h]
  __int64 v47; // [rsp+108h] [rbp+8h]
  int *v48; // [rsp+110h] [rbp+10h]
  __int64 v49; // [rsp+118h] [rbp+18h]
  const wchar_t *v50; // [rsp+120h] [rbp+20h]
  __int64 v51; // [rsp+128h] [rbp+28h]

  v35[0] = &ATL::CSid::`vftable';
  v36 = 0;
  v37 = 7;
  v38 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v39 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v40 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v41 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v33 = 0;
  v34[0] = "CAutoImpersonateClient::GetTokenUser";
  v34[1] = &v33;
  v34[2] = 0;
  v34[3] = 0;
  v4 = -1;
  switch ( dword_1801C3ABC )
  {
    case 4:
      if ( (byte_1801C36C4 & 4) == 0 )
        break;
      v5 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
      if ( v5 )
        v7 = v5 + 1;
      else
        v7 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
      v32 = 426;
      if ( v7 )
      {
        v8 = -1;
        do
          ++v8;
        while ( v7[v8] );
        v9 = (unsigned int)(v8 + 1);
      }
      else
      {
        v7 = "NULL";
        v9 = 5;
      }
      v10 = WlidSvc_TraceFunction_Enter;
      goto LABEL_10;
    case 5:
      if ( byte_1801C36C5 < 0 )
      {
        v30 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
        if ( v30 )
          v7 = v30 + 1;
        else
          v7 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
        v32 = 426;
        if ( v7 )
        {
          v31 = -1;
          do
            ++v31;
          while ( v7[v31] );
          v9 = (unsigned int)(v31 + 1);
        }
        else
        {
          v7 = "NULL";
          v9 = 5;
        }
        v10 = WlidModern_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 6:
      if ( (byte_1801C36C7 & 8) != 0 )
      {
        v28 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
        if ( v28 )
          v7 = v28 + 1;
        else
          v7 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
        v32 = 426;
        if ( v7 )
        {
          v29 = -1;
          do
            ++v29;
          while ( v7[v29] );
          v9 = (unsigned int)(v29 + 1);
        }
        else
        {
          v7 = "NULL";
          v9 = 5;
        }
        v10 = WlidCli_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 7:
      if ( (byte_1801C36C8 & 8) != 0 )
      {
        v26 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
        if ( v26 )
          v7 = v26 + 1;
        else
          v7 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
        v32 = 426;
        if ( v7 )
        {
          v27 = -1;
          do
            ++v27;
          while ( v7[v27] );
          v9 = (unsigned int)(v27 + 1);
        }
        else
        {
          v7 = "NULL";
          v9 = 5;
        }
        v10 = WlidProv_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 8:
      if ( (byte_1801C36C9 & 0x10) != 0 )
      {
        v24 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
        if ( v24 )
          v7 = v24 + 1;
        else
          v7 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
        v32 = 426;
        if ( v7 )
        {
          v25 = -1;
          do
            ++v25;
          while ( v7[v25] );
          v9 = (unsigned int)(v25 + 1);
        }
        else
        {
          v7 = "NULL";
          v9 = 5;
        }
        v10 = WlidBho_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 9:
      if ( (byte_1801C36CA & 0x10) != 0 )
      {
        v18 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
        if ( v18 )
          v7 = v18 + 1;
        else
          v7 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
        v32 = 426;
        if ( v7 )
        {
          v19 = -1;
          do
            ++v19;
          while ( v7[v19] );
          v9 = (unsigned int)(v19 + 1);
        }
        else
        {
          v7 = "NULL";
          v9 = 5;
        }
        v10 = TokenProvider_TraceFunction_Enter;
LABEL_10:
        v43 = v7;
        v46 = "CAutoImpersonateClient::GetTokenUser";
        v48 = &v32;
        v50 = L"NULL";
        v44 = v9;
        v45 = 0;
        v47 = 37;
        v49 = 4;
        v51 = 10;
        McGenEventWrite_EventWriteTransfer(v9, v10, v6, 5, v42);
      }
      break;
    default:
      if ( dword_1801C3ABC == 10 && (byte_1801C36CB & 0x10) != 0 )
      {
        v22 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
        if ( v22 )
          v7 = v22 + 1;
        else
          v7 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
        v32 = 426;
        if ( v7 )
        {
          v23 = -1;
          do
            ++v23;
          while ( v7[v23] );
          v9 = (unsigned int)(v23 + 1);
        }
        else
        {
          v7 = "NULL";
          v9 = 5;
        }
        v10 = Extension_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
  }
  TokenSid = CAutoImpersonateClient::GetTokenSid(this, (struct ATL::CSid *)v35);
  v33 = TokenSid;
  if ( TokenSid < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h",
      "CAutoImpersonateClient::GetTokenUser",
      0x1ACu,
      TokenSid,
      "hr = GetTokenSid(sid)");
  }
  else
  {
    v12 = ATL::CSid::Sid((ATL::CSid *)v35);
    v13 = v12;
    if ( !v12 )
      goto LABEL_35;
    do
      ++v4;
    while ( v12[v4] );
    if ( (_DWORD)v4 )
    {
      v14 = *(unsigned int *)(*a2 - 16LL);
      v15 = ((__int64)v12 - *a2) >> 1;
      if ( (int)((*(_DWORD *)(*a2 - 12LL) - v4) | (1 - *(_DWORD *)(*a2 - 8LL))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, (unsigned int)v4);
      v16 = (char *)*a2;
      v17 = 2LL * (int)v4;
      if ( v15 <= v14 )
      {
        memmove_s_0(v16, 2LL * (int)v4, &v16[2 * v15], 2LL * (int)v4);
      }
      else if ( v17 )
      {
        if ( v16 )
        {
          memcpy_0(v16, v13, 2LL * (int)v4);
        }
        else
        {
          *(_DWORD *)_o__errno() = 22;
          invalid_parameter_noinfo();
        }
      }
      if ( (int)v4 < 0 || (int)v4 > *(_DWORD *)(*a2 - 12LL) )
        ATL::AtlThrowImpl(-2147024809);
      *(_DWORD *)(*a2 - 16LL) = v4;
      *(_WORD *)(v17 + *a2) = 0;
    }
    else
    {
LABEL_35:
      ATL::CSimpleStringT<unsigned short,0>::Empty(a2);
    }
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h",
      0x1B0u,
      L"sid='%s'",
      *a2);
  }
  v20 = v33;
  CTraceFuncW<long>::~CTraceFuncW<long>(v34);
  ATL::CSid::~CSid((ATL::CSid *)v35);
  return v20;
}

```

## disassembly

```asm
0x18001dfec  mov     [rsp-8+arg_10], rbx
0x18001dff1  push    rbp
0x18001dff2  push    rsi
0x18001dff3  push    rdi
0x18001dff4  push    r12
0x18001dff6  push    r13
0x18001dff8  push    r14
0x18001dffa  push    r15
0x18001dffc  lea     rbp, [rsp-40h]
0x18001e001  sub     rsp, 140h
0x18001e008  mov     rax, cs:__security_cookie
0x18001e00f  xor     rax, rsp
0x18001e012  mov     [rbp+70h+var_40], rax
0x18001e016  mov     r15, rdx
0x18001e019  mov     rdi, rcx
0x18001e01c  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x18001e023  mov     [rsp+170h+var_110], rax
0x18001e028  xor     r13d, r13d
0x18001e02b  mov     [rbp+70h+var_C4], r13b
0x18001e02f  mov     [rbp+70h+var_C0], 7
0x18001e036  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001e03d  lea     rbx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001e044  mov     rcx, rbx
0x18001e047  mov     rax, [rax+18h]
0x18001e04b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e050  add     rax, 18h
0x18001e054  mov     [rbp+70h+var_B8], rax
0x18001e058  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001e05f  mov     rcx, rbx
0x18001e062  mov     rax, [rax+18h]
0x18001e066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e06b  add     rax, 18h
0x18001e06f  mov     [rbp+70h+var_B0], rax
0x18001e073  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001e07a  mov     rcx, rbx
0x18001e07d  mov     rax, [rax+18h]
0x18001e081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e086  add     rax, 18h
0x18001e08a  mov     [rbp+70h+var_A8], rax
0x18001e08e  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001e095  mov     rcx, rbx
0x18001e098  mov     rax, [rax+18h]
0x18001e09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0a1  add     rax, 18h
0x18001e0a5  mov     [rbp+70h+var_A0], rax
0x18001e0a9  mov     [rsp+170h+var_138], r13d
0x18001e0ae  lea     rax, aCautoimpersona_4; "CAutoImpersonateClient::GetTokenUser"
0x18001e0b5  mov     [rsp+170h+var_130], rax
0x18001e0ba  lea     rax, [rsp+170h+var_138]
0x18001e0bf  mov     [rsp+170h+var_128], rax
0x18001e0c4  mov     [rsp+170h+var_120], r13
0x18001e0c9  mov     [rsp+170h+var_118], r13
0x18001e0ce  mov     ecx, cs:dword_1801C3ABC
0x18001e0d4  lea     rsi, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001e0db  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001e0df  lea     r14d, [r13+5]
0x18001e0e3  lea     r12d, [r13+4]
0x18001e0e7  sub     ecx, r12d
0x18001e0ea  jnz     loc_18001E234
0x18001e0f0  test    cs:byte_1801C36C4, r12b
0x18001e0f7  jz      loc_18001E18B
0x18001e0fd  lea     edx, [rbx+5Dh]; Ch
0x18001e100  mov     rcx, rsi; Str
0x18001e103  call    cs:__imp_strrchr
0x18001e109  test    rax, rax
0x18001e10c  jz      loc_18001E22C
0x18001e112  inc     rax
0x18001e115  mov     [rsp+170h+var_140], 1AAh
0x18001e11d  test    rax, rax
0x18001e120  jz      loc_18001E591
0x18001e126  mov     rcx, rbx
0x18001e129  inc     rcx
0x18001e12c  cmp     [rax+rcx], r13b
0x18001e130  jnz     short loc_18001E129
0x18001e132  inc     ecx
0x18001e134  lea     rdx, WlidSvc_TraceFunction_Enter
0x18001e13b  mov     [rbp+70h+var_80], rax
0x18001e13f  lea     rax, aCautoimpersona_4; "CAutoImpersonateClient::GetTokenUser"
0x18001e146  mov     [rbp+70h+var_70], rax
0x18001e14a  lea     rax, [rsp+170h+var_140]
0x18001e14f  mov     [rbp+70h+var_60], rax
0x18001e153  lea     rax, aNull_2; "NULL"
0x18001e15a  mov     [rbp+70h+var_50], rax
0x18001e15e  lea     rax, [rbp+70h+var_90]
0x18001e162  mov     [rsp+170h+var_150], rax
0x18001e167  mov     [rbp+70h+var_78], ecx
0x18001e16a  mov     [rbp+70h+var_74], r13d
0x18001e16e  mov     [rbp+70h+var_68], 25h ; '%'
0x18001e176  mov     [rbp+70h+var_58], r12
0x18001e17a  mov     [rbp+70h+var_48], 0Ah
0x18001e182  mov     r9d, r14d
0x18001e185  call    McGenEventWrite_EventWriteTransfer
0x18001e18a  nop
0x18001e18b  lea     rdx, [rsp+170h+var_110]; struct ATL::CSid *
0x18001e190  mov     rcx, rdi; this
0x18001e193  call    ?GetTokenSid@CAutoImpersonateClient@@QEAAJAEAVCSid@ATL@@@Z; CAutoImpersonateClient::GetTokenSid(ATL::CSid &)
0x18001e198  mov     [rsp+170h+var_138], eax
0x18001e19c  test    eax, eax
0x18001e19e  js      loc_18001E5A0
0x18001e1a4  lea     rcx, [rsp+170h+var_110]; this
0x18001e1a9  call    ?Sid@CSid@ATL@@QEBAPEBGXZ; ATL::CSid::Sid(void)
0x18001e1ae  mov     r14, rax
0x18001e1b1  test    rax, rax
0x18001e1b4  jz      loc_18001E2B1
0x18001e1ba  inc     rbx
0x18001e1bd  cmp     [rax+rbx*2], r13w
0x18001e1c2  jnz     short loc_18001E1BA
0x18001e1c4  test    ebx, ebx
0x18001e1c6  jz      loc_18001E2B1
0x18001e1cc  mov     rax, [r15]
0x18001e1cf  mov     r12d, [rax-10h]
0x18001e1d3  mov     rdi, r14
0x18001e1d6  sub     rdi, rax
0x18001e1d9  sar     rdi, 1
0x18001e1dc  mov     ecx, 1
0x18001e1e1  sub     ecx, [rax-8]
0x18001e1e4  mov     eax, [rax-0Ch]
0x18001e1e7  sub     eax, ebx
0x18001e1e9  or      ecx, eax
0x18001e1eb  jge     short loc_18001E1F7
0x18001e1ed  mov     edx, ebx
0x18001e1ef  mov     rcx, r15
0x18001e1f2  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18001e1f7  mov     rcx, [r15]; void *
0x18001e1fa  movsxd  rax, ebx
0x18001e1fd  lea     rsi, [rax+rax]
0x18001e201  cmp     rdi, r12
0x18001e204  jbe     loc_18001E523
0x18001e20a  test    rsi, rsi
0x18001e20d  jz      loc_18001E2CC
0x18001e213  test    rcx, rcx
0x18001e216  jz      loc_18001E2BB
0x18001e21c  mov     r8, rsi; Size
0x18001e21f  mov     rdx, r14; Src
0x18001e222  call    memcpy_0
0x18001e227  jmp     loc_18001E2CC
0x18001e22c  mov     rax, rsi
0x18001e22f  jmp     loc_18001E115
0x18001e234  sub     ecx, 1
0x18001e237  jz      loc_18001E4A8
0x18001e23d  sub     ecx, 1
0x18001e240  jz      loc_18001E456
0x18001e246  sub     ecx, 1
0x18001e249  jz      loc_18001E404
0x18001e24f  sub     ecx, 1
0x18001e252  jz      loc_18001E3B2
0x18001e258  sub     ecx, 1
0x18001e25b  jnz     loc_18001E359
0x18001e261  test    cs:byte_1801C36CA, 10h
0x18001e268  jz      loc_18001E18B
0x18001e26e  lea     edx, [rcx+5Ch]; Ch
0x18001e271  mov     rcx, rsi; Str
0x18001e274  call    cs:__imp_strrchr
0x18001e27a  test    rax, rax
0x18001e27d  jz      loc_18001E4FE
0x18001e283  inc     rax
0x18001e286  mov     [rsp+170h+var_140], 1AAh
0x18001e28e  test    rax, rax
0x18001e291  jz      loc_18001E546
0x18001e297  mov     rcx, rbx
0x18001e29a  inc     rcx
0x18001e29d  cmp     [rax+rcx], r13b
0x18001e2a1  jnz     short loc_18001E29A
0x18001e2a3  inc     ecx
0x18001e2a5  lea     rdx, TokenProvider_TraceFunction_Enter
0x18001e2ac  jmp     loc_18001E13B
0x18001e2b1  mov     rcx, r15
0x18001e2b4  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18001e2b9  jmp     short loc_18001E2EA
0x18001e2bb  call    cs:__imp__o__errno
0x18001e2c1  mov     dword ptr [rax], 16h
0x18001e2c7  call    _invalid_parameter_noinfo
0x18001e2cc  test    ebx, ebx
0x18001e2ce  js      short loc_18001E34E
0x18001e2d0  mov     rax, [r15]
0x18001e2d3  cmp     ebx, [rax-0Ch]
0x18001e2d6  jg      short loc_18001E34E
0x18001e2d8  mov     [rax-10h], ebx
0x18001e2db  mov     rcx, [r15]
0x18001e2de  mov     [rsi+rcx], r13w
0x18001e2e3  lea     rsi, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001e2ea  mov     rax, [r15]
0x18001e2ed  mov     [rsp+170h+var_150], rax
0x18001e2f2  lea     r9, aSidS_0; "sid='%s'"
0x18001e2f9  mov     r8d, 1B0h; unsigned int
0x18001e2ff  mov     rdx, rsi; char *
0x18001e302  mov     ecx, 5; unsigned __int8
0x18001e307  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001e30c  mov     ebx, [rsp+170h+var_138]
0x18001e310  lea     rcx, [rsp+170h+var_130]
0x18001e315  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18001e31a  nop
0x18001e31b  lea     rcx, [rsp+170h+var_110]; this
0x18001e320  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18001e325  mov     eax, ebx
0x18001e327  mov     rcx, [rbp+70h+var_40]
0x18001e32b  xor     rcx, rsp; StackCookie
0x18001e32e  call    __security_check_cookie
0x18001e333  mov     rbx, [rsp+170h+arg_10]
0x18001e33b  add     rsp, 140h
0x18001e342  pop     r15
0x18001e344  pop     r14
0x18001e346  pop     r13
0x18001e348  pop     r12
0x18001e34a  pop     rdi
0x18001e34b  pop     rsi
0x18001e34c  pop     rbp
0x18001e34d  retn
0x18001e34e  mov     ecx, 80070057h; int
0x18001e353  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e359  cmp     ecx, 1
0x18001e35c  jnz     loc_18001E18B
0x18001e362  test    cs:byte_1801C36CB, 10h
0x18001e369  jz      loc_18001E18B
0x18001e36f  lea     edx, [rcx+5Bh]; Ch
0x18001e372  mov     rcx, rsi; Str
0x18001e375  call    cs:__imp_strrchr
0x18001e37b  test    rax, rax
0x18001e37e  jz      loc_18001E4F6
0x18001e384  inc     rax
0x18001e387  mov     [rsp+170h+var_140], 1AAh
0x18001e38f  test    rax, rax
0x18001e392  jz      loc_18001E537
0x18001e398  mov     rcx, rbx
0x18001e39b  inc     rcx
0x18001e39e  cmp     [rax+rcx], r13b
0x18001e3a2  jnz     short loc_18001E39B
0x18001e3a4  inc     ecx
0x18001e3a6  lea     rdx, Extension_TraceFunction_Enter
0x18001e3ad  jmp     loc_18001E13B
0x18001e3b2  test    cs:byte_1801C36C9, 10h
0x18001e3b9  jz      loc_18001E18B
0x18001e3bf  mov     edx, 5Ch ; '\'; Ch
0x18001e3c4  mov     rcx, rsi; Str
0x18001e3c7  call    cs:__imp_strrchr
0x18001e3cd  test    rax, rax
0x18001e3d0  jz      loc_18001E506
0x18001e3d6  inc     rax
0x18001e3d9  mov     [rsp+170h+var_140], 1AAh
0x18001e3e1  test    rax, rax
0x18001e3e4  jz      loc_18001E555
0x18001e3ea  mov     rcx, rbx
0x18001e3ed  inc     rcx
0x18001e3f0  cmp     [rax+rcx], r13b
0x18001e3f4  jnz     short loc_18001E3ED
0x18001e3f6  inc     ecx
0x18001e3f8  lea     rdx, WlidBho_TraceFunction_Enter
0x18001e3ff  jmp     loc_18001E13B
0x18001e404  test    cs:byte_1801C36C8, 8
0x18001e40b  jz      loc_18001E18B
0x18001e411  mov     edx, 5Ch ; '\'; Ch
0x18001e416  mov     rcx, rsi; Str
0x18001e419  call    cs:__imp_strrchr
0x18001e41f  test    rax, rax
0x18001e422  jz      loc_18001E50E
0x18001e428  inc     rax
0x18001e42b  mov     [rsp+170h+var_140], 1AAh
0x18001e433  test    rax, rax
0x18001e436  jz      loc_18001E564
0x18001e43c  mov     rcx, rbx
0x18001e43f  inc     rcx
0x18001e442  cmp     [rax+rcx], r13b
0x18001e446  jnz     short loc_18001E43F
0x18001e448  inc     ecx
0x18001e44a  lea     rdx, WlidProv_TraceFunction_Enter
0x18001e451  jmp     loc_18001E13B
0x18001e456  test    cs:byte_1801C36C7, 8
0x18001e45d  jz      loc_18001E18B
0x18001e463  mov     edx, 5Ch ; '\'; Ch
0x18001e468  mov     rcx, rsi; Str
0x18001e46b  call    cs:__imp_strrchr
0x18001e471  test    rax, rax
0x18001e474  jz      loc_18001E516
0x18001e47a  inc     rax
0x18001e47d  mov     [rsp+170h+var_140], 1AAh
0x18001e485  test    rax, rax
0x18001e488  jz      loc_18001E573
0x18001e48e  mov     rcx, rbx
0x18001e491  inc     rcx
0x18001e494  cmp     [rax+rcx], r13b
0x18001e498  jnz     short loc_18001E491
0x18001e49a  inc     ecx
0x18001e49c  lea     rdx, WlidCli_TraceFunction_Enter
0x18001e4a3  jmp     loc_18001E13B
0x18001e4a8  cmp     cs:byte_1801C36C5, r13b
0x18001e4af  jge     loc_18001E18B
0x18001e4b5  mov     edx, 5Ch ; '\'; Ch
0x18001e4ba  mov     rcx, rsi; Str
0x18001e4bd  call    cs:__imp_strrchr
0x18001e4c3  test    rax, rax
0x18001e4c6  jz      short loc_18001E51E
0x18001e4c8  inc     rax
0x18001e4cb  mov     [rsp+170h+var_140], 1AAh
0x18001e4d3  test    rax, rax
0x18001e4d6  jz      loc_18001E582
0x18001e4dc  mov     rcx, rbx
0x18001e4df  inc     rcx
0x18001e4e2  cmp     [rax+rcx], r13b
0x18001e4e6  jnz     short loc_18001E4DF
0x18001e4e8  inc     ecx
  ... truncated ...
```
