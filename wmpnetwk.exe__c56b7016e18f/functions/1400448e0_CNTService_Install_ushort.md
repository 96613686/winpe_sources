# CNTService::Install(ushort *)

- ea: `0x1400448e0`
- end: `0x140044f6e`
- name: `?Install@CNTService@@UEAAKPEAG@Z`
- size: `1678`
- prototype: `__int64 __fastcall(CNTService *this, LPCWSTR lpDependencies)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x14004e7c0`

## callees

- `0x140006d70`
- `0x140007020`
- `0x140008eac`
- `0x14000b3b0`
- `0x14000c780`
- `0x14000c920`
- `0x1400105a0`
- `0x140018df0`
- `0x140032eec`
- `0x14003e5f4`
- `0x14003f17c`
- `0x1400448e0`
- `0x140045f20`
- `0x1400476ac`
- `0x140047798`
- `0x140048760`
- `0x1400488f4`
- `0x14004a79c`
- `0x140093330`
- `0x14009ad04`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x1400449ed`
- `ADVAPI32!OpenSCManagerW` at `0x1400449ed`
- `ADVAPI32!CloseServiceHandle` at `0x140044b1e`
- `ADVAPI32!CloseServiceHandle` at `0x140044e23`
- `ADVAPI32!CloseServiceHandle` at `0x140044e2c`
- `ADVAPI32!CloseServiceHandle` at `0x140044b1e`
- `ADVAPI32!CloseServiceHandle` at `0x140044e23`
- `ADVAPI32!CloseServiceHandle` at `0x140044e2c`
- `ADVAPI32!CreateServiceW` at `0x140044abc`
- `ADVAPI32!CreateServiceW` at `0x140044abc`
- `ADVAPI32!ChangeServiceConfig2W` at `0x140044c25`
- `ADVAPI32!ChangeServiceConfig2W` at `0x140044ce8`
- `ADVAPI32!ChangeServiceConfig2W` at `0x140044dd2`
- `ADVAPI32!ChangeServiceConfig2W` at `0x140044c25`
- `ADVAPI32!ChangeServiceConfig2W` at `0x140044ce8`
- `ADVAPI32!ChangeServiceConfig2W` at `0x140044dd2`
- `KERNEL32!GetLastError` at `0x1400449fb`
- `KERNEL32!GetLastError` at `0x140044ace`
- `KERNEL32!GetLastError` at `0x140044c4e`
- `KERNEL32!GetLastError` at `0x140044d11`
- `KERNEL32!GetLastError` at `0x140044dfb`
- `KERNEL32!GetLastError` at `0x1400449fb`
- `KERNEL32!GetLastError` at `0x140044ace`
- `KERNEL32!GetLastError` at `0x140044c4e`
- `KERNEL32!GetLastError` at `0x140044d11`
- `KERNEL32!GetLastError` at `0x140044dfb`

## string_xrefs

- `0x14004496a`: `SYSTEM\CurrentControlSet\Services\`
- `0x1400449a3`: `UNKNOWN_SERVICE`
- `0x140044a74`: `NT AUTHORITY\NetworkService`

## pseudocode

```c
__int64 __fastcall CNTService::Install(CNTService *this, LPCWSTR lpDependencies)
{
  LPCWSTR *v4; // rsi
  SC_HANDLE v5; // r14
  DWORD LastError; // eax
  DWORD v7; // ebx
  SC_HANDLE ServiceW; // rdi
  PVOID *v9; // rcx
  DWORD v10; // eax
  DWORD v11; // eax
  PVOID *v12; // rcx
  DWORD v13; // eax
  __int128 v14; // xmm0
  PVOID *v15; // r10
  __int64 v16; // rdx
  const unsigned __int16 *Info; // [rsp+70h] [rbp-69h] BYREF
  const unsigned __int16 *v19; // [rsp+78h] [rbp-61h] BYREF
  LPCWSTR lpDisplayName; // [rsp+80h] [rbp-59h] BYREF
  LPCWSTR lpSubKey; // [rsp+88h] [rbp-51h] BYREF
  _QWORD v22[3]; // [rsp+90h] [rbp-49h] BYREF
  __int64 v23; // [rsp+A8h] [rbp-31h] BYREF
  __int128 v24; // [rsp+B0h] [rbp-29h]
  __int64 v25; // [rsp+C0h] [rbp-19h]
  _DWORD *v26; // [rsp+C8h] [rbp-11h]
  __int128 Buf2; // [rsp+D0h] [rbp-9h] BYREF
  _DWORD v28[3]; // [rsp+E0h] [rbp+7h] BYREF
  __int64 v29; // [rsp+ECh] [rbp+13h]
  int v30; // [rsp+F4h] [rbp+1Bh]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, lpDependencies);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&lpDisplayName);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v19);
  memset(v22, 0, sizeof(v22));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &lpSubKey,
    L"SYSTEM\\CurrentControlSet\\Services\\");
  v4 = (LPCWSTR *)((char *)this + 40);
  ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, (char *)this + 40);
  Buf2 = 0;
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::LoadStringW(
                        &lpDisplayName,
                        *((unsigned int *)this + 12)) )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&lpDisplayName, L"UNKNOWN_SERVICE");
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::LoadStringW(
                        &v19,
                        *((unsigned int *)this + 13)) )
    ATL::CSimpleStringT<unsigned short,0>::Empty(&v19);
  if ( (unsigned int)CNTService::IsInstalled(this) )
  {
    v7 = 0;
    v14 = WMC_I_SERVICE_INSTALL_SKIPPED;
    goto LABEL_68;
  }
  v5 = OpenSCManagerW(0, 0, 0xF003Fu);
  if ( !v5 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, LastError);
    }
    if ( v7 == 5 )
    {
      Buf2 = WMC_E_SERVICE_INSTALL_FAILED_OPENSCMANAGER_ACCESSDENIED;
      goto LABEL_25;
    }
    Buf2 = WMC_E_SERVICE_INSTALL_FAILED_OPENSCMANAGER_UNKNOWN;
    goto LABEL_24;
  }
  ServiceW = CreateServiceW(
               v5,
               *v4,
               lpDisplayName,
               0xF01FFu,
               0x10u,
               3u,
               1u,
               g_strModuleFileName,
               0,
               0,
               lpDependencies,
               L"NT AUTHORITY\\NetworkService",
               &Password);
  if ( !ServiceW )
  {
    v7 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        (unsigned int)&WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids,
        (unsigned int)*v4,
        v7);
    }
    Buf2 = WMC_E_SERVICE_INSTALL_FAILED_CREATESERVICE;
    CloseServiceHandle(v5);
    goto LABEL_24;
  }
  v7 = ATL::CRegKey::Open((ATL::CRegKey *)v22, HKEY_LOCAL_MACHINE, lpSubKey, 0xF003Fu);
  Buf2 = WMC_E_SERVICE_INSTALL_FAILED_OPENSERVICEKEY;
  if ( !*((_DWORD *)v19 - 4) )
    goto LABEL_40;
  Info = v19;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
  }
  if ( ChangeServiceConfig2W(ServiceW, 1u, &Info) )
    goto LABEL_40;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v10 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, v10);
LABEL_40:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v28[0] = 1;
  v28[1] = 30000;
  v28[2] = 1;
  v29 = 30000;
  v30 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 3;
  v26 = v28;
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 && *((_BYTE *)v9 + 25) >= 4u )
    WPP_SF_(v9[2], 33, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
  if ( !ChangeServiceConfig2W(ServiceW, 2u, &v23)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v11 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, v11);
  }
  if ( (unsigned int)SetHandleACLs((HKEY)ServiceW, L"S-1-5-4", 2, 0x2019Du, 0) )
    goto LABEL_55;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
LABEL_55:
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  LODWORD(Info) = 1;
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 && *((_BYTE *)v12 + 25) >= 4u )
    WPP_SF_(v12[2], 36, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
  if ( !ChangeServiceConfig2W(ServiceW, 5u, &Info)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v13 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, v13);
  }
  CloseServiceHandle(ServiceW);
  CloseServiceHandle(v5);
  if ( !v7 )
  {
    v14 = WMC_I_SERVICE_INSTALLED;
LABEL_68:
    Buf2 = v14;
    goto LABEL_69;
  }
LABEL_24:
  if ( v7 )
  {
LABEL_25:
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&Info);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
      &Info,
      L"%lu",
      v7);
    CNTService::LogEvent(this, (const struct _EVENT_DESCRIPTOR *)&Buf2, *v4, Info, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        (unsigned int)&WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids,
        (unsigned int)*v4,
        v7);
    }
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&Info);
    goto LABEL_79;
  }
LABEL_69:
  CNTService::LogEvent(this, (const struct _EVENT_DESCRIPTOR *)&Buf2, *v4, 0, 0);
  if ( memcmp_0(&WMC_I_SERVICE_INSTALL_SKIPPED, &Buf2, 0x10u) )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_84;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      goto LABEL_80;
    v16 = 39;
    goto LABEL_78;
  }
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_84;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v16 = 38;
LABEL_78:
    WPP_SF_S(v15[2], v16, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, *v4);
LABEL_79:
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_80:
  if ( v15 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v15 + 28) & 1) != 0
    && *((unsigned __int8 *)v15 + 25) >= (unsigned int)(v7 != 0 ? 2 : 5) )
  {
    WPP_SF_d(v15[2], 41, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, v7);
  }
LABEL_84:
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpSubKey);
  ATL::CRegKey::Close((ATL::CRegKey *)v22);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v19);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpDisplayName);
  return v7;
}

```

## disassembly

```asm
0x1400448e0  mov     [rsp-8+arg_10], rbx
0x1400448e5  push    rbp
0x1400448e6  push    rsi
0x1400448e7  push    rdi
0x1400448e8  push    r12
0x1400448ea  push    r13
0x1400448ec  push    r14
0x1400448ee  push    r15
0x1400448f0  lea     rbp, [rsp-27h]
0x1400448f5  sub     rsp, 100h
0x1400448fc  mov     rax, cs:__security_cookie
0x140044903  xor     rax, rsp
0x140044906  mov     [rbp+57h+var_38], rax
0x14004490a  mov     rbx, rdx
0x14004490d  mov     r15, rcx
0x140044910  lea     r14, WPP_GLOBAL_Control
0x140044917  mov     rcx, cs:WPP_GLOBAL_Control
0x14004491e  cmp     rcx, r14
0x140044921  jz      short loc_140044947
0x140044923  test    byte ptr [rcx+1Ch], 1
0x140044927  jz      short loc_140044947
0x140044929  cmp     byte ptr [rcx+19h], 5
0x14004492d  jb      short loc_140044947
0x14004492f  mov     edx, 1Ch
0x140044934  mov     r9, rbx
0x140044937  lea     r8, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x14004493e  mov     rcx, [rcx+10h]
0x140044942  call    WPP_SF_S
0x140044947  lea     rcx, [rbp+57h+lpDisplayName]
0x14004494b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140044950  nop
0x140044951  lea     rcx, [rbp+57h+var_B8]
0x140044955  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14004495a  nop
0x14004495b  xor     r13d, r13d
0x14004495e  mov     [rbp+57h+var_A0], r13
0x140044962  mov     [rbp+57h+var_98], r13
0x140044966  mov     [rbp+57h+var_90], r13
0x14004496a  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\"
0x140044971  lea     rcx, [rbp+57h+lpSubKey]
0x140044975  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14004497a  nop
0x14004497b  lea     rsi, [r15+28h]
0x14004497f  mov     rdx, rsi
0x140044982  lea     rcx, [rbp+57h+lpSubKey]
0x140044986  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<ushort,0>::Append(ATL::CSimpleStringT<ushort,0> const &)
0x14004498b  xorps   xmm0, xmm0
0x14004498e  movups  [rbp+57h+Buf2], xmm0
0x140044992  mov     edx, [r15+30h]
0x140044996  lea     rcx, [rbp+57h+lpDisplayName]
0x14004499a  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::LoadStringW(uint)
0x14004499f  test    eax, eax
0x1400449a1  jnz     short loc_1400449B3
0x1400449a3  lea     rdx, aUnknownService; "UNKNOWN_SERVICE"
0x1400449aa  lea     rcx, [rbp+57h+lpDisplayName]
0x1400449ae  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1400449b3  mov     edx, [r15+34h]
0x1400449b7  lea     rcx, [rbp+57h+var_B8]
0x1400449bb  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::LoadStringW(uint)
0x1400449c0  test    eax, eax
0x1400449c2  jnz     short loc_1400449CD
0x1400449c4  lea     rcx, [rbp+57h+var_B8]
0x1400449c8  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1400449cd  mov     rcx, r15; this
0x1400449d0  call    ?IsInstalled@CNTService@@QEAAHXZ; CNTService::IsInstalled(void)
0x1400449d5  mov     r12d, 2
0x1400449db  test    eax, eax
0x1400449dd  jnz     loc_140044E4A
0x1400449e3  xor     edx, edx; lpDatabaseName
0x1400449e5  xor     ecx, ecx; lpMachineName
0x1400449e7  mov     r8d, 0F003Fh; dwDesiredAccess
0x1400449ed  call    cs:__imp_OpenSCManagerW
0x1400449f3  mov     r14, rax
0x1400449f6  test    rax, rax
0x1400449f9  jnz     short loc_140044A61
0x1400449fb  call    cs:__imp_GetLastError
0x140044a01  mov     ebx, eax
0x140044a03  mov     rcx, cs:WPP_GLOBAL_Control
0x140044a0a  lea     r14, WPP_GLOBAL_Control
0x140044a11  cmp     rcx, r14
0x140044a14  jz      short loc_140044A3A
0x140044a16  test    [rcx+1Ch], r12b
0x140044a1a  jz      short loc_140044A3A
0x140044a1c  cmp     [rcx+19h], r12b
0x140044a20  jb      short loc_140044A3A
0x140044a22  lea     edx, [r12+1Bh]
0x140044a27  mov     r9d, eax
0x140044a2a  lea     r8, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x140044a31  mov     rcx, [rcx+10h]
0x140044a35  call    WPP_SF_d
0x140044a3a  cmp     ebx, 5
0x140044a3d  jnz     short loc_140044A50
0x140044a3f  movups  xmm0, cs:WMC_E_SERVICE_INSTALL_FAILED_OPENSCMANAGER_ACCESSDENIED
0x140044a46  movdqu  [rbp+57h+Buf2], xmm0
0x140044a4b  jmp     loc_140044B33
0x140044a50  movups  xmm0, cs:WMC_E_SERVICE_INSTALL_FAILED_OPENSCMANAGER_UNKNOWN
0x140044a57  movdqu  [rbp+57h+Buf2], xmm0
0x140044a5c  jmp     loc_140044B2B
0x140044a61  mov     rax, cs:?g_strModuleFileName@@3V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@A; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> g_strModuleFileName
0x140044a68  lea     rcx, Password
0x140044a6f  mov     [rsp+130h+lpPassword], rcx; lpPassword
0x140044a74  lea     rcx, ServiceStartName; "NT AUTHORITY\\NetworkService"
0x140044a7b  mov     [rsp+130h+lpServiceStartName], rcx; lpServiceStartName
0x140044a80  mov     [rsp+130h+lpDependencies], rbx; lpDependencies
0x140044a85  mov     [rsp+130h+lpdwTagId], r13; lpdwTagId
0x140044a8a  mov     [rsp+130h+lpLoadOrderGroup], r13; lpLoadOrderGroup
0x140044a8f  mov     [rsp+130h+lpBinaryPathName], rax; lpBinaryPathName
0x140044a94  mov     [rsp+130h+dwErrorControl], 1; dwErrorControl
0x140044a9c  mov     [rsp+130h+dwStartType], 3; dwStartType
0x140044aa4  mov     [rsp+130h+dwServiceType], 10h; dwServiceType
0x140044aac  mov     r9d, 0F01FFh; dwDesiredAccess
0x140044ab2  mov     r8, [rbp+57h+lpDisplayName]; lpDisplayName
0x140044ab6  mov     rdx, [rsi]; lpServiceName
0x140044ab9  mov     rcx, r14; hSCManager
0x140044abc  call    cs:__imp_CreateServiceW
0x140044ac2  mov     rdi, rax
0x140044ac5  test    rax, rax
0x140044ac8  jnz     loc_140044BAB
0x140044ace  call    cs:__imp_GetLastError
0x140044ad4  mov     ebx, eax
0x140044ad6  mov     rcx, cs:WPP_GLOBAL_Control
0x140044add  lea     rax, WPP_GLOBAL_Control
0x140044ae4  cmp     rcx, rax
0x140044ae7  jz      short loc_140044B0F
0x140044ae9  test    [rcx+1Ch], r12b
0x140044aed  jz      short loc_140044B0F
0x140044aef  cmp     [rcx+19h], r12b
0x140044af3  jb      short loc_140044B0F
0x140044af5  lea     edx, [rdi+1Eh]
0x140044af8  mov     [rsp+130h+dwServiceType], ebx
0x140044afc  mov     r9, [rsi]
0x140044aff  lea     r8, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x140044b06  mov     rcx, [rcx+10h]
0x140044b0a  call    WPP_SF_Sd
0x140044b0f  movups  xmm0, cs:WMC_E_SERVICE_INSTALL_FAILED_CREATESERVICE
0x140044b16  movdqu  [rbp+57h+Buf2], xmm0
0x140044b1b  mov     rcx, r14; hSCObject
0x140044b1e  call    cs:__imp_CloseServiceHandle
0x140044b24  lea     r14, WPP_GLOBAL_Control
0x140044b2b  test    ebx, ebx
0x140044b2d  jz      loc_140044E59
0x140044b33  lea     rcx, [rbp+57h+Info]
0x140044b37  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140044b3c  nop
0x140044b3d  mov     r8d, ebx
0x140044b40  lea     rdx, aLu; "%lu"
0x140044b47  lea     rcx, [rbp+57h+Info]
0x140044b4b  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Format(ushort const *,...)
0x140044b50  mov     qword ptr [rsp+130h+dwServiceType], r13; unsigned __int16 *
0x140044b55  mov     r9, [rbp+57h+Info]; unsigned __int16 *
0x140044b59  mov     r8, [rsi]; unsigned __int16 *
0x140044b5c  lea     rdx, [rbp+57h+Buf2]; struct _EVENT_DESCRIPTOR *
0x140044b60  mov     rcx, r15; this
0x140044b63  call    ?LogEvent@CNTService@@QEAAXAEBU_EVENT_DESCRIPTOR@@PEBG11@Z; CNTService::LogEvent(_EVENT_DESCRIPTOR const &,ushort const *,ushort const *,ushort const *)
0x140044b68  mov     rcx, cs:WPP_GLOBAL_Control
0x140044b6f  cmp     rcx, r14
0x140044b72  jz      short loc_140044B9D
0x140044b74  test    [rcx+1Ch], r12b
0x140044b78  jz      short loc_140044B9D
0x140044b7a  cmp     [rcx+19h], r12b
0x140044b7e  jb      short loc_140044B9D
0x140044b80  mov     edx, 28h ; '('
0x140044b85  mov     [rsp+130h+dwServiceType], ebx
0x140044b89  mov     r9, [rsi]
0x140044b8c  lea     r8, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x140044b93  mov     rcx, [rcx+10h]
0x140044b97  call    WPP_SF_Sd
0x140044b9c  nop
0x140044b9d  lea     rcx, [rbp+57h+Info]
0x140044ba1  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140044ba6  jmp     loc_140044EDD
0x140044bab  mov     r9d, 0F003Fh; unsigned int
0x140044bb1  mov     r8, [rbp+57h+lpSubKey]; lpSubKey
0x140044bb5  mov     rdx, 0FFFFFFFF80000002h; hKey
0x140044bbc  lea     rcx, [rbp+57h+var_A0]; this
0x140044bc0  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140044bc5  mov     ebx, eax
0x140044bc7  movups  xmm0, cs:WMC_E_SERVICE_INSTALL_FAILED_OPENSERVICEKEY
0x140044bce  movdqu  [rbp+57h+Buf2], xmm0
0x140044bd3  mov     rax, [rbp+57h+var_B8]
0x140044bd7  cmp     [rax-10h], r13d
0x140044bdb  jz      loc_140044C73
0x140044be1  mov     [rbp+57h+Info], rax
0x140044be5  mov     rcx, cs:WPP_GLOBAL_Control
0x140044bec  lea     rax, WPP_GLOBAL_Control
0x140044bf3  cmp     rcx, rax
0x140044bf6  jz      short loc_140044C19
0x140044bf8  test    [rcx+1Ch], r12b
0x140044bfc  jz      short loc_140044C19
0x140044bfe  cmp     byte ptr [rcx+19h], 4
0x140044c02  jb      short loc_140044C19
0x140044c04  mov     edx, 1Fh
0x140044c09  lea     r8, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x140044c10  mov     rcx, [rcx+10h]
0x140044c14  call    WPP_SF_
0x140044c19  lea     r8, [rbp+57h+Info]; lpInfo
0x140044c1d  mov     edx, 1; dwInfoLevel
0x140044c22  mov     rcx, rdi; hService
0x140044c25  call    cs:__imp_ChangeServiceConfig2W
0x140044c2b  test    eax, eax
0x140044c2d  jnz     short loc_140044C73
0x140044c2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140044c36  lea     rax, WPP_GLOBAL_Control
0x140044c3d  cmp     rcx, rax
0x140044c40  jz      short loc_140044C7A
0x140044c42  test    [rcx+1Ch], r12b
0x140044c46  jz      short loc_140044C7A
0x140044c48  cmp     byte ptr [rcx+19h], 3
0x140044c4c  jb      short loc_140044C7A
0x140044c4e  call    cs:__imp_GetLastError
0x140044c54  mov     edx, 20h ; ' '
0x140044c59  mov     r9d, eax
0x140044c5c  lea     r8, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x140044c63  mov     rcx, cs:WPP_GLOBAL_Control
0x140044c6a  mov     rcx, [rcx+10h]
0x140044c6e  call    WPP_SF_d
0x140044c73  mov     rcx, cs:WPP_GLOBAL_Control
0x140044c7a  mov     edx, 1
0x140044c7f  mov     [rbp+57h+var_50], edx
0x140044c82  mov     eax, 7530h
0x140044c87  mov     [rbp+57h+var_4C], eax
0x140044c8a  mov     [rbp+57h+var_48], edx
0x140044c8d  mov     [rbp+57h+var_44], rax
0x140044c91  mov     [rbp+57h+var_3C], r13d
0x140044c95  mov     [rbp+57h+var_88], r13
0x140044c99  xorps   xmm0, xmm0
0x140044c9c  movdqu  [rbp+57h+var_80], xmm0
0x140044ca1  mov     [rbp+57h+var_70], 3
0x140044ca9  lea     rax, [rbp+57h+var_50]
0x140044cad  mov     [rbp+57h+var_68], rax
0x140044cb1  lea     rax, WPP_GLOBAL_Control
0x140044cb8  cmp     rcx, rax
0x140044cbb  jz      short loc_140044CDE
0x140044cbd  test    [rcx+1Ch], r12b
0x140044cc1  jz      short loc_140044CDE
0x140044cc3  cmp     byte ptr [rcx+19h], 4
0x140044cc7  jb      short loc_140044CDE
0x140044cc9  mov     edx, 21h ; '!'
0x140044cce  lea     r8, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x140044cd5  mov     rcx, [rcx+10h]
0x140044cd9  call    WPP_SF_
0x140044cde  lea     r8, [rbp+57h+var_88]; lpInfo
0x140044ce2  mov     edx, r12d; dwInfoLevel
0x140044ce5  mov     rcx, rdi; hService
0x140044ce8  call    cs:__imp_ChangeServiceConfig2W
0x140044cee  test    eax, eax
0x140044cf0  jnz     short loc_140044D36
0x140044cf2  mov     rax, cs:WPP_GLOBAL_Control
0x140044cf9  lea     rcx, WPP_GLOBAL_Control
0x140044d00  cmp     rax, rcx
0x140044d03  jz      short loc_140044D36
0x140044d05  test    [rax+1Ch], r12b
0x140044d09  jz      short loc_140044D36
0x140044d0b  cmp     byte ptr [rax+19h], 3
0x140044d0f  jb      short loc_140044D36
0x140044d11  call    cs:__imp_GetLastError
0x140044d17  mov     edx, 22h ; '"'
0x140044d1c  mov     r9d, eax
0x140044d1f  lea     r8, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x140044d26  mov     rcx, cs:WPP_GLOBAL_Control
0x140044d2d  mov     rcx, [rcx+10h]
0x140044d31  call    WPP_SF_d
0x140044d36  mov     byte ptr [rsp+130h+dwServiceType], r13b; unsigned __int8
0x140044d3b  mov     r9d, 2019Dh; unsigned int
0x140044d41  mov     r8d, r12d; enum _SE_OBJECT_TYPE
0x140044d44  lea     rdx, aS154; "S-1-5-4"
0x140044d4b  mov     rcx, rdi; void *
0x140044d4e  call    ?SetHandleACLs@@YAHPEAXPEBGW4_SE_OBJECT_TYPE@@KE@Z; SetHandleACLs(void *,ushort const *,_SE_OBJECT_TYPE,ulong,uchar)
0x140044d53  test    eax, eax
0x140044d55  jnz     short loc_140044D8B
0x140044d57  mov     rcx, cs:WPP_GLOBAL_Control
0x140044d5e  lea     rax, WPP_GLOBAL_Control
0x140044d65  cmp     rcx, rax
0x140044d68  jz      short loc_140044D99
0x140044d6a  test    [rcx+1Ch], r12b
0x140044d6e  jz      short loc_140044D99
0x140044d70  cmp     byte ptr [rcx+19h], 3
0x140044d74  jb      short loc_140044D99
0x140044d76  mov     edx, 23h ; '#'
0x140044d7b  lea     r8, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x140044d82  mov     rcx, [rcx+10h]
0x140044d86  call    WPP_SF_
0x140044d8b  lea     rax, WPP_GLOBAL_Control
0x140044d92  mov     rcx, cs:WPP_GLOBAL_Control
0x140044d99  mov     dword ptr [rbp+57h+Info], 1
0x140044da0  cmp     rcx, rax
0x140044da3  jz      short loc_140044DC6
0x140044da5  test    [rcx+1Ch], r12b
0x140044da9  jz      short loc_140044DC6
0x140044dab  cmp     byte ptr [rcx+19h], 4
0x140044daf  jb      short loc_140044DC6
0x140044db1  mov     edx, 24h ; '$'
0x140044db6  lea     r8, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x140044dbd  mov     rcx, [rcx+10h]
0x140044dc1  call    WPP_SF_
0x140044dc6  lea     r8, [rbp+57h+Info]; lpInfo
0x140044dca  mov     edx, 5; dwInfoLevel
0x140044dcf  mov     rcx, rdi; hService
0x140044dd2  call    cs:__imp_ChangeServiceConfig2W
0x140044dd8  test    eax, eax
  ... truncated ...
```
