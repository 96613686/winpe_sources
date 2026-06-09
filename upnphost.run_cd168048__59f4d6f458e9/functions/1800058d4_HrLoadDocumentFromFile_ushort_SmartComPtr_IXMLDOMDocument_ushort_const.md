# HrLoadDocumentFromFile(ushort *,SmartComPtr<IXMLDOMDocument> &,ushort const *)

- ea: `0x1800058d4`
- end: `0x180005b1c`
- name: `?HrLoadDocumentFromFile@@YAJPEAGAEAV?$SmartComPtr@UIXMLDOMDocument@@@@PEBG@Z`
- size: `584`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000413c`
- `0x180005df0`

## callees

- `0x18000471c`
- `0x180004730`
- `0x1800058d4`
- `0x180005b24`
- `0x180005bc0`
- `0x18003b1cc`
- `0x18003c018`
- `0x18003cb60`
- `0x18004c4bc`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180005916`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180005916`

## string_xrefs

- `0x1800059e5`: `xmlns:scpd='urn:schemas-upnp-org:service-1-0'`

## pseudocode

```c
__int64 __fastcall HrLoadDocumentFromFile(const WCHAR *a1, LPVOID *a2)
{
  unsigned int Instance; // ebx
  int v5; // eax
  int v6; // eax
  bool v7; // zf
  __int64 (__fastcall ***v8)(LPVOID, GUID *, __int64 **); // rcx
  __int64 v9; // rcx
  __int64 (__fastcall *v10)(__int64 *, const wchar_t *, VARIANTARG *); // rbx
  STRSAFE_PCNZWCH v12; // rcx
  __int16 v13; // [rsp+20h] [rbp-49h] BYREF
  __int64 *v14; // [rsp+28h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-39h] BYREF
  VARIANTARG v16; // [rsp+50h] [rbp-19h] BYREF
  __int128 FileInformation; // [rsp+70h] [rbp+7h] BYREF
  __int128 v18; // [rsp+80h] [rbp+17h]
  unsigned int v19; // [rsp+90h] [rbp+27h]

  v19 = 0;
  FileInformation = 0;
  v18 = 0;
  if ( GetFileAttributesExW(a1, GetFileExInfoStandard, &FileInformation)
    && (HIDWORD(v18) || v19 > (unsigned int)DwDHFileSizeLimit()) )
  {
    Instance = -2147024882;
    goto LABEL_12;
  }
  Instance = ATL::CComPtrBase<IXMLDOMDocument>::CoCreateInstance(a2);
  if ( (Instance & 0x80000000) != 0 )
  {
LABEL_10:
    if ( !Instance )
      return Instance;
    goto LABEL_12;
  }
  v13 = 0;
  *(_QWORD *)&pvarg.vt = 8;
  *(_OWORD *)&pvarg.decVal.Lo32 = (unsigned __int64)a1;
  v5 = DwDHFileSizeLimit();
  RestrictDomDocument((struct IXMLDOMDocument *)*a2, v5);
  v6 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(*(_QWORD *)*a2 + 464LL))(*a2, &pvarg, &v13);
  Instance = v6;
  v7 = v6 == 0;
  if ( v6 >= 0 )
  {
    if ( !v13 )
    {
      Instance = -2147467259;
      goto LABEL_12;
    }
    v7 = v6 == 0;
  }
  if ( v7 )
  {
    v8 = (__int64 (__fastcall ***)(LPVOID, GUID *, __int64 **))*a2;
    v14 = 0;
    Instance = (**v8)(v8, &IID_IXMLDOMDocument2, &v14);
    if ( !Instance )
    {
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids);
      v9 = *v14;
      pvarg.vt = 0;
      v10 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v9 + 640);
      ATL::CComVariant::operator=(&pvarg, L"xmlns:scpd='urn:schemas-upnp-org:service-1-0'");
      v16 = pvarg;
      Instance = v10(v14, L"SelectionNamespaces", &v16);
      ATL::CComVariant::Clear(&pvarg);
      (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
      goto LABEL_10;
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      return Instance;
    if ( (WPP_GLOBAL_Control[14] & 0x40) == 0 )
      goto LABEL_13;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids);
  }
LABEL_12:
  v12 = WPP_GLOBAL_Control;
LABEL_13:
  if ( v12 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v12[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v12 + 2), 15, WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids, Instance);
  return Instance;
}

```

## disassembly

```asm
0x1800058d4  mov     [rsp-8+arg_10], rbx
0x1800058d9  push    rbp
0x1800058da  push    rsi
0x1800058db  push    rdi
0x1800058dc  push    r14
0x1800058de  push    r15
0x1800058e0  lea     rbp, [rsp-37h]
0x1800058e5  sub     rsp, 0A0h
0x1800058ec  mov     rax, cs:__security_cookie
0x1800058f3  xor     rax, rsp
0x1800058f6  mov     [rbp+57h+var_28], rax
0x1800058fa  xorps   xmm0, xmm0
0x1800058fd  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x180005901  mov     rdi, rdx
0x180005904  xor     eax, eax
0x180005906  xor     edx, edx; fInfoLevelId
0x180005908  mov     [rbp+57h+var_30], eax
0x18000590b  movups  [rbp+57h+FileInformation], xmm0
0x18000590f  mov     rsi, rcx
0x180005912  movups  [rbp+57h+var_40], xmm0
0x180005916  call    cs:__imp_GetFileAttributesExW
0x18000591d  nop     dword ptr [rax+rax+00h]
0x180005922  xor     r14d, r14d
0x180005925  lea     r15, WPP_GLOBAL_Control
0x18000592c  test    eax, eax
0x18000592e  jnz     loc_180005AAC
0x180005934  mov     rcx, rdi; ppv
0x180005937  call    ?CoCreateInstance@?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IXMLDOMDocument>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x18000593c  mov     ebx, eax
0x18000593e  test    eax, eax
0x180005940  js      loc_180005A48
0x180005946  xorps   xmm0, xmm0
0x180005949  mov     [rbp+57h+var_A0], r14w
0x18000594e  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180005952  xor     ebx, ebx
0x180005954  mov     qword ptr [rbp+57h+pvarg+8], rsi
0x180005958  lea     eax, [rbx+8]
0x18000595b  mov     word ptr [rbp+57h+pvarg], ax
0x18000595f  call    ?DwDHFileSizeLimit@@YAKXZ; DwDHFileSizeLimit(void)
0x180005964  mov     rcx, [rdi]; struct IXMLDOMDocument *
0x180005967  mov     edx, eax; unsigned int
0x180005969  call    ?RestrictDomDocument@@YAXPEAUIXMLDOMDocument@@KK@Z; RestrictDomDocument(IXMLDOMDocument *,ulong,ulong)
0x18000596e  mov     rcx, [rdi]
0x180005971  lea     r8, [rbp+57h+var_A0]
0x180005975  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180005979  lea     rdx, [rbp+57h+pvarg]
0x18000597d  mov     qword ptr [rbp+57h+pvarg+10h], rbx
0x180005981  mov     rax, [rcx]
0x180005984  movaps  xmmword ptr [rbp+57h+pvarg], xmm0
0x180005988  mov     rax, [rax+1D0h]
0x18000598f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005994  mov     ebx, eax
0x180005996  test    eax, eax
0x180005998  jns     loc_180005A9E
0x18000599e  jnz     loc_180005A72
0x1800059a4  mov     rcx, [rdi]
0x1800059a7  lea     r8, [rbp+57h+var_98]
0x1800059ab  mov     [rbp+57h+var_98], r14
0x1800059af  lea     rdx, IID_IXMLDOMDocument2
0x1800059b6  mov     rax, [rcx]
0x1800059b9  mov     rax, [rax]
0x1800059bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059c1  mov     ebx, eax
0x1800059c3  test    eax, eax
0x1800059c5  jnz     loc_180005AE8
0x1800059cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059d2  cmp     rcx, r15
0x1800059d5  jz      short loc_1800059E1
0x1800059d7  test    byte ptr [rcx+1Ch], 40h
0x1800059db  jnz     loc_180005ACE
0x1800059e1  mov     rax, [rbp+57h+var_98]
0x1800059e5  lea     rdx, aXmlnsScpdUrnSc; "xmlns:scpd='urn:schemas-upnp-org:servic"...
0x1800059ec  mov     rcx, [rax]
0x1800059ef  mov     word ptr [rbp+57h+pvarg], r14w
0x1800059f4  mov     rbx, [rcx+280h]
0x1800059fb  lea     rcx, [rbp+57h+pvarg]
0x1800059ff  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x180005a04  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180005a08  lea     r8, [rbp+57h+var_70]
0x180005a0c  mov     rcx, [rbp+57h+var_98]
0x180005a10  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180005a15  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x180005a1c  mov     rax, rbx
0x180005a1f  movaps  [rbp+57h+var_70], xmm0
0x180005a23  movsd   [rbp+57h+var_60], xmm1
0x180005a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a2d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180005a31  mov     ebx, eax
0x180005a33  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x180005a38  mov     rcx, [rbp+57h+var_98]
0x180005a3c  mov     rax, [rcx]
0x180005a3f  mov     rax, [rax+10h]
0x180005a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a48  test    ebx, ebx
0x180005a4a  jnz     short loc_180005A72
0x180005a4c  mov     eax, ebx
0x180005a4e  mov     rcx, [rbp+57h+var_28]
0x180005a52  xor     rcx, rsp; StackCookie
0x180005a55  call    __security_check_cookie
0x180005a5a  mov     rbx, [rsp+0C0h+arg_10]
0x180005a62  add     rsp, 0A0h
0x180005a69  pop     r15
0x180005a6b  pop     r14
0x180005a6d  pop     rdi
0x180005a6e  pop     rsi
0x180005a6f  pop     rbp
0x180005a70  retn
0x180005a72  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a79  cmp     rcx, r15
0x180005a7c  jz      short loc_180005A4C
0x180005a7e  test    byte ptr [rcx+1Ch], 1
0x180005a82  jz      short loc_180005A4C
0x180005a84  mov     rcx, [rcx+10h]
0x180005a88  lea     r8, WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids
0x180005a8f  mov     edx, 0Fh
0x180005a94  mov     r9d, ebx
0x180005a97  call    WPP_SF_d
0x180005a9c  jmp     short loc_180005A4C
0x180005a9e  cmp     [rbp+57h+var_A0], r14w
0x180005aa3  jz      short loc_180005AC7
0x180005aa5  test    eax, eax
0x180005aa7  jmp     loc_18000599E
0x180005aac  cmp     dword ptr [rbp+57h+var_40+0Ch], r14d
0x180005ab0  jnz     short loc_180005AC0
0x180005ab2  call    ?DwDHFileSizeLimit@@YAKXZ; DwDHFileSizeLimit(void)
0x180005ab7  cmp     [rbp+57h+var_30], eax
0x180005aba  jbe     loc_180005934
0x180005ac0  mov     ebx, 8007000Eh
0x180005ac5  jmp     short loc_180005A72
0x180005ac7  mov     ebx, 80004005h
0x180005acc  jmp     short loc_180005A72
0x180005ace  mov     rcx, [rcx+10h]
0x180005ad2  lea     r8, WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids
0x180005ad9  mov     edx, 0Dh
0x180005ade  call    WPP_SF_
0x180005ae3  jmp     loc_1800059E1
0x180005ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x180005aef  cmp     rcx, r15
0x180005af2  jz      loc_180005A4C
0x180005af8  test    byte ptr [rcx+1Ch], 40h
0x180005afc  jz      loc_180005A79
0x180005b02  mov     rcx, [rcx+10h]
0x180005b06  lea     r8, WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids
0x180005b0d  mov     edx, 0Eh
0x180005b12  call    WPP_SF_
0x180005b17  jmp     loc_180005A72
```
