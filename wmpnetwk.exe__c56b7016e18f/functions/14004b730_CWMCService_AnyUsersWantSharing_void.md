# CWMCService::AnyUsersWantSharing(void)

- ea: `0x14004b730`
- end: `0x14004bb55`
- name: `?AnyUsersWantSharing@CWMCService@@AEAAHXZ`
- size: `1061`
- prototype: `__int64 __fastcall(CWMCService *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140050240`
- `0x140052250`

## callees

- `0x140006d70`
- `0x140008eac`
- `0x14000b3b0`
- `0x14000c920`
- `0x14000e660`
- `0x140015100`
- `0x140032eec`
- `0x14003e5f4`
- `0x14003f17c`
- `0x140045f20`
- `0x140047798`
- `0x14004a79c`
- `0x14004b730`

## import_xrefs

- `ADVAPI32!GetNamedSecurityInfoW` at `0x14004b99c`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x14004b99c`
- `ADVAPI32!RegEnumKeyExW` at `0x14004b843`
- `ADVAPI32!RegEnumKeyExW` at `0x14004b843`
- `KERNEL32!LocalFree` at `0x14004b7d8`
- `KERNEL32!LocalFree` at `0x14004baf8`
- `KERNEL32!LocalFree` at `0x14004b7d8`
- `KERNEL32!LocalFree` at `0x14004baf8`
- `KERNEL32!lstrcmpW` at `0x14004b962`
- `KERNEL32!lstrcmpW` at `0x14004b962`

## string_xrefs

- `0x14004b8fc`: `SharedLibraryPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWMCService::AnyUsersWantSharing(CWMCService *this)
{
  PVOID *v1; // rcx
  unsigned int v2; // esi
  PSECURITY_DESCRIPTOR v3; // rax
  DWORD v4; // r14d
  signed int v5; // eax
  unsigned int v6; // eax
  unsigned int StringValue; // eax
  int v8; // edi
  DWORD NamedSecurityInfoW; // eax
  PVOID *v10; // rcx
  LPCWSTR lpString1; // [rsp+40h] [rbp-C0h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v16[3]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey[3]; // [rsp+78h] [rbp-88h] BYREF
  PSID ppsidOwner; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Name[256]; // [rsp+A0h] [rbp-60h] BYREF

  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 265, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  v2 = 1;
  v3 = 0;
  v4 = 0;
  ppSecurityDescriptor = 0;
  while ( 1 )
  {
    if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 2) != 0 && *((_BYTE *)v1 + 25) >= 5u )
    {
      WPP_SF_d(v1[2], 266, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v4);
      v3 = ppSecurityDescriptor;
    }
    if ( v3 )
    {
      LocalFree(v3);
      ppSecurityDescriptor = 0;
    }
    memset(hKey, 0, sizeof(hKey));
    v5 = ATL::CRegKey::Open(
           (ATL::CRegKey *)hKey,
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\MediaPlayer\\Preferences\\HME\\",
           0x20219u);
    if ( v5 )
      break;
    cchName = 256;
    v6 = RegEnumKeyExW(hKey[0], v4, Name, &cchName, 0, 0, 0, 0);
    if ( v6 == 259 )
    {
      v2 = 0;
      goto LABEL_51;
    }
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 268, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v6);
      }
      goto LABEL_51;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      &lpSubKey,
      L"Software\\Microsoft\\MediaPlayer\\Preferences\\HME\\");
    ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, Name);
    memset(v16, 0, sizeof(v16));
    if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v16, HKEY_LOCAL_MACHINE, lpSubKey, 0x20219u) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&lpString1);
      StringValue = GetStringValue((ATL::CRegKey *)v16, L"SharedLibraryPath");
      if ( StringValue )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            270,
            &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
            StringValue);
        }
        goto LABEL_37;
      }
      ppsidOwner = 0;
      if ( !lstrcmpW(lpString1, &Password) )
      {
        v8 = 1;
        goto LABEL_31;
      }
      v8 = 0;
      NamedSecurityInfoW = GetNamedSecurityInfoW(
                             lpString1,
                             SE_FILE_OBJECT,
                             1u,
                             &ppsidOwner,
                             0,
                             0,
                             0,
                             &ppSecurityDescriptor);
      if ( NamedSecurityInfoW )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        {
LABEL_37:
          ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpString1);
          goto LABEL_38;
        }
        v8 = 1;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            271,
            (unsigned int)&WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
            (_DWORD)lpString1,
            NamedSecurityInfoW);
          goto LABEL_31;
        }
      }
      else
      {
LABEL_31:
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 && *((_BYTE *)v10 + 25) >= 4u )
        WPP_SF_Sd(
          (unsigned int)v10[2],
          272,
          (unsigned int)&WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
          (unsigned int)Name,
          v8);
      if ( !v8 )
      {
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpString1);
        ATL::CRegKey::Close((ATL::CRegKey *)v16);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpSubKey);
        goto LABEL_51;
      }
      goto LABEL_37;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 269, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, lpSubKey);
    }
LABEL_38:
    ATL::CRegKey::Close((ATL::CRegKey *)v16);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpSubKey);
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    v3 = ppSecurityDescriptor;
    ++v4;
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80070000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      267,
      &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
      (unsigned int)v5);
  }
LABEL_51:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  if ( ppSecurityDescriptor )
  {
    LocalFree(ppSecurityDescriptor);
    ppSecurityDescriptor = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 273, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x14004b730  push    rbp
0x14004b732  push    rsi
0x14004b733  push    rdi
0x14004b734  push    r13
0x14004b736  push    r14
0x14004b738  push    r15
0x14004b73a  lea     rbp, [rsp-1B8h]
0x14004b742  sub     rsp, 2B8h
0x14004b749  mov     rax, cs:__security_cookie
0x14004b750  xor     rax, rsp
0x14004b753  mov     [rbp+1E0h+var_40], rax
0x14004b75a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b761  lea     r13, WPP_GLOBAL_Control
0x14004b768  cmp     rcx, r13
0x14004b76b  jz      short loc_14004B78F
0x14004b76d  test    byte ptr [rcx+1Ch], 1
0x14004b771  jz      short loc_14004B78F
0x14004b773  mov     rcx, [rcx+10h]
0x14004b777  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004b77e  mov     edx, 109h
0x14004b783  call    WPP_SF_
0x14004b788  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b78f  xor     r15d, r15d
0x14004b792  mov     esi, 1
0x14004b797  mov     eax, r15d
0x14004b79a  mov     r14d, r15d
0x14004b79d  mov     [rsp+2E0h+ppSecurityDescriptor], rax
0x14004b7a2  cmp     rcx, r13
0x14004b7a5  jz      short loc_14004B7D0
0x14004b7a7  test    byte ptr [rcx+1Ch], 2
0x14004b7ab  jz      short loc_14004B7D0
0x14004b7ad  cmp     byte ptr [rcx+19h], 5
0x14004b7b1  jb      short loc_14004B7D0
0x14004b7b3  mov     rcx, [rcx+10h]
0x14004b7b7  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004b7be  mov     edx, 10Ah
0x14004b7c3  mov     r9d, r14d
0x14004b7c6  call    WPP_SF_d
0x14004b7cb  mov     rax, [rsp+2E0h+ppSecurityDescriptor]
0x14004b7d0  test    rax, rax
0x14004b7d3  jz      short loc_14004B7E3
0x14004b7d5  mov     rcx, rax; hMem
0x14004b7d8  call    cs:__imp_LocalFree
0x14004b7de  mov     [rsp+2E0h+ppSecurityDescriptor], r15
0x14004b7e3  mov     r9d, 20219h; unsigned int
0x14004b7e9  mov     [rsp+2E0h+hKey], r15
0x14004b7ee  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\MediaPlayer\\Prefe"...
0x14004b7f5  mov     [rbp+1E0h+var_260], r15
0x14004b7f9  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14004b800  mov     [rbp+1E0h+var_258], r15
0x14004b804  lea     rcx, [rsp+2E0h+hKey]; this
0x14004b809  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14004b80e  test    eax, eax
0x14004b810  jnz     loc_14004BAAA
0x14004b816  mov     rcx, [rsp+2E0h+hKey]; hKey
0x14004b81b  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x14004b820  mov     [rsp+2E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x14004b825  lea     r8, [rbp+1E0h+Name]; lpName
0x14004b829  mov     [rsp+2E0h+lpcchClass], r15; lpcchClass
0x14004b82e  mov     edx, r14d; dwIndex
0x14004b831  mov     [rsp+2E0h+lpClass], r15; lpClass
0x14004b836  mov     [rsp+2E0h+lpReserved], r15; lpReserved
0x14004b83b  mov     [rsp+2E0h+cchName], 100h
0x14004b843  call    cs:__imp_RegEnumKeyExW
0x14004b849  cmp     eax, 103h
0x14004b84e  jz      loc_14004BAA5
0x14004b854  test    eax, eax
0x14004b856  jnz     loc_14004BA73
0x14004b85c  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\MediaPlayer\\Prefe"...
0x14004b863  lea     rcx, [rsp+2E0h+lpSubKey]
0x14004b868  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14004b86d  lea     rdx, [rbp+1E0h+Name]
0x14004b871  lea     rcx, [rsp+2E0h+lpSubKey]
0x14004b876  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x14004b87b  mov     r8, [rsp+2E0h+lpSubKey]; lpSubKey
0x14004b880  lea     rcx, [rsp+2E0h+var_280]; this
0x14004b885  mov     r9d, 20219h; unsigned int
0x14004b88b  mov     [rsp+2E0h+var_280], r15
0x14004b890  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14004b897  mov     [rsp+2E0h+var_278], r15
0x14004b89c  mov     [rsp+2E0h+var_270], r15
0x14004b8a1  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14004b8a6  test    eax, eax
0x14004b8a8  jz      short loc_14004B8ED
0x14004b8aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b8b1  cmp     rcx, r13
0x14004b8b4  jz      loc_14004BA21
0x14004b8ba  test    byte ptr [rcx+1Ch], 2
0x14004b8be  jz      loc_14004BA21
0x14004b8c4  cmp     byte ptr [rcx+19h], 2
0x14004b8c8  jb      loc_14004BA21
0x14004b8ce  mov     r9, [rsp+2E0h+lpSubKey]
0x14004b8d3  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004b8da  mov     rcx, [rcx+10h]
0x14004b8de  mov     edx, 10Dh
0x14004b8e3  call    WPP_SF_S
0x14004b8e8  jmp     loc_14004BA21
0x14004b8ed  lea     rcx, [rsp+2E0h+lpString1]
0x14004b8f2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14004b8f7  lea     r8, [rsp+2E0h+lpString1]
0x14004b8fc  lea     rdx, aSharedlibraryp_0; "SharedLibraryPath"
0x14004b903  lea     rcx, [rsp+2E0h+var_280]; this
0x14004b908  call    ?GetStringValue@@YAJAEAVCRegKey@ATL@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@2@@Z; GetStringValue(ATL::CRegKey &,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x14004b90d  test    eax, eax
0x14004b90f  jz      short loc_14004B952
0x14004b911  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b918  cmp     rcx, r13
0x14004b91b  jz      loc_14004BA17
0x14004b921  test    byte ptr [rcx+1Ch], 2
0x14004b925  jz      loc_14004BA17
0x14004b92b  cmp     byte ptr [rcx+19h], 5
0x14004b92f  jb      loc_14004BA17
0x14004b935  mov     rcx, [rcx+10h]
0x14004b939  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004b940  mov     edx, 10Eh
0x14004b945  mov     r9d, eax
0x14004b948  call    WPP_SF_d
0x14004b94d  jmp     loc_14004BA17
0x14004b952  mov     rcx, [rsp+2E0h+lpString1]; lpString1
0x14004b957  lea     rdx, Password; lpString2
0x14004b95e  mov     [rbp+1E0h+ppsidOwner], r15
0x14004b962  call    cs:__imp_lstrcmpW
0x14004b968  test    eax, eax
0x14004b96a  jnz     short loc_14004B970
0x14004b96c  mov     edi, esi
0x14004b96e  jmp     short loc_14004B9DE
0x14004b970  mov     rcx, [rsp+2E0h+lpString1]; pObjectName
0x14004b975  lea     rax, [rsp+2E0h+ppSecurityDescriptor]
0x14004b97a  mov     [rsp+2E0h+lpftLastWriteTime], rax; ppSecurityDescriptor
0x14004b97f  lea     r9, [rbp+1E0h+ppsidOwner]; ppsidOwner
0x14004b983  mov     eax, esi
0x14004b985  mov     [rsp+2E0h+lpcchClass], r15; ppSacl
0x14004b98a  mov     r8d, eax; SecurityInfo
0x14004b98d  mov     [rsp+2E0h+lpClass], r15; ppDacl
0x14004b992  mov     edx, eax; ObjectType
0x14004b994  mov     [rsp+2E0h+lpReserved], r15; ppsidGroup
0x14004b999  mov     edi, r15d
0x14004b99c  call    cs:__imp_GetNamedSecurityInfoW
0x14004b9a2  test    eax, eax
0x14004b9a4  jz      short loc_14004B9DE
0x14004b9a6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b9ad  cmp     rcx, r13
0x14004b9b0  jz      short loc_14004BA17
0x14004b9b2  test    byte ptr [rcx+1Ch], 2
0x14004b9b6  mov     edi, esi
0x14004b9b8  jz      short loc_14004B9E5
0x14004b9ba  cmp     byte ptr [rcx+19h], 5
0x14004b9be  jb      short loc_14004B9E5
0x14004b9c0  mov     r9, [rsp+2E0h+lpString1]
0x14004b9c5  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004b9cc  mov     rcx, [rcx+10h]
0x14004b9d0  mov     edx, 10Fh
0x14004b9d5  mov     dword ptr [rsp+2E0h+lpReserved], eax
0x14004b9d9  call    WPP_SF_Sd
0x14004b9de  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b9e5  cmp     rcx, r13
0x14004b9e8  jz      short loc_14004BA13
0x14004b9ea  test    byte ptr [rcx+1Ch], 2
0x14004b9ee  jz      short loc_14004BA13
0x14004b9f0  cmp     byte ptr [rcx+19h], 4
0x14004b9f4  jb      short loc_14004BA13
0x14004b9f6  mov     rcx, [rcx+10h]
0x14004b9fa  lea     r9, [rbp+1E0h+Name]
0x14004b9fe  mov     edx, 110h
0x14004ba03  mov     dword ptr [rsp+2E0h+lpReserved], edi
0x14004ba07  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004ba0e  call    WPP_SF_Sd
0x14004ba13  test    edi, edi
0x14004ba15  jz      short loc_14004BA53
0x14004ba17  lea     rcx, [rsp+2E0h+lpString1]
0x14004ba1c  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14004ba21  lea     rcx, [rsp+2E0h+var_280]; this
0x14004ba26  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14004ba2b  lea     rcx, [rsp+2E0h+lpSubKey]
0x14004ba30  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14004ba35  lea     rcx, [rsp+2E0h+hKey]; this
0x14004ba3a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14004ba3f  mov     rax, [rsp+2E0h+ppSecurityDescriptor]
0x14004ba44  inc     r14d
0x14004ba47  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ba4e  jmp     loc_14004B7A2
0x14004ba53  lea     rcx, [rsp+2E0h+lpString1]
0x14004ba58  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14004ba5d  lea     rcx, [rsp+2E0h+var_280]; this
0x14004ba62  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14004ba67  lea     rcx, [rsp+2E0h+lpSubKey]
0x14004ba6c  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14004ba71  jmp     short loc_14004BAE4
0x14004ba73  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ba7a  cmp     rcx, r13
0x14004ba7d  jz      short loc_14004BAE4
0x14004ba7f  test    byte ptr [rcx+1Ch], 2
0x14004ba83  jz      short loc_14004BAE4
0x14004ba85  cmp     byte ptr [rcx+19h], 2
0x14004ba89  jb      short loc_14004BAE4
0x14004ba8b  mov     rcx, [rcx+10h]
0x14004ba8f  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004ba96  mov     edx, 10Ch
0x14004ba9b  mov     r9d, eax
0x14004ba9e  call    WPP_SF_d
0x14004baa3  jmp     short loc_14004BAE4
0x14004baa5  mov     esi, r15d
0x14004baa8  jmp     short loc_14004BAE4
0x14004baaa  jle     short loc_14004BAB4
0x14004baac  movzx   eax, ax
0x14004baaf  or      eax, 80070000h
0x14004bab4  mov     rcx, cs:WPP_GLOBAL_Control
0x14004babb  cmp     rcx, r13
0x14004babe  jz      short loc_14004BAE4
0x14004bac0  test    byte ptr [rcx+1Ch], 2
0x14004bac4  jz      short loc_14004BAE4
0x14004bac6  cmp     byte ptr [rcx+19h], 2
0x14004baca  jb      short loc_14004BAE4
0x14004bacc  mov     rcx, [rcx+10h]
0x14004bad0  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004bad7  mov     edx, 10Bh
0x14004badc  mov     r9d, eax
0x14004badf  call    WPP_SF_d
0x14004bae4  lea     rcx, [rsp+2E0h+hKey]; this
0x14004bae9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14004baee  mov     rcx, [rsp+2E0h+ppSecurityDescriptor]; hMem
0x14004baf3  test    rcx, rcx
0x14004baf6  jz      short loc_14004BB03
0x14004baf8  call    cs:__imp_LocalFree
0x14004bafe  mov     [rsp+2E0h+ppSecurityDescriptor], r15
0x14004bb03  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bb0a  cmp     rcx, r13
0x14004bb0d  jz      short loc_14004BB33
0x14004bb0f  test    byte ptr [rcx+1Ch], 1
0x14004bb13  jz      short loc_14004BB33
0x14004bb15  cmp     byte ptr [rcx+19h], 5
0x14004bb19  jb      short loc_14004BB33
0x14004bb1b  mov     rcx, [rcx+10h]
0x14004bb1f  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004bb26  mov     edx, 111h
0x14004bb2b  mov     r9d, esi
0x14004bb2e  call    WPP_SF_d
0x14004bb33  mov     eax, esi
0x14004bb35  mov     rcx, [rbp+1E0h+var_40]
0x14004bb3c  xor     rcx, rsp; StackCookie
0x14004bb3f  call    __security_check_cookie
0x14004bb44  add     rsp, 2B8h
0x14004bb4b  pop     r15
0x14004bb4d  pop     r14
0x14004bb4f  pop     r13
0x14004bb51  pop     rdi
0x14004bb52  pop     rsi
0x14004bb53  pop     rbp
0x14004bb54  retn
```
