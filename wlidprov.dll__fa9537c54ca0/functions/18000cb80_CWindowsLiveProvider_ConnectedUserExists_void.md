# CWindowsLiveProvider::ConnectedUserExists(void)

- ea: `0x18000cb80`
- end: `0x18000cea2`
- name: `?ConnectedUserExists@CWindowsLiveProvider@@AEAA_NXZ`
- size: `802`
- prototype: `bool __fastcall(CWindowsLiveProvider *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000c4f0`

## callees

- `0x1800039c8`
- `0x180003c44`
- `0x180004b00`
- `0x180004b2c`
- `0x180009630`
- `0x180009e00`
- `0x18000a400`
- `0x18000cb80`
- `0x180010be0`
- `0x1800113e8`
- `0x180011a80`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ce6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ce6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccfb`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000cca4`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000cca4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000ccf1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000ccf1`

## string_xrefs

- `0x18000ccb8`: `CreateWellKnownSid failed. (0x%x)`
- `0x18000cd05`: `ConvertSidToStringSid failed. (0x%x)`
- `0x18000cd8e`: `regStoredIdentityKey.Open failed. (0x%x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
unsigned __int8 __fastcall CWindowsLiveProvider::ConnectedUserExists(CWindowsLiveProvider *this)
{
  int v1; // r8d
  int v2; // r8d
  int v3; // eax
  int v4; // r8d
  int v5; // r8d
  unsigned __int16 *BufferSetLength; // rax
  int v7; // ebx
  int v8; // r8d
  unsigned __int8 v9; // al
  unsigned __int8 v10; // bl
  const unsigned __int16 *v12; // [rsp+20h] [rbp-108h]
  PFILETIME v13; // [rsp+20h] [rbp-108h]
  PFILETIME v14; // [rsp+20h] [rbp-108h]
  unsigned __int8 v15; // [rsp+30h] [rbp-F8h] BYREF
  unsigned int v16; // [rsp+34h] [rbp-F4h] BYREF
  DWORD cbSid; // [rsp+38h] [rbp-F0h] BYREF
  __int64 v18; // [rsp+40h] [rbp-E8h] BYREF
  unsigned __int16 *v19; // [rsp+48h] [rbp-E0h] BYREF
  HKEY hKey[3]; // [rsp+50h] [rbp-D8h] BYREF
  LPWSTR StringSid[7]; // [rsp+68h] [rbp-C0h] BYREF
  _BYTE pSid[80]; // [rsp+A0h] [rbp-88h] BYREF
  CPassportException *v23; // [rsp+F0h] [rbp-38h] BYREF
  ATL::CAtlException *v24; // [rsp+F8h] [rbp-30h] BYREF
  __int64 v25; // [rsp+100h] [rbp-28h] BYREF
  const wil::ResultException *v26; // [rsp+108h] [rbp-20h] BYREF

  memset_0(pSid, 0, 0x44u);
  memset(StringSid, 0, 24);
  cbSid = 68;
  memset(hKey, 0, sizeof(hKey));
  v19 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v18 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v16 = 0x2000;
  v15 = 1;
  StringSid[3] = (LPWSTR)"CWindowsLiveProvider::ConnectedUserExists";
  StringSid[4] = (LPWSTR)&v15;
  StringSid[5] = 0;
  StringSid[6] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
    "CWindowsLiveProvider::ConnectedUserExists",
    (const char *)0x186,
    0,
    v12);
  if ( CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
  {
    if ( ConvertSidToStringSidW(pSid, StringSid) )
    {
      try
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v19,
          L"%s\\%s",
          StringSid[0],
          L"Software\\Microsoft\\IdentityCRL\\StoredIdentities");
        v3 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_USERS, v19, 0x20019u);
        if ( v3 == 2 )
        {
          v15 = 0;
          MsaTracingInternal::TraceFunctionExit(
            (MsaTracingInternal *)"CWindowsLiveProvider::ConnectedUserExists",
            0,
            v4);
        }
        else if ( v3 )
        {
          LODWORD(v13) = v3;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
            0x1A2u,
            L"regStoredIdentityKey.Open failed. (0x%x)",
            v13);
          MsaTracingInternal::TraceFunctionExit(
            (MsaTracingInternal *)"CWindowsLiveProvider::ConnectedUserExists",
            (const char *)v15,
            v5);
        }
        else
        {
          BufferSetLength = (unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(&v18);
          v7 = ATL::CRegKey::EnumKey((ATL::CRegKey *)hKey, 0, BufferSetLength, &v16, 0);
          ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&v18, 0xFFFFFFFFLL);
          LODWORD(v14) = v7;
          TracePrintW(
            5u,
            "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
            0x1AAu,
            L"regStoredIdentityKey.EnumKey returned. (0x%x)",
            v14);
          if ( v7 == 259 )
          {
            v9 = 0;
            v15 = 0;
          }
          else
          {
            v9 = v15;
          }
          MsaTracingInternal::TraceFunctionExit(
            (MsaTracingInternal *)"CWindowsLiveProvider::ConnectedUserExists",
            (const char *)v9,
            v8);
        }
      }
      catch ( CPassportException *v23 )
      {
      }
      catch ( ATL::CAtlException *v24 )
      {
      }
      catch ( std::bad_alloc )
      {
      }
      catch ( long v25 )
      {
      }
      catch ( const wil::ResultException *v26 )
      {
      }
    }
    else
    {
      LODWORD(v13) = GetLastError();
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
        0x191u,
        L"ConvertSidToStringSid failed. (0x%x)",
        v13);
      MsaTracingInternal::TraceFunctionExit(
        (MsaTracingInternal *)"CWindowsLiveProvider::ConnectedUserExists",
        (const char *)v15,
        v2);
    }
  }
  else
  {
    LODWORD(v13) = GetLastError();
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
      0x18Bu,
      L"CreateWellKnownSid failed. (0x%x)",
      v13);
    MsaTracingInternal::TraceFunctionExit(
      (MsaTracingInternal *)"CWindowsLiveProvider::ConnectedUserExists",
      (const char *)v15,
      v1);
  }
  v10 = v15;
  ATL::CStringData::Release((ATL::CStringData *)(v18 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v19 - 12));
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(StringSid);
  return v10;
}

```

## disassembly

```asm
0x18000cb80  mov     [rsp+arg_0], rbx
0x18000cb85  mov     [rsp+arg_8], rsi
0x18000cb8a  push    rdi
0x18000cb8b  sub     rsp, 120h
0x18000cb92  mov     rax, cs:__security_cookie
0x18000cb99  xor     rax, rsp
0x18000cb9c  mov     [rsp+128h+var_18], rax
0x18000cba4  mov     ebx, 44h ; 'D'
0x18000cba9  mov     r8d, ebx; Size
0x18000cbac  xor     edx, edx; Val
0x18000cbae  lea     rcx, [rsp+128h+pSid]; void *
0x18000cbb6  call    memset_0
0x18000cbbb  mov     [rsp+128h+StringSid], 0
0x18000cbc4  mov     [rsp+128h+var_B0], 0
0x18000cbcd  mov     [rsp+128h+var_B8], 0
0x18000cbd6  mov     [rsp+128h+cbSid], ebx
0x18000cbda  mov     [rsp+128h+hKey], 0
0x18000cbe3  mov     [rsp+128h+var_D0], 0
0x18000cbec  mov     [rsp+128h+var_C8], 0
0x18000cbf5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000cbfc  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000cc03  mov     rax, [rax+18h]
0x18000cc07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc0c  add     rax, 18h
0x18000cc10  mov     [rsp+128h+var_E0], rax
0x18000cc15  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000cc1c  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000cc23  mov     rax, [rax+18h]
0x18000cc27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc2c  add     rax, 18h
0x18000cc30  mov     [rsp+128h+var_E8], rax
0x18000cc35  mov     [rsp+128h+var_F4], 2000h
0x18000cc3d  mov     [rsp+128h+var_F8], 1
0x18000cc42  lea     rdi, aCwindowslivepr_1; "CWindowsLiveProvider::ConnectedUserExis"...
0x18000cc49  mov     [rsp+128h+var_A8], rdi
0x18000cc51  lea     rax, [rsp+128h+var_F8]
0x18000cc56  mov     [rsp+128h+var_A0], rax
0x18000cc5e  mov     [rsp+128h+var_98], 0
0x18000cc6a  mov     [rsp+128h+var_90], 0
0x18000cc76  xor     r9d, r9d; unsigned int
0x18000cc79  mov     r8d, 186h; char *
0x18000cc7f  mov     rdx, rdi; char *
0x18000cc82  lea     rsi, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18000cc89  mov     rcx, rsi; this
0x18000cc8c  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000cc91  nop
0x18000cc92  lea     r9, [rsp+128h+cbSid]; cbSid
0x18000cc97  lea     r8, [rsp+128h+pSid]; pSid
0x18000cc9f  xor     edx, edx; DomainSid
0x18000cca1  lea     ecx, [rbx-2Eh]; WellKnownSidType
0x18000cca4  call    cs:__imp_CreateWellKnownSid
0x18000ccaa  test    eax, eax
0x18000ccac  jnz     short loc_18000CCE4
0x18000ccae  call    cs:__imp_GetLastError
0x18000ccb4  mov     dword ptr [rsp+128h+var_108], eax
0x18000ccb8  lea     r9, aCreatewellknow; "CreateWellKnownSid failed. (0x%x)"
0x18000ccbf  mov     r8d, 18Bh; unsigned int
0x18000ccc5  mov     rdx, rsi; char *
0x18000ccc8  lea     ecx, [rbx-42h]; unsigned __int8
0x18000cccb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000ccd0  nop
0x18000ccd1  movzx   edx, [rsp+128h+var_F8]; char *
0x18000ccd6  mov     rcx, rdi; this
0x18000ccd9  call    ?TraceFunctionExit@MsaTracingInternal@@YAKPEBDJ@Z; MsaTracingInternal::TraceFunctionExit(char const *,long)
0x18000ccde  nop
0x18000ccdf  jmp     loc_18000CE3E
0x18000cce4  lea     rdx, [rsp+128h+StringSid]; StringSid
0x18000cce9  lea     rcx, [rsp+128h+pSid]; Sid
0x18000ccf1  call    cs:__imp_ConvertSidToStringSidW
0x18000ccf7  test    eax, eax
0x18000ccf9  jnz     short loc_18000CD33
0x18000ccfb  call    cs:__imp_GetLastError
0x18000cd01  mov     dword ptr [rsp+128h+var_108], eax
0x18000cd05  lea     r9, aConvertsidtost_1; "ConvertSidToStringSid failed. (0x%x)"
0x18000cd0c  mov     r8d, 191h; unsigned int
0x18000cd12  mov     rdx, rsi; char *
0x18000cd15  mov     ecx, 2; unsigned __int8
0x18000cd1a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000cd1f  nop
0x18000cd20  movzx   edx, [rsp+128h+var_F8]; char *
0x18000cd25  mov     rcx, rdi; this
0x18000cd28  call    ?TraceFunctionExit@MsaTracingInternal@@YAKPEBDJ@Z; MsaTracingInternal::TraceFunctionExit(char const *,long)
0x18000cd2d  nop
0x18000cd2e  jmp     loc_18000CE3E
0x18000cd33  lea     r9, aSoftwareMicros_3; "Software\\Microsoft\\IdentityCRL\\Store"...
0x18000cd3a  mov     r8, [rsp+128h+StringSid]
0x18000cd3f  lea     rdx, aSS; "%s\\%s"
0x18000cd46  lea     rcx, [rsp+128h+var_E0]
0x18000cd4b  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000cd50  mov     r9d, 20019h; unsigned int
0x18000cd56  mov     r8, [rsp+128h+var_E0]; unsigned __int16 *
0x18000cd5b  mov     rdx, 0FFFFFFFF80000003h; HKEY
0x18000cd62  lea     rcx, [rsp+128h+hKey]; this
0x18000cd67  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000cd6c  cmp     eax, 2
0x18000cd6f  jnz     short loc_18000CD86
0x18000cd71  mov     [rsp+128h+var_F8], 0
0x18000cd76  xor     edx, edx; char *
0x18000cd78  mov     rcx, rdi; this
0x18000cd7b  call    ?TraceFunctionExit@MsaTracingInternal@@YAKPEBDJ@Z; MsaTracingInternal::TraceFunctionExit(char const *,long)
0x18000cd80  nop
0x18000cd81  jmp     loc_18000CE3E
0x18000cd86  test    eax, eax
0x18000cd88  jz      short loc_18000CDBC
0x18000cd8a  mov     dword ptr [rsp+128h+var_108], eax
0x18000cd8e  lea     r9, aRegstoredident_0; "regStoredIdentityKey.Open failed. (0x%x"...
0x18000cd95  mov     r8d, 1A2h; unsigned int
0x18000cd9b  mov     rdx, rsi; char *
0x18000cd9e  mov     ecx, 2; unsigned __int8
0x18000cda3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000cda8  nop
0x18000cda9  movzx   edx, [rsp+128h+var_F8]; char *
0x18000cdae  mov     rcx, rdi; this
0x18000cdb1  call    ?TraceFunctionExit@MsaTracingInternal@@YAKPEBDJ@Z; MsaTracingInternal::TraceFunctionExit(char const *,long)
0x18000cdb6  nop
0x18000cdb7  jmp     loc_18000CE3E
0x18000cdbc  mov     edx, [rsp+128h+var_F4]
0x18000cdc0  lea     rcx, [rsp+128h+var_E8]
0x18000cdc5  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x18000cdca  mov     [rsp+128h+var_108], 0; PFILETIME
0x18000cdd3  lea     r9, [rsp+128h+var_F4]; unsigned int *
0x18000cdd8  mov     r8, rax; unsigned __int16 *
0x18000cddb  xor     edx, edx; unsigned int
0x18000cddd  lea     rcx, [rsp+128h+hKey]; this
0x18000cde2  call    ?EnumKey@CRegKey@ATL@@QEAAJKPEAGPEAKPEAU_FILETIME@@@Z; ATL::CRegKey::EnumKey(ulong,ushort *,ulong *,_FILETIME *)
0x18000cde7  mov     ebx, eax
0x18000cde9  or      edx, 0FFFFFFFFh
0x18000cdec  lea     rcx, [rsp+128h+var_E8]
0x18000cdf1  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18000cdf6  mov     dword ptr [rsp+128h+var_108], ebx
0x18000cdfa  lea     r9, aRegstoredident; "regStoredIdentityKey.EnumKey returned. "...
0x18000ce01  mov     r8d, 1AAh; unsigned int
0x18000ce07  mov     rdx, rsi; char *
0x18000ce0a  mov     ecx, 5; unsigned __int8
0x18000ce0f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000ce14  cmp     ebx, 103h
0x18000ce1a  jnz     short loc_18000CE24
0x18000ce1c  xor     al, al
0x18000ce1e  mov     [rsp+128h+var_F8], al
0x18000ce22  jmp     short loc_18000CE28
0x18000ce24  mov     al, [rsp+128h+var_F8]
0x18000ce28  movzx   edx, al; char *
0x18000ce2b  mov     rcx, rdi; this
0x18000ce2e  call    ?TraceFunctionExit@MsaTracingInternal@@YAKPEBDJ@Z; MsaTracingInternal::TraceFunctionExit(char const *,long)
0x18000ce33  nop
0x18000ce34  jmp     short loc_18000CE3E
0x18000ce36  jmp     short loc_18000CE3E
0x18000ce38  jmp     short loc_18000CE3E
0x18000ce3a  jmp     short loc_18000CE3E
0x18000ce3c  jmp     short $+2
0x18000ce3e  mov     bl, [rsp+128h+var_F8]
0x18000ce42  mov     rcx, [rsp+128h+var_E8]
0x18000ce47  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000ce4b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000ce50  nop
0x18000ce51  mov     rcx, [rsp+128h+var_E0]
0x18000ce56  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000ce5a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000ce5f  nop
0x18000ce60  mov     rcx, [rsp+128h+hKey]; hKey
0x18000ce65  test    rcx, rcx
0x18000ce68  jz      short loc_18000CE71
0x18000ce6a  call    cs:__imp_RegCloseKey
0x18000ce70  nop
0x18000ce71  lea     rcx, [rsp+128h+StringSid]
0x18000ce76  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x18000ce7b  mov     al, bl
0x18000ce7d  mov     rcx, [rsp+128h+var_18]
0x18000ce85  xor     rcx, rsp; StackCookie
0x18000ce88  call    __security_check_cookie
0x18000ce8d  lea     r11, [rsp+128h+var_8]
0x18000ce95  mov     rbx, [r11+10h]
0x18000ce99  mov     rsi, [r11+18h]
0x18000ce9d  mov     rsp, r11
0x18000cea0  pop     rdi
0x18000cea1  retn
```
