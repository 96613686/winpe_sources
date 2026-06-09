# UrlContextInfo::GetPlatformIdentifiers(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180018164`
- end: `0x180018395`
- name: `?GetPlatformIdentifiers@UrlContextInfo@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z`
- size: `561`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033a70`

## callees

- `0x1800034c0`
- `0x180003990`
- `0x1800039c8`
- `0x180003cf0`
- `0x180004b00`
- `0x180004b2c`
- `0x180004dd4`
- `0x1800061a8`
- `0x180006aa4`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x180010b80`
- `0x180018164`
- `0x18003f9c4`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800181ce`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800181ce`

## string_xrefs

- `0x1800181b8`: `onecoreuap\ds\ext\live\identity\lib\platformextension\urlcontextinfo.cpp`
- `0x180018238`: `onecoreuap\ds\ext\live\identity\lib\platformextension\urlcontextinfo.cpp`
- `0x180018306`: `onecoreuap\ds\ext\live\identity\lib\platformextension\urlcontextinfo.cpp`
- `0x180018358`: `onecoreuap\ds\ext\live\identity\lib\platformextension\urlcontextinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UrlContextInfo::GetPlatformIdentifiers(_QWORD *a1, _QWORD *a2)
{
  unsigned __int16 **v4; // rdx
  int *v5; // rsi
  __int64 v6; // rbx
  const wchar_t *v7; // rdx
  int PlatformQualifier; // eax
  _QWORD *v9; // rcx
  unsigned int v10; // ebx
  char *v12; // [rsp+20h] [rbp-50h]
  __int64 v13; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v14[3]; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v15[4]; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v16; // [rsp+A0h] [rbp+30h] BYREF
  int v17; // [rsp+A8h] [rbp+38h] BYREF

  v17 = 0;
  v16 = 0;
  memset(v14, 0, sizeof(v14));
  v15[0] = "UrlContextInfo::GetPlatformIdentifiers";
  v15[1] = &v17;
  v15[2] = 0;
  v15[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\platformextension\\urlcontextinfo.cpp",
    "UrlContextInfo::GetPlatformIdentifiers",
    (const char *)0x24,
    0,
    (const unsigned __int16 *)v12);
  RtlGetDeviceFamilyInfoEnum(0, &v16, 0);
  ATL::CSimpleStringT<unsigned short,0>::SetString(a1, L"Windows10");
  ATL::CSimpleStringT<unsigned short,0>::SetString(a2, L"Win10");
  if ( v16 == 3 )
    goto LABEL_20;
  if ( v16 == 5 )
    goto LABEL_17;
  if ( v16 != 6 )
  {
    if ( v16 == 10 )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(a1, L"Holo");
      v7 = L"Holo";
LABEL_18:
      v9 = a2;
      goto LABEL_19;
    }
    if ( v16 - 11 >= 2 )
    {
      TracePrintW(
        3u,
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\platformextension\\urlcontextinfo.cpp",
        0x44u,
        L"No specialized identifier for current platform.");
      if ( v16 > 0xD )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v13);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v13,
          L"Windows.%d",
          v16);
        v5 = (int *)(*a1 - 24LL);
        if ( (int *)(v13 - 24) != v5 )
        {
          if ( v5[4] >= 0 && *(_QWORD *)(v13 - 24) == *(_QWORD *)v5 )
          {
            v6 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
            ATL::CStringData::Release((ATL::CStringData *)v5);
            *a1 = v6 + 24;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(a1, v13, *(unsigned int *)(v13 - 16));
          }
        }
        ATL::CSimpleStringT<unsigned short,0>::Empty(a2);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v13);
      }
      goto LABEL_20;
    }
LABEL_17:
    ATL::CSimpleStringT<unsigned short,0>::SetString(a1, L"Xbox1Core");
    v7 = L"XboxOneCore";
    goto LABEL_18;
  }
  PlatformQualifier = MsaUserExtImpl::GetPlatformQualifier((MsaUserExtImpl *)v14, v4);
  v17 = PlatformQualifier;
  if ( PlatformQualifier >= 0 )
  {
    v7 = (const wchar_t *)v14[0];
    v9 = a1;
LABEL_19:
    ATL::CSimpleStringT<unsigned short,0>::SetString(v9, v7);
LABEL_20:
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\platformextension\\urlcontextinfo.cpp",
      0x55u,
      L"URL query string platform is: %ls, uiflavor is: %ls",
      *a1,
      *a2);
    goto LABEL_21;
  }
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\platformextension\\urlcontextinfo.cpp",
    "UrlContextInfo::GetPlatformIdentifiers",
    0x32u,
    PlatformQualifier,
    "hr = MsaUserExtImpl::GetPlatformQualifier(&spPlatform)");
LABEL_21:
  v10 = v17;
  CTraceFuncW<long>::~CTraceFuncW<long>(v15);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(v14);
  return v10;
}

```

## disassembly

```asm
0x180018164  mov     [rsp-18h+arg_0], rbx
0x180018169  mov     [rsp-18h+arg_8], rsi
0x18001816e  push    rbp
0x18001816f  push    rdi
0x180018170  push    r14
0x180018172  mov     rbp, rsp
0x180018175  sub     rsp, 70h
0x180018179  mov     r14, rdx
0x18001817c  mov     rdi, rcx
0x18001817f  xor     ebx, ebx
0x180018181  mov     [rbp+arg_18], ebx
0x180018184  mov     [rbp+arg_10], ebx
0x180018187  mov     [rbp+var_38], rbx
0x18001818b  mov     [rbp+var_28], rbx
0x18001818f  mov     [rbp+var_30], rbx
0x180018193  lea     rsi, aUrlcontextinfo; "UrlContextInfo::GetPlatformIdentifiers"
0x18001819a  mov     [rbp+var_20], rsi
0x18001819e  lea     rax, [rbp+arg_18]
0x1800181a2  mov     [rbp+var_18], rax
0x1800181a6  mov     [rbp+var_10], rbx
0x1800181aa  mov     [rbp+var_8], rbx
0x1800181ae  xor     r9d, r9d; unsigned int
0x1800181b1  lea     r8d, [rbx+24h]; char *
0x1800181b5  mov     rdx, rsi; char *
0x1800181b8  lea     rcx, aOnecoreuapDsEx_8; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800181bf  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800181c4  nop
0x1800181c5  xor     r8d, r8d
0x1800181c8  lea     rdx, [rbp+arg_10]
0x1800181cc  xor     ecx, ecx
0x1800181ce  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800181d4  lea     rdx, aWindows10; "Windows10"
0x1800181db  mov     rcx, rdi
0x1800181de  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800181e3  lea     rdx, aWin10; "Win10"
0x1800181ea  mov     rcx, r14
0x1800181ed  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800181f2  mov     eax, [rbp+arg_10]
0x1800181f5  lea     ecx, [rbx+3]; unsigned __int8
0x1800181f8  sub     eax, ecx
0x1800181fa  jz      loc_18001833B
0x180018200  sub     eax, 2
0x180018203  jz      loc_18001831D
0x180018209  sub     eax, 1
0x18001820c  jz      loc_1800182DE
0x180018212  sub     eax, 4
0x180018215  jz      loc_1800182C6
0x18001821b  sub     eax, 1
0x18001821e  jz      loc_18001831D
0x180018224  cmp     eax, 1
0x180018227  jz      loc_18001831D
0x18001822d  lea     r9, aNoSpecializedI; "No specialized identifier for current p"...
0x180018234  lea     r8d, [rbx+44h]; unsigned int
0x180018238  lea     rdx, aOnecoreuapDsEx_8; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001823f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180018244  cmp     [rbp+arg_10], 0Dh
0x180018248  jbe     loc_18001833B
0x18001824e  lea     rcx, [rbp+var_40]; void *
0x180018252  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180018257  nop
0x180018258  mov     r8d, [rbp+arg_10]
0x18001825c  lea     rdx, aWindowsD; "Windows.%d"
0x180018263  lea     rcx, [rbp+var_40]
0x180018267  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001826c  mov     rdx, [rbp+var_40]
0x180018270  lea     rcx, [rdx-18h]
0x180018274  mov     rsi, [rdi]
0x180018277  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18001827b  cmp     rcx, rsi
0x18001827e  jz      short loc_1800182B2
0x180018280  cmp     [rsi+10h], ebx
0x180018283  jl      short loc_1800182A6
0x180018285  mov     rax, [rsi]
0x180018288  cmp     [rcx], rax
0x18001828b  jnz     short loc_1800182A6
0x18001828d  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180018292  mov     rbx, rax
0x180018295  mov     rcx, rsi; this
0x180018298  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001829d  lea     rax, [rbx+18h]
0x1800182a1  mov     [rdi], rax
0x1800182a4  jmp     short loc_1800182B2
0x1800182a6  mov     r8d, [rdx-10h]
0x1800182aa  mov     rcx, rdi
0x1800182ad  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800182b2  mov     rcx, r14
0x1800182b5  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800182ba  nop
0x1800182bb  lea     rcx, [rbp+var_40]; void *
0x1800182bf  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800182c4  jmp     short loc_18001833B
0x1800182c6  lea     rdx, aHolo; "Holo"
0x1800182cd  mov     rcx, rdi
0x1800182d0  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800182d5  lea     rdx, aHolo; "Holo"
0x1800182dc  jmp     short loc_180018333
0x1800182de  lea     rcx, [rbp+var_38]; this
0x1800182e2  call    ?GetPlatformQualifier@MsaUserExtImpl@@YAJPEAPEAG@Z; MsaUserExtImpl::GetPlatformQualifier(ushort * *)
0x1800182e7  mov     [rbp+arg_18], eax
0x1800182ea  test    eax, eax
0x1800182ec  jns     short loc_180018314
0x1800182ee  lea     r8, aHrMsauserextim; "hr = MsaUserExtImpl::GetPlatformQualifi"...
0x1800182f5  mov     [rsp+70h+var_50], r8; char *
0x1800182fa  mov     r9d, eax; int
0x1800182fd  mov     r8d, 32h ; '2'; unsigned int
0x180018303  mov     rdx, rsi; char *
0x180018306  lea     rcx, aOnecoreuapDsEx_8; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001830d  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180018312  jmp     short loc_180018368
0x180018314  mov     rdx, [rbp+var_38]
0x180018318  mov     rcx, rdi
0x18001831b  jmp     short loc_180018336
0x18001831d  lea     rdx, aXbox1core; "Xbox1Core"
0x180018324  mov     rcx, rdi
0x180018327  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18001832c  lea     rdx, aXboxonecore; "XboxOneCore"
0x180018333  mov     rcx, r14
0x180018336  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18001833b  mov     rax, [r14]
0x18001833e  mov     [rsp+70h+var_48], rax
0x180018343  mov     rax, [rdi]
0x180018346  mov     [rsp+70h+var_50], rax
0x18001834b  lea     r9, aUrlQueryString; "URL query string platform is: %ls, uifl"...
0x180018352  mov     r8d, 55h ; 'U'; unsigned int
0x180018358  lea     rdx, aOnecoreuapDsEx_8; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001835f  lea     ecx, [r8-50h]; unsigned __int8
0x180018363  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180018368  mov     ebx, [rbp+arg_18]
0x18001836b  lea     rcx, [rbp+var_20]
0x18001836f  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180018374  nop
0x180018375  lea     rcx, [rbp+var_38]
0x180018379  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x18001837e  mov     eax, ebx
0x180018380  lea     r11, [rsp+70h+var_s0]
0x180018385  mov     rbx, [r11+20h]
0x180018389  mov     rsi, [r11+28h]
0x18001838d  mov     rsp, r11
0x180018390  pop     r14
0x180018392  pop     rdi
0x180018393  pop     rbp
0x180018394  retn
```
