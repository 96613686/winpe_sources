# CXMLPropStoreSaxParser::_RetrieveRootNodeAndNamespace(IStream *,ushort * *,ushort * *)

- ea: `0x1800327a0`
- end: `0x180032941`
- name: `?_RetrieveRootNodeAndNamespace@CXMLPropStoreSaxParser@@AEAAJPEAUIStream@@PEAPEAG1@Z`
- size: `417`
- prototype: `int(CXMLPropStoreSaxParser *__hidden this, struct IStream *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800301f0`

## callees

- `0x180012550`
- `0x180023940`
- `0x18002d5a0`
- `0x18002d900`
- `0x18002f100`
- `0x1800327a0`
- `0x180037010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800328c7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800328c7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032801`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032801`

## pseudocode

```c
__int64 __fastcall CXMLPropStoreSaxParser::_RetrieveRootNodeAndNamespace(
        CXMLPropStoreSaxParser *this,
        struct IStream *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  HRESULT Instance; // edi
  int v8; // ebx
  _QWORD v10[4]; // [rsp+30h] [rbp-49h] BYREF
  LPVOID ppv[2]; // [rsp+50h] [rbp-29h] BYREF
  _QWORD v12[2]; // [rsp+60h] [rbp-19h] BYREF
  __int128 v13; // [rsp+70h] [rbp-9h]
  __int128 v14; // [rsp+80h] [rbp+7h]
  __int128 v15; // [rsp+90h] [rbp+17h]

  *a3 = 0;
  *a4 = 0;
  ppv[0] = 0;
  Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(ppv);
  Instance = CoCreateInstance(&CLSID_SAXXMLReader60, 0, 1u, &GUID_a4f96ed0_f829_476e_81c0_cdc7bd2a0802, ppv);
  if ( Instance >= 0 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISAXContentHandler>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISAXContentHandler>(v12);
    v12[0] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ISAXContentHandler>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v12[0] = &CXMLPropStoreSaxParser::CStubSaxParser2::`vftable';
    v13 = 0;
    v14 = 0;
    v15 = 0;
    Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)ppv[0] + 80LL))(ppv[0], v12);
    if ( Instance >= 0 )
    {
      v10[2] = 0;
      v10[0] = 13;
      v10[1] = a2;
      v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)ppv[0] + 152LL))(ppv[0], v10);
      Instance = v8 != -2147467260 ? 0x8000FFFF : 0;
      IStream_Reset(a2);
      if ( v8 == -2147467260 )
        Instance = CXMLPropStoreSaxParser::CStubSaxParser2::RetrieveRootNodeAndNamespace(
                     (CXMLPropStoreSaxParser::CStubSaxParser2 *)v12,
                     a3,
                     a4);
    }
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv[0] + 112LL))(ppv[0], 0);
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv[0] + 80LL))(ppv[0], 0);
    CXMLPropStoreSaxParser::CStubSaxParser2::~CStubSaxParser2((CXMLPropStoreSaxParser::CStubSaxParser2 *)v12);
  }
  Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800327a0  mov     [rsp-8+arg_0], rbx
0x1800327a5  push    rbp
0x1800327a6  push    rsi
0x1800327a7  push    rdi
0x1800327a8  push    r14
0x1800327aa  push    r15
0x1800327ac  lea     rbp, [rsp-37h]
0x1800327b1  sub     rsp, 0B0h
0x1800327b8  mov     rax, cs:__security_cookie
0x1800327bf  xor     rax, rsp
0x1800327c2  mov     [rbp+57h+var_30], rax
0x1800327c6  xor     ebx, ebx
0x1800327c8  lea     rcx, [rbp+57h+var_80]
0x1800327cc  mov     [r8], rbx
0x1800327cf  mov     r14, r9
0x1800327d2  mov     [r9], rbx
0x1800327d5  mov     rsi, r8
0x1800327d8  mov     r15, rdx
0x1800327db  mov     [rbp+57h+var_80], rbx
0x1800327df  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x1800327e4  lea     rax, [rbp+57h+var_80]
0x1800327e8  xor     edx, edx; pUnkOuter
0x1800327ea  lea     r9, _GUID_a4f96ed0_f829_476e_81c0_cdc7bd2a0802; riid
0x1800327f1  mov     [rsp+0D0h+ppv], rax; ppv
0x1800327f6  lea     r8d, [rbx+1]; dwClsContext
0x1800327fa  lea     rcx, CLSID_SAXXMLReader60; rclsid
0x180032801  call    cs:__imp_CoCreateInstance
0x180032807  mov     edi, eax
0x180032809  test    eax, eax
0x18003280b  js      loc_180032913
0x180032811  lea     rcx, [rbp+57h+var_70]
0x180032815  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UISAXContentHandler@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISAXContentHandler>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISAXContentHandler>(void)
0x18003281a  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UISAXContentHandler@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ISAXContentHandler>::`vftable'
0x180032821  mov     [rbp+57h+var_70], rcx
0x180032825  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18003282c  test    rcx, rcx
0x18003282f  jz      short loc_18003283D
0x180032831  mov     rax, [rcx]
0x180032834  mov     rax, [rax+8]
0x180032838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003283d  mov     rcx, [rbp+57h+var_80]
0x180032841  lea     rax, ??_7CStubSaxParser2@CXMLPropStoreSaxParser@@6B@; const CXMLPropStoreSaxParser::CStubSaxParser2::`vftable'
0x180032848  xorps   xmm0, xmm0
0x18003284b  mov     [rbp+57h+var_70], rax
0x18003284f  xorps   xmm1, xmm1
0x180032852  movdqa  [rbp+57h+var_60], xmm0
0x180032857  movdqa  [rbp+57h+var_50], xmm1
0x18003285c  lea     rdx, [rbp+57h+var_70]
0x180032860  movdqa  [rbp+57h+var_40], xmm0
0x180032865  mov     rax, [rcx]
0x180032868  mov     rax, [rax+50h]
0x18003286c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032871  mov     edi, eax
0x180032873  test    eax, eax
0x180032875  js      short loc_1800328E6
0x180032877  mov     rcx, [rbp+57h+var_80]
0x18003287b  xor     edx, edx
0x18003287d  xorps   xmm0, xmm0
0x180032880  mov     [rbp+57h+var_90], rdx
0x180032884  movups  [rbp+57h+var_A0], xmm0
0x180032888  mov     qword ptr [rbp+57h+var_A0+8], r15
0x18003288c  lea     eax, [rdx+0Dh]
0x18003288f  mov     word ptr [rbp+57h+var_A0], ax
0x180032893  lea     rdx, [rbp+57h+var_A0]
0x180032897  mov     rax, [rcx]
0x18003289a  movups  xmm0, [rbp+57h+var_A0]
0x18003289e  mov     rax, [rax+98h]
0x1800328a5  movaps  [rbp+57h+var_A0], xmm0
0x1800328a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328ae  mov     r9d, 80004004h
0x1800328b4  mov     rcx, r15; pstm
0x1800328b7  sub     r9d, eax
0x1800328ba  mov     ebx, eax
0x1800328bc  neg     r9d
0x1800328bf  sbb     edi, edi
0x1800328c1  and     edi, 8000FFFFh
0x1800328c7  call    cs:__imp_IStream_Reset
0x1800328cd  cmp     ebx, 80004004h
0x1800328d3  jnz     short loc_1800328E6
0x1800328d5  mov     r8, r14; unsigned __int16 **
0x1800328d8  lea     rcx, [rbp+57h+var_70]; this
0x1800328dc  mov     rdx, rsi; unsigned __int16 **
0x1800328df  call    ?RetrieveRootNodeAndNamespace@CStubSaxParser2@CXMLPropStoreSaxParser@@QEAAJPEAPEAG0@Z; CXMLPropStoreSaxParser::CStubSaxParser2::RetrieveRootNodeAndNamespace(ushort * *,ushort * *)
0x1800328e4  mov     edi, eax
0x1800328e6  mov     rcx, [rbp+57h+var_80]
0x1800328ea  xor     edx, edx
0x1800328ec  mov     rax, [rcx]
0x1800328ef  mov     rax, [rax+70h]
0x1800328f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328f8  mov     rcx, [rbp+57h+var_80]
0x1800328fc  xor     edx, edx
0x1800328fe  mov     rax, [rcx]
0x180032901  mov     rax, [rax+50h]
0x180032905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003290a  lea     rcx, [rbp+57h+var_70]; this
0x18003290e  call    ??1CStubSaxParser2@CXMLPropStoreSaxParser@@UEAA@XZ; CXMLPropStoreSaxParser::CStubSaxParser2::~CStubSaxParser2(void)
0x180032913  lea     rcx, [rbp+57h+var_80]
0x180032917  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x18003291c  mov     eax, edi
0x18003291e  mov     rcx, [rbp+57h+var_30]
0x180032922  xor     rcx, rsp; StackCookie
0x180032925  call    __security_check_cookie
0x18003292a  mov     rbx, [rsp+0D0h+arg_0]
0x180032932  add     rsp, 0B0h
0x180032939  pop     r15
0x18003293b  pop     r14
0x18003293d  pop     rdi
0x18003293e  pop     rsi
0x18003293f  pop     rbp
0x180032940  retn
```
