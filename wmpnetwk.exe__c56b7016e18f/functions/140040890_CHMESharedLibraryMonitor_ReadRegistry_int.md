# CHMESharedLibraryMonitor::_ReadRegistry(int)

- ea: `0x140040890`
- end: `0x140040e39`
- name: `?_ReadRegistry@CHMESharedLibraryMonitor@@IEAAJH@Z`
- size: `1449`
- prototype: `__int64 __fastcall(CHMESharedLibraryMonitor *this, int, __int64)`
- caller_count: `2`
- callee_count: `26`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14008af50`
- `0x14008c050`

## callees

- `0x140006d70`
- `0x140008eac`
- `0x14000b3b0`
- `0x14000b3f0`
- `0x14000c780`
- `0x14000c920`
- `0x14000e660`
- `0x140015100`
- `0x1400329d4`
- `0x140032eec`
- `0x14003e5f4`
- `0x14003f17c`
- `0x14004057c`
- `0x140040890`
- `0x140040e40`
- `0x140045f20`
- `0x14004a79c`
- `0x14004aa78`
- `0x14004af64`
- `0x14005e390`
- `0x140086534`
- `0x14008acf4`
- `0x14008b124`
- `0x14008b434`
- `0x14008b558`
- `0x14008bfa4`

## import_xrefs

- `ADVAPI32!GetNamedSecurityInfoW` at `0x140040afe`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x140040afe`
- `ADVAPI32!RegEnumKeyExW` at `0x140040949`
- `ADVAPI32!RegEnumKeyExW` at `0x140040949`
- `KERNEL32!LocalFree` at `0x140040e04`
- `KERNEL32!LocalFree` at `0x140040e04`
- `KERNEL32!lstrcmpW` at `0x140040a8a`
- `KERNEL32!lstrcmpW` at `0x140040ac5`
- `KERNEL32!lstrcmpW` at `0x140040baa`
- `KERNEL32!lstrcmpW` at `0x140040a8a`
- `KERNEL32!lstrcmpW` at `0x140040ac5`
- `KERNEL32!lstrcmpW` at `0x140040baa`

## string_xrefs

- `0x1400409d9`: `SharedLibraryPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CHMESharedLibraryMonitor::_ReadRegistry(CHMESharedLibraryMonitor *this, int a2, __int64 a3)
{
  CHMESharedLibraryMonitor *v3; // r13
  DWORD v4; // edi
  int v5; // eax
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  LPCWSTR v8; // rdi
  bool v9; // r15
  __int64 v10; // rax
  const WCHAR *v11; // r14
  char v12; // r12
  DWORD NamedSecurityInfoW; // eax
  __int64 v14; // rax
  char *v15; // rsi
  char v16; // al
  LPCWSTR v17; // rbx
  char v18; // al
  bool v19; // r13
  __int64 v20; // rax
  __int64 v21; // rsi
  bool v22; // al
  __int64 v23; // rdx
  int lpClass; // [rsp+28h] [rbp-D8h]
  char v26; // [rsp+41h] [rbp-BFh]
  unsigned int v27; // [rsp+44h] [rbp-BCh] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD i; // [rsp+50h] [rbp-B0h]
  LPCWSTR lpString2; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR pObjectName; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR v32; // [rsp+68h] [rbp-98h] BYREF
  char v33; // [rsp+70h] [rbp-90h]
  bool v34; // [rsp+71h] [rbp-8Fh]
  DWORD cchName; // [rsp+78h] [rbp-88h] BYREF
  int v36; // [rsp+7Ch] [rbp-84h]
  LPCWSTR lpString1; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v38[3]; // [rsp+88h] [rbp-78h] BYREF
  CHMESharedLibraryMonitor *v39; // [rsp+A0h] [rbp-60h]
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+A8h] [rbp-58h] BYREF
  HKEY hKey[3]; // [rsp+B0h] [rbp-50h] BYREF
  PSID ppsidOwner; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v43[16]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Name[256]; // [rsp+E0h] [rbp-20h] BYREF

  v36 = a2;
  v3 = this;
  v39 = this;
  LOBYTE(a3) = 1;
  ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(v43, this, a3);
  ppSecurityDescriptor = 0;
  v4 = 0;
  for ( i = 0; ; i = v4 )
  {
    memset(hKey, 0, sizeof(hKey));
    v5 = ATL::CRegKey::Open(
           (ATL::CRegKey *)hKey,
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\MediaPlayer\\Preferences\\HME\\",
           0x20219u);
    v6 = v5;
    if ( v5 )
      break;
    cchName = 256;
    v7 = RegEnumKeyExW(hKey[0], v4, Name, &cchName, 0, 0, 0, 0);
    v6 = v7;
    if ( v7 == 259 )
    {
      v6 = 0;
      goto LABEL_65;
    }
    if ( v7 )
    {
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_03e2d22dd8b23a87589ec6c69d825632_Traceguids, v6);
      }
      goto LABEL_65;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      &lpSubKey,
      L"Software\\Microsoft\\MediaPlayer\\Preferences\\HME\\");
    ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, Name);
    memset(v38, 0, sizeof(v38));
    if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v38, HKEY_LOCAL_MACHINE, lpSubKey, 0x20219u) )
      goto LABEL_6;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&pObjectName);
    if ( (unsigned int)GetStringValue((ATL::CRegKey *)v38, L"SharedLibraryPath") )
      goto LABEL_8;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&lpString2);
    if ( (unsigned int)GetStringValue((ATL::CRegKey *)v38, L"DisplayName") )
    {
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpString2);
LABEL_8:
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&pObjectName);
LABEL_6:
      ATL::CRegKey::Close((ATL::CRegKey *)v38);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpSubKey);
      goto LABEL_55;
    }
    v27 = 0;
    if ( (unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v38, L"AlwaysAllowMachineToSleep", &v27) )
      v27 = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&lpString1);
    ATL::CRBMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::Lookup(
      (char *)v3 + 40,
      Name,
      &lpString1);
    v8 = lpString1;
    if ( *((_DWORD *)lpString1 - 4) )
    {
      v26 = 1;
      v9 = lstrcmpW(lpString1, &Password) == 0;
      v10 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<bool>>::Find(
              (char *)v3 + 40,
              Name);
      if ( v10 )
        ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RBDelete(
          (char *)v3 + 40,
          v10);
    }
    else
    {
      v26 = 0;
      v9 = 1;
    }
    ppsidOwner = 0;
    v11 = pObjectName;
    if ( lstrcmpW(pObjectName, &Password) )
    {
      NamedSecurityInfoW = GetNamedSecurityInfoW(v11, SE_FILE_OBJECT, 1u, &ppsidOwner, 0, 0, 0, &ppSecurityDescriptor);
      if ( NamedSecurityInfoW )
      {
        v12 = 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            (unsigned int)WPP_03e2d22dd8b23a87589ec6c69d825632_Traceguids,
            (_DWORD)v11,
            NamedSecurityInfoW);
        }
      }
      else
      {
        v12 = 0;
        v14 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,bool,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<bool>>::Find(
                (char *)v3 + 40,
                Name);
        if ( v14 )
          ATL::CSimpleStringT<unsigned short,0>::SetString(v14 + 8, v11);
        else
          ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RBInsert(
            (char *)v3 + 40,
            Name,
            v11);
      }
    }
    else
    {
      v12 = 1;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v32);
    v15 = (char *)v3 + 88;
    v16 = ATL::CRBMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CHMESharedLibraryMonitor::LibraryParams,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<CHMESharedLibraryMonitor::LibraryParams>>::Lookup(
            (char *)v3 + 88,
            Name,
            &v32);
    v17 = lpString2;
    if ( !v16 || lstrcmpW(v32, lpString2) )
    {
      ATL::CSimpleStringT<unsigned short,0>::operator=(&v32, &lpString2);
      v33 = 0;
      v19 = v27 == 1;
      v34 = v27 == 1;
      v20 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CHMESharedLibraryMonitor::LibraryParams,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<CHMESharedLibraryMonitor::LibraryParams>>::Find(
              v15,
              Name);
      if ( v20 )
      {
        v21 = v20 + 8;
        ATL::CSimpleStringT<unsigned short,0>::operator=(v20 + 8, &v32);
        *(_BYTE *)(v21 + 8) = 0;
        *(_BYTE *)(v21 + 9) = v19;
      }
      else
      {
        ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CHMESharedLibraryMonitor::LibraryParams,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<CHMESharedLibraryMonitor::LibraryParams>>::RBInsert(
          v15,
          Name,
          &v32);
      }
      v3 = v39;
      v18 = 1;
    }
    else
    {
      v18 = 0;
    }
    if ( v36 )
    {
      if ( v26 && !v9 )
        goto LABEL_44;
      if ( !v12 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)Name, (__int64)v17);
        }
        v22 = v27 == 1;
        v23 = 0;
LABEL_53:
        LOBYTE(lpClass) = v22;
        CHMESharedLibraryMonitor::_OnLibraryEvent(v3, v23, v11, Name, v17, lpClass);
        goto LABEL_54;
      }
      if ( !v9 )
      {
LABEL_44:
        if ( v12 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_03e2d22dd8b23a87589ec6c69d825632_Traceguids, v8);
          }
          LOBYTE(lpClass) = 0;
          CHMESharedLibraryMonitor::_OnLibraryEvent(v3, 1, v8, Name, 0, lpClass);
          goto LABEL_54;
        }
      }
      if ( v18 )
      {
        LOBYTE(lpClass) = v27 == 1;
        CHMESharedLibraryMonitor::_OnLibraryEvent(v3, 2, v11, Name, v17, lpClass);
      }
      v22 = v27 == 1;
      v23 = 3;
      goto LABEL_53;
    }
LABEL_54:
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v32);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpString1);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpString2);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&pObjectName);
    ATL::CRegKey::Close((ATL::CRegKey *)v38);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpSubKey);
    v4 = i;
LABEL_55:
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    ++v4;
  }
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
LABEL_65:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  if ( ppSecurityDescriptor )
    LocalFree(ppSecurityDescriptor);
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v43);
  return v6;
}

```

## disassembly

```asm
0x140040890  push    rbp
0x140040892  push    rbx
0x140040893  push    rsi
0x140040894  push    rdi
0x140040895  push    r12
0x140040897  push    r13
0x140040899  push    r14
0x14004089b  push    r15
0x14004089d  lea     rbp, [rsp-1F8h]
0x1400408a5  sub     rsp, 2F8h
0x1400408ac  mov     rax, cs:__security_cookie
0x1400408b3  xor     rax, rsp
0x1400408b6  mov     [rbp+230h+var_50], rax
0x1400408bd  mov     [rsp+330h+var_2B4], edx
0x1400408c1  mov     r13, rcx
0x1400408c4  mov     [rbp+230h+var_290], rcx
0x1400408c8  mov     r8b, 1
0x1400408cb  mov     rdx, rcx
0x1400408ce  lea     rcx, [rbp+230h+var_260]
0x1400408d2  call    ??0?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@AEAVCComCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(ATL::CComCriticalSection &,bool)
0x1400408d7  nop
0x1400408d8  xor     esi, esi
0x1400408da  mov     [rbp+230h+ppSecurityDescriptor], rsi
0x1400408de  mov     edi, esi
0x1400408e0  mov     [rsp+330h+var_2E0], esi
0x1400408e4  lea     r14, WPP_GLOBAL_Control
0x1400408eb  mov     [rbp+230h+hKey], rsi
0x1400408ef  mov     [rbp+230h+var_278], rsi
0x1400408f3  mov     [rbp+230h+var_270], rsi
0x1400408f7  mov     r9d, 20219h; unsigned int
0x1400408fd  lea     r8, aSoftwareMicros_9; "Software\\Microsoft\\MediaPlayer\\Prefe"...
0x140040904  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14004090b  lea     rcx, [rbp+230h+hKey]; this
0x14004090f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140040914  mov     ebx, eax
0x140040916  test    eax, eax
0x140040918  jnz     loc_140040DE7
0x14004091e  mov     [rsp+330h+cchName], 100h
0x140040926  mov     [rsp+330h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x14004092b  mov     [rsp+330h+lpcchClass], rsi; lpcchClass
0x140040930  mov     [rsp+330h+lpClass], rsi; lpClass
0x140040935  mov     [rsp+330h+lpReserved], rsi; lpReserved
0x14004093a  lea     r9, [rsp+330h+cchName]; lpcchName
0x14004093f  lea     r8, [rbp+230h+Name]; lpName
0x140040943  mov     edx, edi; dwIndex
0x140040945  mov     rcx, [rbp+230h+hKey]; hKey
0x140040949  call    cs:__imp_RegEnumKeyExW
0x14004094f  mov     ebx, eax
0x140040951  cmp     eax, 103h
0x140040956  jz      loc_140040DE3
0x14004095c  test    eax, eax
0x14004095e  jnz     loc_140040DA6
0x140040964  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\MediaPlayer\\Prefe"...
0x14004096b  lea     rcx, [rsp+330h+lpSubKey]
0x140040970  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140040975  nop
0x140040976  lea     rdx, [rbp+230h+Name]
0x14004097a  lea     rcx, [rsp+330h+lpSubKey]
0x14004097f  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x140040984  mov     [rbp+230h+var_2A8], rsi
0x140040988  mov     [rbp+230h+var_2A0], rsi
0x14004098c  mov     [rbp+230h+var_298], rsi
0x140040990  mov     r9d, 20219h; unsigned int
0x140040996  mov     r8, [rsp+330h+lpSubKey]; lpSubKey
0x14004099b  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1400409a2  lea     rcx, [rbp+230h+var_2A8]; this
0x1400409a6  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400409ab  test    eax, eax
0x1400409ad  jz      short loc_1400409C9
0x1400409af  lea     rcx, [rbp+230h+var_2A8]; this
0x1400409b3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400409b8  nop
0x1400409b9  lea     rcx, [rsp+330h+lpSubKey]
0x1400409be  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400409c3  nop
0x1400409c4  jmp     loc_140040D92
0x1400409c9  lea     rcx, [rsp+330h+pObjectName]
0x1400409ce  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x1400409d3  nop
0x1400409d4  lea     r8, [rsp+330h+pObjectName]
0x1400409d9  lea     rdx, aSharedlibraryp; "SharedLibraryPath"
0x1400409e0  lea     rcx, [rbp+230h+var_2A8]; this
0x1400409e4  call    ?GetStringValue@@YAJAEAVCRegKey@ATL@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@2@@Z; GetStringValue(ATL::CRegKey &,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x1400409e9  test    eax, eax
0x1400409eb  jz      short loc_1400409F9
0x1400409ed  lea     rcx, [rsp+330h+pObjectName]
0x1400409f2  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400409f7  jmp     short loc_1400409AF
0x1400409f9  lea     rcx, [rsp+330h+lpString2]
0x1400409fe  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140040a03  nop
0x140040a04  lea     r8, [rsp+330h+lpString2]
0x140040a09  lea     rdx, aDisplayname; "DisplayName"
0x140040a10  lea     rcx, [rbp+230h+var_2A8]; this
0x140040a14  call    ?GetStringValue@@YAJAEAVCRegKey@ATL@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@2@@Z; GetStringValue(ATL::CRegKey &,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x140040a19  test    eax, eax
0x140040a1b  jz      short loc_140040A29
0x140040a1d  lea     rcx, [rsp+330h+lpString2]
0x140040a22  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140040a27  jmp     short loc_1400409ED
0x140040a29  mov     [rsp+330h+var_2EC], esi
0x140040a2d  lea     r8, [rsp+330h+var_2EC]; unsigned int *
0x140040a32  lea     rdx, aAlwaysallowmac; "AlwaysAllowMachineToSleep"
0x140040a39  lea     rcx, [rbp+230h+var_2A8]; this
0x140040a3d  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x140040a42  test    eax, eax
0x140040a44  jz      short loc_140040A4A
0x140040a46  mov     [rsp+330h+var_2EC], esi
0x140040a4a  lea     rcx, [rbp+230h+lpString1]
0x140040a4e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140040a53  nop
0x140040a54  lea     rbx, [r13+28h]
0x140040a58  lea     r8, [rbp+230h+lpString1]
0x140040a5c  lea     rdx, [rbp+230h+Name]
0x140040a60  mov     rcx, rbx
0x140040a63  call    ?Lookup@?$CRBMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@2@@Z; ATL::CRBMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::Lookup(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x140040a68  mov     rdi, [rbp+230h+lpString1]
0x140040a6c  cmp     [rdi-10h], esi
0x140040a6f  jnz     short loc_140040A7B
0x140040a71  mov     [rsp+330h+var_2EF], sil
0x140040a76  mov     r15b, 1
0x140040a79  jmp     short loc_140040AB2
0x140040a7b  mov     [rsp+330h+var_2EF], 1
0x140040a80  lea     rdx, Password; lpString2
0x140040a87  mov     rcx, rdi; lpString1
0x140040a8a  call    cs:__imp_lstrcmpW
0x140040a90  test    eax, eax
0x140040a92  setz    r15b
0x140040a96  lea     rdx, [rbp+230h+Name]
0x140040a9a  mov     rcx, rbx
0x140040a9d  call    ?Find@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@_NV?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@_N@2@@ATL@@IEBAPEAVCNode@12@PEBG@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,bool,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<bool>>::Find(ushort const *)
0x140040aa2  test    rax, rax
0x140040aa5  jz      short loc_140040AB2
0x140040aa7  mov     rdx, rax
0x140040aaa  mov     rcx, rbx
0x140040aad  call    ?RBDelete@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@AEAA_NPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::RBDelete(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::CNode *)
0x140040ab2  mov     [rbp+230h+ppsidOwner], rsi
0x140040ab6  lea     rdx, Password; lpString2
0x140040abd  mov     r14, [rsp+330h+pObjectName]
0x140040ac2  mov     rcx, r14; lpString1
0x140040ac5  call    cs:__imp_lstrcmpW
0x140040acb  test    eax, eax
0x140040acd  jnz     short loc_140040AD7
0x140040acf  mov     r12b, 1
0x140040ad2  jmp     loc_140040B79
0x140040ad7  lea     rax, [rbp+230h+ppSecurityDescriptor]
0x140040adb  mov     [rsp+330h+lpftLastWriteTime], rax; ppSecurityDescriptor
0x140040ae0  mov     [rsp+330h+lpcchClass], rsi; ppSacl
0x140040ae5  mov     [rsp+330h+lpClass], rsi; ppDacl
0x140040aea  mov     [rsp+330h+lpReserved], rsi; ppsidGroup
0x140040aef  lea     r9, [rbp+230h+ppsidOwner]; ppsidOwner
0x140040af3  mov     edx, 1; ObjectType
0x140040af8  mov     r8d, edx; SecurityInfo
0x140040afb  mov     rcx, r14; pObjectName
0x140040afe  call    cs:__imp_GetNamedSecurityInfoW
0x140040b04  test    eax, eax
0x140040b06  jz      short loc_140040B48
0x140040b08  mov     r12b, 1
0x140040b0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140040b12  lea     rdx, WPP_GLOBAL_Control
0x140040b19  cmp     rcx, rdx
0x140040b1c  jz      short loc_140040B79
0x140040b1e  test    byte ptr [rcx+1Ch], 2
0x140040b22  jz      short loc_140040B79
0x140040b24  cmp     byte ptr [rcx+19h], 5
0x140040b28  jb      short loc_140040B79
0x140040b2a  mov     edx, 0Ch
0x140040b2f  mov     dword ptr [rsp+330h+lpReserved], eax
0x140040b33  mov     r9, r14
0x140040b36  lea     r8, WPP_03e2d22dd8b23a87589ec6c69d825632_Traceguids
0x140040b3d  mov     rcx, [rcx+10h]
0x140040b41  call    WPP_SF_Sd
0x140040b46  jmp     short loc_140040B79
0x140040b48  mov     r12b, sil
0x140040b4b  lea     rdx, [rbp+230h+Name]
0x140040b4f  mov     rcx, rbx
0x140040b52  call    ?Find@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@_NV?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@_N@2@@ATL@@IEBAPEAVCNode@12@PEBG@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,bool,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<bool>>::Find(ushort const *)
0x140040b57  test    rax, rax
0x140040b5a  jnz     short loc_140040B6D
0x140040b5c  mov     r8, r14
0x140040b5f  lea     rdx, [rbp+230h+Name]
0x140040b63  mov     rcx, rbx
0x140040b66  call    ?RBInsert@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@IEAAPEAVCNode@12@PEBG0@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::RBInsert(ushort const *,ushort const *)
0x140040b6b  jmp     short loc_140040B79
0x140040b6d  lea     rcx, [rax+8]
0x140040b71  mov     rdx, r14
0x140040b74  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x140040b79  lea     rcx, [rsp+330h+var_2C8]
0x140040b7e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140040b83  nop
0x140040b84  lea     rsi, [r13+58h]
0x140040b88  lea     r8, [rsp+330h+var_2C8]
0x140040b8d  lea     rdx, [rbp+230h+Name]
0x140040b91  mov     rcx, rsi
0x140040b94  call    ?Lookup@?$CRBMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@ULibraryParams@CHMESharedLibraryMonitor@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@ULibraryParams@CHMESharedLibraryMonitor@@@2@@ATL@@QEBA_NPEBGAEAULibraryParams@CHMESharedLibraryMonitor@@@Z; ATL::CRBMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CHMESharedLibraryMonitor::LibraryParams,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<CHMESharedLibraryMonitor::LibraryParams>>::Lookup(ushort const *,CHMESharedLibraryMonitor::LibraryParams &)
0x140040b99  mov     rbx, [rsp+330h+lpString2]
0x140040b9e  test    al, al
0x140040ba0  jz      short loc_140040BBB
0x140040ba2  mov     rdx, rbx; lpString2
0x140040ba5  mov     rcx, [rsp+330h+var_2C8]; lpString1
0x140040baa  call    cs:__imp_lstrcmpW
0x140040bb0  test    eax, eax
0x140040bb2  jnz     short loc_140040BBB
0x140040bb4  xor     esi, esi
0x140040bb6  mov     al, sil
0x140040bb9  jmp     short loc_140040C29
0x140040bbb  mov     [rsp+330h+var_2F0], 1
0x140040bc0  lea     rdx, [rsp+330h+lpString2]
0x140040bc5  lea     rcx, [rsp+330h+var_2C8]
0x140040bca  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140040bcf  mov     [rsp+330h+var_2C0], 0
0x140040bd4  cmp     [rsp+330h+var_2EC], 1
0x140040bd9  setz    r13b
0x140040bdd  mov     [rsp+330h+var_2BF], r13b
0x140040be2  lea     rdx, [rbp+230h+Name]
0x140040be6  mov     rcx, rsi
0x140040be9  call    ?Find@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@ULibraryParams@CHMESharedLibraryMonitor@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@ULibraryParams@CHMESharedLibraryMonitor@@@2@@ATL@@IEBAPEAVCNode@12@PEBG@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CHMESharedLibraryMonitor::LibraryParams,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<CHMESharedLibraryMonitor::LibraryParams>>::Find(ushort const *)
0x140040bee  test    rax, rax
0x140040bf1  jnz     short loc_140040C06
0x140040bf3  lea     r8, [rsp+330h+var_2C8]
0x140040bf8  lea     rdx, [rbp+230h+Name]
0x140040bfc  mov     rcx, rsi
0x140040bff  call    ?RBInsert@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@ULibraryParams@CHMESharedLibraryMonitor@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@ULibraryParams@CHMESharedLibraryMonitor@@@2@@ATL@@IEAAPEAVCNode@12@PEBGAEBULibraryParams@CHMESharedLibraryMonitor@@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CHMESharedLibraryMonitor::LibraryParams,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<CHMESharedLibraryMonitor::LibraryParams>>::RBInsert(ushort const *,CHMESharedLibraryMonitor::LibraryParams const &)
0x140040c04  jmp     short loc_140040C1F
0x140040c06  lea     rsi, [rax+8]
0x140040c0a  lea     rdx, [rsp+330h+var_2C8]
0x140040c0f  mov     rcx, rsi
0x140040c12  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140040c17  mov     byte ptr [rsi+8], 0
0x140040c1b  mov     [rsi+9], r13b
0x140040c1f  xor     esi, esi
0x140040c21  mov     r13, [rbp+230h+var_290]
0x140040c25  mov     al, [rsp+330h+var_2F0]
0x140040c29  cmp     [rsp+330h+var_2B4], esi
0x140040c2d  jz      loc_140040D47
0x140040c33  cmp     [rsp+330h+var_2EF], sil
0x140040c38  jz      short loc_140040C3F
0x140040c3a  test    r15b, r15b
0x140040c3d  jz      short loc_140040C9D
0x140040c3f  test    r12b, r12b
0x140040c42  jnz     short loc_140040C98
0x140040c44  mov     rcx, cs:WPP_GLOBAL_Control
0x140040c4b  lea     rax, WPP_GLOBAL_Control
0x140040c52  cmp     rcx, rax
0x140040c55  jz      short loc_140040C89
0x140040c57  test    byte ptr [rcx+1Ch], 2
0x140040c5b  jz      short loc_140040C89
0x140040c5d  cmp     byte ptr [rcx+19h], 5
0x140040c61  jb      short loc_140040C89
0x140040c63  mov     edx, 0Dh
0x140040c68  mov     [rsp+330h+lpClass], rbx; __int64
0x140040c6d  lea     rax, [rbp+230h+Name]
0x140040c71  mov     [rsp+330h+lpReserved], rax; __int64
0x140040c76  mov     r9, r14
0x140040c79  lea     r8, WPP_03e2d22dd8b23a87589ec6c69d825632_Traceguids
0x140040c80  mov     rcx, [rcx+10h]; LoggerHandle
0x140040c84  call    WPP_SF_SSS
0x140040c89  cmp     [rsp+330h+var_2EC], 1
0x140040c8e  setz    al
0x140040c91  xor     edx, edx
0x140040c93  jmp     loc_140040D2F
0x140040c98  test    r15b, r15b
0x140040c9b  jnz     short loc_140040CF9
0x140040c9d  test    r12b, r12b
0x140040ca0  jz      short loc_140040CF9
0x140040ca2  mov     rcx, cs:WPP_GLOBAL_Control
0x140040ca9  lea     r14, WPP_GLOBAL_Control
0x140040cb0  cmp     rcx, r14
0x140040cb3  jz      short loc_140040CD9
0x140040cb5  test    byte ptr [rcx+1Ch], 2
0x140040cb9  jz      short loc_140040CD9
0x140040cbb  cmp     byte ptr [rcx+19h], 5
0x140040cbf  jb      short loc_140040CD9
0x140040cc1  mov     edx, 0Eh
0x140040cc6  mov     r9, rdi
0x140040cc9  lea     r8, WPP_03e2d22dd8b23a87589ec6c69d825632_Traceguids
0x140040cd0  mov     rcx, [rcx+10h]
0x140040cd4  call    WPP_SF_S
0x140040cd9  mov     byte ptr [rsp+330h+lpClass], sil
0x140040cde  mov     [rsp+330h+lpReserved], rsi
0x140040ce3  lea     r9, [rbp+230h+Name]
0x140040ce7  mov     r8, rdi
0x140040cea  mov     edx, 1
0x140040cef  mov     rcx, r13
0x140040cf2  call    ?_OnLibraryEvent@CHMESharedLibraryMonitor@@IEAAJW4HMELibraryEvents@1@PEBG11_N@Z; CHMESharedLibraryMonitor::_OnLibraryEvent(CHMESharedLibraryMonitor::HMELibraryEvents,ushort const *,ushort const *,ushort const *,bool)
0x140040cf7  jmp     short loc_140040D4E
0x140040cf9  test    al, al
0x140040cfb  jz      short loc_140040D22
0x140040cfd  cmp     [rsp+330h+var_2EC], 1
0x140040d02  setz    al
0x140040d05  mov     byte ptr [rsp+330h+lpClass], al
0x140040d09  mov     [rsp+330h+lpReserved], rbx
0x140040d0e  lea     r9, [rbp+230h+Name]
0x140040d12  mov     r8, r14
0x140040d15  mov     edx, 2
0x140040d1a  mov     rcx, r13
0x140040d1d  call    ?_OnLibraryEvent@CHMESharedLibraryMonitor@@IEAAJW4HMELibraryEvents@1@PEBG11_N@Z; CHMESharedLibraryMonitor::_OnLibraryEvent(CHMESharedLibraryMonitor::HMELibraryEvents,ushort const *,ushort const *,ushort const *,bool)
0x140040d22  cmp     [rsp+330h+var_2EC], 1
0x140040d27  setz    al
0x140040d2a  mov     edx, 3
  ... truncated ...
```
