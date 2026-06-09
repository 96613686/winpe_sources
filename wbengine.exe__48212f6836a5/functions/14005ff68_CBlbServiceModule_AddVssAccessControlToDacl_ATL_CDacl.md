# CBlbServiceModule::AddVssAccessControlToDacl(ATL::CDacl *)

- ea: `0x14005ff68`
- end: `0x1400603e5`
- name: `?AddVssAccessControlToDacl@CBlbServiceModule@@AEAAJPEAVCDacl@ATL@@@Z`
- size: `1149`
- prototype: `__int64 __fastcall(CBlbServiceModule *this, struct ATL::CDacl *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x140062ce8`

## callees

- `0x14000bb24`
- `0x14000bb4c`
- `0x140014260`
- `0x14003c434`
- `0x14003c54c`
- `0x14005eae8`
- `0x14005f490`
- `0x14005fd94`
- `0x14005ff68`
- `0x140063608`
- `0x140134d20`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14005ffb8`
- `ADVAPI32!RegOpenKeyExW` at `0x14005ffb8`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140060068`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140060068`
- `ADVAPI32!RegCloseKey` at `0x1400603c0`
- `ADVAPI32!RegCloseKey` at `0x1400603c0`
- `ADVAPI32!RegEnumValueW` at `0x1400601cb`
- `ADVAPI32!RegEnumValueW` at `0x1400601cb`
- `KERNEL32!GetLastError` at `0x1400602b7`
- `KERNEL32!GetLastError` at `0x1400602b7`
- `ole32!CoTaskMemAlloc` at `0x140060175`
- `ole32!CoTaskMemAlloc` at `0x140060175`
- `ole32!CoTaskMemFree` at `0x140060166`
- `ole32!CoTaskMemFree` at `0x1400603b5`
- `ole32!CoTaskMemFree` at `0x140060166`
- `ole32!CoTaskMemFree` at `0x1400603b5`

## string_xrefs

- `0x14005ffaa`: `SYSTEM\CurrentControlSet\Services\VSS\VssAccessControl`

## pseudocode

```c
__int64 __fastcall CBlbServiceModule::AddVssAccessControlToDacl(CBlbServiceModule *this, struct ATL::CDacl *a2)
{
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  void *v6; // r14
  DWORD i; // ebx
  const unsigned __int16 *v8; // r8
  _QWORD *v9; // rcx
  DWORD v10; // edx
  char LastError; // al
  DWORD cValues; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchValueName; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD Type; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[4]; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbMaxValueLen[4]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v21[9]; // [rsp+90h] [rbp-70h] BYREF
  char v22; // [rsp+DCh] [rbp-24h]
  int v23; // [rsp+E0h] [rbp-20h]
  _BYTE v24[8]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v25[8]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v26[8]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v27[16]; // [rsp+100h] [rbp+0h] BYREF

  hKey = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\VSS\\VssAccessControl",
         0,
         0x20019u,
         &hKey);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids);
    }
    return v4;
  }
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen[0] = 0;
  v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, cbMaxValueLen, 0, 0);
  v4 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids);
    }
    goto LABEL_59;
  }
  v6 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids);
  }
  for ( i = 0; i < cValues; ++i )
  {
    v21[0] = &ATL::CSid::`vftable';
    v22 = 0;
    v23 = 7;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v24);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v25);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v26);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v27);
    cchValueName = 0;
    Type = 0;
    *(_DWORD *)Data = 0;
    cbData = 0;
    if ( v6 )
      CoTaskMemFree(v6);
    v6 = CoTaskMemAlloc(2LL * (cbMaxValueNameLen + 1));
    if ( !v6 )
    {
      v4 = -2147024882;
      ATL::CSid::~CSid((ATL::CSid *)v21);
      goto LABEL_59;
    }
    cchValueName = cbMaxValueNameLen + 1;
    cbData = 4;
    if ( RegEnumValueW(hKey, i, (LPWSTR)v6, &cchValueName, 0, &Type, Data, &cbData) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids);
      }
    }
    else if ( Type == 4 && cbData == 4 )
    {
      if ( *(_DWORD *)Data == 1 )
      {
        if ( ATL::CSid::LoadAccount((ATL::CSid *)v21, (LPCWSTR)v6, v8) )
        {
          if ( ATL::CDacl::AddAllowedAce(a2, (const struct ATL::CSid *)v21, 1u, 0) )
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              v10 = 31;
              goto LABEL_36;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids);
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            (unsigned int)WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids,
            (_DWORD)v6,
            LastError);
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= (unsigned __int8)Type )
        {
          v10 = Type + 24;
LABEL_36:
          WPP_SF_dS(v9[2], v10, (unsigned int)WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids, i, (__int64)v6);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids);
    }
    ATL::CSid::~CSid((ATL::CSid *)v21);
  }
  v4 = 0;
  if ( v6 )
    CoTaskMemFree(v6);
LABEL_59:
  RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x14005ff68  push    rbp
0x14005ff6a  push    rbx
0x14005ff6b  push    rdi
0x14005ff6c  push    r12
0x14005ff6e  push    r14
0x14005ff70  push    r15
0x14005ff72  lea     rbp, [rsp-28h]
0x14005ff77  sub     rsp, 128h
0x14005ff7e  mov     rax, cs:__security_cookie
0x14005ff85  xor     rax, rsp
0x14005ff88  mov     [rbp+50h+var_40], rax
0x14005ff8c  mov     r15, rdx
0x14005ff8f  xor     r12d, r12d
0x14005ff92  mov     [rsp+150h+hKey], r12
0x14005ff97  lea     rax, [rsp+150h+hKey]
0x14005ff9c  mov     [rsp+150h+phkResult], rax; phkResult
0x14005ffa1  mov     r9d, 20019h; samDesired
0x14005ffa7  xor     r8d, r8d; ulOptions
0x14005ffaa  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\VS"...
0x14005ffb1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005ffb8  call    cs:__imp_RegOpenKeyExW
0x14005ffbe  mov     ebx, eax
0x14005ffc0  test    eax, eax
0x14005ffc2  jz      short loc_140060017
0x14005ffc4  jle     short loc_14005FFCF
0x14005ffc6  movzx   ebx, ax
0x14005ffc9  or      ebx, 80070000h
0x14005ffcf  lea     rdi, WPP_GLOBAL_Control
0x14005ffd6  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ffdd  cmp     rcx, rdi
0x14005ffe0  jz      loc_1400603C6
0x14005ffe6  test    byte ptr [rcx+1Ch], 1
0x14005ffea  jz      loc_1400603C6
0x14005fff0  cmp     byte ptr [rcx+19h], 3
0x14005fff4  jb      loc_1400603C6
0x14005fffa  mov     edx, 17h
0x14005ffff  mov     r9d, ebx
0x140060002  lea     r8, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids
0x140060009  mov     rcx, [rcx+10h]
0x14006000d  call    WPP_SF_d
0x140060012  jmp     loc_1400603C6
0x140060017  mov     [rsp+150h+cValues], r12d
0x14006001c  mov     [rsp+150h+cbMaxValueNameLen], r12d
0x140060021  mov     [rbp+50h+cbMaxValueLen], r12d
0x140060025  mov     [rsp+150h+lpftLastWriteTime], r12; lpftLastWriteTime
0x14006002a  mov     [rsp+150h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x14006002f  lea     rax, [rbp+50h+cbMaxValueLen]
0x140060033  mov     [rsp+150h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x140060038  lea     rax, [rsp+150h+cbMaxValueNameLen]
0x14006003d  mov     [rsp+150h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x140060042  lea     rax, [rsp+150h+cValues]
0x140060047  mov     [rsp+150h+lpcValues], rax; lpcValues
0x14006004c  mov     [rsp+150h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x140060051  mov     [rsp+150h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x140060056  mov     [rsp+150h+phkResult], r12; lpcSubKeys
0x14006005b  xor     r9d, r9d; lpReserved
0x14006005e  xor     r8d, r8d; lpcchClass
0x140060061  xor     edx, edx; lpClass
0x140060063  mov     rcx, [rsp+150h+hKey]; hKey
0x140060068  call    cs:__imp_RegQueryInfoKeyW
0x14006006e  mov     ebx, eax
0x140060070  test    eax, eax
0x140060072  jz      short loc_1400600C7
0x140060074  jle     short loc_14006007F
0x140060076  movzx   ebx, ax
0x140060079  or      ebx, 80070000h
0x14006007f  lea     rdi, WPP_GLOBAL_Control
0x140060086  mov     rcx, cs:WPP_GLOBAL_Control
0x14006008d  cmp     rcx, rdi
0x140060090  jz      loc_1400603BB
0x140060096  test    byte ptr [rcx+1Ch], 1
0x14006009a  jz      loc_1400603BB
0x1400600a0  cmp     byte ptr [rcx+19h], 3
0x1400600a4  jb      loc_1400603BB
0x1400600aa  mov     edx, 18h
0x1400600af  mov     r9d, ebx
0x1400600b2  lea     r8, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids
0x1400600b9  mov     rcx, [rcx+10h]
0x1400600bd  call    WPP_SF_d
0x1400600c2  jmp     loc_1400603BB
0x1400600c7  mov     r14, r12
0x1400600ca  lea     rdi, WPP_GLOBAL_Control
0x1400600d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400600d8  cmp     rcx, rdi
0x1400600db  jz      short loc_140060103
0x1400600dd  test    byte ptr [rcx+1Ch], 1
0x1400600e1  jz      short loc_140060103
0x1400600e3  cmp     byte ptr [rcx+19h], 4
0x1400600e7  jb      short loc_140060103
0x1400600e9  mov     edx, 19h
0x1400600ee  mov     r9d, [rsp+150h+cValues]
0x1400600f3  lea     r8, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids
0x1400600fa  mov     rcx, [rcx+10h]
0x1400600fe  call    WPP_SF_d
0x140060103  mov     ebx, r12d
0x140060106  cmp     ebx, [rsp+150h+cValues]
0x14006010a  jnb     loc_1400603AA
0x140060110  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x140060117  mov     [rbp+50h+var_C0], rax
0x14006011b  mov     [rbp+50h+var_74], r12b
0x14006011f  mov     [rbp+50h+var_70], 7
0x140060126  lea     rcx, [rbp+50h+var_68]
0x14006012a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x14006012f  lea     rcx, [rbp+50h+var_60]
0x140060133  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x140060138  lea     rcx, [rbp+50h+var_58]
0x14006013c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x140060141  lea     rcx, [rbp+50h+var_50]
0x140060145  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x14006014a  mov     [rsp+150h+cchValueName], r12d
0x14006014f  mov     [rsp+150h+Type], r12d
0x140060154  mov     dword ptr [rsp+150h+Data], r12d
0x140060159  mov     [rsp+150h+cbData], r12d
0x14006015e  test    r14, r14
0x140060161  jz      short loc_14006016C
0x140060163  mov     rcx, r14; pv
0x140060166  call    cs:__imp_CoTaskMemFree
0x14006016c  mov     ecx, [rsp+150h+cbMaxValueNameLen]
0x140060170  inc     ecx
0x140060172  add     rcx, rcx; cb
0x140060175  call    cs:__imp_CoTaskMemAlloc
0x14006017b  mov     r14, rax
0x14006017e  test    rax, rax
0x140060181  jz      loc_14006039A
0x140060187  mov     eax, [rsp+150h+cbMaxValueNameLen]
0x14006018b  inc     eax
0x14006018d  mov     [rsp+150h+cchValueName], eax
0x140060191  mov     [rsp+150h+cbData], 4
0x140060199  lea     rax, [rsp+150h+cbData]
0x14006019e  mov     [rsp+150h+lpcValues], rax; lpcbData
0x1400601a3  lea     rax, [rsp+150h+Data]
0x1400601a8  mov     [rsp+150h+lpcbMaxClassLen], rax; lpData
0x1400601ad  lea     rax, [rsp+150h+Type]
0x1400601b2  mov     [rsp+150h+lpcbMaxSubKeyLen], rax; lpType
0x1400601b7  mov     [rsp+150h+phkResult], r12; lpReserved
0x1400601bc  lea     r9, [rsp+150h+cchValueName]; lpcchValueName
0x1400601c1  mov     r8, r14; lpValueName
0x1400601c4  mov     edx, ebx; dwIndex
0x1400601c6  mov     rcx, [rsp+150h+hKey]; hKey
0x1400601cb  call    cs:__imp_RegEnumValueW
0x1400601d1  test    eax, eax
0x1400601d3  jz      short loc_14006021B
0x1400601d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400601dc  cmp     rcx, rdi
0x1400601df  jz      loc_14006038A
0x1400601e5  test    byte ptr [rcx+1Ch], 1
0x1400601e9  jz      loc_14006038A
0x1400601ef  cmp     byte ptr [rcx+19h], 2
0x1400601f3  jb      loc_14006038A
0x1400601f9  mov     edx, 1Ah
0x1400601fe  mov     dword ptr [rsp+150h+phkResult], r12d
0x140060203  mov     r9d, ebx
0x140060206  lea     r8, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids
0x14006020d  mov     rcx, [rcx+10h]
0x140060211  call    WPP_SF_dd
0x140060216  jmp     loc_14006038A
0x14006021b  mov     eax, [rsp+150h+cbData]
0x14006021f  mov     r9d, [rsp+150h+Type]
0x140060224  cmp     r9d, 4
0x140060228  jnz     loc_140060359
0x14006022e  cmp     eax, r9d
0x140060231  jnz     loc_140060359
0x140060237  cmp     dword ptr [rsp+150h+Data], 1
0x14006023c  jz      short loc_140060283
0x14006023e  mov     rcx, cs:WPP_GLOBAL_Control
0x140060245  cmp     rcx, rdi
0x140060248  jz      loc_14006038A
0x14006024e  test    byte ptr [rcx+1Ch], 1
0x140060252  jz      loc_14006038A
0x140060258  cmp     [rcx+19h], r9b
0x14006025c  jb      loc_14006038A
0x140060262  lea     edx, [r9+18h]
0x140060266  mov     [rsp+150h+phkResult], r14
0x14006026b  mov     r9d, ebx
0x14006026e  lea     r8, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids
0x140060275  mov     rcx, [rcx+10h]
0x140060279  call    WPP_SF_dS
0x14006027e  jmp     loc_14006038A
0x140060283  mov     rdx, r14; lpAccountName
0x140060286  lea     rcx, [rbp+50h+var_C0]; this
0x14006028a  call    ?LoadAccount@CSid@ATL@@QEAA_NPEBG0@Z; ATL::CSid::LoadAccount(ushort const *,ushort const *)
0x14006028f  test    al, al
0x140060291  jnz     short loc_1400602F1
0x140060293  mov     rax, cs:WPP_GLOBAL_Control
0x14006029a  cmp     rax, rdi
0x14006029d  jz      loc_14006038A
0x1400602a3  test    byte ptr [rax+1Ch], 1
0x1400602a7  jz      loc_14006038A
0x1400602ad  cmp     byte ptr [rax+19h], 2
0x1400602b1  jb      loc_14006038A
0x1400602b7  call    cs:__imp_GetLastError
0x1400602bd  test    eax, eax
0x1400602bf  jle     short loc_1400602C9
0x1400602c1  movzx   eax, ax
0x1400602c4  or      eax, 80070000h
0x1400602c9  mov     edx, 1Dh
0x1400602ce  mov     dword ptr [rsp+150h+phkResult], eax
0x1400602d2  mov     r9, r14
0x1400602d5  lea     r8, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids
0x1400602dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400602e3  mov     rcx, [rcx+10h]
0x1400602e7  call    WPP_SF_Sd
0x1400602ec  jmp     loc_14006038A
0x1400602f1  xor     r9d, r9d; unsigned __int8
0x1400602f4  lea     r8d, [r9+1]; unsigned int
0x1400602f8  lea     rdx, [rbp+50h+var_C0]; struct ATL::CSid *
0x1400602fc  mov     rcx, r15; this
0x1400602ff  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x140060304  test    al, al
0x140060306  jnz     short loc_140060337
0x140060308  mov     rcx, cs:WPP_GLOBAL_Control
0x14006030f  cmp     rcx, rdi
0x140060312  jz      short loc_14006038A
0x140060314  test    byte ptr [rcx+1Ch], 1
0x140060318  jz      short loc_14006038A
0x14006031a  cmp     byte ptr [rcx+19h], 2
0x14006031e  jb      short loc_14006038A
0x140060320  mov     edx, 1Eh
0x140060325  lea     r8, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids
0x14006032c  mov     rcx, [rcx+10h]
0x140060330  call    WPP_SF_
0x140060335  jmp     short loc_14006038A
0x140060337  mov     rcx, cs:WPP_GLOBAL_Control
0x14006033e  cmp     rcx, rdi
0x140060341  jz      short loc_14006038A
0x140060343  test    byte ptr [rcx+1Ch], 1
0x140060347  jz      short loc_14006038A
0x140060349  cmp     byte ptr [rcx+19h], 4
0x14006034d  jb      short loc_14006038A
0x14006034f  mov     edx, 1Fh
0x140060354  jmp     loc_140060266
0x140060359  mov     rcx, cs:WPP_GLOBAL_Control
0x140060360  cmp     rcx, rdi
0x140060363  jz      short loc_14006038A
0x140060365  test    byte ptr [rcx+1Ch], 1
0x140060369  jz      short loc_14006038A
0x14006036b  cmp     byte ptr [rcx+19h], 3
0x14006036f  jb      short loc_14006038A
0x140060371  mov     edx, 1Bh
0x140060376  mov     dword ptr [rsp+150h+phkResult], eax
0x14006037a  lea     r8, WPP_bd42bb2a738d3306f07f53407d3aefd0_Traceguids
0x140060381  mov     rcx, [rcx+10h]
0x140060385  call    WPP_SF_dd
0x14006038a  lea     rcx, [rbp+50h+var_C0]; this
0x14006038e  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x140060393  inc     ebx
0x140060395  jmp     loc_140060106
0x14006039a  mov     ebx, 8007000Eh
0x14006039f  lea     rcx, [rbp+50h+var_C0]; this
0x1400603a3  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1400603a8  jmp     short loc_1400603BB
0x1400603aa  mov     ebx, r12d
0x1400603ad  test    r14, r14
0x1400603b0  jz      short loc_1400603BB
0x1400603b2  mov     rcx, r14; pv
0x1400603b5  call    cs:__imp_CoTaskMemFree
0x1400603bb  mov     rcx, [rsp+150h+hKey]; hKey
0x1400603c0  call    cs:__imp_RegCloseKey
0x1400603c6  mov     eax, ebx
0x1400603c8  mov     rcx, [rbp+50h+var_40]
0x1400603cc  xor     rcx, rsp; StackCookie
0x1400603cf  call    __security_check_cookie
0x1400603d4  add     rsp, 128h
0x1400603db  pop     r15
0x1400603dd  pop     r14
0x1400603df  pop     r12
0x1400603e1  pop     rdi
0x1400603e2  pop     rbx
0x1400603e3  pop     rbp
0x1400603e4  retn
```
