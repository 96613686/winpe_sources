# UrlUtilities::GetMarket(IWinApiLite *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180007378`
- end: `0x180007670`
- name: `?GetMarket@UrlUtilities@@SAJPEAVIWinApiLite@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008460`

## callees

- `0x180007378`
- `0x180009e98`
- `0x18000a36c`
- `0x18000c050`
- `0x18000ed04`
- `0x180014640`
- `0x1800151c4`
- `0x180015860`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18003722c`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800075da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800075da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000757d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800075ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800075f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000757d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800075ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800075f1`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000743a`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000743a`
- `Bcp47Langs!GetUserLanguages` at `0x180007593`
- `Bcp47Langs!GetUserLanguages` at `0x180007593`

## string_xrefs

- `0x1800074ae`: `Failure - GetThreadPreferredUILanguages, HRESULT: 0x%08X\n`
- `0x180007534`: `Failure - GetThreadPreferredUILanguages, HRESULT: 0x%08X\n`

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
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v20);
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
  ErrorVerifier::ErrorVerifier((ErrorVerifier *)v21, "UrlUtilities::GetMarket", &v23, 0xAu, &qword_180191E20);
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
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v22);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v20);
  return v12;
}

```

## disassembly

```asm
0x180007378  mov     rax, rsp
0x18000737b  mov     [rax+8], rbx
0x18000737f  push    rsi
0x180007380  push    rdi
0x180007381  push    r15
0x180007383  sub     rsp, 0B0h
0x18000738a  mov     rdi, rdx
0x18000738d  mov     rbx, rcx
0x180007390  mov     [rsp+0C8h+var_94], 0
0x180007398  mov     dword ptr [rax+20h], 0
0x18000739f  lea     rcx, [rsp+0C8h+var_88]
0x1800073a4  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800073a9  nop
0x1800073aa  mov     [rsp+0C8h+arg_10], 0
0x1800073b5  mov     [rsp+0C8h+var_98], 0
0x1800073bd  lea     rsi, aUrlutilitiesGe; "UrlUtilities::GetMarket"
0x1800073c4  mov     [rsp+0C8h+var_58], rsi
0x1800073c9  lea     rax, [rsp+0C8h+arg_10]
0x1800073d1  mov     [rsp+0C8h+var_50], rax
0x1800073d6  mov     [rsp+0C8h+var_48], 0
0x1800073e2  mov     [rsp+0C8h+var_40], 0
0x1800073ee  xor     r9d, r9d; unsigned int
0x1800073f1  lea     r8d, [r9+3Bh]; char *
0x1800073f5  mov     rdx, rsi; char *
0x1800073f8  lea     r15, aOnecoreuapDsEx_62; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800073ff  mov     rcx, r15; this
0x180007402  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180007407  nop
0x180007408  lea     rax, qword_180191E20
0x18000740f  mov     [rsp+0C8h+var_A8], rax; int *
0x180007414  mov     r9d, 0Ah; unsigned __int64
0x18000741a  lea     r8, [rsp+0C8h+arg_10]; int *
0x180007422  mov     rdx, rsi; char *
0x180007425  lea     rcx, [rsp+0C8h+var_78]; this
0x18000742a  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x18000742f  nop
0x180007430  xor     r8d, r8d
0x180007433  lea     rdx, [rsp+0C8h+var_98]
0x180007438  xor     ecx, ecx
0x18000743a  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180007440  mov     eax, [rsp+0C8h+var_98]
0x180007444  cmp     eax, 5
0x180007447  jz      loc_180007572
0x18000744d  add     eax, 0FFFFFFF5h
0x180007450  cmp     eax, 1
0x180007453  jbe     loc_180007572
0x180007459  mov     rax, [rbx]
0x18000745c  lea     rcx, [rsp+0C8h+arg_18]
0x180007464  mov     [rsp+0C8h+var_A8], rcx
0x180007469  xor     r9d, r9d
0x18000746c  lea     r8, [rsp+0C8h+var_94]
0x180007471  lea     edx, [r9+8]
0x180007475  mov     rcx, rbx
0x180007478  mov     rax, [rax+88h]
0x18000747f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007484  mov     rdx, [rbx]
0x180007487  test    eax, eax
0x180007489  jnz     short loc_1800074CD
0x18000748b  mov     rcx, rbx
0x18000748e  mov     rax, [rdx+78h]
0x180007492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007497  test    eax, eax
0x180007499  jle     short loc_1800074A3
0x18000749b  movzx   eax, ax
0x18000749e  or      eax, 80070000h
0x1800074a3  mov     [rsp+0C8h+arg_10], eax
0x1800074aa  mov     dword ptr [rsp+0C8h+var_A8], eax
0x1800074ae  lea     r9, aFailureGetthre; "Failure - GetThreadPreferredUILanguages"...
0x1800074b5  mov     r8d, 53h ; 'S'; unsigned int
0x1800074bb  mov     rdx, r15; char *
0x1800074be  lea     ecx, [r8-51h]; unsigned __int8
0x1800074c2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800074c7  nop
0x1800074c8  jmp     loc_180007619
0x1800074cd  mov     rsi, [rdx+88h]
0x1800074d4  mov     edx, [rsp+0C8h+arg_18]
0x1800074db  lea     rcx, [rsp+0C8h+var_88]
0x1800074e0  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x1800074e5  lea     rcx, [rsp+0C8h+arg_18]
0x1800074ed  mov     [rsp+0C8h+var_A8], rcx
0x1800074f2  mov     r9, rax
0x1800074f5  lea     r8, [rsp+0C8h+var_94]
0x1800074fa  mov     edx, 8
0x1800074ff  mov     rcx, rbx
0x180007502  mov     rax, rsi
0x180007505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000750a  test    eax, eax
0x18000750c  jnz     short loc_180007553
0x18000750e  mov     rax, [rbx]
0x180007511  mov     rcx, rbx
0x180007514  mov     rax, [rax+78h]
0x180007518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000751d  test    eax, eax
0x18000751f  jle     short loc_180007529
0x180007521  movzx   eax, ax
0x180007524  or      eax, 80070000h
0x180007529  mov     [rsp+0C8h+arg_10], eax
0x180007530  mov     dword ptr [rsp+0C8h+var_A8], eax
0x180007534  lea     r9, aFailureGetthre; "Failure - GetThreadPreferredUILanguages"...
0x18000753b  mov     r8d, 5Dh ; ']'; unsigned int
0x180007541  mov     rdx, r15; char *
0x180007544  lea     ecx, [r8-5Bh]; unsigned __int8
0x180007548  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000754d  nop
0x18000754e  jmp     loc_180007619
0x180007553  or      edx, 0FFFFFFFFh
0x180007556  lea     rcx, [rsp+0C8h+var_88]
0x18000755b  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x180007560  mov     rdx, [rsp+0C8h+var_88]
0x180007565  mov     rcx, rdi
0x180007568  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18000756d  jmp     loc_1800075F7
0x180007572  mov     [rsp+0C8h+string], 0
0x18000757b  xor     ecx, ecx; string
0x18000757d  call    cs:__imp_WindowsDeleteString
0x180007583  mov     [rsp+0C8h+string], 0
0x18000758c  xor     ecx, ecx
0x18000758e  lea     rdx, [rsp+0C8h+string]
0x180007593  call    cs:__imp_GetUserLanguages
0x180007599  mov     [rsp+0C8h+arg_10], eax
0x1800075a0  test    eax, eax
0x1800075a2  jns     short loc_1800075D3
0x1800075a4  lea     rcx, aHrGetuserlangu; "hr = GetUserLanguages(L'\\0', langList."...
0x1800075ab  mov     [rsp+0C8h+var_A8], rcx; char *
0x1800075b0  mov     r9d, eax; int
0x1800075b3  mov     r8d, 49h ; 'I'; unsigned int
0x1800075b9  mov     rdx, rsi; char *
0x1800075bc  mov     rcx, r15; char *
0x1800075bf  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800075c4  nop
0x1800075c5  mov     rcx, [rsp+0C8h+string]; string
0x1800075ca  call    cs:__imp_WindowsDeleteString
0x1800075d0  nop
0x1800075d1  jmp     short loc_180007619
0x1800075d3  xor     edx, edx; length
0x1800075d5  mov     rcx, [rsp+0C8h+string]; string
0x1800075da  call    cs:__imp_WindowsGetStringRawBuffer
0x1800075e0  mov     rdx, rax
0x1800075e3  mov     rcx, rdi
0x1800075e6  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800075eb  nop
0x1800075ec  mov     rcx, [rsp+0C8h+string]; string
0x1800075f1  call    cs:__imp_WindowsDeleteString
0x1800075f7  mov     rax, [rdi]
0x1800075fa  mov     [rsp+0C8h+var_A8], rax
0x1800075ff  lea     r9, aFoundUserMarke; "Found user market of '%ls'."
0x180007606  mov     r8d, 6Fh ; 'o'; unsigned int
0x18000760c  mov     rdx, r15; char *
0x18000760f  lea     ecx, [r8-6Ah]; unsigned __int8
0x180007613  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180007618  nop
0x180007619  mov     ebx, [rsp+0C8h+arg_10]
0x180007620  mov     r9, [rsp+0C8h+var_78]; int *
0x180007625  mov     r8, [rsp+0C8h+var_70]; unsigned __int64
0x18000762a  mov     rdx, [rsp+0C8h+var_68]
0x18000762f  mov     edx, [rdx]; int
0x180007631  mov     rcx, [rsp+0C8h+var_60]; char *
0x180007636  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x18000763b  nop
0x18000763c  lea     rcx, [rsp+0C8h+var_58]
0x180007641  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180007646  nop
0x180007647  lea     rcx, [rsp+0C8h+var_88]
0x18000764c  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180007651  mov     eax, ebx
0x180007653  mov     rbx, [rsp+0C8h+arg_0]
0x18000765b  add     rsp, 0B0h
0x180007662  pop     r15
0x180007664  pop     rdi
0x180007665  pop     rsi
0x180007666  retn
0x180007667  jmp     short loc_180007619
0x180007669  jmp     short loc_180007619
0x18000766b  jmp     short loc_180007619
0x18000766d  jmp     short loc_180007619
```
