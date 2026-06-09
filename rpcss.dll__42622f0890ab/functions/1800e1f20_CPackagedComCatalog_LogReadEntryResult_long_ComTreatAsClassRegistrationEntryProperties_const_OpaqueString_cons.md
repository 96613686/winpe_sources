# CPackagedComCatalog::LogReadEntryResult(long,ComTreatAsClassRegistrationEntryProperties const &,OpaqueString const &,_GUID const &,ComTreatAsClassRegistrationEntryPropertyFlags,ComTreatAsClassRegistrationEntryPropertyFlags)

- ea: `0x1800e1f20`
- end: `0x1800e2192`
- name: `?LogReadEntryResult@CPackagedComCatalog@@CAXJAEBUComTreatAsClassRegistrationEntryProperties@@AEBVOpaqueString@@AEBU_GUID@@W4ComTreatAsClassRegistrationEntryPropertyFlags@@3@Z`
- size: `626`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008f084`
- `0x1800d77b0`

## callees

- `0x18000f270`
- `0x180016160`
- `0x180034540`
- `0x18009ffc0`
- `0x1800a16f4`
- `0x1800b27e0`
- `0x1800d41c0`
- `0x1800d4230`
- `0x1800e1f20`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e1f9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e1fb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e1f9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e1fb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e1f90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e1fcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e2046`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e20c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e213e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e1f90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e1fcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e2046`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e20c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e213e`

## string_xrefs

- `0x1800e205d`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e2154`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e2051`: `CPackagedComCatalog::LogReadEntryResult`
- `0x1800e2148`: `CPackagedComCatalog::LogReadEntryResult`
- `0x1800e2064`: `Missing TreatAs entry (PackageId=%S, CLSID=%ws)`
- `0x1800e1fee`: `Successfully read TreatAs entry (PackageId=%S, CLSID=%ws): DisplayName=%S`
- `0x1800e20f1`: `Corrupt TreatAs entry (PackageId=%S, CLSID=%ws): Missing properties %#x, invalid properties %#x`
- `0x1800e2166`: `Failure reading TreatAs entry (PackageId=%S, CLSID=%ws): %!HRESULT!`

## pseudocode

```c
void __fastcall CPackagedComCatalog::LogReadEntryResult(
        signed int a1,
        __int64 a2,
        HSTRING *a3,
        const struct _GUID *a4,
        unsigned int a5,
        unsigned int a6)
{
  __int64 v9; // r8
  HSTRING *ValueOrDefault; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  CGuidStr *v13; // rbx
  PCWSTR StringRawBuffer; // rax
  CGuidStr *v15; // rbx
  PCWSTR v16; // rax
  int v17; // r9d
  HSTRING string; // [rsp+50h] [rbp-88h] BYREF
  HSTRING v19; // [rsp+58h] [rbp-80h] BYREF
  _BYTE v20[80]; // [rsp+60h] [rbp-78h] BYREF

  if ( a1 < 0 )
  {
    if ( a1 == -2147024894 )
    {
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v13 = CGuidStr::CGuidStr((CGuidStr *)v20, a4);
        StringRawBuffer = WindowsGetStringRawBuffer(*a3, 0);
        ComTraceMessageT<unsigned short const *,unsigned short *>(
          (__int64)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (__int64)"CPackagedComCatalog::LogReadEntryResult",
          0xE79u,
          0,
          (__int64)L"Missing TreatAs entry (PackageId=%S, CLSID=%ws)",
          StringRawBuffer,
          v13);
      }
    }
    else if ( a1 == -2147024883 )
    {
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        CGuidStr::CGuidStr((CGuidStr *)v20, a4);
        WindowsGetStringRawBuffer(*a3, 0);
        ComTraceMessageT<unsigned short const *,unsigned short *,unsigned int,unsigned int>(a6, a5, 0xE80u);
      }
    }
    else if ( a1 != -2147024637 && (dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
    {
      v15 = CGuidStr::CGuidStr((CGuidStr *)v20, a4);
      v16 = WindowsGetStringRawBuffer(*a3, 0);
      ComTraceMessageT<unsigned short *,unsigned short const *,long>(
        (__int64)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (__int64)"CPackagedComCatalog::LogReadEntryResult",
        0xE85u,
        v17,
        (__int64)L"Failure reading TreatAs entry (PackageId=%S, CLSID=%ws): %!HRESULT!",
        (__int64)v16,
        (__int64)v15,
        a1);
    }
  }
  else if ( gfEnableTracing )
  {
    if ( (unsigned __int8)IsWppLevelEnabled(4) )
    {
      v19 = 0;
      ValueOrDefault = (HSTRING *)Optional<OpaqueString>::GetValueOrDefault(v9 + 16, &string, &v19);
      WindowsGetStringRawBuffer(*ValueOrDefault, 0);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v19);
      CGuidStr::CGuidStr((CGuidStr *)v20, a4);
      WindowsGetStringRawBuffer(*a3, 0);
      ComTraceMessageT<unsigned short const *,unsigned short *,unsigned short const *>(v12, v11, 0xE74u);
    }
  }
}

```

## disassembly

```asm
0x1800e1f20  push    rbx
0x1800e1f22  push    rsi
0x1800e1f23  push    rdi
0x1800e1f24  sub     rsp, 0C0h
0x1800e1f2b  mov     rax, cs:__security_cookie
0x1800e1f32  xor     rax, rsp
0x1800e1f35  mov     [rsp+0D8h+var_28], rax
0x1800e1f3d  mov     rsi, r8
0x1800e1f40  mov     r8, rdx
0x1800e1f43  mov     rbx, r9
0x1800e1f46  mov     edi, ecx
0x1800e1f48  test    ecx, ecx
0x1800e1f4a  js      loc_1800E2004
0x1800e1f50  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800e1f57  jz      loc_1800E2177
0x1800e1f5d  mov     ecx, 4
0x1800e1f62  call    IsWppLevelEnabled
0x1800e1f67  test    al, al
0x1800e1f69  jz      loc_1800E2177
0x1800e1f6f  lea     rcx, [r8+10h]
0x1800e1f73  mov     [rsp+0D8h+var_80], 0
0x1800e1f7c  lea     r8, [rsp+0D8h+var_80]
0x1800e1f81  lea     rdx, [rsp+0D8h+string]
0x1800e1f86  call    ?GetValueOrDefault@?$Optional@VOpaqueString@@@@QEBA?AVOpaqueString@@AEBV2@@Z; Optional<OpaqueString>::GetValueOrDefault(OpaqueString const &)
0x1800e1f8b  xor     edx, edx; length
0x1800e1f8d  mov     rcx, [rax]; string
0x1800e1f90  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e1f96  mov     rcx, [rsp+0D8h+string]; string
0x1800e1f9b  mov     rdi, rax
0x1800e1f9e  call    cs:__imp_WindowsDeleteString
0x1800e1fa4  mov     rcx, [rsp+0D8h+var_80]; string
0x1800e1fa9  mov     [rsp+0D8h+string], 0
0x1800e1fb2  call    cs:__imp_WindowsDeleteString
0x1800e1fb8  mov     rdx, rbx; struct _GUID *
0x1800e1fbb  lea     rcx, [rsp+0D8h+var_78]; this
0x1800e1fc0  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800e1fc5  mov     rcx, [rsi]; string
0x1800e1fc8  xor     edx, edx; length
0x1800e1fca  mov     rbx, rax
0x1800e1fcd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e1fd3  mov     [rsp+0D8h+var_A0], rdi
0x1800e1fd8  mov     r9d, 4
0x1800e1fde  mov     [rsp+0D8h+var_A8], rbx
0x1800e1fe3  mov     r8d, 0E74h
0x1800e1fe9  mov     [rsp+0D8h+var_B0], rax
0x1800e1fee  lea     rax, aSuccessfullyRe_4; "Successfully read TreatAs entry (Packag"...
0x1800e1ff5  mov     [rsp+0D8h+var_B8], rax
0x1800e1ffa  call    ??$ComTraceMessageT@PEBGPEAGPEBG@@YAXPEBD0HW4TraceLevel@@PEBG2PEAG2@Z; ComTraceMessageT<ushort const *,ushort *,ushort const *>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ushort *,ushort const *)
0x1800e1fff  jmp     loc_1800E2177
0x1800e2004  cmp     edi, 80070002h
0x1800e200a  jnz     short loc_1800E2083
0x1800e200c  mov     eax, cs:dword_18014E4B8
0x1800e2012  test    eax, eax
0x1800e2014  jnz     short loc_1800E2031
0x1800e2016  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800e201c  jz      loc_1800E2177
0x1800e2022  xor     ecx, ecx
0x1800e2024  call    IsWppLevelEnabled
0x1800e2029  test    al, al
0x1800e202b  jz      loc_1800E2177
0x1800e2031  mov     rdx, rbx; struct _GUID *
0x1800e2034  lea     rcx, [rsp+0D8h+var_78]; this
0x1800e2039  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800e203e  mov     rcx, [rsi]; string
0x1800e2041  xor     edx, edx; length
0x1800e2043  mov     rbx, rax
0x1800e2046  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e204c  mov     [rsp+0D8h+var_A8], rbx
0x1800e2051  lea     rdx, aCpackagedcomca_5; "CPackagedComCatalog::LogReadEntryResult"
0x1800e2058  mov     [rsp+0D8h+var_B0], rax
0x1800e205d  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e2064  lea     rax, aMissingTreatas; "Missing TreatAs entry (PackageId=%S, CL"...
0x1800e206b  xor     r9d, r9d
0x1800e206e  mov     r8d, 0E79h
0x1800e2074  mov     [rsp+0D8h+var_B8], rax
0x1800e2079  call    ??$ComTraceMessageT@PEBGPEAG@@YAXPEBD0HW4TraceLevel@@PEBG2PEAG@Z; ComTraceMessageT<ushort const *,ushort *>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ushort *)
0x1800e207e  jmp     loc_1800E2177
0x1800e2083  cmp     edi, 8007000Dh
0x1800e2089  jnz     short loc_1800E2104
0x1800e208b  mov     eax, cs:dword_18014E4B8
0x1800e2091  test    eax, eax
0x1800e2093  jnz     short loc_1800E20B0
0x1800e2095  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800e209b  jz      loc_1800E2177
0x1800e20a1  xor     ecx, ecx
0x1800e20a3  call    IsWppLevelEnabled
0x1800e20a8  test    al, al
0x1800e20aa  jz      loc_1800E2177
0x1800e20b0  mov     rdx, rbx; struct _GUID *
0x1800e20b3  lea     rcx, [rsp+0D8h+var_78]; this
0x1800e20b8  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800e20bd  mov     rcx, [rsi]; string
0x1800e20c0  xor     edx, edx; length
0x1800e20c2  mov     rbx, rax
0x1800e20c5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e20cb  mov     ecx, [rsp+0D8h+arg_28]
0x1800e20d2  mov     r8d, 0E80h
0x1800e20d8  mov     edx, [rsp+0D8h+arg_20]
0x1800e20df  mov     [rsp+0D8h+var_98], ecx
0x1800e20e3  mov     dword ptr [rsp+0D8h+var_A0], edx
0x1800e20e7  mov     [rsp+0D8h+var_A8], rbx
0x1800e20ec  mov     [rsp+0D8h+var_B0], rax
0x1800e20f1  lea     rax, aCorruptTreatas; "Corrupt TreatAs entry (PackageId=%S, CL"...
0x1800e20f8  mov     [rsp+0D8h+var_B8], rax
0x1800e20fd  call    ??$ComTraceMessageT@PEBGPEAGII@@YAXPEBD0HW4TraceLevel@@PEBG2PEAGII@Z; ComTraceMessageT<ushort const *,ushort *,uint,uint>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ushort *,uint,uint)
0x1800e2102  jmp     short loc_1800E2177
0x1800e2104  cmp     edi, 80070103h
0x1800e210a  jz      short loc_1800E2177
0x1800e210c  mov     eax, cs:dword_18014E4B8
0x1800e2112  test    eax, eax
0x1800e2114  jnz     short loc_1800E2129
0x1800e2116  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800e211c  jz      short loc_1800E2177
0x1800e211e  xor     ecx, ecx
0x1800e2120  call    IsWppLevelEnabled
0x1800e2125  test    al, al
0x1800e2127  jz      short loc_1800E2177
0x1800e2129  mov     rdx, rbx; struct _GUID *
0x1800e212c  lea     rcx, [rsp+0D8h+var_78]; this
0x1800e2131  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800e2136  mov     rcx, [rsi]; string
0x1800e2139  xor     edx, edx; length
0x1800e213b  mov     rbx, rax
0x1800e213e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e2144  mov     dword ptr [rsp+0D8h+var_A0], edi
0x1800e2148  lea     rdx, aCpackagedcomca_5; "CPackagedComCatalog::LogReadEntryResult"
0x1800e214f  mov     [rsp+0D8h+var_A8], rbx
0x1800e2154  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e215b  mov     [rsp+0D8h+var_B0], rax
0x1800e2160  mov     r8d, 0E85h
0x1800e2166  lea     rax, aFailureReading_1; "Failure reading TreatAs entry (PackageI"...
0x1800e216d  mov     [rsp+0D8h+var_B8], rax
0x1800e2172  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x1800e2177  mov     rcx, [rsp+0D8h+var_28]
0x1800e217f  xor     rcx, rsp; StackCookie
0x1800e2182  call    __security_check_cookie
0x1800e2187  add     rsp, 0C0h
0x1800e218e  pop     rdi
0x1800e218f  pop     rsi
0x1800e2190  pop     rbx
0x1800e2191  retn
```
