# XopParseEapConfig(ulong,IXMLDOMNode *,_ONEX_CONNECTION_PROFILE * *,ulong *)

- ea: `0x18004f954`
- end: `0x18004fc60`
- name: `?XopParseEapConfig@@YAKKPEAUIXMLDOMNode@@PEAPEAU_ONEX_CONNECTION_PROFILE@@PEAK@Z`
- size: `780`
- prototype: `unsigned int(unsigned int, struct IXMLDOMNode *, struct _ONEX_CONNECTION_PROFILE **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004f200`

## callees

- `0x180009654`
- `0x18000dea8`
- `0x18000f7a8`
- `0x180019370`
- `0x180019a20`
- `0x180043748`
- `0x18004f954`
- `0x18006013c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fab7`
- `eappcfg!EapHostPeerFreeMemory` at `0x18004fc29`
- `eappcfg!EapHostPeerFreeMemory` at `0x18004fc29`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18004fc1a`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18004fc1a`
- `eappcfg!EapHostPeerConfigXml2Blob` at `0x18004fa2e`
- `eappcfg!EapHostPeerConfigXml2Blob` at `0x18004fa2e`

## string_xrefs

- `0x18004f9b1`: `OneX:EAPConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XopParseEapConfig(
        int a1,
        struct IXMLDOMNode *a2,
        struct _ONEX_CONNECTION_PROFILE **a3,
        unsigned int *a4)
{
  unsigned int SingleNode; // eax
  DWORD LastError; // ebx
  int v9; // eax
  char *v10; // rcx
  __int64 v11; // rax
  DWORD v12; // ebx
  DWORD v13; // esi
  _OWORD *v14; // rdi
  char *v15; // rax
  __int64 v16; // r8
  EAP_METHOD_TYPE v17; // xmm2
  unsigned int *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // r10d
  __int64 v22; // r11
  unsigned int v23; // ebx
  unsigned int *v24; // rdx
  int v25; // r8d
  __int64 v26; // r9
  size_t v27; // r10
  const void *v28; // r11
  __int64 v29; // rax
  __int64 v30; // r9
  DWORD pdwSizeOfConfigOut; // [rsp+30h] [rbp-50h] BYREF
  BYTE *ppConfigOut; // [rsp+38h] [rbp-48h] BYREF
  EAP_ERROR *pEapError; // [rsp+40h] [rbp-40h] BYREF
  IXMLDOMNode *pConfigDoc; // [rsp+48h] [rbp-38h] BYREF
  struct IXMLDOMNode *v36[2]; // [rsp+50h] [rbp-30h] BYREF
  EAP_METHOD_TYPE pEapMethodType; // [rsp+60h] [rbp-20h] BYREF

  v36[0] = 0;
  pConfigDoc = 0;
  pEapMethodType.eapType.type = 0;
  *(_WORD *)(&pEapMethodType.eapType.type + 1) = 0;
  *(&pEapMethodType.eapType.type + 3) = 0;
  *(_QWORD *)&pEapMethodType.eapType.dwVendorId = 0;
  pEapMethodType.dwAuthorId = 0;
  pdwSizeOfConfigOut = 0;
  ppConfigOut = 0;
  pEapError = 0;
  SingleNode = XcGetSingleNode(a2, L"OneX:EAPConfig", v36);
  LastError = SingleNode;
  if ( SingleNode == 1168 )
  {
    LastError = 1206;
    goto LABEL_43;
  }
  if ( SingleNode )
    goto LABEL_43;
  v9 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, IXMLDOMNode **))v36[0]->lpVtbl->get_firstChild)(
         v36[0],
         &pConfigDoc);
  LastError = v9;
  if ( v9 < 0 )
  {
    if ( (v9 & 0x1FFF0000) == 0x70000 )
      LastError = (unsigned __int16)v9;
    if ( LastError )
      goto LABEL_43;
  }
  if ( !EapHostPeerConfigXml2Blob(a1 | 0x80, pConfigDoc, &pdwSizeOfConfigOut, &ppConfigOut, &pEapMethodType, &pEapError) )
  {
    v10 = (char *)*a3;
    v11 = *((unsigned int *)*a3 + 16);
    *(_DWORD *)&v10[v11 + 20] &= ~1u;
    *(EAP_METHOD_TYPE *)&v10[v11 + 4] = pEapMethodType;
    if ( !*a3 )
    {
      LastError = 87;
      goto LABEL_43;
    }
    v12 = 104;
    v13 = 104;
    if ( ppConfigOut )
    {
      if ( pdwSizeOfConfigOut )
      {
        if ( pdwSizeOfConfigOut >= 0xFFFFFFEC || (v13 = pdwSizeOfConfigOut + 124, pdwSizeOfConfigOut + 124 < 0x68) )
        {
          LastError = 534;
          goto LABEL_43;
        }
      }
    }
    v14 = Xc_Process_user_allocate(v13);
    if ( !v14 )
    {
      LastError = GetLastError();
      goto LABEL_43;
    }
    v15 = (char *)*a3;
    if ( !*a3 )
    {
      LastError = 87;
      goto LABEL_41;
    }
    v16 = 0;
    if ( ppConfigOut && pdwSizeOfConfigOut )
    {
      v16 = pdwSizeOfConfigOut + 20;
      if ( pdwSizeOfConfigOut >= 0xFFFFFFEC || pdwSizeOfConfigOut + 124 < 0x68 )
        goto LABEL_36;
      v12 = pdwSizeOfConfigOut + 124;
    }
    if ( v13 < v12 )
    {
      LastError = 122;
      goto LABEL_41;
    }
    v17 = pEapMethodType;
    *v14 = *(_OWORD *)v15;
    v14[1] = *((_OWORD *)v15 + 1);
    v14[2] = *((_OWORD *)v15 + 2);
    v14[3] = *((_OWORD *)v15 + 3);
    v14[4] = *((_OWORD *)v15 + 4);
    v14[5] = *((_OWORD *)v15 + 5);
    *((_QWORD *)v14 + 12) = *((_QWORD *)v15 + 12);
    *((_DWORD *)v14 + 1) = v12;
    *(EAP_METHOD_TYPE *)((char *)v14 + *((unsigned int *)v14 + 16) + 4) = v17;
    LastError = GetAlignedSize(32, (char *)v14 + 60, v16);
    if ( LastError )
      goto LABEL_41;
    v23 = *v18 + v19;
    if ( v23 >= *v18 )
    {
      *v18 = v23;
      if ( v22 && v21 )
      {
        *(_DWORD *)(v20 + 20) |= 1u;
        LastError = GetAlignedSize(32, v20 + 28, v19);
        if ( !LastError )
        {
          *(_DWORD *)(v26 + 24) = v25;
          v29 = *v24;
          *(_DWORD *)(v29 + v26 + 16) = v27;
          *(EAP_METHOD_TYPE *)(v29 + v26) = v17;
          memcpy_0((void *)(v26 + v29 + 20), v28, v27);
LABEL_38:
          Xc_Process_user_free(*a3);
          *a3 = (struct _ONEX_CONNECTION_PROFILE *)v14;
          goto LABEL_43;
        }
      }
      else
      {
        *(_DWORD *)(v20 + 20) &= ~1u;
        LastError = GetAlignedSize(32, v20 + 28, v19);
        if ( !LastError )
        {
          *(_DWORD *)(v30 + 24) = 0;
          goto LABEL_38;
        }
      }
LABEL_41:
      Xc_Process_user_free(v14);
      goto LABEL_43;
    }
    *v18 = -1;
LABEL_36:
    LastError = 534;
    goto LABEL_41;
  }
  LastError = 1206;
  if ( !pEapError )
    goto LABEL_45;
  if ( a4 )
    *a4 = pEapError->dwWinError;
LABEL_43:
  if ( pEapError )
    EapHostPeerFreeErrorMemory(pEapError);
LABEL_45:
  if ( ppConfigOut )
    EapHostPeerFreeMemory(ppConfigOut);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&pConfigDoc);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(v36);
  return LastError;
}

```

## disassembly

```asm
0x18004f954  push    rbp
0x18004f956  push    rbx
0x18004f957  push    rsi
0x18004f958  push    rdi
0x18004f959  push    r14
0x18004f95b  mov     rbp, rsp
0x18004f95e  sub     rsp, 80h
0x18004f965  mov     rax, cs:__security_cookie
0x18004f96c  xor     rax, rsp
0x18004f96f  mov     [rbp+var_10], rax
0x18004f973  mov     rsi, r9
0x18004f976  mov     r14, r8
0x18004f979  mov     rax, rdx
0x18004f97c  mov     edi, ecx
0x18004f97e  mov     [rbp+var_30], 0
0x18004f986  mov     [rbp+pConfigDoc], 0
0x18004f98e  mov     [rbp+var_20.eapType.type], 0
0x18004f992  xor     ecx, ecx
0x18004f994  mov     word ptr [rbp+var_20.eapType+1], cx
0x18004f998  mov     byte ptr [rbp+var_20.eapType+3], cl
0x18004f99b  mov     qword ptr [rbp+var_20.eapType.dwVendorId], rcx
0x18004f99f  mov     [rbp+var_20.dwAuthorId], ecx
0x18004f9a2  mov     [rbp+pdwSizeOfConfigOut], ecx
0x18004f9a5  mov     [rbp+ppConfigOut], rcx
0x18004f9a9  mov     [rbp+pEapError], rcx
0x18004f9ad  lea     r8, [rbp+var_30]; struct IXMLDOMNode **
0x18004f9b1  lea     rdx, aOnexEapconfig; "OneX:EAPConfig"
0x18004f9b8  mov     rcx, rax; struct IXMLDOMNode *
0x18004f9bb  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18004f9c0  mov     ebx, eax
0x18004f9c2  cmp     eax, 490h
0x18004f9c7  jnz     short loc_18004F9D1
0x18004f9c9  lea     ebx, [rax+26h]
0x18004f9cc  jmp     loc_18004FC11
0x18004f9d1  test    eax, eax
0x18004f9d3  jnz     loc_18004FC11
0x18004f9d9  mov     rcx, [rbp+var_30]
0x18004f9dd  mov     rax, [rcx]
0x18004f9e0  lea     rdx, [rbp+pConfigDoc]
0x18004f9e4  mov     rax, [rax+68h]
0x18004f9e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f9ed  mov     ebx, eax
0x18004f9ef  test    eax, eax
0x18004f9f1  jns     short loc_18004FA0A
0x18004f9f3  and     eax, 1FFF0000h
0x18004f9f8  cmp     eax, 70000h
0x18004f9fd  jnz     short loc_18004FA02
0x18004f9ff  movzx   ebx, bx
0x18004fa02  test    ebx, ebx
0x18004fa04  jnz     loc_18004FC11
0x18004fa0a  bts     edi, 7
0x18004fa0e  lea     rax, [rbp+pEapError]
0x18004fa12  mov     [rsp+80h+ppEapError], rax; ppEapError
0x18004fa17  lea     rax, [rbp+var_20]
0x18004fa1b  mov     [rsp+80h+pEapMethodType], rax; pEapMethodType
0x18004fa20  lea     r9, [rbp+ppConfigOut]; ppConfigOut
0x18004fa24  lea     r8, [rbp+pdwSizeOfConfigOut]; pdwSizeOfConfigOut
0x18004fa28  mov     rdx, [rbp+pConfigDoc]; pConfigDoc
0x18004fa2c  mov     ecx, edi; dwFlags
0x18004fa2e  call    cs:__imp_EapHostPeerConfigXml2Blob
0x18004fa34  test    eax, eax
0x18004fa36  jz      short loc_18004FA5C
0x18004fa38  mov     ebx, 4B6h
0x18004fa3d  mov     rcx, [rbp+pEapError]
0x18004fa41  test    rcx, rcx
0x18004fa44  jz      loc_18004FC20
0x18004fa4a  test    rsi, rsi
0x18004fa4d  jz      loc_18004FC11
0x18004fa53  mov     eax, [rcx]
0x18004fa55  mov     [rsi], eax
0x18004fa57  jmp     loc_18004FC11
0x18004fa5c  mov     rcx, [r14]
0x18004fa5f  mov     eax, [rcx+40h]
0x18004fa62  and     dword ptr [rax+rcx+14h], 0FFFFFFFEh
0x18004fa67  movaps  xmm0, xmmword ptr [rbp+var_20.eapType.type]
0x18004fa6b  movdqu  xmmword ptr [rax+rcx+4], xmm0
0x18004fa71  cmp     qword ptr [r14], 0
0x18004fa75  jz      loc_18004FC0C
0x18004fa7b  mov     ebx, 68h ; 'h'
0x18004fa80  mov     esi, ebx
0x18004fa82  cmp     [rbp+ppConfigOut], 0
0x18004fa87  jz      short loc_18004FAA8
0x18004fa89  mov     eax, [rbp+pdwSizeOfConfigOut]
0x18004fa8c  test    eax, eax
0x18004fa8e  jz      short loc_18004FAA8
0x18004fa90  lea     esi, [rax+14h]
0x18004fa93  cmp     esi, 14h
0x18004fa96  jb      short loc_18004FA9E
0x18004fa98  add     esi, ebx
0x18004fa9a  cmp     esi, ebx
0x18004fa9c  jnb     short loc_18004FAA8
0x18004fa9e  mov     ebx, 216h
0x18004faa3  jmp     loc_18004FC11
0x18004faa8  mov     ecx, esi; dwBytes
0x18004faaa  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x18004faaf  mov     rdi, rax
0x18004fab2  test    rax, rax
0x18004fab5  jnz     short loc_18004FAC4
0x18004fab7  call    cs:__imp_GetLastError
0x18004fabd  mov     ebx, eax
0x18004fabf  jmp     loc_18004FC11
0x18004fac4  mov     rax, [r14]
0x18004fac7  test    rax, rax
0x18004faca  jz      loc_18004FBFD
0x18004fad0  mov     r11, [rbp+ppConfigOut]
0x18004fad4  mov     r10d, [rbp+pdwSizeOfConfigOut]
0x18004fad8  xor     r8d, r8d
0x18004fadb  test    r11, r11
0x18004fade  jz      short loc_18004FB01
0x18004fae0  test    r10d, r10d
0x18004fae3  jz      short loc_18004FB01
0x18004fae5  lea     r8d, [r10+14h]
0x18004fae9  cmp     r8d, 14h
0x18004faed  jb      loc_18004FBDE
0x18004faf3  lea     ecx, [r8+68h]
0x18004faf7  cmp     ecx, ebx
0x18004faf9  jb      loc_18004FBDE
0x18004faff  mov     ebx, ecx
0x18004fb01  cmp     esi, ebx
0x18004fb03  jb      loc_18004FBF6
0x18004fb09  movaps  xmm2, xmmword ptr [rbp+var_20.eapType.type]
0x18004fb0d  movups  xmm0, xmmword ptr [rax]
0x18004fb10  movups  xmmword ptr [rdi], xmm0
0x18004fb13  movups  xmm1, xmmword ptr [rax+10h]
0x18004fb17  movups  xmmword ptr [rdi+10h], xmm1
0x18004fb1b  movups  xmm0, xmmword ptr [rax+20h]
0x18004fb1f  movups  xmmword ptr [rdi+20h], xmm0
0x18004fb23  movups  xmm1, xmmword ptr [rax+30h]
0x18004fb27  movups  xmmword ptr [rdi+30h], xmm1
0x18004fb2b  movups  xmm0, xmmword ptr [rax+40h]
0x18004fb2f  movups  xmmword ptr [rdi+40h], xmm0
0x18004fb33  movups  xmm1, xmmword ptr [rax+50h]
0x18004fb37  movups  xmmword ptr [rdi+50h], xmm1
0x18004fb3b  movsd   xmm0, qword ptr [rax+60h]
0x18004fb40  movsd   qword ptr [rdi+60h], xmm0
0x18004fb45  mov     [rdi+4], ebx
0x18004fb48  mov     r9d, [rdi+40h]
0x18004fb4c  add     r9, rdi
0x18004fb4f  movdqu  xmmword ptr [r9+4], xmm2
0x18004fb55  lea     rdx, [rdi+3Ch]
0x18004fb59  mov     esi, 20h ; ' '
0x18004fb5e  mov     ecx, esi
0x18004fb60  call    GetAlignedSize
0x18004fb65  mov     ebx, eax
0x18004fb67  test    eax, eax
0x18004fb69  jnz     short loc_18004FBE5
0x18004fb6b  mov     eax, [rdx]
0x18004fb6d  lea     ebx, [rax+r8]
0x18004fb71  cmp     ebx, eax
0x18004fb73  jb      short loc_18004FBD8
0x18004fb75  mov     [rdx], ebx
0x18004fb77  test    r11, r11
0x18004fb7a  jz      short loc_18004FBBC
0x18004fb7c  test    r10d, r10d
0x18004fb7f  jz      short loc_18004FBBC
0x18004fb81  or      dword ptr [r9+14h], 1
0x18004fb86  lea     rdx, [r9+1Ch]
0x18004fb8a  mov     ecx, esi
0x18004fb8c  call    GetAlignedSize
0x18004fb91  mov     ebx, eax
0x18004fb93  test    eax, eax
0x18004fb95  jnz     short loc_18004FBE5
0x18004fb97  mov     [r9+18h], r8d
0x18004fb9b  mov     eax, [rdx]
0x18004fb9d  mov     [rax+r9+10h], r10d
0x18004fba2  movdqu  xmmword ptr [rax+r9], xmm2
0x18004fba8  mov     r8, r10; Size
0x18004fbab  lea     rcx, [rax+14h]
0x18004fbaf  add     rcx, r9; void *
0x18004fbb2  mov     rdx, r11; Src
0x18004fbb5  call    memcpy_0
0x18004fbba  jmp     short loc_18004FBE9
0x18004fbbc  and     dword ptr [r9+14h], 0FFFFFFFEh
0x18004fbc1  lea     rdx, [r9+1Ch]
0x18004fbc5  mov     ecx, esi
0x18004fbc7  call    GetAlignedSize
0x18004fbcc  mov     ebx, eax
0x18004fbce  test    eax, eax
0x18004fbd0  jnz     short loc_18004FBE5
0x18004fbd2  mov     [r9+18h], eax
0x18004fbd6  jmp     short loc_18004FBE9
0x18004fbd8  mov     dword ptr [rdx], 0FFFFFFFFh
0x18004fbde  mov     ebx, 216h
0x18004fbe3  jmp     short loc_18004FC02
0x18004fbe5  test    ebx, ebx
0x18004fbe7  jnz     short loc_18004FC02
0x18004fbe9  mov     rcx, [r14]; lpMem
0x18004fbec  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18004fbf1  mov     [r14], rdi
0x18004fbf4  jmp     short loc_18004FC11
0x18004fbf6  mov     ebx, 7Ah ; 'z'
0x18004fbfb  jmp     short loc_18004FC02
0x18004fbfd  mov     ebx, 57h ; 'W'
0x18004fc02  mov     rcx, rdi; lpMem
0x18004fc05  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18004fc0a  jmp     short loc_18004FC11
0x18004fc0c  mov     ebx, 57h ; 'W'
0x18004fc11  mov     rcx, [rbp+pEapError]; pEapError
0x18004fc15  test    rcx, rcx
0x18004fc18  jz      short loc_18004FC20
0x18004fc1a  call    cs:__imp_EapHostPeerFreeErrorMemory
0x18004fc20  mov     rcx, [rbp+ppConfigOut]; pData
0x18004fc24  test    rcx, rcx
0x18004fc27  jz      short loc_18004FC30
0x18004fc29  call    cs:__imp_EapHostPeerFreeMemory
0x18004fc2f  nop
0x18004fc30  lea     rcx, [rbp+pConfigDoc]
0x18004fc34  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18004fc39  nop
0x18004fc3a  lea     rcx, [rbp+var_30]
0x18004fc3e  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18004fc43  nop
0x18004fc44  mov     eax, ebx
0x18004fc46  mov     rcx, [rbp+var_10]
0x18004fc4a  xor     rcx, rsp; StackCookie
0x18004fc4d  call    __security_check_cookie
0x18004fc52  add     rsp, 80h
0x18004fc59  pop     r14
0x18004fc5b  pop     rdi
0x18004fc5c  pop     rsi
0x18004fc5d  pop     rbx
0x18004fc5e  pop     rbp
0x18004fc5f  retn
```
