# CWMCService::Install(ushort *)

- ea: `0x14004e7c0`
- end: `0x14004ef53`
- name: `?Install@CWMCService@@UEAAKPEAG@Z`
- size: `1939`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, LPCWSTR lpDependencies)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400479b0`

## callees

- `0x140008eac`
- `0x14000b3b0`
- `0x14000c920`
- `0x140018df0`
- `0x140024688`
- `0x14003b08c`
- `0x14003e5f4`
- `0x14003f17c`
- `0x1400448e0`
- `0x140045f20`
- `0x140047798`
- `0x1400488f4`
- `0x14004a79c`
- `0x14004a834`
- `0x14004b074`
- `0x14004bf30`
- `0x14004e7c0`
- `0x140051db0`
- `0x140054624`
- `0x1400926e0`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14004ec14`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14004ec14`
- `ADVAPI32!RegSetKeySecurity` at `0x14004ec7a`
- `ADVAPI32!RegSetKeySecurity` at `0x14004ec7a`
- `KERNEL32!GetCurrentProcess` at `0x14004eb6a`
- `KERNEL32!GetCurrentProcess` at `0x14004eb6a`
- `KERNEL32!IsWow64Process` at `0x14004eb77`
- `KERNEL32!IsWow64Process` at `0x14004eb77`
- `KERNEL32!LocalFree` at `0x14004ecc5`
- `KERNEL32!LocalFree` at `0x14004ecc5`
- `OLEAUT32!__imp_LoadTypeLib` at `0x14004ea0b`
- `OLEAUT32!__imp_LoadTypeLib` at `0x14004ea0b`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x14004ea81`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x14004ea81`

## string_xrefs

- `0x14004eedf`: `SOFTWARE\Microsoft\Windows Media Player NSS\3.0\MAC Access Control`

## pseudocode

```c
__int64 __fastcall CWMCService::Install(const unsigned __int16 **this, LPCWSTR lpDependencies)
{
  unsigned int KeyAndSetACLs; // ebx
  HRESULT v5; // edi
  PVOID *v6; // r10
  PVOID *v8; // r10
  HANDLE CurrentProcess; // rax
  unsigned __int16 *v10; // r9
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // [rsp+20h] [rbp-89h]
  struct _SECURITY_ATTRIBUTES *v20; // [rsp+30h] [rbp-79h]
  unsigned int *v21; // [rsp+38h] [rbp-71h]
  ITypeLib *pptlib; // [rsp+40h] [rbp-69h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-61h] BYREF
  _QWORD v24[2]; // [rsp+50h] [rbp-59h] BYREF
  HKEY hKey[3]; // [rsp+60h] [rbp-49h] BYREF
  _QWORD v26[2]; // [rsp+78h] [rbp-31h] BYREF
  char v27; // [rsp+88h] [rbp-21h]
  int v28; // [rsp+8Ch] [rbp-1Dh]
  __int128 v29; // [rsp+90h] [rbp-19h]
  __int64 v30; // [rsp+A0h] [rbp-9h]
  int v31; // [rsp+A8h] [rbp-1h]
  struct _EVENT_DESCRIPTOR v32; // [rsp+B0h] [rbp+7h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, lpDependencies);
  }
  v24[0] = &ATL::CSecurityDesc::`vftable';
  v24[1] = 0;
  v26[1] = 0;
  v27 = 0;
  v28 = 2;
  v26[0] = &ATL::CDacl::`vftable';
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  KeyAndSetACLs = CNTService::Install((CNTService *)this, lpDependencies);
  if ( !KeyAndSetACLs )
  {
    pptlib = 0;
    v5 = LoadTypeLib(g_strModuleFileName, &pptlib);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v5 >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_dSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        160,
        (unsigned int)&WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
        v5,
        (__int64)g_strModuleFileName,
        v5);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 < 0 )
    {
      v32.Id = 14305;
      *(_DWORD *)((char *)&v32.Keyword + 2) = 0;
    }
    else
    {
      v5 = RegisterTypeLib(pptlib, g_strModuleFileName, 0);
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v5 >> 31) & 0xFFFFFFFD) + 5 )
      {
        v19 = v5;
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          161,
          &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
          (unsigned int)v5);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v5 >= 0 )
      {
LABEL_40:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pptlib);
        if ( !KeyAndSetACLs )
        {
          LODWORD(pptlib) = 0;
          CurrentProcess = GetCurrentProcess();
          IsWow64Process(CurrentProcess, (PBOOL)&pptlib);
          if ( (_DWORD)pptlib )
          {
            memset(hKey, 0, sizeof(hKey));
            KeyAndSetACLs = ATL::CRegKey::Create(
                              (ATL::CRegKey *)hKey,
                              HKEY_LOCAL_MACHINE,
                              L"SOFTWARE\\Microsoft\\Windows Media Player NSS\\3.0",
                              v10,
                              v19,
                              0xF013Fu,
                              v20,
                              v21);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v11 = 5;
              if ( KeyAndSetACLs )
                v11 = 2;
              if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v11 )
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  163,
                  &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                  KeyAndSetACLs);
            }
            if ( !KeyAndSetACLs )
            {
              SecurityDescriptor = 0;
              if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
                      L"D:P(A;CI;KA;;;BA)(A;CIIO;KA;;;CO)(A;CI;KA;;;NS)(A;CI;CCDCLCSWRPSDRC;;;PU)(A;CI;KA;;;SY)(A;CI;KR;;;BU)",
                      1u,
                      &SecurityDescriptor,
                      0) )
                KeyAndSetACLs = 1603;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v12 = 5;
                if ( KeyAndSetACLs )
                  v12 = 2;
                if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v12 )
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    164,
                    &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                    KeyAndSetACLs);
              }
              if ( !KeyAndSetACLs )
              {
                KeyAndSetACLs = RegSetKeySecurity(hKey[0], 4u, SecurityDescriptor);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v13 = 5;
                  if ( KeyAndSetACLs )
                    v13 = 2;
                  if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v13 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      165,
                      &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                      KeyAndSetACLs);
                }
              }
              LocalFree(SecurityDescriptor);
            }
            ATL::CRegKey::Close((ATL::CRegKey *)hKey);
          }
          else
          {
            KeyAndSetACLs = CreateKeyAndSetACLs(
                              L"SOFTWARE\\Microsoft\\Windows Media Player NSS\\3.0",
                              L"S-1-5-80-2375682873-768044350-3534595160-1005545032-2873800392",
                              0x10000000u,
                              3u);
            if ( KeyAndSetACLs == 13 )
              KeyAndSetACLs = 1603;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v14 = 5;
              if ( KeyAndSetACLs )
                v14 = 2;
              if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v14 )
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  166,
                  &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                  KeyAndSetACLs);
            }
          }
          if ( !KeyAndSetACLs )
          {
            KeyAndSetACLs = CreateKeyAndSetACLs(
                              L"SOFTWARE\\Microsoft\\Windows Media Player NSS\\3.0\\Devices",
                              L"S-1-5-4",
                              0x20019u,
                              3u);
            if ( KeyAndSetACLs == 13 )
              KeyAndSetACLs = 1603;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v15 = 5;
              if ( KeyAndSetACLs )
                v15 = 2;
              if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v15 )
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  167,
                  &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                  KeyAndSetACLs);
            }
            if ( !KeyAndSetACLs )
            {
              KeyAndSetACLs = CreateKeyAndSetACLs(
                                L"SOFTWARE\\Microsoft\\Windows Media Player NSS\\3.0\\Events",
                                L"S-1-5-4",
                                4u,
                                0);
              if ( KeyAndSetACLs == 13 )
                KeyAndSetACLs = 1603;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v16 = 5;
                if ( KeyAndSetACLs )
                  v16 = 2;
                if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v16 )
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    168,
                    &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                    KeyAndSetACLs);
              }
              if ( !KeyAndSetACLs )
              {
                KeyAndSetACLs = CreateKeyAndSetACLs(
                                  L"SOFTWARE\\Microsoft\\Windows Media Player NSS\\3.0\\Events",
                                  L"S-1-5-4",
                                  0xF003Fu,
                                  0xBu);
                if ( KeyAndSetACLs == 13 )
                  KeyAndSetACLs = 1603;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v17 = 5;
                  if ( KeyAndSetACLs )
                    v17 = 2;
                  if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v17 )
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      169,
                      &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                      KeyAndSetACLs);
                }
                if ( !KeyAndSetACLs )
                {
                  KeyAndSetACLs = CreateKeyAndSetACLs(
                                    L"SOFTWARE\\Microsoft\\Windows Media Player NSS\\3.0\\MAC Access Control",
                                    L"S-1-5-4",
                                    0x20019u,
                                    0);
                  if ( KeyAndSetACLs == 13 )
                    KeyAndSetACLs = 1603;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v18 = 5;
                    if ( KeyAndSetACLs )
                      v18 = 2;
                    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v18 )
                      WPP_SF_Dd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        170,
                        &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                        KeyAndSetACLs);
                  }
                  if ( !KeyAndSetACLs )
                  {
                    KeyAndSetACLs = CWMCService::ReserveURLNamespace((CWMCService *)this);
LABEL_17:
                    v6 = (PVOID *)WPP_GLOBAL_Control;
                    goto LABEL_18;
                  }
                }
              }
            }
          }
          v32.Id = 14306;
          *(_QWORD *)&v32.Version = 133120;
          *(_DWORD *)((char *)&v32.Keyword + 2) = 0;
          HIWORD(v32.Keyword) = 0x4000;
LABEL_12:
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&pptlib);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
            &pptlib,
            L"%lu",
            KeyAndSetACLs);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&SecurityDescriptor);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
            &SecurityDescriptor,
            L"0x%08x",
            (unsigned int)v5);
          CNTService::LogEvent(
            (CNTService *)this,
            &v32,
            this[5],
            (const unsigned __int16 *)pptlib,
            (const unsigned __int16 *)SecurityDescriptor);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              171,
              (unsigned int)&WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
              (unsigned int)this[5],
              KeyAndSetACLs);
          }
          ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&SecurityDescriptor);
          ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&pptlib);
          goto LABEL_17;
        }
        goto LABEL_10;
      }
      v32.Id = 14304;
      *(_DWORD *)((char *)&v32.Keyword + 2) = 0;
    }
    HIWORD(v32.Keyword) = 0x4000;
    *(_QWORD *)&v32.Version = 133120;
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 && *((_BYTE *)v8 + 25) >= 4u )
      WPP_SF_(v8[2], 162, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
    KeyAndSetACLs = 1603;
    goto LABEL_40;
  }
  v5 = 0;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, KeyAndSetACLs);
LABEL_10:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v32.Id )
    goto LABEL_12;
LABEL_18:
  if ( v6 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v6 + 28) & 1) != 0
    && *((unsigned __int8 *)v6 + 25) >= (unsigned int)(KeyAndSetACLs != 0 ? 2 : 5) )
  {
    WPP_SF_d(v6[2], 172, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, KeyAndSetACLs);
  }
  ATL::CDacl::~CDacl((ATL::CDacl *)v26);
  v24[0] = &ATL::CSecurityDesc::`vftable';
  ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)v24);
  return KeyAndSetACLs;
}

```

## disassembly

```asm
0x14004e7c0  mov     [rsp-8+arg_10], rbx
0x14004e7c5  push    rbp
0x14004e7c6  push    rsi
0x14004e7c7  push    rdi
0x14004e7c8  push    r12
0x14004e7ca  push    r13
0x14004e7cc  push    r14
0x14004e7ce  push    r15
0x14004e7d0  lea     rbp, [rsp-27h]
0x14004e7d5  sub     rsp, 0D0h
0x14004e7dc  mov     rax, cs:__security_cookie
0x14004e7e3  xor     rax, rsp
0x14004e7e6  mov     [rbp+57h+var_40], rax
0x14004e7ea  mov     rbx, rdx
0x14004e7ed  mov     rsi, rcx
0x14004e7f0  lea     rax, WPP_GLOBAL_Control
0x14004e7f7  mov     r13d, 5
0x14004e7fd  lea     r12, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004e804  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e80b  cmp     rcx, rax
0x14004e80e  jz      short loc_14004E830
0x14004e810  test    byte ptr [rcx+1Ch], 1
0x14004e814  jz      short loc_14004E830
0x14004e816  cmp     [rcx+19h], r13b
0x14004e81a  jb      short loc_14004E830
0x14004e81c  mov     edx, 9Eh
0x14004e821  mov     r9, rbx
0x14004e824  mov     r8, r12
0x14004e827  mov     rcx, [rcx+10h]
0x14004e82b  call    WPP_SF_S
0x14004e830  lea     rax, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x14004e837  mov     [rbp+57h+var_B0], rax
0x14004e83b  xor     r14d, r14d
0x14004e83e  mov     [rbp+57h+var_A8], r14
0x14004e842  mov     [rbp+57h+var_80], r14
0x14004e846  mov     [rbp+57h+var_78], r14b
0x14004e84a  lea     r15d, [r14+2]
0x14004e84e  mov     [rbp+57h+var_74], r15d
0x14004e852  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x14004e859  mov     [rbp+57h+var_88], rax
0x14004e85d  xorps   xmm0, xmm0
0x14004e860  movdqu  [rbp+57h+var_70], xmm0
0x14004e865  mov     [rbp+57h+var_60], r14
0x14004e869  mov     [rbp+57h+var_58], r14d
0x14004e86d  movups  xmmword ptr [rbp+57h+var_50.Id], xmm0
0x14004e871  mov     rdx, rbx; lpDependencies
0x14004e874  mov     rcx, rsi; this
0x14004e877  call    ?Install@CNTService@@UEAAKPEAG@Z; CNTService::Install(ushort *)
0x14004e87c  mov     ebx, eax
0x14004e87e  test    eax, eax
0x14004e880  jz      loc_14004E9FC
0x14004e886  mov     edi, r14d
0x14004e889  mov     r10, cs:WPP_GLOBAL_Control
0x14004e890  lea     rax, WPP_GLOBAL_Control
0x14004e897  cmp     r10, rax
0x14004e89a  jz      short loc_14004E8C3
0x14004e89c  test    [r10+1Ch], r15b
0x14004e8a0  jz      short loc_14004E8C3
0x14004e8a2  cmp     [r10+19h], r15b
0x14004e8a6  jb      short loc_14004E8C3
0x14004e8a8  mov     edx, 9Fh
0x14004e8ad  mov     r9d, ebx
0x14004e8b0  mov     r8, r12
0x14004e8b3  mov     rcx, [r10+10h]
0x14004e8b7  call    WPP_SF_d
0x14004e8bc  mov     r10, cs:WPP_GLOBAL_Control
0x14004e8c3  cmp     r14w, [rbp+57h+var_50.Id]
0x14004e8c8  jz      loc_14004E978
0x14004e8ce  lea     rcx, [rbp+57h+pptlib]
0x14004e8d2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14004e8d7  nop
0x14004e8d8  mov     r8d, ebx
0x14004e8db  lea     rdx, aLu; "%lu"
0x14004e8e2  lea     rcx, [rbp+57h+pptlib]
0x14004e8e6  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Format(ushort const *,...)
0x14004e8eb  lea     rcx, [rbp+57h+SecurityDescriptor]
0x14004e8ef  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14004e8f4  nop
0x14004e8f5  mov     r8d, edi
0x14004e8f8  lea     rdx, a0x08x; "0x%08x"
0x14004e8ff  lea     rcx, [rbp+57h+SecurityDescriptor]
0x14004e903  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Format(ushort const *,...)
0x14004e908  mov     rax, [rbp+57h+SecurityDescriptor]
0x14004e90c  mov     [rsp+100h+var_E0], rax; unsigned __int16 *
0x14004e911  mov     r9, [rbp+57h+pptlib]; unsigned __int16 *
0x14004e915  mov     r8, [rsi+28h]; unsigned __int16 *
0x14004e919  lea     rdx, [rbp+57h+var_50]; struct _EVENT_DESCRIPTOR *
0x14004e91d  mov     rcx, rsi; this
0x14004e920  call    ?LogEvent@CNTService@@QEAAXAEBU_EVENT_DESCRIPTOR@@PEBG11@Z; CNTService::LogEvent(_EVENT_DESCRIPTOR const &,ushort const *,ushort const *,ushort const *)
0x14004e925  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e92c  lea     rax, WPP_GLOBAL_Control
0x14004e933  cmp     rcx, rax
0x14004e936  jz      short loc_14004E95E
0x14004e938  test    [rcx+1Ch], r15b
0x14004e93c  jz      short loc_14004E95E
0x14004e93e  cmp     [rcx+19h], r15b
0x14004e942  jb      short loc_14004E95E
0x14004e944  mov     edx, 0ABh
0x14004e949  mov     dword ptr [rsp+100h+var_E0], ebx
0x14004e94d  mov     r9, [rsi+28h]
0x14004e951  mov     r8, r12
0x14004e954  mov     rcx, [rcx+10h]
0x14004e958  call    WPP_SF_Sd
0x14004e95d  nop
0x14004e95e  lea     rcx, [rbp+57h+SecurityDescriptor]
0x14004e962  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14004e967  nop
0x14004e968  lea     rcx, [rbp+57h+pptlib]
0x14004e96c  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14004e971  mov     r10, cs:WPP_GLOBAL_Control
0x14004e978  lea     rax, WPP_GLOBAL_Control
0x14004e97f  cmp     r10, rax
0x14004e982  jz      short loc_14004E9B5
0x14004e984  test    byte ptr [r10+1Ch], 1
0x14004e989  jz      short loc_14004E9B5
0x14004e98b  movzx   edx, byte ptr [r10+19h]
0x14004e990  mov     eax, ebx
0x14004e992  neg     eax
0x14004e994  sbb     ecx, ecx
0x14004e996  and     ecx, 0FFFFFFFDh
0x14004e999  add     ecx, r13d
0x14004e99c  cmp     edx, ecx
0x14004e99e  jb      short loc_14004E9B5
0x14004e9a0  mov     edx, 0ACh
0x14004e9a5  mov     r9d, ebx
0x14004e9a8  mov     r8, r12
0x14004e9ab  mov     rcx, [r10+10h]
0x14004e9af  call    WPP_SF_d
0x14004e9b4  nop
0x14004e9b5  lea     rcx, [rbp+57h+var_88]; this
0x14004e9b9  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x14004e9be  nop
0x14004e9bf  lea     rax, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x14004e9c6  mov     [rbp+57h+var_B0], rax
0x14004e9ca  lea     rcx, [rbp+57h+var_B0]; this
0x14004e9ce  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x14004e9d3  mov     eax, ebx
0x14004e9d5  mov     rcx, [rbp+57h+var_40]
0x14004e9d9  xor     rcx, rsp; StackCookie
0x14004e9dc  call    __security_check_cookie
0x14004e9e1  mov     rbx, [rsp+100h+arg_10]
0x14004e9e9  add     rsp, 0D0h
0x14004e9f0  pop     r15
0x14004e9f2  pop     r14
0x14004e9f4  pop     r13
0x14004e9f6  pop     r12
0x14004e9f8  pop     rdi
0x14004e9f9  pop     rsi
0x14004e9fa  pop     rbp
0x14004e9fb  retn
0x14004e9fc  mov     [rbp+57h+pptlib], r14
0x14004ea00  lea     rdx, [rbp+57h+pptlib]; pptlib
0x14004ea04  mov     rcx, cs:?g_strModuleFileName@@3V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@A; szFile
0x14004ea0b  call    cs:__imp_LoadTypeLib
0x14004ea11  mov     edi, eax
0x14004ea13  mov     r10, cs:WPP_GLOBAL_Control
0x14004ea1a  lea     rax, WPP_GLOBAL_Control
0x14004ea21  cmp     r10, rax
0x14004ea24  jz      short loc_14004EA6B
0x14004ea26  test    [r10+1Ch], r15b
0x14004ea2a  jz      short loc_14004EA6B
0x14004ea2c  mov     ecx, edi
0x14004ea2e  sar     ecx, 1Fh
0x14004ea31  and     ecx, 0FFFFFFFDh
0x14004ea34  add     ecx, r13d
0x14004ea37  movzx   eax, byte ptr [r10+19h]
0x14004ea3c  cmp     eax, ecx
0x14004ea3e  jb      short loc_14004EA6B
0x14004ea40  mov     edx, 0A0h
0x14004ea45  mov     [rsp+100h+var_D8], edi
0x14004ea49  mov     rax, cs:?g_strModuleFileName@@3V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@A; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> g_strModuleFileName
0x14004ea50  mov     [rsp+100h+var_E0], rax; unsigned int
0x14004ea55  mov     r9d, edi
0x14004ea58  mov     r8, r12
0x14004ea5b  mov     rcx, [r10+10h]
0x14004ea5f  call    WPP_SF_dSd
0x14004ea64  mov     r10, cs:WPP_GLOBAL_Control
0x14004ea6b  test    edi, edi
0x14004ea6d  js      loc_14004EAFC
0x14004ea73  xor     r8d, r8d; szHelpDir
0x14004ea76  mov     rdx, cs:?g_strModuleFileName@@3V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@A; szFullPath
0x14004ea7d  mov     rcx, [rbp+57h+pptlib]; ptlib
0x14004ea81  call    cs:__imp_RegisterTypeLib
0x14004ea87  mov     edi, eax
0x14004ea89  mov     r10, cs:WPP_GLOBAL_Control
0x14004ea90  lea     rax, WPP_GLOBAL_Control
0x14004ea97  cmp     r10, rax
0x14004ea9a  jz      short loc_14004EAD5
0x14004ea9c  test    [r10+1Ch], r15b
0x14004eaa0  jz      short loc_14004EAD5
0x14004eaa2  mov     ecx, edi
0x14004eaa4  sar     ecx, 1Fh
0x14004eaa7  and     ecx, 0FFFFFFFDh
0x14004eaaa  add     ecx, r13d
0x14004eaad  movzx   eax, byte ptr [r10+19h]
0x14004eab2  cmp     eax, ecx
0x14004eab4  jb      short loc_14004EAD5
0x14004eab6  mov     edx, 0A1h
0x14004eabb  mov     dword ptr [rsp+100h+var_E0], edi
0x14004eabf  mov     r9d, edi
0x14004eac2  mov     r8, r12
0x14004eac5  mov     rcx, [r10+10h]
0x14004eac9  call    WPP_SF_Dd
0x14004eace  mov     r10, cs:WPP_GLOBAL_Control
0x14004ead5  test    edi, edi
0x14004ead7  jns     short loc_14004EB55
0x14004ead9  mov     eax, 37E0h
0x14004eade  mov     [rbp+57h+var_50.Id], ax
0x14004eae2  movsd   xmm0, cs:qword_1400A73B2
0x14004eaea  mov     eax, cs:dword_1400A73BA
0x14004eaf0  mov     dword ptr [rbp+57h+var_50.Keyword+2], eax
0x14004eaf3  movzx   eax, cs:word_1400A73BE
0x14004eafa  jmp     short loc_14004EB1D
0x14004eafc  mov     eax, 37E1h
0x14004eb01  mov     [rbp+57h+var_50.Id], ax
0x14004eb05  movsd   xmm0, cs:qword_1400A73A2
0x14004eb0d  mov     eax, cs:dword_1400A73AA
0x14004eb13  mov     dword ptr [rbp+57h+var_50.Keyword+2], eax
0x14004eb16  movzx   eax, cs:word_1400A73AE
0x14004eb1d  mov     word ptr [rbp+57h+var_50.Keyword+6], ax
0x14004eb21  movsd   qword ptr [rbp+57h+var_50.Version], xmm0
0x14004eb26  lea     rax, WPP_GLOBAL_Control
0x14004eb2d  cmp     r10, rax
0x14004eb30  jz      short loc_14004EB50
0x14004eb32  test    [r10+1Ch], r15b
0x14004eb36  jz      short loc_14004EB50
0x14004eb38  cmp     byte ptr [r10+19h], 4
0x14004eb3d  jb      short loc_14004EB50
0x14004eb3f  mov     edx, 0A2h
0x14004eb44  mov     r8, r12
0x14004eb47  mov     rcx, [r10+10h]
0x14004eb4b  call    WPP_SF_
0x14004eb50  mov     ebx, 643h
0x14004eb55  lea     rcx, [rbp+57h+pptlib]
0x14004eb59  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004eb5e  test    ebx, ebx
0x14004eb60  jnz     loc_14004E8BC
0x14004eb66  mov     dword ptr [rbp+57h+pptlib], r14d
0x14004eb6a  call    cs:__imp_GetCurrentProcess
0x14004eb70  mov     rcx, rax; hProcess
0x14004eb73  lea     rdx, [rbp+57h+pptlib]; Wow64Process
0x14004eb77  call    cs:__imp_IsWow64Process
0x14004eb7d  cmp     dword ptr [rbp+57h+pptlib], r14d
0x14004eb81  jz      loc_14004ECD6
0x14004eb87  mov     [rbp+57h+hKey], r14
0x14004eb8b  mov     [rbp+57h+var_98], r14
0x14004eb8f  mov     [rbp+57h+var_90], r14
0x14004eb93  mov     [rsp+100h+var_D8], 0F013Fh; unsigned int
0x14004eb9b  lea     r8, SubKey; "SOFTWARE\\Microsoft\\Windows Media Play"...
0x14004eba2  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14004eba9  lea     rcx, [rbp+57h+hKey]; this
0x14004ebad  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x14004ebb2  mov     ebx, eax
0x14004ebb4  mov     r10, cs:WPP_GLOBAL_Control
0x14004ebbb  lea     rax, WPP_GLOBAL_Control
0x14004ebc2  cmp     r10, rax
0x14004ebc5  jz      short loc_14004EBF7
0x14004ebc7  test    [r10+1Ch], r15b
0x14004ebcb  jz      short loc_14004EBF7
0x14004ebcd  movzx   ecx, byte ptr [r10+19h]
0x14004ebd2  mov     eax, r13d
0x14004ebd5  test    ebx, ebx
0x14004ebd7  cmovnz  eax, r15d
0x14004ebdb  cmp     ecx, eax
0x14004ebdd  jb      short loc_14004EBF7
0x14004ebdf  mov     edx, 0A3h
0x14004ebe4  mov     dword ptr [rsp+100h+var_E0], ebx
0x14004ebe8  mov     r9d, ebx
0x14004ebeb  mov     r8, r12
0x14004ebee  mov     rcx, [r10+10h]
0x14004ebf2  call    WPP_SF_Dd
0x14004ebf7  test    ebx, ebx
0x14004ebf9  jnz     loc_14004ECCB
0x14004ebff  mov     [rbp+57h+SecurityDescriptor], r14
0x14004ec03  xor     r9d, r9d; SecurityDescriptorSize
0x14004ec06  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14004ec0a  lea     edx, [rbx+1]; StringSDRevision
0x14004ec0d  lea     rcx, StringSecurityDescriptor; "D:P(A;CI;KA;;;BA)(A;CIIO;KA;;;CO)(A;CI;"...
0x14004ec14  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14004ec1a  mov     r8d, eax
0x14004ec1d  test    eax, eax
0x14004ec1f  mov     eax, 643h
0x14004ec24  cmovz   ebx, eax
0x14004ec27  mov     r10, cs:WPP_GLOBAL_Control
0x14004ec2e  lea     rax, WPP_GLOBAL_Control
0x14004ec35  cmp     r10, rax
0x14004ec38  jz      short loc_14004EC6B
0x14004ec3a  test    [r10+1Ch], r15b
0x14004ec3e  jz      short loc_14004EC6B
0x14004ec40  movzx   ecx, byte ptr [r10+19h]
0x14004ec45  mov     eax, r13d
0x14004ec48  test    ebx, ebx
0x14004ec4a  cmovnz  eax, r15d
0x14004ec4e  cmp     ecx, eax
0x14004ec50  jb      short loc_14004EC6B
0x14004ec52  mov     edx, 0A4h
0x14004ec57  mov     dword ptr [rsp+100h+var_E0], r8d
0x14004ec5c  mov     r9d, ebx
0x14004ec5f  mov     r8, r12
0x14004ec62  mov     rcx, [r10+10h]
  ... truncated ...
```
