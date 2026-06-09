# HrLoadDocumentFromFile(ushort *,SmartComPtr<IXMLDOMDocument> &,ushort const *)

- ea: `0x1800119b4`
- end: `0x180011bf5`
- name: `?HrLoadDocumentFromFile@@YAJPEAGAEAV?$SmartComPtr@UIXMLDOMDocument@@@@PEBG@Z`
- size: `577`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180011e80`
- `0x18002518c`

## callees

- `0x180010794`
- `0x1800107a4`
- `0x1800119b4`
- `0x180011bfc`
- `0x180011c90`
- `0x180038ce4`
- `0x180039a84`
- `0x18003a560`
- `0x1800495d8`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800119f6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800119f6`

## string_xrefs

- `0x180011abf`: `xmlns:scpd='urn:schemas-upnp-org:service-1-0'`

## pseudocode

```c
__int64 __fastcall HrLoadDocumentFromFile(const WCHAR *a1, LPVOID *a2)
{
  unsigned int Instance; // ebx
  unsigned int v5; // eax
  unsigned int v6; // r8d
  int v7; // eax
  bool v8; // zf
  __int64 (__fastcall ***v9)(LPVOID, GUID *, __int64 **); // rcx
  __int64 v10; // rcx
  __int64 (__fastcall *v11)(__int64 *, const wchar_t *, VARIANTARG *); // rbx
  STRSAFE_PCNZWCH v13; // rcx
  __int16 v14; // [rsp+20h] [rbp-49h] BYREF
  __int64 *v15; // [rsp+28h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-39h] BYREF
  VARIANTARG v17; // [rsp+50h] [rbp-19h] BYREF
  __int128 FileInformation; // [rsp+70h] [rbp+7h] BYREF
  __int128 v19; // [rsp+80h] [rbp+17h]
  unsigned int v20; // [rsp+90h] [rbp+27h]

  v20 = 0;
  FileInformation = 0;
  v19 = 0;
  if ( GetFileAttributesExW(a1, GetFileExInfoStandard, &FileInformation) && (HIDWORD(v19) || v20 > DwDHFileSizeLimit()) )
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
  v14 = 0;
  *(_QWORD *)&pvarg.vt = 8;
  *(_OWORD *)&pvarg.decVal.Lo32 = (unsigned __int64)a1;
  v5 = DwDHFileSizeLimit();
  RestrictDomDocument((struct IXMLDOMDocument *)*a2, v5, v6);
  v7 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(*(_QWORD *)*a2 + 464LL))(*a2, &pvarg, &v14);
  Instance = v7;
  v8 = v7 == 0;
  if ( v7 >= 0 )
  {
    if ( !v14 )
    {
      Instance = -2147467259;
      goto LABEL_12;
    }
    v8 = v7 == 0;
  }
  if ( v8 )
  {
    v9 = (__int64 (__fastcall ***)(LPVOID, GUID *, __int64 **))*a2;
    v15 = 0;
    Instance = (**v9)(v9, &IID_IXMLDOMDocument2, &v15);
    if ( !Instance )
    {
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids);
      v10 = *v15;
      pvarg.vt = 0;
      v11 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v10 + 640);
      ATL::CComVariant::operator=(&pvarg, L"xmlns:scpd='urn:schemas-upnp-org:service-1-0'");
      v17 = pvarg;
      Instance = v11(v15, L"SelectionNamespaces", &v17);
      ATL::CComVariant::Clear(&pvarg);
      (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
      goto LABEL_10;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      return Instance;
    if ( (WPP_GLOBAL_Control[14] & 0x40) == 0 )
      goto LABEL_13;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids);
  }
LABEL_12:
  v13 = WPP_GLOBAL_Control;
LABEL_13:
  if ( v13 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v13[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v13 + 2), 15, WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids, Instance);
  return Instance;
}

```

## disassembly

```asm
0x1800119b4  mov     [rsp-8+arg_10], rbx
0x1800119b9  push    rbp
0x1800119ba  push    rsi
0x1800119bb  push    rdi
0x1800119bc  push    r14
0x1800119be  push    r15
0x1800119c0  lea     rbp, [rsp-37h]
0x1800119c5  sub     rsp, 0A0h
0x1800119cc  mov     rax, cs:__security_cookie
0x1800119d3  xor     rax, rsp
0x1800119d6  mov     [rbp+57h+var_28], rax
0x1800119da  xorps   xmm0, xmm0
0x1800119dd  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x1800119e1  mov     rdi, rdx
0x1800119e4  xor     eax, eax
0x1800119e6  xor     edx, edx; fInfoLevelId
0x1800119e8  mov     [rbp+57h+var_30], eax
0x1800119eb  movups  [rbp+57h+FileInformation], xmm0
0x1800119ef  mov     rsi, rcx
0x1800119f2  movups  [rbp+57h+var_40], xmm0
0x1800119f6  call    cs:__imp_GetFileAttributesExW
0x1800119fc  xor     r14d, r14d
0x1800119ff  lea     r15, WPP_GLOBAL_Control
0x180011a06  test    eax, eax
0x180011a08  jnz     loc_180011B85
0x180011a0e  mov     rcx, rdi; ppv
0x180011a11  call    ?CoCreateInstance@?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IXMLDOMDocument>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x180011a16  mov     ebx, eax
0x180011a18  test    eax, eax
0x180011a1a  js      loc_180011B22
0x180011a20  xorps   xmm0, xmm0
0x180011a23  mov     [rbp+57h+var_A0], r14w
0x180011a28  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180011a2c  xor     ebx, ebx
0x180011a2e  mov     qword ptr [rbp+57h+pvarg+8], rsi
0x180011a32  lea     eax, [rbx+8]
0x180011a35  mov     word ptr [rbp+57h+pvarg], ax
0x180011a39  call    ?DwDHFileSizeLimit@@YAKXZ; DwDHFileSizeLimit(void)
0x180011a3e  mov     rcx, [rdi]; struct IXMLDOMDocument *
0x180011a41  mov     edx, eax; unsigned int
0x180011a43  call    ?RestrictDomDocument@@YAXPEAUIXMLDOMDocument@@KK@Z; RestrictDomDocument(IXMLDOMDocument *,ulong,ulong)
0x180011a48  mov     rcx, [rdi]
0x180011a4b  lea     r8, [rbp+57h+var_A0]
0x180011a4f  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180011a53  lea     rdx, [rbp+57h+pvarg]
0x180011a57  mov     qword ptr [rbp+57h+pvarg+10h], rbx
0x180011a5b  mov     rax, [rcx]
0x180011a5e  movaps  xmmword ptr [rbp+57h+pvarg], xmm0
0x180011a62  mov     rax, [rax+1D0h]
0x180011a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a6e  mov     ebx, eax
0x180011a70  test    eax, eax
0x180011a72  jns     loc_180011B77
0x180011a78  jnz     loc_180011B4B
0x180011a7e  mov     rcx, [rdi]
0x180011a81  lea     r8, [rbp+57h+var_98]
0x180011a85  mov     [rbp+57h+var_98], r14
0x180011a89  lea     rdx, IID_IXMLDOMDocument2
0x180011a90  mov     rax, [rcx]
0x180011a93  mov     rax, [rax]
0x180011a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a9b  mov     ebx, eax
0x180011a9d  test    eax, eax
0x180011a9f  jnz     loc_180011BC1
0x180011aa5  mov     rcx, cs:WPP_GLOBAL_Control
0x180011aac  cmp     rcx, r15
0x180011aaf  jz      short loc_180011ABB
0x180011ab1  test    byte ptr [rcx+1Ch], 40h
0x180011ab5  jnz     loc_180011BA7
0x180011abb  mov     rax, [rbp+57h+var_98]
0x180011abf  lea     rdx, aXmlnsScpdUrnSc; "xmlns:scpd='urn:schemas-upnp-org:servic"...
0x180011ac6  mov     rcx, [rax]
0x180011ac9  mov     word ptr [rbp+57h+pvarg], r14w
0x180011ace  mov     rbx, [rcx+280h]
0x180011ad5  lea     rcx, [rbp+57h+pvarg]
0x180011ad9  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x180011ade  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180011ae2  lea     r8, [rbp+57h+var_70]
0x180011ae6  mov     rcx, [rbp+57h+var_98]
0x180011aea  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180011aef  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x180011af6  mov     rax, rbx
0x180011af9  movaps  [rbp+57h+var_70], xmm0
0x180011afd  movsd   [rbp+57h+var_60], xmm1
0x180011b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b07  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180011b0b  mov     ebx, eax
0x180011b0d  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x180011b12  mov     rcx, [rbp+57h+var_98]
0x180011b16  mov     rax, [rcx]
0x180011b19  mov     rax, [rax+10h]
0x180011b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b22  test    ebx, ebx
0x180011b24  jnz     short loc_180011B4B
0x180011b26  mov     eax, ebx
0x180011b28  mov     rcx, [rbp+57h+var_28]
0x180011b2c  xor     rcx, rsp; StackCookie
0x180011b2f  call    __security_check_cookie
0x180011b34  mov     rbx, [rsp+0C0h+arg_10]
0x180011b3c  add     rsp, 0A0h
0x180011b43  pop     r15
0x180011b45  pop     r14
0x180011b47  pop     rdi
0x180011b48  pop     rsi
0x180011b49  pop     rbp
0x180011b4a  retn
0x180011b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b52  cmp     rcx, r15
0x180011b55  jz      short loc_180011B26
0x180011b57  test    byte ptr [rcx+1Ch], 1
0x180011b5b  jz      short loc_180011B26
0x180011b5d  mov     rcx, [rcx+10h]
0x180011b61  lea     r8, WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids
0x180011b68  mov     edx, 0Fh
0x180011b6d  mov     r9d, ebx
0x180011b70  call    WPP_SF_d
0x180011b75  jmp     short loc_180011B26
0x180011b77  cmp     [rbp+57h+var_A0], r14w
0x180011b7c  jz      short loc_180011BA0
0x180011b7e  test    eax, eax
0x180011b80  jmp     loc_180011A78
0x180011b85  cmp     dword ptr [rbp+57h+var_40+0Ch], r14d
0x180011b89  jnz     short loc_180011B99
0x180011b8b  call    ?DwDHFileSizeLimit@@YAKXZ; DwDHFileSizeLimit(void)
0x180011b90  cmp     [rbp+57h+var_30], eax
0x180011b93  jbe     loc_180011A0E
0x180011b99  mov     ebx, 8007000Eh
0x180011b9e  jmp     short loc_180011B4B
0x180011ba0  mov     ebx, 80004005h
0x180011ba5  jmp     short loc_180011B4B
0x180011ba7  mov     rcx, [rcx+10h]
0x180011bab  lea     r8, WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids
0x180011bb2  mov     edx, 0Dh
0x180011bb7  call    WPP_SF_
0x180011bbc  jmp     loc_180011ABB
0x180011bc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180011bc8  cmp     rcx, r15
0x180011bcb  jz      loc_180011B26
0x180011bd1  test    byte ptr [rcx+1Ch], 40h
0x180011bd5  jz      loc_180011B52
0x180011bdb  mov     rcx, [rcx+10h]
0x180011bdf  lea     r8, WPP_0f728bc4424332fd22a71fc2ba056f71_Traceguids
0x180011be6  mov     edx, 0Eh
0x180011beb  call    WPP_SF_
0x180011bf0  jmp     loc_180011B4B
```
