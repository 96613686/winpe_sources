# XwpParseSSIDConfigSSIDNodes(ulong,ATL::CComPtr<IXMLDOMNodeList>,DOT11_SSID_LIST * *,ulong,int,ulong *,int *)

- ea: `0x180046a18`
- end: `0x180046c5d`
- name: `?XwpParseSSIDConfigSSIDNodes@@YAKKV?$CComPtr@UIXMLDOMNodeList@@@ATL@@PEAPEAUDOT11_SSID_LIST@@KHPEAKPEAH@Z`
- size: `581`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000df08`

## callees

- `0x180009654`
- `0x18000f7a8`
- `0x18000fc48`
- `0x18000fed0`
- `0x180014d9c`
- `0x180019370`
- `0x180039340`
- `0x180046a18`
- `0x18004e92c`
- `0x18006013c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046a61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046a61`
- `OLEAUT32!__imp_VariantInit` at `0x180046a9f`
- `OLEAUT32!__imp_VariantInit` at `0x180046a9f`
- `OLEAUT32!__imp_VariantClear` at `0x180046bc5`
- `OLEAUT32!__imp_VariantClear` at `0x180046beb`
- `OLEAUT32!__imp_VariantClear` at `0x180046c1e`
- `OLEAUT32!__imp_VariantClear` at `0x180046bc5`
- `OLEAUT32!__imp_VariantClear` at `0x180046beb`
- `OLEAUT32!__imp_VariantClear` at `0x180046c1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall XwpParseSSIDConfigSSIDNodes(
        unsigned int a1,
        struct IXMLDOMNodeList **a2,
        __int64 *a3,
        int a4,
        int a5,
        _DWORD *a6,
        struct IXMLDOMNode *a7)
{
  unsigned int v8; // eax
  _DWORD *v9; // rsi
  struct IXMLDOMNode *v10; // rdi
  unsigned int LastError; // ebx
  int v12; // r14d
  __int64 v13; // r12
  unsigned int i; // r15d
  __int64 v15; // r12
  const unsigned __int16 *v16; // r14
  unsigned int SingleNode; // eax
  void *v18; // r14
  unsigned int v19; // ecx
  const unsigned __int16 *v20; // rdx
  void *Src; // [rsp+20h] [rbp-38h] BYREF
  __int64 v23; // [rsp+28h] [rbp-30h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF
  struct IXMLDOMNode *v26; // [rsp+B0h] [rbp+58h] BYREF
  int v27; // [rsp+B8h] [rbp+60h]

  v27 = a4;
  v8 = a1;
  v9 = a6;
  if ( a6 )
    *a6 = 0;
  v10 = a7;
  if ( a7 )
    LODWORD(a7->lpVtbl) = 0;
  if ( !a3 )
  {
    LastError = GetLastError();
    goto LABEL_37;
  }
  LastError = 0;
  v12 = 1;
  LODWORD(a6) = 1;
  v13 = *a3;
  v23 = *a3;
  for ( i = 0; i < v8; ++i )
  {
    a7 = 0;
    v26 = 0;
    VariantInit(&pvarg);
    Src = 0;
    LastError = XcGetItem(*a2, i, &a7);
    if ( LastError )
      goto LABEL_34;
    v15 = v13 + 36LL * (i + v27);
    v16 = L"WLANProfile:hex";
    if ( !a5 )
      v16 = L"WLANProfileV2:hex";
    SingleNode = XcGetSingleNode(a7, v16, &v26);
    LastError = SingleNode;
    if ( !SingleNode )
    {
      LastError = XcGetNodeHexBinaryValue(a7, v16, (unsigned __int8 **)&Src, (unsigned int *)(v15 + 12));
      v18 = Src;
      if ( !LastError )
      {
        v19 = *(_DWORD *)(v15 + 12);
        if ( v19 - 1 > 0x1F )
          LastError = 1206;
        else
          memcpy_0((void *)(v15 + 16), Src, v19);
      }
      if ( v18 )
        Xc_Process_user_free(v18);
LABEL_19:
      v12 = (int)a6;
      goto LABEL_20;
    }
    if ( SingleNode != 1168 )
      goto LABEL_19;
    v20 = L"WLANProfile:name";
    if ( !a5 )
      v20 = L"WLANProfileV2:name";
    LastError = XcGetNodeTypedValue(a7, v20, &pvarg);
    if ( LastError )
      goto LABEL_19;
    LastError = WlanStringToSsid(pvarg.bstrVal);
    if ( LastError )
      LastError = 1206;
    v12 = 0;
    LODWORD(a6) = 0;
    VariantClear(&pvarg);
LABEL_20:
    if ( LastError == 1206 || LastError == 1168 )
    {
      LastError = 1206;
      if ( v9 )
      {
        *v9 = 524307;
LABEL_34:
        VariantClear(&pvarg);
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v26);
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&a7);
        goto LABEL_37;
      }
    }
    else if ( LastError )
    {
      goto LABEL_34;
    }
    ATL::CComPtrBase<IXMLDOMNode>::Release(&v26);
    ATL::CComPtrBase<IXMLDOMNode>::Release(&a7);
    VariantClear(&pvarg);
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v26);
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&a7);
    v8 = a1;
    v13 = v23;
  }
  if ( v10 )
    LODWORD(v10->lpVtbl) = v12;
LABEL_37:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)a2);
  return LastError;
}

```

## disassembly

```asm
0x180046a18  mov     [rsp-40h+arg_18], r9d
0x180046a1d  mov     [rsp-40h+arg_8], rdx
0x180046a22  mov     [rsp-40h+arg_0], ecx
0x180046a26  push    rbp
0x180046a27  push    rbx
0x180046a28  push    rsi
0x180046a29  push    rdi
0x180046a2a  push    r12
0x180046a2c  push    r13
0x180046a2e  push    r14
0x180046a30  push    r15
0x180046a32  mov     rbp, rsp
0x180046a35  sub     rsp, 58h
0x180046a39  mov     r13, rdx
0x180046a3c  mov     eax, ecx
0x180046a3e  mov     rsi, [rbp+arg_28]
0x180046a42  test    rsi, rsi
0x180046a45  jz      short loc_180046A4D
0x180046a47  mov     dword ptr [rsi], 0
0x180046a4d  mov     rdi, [rbp+arg_30]
0x180046a51  test    rdi, rdi
0x180046a54  jz      short loc_180046A5C
0x180046a56  mov     dword ptr [rdi], 0
0x180046a5c  test    r8, r8
0x180046a5f  jnz     short loc_180046A6E
0x180046a61  call    cs:__imp_GetLastError
0x180046a67  mov     ebx, eax
0x180046a69  jmp     loc_180046C42
0x180046a6e  xor     ebx, ebx
0x180046a70  lea     r14d, [rbx+1]
0x180046a74  mov     dword ptr [rbp+arg_28], r14d
0x180046a78  mov     r12, [r8]
0x180046a7b  mov     [rbp+var_30], r12
0x180046a7f  xor     r15d, r15d
0x180046a82  cmp     r15d, eax
0x180046a85  jnb     loc_180046C3A
0x180046a8b  mov     [rbp+arg_30], 0
0x180046a93  mov     [rbp+arg_10], 0
0x180046a9b  lea     rcx, [rbp+pvarg]; pvarg
0x180046a9f  call    cs:__imp_VariantInit
0x180046aa5  nop
0x180046aa6  mov     [rbp+Src], 0
0x180046aae  lea     r8, [rbp+arg_30]; struct IXMLDOMNode **
0x180046ab2  mov     edx, r15d; int
0x180046ab5  mov     rcx, [r13+0]; struct IXMLDOMNodeList *
0x180046ab9  call    ?XcGetItem@@YAKPEAUIXMLDOMNodeList@@JPEAPEAUIXMLDOMNode@@@Z; XcGetItem(IXMLDOMNodeList *,long,IXMLDOMNode * *)
0x180046abe  mov     ebx, eax
0x180046ac0  test    eax, eax
0x180046ac2  jnz     loc_180046C1A
0x180046ac8  mov     eax, [rbp+arg_18]
0x180046acb  add     eax, r15d
0x180046ace  lea     rax, [rax+rax*8]
0x180046ad2  lea     r12, [r12+rax*4]
0x180046ad6  lea     rax, aWlanprofilev2H; "WLANProfileV2:hex"
0x180046add  lea     r14, aWlanprofileHex; "WLANProfile:hex"
0x180046ae4  cmp     [rbp+arg_20], ebx
0x180046ae7  cmovz   r14, rax
0x180046aeb  lea     r8, [rbp+arg_10]; struct IXMLDOMNode **
0x180046aef  mov     rdx, r14; unsigned __int16 *
0x180046af2  mov     rcx, [rbp+arg_30]; struct IXMLDOMNode *
0x180046af6  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x180046afb  mov     ebx, eax
0x180046afd  test    eax, eax
0x180046aff  jnz     short loc_180046B70
0x180046b01  lea     r9, [r12+0Ch]; unsigned int *
0x180046b06  lea     r8, [rbp+Src]; unsigned __int8 **
0x180046b0a  mov     rdx, r14; unsigned __int16 *
0x180046b0d  mov     rcx, [rbp+arg_30]; struct IXMLDOMNode *
0x180046b11  call    ?XcGetNodeHexBinaryValue@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAEPEAK@Z; XcGetNodeHexBinaryValue(IXMLDOMNode *,ushort const *,uchar * *,ulong *)
0x180046b16  mov     ebx, eax
0x180046b18  mov     r14, [rbp+Src]
0x180046b1c  test    eax, eax
0x180046b1e  jnz     short loc_180046B44
0x180046b20  mov     ecx, [r12+0Ch]
0x180046b25  lea     eax, [rcx-1]
0x180046b28  cmp     eax, 1Fh
0x180046b2b  ja      short loc_180046B3F
0x180046b2d  mov     r8d, ecx; Size
0x180046b30  lea     rcx, [r12+10h]; void *
0x180046b35  mov     rdx, r14; Src
0x180046b38  call    memcpy_0
0x180046b3d  jmp     short loc_180046B44
0x180046b3f  mov     ebx, 4B6h
0x180046b44  test    r14, r14
0x180046b47  jz      short loc_180046B51
0x180046b49  mov     rcx, r14; lpMem
0x180046b4c  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x180046b51  mov     r14d, dword ptr [rbp+arg_28]
0x180046b55  mov     eax, 4B6h
0x180046b5a  cmp     ebx, eax
0x180046b5c  jz      short loc_180046BCD
0x180046b5e  cmp     ebx, 490h
0x180046b64  jz      short loc_180046BCD
0x180046b66  test    ebx, ebx
0x180046b68  jnz     loc_180046C1A
0x180046b6e  jmp     short loc_180046BD4
0x180046b70  cmp     eax, 490h
0x180046b75  jnz     short loc_180046B51
0x180046b77  lea     rax, aWlanprofilev2N; "WLANProfileV2:name"
0x180046b7e  lea     rdx, aWlanprofileNam; "WLANProfile:name"
0x180046b85  cmp     [rbp+arg_20], 0
0x180046b89  cmovz   rdx, rax; unsigned __int16 *
0x180046b8d  lea     r8, [rbp+pvarg]; struct tagVARIANT *
0x180046b91  mov     rcx, [rbp+arg_30]; struct IXMLDOMNode *
0x180046b95  call    ?XcGetNodeTypedValue@@YAKPEAUIXMLDOMNode@@PEBGPEAUtagVARIANT@@@Z; XcGetNodeTypedValue(IXMLDOMNode *,ushort const *,tagVARIANT *)
0x180046b9a  mov     ebx, eax
0x180046b9c  test    eax, eax
0x180046b9e  jnz     short loc_180046B51
0x180046ba0  lea     rdx, [r12+0Ch]
0x180046ba5  mov     rcx, qword ptr [rbp+pvarg+8]; lpWideCharStr
0x180046ba9  call    WlanStringToSsid
0x180046bae  mov     ebx, eax
0x180046bb0  test    eax, eax
0x180046bb2  mov     eax, 4B6h
0x180046bb7  cmovnz  ebx, eax
0x180046bba  xor     r14d, r14d
0x180046bbd  mov     dword ptr [rbp+arg_28], r14d
0x180046bc1  lea     rcx, [rbp+pvarg]; pvarg
0x180046bc5  call    cs:__imp_VariantClear
0x180046bcb  jmp     short loc_180046B55
0x180046bcd  mov     ebx, eax
0x180046bcf  test    rsi, rsi
0x180046bd2  jnz     short loc_180046C14
0x180046bd4  lea     rcx, [rbp+arg_10]
0x180046bd8  call    ?Release@?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IXMLDOMNode>::Release(void)
0x180046bdd  lea     rcx, [rbp+arg_30]
0x180046be1  call    ?Release@?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IXMLDOMNode>::Release(void)
0x180046be6  nop
0x180046be7  lea     rcx, [rbp+pvarg]; pvarg
0x180046beb  call    cs:__imp_VariantClear
0x180046bf1  nop
0x180046bf2  lea     rcx, [rbp+arg_10]
0x180046bf6  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180046bfb  nop
0x180046bfc  lea     rcx, [rbp+arg_30]
0x180046c00  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180046c05  inc     r15d
0x180046c08  mov     eax, [rbp+arg_0]
0x180046c0b  mov     r12, [rbp+var_30]
0x180046c0f  jmp     loc_180046A82
0x180046c14  mov     dword ptr [rsi], 80013h
0x180046c1a  lea     rcx, [rbp+pvarg]; pvarg
0x180046c1e  call    cs:__imp_VariantClear
0x180046c24  nop
0x180046c25  lea     rcx, [rbp+arg_10]
0x180046c29  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180046c2e  nop
0x180046c2f  lea     rcx, [rbp+arg_30]
0x180046c33  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180046c38  jmp     short loc_180046C42
0x180046c3a  test    rdi, rdi
0x180046c3d  jz      short loc_180046C42
0x180046c3f  mov     [rdi], r14d
0x180046c42  mov     rcx, r13
0x180046c45  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180046c4a  mov     eax, ebx
0x180046c4c  add     rsp, 58h
0x180046c50  pop     r15
0x180046c52  pop     r14
0x180046c54  pop     r13
0x180046c56  pop     r12
0x180046c58  pop     rdi
0x180046c59  pop     rsi
0x180046c5a  pop     rbx
0x180046c5b  pop     rbp
0x180046c5c  retn
```
