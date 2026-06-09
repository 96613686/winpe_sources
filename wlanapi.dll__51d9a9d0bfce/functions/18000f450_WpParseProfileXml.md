# WpParseProfileXml

- ea: `0x18000f450`
- end: `0x18000f663`
- name: `WpParseProfileXml`
- size: `531`
- prototype: `__int64 __fastcall(OLECHAR *psz)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f170`
- `0x180020d40`
- `0x18002b760`
- `0x18002e510`

## callees

- `0x18000f450`
- `0x18000f66c`
- `0x18000f8f4`
- `0x18000f948`
- `0x180013ca8`
- `0x180018ac0`
- `0x18004e9ec`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000f658`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000f658`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f52c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f52c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f523`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f540`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f579`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f523`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f540`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f579`

## string_xrefs

- `0x18000f4cb`: `xmlns:WLANProfile='http://www.microsoft.com/networking/WLAN/profile/v1' xmlns:WLANPolicy='http://www.microsoft.com/networking/WLAN/policy/v1' xmlns:LANProfile='http://www.microsoft.com/networking/LAN/profile/v1' xmlns:LANPolicy='http://www.microsoft.com/networking/LAN/policy/v1' xmlns:LANPolicyV2='http://www.microsoft.com/networking/LAN/policy/v2' xmlns:OneX='http://www.microsoft.com/networking/OneX/v1' xmlns:baseeapconnectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapConnectionP`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WpParseProfileXml(OLECHAR *psz, _QWORD *a2, struct IUnknown *a3, _DWORD *a4)
{
  struct IXMLDOMDocument2 *v7; // rbx
  unsigned int ProfileSchemaCollectionInternal; // r14d
  struct IXMLDOMDocument2 *v9; // rdi
  struct IUnknown *v10; // rsi
  int v11; // esi
  OLECHAR *v12; // rdi
  int v13; // eax
  unsigned int LoadError; // eax
  struct IXMLDOMDocument2 *v16; // [rsp+20h] [rbp-10h] BYREF
  struct IUnknown *v17; // [rsp+78h] [rbp+48h] BYREF
  int v18; // [rsp+88h] [rbp+58h] BYREF

  v18 = 0;
  v7 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a4 )
    *a4 = 0;
  ProfileSchemaCollectionInternal = CXcSmartCoInit::Init((CXcSmartCoInit *)&v18);
  if ( ProfileSchemaCollectionInternal )
    goto LABEL_22;
  v9 = 0;
  v16 = 0;
  v17 = 0;
  if ( a3 )
  {
    ATL::AtlComPtrAssign(&v17, a3);
  }
  else
  {
    ProfileSchemaCollectionInternal = WpCreateProfileSchemaCollectionInternal((struct IXMLDOMSchemaCollection **)&v17);
    if ( ProfileSchemaCollectionInternal )
    {
      v10 = v17;
      goto LABEL_10;
    }
  }
  v10 = v17;
  ProfileSchemaCollectionInternal = XcCreateXmlDoc(
                                      (OLECHAR *)L"xmlns:WLANProfile='http://www.microsoft.com/networking/WLAN/profile/v1'"
                                                  " xmlns:WLANPolicy='http://www.microsoft.com/networking/WLAN/policy/v1'"
                                                  " xmlns:LANProfile='http://www.microsoft.com/networking/LAN/profile/v1'"
                                                  " xmlns:LANPolicy='http://www.microsoft.com/networking/LAN/policy/v1' x"
                                                  "mlns:LANPolicyV2='http://www.microsoft.com/networking/LAN/policy/v2' x"
                                                  "mlns:OneX='http://www.microsoft.com/networking/OneX/v1' xmlns:baseeapc"
                                                  "onnectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapCo"
                                                  "nnectionPropertiesV1' xmlns:mspeapconnectionpropertiesv1='http://www.m"
                                                  "icrosoft.com/provisioning/MsPeapConnectionPropertiesV1' xmlns:mschapv2"
                                                  "connectionpropertiesv1='http://www.microsoft.com/provisioning/MsChapV2"
                                                  "ConnectionPropertiesV1' xmlns:WLANProfileV2='http://www.microsoft.com/"
                                                  "networking/WLAN/profile/v2' xmlns:WLANProfileV3='http://www.microsoft."
                                                  "com/networking/WLAN/profile/v3' xmlns:WLANProfileV4='http://www.micros"
                                                  "oft.com/networking/WLAN/profile/v4' xmlns:WLANProfileV5='http://www.mi"
                                                  "crosoft.com/networking/WLAN/profile/v5' xmlns:WLANPolicyV2='http://www"
                                                  ".microsoft.com/networking/WLAN/policy/v2' xmlns:WLANPolicyV3='http://w"
                                                  "ww.microsoft.com/networking/WLAN/policy/v3' xmlns:WLANPolicyV4='http:/"
                                                  "/www.microsoft.com/networking/WLAN/policy/v4' xmlns:WLANAPProfile='htt"
                                                  "p://www.microsoft.com/networking/WLANAP/profile/v1' xmlns:WFDProfile='"
                                                  "http://www.microsoft.com/networking/WiFiDirect/profile/v1' xmlns:WFDLe"
                                                  "gacyProfile='http://www.microsoft.com/networking/WiFiDirectLegacy/profile/v1' ",
                                      (struct IXMLDOMSchemaCollection *)v17,
                                      &v16);
  if ( ProfileSchemaCollectionInternal )
    v9 = v16;
  else
    v7 = v16;
LABEL_10:
  if ( v10 )
    ((void (__fastcall *)(struct IUnknown *))v10->lpVtbl->Release)(v10);
  if ( v9 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v9->lpVtbl->Release)(v9);
  if ( ProfileSchemaCollectionInternal )
    goto LABEL_22;
  v11 = 0;
  LOWORD(v17) = 0;
  SysFreeString(0);
  v12 = SysAllocString(psz);
  if ( v12 )
  {
    SysFreeString(0);
    v13 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, OLECHAR *, struct IUnknown **))v7->lpVtbl->loadXML)(
            v7,
            v12,
            &v17);
    ProfileSchemaCollectionInternal = v13;
    if ( v13 < 0 )
    {
      if ( (v13 & 0x1FFF0000) == 0x70000 )
        ProfileSchemaCollectionInternal = (unsigned __int16)v13;
      if ( ProfileSchemaCollectionInternal )
        goto LABEL_19;
    }
    else
    {
      ProfileSchemaCollectionInternal = 0;
    }
    LOBYTE(v11) = (_WORD)v17 == 0xFFFF;
  }
  else
  {
    v12 = 0;
    ProfileSchemaCollectionInternal = 14;
  }
LABEL_19:
  SysFreeString(v12);
  if ( ProfileSchemaCollectionInternal )
    goto LABEL_22;
  if ( v11 )
    goto LABEL_21;
  LoadError = XcGetLoadError(v7);
  ProfileSchemaCollectionInternal = LoadError;
  if ( LoadError == 1206 )
  {
    if ( a4 )
      *a4 = 524289;
  }
  else if ( !LoadError )
  {
LABEL_21:
    ProfileSchemaCollectionInternal = WpParseProfileXmlDoc((struct IXMLDOMNode *)v7);
  }
LABEL_22:
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v7->lpVtbl->Release)(v7);
  if ( v18 )
    CoUninitialize();
  return ProfileSchemaCollectionInternal;
}

```

## disassembly

```asm
0x18000f450  mov     [rsp-38h+arg_0], rbx
0x18000f455  push    rbp
0x18000f456  push    rsi
0x18000f457  push    rdi
0x18000f458  push    r12
0x18000f45a  push    r13
0x18000f45c  push    r14
0x18000f45e  push    r15
0x18000f460  mov     rbp, rsp
0x18000f463  sub     rsp, 30h
0x18000f467  mov     r15, r9
0x18000f46a  mov     rsi, r8
0x18000f46d  mov     r12, rdx
0x18000f470  mov     r13, rcx
0x18000f473  mov     [rbp+arg_18], 0
0x18000f47a  xor     ebx, ebx
0x18000f47c  test    rdx, rdx
0x18000f47f  jz      short loc_18000F484
0x18000f481  mov     [rdx], rbx
0x18000f484  test    r15, r15
0x18000f487  jnz     loc_18000F5E5
0x18000f48d  lea     rcx, [rbp+arg_18]; this
0x18000f491  call    ?Init@CXcSmartCoInit@@QEAAKXZ; CXcSmartCoInit::Init(void)
0x18000f496  mov     r14d, eax
0x18000f499  test    eax, eax
0x18000f49b  jnz     loc_18000F59D
0x18000f4a1  xor     edi, edi
0x18000f4a3  mov     [rbp+var_10], rdi
0x18000f4a7  mov     [rbp+arg_8], rbx
0x18000f4ab  lea     rcx, [rbp+arg_8]; struct IXMLDOMSchemaCollection **
0x18000f4af  test    rsi, rsi
0x18000f4b2  jz      loc_18000F5ED
0x18000f4b8  mov     rdx, rsi; struct IUnknown *
0x18000f4bb  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000f4c0  lea     r8, [rbp+var_10]; struct IXMLDOMDocument2 **
0x18000f4c4  mov     rsi, [rbp+arg_8]
0x18000f4c8  mov     rdx, rsi; struct IXMLDOMSchemaCollection *
0x18000f4cb  lea     rcx, aXmlnsWlanprofi; "xmlns:WLANProfile='http://www.microsoft"...
0x18000f4d2  call    ?XcCreateXmlDoc@@YAKPEBGPEAUIXMLDOMSchemaCollection@@PEAPEAUIXMLDOMDocument2@@@Z; XcCreateXmlDoc(ushort const *,IXMLDOMSchemaCollection *,IXMLDOMDocument2 * *)
0x18000f4d7  mov     r14d, eax
0x18000f4da  test    eax, eax
0x18000f4dc  jnz     loc_18000F5D4
0x18000f4e2  mov     rbx, [rbp+var_10]
0x18000f4e6  test    rsi, rsi
0x18000f4e9  jz      short loc_18000F4FB
0x18000f4eb  mov     rax, [rsi]
0x18000f4ee  mov     rcx, rsi
0x18000f4f1  mov     rax, [rax+10h]
0x18000f4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4fa  nop
0x18000f4fb  test    rdi, rdi
0x18000f4fe  jz      short loc_18000F510
0x18000f500  mov     rax, [rdi]
0x18000f503  mov     rcx, rdi
0x18000f506  mov     rax, [rax+10h]
0x18000f50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f50f  nop
0x18000f510  test    r14d, r14d
0x18000f513  jnz     loc_18000F59D
0x18000f519  xor     esi, esi
0x18000f51b  xor     eax, eax
0x18000f51d  mov     word ptr [rbp+arg_8], ax
0x18000f521  xor     ecx, ecx; bstrString
0x18000f523  call    cs:__imp_SysFreeString
0x18000f529  mov     rcx, r13; psz
0x18000f52c  call    cs:__imp_SysAllocString
0x18000f532  mov     rdi, rax
0x18000f535  test    rax, rax
0x18000f538  jz      loc_18000F5DD
0x18000f53e  xor     ecx, ecx; bstrString
0x18000f540  call    cs:__imp_SysFreeString
0x18000f546  mov     rax, [rbx]
0x18000f549  lea     r8, [rbp+arg_8]
0x18000f54d  mov     rdx, rdi
0x18000f550  mov     rcx, rbx
0x18000f553  mov     rax, [rax+208h]
0x18000f55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f55f  mov     r14d, eax
0x18000f562  test    eax, eax
0x18000f564  js      loc_18000F606
0x18000f56a  xor     r14d, r14d
0x18000f56d  cmp     word ptr [rbp+arg_8], 0FFFFh
0x18000f572  setz    sil
0x18000f576  mov     rcx, rdi; bstrString
0x18000f579  call    cs:__imp_SysFreeString
0x18000f57f  test    r14d, r14d
0x18000f582  jnz     short loc_18000F59D
0x18000f584  test    esi, esi
0x18000f586  jz      loc_18000F624
0x18000f58c  mov     r9, r15
0x18000f58f  mov     rdx, r12
0x18000f592  mov     rcx, rbx; struct IXMLDOMNode *
0x18000f595  call    WpParseProfileXmlDoc
0x18000f59a  mov     r14d, eax
0x18000f59d  test    rbx, rbx
0x18000f5a0  jz      short loc_18000F5B2
0x18000f5a2  mov     rax, [rbx]
0x18000f5a5  mov     rcx, rbx
0x18000f5a8  mov     rax, [rax+10h]
0x18000f5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5b1  nop
0x18000f5b2  cmp     [rbp+arg_18], 0
0x18000f5b6  jnz     loc_18000F658
0x18000f5bc  mov     eax, r14d
0x18000f5bf  mov     rbx, [rsp+30h+arg_0]
0x18000f5c4  add     rsp, 30h
0x18000f5c8  pop     r15
0x18000f5ca  pop     r14
0x18000f5cc  pop     r13
0x18000f5ce  pop     r12
0x18000f5d0  pop     rdi
0x18000f5d1  pop     rsi
0x18000f5d2  pop     rbp
0x18000f5d3  retn
0x18000f5d4  mov     rdi, [rbp+var_10]
0x18000f5d8  jmp     loc_18000F4E6
0x18000f5dd  xor     edi, edi
0x18000f5df  lea     r14d, [rdi+0Eh]
0x18000f5e3  jmp     short loc_18000F576
0x18000f5e5  mov     [r9], ebx
0x18000f5e8  jmp     loc_18000F48D
0x18000f5ed  call    ?WpCreateProfileSchemaCollectionInternal@@YAKPEAPEAUIXMLDOMSchemaCollection@@@Z; WpCreateProfileSchemaCollectionInternal(IXMLDOMSchemaCollection * *)
0x18000f5f2  mov     r14d, eax
0x18000f5f5  test    eax, eax
0x18000f5f7  jz      loc_18000F4C0
0x18000f5fd  mov     rsi, [rbp+arg_8]
0x18000f601  jmp     loc_18000F4E6
0x18000f606  and     eax, 1FFF0000h
0x18000f60b  cmp     eax, 70000h
0x18000f610  jnz     short loc_18000F616
0x18000f612  movzx   r14d, r14w
0x18000f616  test    r14d, r14d
0x18000f619  jnz     loc_18000F576
0x18000f61f  jmp     loc_18000F56D
0x18000f624  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18000f627  call    ?XcGetLoadError@@YAKPEAUIXMLDOMDocument2@@@Z; XcGetLoadError(IXMLDOMDocument2 *)
0x18000f62c  mov     r14d, eax
0x18000f62f  cmp     eax, 4B6h
0x18000f634  jnz     short loc_18000F64B
0x18000f636  test    r15, r15
0x18000f639  jz      loc_18000F59D
0x18000f63f  mov     dword ptr [r15], 80001h
0x18000f646  jmp     loc_18000F59D
0x18000f64b  test    eax, eax
0x18000f64d  jnz     loc_18000F59D
0x18000f653  jmp     loc_18000F58C
0x18000f658  call    cs:__imp_CoUninitialize
0x18000f65e  jmp     loc_18000F5BC
```
