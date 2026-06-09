# Windows::System::Internal::Implementation::RegUtil::ReadValue<Windows::Foundation::IPropertyValue *>(HKEY__ *,ushort const *,Windows::Foundation::IPropertyValue * *)

- ea: `0x18004c06c`
- end: `0x18004c2f0`
- name: `??$ReadValue@PEAUIPropertyValue@Foundation@Windows@@@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAPEAUIPropertyValue@Foundation@4@@Z`
- size: `644`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004f770`

## callees

- `0x18000acdc`
- `0x18000ce48`
- `0x180040bec`
- `0x18004b93c`
- `0x18004bb04`
- `0x18004c06c`
- `0x18004c2f8`
- `0x18004df20`
- `0x18004e508`
- `0x1800503f4`
- `0x1800cd938`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c224`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c29c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c224`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c29c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004c0e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004c0e1`

## string_xrefs

- `0x18004c094`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004c0f3`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004c12a`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004c160`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004c19a`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004c1cf`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004c208`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004c24f`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004c285`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004c2bb`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::System::Internal::Implementation::RegUtil::ReadValue<Windows::Foundation::IPropertyValue *>(
        HKEY hKey,
        LPCWSTR lpValueName,
        _QWORD *a3)
{
  unsigned int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  const char *v14; // r9
  __int64 result; // rax
  int lpData; // [rsp+20h] [rbp-38h]
  unsigned int lpDataa; // [rsp+20h] [rbp-38h]
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  __int64 v19; // [rsp+38h] [rbp-20h] BYREF
  HSTRING string; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v21[2]; // [rsp+48h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD Type; // [rsp+70h] [rbp+18h] BYREF
  unsigned int Data; // [rsp+78h] [rbp+20h] BYREF

  try
  {
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
        (const char *)0x80004003LL,
        lpData);
    *a3 = 0;
    cbData = 0;
    Type = 0;
    v19 = 0;
    v6 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
    if ( v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x72,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
        (const char *)v6,
        lpDataa);
    switch ( Type )
    {
      case 1u:
        string = 0;
        WindowsDeleteString(0);
        string = 0;
        v11 = Windows::System::Internal::Implementation::RegUtil::ReadValue<HSTRING__ *>(hKey, lpValueName, &string);
        if ( v11 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7E,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
            (const char *)(unsigned int)v11,
            lpDataa);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
        v12 = Windows::System::Internal::Implementation::ComUtils::ToInspectable<HSTRING__ *>(string, &v19);
        if ( v12 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7F,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
            (const char *)(unsigned int)v12,
            lpDataa);
        WindowsDeleteString(string);
        break;
      case 4u:
        Data = 0;
        v9 = Windows::System::Internal::Implementation::RegUtil::ReadValue<unsigned long>(
               hKey,
               lpValueName,
               (LPBYTE)&Data);
        if ( v9 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x78,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
            (const char *)(unsigned int)v9,
            lpDataa);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
        v10 = Windows::System::Internal::Implementation::ComUtils::ToInspectable<unsigned long>(Data, &v19);
        if ( v10 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x79,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
            (const char *)(unsigned int)v10,
            lpDataa);
        break;
      case 0xBu:
        *(_QWORD *)v21 = 0;
        v7 = Windows::System::Internal::Implementation::RegUtil::ReadValue<unsigned __int64>(
               hKey,
               lpValueName,
               (unsigned int)v21);
        if ( v7 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x84,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
            (const char *)(unsigned int)v7,
            lpDataa);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
        v8 = Windows::System::Internal::Implementation::ComUtils::ToInspectable<unsigned __int64>(*(_QWORD *)v21, &v19);
        if ( v8 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x85,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
            (const char *)(unsigned int)v8,
            lpDataa);
        break;
      default:
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x88,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
          (const char *)0x8000FFFFLL,
          lpDataa);
    }
    v13 = Microsoft::WRL::ComPtr<IInspectable>::CopyTo<Windows::Foundation::IPropertyValue>(&v19, (__int64)a3);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
        (const char *)(unsigned int)v13,
        lpDataa);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x8F,
                           (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x18004c06c  mov     [rsp+arg_0], rbx
0x18004c071  mov     [rsp+arg_8], rsi
0x18004c076  push    rdi
0x18004c077  sub     rsp, 50h
0x18004c07b  mov     rsi, r8
0x18004c07e  mov     rbx, rdx
0x18004c081  mov     rdi, rcx
0x18004c084  mov     rcx, [rsp+58h]; this
0x18004c089  test    r8, r8
0x18004c08c  jnz     short loc_18004C0A3
0x18004c08e  mov     r9d, 80004003h; char *
0x18004c094  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004c09b  lea     edx, [rsi+6Ch]; void *
0x18004c09e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c0a3  mov     qword ptr [r8], 0
0x18004c0aa  mov     [rsp+58h+cbData], 0
0x18004c0b2  mov     [rsp+58h+Type], 0
0x18004c0ba  mov     [rsp+58h+var_20], 0
0x18004c0c3  lea     rax, [rsp+58h+cbData]
0x18004c0c8  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18004c0cd  mov     [rsp+58h+lpData], 0; int
0x18004c0d6  lea     r9, [rsp+58h+Type]; lpType
0x18004c0db  xor     r8d, r8d; lpReserved
0x18004c0de  mov     rcx, rdi; hKey
0x18004c0e1  call    cs:__imp_RegQueryValueExW
0x18004c0e7  mov     rcx, [rsp+58h]; this
0x18004c0ec  test    eax, eax
0x18004c0ee  jz      short loc_18004C104
0x18004c0f0  mov     r9d, eax; char *
0x18004c0f3  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004c0fa  mov     edx, 72h ; 'r'; void *
0x18004c0ff  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004c104  mov     eax, [rsp+58h+Type]
0x18004c108  sub     eax, 1
0x18004c10b  jz      loc_18004C219
0x18004c111  sub     eax, 3
0x18004c114  jz      loc_18004C1AB
0x18004c11a  cmp     eax, 7
0x18004c11d  jz      short loc_18004C13B
0x18004c11f  mov     rcx, [rsp+58h]; this
0x18004c124  mov     r9d, 8000FFFFh; char *
0x18004c12a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004c131  mov     edx, 88h; void *
0x18004c136  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c13b  mov     qword ptr [rsp+58h+var_10], 0
0x18004c144  lea     r8, [rsp+58h+var_10]; unsigned int
0x18004c149  mov     rdx, rbx; lpValueName
0x18004c14c  mov     rcx, rdi; hKey
0x18004c14f  call    ??$ReadValue@_K@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEA_K@Z; Windows::System::Internal::Implementation::RegUtil::ReadValue<unsigned __int64>(HKEY__ *,ushort const *,unsigned __int64 *)
0x18004c154  mov     rcx, [rsp+58h]; this
0x18004c159  test    eax, eax
0x18004c15b  jns     short loc_18004C171
0x18004c15d  mov     r9d, eax; char *
0x18004c160  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004c167  mov     edx, 84h; void *
0x18004c16c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c171  lea     rcx, [rsp+58h+var_20]
0x18004c176  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c17b  lea     rdx, [rsp+58h+var_20]
0x18004c180  mov     rcx, qword ptr [rsp+58h+var_10]
0x18004c185  call    ??$ToInspectable@_K@ComUtils@Implementation@Internal@System@Windows@@SAJ_KPEAPEAUIInspectable@@@Z; Windows::System::Internal::Implementation::ComUtils::ToInspectable<unsigned __int64>(unsigned __int64,IInspectable * *)
0x18004c18a  mov     rcx, [rsp+58h]; this
0x18004c18f  test    eax, eax
0x18004c191  jns     loc_18004C2A2
0x18004c197  mov     r9d, eax; char *
0x18004c19a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004c1a1  mov     edx, 85h; void *
0x18004c1a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c1ab  mov     [rsp+58h+Data], 0
0x18004c1b3  lea     r8, [rsp+58h+Data]; lpData
0x18004c1b8  mov     rdx, rbx; lpValueName
0x18004c1bb  mov     rcx, rdi; hKey
0x18004c1be  call    ??$ReadValue@K@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAK@Z; Windows::System::Internal::Implementation::RegUtil::ReadValue<ulong>(HKEY__ *,ushort const *,ulong *)
0x18004c1c3  mov     rcx, [rsp+58h]; this
0x18004c1c8  test    eax, eax
0x18004c1ca  jns     short loc_18004C1E0
0x18004c1cc  mov     r9d, eax; char *
0x18004c1cf  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004c1d6  mov     edx, 78h ; 'x'; void *
0x18004c1db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c1e0  lea     rcx, [rsp+58h+var_20]
0x18004c1e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c1ea  lea     rdx, [rsp+58h+var_20]
0x18004c1ef  mov     ecx, [rsp+58h+Data]
0x18004c1f3  call    ??$ToInspectable@K@ComUtils@Implementation@Internal@System@Windows@@SAJKPEAPEAUIInspectable@@@Z; Windows::System::Internal::Implementation::ComUtils::ToInspectable<ulong>(ulong,IInspectable * *)
0x18004c1f8  mov     rcx, [rsp+58h]; this
0x18004c1fd  test    eax, eax
0x18004c1ff  jns     loc_18004C2A2
0x18004c205  mov     r9d, eax; char *
0x18004c208  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004c20f  mov     edx, 79h ; 'y'; void *
0x18004c214  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c219  mov     [rsp+58h+string], 0
0x18004c222  xor     ecx, ecx; string
0x18004c224  call    cs:__imp_WindowsDeleteString
0x18004c22a  mov     [rsp+58h+string], 0
0x18004c233  lea     r8, [rsp+58h+string]; string
0x18004c238  mov     rdx, rbx; lpValueName
0x18004c23b  mov     rcx, rdi; hKey
0x18004c23e  call    ??$ReadValue@PEAUHSTRING__@@@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAPEAUHSTRING__@@@Z; Windows::System::Internal::Implementation::RegUtil::ReadValue<HSTRING__ *>(HKEY__ *,ushort const *,HSTRING__ * *)
0x18004c243  mov     rcx, [rsp+58h]; this
0x18004c248  test    eax, eax
0x18004c24a  jns     short loc_18004C260
0x18004c24c  mov     r9d, eax; char *
0x18004c24f  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004c256  mov     edx, 7Eh ; '~'; void *
0x18004c25b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c260  lea     rcx, [rsp+58h+var_20]
0x18004c265  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c26a  lea     rdx, [rsp+58h+var_20]
0x18004c26f  mov     rcx, [rsp+58h+string]
0x18004c274  call    ??$ToInspectable@PEAUHSTRING__@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; Windows::System::Internal::Implementation::ComUtils::ToInspectable<HSTRING__ *>(HSTRING__ *,IInspectable * *)
0x18004c279  mov     rcx, [rsp+58h]; this
0x18004c27e  test    eax, eax
0x18004c280  jns     short loc_18004C297
0x18004c282  mov     r9d, eax; char *
0x18004c285  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004c28c  mov     edx, 7Fh; void *
0x18004c291  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c297  mov     rcx, [rsp+58h+string]; string
0x18004c29c  call    cs:__imp_WindowsDeleteString
0x18004c2a2  mov     rdx, rsi
0x18004c2a5  lea     rcx, [rsp+58h+var_20]
0x18004c2aa  call    ??$CopyTo@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJPEAPEAUIPropertyValue@Foundation@Windows@@@Z; Microsoft::WRL::ComPtr<IInspectable>::CopyTo<Windows::Foundation::IPropertyValue>(Windows::Foundation::IPropertyValue * *)
0x18004c2af  mov     rcx, [rsp+58h]; this
0x18004c2b4  test    eax, eax
0x18004c2b6  jns     short loc_18004C2CD
0x18004c2b8  mov     r9d, eax; char *
0x18004c2bb  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004c2c2  mov     edx, 8Bh; void *
0x18004c2c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c2cd  lea     rcx, [rsp+58h+var_20]
0x18004c2d2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c2d7  xor     eax, eax
0x18004c2d9  jmp     short loc_18004C2DF
0x18004c2db  mov     eax, [rsp+58h+Type]
0x18004c2df  mov     rbx, [rsp+58h+arg_0]
0x18004c2e4  mov     rsi, [rsp+58h+arg_8]
0x18004c2e9  add     rsp, 50h
0x18004c2ed  pop     rdi
0x18004c2ee  retn
```
