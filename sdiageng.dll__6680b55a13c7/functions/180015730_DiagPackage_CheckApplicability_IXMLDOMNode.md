# DiagPackage::CheckApplicability(IXMLDOMNode *)

- ea: `0x180015730`
- end: `0x180015c0e`
- name: `?CheckApplicability@DiagPackage@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `1246`
- prototype: `__int64 __fastcall(DiagPackage *this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016630`

## callees

- `0x180002978`
- `0x18000330c`
- `0x18001483c`
- `0x180015730`
- `0x18002146c`
- `0x180026fa0`
- `0x180029882`
- `0x1800298c0`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800158a9`
- `KERNEL32!GetLastError` at `0x1800158a9`
- `KERNEL32!GetNativeSystemInfo` at `0x1800158d4`
- `KERNEL32!GetNativeSystemInfo` at `0x1800158d4`
- `KERNEL32!GetVersionExW` at `0x18001589f`
- `KERNEL32!GetVersionExW` at `0x18001589f`
- `OLEAUT32!__imp_SysAllocString` at `0x180015953`
- `OLEAUT32!__imp_SysAllocString` at `0x1800159bf`
- `OLEAUT32!__imp_SysAllocString` at `0x180015b68`
- `OLEAUT32!__imp_SysAllocString` at `0x180015953`
- `OLEAUT32!__imp_SysAllocString` at `0x1800159bf`
- `OLEAUT32!__imp_SysAllocString` at `0x180015b68`
- `OLEAUT32!__imp_SysFreeString` at `0x180015b55`
- `OLEAUT32!__imp_SysFreeString` at `0x180015bc2`
- `OLEAUT32!__imp_SysFreeString` at `0x180015b55`
- `OLEAUT32!__imp_SysFreeString` at `0x180015bc2`
- `OLEAUT32!__imp_VariantInit` at `0x1800157d1`
- `OLEAUT32!__imp_VariantInit` at `0x1800157dc`
- `OLEAUT32!__imp_VariantInit` at `0x1800157e7`
- `OLEAUT32!__imp_VariantInit` at `0x1800157d1`
- `OLEAUT32!__imp_VariantInit` at `0x1800157dc`
- `OLEAUT32!__imp_VariantInit` at `0x1800157e7`
- `OLEAUT32!__imp_VariantClear` at `0x1800159aa`
- `OLEAUT32!__imp_VariantClear` at `0x180015b9c`
- `OLEAUT32!__imp_VariantClear` at `0x180015ba7`
- `OLEAUT32!__imp_VariantClear` at `0x180015bb2`
- `OLEAUT32!__imp_VariantClear` at `0x1800159aa`
- `OLEAUT32!__imp_VariantClear` at `0x180015b9c`
- `OLEAUT32!__imp_VariantClear` at `0x180015ba7`
- `OLEAUT32!__imp_VariantClear` at `0x180015bb2`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001598b`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800159f7`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18001598b`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800159f7`

## pseudocode

```c
__int64 __fastcall DiagPackage::CheckApplicability(DiagPackage *this, struct IXMLDOMNode *a2)
{
  struct IXMLDOMDocument2 *v4; // rsi
  signed int v5; // ebx
  int v6; // r8d
  int v7; // r9d
  int v8; // r8d
  signed int LastError; // eax
  int v10; // eax
  bool v11; // zf
  HRESULT v12; // eax
  HRESULT v13; // eax
  __int64 v14; // rax
  __int64 v15; // r14
  __int64 v16; // rdx
  _OSVERSIONINFOEXW *v17; // rax
  _OSVERSIONINFOW *p_VersionInformation; // rcx
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm1
  int v27; // eax
  int v28; // r9d
  int v29; // r8d
  int v30; // eax
  OLECHAR *v31; // rcx
  BSTR v32; // rax
  int v34; // [rsp+30h] [rbp-D0h] BYREF
  int v35; // [rsp+34h] [rbp-CCh] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C8h] BYREF
  struct IXMLDOMDocument2 *v37; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvargDest; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG v40; // [rsp+78h] [rbp-88h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+90h] [rbp-70h] BYREF
  struct _SYSTEM_INFO v42; // [rsp+C0h] [rbp-40h] BYREF
  _OSVERSIONINFOEXW v43; // [rsp+F0h] [rbp-10h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int8 v45; // [rsp+32Ah] [rbp+22Ah]
  OLECHAR psz[12]; // [rsp+330h] [rbp+230h] BYREF

  v34 = 0;
  v35 = 0;
  v4 = 0;
  bstrString = 0;
  v37 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&pvargDest, 0, sizeof(pvargDest));
  memset(&v40, 0, sizeof(v40));
  memset_0(&VersionInformation, 0, 0x11Cu);
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  VariantInit(&pvarg);
  VariantInit(&pvargDest);
  VariantInit(&v40);
  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = 1601;
    v7 = -2147024809;
LABEL_54:
    SdpDebugTrace(1u, L"DiagPackage::CheckApplicability", v6, v7);
    goto LABEL_55;
  }
  v5 = SdpCheckBooleanAttribute(a2, (OLECHAR *)L"clientSupported", &v34);
  if ( v5 < 0 )
  {
    v8 = 742;
LABEL_9:
    SdpDebugTrace(1u, L"SdpParseProfileNode", v8, v5);
    v7 = v5;
    v6 = 1611;
    goto LABEL_54;
  }
  v5 = SdpCheckBooleanAttribute(a2, (OLECHAR *)L"serverSupported", &v35);
  if ( v5 < 0 )
  {
    v8 = 747;
    goto LABEL_9;
  }
  v5 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))a2->lpVtbl->get_text)(a2, &bstrString);
  if ( v5 < 0 )
  {
    v8 = 750;
    goto LABEL_9;
  }
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( !GetVersionExW(&VersionInformation) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
    {
      v7 = v5;
      v6 = 1620;
      goto LABEL_54;
    }
  }
  GetNativeSystemInfo(&SystemInfo);
  v10 = StringCchPrintfW(psz, 0xAu, L"%u.%u", VersionInformation.dwMajorVersion, VersionInformation.dwMinorVersion);
  v5 = v10;
  if ( v10 < 0 )
  {
    v7 = v10;
    v6 = 1637;
    goto LABEL_54;
  }
  if ( v45 == 1 )
  {
    v11 = v34 == 0;
  }
  else
  {
    if ( (unsigned int)v45 - 2 > 1 )
      goto LABEL_23;
    v11 = v35 == 0;
  }
  if ( v11 )
    *(_DWORD *)this &= ~1u;
LABEL_23:
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(psz);
  if ( !pvarg.llVal )
  {
    v6 = 1657;
LABEL_52:
    v7 = -2147024882;
    goto LABEL_53;
  }
  v12 = VariantChangeTypeEx(&pvargDest, &pvarg, 0x409u, 4u, 4u);
  v5 = v12;
  if ( v12 < 0 )
  {
    v7 = v12;
    v6 = 1664;
    goto LABEL_54;
  }
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(bstrString);
  if ( !pvarg.llVal )
  {
    v6 = 1670;
    goto LABEL_52;
  }
  v13 = VariantChangeTypeEx(&v40, &pvarg, 0x409u, 4u, 4u);
  v5 = v13;
  if ( v13 < 0 )
  {
    v7 = v13;
    v6 = 1677;
    goto LABEL_54;
  }
  if ( v40.fltVal > pvargDest.fltVal )
    *(_DWORD *)this &= ~1u;
  v14 = *((_QWORD *)this + 1);
  if ( !v14 )
  {
    v7 = -2147467261;
    v6 = 1687;
LABEL_53:
    v5 = v7;
    goto LABEL_54;
  }
  v15 = *(_QWORD *)(v14 + 72);
  v16 = 2;
  v17 = &v43;
  p_VersionInformation = &VersionInformation;
  v42 = SystemInfo;
  do
  {
    v19 = *(_OWORD *)&p_VersionInformation->dwPlatformId;
    *(_OWORD *)&v17->dwOSVersionInfoSize = *(_OWORD *)&p_VersionInformation->dwOSVersionInfoSize;
    v20 = *(_OWORD *)&p_VersionInformation->szCSDVersion[6];
    *(_OWORD *)&v17->dwPlatformId = v19;
    v21 = *(_OWORD *)&p_VersionInformation->szCSDVersion[14];
    *(_OWORD *)&v17->szCSDVersion[6] = v20;
    v22 = *(_OWORD *)&p_VersionInformation->szCSDVersion[22];
    *(_OWORD *)&v17->szCSDVersion[14] = v21;
    v23 = *(_OWORD *)&p_VersionInformation->szCSDVersion[30];
    *(_OWORD *)&v17->szCSDVersion[22] = v22;
    v24 = *(_OWORD *)&p_VersionInformation->szCSDVersion[38];
    *(_OWORD *)&v17->szCSDVersion[30] = v23;
    v25 = *(_OWORD *)&p_VersionInformation->szCSDVersion[46];
    p_VersionInformation = (_OSVERSIONINFOW *)((char *)p_VersionInformation + 128);
    *(_OWORD *)&v17->szCSDVersion[38] = v24;
    *(_OWORD *)&v17->szCSDVersion[46] = v25;
    v17 = (_OSVERSIONINFOEXW *)((char *)v17 + 128);
    --v16;
  }
  while ( v16 );
  v26 = *(_OWORD *)&p_VersionInformation->dwBuildNumber;
  *(_OWORD *)&v17->dwOSVersionInfoSize = *(_OWORD *)&p_VersionInformation->dwOSVersionInfoSize;
  *(_OWORD *)&v17->dwBuildNumber = v26;
  v27 = DiagPackage::BuildReportComputerXml((DiagPackage *)p_VersionInformation, &v43, &v42, &v37);
  v5 = v27;
  if ( v27 < 0 )
  {
    v28 = v27;
    v29 = 1692;
LABEL_39:
    SdpDebugTrace(1u, L"DiagPackage::CheckApplicability", v29, v28);
    v4 = v37;
    goto LABEL_55;
  }
  if ( !v15 )
  {
    v28 = -2147467261;
    v29 = 1694;
    v5 = -2147467261;
    goto LABEL_39;
  }
  v4 = v37;
  v30 = Reporter::AddXmlToReport(v15, v37, 0);
  v5 = v30;
  if ( v30 < 0 )
  {
    v7 = v30;
    v6 = 1697;
    goto LABEL_54;
  }
  if ( v34 )
    *(_DWORD *)this |= 2u;
  if ( v35 )
    *(_DWORD *)this |= 4u;
  v31 = (OLECHAR *)*((_QWORD *)this + 13);
  if ( v31 )
  {
    SysFreeString(v31);
    *((_QWORD *)this + 13) = 0;
  }
  v32 = SysAllocString(bstrString);
  *((_QWORD *)this + 13) = v32;
  if ( !v32 )
  {
    v6 = 1713;
    goto LABEL_52;
  }
LABEL_55:
  VariantClear(&pvarg);
  VariantClear(&pvargDest);
  VariantClear(&v40);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v4->lpVtbl->Release)(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180015730  mov     [rsp-8+arg_10], rbx
0x180015735  mov     [rsp-8+arg_18], rsi
0x18001573a  push    rbp
0x18001573b  push    rdi
0x18001573c  push    r14
0x18001573e  lea     rbp, [rsp-250h]
0x180015746  sub     rsp, 350h
0x18001574d  mov     rax, cs:__security_cookie
0x180015754  xor     rax, rsp
0x180015757  mov     [rbp+260h+var_18], rax
0x18001575e  xor     eax, eax
0x180015760  mov     [rsp+360h+var_330], 0
0x180015768  xorps   xmm0, xmm0
0x18001576b  mov     qword ptr [rsp+360h+pvarg+10h], rax
0x180015770  mov     r14, rdx
0x180015773  mov     qword ptr [rsp+360h+pvargDest+10h], rax
0x180015778  mov     rdi, rcx
0x18001577b  mov     qword ptr [rbp+260h+var_2E8+10h], rax
0x18001577f  xorps   xmm1, xmm1
0x180015782  mov     [rsp+360h+var_32C], 0
0x18001578a  xor     esi, esi
0x18001578c  mov     [rsp+360h+bstrString], 0
0x180015795  xor     edx, edx; Val
0x180015797  mov     [rsp+360h+var_320], rsi
0x18001579c  lea     rcx, [rbp+260h+VersionInformation]; void *
0x1800157a3  mov     r8d, 11Ch; Size
0x1800157a9  movups  xmmword ptr [rsp+360h+pvarg], xmm0
0x1800157ae  movups  xmmword ptr [rsp+360h+pvargDest], xmm1
0x1800157b3  movups  xmmword ptr [rsp+360h+var_2E8], xmm0
0x1800157b8  call    memset_0
0x1800157bd  xorps   xmm0, xmm0
0x1800157c0  lea     rcx, [rsp+360h+pvarg]; pvarg
0x1800157c5  movups  xmmword ptr [rbp+260h+SystemInfo], xmm0
0x1800157c9  movups  xmmword ptr [rbp+260h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800157cd  movups  xmmword ptr [rbp+260h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800157d1  call    cs:__imp_VariantInit
0x1800157d7  lea     rcx, [rsp+360h+pvargDest]; pvarg
0x1800157dc  call    cs:__imp_VariantInit
0x1800157e2  lea     rcx, [rsp+360h+var_2E8]; pvarg
0x1800157e7  call    cs:__imp_VariantInit
0x1800157ed  test    r14, r14
0x1800157f0  jnz     short loc_180015805
0x1800157f2  mov     ebx, 80070057h
0x1800157f7  mov     r8d, 641h
0x1800157fd  mov     r9d, ebx
0x180015800  jmp     loc_180015B86
0x180015805  lea     r8, [rsp+360h+var_330]; int *
0x18001580a  mov     rcx, r14; struct IXMLDOMNode *
0x18001580d  lea     rdx, aClientsupporte; "clientSupported"
0x180015814  call    ?SdpCheckBooleanAttribute@@YAJPEAUIXMLDOMNode@@PEBGPEAH@Z; SdpCheckBooleanAttribute(IXMLDOMNode *,ushort const *,int *)
0x180015819  mov     ebx, eax
0x18001581b  test    eax, eax
0x18001581d  jns     short loc_180015827
0x18001581f  mov     r8d, 2E6h
0x180015825  jmp     short loc_18001586C
0x180015827  lea     r8, [rsp+360h+var_32C]; int *
0x18001582c  mov     rcx, r14; struct IXMLDOMNode *
0x18001582f  lea     rdx, aServersupporte; "serverSupported"
0x180015836  call    ?SdpCheckBooleanAttribute@@YAJPEAUIXMLDOMNode@@PEBGPEAH@Z; SdpCheckBooleanAttribute(IXMLDOMNode *,ushort const *,int *)
0x18001583b  mov     ebx, eax
0x18001583d  test    eax, eax
0x18001583f  jns     short loc_180015849
0x180015841  mov     r8d, 2EBh
0x180015847  jmp     short loc_18001586C
0x180015849  mov     rax, [r14]
0x18001584c  lea     rdx, [rsp+360h+bstrString]
0x180015851  mov     rcx, r14
0x180015854  mov     rax, [rax+0D0h]
0x18001585b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015860  mov     ebx, eax
0x180015862  test    eax, eax
0x180015864  jns     short loc_18001588E
0x180015866  mov     r8d, 2EEh; int
0x18001586c  lea     rdx, aSdpparseprofil; "SdpParseProfileNode"
0x180015873  mov     r9d, ebx; int
0x180015876  mov     ecx, 1; Level
0x18001587b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180015880  mov     r9d, ebx
0x180015883  mov     r8d, 64Bh
0x180015889  jmp     loc_180015B86
0x18001588e  lea     rcx, [rbp+260h+VersionInformation]; lpVersionInformation
0x180015895  mov     [rbp+260h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18001589f  call    cs:__imp_GetVersionExW
0x1800158a5  test    eax, eax
0x1800158a7  jnz     short loc_1800158D0
0x1800158a9  call    cs:__imp_GetLastError
0x1800158af  mov     ebx, eax
0x1800158b1  test    eax, eax
0x1800158b3  jle     short loc_1800158BE
0x1800158b5  movzx   ebx, ax
0x1800158b8  or      ebx, 80070000h
0x1800158be  test    ebx, ebx
0x1800158c0  jns     short loc_1800158D0
0x1800158c2  mov     r9d, ebx
0x1800158c5  mov     r8d, 654h
0x1800158cb  jmp     loc_180015B86
0x1800158d0  lea     rcx, [rbp+260h+SystemInfo]; lpSystemInfo
0x1800158d4  call    cs:__imp_GetNativeSystemInfo
0x1800158da  mov     eax, [rbp+260h+VersionInformation.dwMinorVersion]
0x1800158e0  lea     r8, aUU; "%u.%u"
0x1800158e7  mov     r9d, [rbp+260h+VersionInformation.dwMajorVersion]
0x1800158ee  lea     rcx, [rbp+260h+psz]; unsigned __int16 *
0x1800158f5  mov     edx, 0Ah; unsigned __int64
0x1800158fa  mov     dword ptr [rsp+360h+vt], eax
0x1800158fe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015903  mov     ebx, eax
0x180015905  test    eax, eax
0x180015907  jns     short loc_180015917
0x180015909  mov     r9d, eax
0x18001590c  mov     r8d, 665h
0x180015912  jmp     loc_180015B86
0x180015917  movzx   ecx, [rbp+260h+var_36]
0x18001591e  mov     r14d, 0FFFFFFFEh
0x180015924  sub     ecx, 1
0x180015927  jz      short loc_180015939
0x180015929  sub     ecx, 1
0x18001592c  jz      short loc_180015933
0x18001592e  cmp     ecx, 1
0x180015931  jnz     short loc_180015942
0x180015933  cmp     [rsp+360h+var_32C], esi
0x180015937  jmp     short loc_18001593D
0x180015939  cmp     [rsp+360h+var_330], esi
0x18001593d  jnz     short loc_180015942
0x18001593f  and     [rdi], r14d
0x180015942  mov     eax, 8
0x180015947  lea     rcx, [rbp+260h+psz]; psz
0x18001594e  mov     word ptr [rsp+360h+pvarg], ax
0x180015953  call    cs:__imp_SysAllocString
0x180015959  mov     qword ptr [rsp+360h+pvarg+8], rax
0x18001595e  test    rax, rax
0x180015961  jnz     short loc_18001596E
0x180015963  mov     r8d, 679h
0x180015969  jmp     loc_180015B7D
0x18001596e  mov     eax, 4
0x180015973  lea     rdx, [rsp+360h+pvarg]; pvarSrc
0x180015978  mov     r9d, eax; wFlags
0x18001597b  mov     [rsp+360h+vt], ax; vt
0x180015980  mov     r8d, 409h; lcid
0x180015986  lea     rcx, [rsp+360h+pvargDest]; pvargDest
0x18001598b  call    cs:__imp_VariantChangeTypeEx
0x180015991  mov     ebx, eax
0x180015993  test    eax, eax
0x180015995  jns     short loc_1800159A5
0x180015997  mov     r9d, eax
0x18001599a  mov     r8d, 680h
0x1800159a0  jmp     loc_180015B86
0x1800159a5  lea     rcx, [rsp+360h+pvarg]; pvarg
0x1800159aa  call    cs:__imp_VariantClear
0x1800159b0  mov     rcx, [rsp+360h+bstrString]; psz
0x1800159b5  mov     eax, 8
0x1800159ba  mov     word ptr [rsp+360h+pvarg], ax
0x1800159bf  call    cs:__imp_SysAllocString
0x1800159c5  mov     qword ptr [rsp+360h+pvarg+8], rax
0x1800159ca  test    rax, rax
0x1800159cd  jnz     short loc_1800159DA
0x1800159cf  mov     r8d, 686h
0x1800159d5  jmp     loc_180015B7D
0x1800159da  mov     eax, 4
0x1800159df  lea     rdx, [rsp+360h+pvarg]; pvarSrc
0x1800159e4  mov     r9d, eax; wFlags
0x1800159e7  mov     [rsp+360h+vt], ax; vt
0x1800159ec  mov     r8d, 409h; lcid
0x1800159f2  lea     rcx, [rsp+360h+var_2E8]; pvargDest
0x1800159f7  call    cs:__imp_VariantChangeTypeEx
0x1800159fd  mov     ebx, eax
0x1800159ff  test    eax, eax
0x180015a01  jns     short loc_180015A11
0x180015a03  mov     r9d, eax
0x180015a06  mov     r8d, 68Dh
0x180015a0c  jmp     loc_180015B86
0x180015a11  movss   xmm0, dword ptr [rbp+260h+var_2E8+8]
0x180015a16  comiss  xmm0, dword ptr [rsp+360h+pvargDest+8]
0x180015a1b  jbe     short loc_180015A20
0x180015a1d  and     [rdi], r14d
0x180015a20  mov     rax, [rdi+8]
0x180015a24  test    rax, rax
0x180015a27  jnz     short loc_180015A3A
0x180015a29  mov     r9d, 80004003h
0x180015a2f  mov     r8d, 697h
0x180015a35  jmp     loc_180015B83
0x180015a3a  mov     r14, [rax+48h]
0x180015a3e  movups  xmm0, xmmword ptr [rbp+260h+SystemInfo]
0x180015a42  mov     edx, 2
0x180015a47  lea     rax, [rbp+260h+var_270]
0x180015a4b  movups  xmm1, xmmword ptr [rbp+260h+SystemInfo.lpMaximumApplicationAddress]
0x180015a4f  lea     rcx, [rbp+260h+VersionInformation]
0x180015a56  movaps  xmmword ptr [rbp+260h+var_2A0], xmm0
0x180015a5a  movups  xmm0, xmmword ptr [rbp+260h+SystemInfo.dwNumberOfProcessors]
0x180015a5e  lea     r8d, [rdx+7Eh]
0x180015a62  movaps  xmmword ptr [rbp+260h+var_2A0.lpMaximumApplicationAddress], xmm1
0x180015a66  movaps  xmmword ptr [rbp+260h+var_2A0.dwNumberOfProcessors], xmm0
0x180015a6a  movups  xmm0, xmmword ptr [rcx]
0x180015a6d  movups  xmm1, xmmword ptr [rcx+10h]
0x180015a71  movups  xmmword ptr [rax], xmm0
0x180015a74  movups  xmm0, xmmword ptr [rcx+20h]
0x180015a78  movups  xmmword ptr [rax+10h], xmm1
0x180015a7c  movups  xmm1, xmmword ptr [rcx+30h]
0x180015a80  movups  xmmword ptr [rax+20h], xmm0
0x180015a84  movups  xmm0, xmmword ptr [rcx+40h]
0x180015a88  movups  xmmword ptr [rax+30h], xmm1
0x180015a8c  movups  xmm1, xmmword ptr [rcx+50h]
0x180015a90  movups  xmmword ptr [rax+40h], xmm0
0x180015a94  movups  xmm0, xmmword ptr [rcx+60h]
0x180015a98  movups  xmmword ptr [rax+50h], xmm1
0x180015a9c  movups  xmm1, xmmword ptr [rcx+70h]
0x180015aa0  add     rcx, r8; this
0x180015aa3  movups  xmmword ptr [rax+60h], xmm0
0x180015aa7  movups  xmmword ptr [rax+70h], xmm1
0x180015aab  add     rax, r8
0x180015aae  sub     rdx, 1
0x180015ab2  jnz     short loc_180015A6A
0x180015ab4  movups  xmm0, xmmword ptr [rcx]
0x180015ab7  lea     r9, [rsp+360h+var_320]; struct IXMLDOMDocument2 **
0x180015abc  movups  xmm1, xmmword ptr [rcx+0Ch]
0x180015ac0  lea     r8, [rbp+260h+var_2A0]; struct _SYSTEM_INFO
0x180015ac4  movups  xmmword ptr [rax], xmm0
0x180015ac7  lea     rdx, [rbp+260h+var_270]; struct _OSVERSIONINFOEXW
0x180015acb  movups  xmmword ptr [rax+0Ch], xmm1
0x180015acf  call    ?BuildReportComputerXml@DiagPackage@@AEAAJU_OSVERSIONINFOEXW@@U_SYSTEM_INFO@@PEAPEAUIXMLDOMDocument2@@@Z; DiagPackage::BuildReportComputerXml(_OSVERSIONINFOEXW,_SYSTEM_INFO,IXMLDOMDocument2 * *)
0x180015ad4  mov     ebx, eax
0x180015ad6  test    eax, eax
0x180015ad8  jns     short loc_180015AFE
0x180015ada  mov     r9d, eax; int
0x180015add  mov     r8d, 69Ch; int
0x180015ae3  lea     rdx, aDiagpackageChe_0; "DiagPackage::CheckApplicability"
0x180015aea  mov     ecx, 1; Level
0x180015aef  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180015af4  mov     rsi, [rsp+360h+var_320]
0x180015af9  jmp     loc_180015B97
0x180015afe  test    r14, r14
0x180015b01  jnz     short loc_180015B14
0x180015b03  mov     r9d, 80004003h
0x180015b09  mov     r8d, 69Eh
0x180015b0f  mov     ebx, r9d
0x180015b12  jmp     short loc_180015AE3
0x180015b14  mov     rsi, [rsp+360h+var_320]
0x180015b19  xor     r8d, r8d
0x180015b1c  mov     rdx, rsi
0x180015b1f  mov     rcx, r14
0x180015b22  call    ?AddXmlToReport@Reporter@@QEAAJPEAUIXMLDOMDocument2@@W4_REPORT_AREA@1@@Z; Reporter::AddXmlToReport(IXMLDOMDocument2 *,Reporter::_REPORT_AREA)
0x180015b27  mov     ebx, eax
0x180015b29  test    eax, eax
0x180015b2b  jns     short loc_180015B38
0x180015b2d  mov     r9d, eax
0x180015b30  mov     r8d, 6A1h
0x180015b36  jmp     short loc_180015B86
0x180015b38  cmp     [rsp+360h+var_330], 0
0x180015b3d  jz      short loc_180015B42
0x180015b3f  or      dword ptr [rdi], 2
0x180015b42  cmp     [rsp+360h+var_32C], 0
0x180015b47  jz      short loc_180015B4C
0x180015b49  or      dword ptr [rdi], 4
0x180015b4c  mov     rcx, [rdi+68h]; bstrString
0x180015b50  test    rcx, rcx
0x180015b53  jz      short loc_180015B63
0x180015b55  call    cs:__imp_SysFreeString
0x180015b5b  mov     qword ptr [rdi+68h], 0
0x180015b63  mov     rcx, [rsp+360h+bstrString]; psz
0x180015b68  call    cs:__imp_SysAllocString
0x180015b6e  mov     [rdi+68h], rax
0x180015b72  test    rax, rax
0x180015b75  jnz     short loc_180015B97
0x180015b77  mov     r8d, 6B1h; int
0x180015b7d  mov     r9d, 8007000Eh; int
0x180015b83  mov     ebx, r9d
0x180015b86  lea     rdx, aDiagpackageChe_0; "DiagPackage::CheckApplicability"
0x180015b8d  mov     ecx, 1; Level
0x180015b92  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180015b97  lea     rcx, [rsp+360h+pvarg]; pvarg
0x180015b9c  call    cs:__imp_VariantClear
0x180015ba2  lea     rcx, [rsp+360h+pvargDest]; pvarg
0x180015ba7  call    cs:__imp_VariantClear
0x180015bad  lea     rcx, [rsp+360h+var_2E8]; pvarg
0x180015bb2  call    cs:__imp_VariantClear
0x180015bb8  mov     rcx, [rsp+360h+bstrString]; bstrString
0x180015bbd  test    rcx, rcx
0x180015bc0  jz      short loc_180015BD1
0x180015bc2  call    cs:__imp_SysFreeString
0x180015bc8  mov     [rsp+360h+bstrString], 0
0x180015bd1  test    rsi, rsi
0x180015bd4  jz      short loc_180015BE5
0x180015bd6  mov     rax, [rsi]
0x180015bd9  mov     rcx, rsi
0x180015bdc  mov     rax, [rax+10h]
0x180015be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015be5  mov     eax, ebx
0x180015be7  mov     rcx, [rbp+260h+var_18]
0x180015bee  xor     rcx, rsp; StackCookie
0x180015bf1  call    __security_check_cookie
0x180015bf6  lea     r11, [rsp+360h+var_10]
0x180015bfe  mov     rbx, [r11+30h]
0x180015c02  mov     rsi, [r11+38h]
0x180015c06  mov     rsp, r11
0x180015c09  pop     r14
0x180015c0b  pop     rdi
0x180015c0c  pop     rbp
0x180015c0d  retn
```
