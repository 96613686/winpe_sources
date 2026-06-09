# UrlUtilities::GetMarket(IWinApiLite *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18004eb64`
- end: `0x18004ee5c`
- name: `?GetMarket@UrlUtilities@@SAJPEAVIWinApiLite@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033a70`
- `0x18004e6b0`

## callees

- `0x1800034c0`
- `0x180003990`
- `0x180003cb0`
- `0x180004824`
- `0x180004910`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x180010b80`
- `0x1800113e8`
- `0x18004eb64`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004edc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004edc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ed69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004edb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004eddd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ed69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004edb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004eddd`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18004ec26`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18004ec26`
- `Bcp47Langs!GetUserLanguages` at `0x18004ed7f`
- `Bcp47Langs!GetUserLanguages` at `0x18004ed7f`

## string_xrefs

- `0x18004ec9a`: `Failure - GetThreadPreferredUILanguages, HRESULT: 0x%08X\n`
- `0x18004ed20`: `Failure - GetThreadPreferredUILanguages, HRESULT: 0x%08X\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall UrlUtilities::GetMarket(__int64 *a1, _QWORD *a2)
{
  int v4; // eax
  __int64 v5; // rdx
  signed int v6; // eax
  unsigned int (__fastcall *v7)(__int64 *, __int64, int *, __int64, unsigned int *); // rsi
  __int64 v8; // rax
  signed int v9; // eax
  int UserLanguages; // eax
  PCWSTR StringRawBuffer; // rax
  unsigned int v12; // ebx
  char *v14; // [rsp+20h] [rbp-A8h]
  char *v15; // [rsp+20h] [rbp-A8h]
  char *v16; // [rsp+20h] [rbp-A8h]
  int v17; // [rsp+30h] [rbp-98h] BYREF
  int v18; // [rsp+34h] [rbp-94h] BYREF
  HSTRING string; // [rsp+38h] [rbp-90h] BYREF
  int *v20[2]; // [rsp+40h] [rbp-88h] BYREF
  int *v21[4]; // [rsp+50h] [rbp-78h] BYREF
  _QWORD v22[11]; // [rsp+70h] [rbp-58h] BYREF
  int v23; // [rsp+E0h] [rbp+18h] BYREF
  unsigned int v24; // [rsp+E8h] [rbp+20h] BYREF

  v18 = 0;
  v24 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v20);
  v23 = 0;
  v17 = 0;
  v22[0] = "UrlUtilities::GetMarket";
  v22[1] = &v23;
  v22[2] = 0;
  v22[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\urlutilities.cpp",
    "UrlUtilities::GetMarket",
    (const char *)0x3B,
    0,
    (const unsigned __int16 *)v14);
  ErrorVerifier::ErrorVerifier((ErrorVerifier *)v21, "UrlUtilities::GetMarket", &v23, 0xAu, &qword_180072D98);
  RtlGetDeviceFamilyInfoEnum(0, &v17, 0);
  if ( v17 == 5 || (unsigned int)(v17 - 11) <= 1 )
  {
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    UserLanguages = GetUserLanguages(0, &string);
    v23 = UserLanguages;
    if ( UserLanguages < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\urlutilities.cpp",
        "UrlUtilities::GetMarket",
        0x49u,
        UserLanguages,
        "hr = GetUserLanguages(L'\\0', langList.GetAddressOf())");
      WindowsDeleteString(string);
      goto LABEL_16;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    ATL::CSimpleStringT<unsigned short,0>::SetString(a2, StringRawBuffer);
    WindowsDeleteString(string);
LABEL_15:
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\urlutilities.cpp",
      0x6Fu,
      L"Found user market of '%ls'.",
      *a2);
    goto LABEL_16;
  }
  v15 = (char *)&v24;
  v4 = (*(__int64 (__fastcall **)(__int64 *, __int64, int *))(*a1 + 136))(a1, 8, &v18);
  v5 = *a1;
  if ( !v4 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64 *))(v5 + 120))(a1);
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    v23 = v6;
    LODWORD(v15) = v6;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\urlutilities.cpp",
      0x53u,
      L"Failure - GetThreadPreferredUILanguages, HRESULT: 0x%08X\n",
      v15);
    goto LABEL_16;
  }
  v7 = *(unsigned int (__fastcall **)(__int64 *, __int64, int *, __int64, unsigned int *))(v5 + 136);
  v8 = ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(v20, v24);
  if ( v7(a1, 8, &v18, v8, &v24) )
  {
    ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(v20, 0xFFFFFFFFLL);
    ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v20[0]);
    goto LABEL_15;
  }
  v9 = (*(__int64 (__fastcall **)(__int64 *))(*a1 + 120))(a1);
  if ( v9 > 0 )
    v9 = (unsigned __int16)v9 | 0x80070000;
  v23 = v9;
  LODWORD(v16) = v9;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\urlutilities.cpp",
    0x5Du,
    L"Failure - GetThreadPreferredUILanguages, HRESULT: 0x%08X\n",
    v16);
LABEL_16:
  v12 = v23;
  ErrorVerifier::CheckAgainstList((const char *)v21[3], *v21[2], (unsigned __int64)v21[1], v21[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>(v22);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v20);
  return v12;
}

```

## disassembly

```asm
0x18004eb64  mov     rax, rsp
0x18004eb67  mov     [rax+8], rbx
0x18004eb6b  push    rsi
0x18004eb6c  push    rdi
0x18004eb6d  push    r15
0x18004eb6f  sub     rsp, 0B0h
0x18004eb76  mov     rdi, rdx
0x18004eb79  mov     rbx, rcx
0x18004eb7c  mov     [rsp+0C8h+var_94], 0
0x18004eb84  mov     dword ptr [rax+20h], 0
0x18004eb8b  lea     rcx, [rsp+0C8h+var_88]; void *
0x18004eb90  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004eb95  nop
0x18004eb96  mov     [rsp+0C8h+arg_10], 0
0x18004eba1  mov     [rsp+0C8h+var_98], 0
0x18004eba9  lea     rsi, aUrlutilitiesGe; "UrlUtilities::GetMarket"
0x18004ebb0  mov     [rsp+0C8h+var_58], rsi
0x18004ebb5  lea     rax, [rsp+0C8h+arg_10]
0x18004ebbd  mov     [rsp+0C8h+var_50], rax
0x18004ebc2  mov     [rsp+0C8h+var_48], 0
0x18004ebce  mov     [rsp+0C8h+var_40], 0
0x18004ebda  xor     r9d, r9d; unsigned int
0x18004ebdd  lea     r8d, [r9+3Bh]; char *
0x18004ebe1  mov     rdx, rsi; char *
0x18004ebe4  lea     r15, aOnecoreuapDsEx_15; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004ebeb  mov     rcx, r15; this
0x18004ebee  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18004ebf3  nop
0x18004ebf4  lea     rax, qword_180072D98
0x18004ebfb  mov     [rsp+0C8h+var_A8], rax; int *
0x18004ec00  mov     r9d, 0Ah; unsigned __int64
0x18004ec06  lea     r8, [rsp+0C8h+arg_10]; int *
0x18004ec0e  mov     rdx, rsi; char *
0x18004ec11  lea     rcx, [rsp+0C8h+var_78]; this
0x18004ec16  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x18004ec1b  nop
0x18004ec1c  xor     r8d, r8d
0x18004ec1f  lea     rdx, [rsp+0C8h+var_98]
0x18004ec24  xor     ecx, ecx
0x18004ec26  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18004ec2c  mov     eax, [rsp+0C8h+var_98]
0x18004ec30  cmp     eax, 5
0x18004ec33  jz      loc_18004ED5E
0x18004ec39  add     eax, 0FFFFFFF5h
0x18004ec3c  cmp     eax, 1
0x18004ec3f  jbe     loc_18004ED5E
0x18004ec45  mov     rax, [rbx]
0x18004ec48  lea     rcx, [rsp+0C8h+arg_18]
0x18004ec50  mov     [rsp+0C8h+var_A8], rcx
0x18004ec55  xor     r9d, r9d
0x18004ec58  lea     r8, [rsp+0C8h+var_94]
0x18004ec5d  lea     edx, [r9+8]
0x18004ec61  mov     rcx, rbx
0x18004ec64  mov     rax, [rax+88h]
0x18004ec6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec70  mov     rdx, [rbx]
0x18004ec73  test    eax, eax
0x18004ec75  jnz     short loc_18004ECB9
0x18004ec77  mov     rcx, rbx
0x18004ec7a  mov     rax, [rdx+78h]
0x18004ec7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec83  test    eax, eax
0x18004ec85  jle     short loc_18004EC8F
0x18004ec87  movzx   eax, ax
0x18004ec8a  or      eax, 80070000h
0x18004ec8f  mov     [rsp+0C8h+arg_10], eax
0x18004ec96  mov     dword ptr [rsp+0C8h+var_A8], eax
0x18004ec9a  lea     r9, aFailureGetthre; "Failure - GetThreadPreferredUILanguages"...
0x18004eca1  mov     r8d, 53h ; 'S'; unsigned int
0x18004eca7  mov     rdx, r15; char *
0x18004ecaa  lea     ecx, [r8-51h]; unsigned __int8
0x18004ecae  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004ecb3  nop
0x18004ecb4  jmp     loc_18004EE05
0x18004ecb9  mov     rsi, [rdx+88h]
0x18004ecc0  mov     edx, [rsp+0C8h+arg_18]
0x18004ecc7  lea     rcx, [rsp+0C8h+var_88]
0x18004eccc  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x18004ecd1  lea     rcx, [rsp+0C8h+arg_18]
0x18004ecd9  mov     [rsp+0C8h+var_A8], rcx
0x18004ecde  mov     r9, rax
0x18004ece1  lea     r8, [rsp+0C8h+var_94]
0x18004ece6  mov     edx, 8
0x18004eceb  mov     rcx, rbx
0x18004ecee  mov     rax, rsi
0x18004ecf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ecf6  test    eax, eax
0x18004ecf8  jnz     short loc_18004ED3F
0x18004ecfa  mov     rax, [rbx]
0x18004ecfd  mov     rcx, rbx
0x18004ed00  mov     rax, [rax+78h]
0x18004ed04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed09  test    eax, eax
0x18004ed0b  jle     short loc_18004ED15
0x18004ed0d  movzx   eax, ax
0x18004ed10  or      eax, 80070000h
0x18004ed15  mov     [rsp+0C8h+arg_10], eax
0x18004ed1c  mov     dword ptr [rsp+0C8h+var_A8], eax
0x18004ed20  lea     r9, aFailureGetthre; "Failure - GetThreadPreferredUILanguages"...
0x18004ed27  mov     r8d, 5Dh ; ']'; unsigned int
0x18004ed2d  mov     rdx, r15; char *
0x18004ed30  lea     ecx, [r8-5Bh]; unsigned __int8
0x18004ed34  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004ed39  nop
0x18004ed3a  jmp     loc_18004EE05
0x18004ed3f  or      edx, 0FFFFFFFFh
0x18004ed42  lea     rcx, [rsp+0C8h+var_88]
0x18004ed47  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18004ed4c  mov     rdx, [rsp+0C8h+var_88]
0x18004ed51  mov     rcx, rdi
0x18004ed54  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18004ed59  jmp     loc_18004EDE3
0x18004ed5e  mov     [rsp+0C8h+string], 0
0x18004ed67  xor     ecx, ecx; string
0x18004ed69  call    cs:__imp_WindowsDeleteString
0x18004ed6f  mov     [rsp+0C8h+string], 0
0x18004ed78  xor     ecx, ecx
0x18004ed7a  lea     rdx, [rsp+0C8h+string]
0x18004ed7f  call    cs:__imp_GetUserLanguages
0x18004ed85  mov     [rsp+0C8h+arg_10], eax
0x18004ed8c  test    eax, eax
0x18004ed8e  jns     short loc_18004EDBF
0x18004ed90  lea     rcx, aHrGetuserlangu; "hr = GetUserLanguages(L'\\0', langList."...
0x18004ed97  mov     [rsp+0C8h+var_A8], rcx; char *
0x18004ed9c  mov     r9d, eax; int
0x18004ed9f  mov     r8d, 49h ; 'I'; unsigned int
0x18004eda5  mov     rdx, rsi; char *
0x18004eda8  mov     rcx, r15; char *
0x18004edab  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18004edb0  nop
0x18004edb1  mov     rcx, [rsp+0C8h+string]; string
0x18004edb6  call    cs:__imp_WindowsDeleteString
0x18004edbc  nop
0x18004edbd  jmp     short loc_18004EE05
0x18004edbf  xor     edx, edx; length
0x18004edc1  mov     rcx, [rsp+0C8h+string]; string
0x18004edc6  call    cs:__imp_WindowsGetStringRawBuffer
0x18004edcc  mov     rdx, rax
0x18004edcf  mov     rcx, rdi
0x18004edd2  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18004edd7  nop
0x18004edd8  mov     rcx, [rsp+0C8h+string]; string
0x18004eddd  call    cs:__imp_WindowsDeleteString
0x18004ede3  mov     rax, [rdi]
0x18004ede6  mov     [rsp+0C8h+var_A8], rax
0x18004edeb  lea     r9, aFoundUserMarke; "Found user market of '%ls'."
0x18004edf2  mov     r8d, 6Fh ; 'o'; unsigned int
0x18004edf8  mov     rdx, r15; char *
0x18004edfb  lea     ecx, [r8-6Ah]; unsigned __int8
0x18004edff  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004ee04  nop
0x18004ee05  mov     ebx, [rsp+0C8h+arg_10]
0x18004ee0c  mov     r9, [rsp+0C8h+var_78]; int *
0x18004ee11  mov     r8, [rsp+0C8h+var_70]; unsigned __int64
0x18004ee16  mov     rdx, [rsp+0C8h+var_68]
0x18004ee1b  mov     edx, [rdx]; int
0x18004ee1d  mov     rcx, [rsp+0C8h+var_60]; char *
0x18004ee22  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x18004ee27  nop
0x18004ee28  lea     rcx, [rsp+0C8h+var_58]
0x18004ee2d  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18004ee32  nop
0x18004ee33  lea     rcx, [rsp+0C8h+var_88]; void *
0x18004ee38  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004ee3d  mov     eax, ebx
0x18004ee3f  mov     rbx, [rsp+0C8h+arg_0]
0x18004ee47  add     rsp, 0B0h
0x18004ee4e  pop     r15
0x18004ee50  pop     rdi
0x18004ee51  pop     rsi
0x18004ee52  retn
0x18004ee53  jmp     short loc_18004EE05
0x18004ee55  jmp     short loc_18004EE05
0x18004ee57  jmp     short loc_18004EE05
0x18004ee59  jmp     short loc_18004EE05
```
