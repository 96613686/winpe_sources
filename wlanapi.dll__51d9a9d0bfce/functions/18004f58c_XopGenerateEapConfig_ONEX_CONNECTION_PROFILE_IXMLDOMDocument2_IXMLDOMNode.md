# XopGenerateEapConfig(_ONEX_CONNECTION_PROFILE *,IXMLDOMDocument2 *,IXMLDOMNode *)

- ea: `0x18004f58c`
- end: `0x18004f7d8`
- name: `?XopGenerateEapConfig@@YAKPEAU_ONEX_CONNECTION_PROFILE@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z`
- size: `588`
- prototype: `unsigned int __fastcall(struct _ONEX_CONNECTION_PROFILE *, struct IXMLDOMDocument2 *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004efd0`

## callees

- `0x180009654`
- `0x18000dea8`
- `0x18000ec9c`
- `0x180017140`
- `0x180019370`
- `0x18004b388`
- `0x18004dd84`
- `0x18004f58c`
- `0x18006013c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f665`
- `eappcfg!EapHostPeerConfigBlob2Xml` at `0x18004f71d`
- `eappcfg!EapHostPeerConfigBlob2Xml` at `0x18004f71d`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18004f794`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18004f794`

## string_xrefs

- `0x18004f5d0`: `http://www.microsoft.com/networking/OneX/v1`
- `0x18004f5d7`: `EAPConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XopGenerateEapConfig(
        struct _ONEX_CONNECTION_PROFILE *a1,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMNode *a3)
{
  void *v4; // rdi
  struct IXMLDOMNode *v5; // r10
  struct IXMLDOMDocument2 *v6; // r11
  DWORD LastError; // ebx
  char *v8; // r9
  EAP_METHOD_TYPE v9; // xmm6
  __int64 v10; // r9
  __int64 v11; // r10
  __int64 v12; // r9
  __int64 v13; // r10
  DWORD v14; // ebx
  char *v15; // r9
  __int64 v16; // r9
  __int64 v17; // r10
  __int64 v18; // r9
  __int64 v19; // r10
  int v20; // eax
  int v21; // eax
  struct IXMLDOMNode *v23; // [rsp+30h] [rbp-19h] BYREF
  IXMLDOMDocument2 *ppConfigDoc; // [rsp+38h] [rbp-11h] BYREF
  EAP_ERROR *pEapError; // [rsp+40h] [rbp-9h] BYREF
  __int128 v26; // [rsp+50h] [rbp+7h] BYREF
  EAP_METHOD_TYPE eapMethodType; // [rsp+60h] [rbp+17h] BYREF
  __int64 v28; // [rsp+C8h] [rbp+7Fh] BYREF

  v4 = 0;
  pEapError = 0;
  ppConfigDoc = 0;
  v23 = 0;
  ATL::CComPtr<IXMLDOMElement>::CComPtr<IXMLDOMElement>(&v28);
  LastError = XcAddChildElement(
                v6,
                v5,
                (OLECHAR *)L"EAPConfig",
                (OLECHAR *)L"http://www.microsoft.com/networking/OneX/v1",
                0,
                &v23);
  if ( !LastError )
  {
    v8 = (char *)a1 + *((unsigned int *)a1 + 16);
    v9 = *(EAP_METHOD_TYPE *)(v8 + 4);
    if ( (v8[20] & 1) == 0
      || (v26 = *(_OWORD *)(v8 + 4), eapMethodType = v9, (unsigned int)AreDifferentEapTypes(&eapMethodType, &v26))
      || (v11 = *(unsigned int *)(v10 + 28),
          eapMethodType = v9,
          v26 = *(_OWORD *)(v11 + v10),
          (unsigned int)AreDifferentEapTypes(&v26, &eapMethodType)) )
    {
      v14 = 0;
      v4 = 0;
    }
    else
    {
      v14 = *(_DWORD *)(v13 + v12 + 16);
      v4 = Xc_Process_user_allocate(v14);
      if ( !v4 )
      {
        LastError = GetLastError();
        goto LABEL_24;
      }
      v15 = (char *)a1 + *((unsigned int *)a1 + 16);
      if ( (v15[20] & 1) == 0
        || (eapMethodType = v9, v26 = *(_OWORD *)(v15 + 4), (unsigned int)AreDifferentEapTypes(&v26, &eapMethodType))
        || (v17 = *(unsigned int *)(v16 + 28),
            eapMethodType = v9,
            v26 = *(_OWORD *)(v17 + v16),
            (unsigned int)AreDifferentEapTypes(&v26, &eapMethodType)) )
      {
        LastError = 1168;
        goto LABEL_24;
      }
      if ( v14 < *(_DWORD *)(v19 + v18 + 16) )
      {
        LastError = 122;
        goto LABEL_24;
      }
      memcpy_0(v4, (const void *)(v19 + v18 + 20), *(unsigned int *)(v19 + v18 + 16));
    }
    eapMethodType = v9;
    LastError = EapHostPeerConfigBlob2Xml(0x80u, &eapMethodType, v14, (BYTE *)v4, &ppConfigDoc, &pEapError);
    if ( !LastError )
    {
      v20 = ((__int64 (__fastcall *)(IXMLDOMDocument2 *, __int64 *))ppConfigDoc->lpVtbl->get_documentElement)(
              ppConfigDoc,
              &v28);
      LastError = v20;
      if ( v20 >= 0 )
        goto LABEL_20;
      if ( (v20 & 0x1FFF0000) == 0x70000 )
        LastError = (unsigned __int16)v20;
      if ( !LastError )
      {
LABEL_20:
        v21 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, _QWORD))v23->lpVtbl->appendChild)(v23, v28, 0);
        LastError = v21;
        if ( v21 < 0 )
        {
          if ( (v21 & 0x1FFF0000) == 0x70000 )
            LastError = (unsigned __int16)v21;
        }
        else
        {
          LastError = 0;
        }
      }
    }
  }
LABEL_24:
  if ( pEapError )
    EapHostPeerFreeErrorMemory(pEapError);
  if ( v4 )
    Xc_Process_user_free(v4);
  ATL::CComPtr<IXMLDOMElement>::~CComPtr<IXMLDOMElement>(&v28);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v23);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&ppConfigDoc);
  return LastError;
}

```

## disassembly

```asm
0x18004f58c  push    rbp
0x18004f58e  push    rbx
0x18004f58f  push    rsi
0x18004f590  push    rdi
0x18004f591  lea     rbp, [rsp-3Fh]
0x18004f596  sub     rsp, 88h
0x18004f59d  movaps  [rsp+0A0h+var_30], xmm6
0x18004f5a2  mov     r10, r8
0x18004f5a5  mov     r11, rdx
0x18004f5a8  mov     rsi, rcx
0x18004f5ab  xor     edi, edi
0x18004f5ad  mov     [rbp+57h+pEapError], rdi
0x18004f5b1  mov     [rbp+57h+var_68], rdi
0x18004f5b5  mov     [rbp+57h+var_70], rdi
0x18004f5b9  lea     rcx, [rbp+57h+arg_18]
0x18004f5bd  call    ??0?$CComPtr@UIXMLDOMElement@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMElement>::CComPtr<IXMLDOMElement>(void)
0x18004f5c2  lea     rcx, [rbp+57h+var_70]
0x18004f5c6  mov     [rsp+0A0h+ppEapError], rcx; struct IXMLDOMNode **
0x18004f5cb  mov     [rsp+0A0h+ppConfigDoc], rdi; OLECHAR *
0x18004f5d0  lea     r9, aHttpWwwMicroso_0; "http://www.microsoft.com/networking/One"...
0x18004f5d7  lea     r8, aEapconfig; "EAPConfig"
0x18004f5de  mov     rdx, r10; struct IXMLDOMNode *
0x18004f5e1  mov     rcx, r11; struct IXMLDOMDocument2 *
0x18004f5e4  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18004f5e9  mov     ebx, eax
0x18004f5eb  test    eax, eax
0x18004f5ed  jnz     loc_18004F78B
0x18004f5f3  mov     r9d, [rsi+40h]
0x18004f5f7  add     r9, rsi
0x18004f5fa  movups  xmm6, xmmword ptr [r9+4]
0x18004f5ff  test    byte ptr [r9+14h], 1
0x18004f604  jz      loc_18004F6F3
0x18004f60a  movdqu  [rbp+57h+var_50], xmm6
0x18004f60f  movdqu  xmmword ptr [rbp+57h+eapMethodType.eapType.type], xmm6
0x18004f614  lea     rdx, [rbp+57h+var_50]
0x18004f618  lea     rcx, [rbp+57h+eapMethodType]
0x18004f61c  call    AreDifferentEapTypes
0x18004f621  test    eax, eax
0x18004f623  jnz     loc_18004F6F3
0x18004f629  mov     r10d, [r9+1Ch]
0x18004f62d  movdqu  xmmword ptr [rbp+57h+eapMethodType.eapType.type], xmm6
0x18004f632  movups  xmm1, xmmword ptr [r10+r9]
0x18004f637  movdqu  [rbp+57h+var_50], xmm1
0x18004f63c  lea     rdx, [rbp+57h+eapMethodType]
0x18004f640  lea     rcx, [rbp+57h+var_50]
0x18004f644  call    AreDifferentEapTypes
0x18004f649  test    eax, eax
0x18004f64b  jnz     loc_18004F6F3
0x18004f651  mov     ebx, [r10+r9+10h]
0x18004f656  mov     ecx, ebx; dwBytes
0x18004f658  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x18004f65d  mov     rdi, rax
0x18004f660  test    rax, rax
0x18004f663  jnz     short loc_18004F672
0x18004f665  call    cs:__imp_GetLastError
0x18004f66b  mov     ebx, eax
0x18004f66d  jmp     loc_18004F78B
0x18004f672  mov     r9d, [rsi+40h]
0x18004f676  add     r9, rsi
0x18004f679  test    byte ptr [r9+14h], 1
0x18004f67e  jz      short loc_18004F6E9
0x18004f680  movdqa  xmmword ptr [rbp+57h+eapMethodType.eapType.type], xmm6
0x18004f685  movups  xmm0, xmmword ptr [r9+4]
0x18004f68a  movdqu  [rbp+57h+var_50], xmm0
0x18004f68f  lea     rdx, [rbp+57h+eapMethodType]
0x18004f693  lea     rcx, [rbp+57h+var_50]
0x18004f697  call    AreDifferentEapTypes
0x18004f69c  test    eax, eax
0x18004f69e  jnz     short loc_18004F6E9
0x18004f6a0  mov     r10d, [r9+1Ch]
0x18004f6a4  movdqa  xmmword ptr [rbp+57h+eapMethodType.eapType.type], xmm6
0x18004f6a9  movups  xmm0, xmmword ptr [r10+r9]
0x18004f6ae  movdqu  [rbp+57h+var_50], xmm0
0x18004f6b3  lea     rdx, [rbp+57h+eapMethodType]
0x18004f6b7  lea     rcx, [rbp+57h+var_50]
0x18004f6bb  call    AreDifferentEapTypes
0x18004f6c0  test    eax, eax
0x18004f6c2  jnz     short loc_18004F6E9
0x18004f6c4  cmp     ebx, [r10+r9+10h]
0x18004f6c9  jnb     short loc_18004F6D3
0x18004f6cb  lea     ebx, [rax+7Ah]
0x18004f6ce  jmp     loc_18004F78B
0x18004f6d3  mov     r8d, [r10+r9+10h]; Size
0x18004f6d8  lea     rdx, [r9+14h]
0x18004f6dc  add     rdx, r10; Src
0x18004f6df  mov     rcx, rdi; void *
0x18004f6e2  call    memcpy_0
0x18004f6e7  jmp     short loc_18004F6F7
0x18004f6e9  mov     ebx, 490h
0x18004f6ee  jmp     loc_18004F78B
0x18004f6f3  xor     ebx, ebx
0x18004f6f5  xor     edi, edi
0x18004f6f7  movdqa  xmmword ptr [rbp+57h+eapMethodType.eapType.type], xmm6
0x18004f6fc  lea     rax, [rbp+57h+pEapError]
0x18004f700  mov     [rsp+0A0h+ppEapError], rax; ppEapError
0x18004f705  lea     rax, [rbp+57h+var_68]
0x18004f709  mov     [rsp+0A0h+ppConfigDoc], rax; ppConfigDoc
0x18004f70e  mov     r9, rdi; pConfigIn
0x18004f711  mov     r8d, ebx; dwSizeOfConfigIn
0x18004f714  lea     rdx, [rbp+57h+eapMethodType]; eapMethodType
0x18004f718  mov     ecx, 80h; dwFlags
0x18004f71d  call    cs:__imp_EapHostPeerConfigBlob2Xml
0x18004f723  mov     ebx, eax
0x18004f725  test    eax, eax
0x18004f727  jnz     short loc_18004F78B
0x18004f729  mov     rcx, [rbp+57h+var_68]
0x18004f72d  mov     rax, [rcx]
0x18004f730  lea     rdx, [rbp+57h+arg_18]
0x18004f734  mov     rax, [rax+168h]
0x18004f73b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f740  mov     ebx, eax
0x18004f742  mov     esi, 1FFF0000h
0x18004f747  test    eax, eax
0x18004f749  jns     short loc_18004F75B
0x18004f74b  and     eax, esi
0x18004f74d  cmp     eax, 70000h
0x18004f752  jnz     short loc_18004F757
0x18004f754  movzx   ebx, bx
0x18004f757  test    ebx, ebx
0x18004f759  jnz     short loc_18004F78B
0x18004f75b  mov     rcx, [rbp+57h+var_70]
0x18004f75f  mov     rax, [rcx]
0x18004f762  xor     r8d, r8d
0x18004f765  mov     rdx, [rbp+57h+arg_18]
0x18004f769  mov     rax, [rax+0A8h]
0x18004f770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f775  mov     ebx, eax
0x18004f777  test    eax, eax
0x18004f779  js      short loc_18004F77F
0x18004f77b  xor     ebx, ebx
0x18004f77d  jmp     short loc_18004F78B
0x18004f77f  and     eax, esi
0x18004f781  cmp     eax, 70000h
0x18004f786  jnz     short loc_18004F78B
0x18004f788  movzx   ebx, bx
0x18004f78b  mov     rcx, [rbp+57h+pEapError]; pEapError
0x18004f78f  test    rcx, rcx
0x18004f792  jz      short loc_18004F79A
0x18004f794  call    cs:__imp_EapHostPeerFreeErrorMemory
0x18004f79a  test    rdi, rdi
0x18004f79d  jz      short loc_18004F7A7
0x18004f79f  mov     rcx, rdi; lpMem
0x18004f7a2  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18004f7a7  lea     rcx, [rbp+57h+arg_18]
0x18004f7ab  call    ??1?$CComPtr@UIXMLDOMElement@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMElement>::~CComPtr<IXMLDOMElement>(void)
0x18004f7b0  nop
0x18004f7b1  lea     rcx, [rbp+57h+var_70]
0x18004f7b5  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18004f7ba  nop
0x18004f7bb  lea     rcx, [rbp+57h+var_68]
0x18004f7bf  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18004f7c4  nop
0x18004f7c5  mov     eax, ebx
0x18004f7c7  movaps  xmm6, [rsp+0A0h+var_30]
0x18004f7cc  add     rsp, 88h
0x18004f7d3  pop     rdi
0x18004f7d4  pop     rsi
0x18004f7d5  pop     rbx
0x18004f7d6  pop     rbp
0x18004f7d7  retn
```
