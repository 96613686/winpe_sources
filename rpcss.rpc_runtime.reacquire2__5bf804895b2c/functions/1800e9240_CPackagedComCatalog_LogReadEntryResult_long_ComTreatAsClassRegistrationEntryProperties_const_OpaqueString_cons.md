# CPackagedComCatalog::LogReadEntryResult(long,ComTreatAsClassRegistrationEntryProperties const &,OpaqueString const &,_GUID const &,ComTreatAsClassRegistrationEntryPropertyFlags,ComTreatAsClassRegistrationEntryPropertyFlags)

- ea: `0x1800e9240`
- end: `0x1800e94dd`
- name: `?LogReadEntryResult@CPackagedComCatalog@@CAXJAEBUComTreatAsClassRegistrationEntryProperties@@AEBVOpaqueString@@AEBU_GUID@@W4ComTreatAsClassRegistrationEntryPropertyFlags@@3@Z`
- size: `669`
- prototype: `static void __high(int, const struct ComTreatAsClassRegistrationEntryProperties *, const struct OpaqueString *, const struct _GUID *, enum ComTreatAsClassRegistrationEntryPropertyFlags, enum ComTreatAsClassRegistrationEntryPropertyFlags)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009633c`
- `0x1800de408`

## callees

- `0x180013ba0`
- `0x18001a374`
- `0x180034260`
- `0x1800a543c`
- `0x1800a6c48`
- `0x1800b7ac0`
- `0x1800dabb4`
- `0x1800dac24`
- `0x1800e9240`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e92c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e92de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e92c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e92de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e92b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e92ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e937e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e9403`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e9482`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e92b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e92ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e937e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e9403`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e9482`

## string_xrefs

- `0x1800e939b`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e949e`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e9326`: `Successfully read TreatAs entry (PackageId=%S, CLSID=%ws): DisplayName=%S`
- `0x1800e938f`: `CPackagedComCatalog::LogReadEntryResult`
- `0x1800e9492`: `CPackagedComCatalog::LogReadEntryResult`
- `0x1800e94b0`: `Failure reading TreatAs entry (PackageId=%S, CLSID=%ws): %!HRESULT!`
- `0x1800e93a2`: `Missing TreatAs entry (PackageId=%S, CLSID=%ws)`
- `0x1800e9435`: `Corrupt TreatAs entry (PackageId=%S, CLSID=%ws): Missing properties %#x, invalid properties %#x`

## pseudocode

```c
void __fastcall CPackagedComCatalog::LogReadEntryResult(
        int a1,
        __int64 a2,
        HSTRING *a3,
        const struct _GUID *a4,
        int a5,
        int a6)
{
  __int64 v9; // r8
  HSTRING *ValueOrDefault; // rax
  PCWSTR v11; // rdi
  CGuidStr *v12; // rbx
  PCWSTR v13; // rax
  int v14; // edx
  int v15; // ecx
  CGuidStr *v16; // rbx
  PCWSTR StringRawBuffer; // rax
  CGuidStr *v18; // rbx
  PCWSTR v19; // rax
  int v20; // r9d
  CGuidStr *v21; // rbx
  PCWSTR v22; // rax
  int v23; // r9d
  HSTRING string; // [rsp+50h] [rbp-88h] BYREF
  HSTRING v25; // [rsp+58h] [rbp-80h] BYREF
  _BYTE v26[80]; // [rsp+60h] [rbp-78h] BYREF

  if ( a1 < 0 )
  {
    if ( a1 == -2147024894 )
    {
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v16 = CGuidStr::CGuidStr((CGuidStr *)v26, a4);
        StringRawBuffer = WindowsGetStringRawBuffer(*a3, 0);
        ComTraceMessageT<unsigned short const *,unsigned short *>(
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (unsigned int)"CPackagedComCatalog::LogReadEntryResult",
          3705,
          0,
          (__int64)L"Missing TreatAs entry (PackageId=%S, CLSID=%ws)",
          StringRawBuffer,
          v16);
      }
    }
    else if ( a1 == -2147024883 )
    {
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v18 = CGuidStr::CGuidStr((CGuidStr *)v26, a4);
        v19 = WindowsGetStringRawBuffer(*a3, 0);
        ComTraceMessageT<unsigned short const *,unsigned short *,unsigned int,unsigned int>(
          a6,
          a5,
          3712,
          v20,
          (__int64)L"Corrupt TreatAs entry (PackageId=%S, CLSID=%ws): Missing properties %#x, invalid properties %#x",
          v19,
          v18,
          a5,
          a6);
      }
    }
    else if ( a1 != -2147024637 && (dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
    {
      v21 = CGuidStr::CGuidStr((CGuidStr *)v26, a4);
      v22 = WindowsGetStringRawBuffer(*a3, 0);
      ComTraceMessageT<unsigned short *,unsigned short const *,long>(
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (unsigned int)"CPackagedComCatalog::LogReadEntryResult",
        3717,
        v23,
        (__int64)L"Failure reading TreatAs entry (PackageId=%S, CLSID=%ws): %!HRESULT!",
        v22,
        v21,
        a1);
    }
  }
  else if ( gfEnableTracing )
  {
    if ( (unsigned __int8)IsWppLevelEnabled(4) )
    {
      v25 = 0;
      ValueOrDefault = (HSTRING *)Optional<OpaqueString>::GetValueOrDefault(v9 + 16, &string, &v25);
      v11 = WindowsGetStringRawBuffer(*ValueOrDefault, 0);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v25);
      v12 = CGuidStr::CGuidStr((CGuidStr *)v26, a4);
      v13 = WindowsGetStringRawBuffer(*a3, 0);
      ComTraceMessageT<unsigned short const *,unsigned short *,unsigned short const *>(
        v15,
        v14,
        3700,
        4,
        (__int64)L"Successfully read TreatAs entry (PackageId=%S, CLSID=%ws): DisplayName=%S",
        v13,
        v12,
        v11);
    }
  }
}

```

## disassembly

```asm
0x1800e9240  push    rbx
0x1800e9242  push    rsi
0x1800e9243  push    rdi
0x1800e9244  sub     rsp, 0C0h
0x1800e924b  mov     rax, cs:__security_cookie
0x1800e9252  xor     rax, rsp
0x1800e9255  mov     [rsp+0D8h+var_28], rax
0x1800e925d  mov     rsi, r8
0x1800e9260  mov     r8, rdx
0x1800e9263  mov     rbx, r9
0x1800e9266  mov     edi, ecx
0x1800e9268  test    ecx, ecx
0x1800e926a  js      loc_1800E933C
0x1800e9270  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800e9277  jz      loc_1800E94C1
0x1800e927d  mov     ecx, 4
0x1800e9282  call    IsWppLevelEnabled
0x1800e9287  test    al, al
0x1800e9289  jz      loc_1800E94C1
0x1800e928f  lea     rcx, [r8+10h]
0x1800e9293  mov     [rsp+0D8h+var_80], 0
0x1800e929c  lea     r8, [rsp+0D8h+var_80]
0x1800e92a1  lea     rdx, [rsp+0D8h+string]
0x1800e92a6  call    ?GetValueOrDefault@?$Optional@VOpaqueString@@@@QEBA?AVOpaqueString@@AEBV2@@Z; Optional<OpaqueString>::GetValueOrDefault(OpaqueString const &)
0x1800e92ab  xor     edx, edx; length
0x1800e92ad  mov     rcx, [rax]; string
0x1800e92b0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e92b7  nop     dword ptr [rax+rax+00h]
0x1800e92bc  mov     rcx, [rsp+0D8h+string]; string
0x1800e92c1  mov     rdi, rax
0x1800e92c4  call    cs:__imp_WindowsDeleteString
0x1800e92cb  nop     dword ptr [rax+rax+00h]
0x1800e92d0  mov     rcx, [rsp+0D8h+var_80]; string
0x1800e92d5  mov     [rsp+0D8h+string], 0
0x1800e92de  call    cs:__imp_WindowsDeleteString
0x1800e92e5  nop     dword ptr [rax+rax+00h]
0x1800e92ea  mov     rdx, rbx; struct _GUID *
0x1800e92ed  lea     rcx, [rsp+0D8h+var_78]; this
0x1800e92f2  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800e92f7  mov     rcx, [rsi]; string
0x1800e92fa  xor     edx, edx; length
0x1800e92fc  mov     rbx, rax
0x1800e92ff  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e9306  nop     dword ptr [rax+rax+00h]
0x1800e930b  mov     [rsp+0D8h+var_A0], rdi
0x1800e9310  mov     r9d, 4
0x1800e9316  mov     [rsp+0D8h+var_A8], rbx
0x1800e931b  mov     r8d, 0E74h
0x1800e9321  mov     [rsp+0D8h+var_B0], rax
0x1800e9326  lea     rax, aSuccessfullyRe_4; "Successfully read TreatAs entry (Packag"...
0x1800e932d  mov     [rsp+0D8h+var_B8], rax
0x1800e9332  call    ??$ComTraceMessageT@PEBGPEAGPEBG@@YAXPEBD0HW4TraceLevel@@PEBG2PEAG2@Z; ComTraceMessageT<ushort const *,ushort *,ushort const *>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ushort *,ushort const *)
0x1800e9337  jmp     loc_1800E94C1
0x1800e933c  cmp     edi, 80070002h
0x1800e9342  jnz     short loc_1800E93C1
0x1800e9344  mov     eax, cs:dword_1801574B8
0x1800e934a  test    eax, eax
0x1800e934c  jnz     short loc_1800E9369
0x1800e934e  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800e9354  jz      loc_1800E94C1
0x1800e935a  xor     ecx, ecx
0x1800e935c  call    IsWppLevelEnabled
0x1800e9361  test    al, al
0x1800e9363  jz      loc_1800E94C1
0x1800e9369  mov     rdx, rbx; struct _GUID *
0x1800e936c  lea     rcx, [rsp+0D8h+var_78]; this
0x1800e9371  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800e9376  mov     rcx, [rsi]; string
0x1800e9379  xor     edx, edx; length
0x1800e937b  mov     rbx, rax
0x1800e937e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e9385  nop     dword ptr [rax+rax+00h]
0x1800e938a  mov     [rsp+0D8h+var_A8], rbx
0x1800e938f  lea     rdx, aCpackagedcomca_5; "CPackagedComCatalog::LogReadEntryResult"
0x1800e9396  mov     [rsp+0D8h+var_B0], rax
0x1800e939b  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e93a2  lea     rax, aMissingTreatas; "Missing TreatAs entry (PackageId=%S, CL"...
0x1800e93a9  xor     r9d, r9d
0x1800e93ac  mov     r8d, 0E79h
0x1800e93b2  mov     [rsp+0D8h+var_B8], rax
0x1800e93b7  call    ??$ComTraceMessageT@PEBGPEAG@@YAXPEBD0HW4TraceLevel@@PEBG2PEAG@Z; ComTraceMessageT<ushort const *,ushort *>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ushort *)
0x1800e93bc  jmp     loc_1800E94C1
0x1800e93c1  cmp     edi, 8007000Dh
0x1800e93c7  jnz     short loc_1800E9448
0x1800e93c9  mov     eax, cs:dword_1801574B8
0x1800e93cf  test    eax, eax
0x1800e93d1  jnz     short loc_1800E93EE
0x1800e93d3  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800e93d9  jz      loc_1800E94C1
0x1800e93df  xor     ecx, ecx
0x1800e93e1  call    IsWppLevelEnabled
0x1800e93e6  test    al, al
0x1800e93e8  jz      loc_1800E94C1
0x1800e93ee  mov     rdx, rbx; struct _GUID *
0x1800e93f1  lea     rcx, [rsp+0D8h+var_78]; this
0x1800e93f6  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800e93fb  mov     rcx, [rsi]; string
0x1800e93fe  xor     edx, edx; length
0x1800e9400  mov     rbx, rax
0x1800e9403  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e940a  nop     dword ptr [rax+rax+00h]
0x1800e940f  mov     ecx, [rsp+0D8h+arg_28]
0x1800e9416  mov     r8d, 0E80h
0x1800e941c  mov     edx, [rsp+0D8h+arg_20]
0x1800e9423  mov     [rsp+0D8h+var_98], ecx
0x1800e9427  mov     dword ptr [rsp+0D8h+var_A0], edx
0x1800e942b  mov     [rsp+0D8h+var_A8], rbx
0x1800e9430  mov     [rsp+0D8h+var_B0], rax
0x1800e9435  lea     rax, aCorruptTreatas; "Corrupt TreatAs entry (PackageId=%S, CL"...
0x1800e943c  mov     [rsp+0D8h+var_B8], rax
0x1800e9441  call    ??$ComTraceMessageT@PEBGPEAGII@@YAXPEBD0HW4TraceLevel@@PEBG2PEAGII@Z; ComTraceMessageT<ushort const *,ushort *,uint,uint>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ushort *,uint,uint)
0x1800e9446  jmp     short loc_1800E94C1
0x1800e9448  cmp     edi, 80070103h
0x1800e944e  jz      short loc_1800E94C1
0x1800e9450  mov     eax, cs:dword_1801574B8
0x1800e9456  test    eax, eax
0x1800e9458  jnz     short loc_1800E946D
0x1800e945a  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800e9460  jz      short loc_1800E94C1
0x1800e9462  xor     ecx, ecx
0x1800e9464  call    IsWppLevelEnabled
0x1800e9469  test    al, al
0x1800e946b  jz      short loc_1800E94C1
0x1800e946d  mov     rdx, rbx; struct _GUID *
0x1800e9470  lea     rcx, [rsp+0D8h+var_78]; this
0x1800e9475  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800e947a  mov     rcx, [rsi]; string
0x1800e947d  xor     edx, edx; length
0x1800e947f  mov     rbx, rax
0x1800e9482  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e9489  nop     dword ptr [rax+rax+00h]
0x1800e948e  mov     dword ptr [rsp+0D8h+var_A0], edi
0x1800e9492  lea     rdx, aCpackagedcomca_5; "CPackagedComCatalog::LogReadEntryResult"
0x1800e9499  mov     [rsp+0D8h+var_A8], rbx
0x1800e949e  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e94a5  mov     [rsp+0D8h+var_B0], rax
0x1800e94aa  mov     r8d, 0E85h
0x1800e94b0  lea     rax, aFailureReading_1; "Failure reading TreatAs entry (PackageI"...
0x1800e94b7  mov     [rsp+0D8h+var_B8], rax
0x1800e94bc  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x1800e94c1  mov     rcx, [rsp+0D8h+var_28]
0x1800e94c9  xor     rcx, rsp; StackCookie
0x1800e94cc  call    __security_check_cookie
0x1800e94d1  add     rsp, 0C0h
0x1800e94d8  pop     rdi
0x1800e94d9  pop     rsi
0x1800e94da  pop     rbx
0x1800e94db  retn
```
