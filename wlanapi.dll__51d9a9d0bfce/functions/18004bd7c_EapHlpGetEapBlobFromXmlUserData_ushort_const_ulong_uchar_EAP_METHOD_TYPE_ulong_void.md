# EapHlpGetEapBlobFromXmlUserData(ushort const *,ulong,uchar *,_EAP_METHOD_TYPE *,ulong *,void * *)

- ea: `0x18004bd7c`
- end: `0x18004bfde`
- name: `?EapHlpGetEapBlobFromXmlUserData@@YAKPEBGKPEAEPEAU_EAP_METHOD_TYPE@@PEAKPEAPEAX@Z`
- size: `610`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, unsigned int@<edx>, unsigned __int8 *@<r8>, struct _EAP_METHOD_TYPE *@<r9>, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020d40`

## callees

- `0x180009654`
- `0x18000f8f4`
- `0x18000f948`
- `0x180011e40`
- `0x180017140`
- `0x180019a20`
- `0x18003af3c`
- `0x18003af80`
- `0x18004b388`
- `0x18004b9c4`
- `0x18004bb34`
- `0x18004bd7c`
- `0x18006013c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004bfb4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004bfb4`
- `eappcfg!EapHostPeerFreeMemory` at `0x18004bf6f`
- `eappcfg!EapHostPeerFreeMemory` at `0x18004bf6f`
- `eappcfg!EapHostPeerCredentialsXml2Blob` at `0x18004bf03`
- `eappcfg!EapHostPeerCredentialsXml2Blob` at `0x18004bf03`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18004bf7f`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18004bf7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EapHlpGetEapBlobFromXmlUserData(
        const unsigned __int16 *a1,
        DWORD a2,
        unsigned __int8 *a3,
        struct _EAP_METHOD_TYPE *a4,
        unsigned int *a5,
        void **a6)
{
  void *v8; // r14
  DWORD v9; // edi
  const unsigned __int16 *v10; // rdx
  struct IXMLDOMDocument2 *v11; // rbx
  int v12; // eax
  unsigned int v13; // r8d
  const char *v14; // r9
  __int64 v16; // [rsp+0h] [rbp-D8h] BYREF
  DWORD pdwSizeOfCredentialsOut; // [rsp+40h] [rbp-98h] BYREF
  DWORD dwSizeOfConfigIn; // [rsp+44h] [rbp-94h]
  int v19; // [rsp+48h] [rbp-90h] BYREF
  int v20; // [rsp+4Ch] [rbp-8Ch] BYREF
  IXMLDOMNode *pCredentialsDoc; // [rsp+50h] [rbp-88h] BYREF
  void *v22; // [rsp+58h] [rbp-80h] BYREF
  BYTE *pData; // [rsp+60h] [rbp-78h] BYREF
  struct IXMLDOMDocument2 *v24; // [rsp+68h] [rbp-70h] BYREF
  EAP_ERROR *pEapError; // [rsp+70h] [rbp-68h] BYREF
  BYTE *pConfigIn; // [rsp+78h] [rbp-60h]
  EAP_METHOD_TYPE pEapMethodType; // [rsp+80h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  pConfigIn = a3;
  dwSizeOfConfigIn = a2;
  v20 = 0;
  v24 = 0;
  ATL::CComPtr<IXMLDOMElement>::CComPtr<IXMLDOMElement>(&pCredentialsDoc);
  v19 = 0;
  pEapMethodType = 0;
  pdwSizeOfCredentialsOut = 0;
  pData = 0;
  pEapError = 0;
  v8 = 0;
  v22 = 0;
  v9 = CXcSmartCoInit::Init((CXcSmartCoInit *)&v20);
  if ( v9 )
    goto LABEL_15;
  v9 = XcCreateXmlDoc(0, 0, &v24);
  if ( v9 )
    goto LABEL_15;
  v10 = a1;
  v11 = v24;
  v9 = XcLoadXml(v24, v10, &v19);
  if ( v9 )
    goto LABEL_15;
  if ( !v19 )
    goto LABEL_14;
  v12 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, IXMLDOMNode **))v11->lpVtbl->get_documentElement)(
          v11,
          &pCredentialsDoc);
  v9 = v12;
  if ( v12 < 0 )
  {
    if ( (v12 & 0x1FFF0000) == 0x70000 )
      v9 = (unsigned __int16)v12;
    goto LABEL_15;
  }
  if ( v12 == 1 || (unsigned __int8)ATL::CComPtrBase<IXMLDOMElement>::operator!(&pCredentialsDoc) )
  {
LABEL_14:
    v9 = 1206;
    goto LABEL_15;
  }
  try
  {
    CheckCredentialXmlMatchesEapType((struct IXMLDOMElement *)pCredentialsDoc, a4);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, &v16, v13, v14);
    dwSizeOfConfigIn = 1206;
    v9 = 1206;
    v8 = v22;
    goto LABEL_15;
  }
  v9 = EapHostPeerCredentialsXml2Blob(
         0x80u,
         pCredentialsDoc,
         dwSizeOfConfigIn,
         pConfigIn,
         &pdwSizeOfCredentialsOut,
         &pData,
         &pEapMethodType,
         &pEapError);
  if ( !v9 )
  {
    v9 = AllocateWLMemory(pdwSizeOfCredentialsOut, &v22);
    v8 = v22;
    if ( !v9 )
    {
      memcpy_0(v22, pData, pdwSizeOfCredentialsOut);
      *a4 = pEapMethodType;
      *a6 = v8;
      *a5 = pdwSizeOfCredentialsOut;
    }
  }
LABEL_15:
  if ( pData )
    EapHostPeerFreeMemory(pData);
  if ( pEapError )
    EapHostPeerFreeErrorMemory(pEapError);
  if ( v9 && v8 )
    FreeWLMemory(v8);
  ATL::CComPtr<IXMLDOMElement>::~CComPtr<IXMLDOMElement>(&pCredentialsDoc);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v24);
  if ( v20 )
    CoUninitialize();
  return v9;
}

```

## disassembly

```asm
0x18004bd7c  push    rbx
0x18004bd7e  push    rdi
0x18004bd7f  push    r12
0x18004bd81  push    r13
0x18004bd83  push    r14
0x18004bd85  push    r15
0x18004bd87  sub     rsp, 0A8h
0x18004bd8e  mov     rax, cs:__security_cookie
0x18004bd95  xor     rax, rsp
0x18004bd98  mov     [rsp+0D8h+var_48], rax
0x18004bda0  mov     r15, r9
0x18004bda3  mov     [rsp+0D8h+pConfigIn], r8
0x18004bda8  mov     [rsp+0D8h+dwSizeOfConfigIn], edx
0x18004bdac  mov     rbx, rcx
0x18004bdaf  mov     r12, [rsp+0D8h+arg_20]
0x18004bdb7  mov     r13, [rsp+0D8h+arg_28]
0x18004bdbf  mov     [rsp+0D8h+var_8C], 0
0x18004bdc7  mov     [rsp+0D8h+var_70], 0
0x18004bdd0  lea     rcx, [rsp+0D8h+pCredentialsDoc]
0x18004bdd5  call    ??0?$CComPtr@UIXMLDOMElement@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMElement>::CComPtr<IXMLDOMElement>(void)
0x18004bdda  nop
0x18004bddb  mov     [rsp+0D8h+var_90], 0
0x18004bde3  xorps   xmm0, xmm0
0x18004bde6  movups  xmmword ptr [rsp+0D8h+var_58.eapType.type], xmm0
0x18004bdee  mov     [rsp+0D8h+var_98], 0
0x18004bdf6  mov     [rsp+0D8h+pData], 0
0x18004bdff  mov     [rsp+0D8h+pEapError], 0
0x18004be08  xor     r14d, r14d
0x18004be0b  mov     [rsp+0D8h+var_80], r14
0x18004be10  lea     rcx, [rsp+0D8h+var_8C]; this
0x18004be15  call    ?Init@CXcSmartCoInit@@QEAAKXZ; CXcSmartCoInit::Init(void)
0x18004be1a  mov     edi, eax
0x18004be1c  test    eax, eax
0x18004be1e  jnz     loc_18004BF65
0x18004be24  lea     r8, [rsp+0D8h+var_70]; struct IXMLDOMDocument2 **
0x18004be29  xor     edx, edx; struct IXMLDOMSchemaCollection *
0x18004be2b  xor     ecx, ecx; psz
0x18004be2d  call    ?XcCreateXmlDoc@@YAKPEBGPEAUIXMLDOMSchemaCollection@@PEAPEAUIXMLDOMDocument2@@@Z; XcCreateXmlDoc(ushort const *,IXMLDOMSchemaCollection *,IXMLDOMDocument2 * *)
0x18004be32  mov     edi, eax
0x18004be34  test    eax, eax
0x18004be36  jnz     loc_18004BF65
0x18004be3c  lea     r8, [rsp+0D8h+var_90]; int *
0x18004be41  mov     rdx, rbx; unsigned __int16 *
0x18004be44  mov     rbx, [rsp+0D8h+var_70]
0x18004be49  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18004be4c  call    ?XcLoadXml@@YAKPEAUIXMLDOMDocument2@@PEBGPEAH@Z; XcLoadXml(IXMLDOMDocument2 *,ushort const *,int *)
0x18004be51  mov     edi, eax
0x18004be53  test    eax, eax
0x18004be55  jnz     loc_18004BF65
0x18004be5b  cmp     [rsp+0D8h+var_90], r14d
0x18004be60  jz      loc_18004BF60
0x18004be66  mov     rax, [rbx]
0x18004be69  lea     rdx, [rsp+0D8h+pCredentialsDoc]
0x18004be6e  mov     rcx, rbx
0x18004be71  mov     rax, [rax+168h]
0x18004be78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be7d  mov     edi, eax
0x18004be7f  test    eax, eax
0x18004be81  jns     short loc_18004BE9B
0x18004be83  and     eax, 1FFF0000h
0x18004be88  cmp     eax, 70000h
0x18004be8d  jnz     loc_18004BF65
0x18004be93  movzx   edi, di
0x18004be96  jmp     loc_18004BF65
0x18004be9b  cmp     edi, 1
0x18004be9e  jz      loc_18004BF60
0x18004bea4  lea     rcx, [rsp+0D8h+pCredentialsDoc]
0x18004bea9  call    ??7?$CComPtrBase@UIXMLDOMElement@@@ATL@@QEBA_NXZ; ATL::CComPtrBase<IXMLDOMElement>::operator!(void)
0x18004beae  test    al, al
0x18004beb0  jnz     loc_18004BF60
0x18004beb6  mov     rdx, r15; struct _EAP_METHOD_TYPE *
0x18004beb9  mov     rcx, [rsp+0D8h+pCredentialsDoc]; struct IXMLDOMElement *
0x18004bebe  call    ?CheckCredentialXmlMatchesEapType@@YAXPEAUIXMLDOMElement@@AEAU_EAP_METHOD_TYPE@@@Z; CheckCredentialXmlMatchesEapType(IXMLDOMElement *,_EAP_METHOD_TYPE &)
0x18004bec3  nop
0x18004bec4  lea     rax, [rsp+0D8h+pEapError]
0x18004bec9  mov     [rsp+0D8h+ppEapError], rax; ppEapError
0x18004bece  lea     rax, [rsp+0D8h+var_58]
0x18004bed6  mov     [rsp+0D8h+pEapMethodType], rax; pEapMethodType
0x18004bedb  lea     rax, [rsp+0D8h+pData]
0x18004bee0  mov     [rsp+0D8h+ppCredentialsOut], rax; ppCredentialsOut
0x18004bee5  lea     rax, [rsp+0D8h+var_98]
0x18004beea  mov     [rsp+0D8h+pdwSizeOfCredentialsOut], rax; pdwSizeOfCredentialsOut
0x18004beef  mov     r9, [rsp+0D8h+pConfigIn]; pConfigIn
0x18004bef4  mov     r8d, [rsp+0D8h+dwSizeOfConfigIn]; dwSizeOfConfigIn
0x18004bef9  mov     rdx, [rsp+0D8h+pCredentialsDoc]; pCredentialsDoc
0x18004befe  mov     ecx, 80h; dwFlags
0x18004bf03  call    cs:__imp_EapHostPeerCredentialsXml2Blob
0x18004bf09  mov     edi, eax
0x18004bf0b  test    eax, eax
0x18004bf0d  jnz     short loc_18004BF65
0x18004bf0f  mov     ecx, [rsp+0D8h+var_98]
0x18004bf13  lea     rdx, [rsp+0D8h+var_80]
0x18004bf18  call    AllocateWLMemory
0x18004bf1d  mov     edi, eax
0x18004bf1f  mov     r14, [rsp+0D8h+var_80]
0x18004bf24  test    eax, eax
0x18004bf26  jnz     short loc_18004BF65
0x18004bf28  mov     r8d, [rsp+0D8h+var_98]; Size
0x18004bf2d  mov     rdx, [rsp+0D8h+pData]; Src
0x18004bf32  mov     rcx, r14; void *
0x18004bf35  call    memcpy_0
0x18004bf3a  movups  xmm0, xmmword ptr [rsp+0D8h+var_58.eapType.type]
0x18004bf42  movdqu  xmmword ptr [r15], xmm0
0x18004bf47  mov     [r13+0], r14
0x18004bf4b  mov     eax, [rsp+0D8h+var_98]
0x18004bf4f  mov     [r12], eax
0x18004bf53  jmp     short loc_18004BF65
0x18004bf55  mov     edi, [rsp+0D8h+dwSizeOfConfigIn]
0x18004bf59  mov     r14, [rsp+0D8h+var_80]
0x18004bf5e  jmp     short loc_18004BF65
0x18004bf60  mov     edi, 4B6h
0x18004bf65  mov     rcx, [rsp+0D8h+pData]; pData
0x18004bf6a  test    rcx, rcx
0x18004bf6d  jz      short loc_18004BF75
0x18004bf6f  call    cs:__imp_EapHostPeerFreeMemory
0x18004bf75  mov     rcx, [rsp+0D8h+pEapError]; pEapError
0x18004bf7a  test    rcx, rcx
0x18004bf7d  jz      short loc_18004BF85
0x18004bf7f  call    cs:__imp_EapHostPeerFreeErrorMemory
0x18004bf85  test    edi, edi
0x18004bf87  jz      short loc_18004BF97
0x18004bf89  test    r14, r14
0x18004bf8c  jz      short loc_18004BF97
0x18004bf8e  mov     rcx, r14
0x18004bf91  call    FreeWLMemory
0x18004bf96  nop
0x18004bf97  lea     rcx, [rsp+0D8h+pCredentialsDoc]
0x18004bf9c  call    ??1?$CComPtr@UIXMLDOMElement@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMElement>::~CComPtr<IXMLDOMElement>(void)
0x18004bfa1  nop
0x18004bfa2  lea     rcx, [rsp+0D8h+var_70]
0x18004bfa7  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18004bfac  nop
0x18004bfad  cmp     [rsp+0D8h+var_8C], 0
0x18004bfb2  jz      short loc_18004BFBA
0x18004bfb4  call    cs:__imp_CoUninitialize
0x18004bfba  mov     eax, edi
0x18004bfbc  mov     rcx, [rsp+0D8h+var_48]
0x18004bfc4  xor     rcx, rsp; StackCookie
0x18004bfc7  call    __security_check_cookie
0x18004bfcc  add     rsp, 0A8h
0x18004bfd3  pop     r15
0x18004bfd5  pop     r14
0x18004bfd7  pop     r13
0x18004bfd9  pop     r12
0x18004bfdb  pop     rdi
0x18004bfdc  pop     rbx
0x18004bfdd  retn
```
