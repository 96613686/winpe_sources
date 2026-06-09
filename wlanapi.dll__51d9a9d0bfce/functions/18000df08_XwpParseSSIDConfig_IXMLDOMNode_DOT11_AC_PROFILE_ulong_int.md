# XwpParseSSIDConfig(IXMLDOMNode *,_DOT11_AC_PROFILE *,ulong *,int *)

- ea: `0x18000df08`
- end: `0x18000e3c8`
- name: `?XwpParseSSIDConfig@@YAKPEAUIXMLDOMNode@@PEAU_DOT11_AC_PROFILE@@PEAKPEAH@Z`
- size: `1216`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, struct _DOT11_AC_PROFILE *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000dafc`

## callees

- `0x18000dea8`
- `0x18000df08`
- `0x18000fb68`
- `0x18000fd24`
- `0x18000fe30`
- `0x18000fed0`
- `0x180019370`
- `0x180046a18`
- `0x18004ef98`
- `0x18006013c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2ea`

## string_xrefs

- `0x18000df73`: `WLANProfile:SSIDConfig`
- `0x18000df99`: `WLANProfile:SSID`
- `0x18000e059`: `WLANProfileV2:SSID`
- `0x18000e07a`: `WLANProfileV2:SSIDBinaryList`
- `0x18000e09a`: `WLANProfileV2:SSIDBinaryList`
- `0x18000e28f`: `WLANProfileV2:SSIDPrefix`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall XwpParseSSIDConfig(struct IXMLDOMNode *a1, struct _DOT11_AC_PROFILE *a2, unsigned int *a3, int *a4)
{
  struct _DOT11_AC_PROFILE *v4; // rsi
  struct IXMLDOMNodeList *v5; // r15
  struct IXMLDOMNodeList *v6; // r12
  void *v7; // rdi
  unsigned __int8 *v8; // r13
  unsigned int FirstNode; // eax
  DWORD Nodes; // ebx
  int v12; // ebx
  unsigned int v13; // eax
  int v14; // edx
  unsigned int v15; // eax
  __int64 v16; // rcx
  int v17; // edx
  unsigned int v18; // ecx
  unsigned int v19; // eax
  _DWORD *v20; // rax
  _DWORD *v21; // r14
  int v22; // eax
  int v23; // ebx
  unsigned int v24; // r8d
  __int64 v25; // rbx
  unsigned int v26; // edx
  int v27; // ebx
  __int64 v28; // rcx
  unsigned int v29; // eax
  int v30; // esi
  _DWORD *v31; // rax
  int v32; // [rsp+48h] [rbp-49h] BYREF
  void *lpMem; // [rsp+50h] [rbp-41h] BYREF
  struct IXMLDOMNode *v34; // [rsp+58h] [rbp-39h] BYREF
  int v35; // [rsp+60h] [rbp-31h]
  unsigned int v36; // [rsp+64h] [rbp-2Dh] BYREF
  int v37[2]; // [rsp+68h] [rbp-29h] BYREF
  int v38; // [rsp+70h] [rbp-21h] BYREF
  int v39; // [rsp+74h] [rbp-1Dh] BYREF
  unsigned int v40; // [rsp+78h] [rbp-19h] BYREF
  SIZE_T dwBytes; // [rsp+80h] [rbp-11h] BYREF
  struct IXMLDOMNodeList *v42; // [rsp+88h] [rbp-9h] BYREF
  int v43[2]; // [rsp+90h] [rbp-1h] BYREF
  struct IXMLDOMNodeList *v44; // [rsp+98h] [rbp+7h] BYREF
  struct IXMLDOMNodeList *v45; // [rsp+A0h] [rbp+Fh] BYREF
  struct IXMLDOMNode *v46; // [rsp+A8h] [rbp+17h] BYREF
  struct IXMLDOMNodeList *v49; // [rsp+110h] [rbp+7Fh] BYREF

  HIDWORD(v49) = HIDWORD(a4);
  v4 = a2;
  v34 = 0;
  v5 = 0;
  v42 = 0;
  v44 = 0;
  v46 = 0;
  v6 = 0;
  v45 = 0;
  LODWORD(v49) = 0;
  v32 = 0;
  v38 = 0;
  v40 = 0;
  v39 = 0;
  v7 = 0;
  dwBytes = 0;
  v8 = 0;
  lpMem = 0;
  v36 = 0;
  FirstNode = XcGetFirstNode(a1, L"WLANProfile:SSIDConfig", &v34);
  Nodes = FirstNode;
  if ( FirstNode == 1168 )
  {
    Nodes = 1206;
    goto LABEL_8;
  }
  if ( !FirstNode )
  {
    Nodes = XcGetNodes(v34, L"WLANProfile:SSID", &v42, (int *)&v49);
    if ( Nodes )
    {
LABEL_7:
      v5 = v42;
      goto LABEL_8;
    }
    if ( (int)v49 < 1 )
    {
      Nodes = 1206;
      goto LABEL_7;
    }
    v12 = 0;
    v35 = 0;
    v13 = XcGetNodes(v34, L"WLANProfileV2:SSID", &v44, &v32);
    v14 = v32;
    if ( v13 )
      v14 = 0;
    v32 = v14;
    v15 = XcGetFirstNode(v34, L"WLANProfileV2:SSIDBinaryList", &v46);
    v5 = v42;
    if ( !v15 )
    {
      Nodes = XcGetNodeHexBinaryValue(v34, L"WLANProfileV2:SSIDBinaryList", (unsigned __int8 **)&lpMem, &v36);
      v8 = (unsigned __int8 *)lpMem;
      if ( Nodes )
        goto LABEL_51;
      v16 = 0;
      v12 = 0;
      while ( (unsigned int)v16 < v36 )
      {
        v17 = *((unsigned __int8 *)lpMem + v16);
        if ( (unsigned int)(v17 - 1) > 0x1F )
          goto LABEL_28;
        v18 = v17 + v16;
        if ( v18 >= v36 )
          goto LABEL_28;
        v35 = ++v12;
        v16 = v18 + 1;
      }
    }
    v19 = (_DWORD)v49 + v12 + v32;
    LODWORD(lpMem) = v19;
    if ( v19 > 0x2810 )
    {
LABEL_28:
      Nodes = 1206;
      goto LABEL_51;
    }
    Nodes = VariableListSize(0xCu, (int)v19, 0x24u, &dwBytes);
    if ( Nodes )
    {
LABEL_51:
      if ( v8 )
        Xc_Process_user_free(v8);
      goto LABEL_8;
    }
    v20 = Xc_Process_user_allocate(dwBytes);
    v21 = v20;
    *(_QWORD *)v43 = v20;
    if ( !v20 )
      goto LABEL_58;
    *v20 = 3146112;
    v22 = (int)lpMem;
    v21[1] = (_DWORD)lpMem;
    v21[2] = v22;
    *(_QWORD *)v37 = v5;
    if ( v5 )
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v5->lpVtbl->AddRef)(v5);
    Nodes = XwpParseSSIDConfigSSIDNodes((int)v49, (int)v37, (int)v43, 0, 1, (__int64)a3, (struct IXMLDOMNode *)&lpMem);
    if ( Nodes )
      goto LABEL_47;
    v23 = v32;
    if ( v32 > 0 )
    {
      *(_QWORD *)v37 = v44;
      if ( v44 )
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v44->lpVtbl->AddRef)(v44);
      Nodes = XwpParseSSIDConfigSSIDNodes(
                v23,
                (int)v37,
                (int)v43,
                (int)v49,
                0,
                (__int64)a3,
                (struct IXMLDOMNode *)&lpMem);
      if ( Nodes )
        goto LABEL_47;
      v23 = v32;
    }
    if ( v35 > 0 )
    {
      v24 = v23 + (_DWORD)v49;
      v25 = 0;
      while ( (unsigned int)v25 < v36 )
      {
        v26 = v8[v25];
        LODWORD(v49) = v26;
        if ( v26 - 1 > 0x1F || v26 + (unsigned int)v25 >= v36 )
          goto LABEL_46;
        v27 = v25 + 1;
        v28 = 9LL * v24;
        LODWORD(lpMem) = v24 + 1;
        v21[v28 + 3] = v26;
        memcpy_0(&v21[v28 + 4], &v8[v27], v26);
        v25 = (unsigned int)((_DWORD)v49 + v27);
        v24 = (unsigned int)lpMem;
      }
    }
    v29 = XcGetNodes(v34, L"WLANProfileV2:SSIDPrefix", &v45, &v38);
    v6 = v45;
    if ( !v29 )
    {
      v30 = v38;
      if ( v38 > 0 )
      {
        if ( (unsigned int)v38 > 0x20 )
        {
LABEL_46:
          Nodes = 1206;
          goto LABEL_47;
        }
        Nodes = VariableListSize(0xCu, v38, 0x24u, &dwBytes);
        if ( Nodes )
          goto LABEL_47;
        v31 = Xc_Process_user_allocate(dwBytes);
        v7 = v31;
        *(_QWORD *)v43 = v31;
        if ( !v31 )
        {
LABEL_58:
          Nodes = GetLastError();
          if ( !Nodes )
            goto LABEL_51;
LABEL_47:
          if ( v21 )
            Xc_Process_user_free(v21);
          if ( v7 )
            Xc_Process_user_free(v7);
          goto LABEL_51;
        }
        *v31 = 3146112;
        v31[1] = v30;
        v31[2] = v30;
        v49 = v6;
        if ( v6 )
          ((void (__fastcall *)(struct IXMLDOMNodeList *))v6->lpVtbl->AddRef)(v6);
        Nodes = XwpParseSSIDConfigSSIDNodes(v30, (int)&v49, (int)v43, 0, 0, (__int64)a3, (struct IXMLDOMNode *)&lpMem);
        if ( Nodes )
          goto LABEL_47;
      }
      v4 = a2;
    }
    Nodes = XcGetNodeEnumValue(
              v34,
              L"WLANProfile:nonBroadcast",
              (const struct _XC_STRING_VALUE_MAPPING *)&off_1800631E0,
              4u,
              &v40,
              1,
              0,
              &v39);
    if ( !Nodes )
    {
      if ( v39 )
      {
        *((_DWORD *)v4 + 1) |= 4u;
        if ( v40 )
          *((_DWORD *)v4 + 6) |= 2u;
      }
      *((_QWORD *)v4 + 1) = v21;
      *((_QWORD *)v4 + 5) = v7;
      goto LABEL_51;
    }
    goto LABEL_47;
  }
LABEL_8:
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v6->lpVtbl->Release)(v6);
  if ( v46 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v46->lpVtbl->Release)(v46);
  if ( v44 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v44->lpVtbl->Release)(v44);
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v5->lpVtbl->Release)(v5);
  if ( v34 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v34->lpVtbl->Release)(v34);
  return Nodes;
}

```

## disassembly

```asm
0x18000df08  mov     rax, rsp
0x18000df0b  mov     [rax+8], rbx
0x18000df0f  mov     [rax+20h], r9
0x18000df13  mov     [rax+18h], r8
0x18000df17  mov     [rax+10h], rdx
0x18000df1b  push    rbp
0x18000df1c  push    rsi
0x18000df1d  push    rdi
0x18000df1e  push    r12
0x18000df20  push    r13
0x18000df22  push    r14
0x18000df24  push    r15
0x18000df26  lea     rbp, [rax-5Fh]
0x18000df2a  sub     rsp, 0B0h
0x18000df31  mov     rsi, rdx
0x18000df34  xor     eax, eax
0x18000df36  mov     [rbp+57h+var_90], rax
0x18000df3a  mov     r15d, eax
0x18000df3d  mov     [rbp+57h+var_60], rax
0x18000df41  mov     [rbp+57h+var_50], rax
0x18000df45  mov     [rbp+57h+var_40], rax
0x18000df49  mov     r12d, eax
0x18000df4c  mov     [rbp+57h+var_48], rax
0x18000df50  mov     dword ptr [rbp+57h+arg_18], eax
0x18000df53  mov     [rbp+57h+var_A0], eax
0x18000df56  mov     [rbp+57h+var_78], eax
0x18000df59  mov     [rbp+57h+var_70], eax
0x18000df5c  mov     [rbp+57h+var_74], eax
0x18000df5f  mov     edi, eax
0x18000df61  mov     [rbp+57h+dwBytes], rax
0x18000df65  mov     r13d, eax
0x18000df68  mov     [rbp+57h+lpMem], rax
0x18000df6c  mov     [rbp+57h+var_84], eax
0x18000df6f  lea     r8, [rbp+57h+var_90]; struct IXMLDOMNode **
0x18000df73  lea     rdx, aWlanprofileSsi; "WLANProfile:SSIDConfig"
0x18000df7a  call    ?XcGetFirstNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetFirstNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000df7f  mov     ebx, eax
0x18000df81  cmp     eax, 490h
0x18000df86  jnz     short loc_18000DF8D
0x18000df88  lea     ebx, [rax+26h]
0x18000df8b  jmp     short loc_18000DFC2
0x18000df8d  test    eax, eax
0x18000df8f  jnz     short loc_18000DFC2
0x18000df91  lea     r9, [rbp+57h+arg_18]; int *
0x18000df95  lea     r8, [rbp+57h+var_60]; struct IXMLDOMNodeList **
0x18000df99  lea     rdx, aWlanprofileSsi_0; "WLANProfile:SSID"
0x18000dfa0  mov     rcx, [rbp+57h+var_90]; struct IXMLDOMNode *
0x18000dfa4  call    ?XcGetNodes@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJ@Z; XcGetNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *)
0x18000dfa9  mov     ebx, eax
0x18000dfab  test    eax, eax
0x18000dfad  jnz     short loc_18000DFBE
0x18000dfaf  cmp     dword ptr [rbp+57h+arg_18], 1
0x18000dfb3  jge     loc_18000E04C
0x18000dfb9  mov     ebx, 4B6h
0x18000dfbe  mov     r15, [rbp+57h+var_60]
0x18000dfc2  test    r12, r12
0x18000dfc5  jz      short loc_18000DFD8
0x18000dfc7  mov     rax, [r12]
0x18000dfcb  mov     rcx, r12
0x18000dfce  mov     rax, [rax+10h]
0x18000dfd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfd7  nop
0x18000dfd8  mov     rcx, [rbp+57h+var_40]
0x18000dfdc  test    rcx, rcx
0x18000dfdf  jz      short loc_18000DFEE
0x18000dfe1  mov     rax, [rcx]
0x18000dfe4  mov     rax, [rax+10h]
0x18000dfe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfed  nop
0x18000dfee  mov     rcx, [rbp+57h+var_50]
0x18000dff2  test    rcx, rcx
0x18000dff5  jz      short loc_18000E004
0x18000dff7  mov     rax, [rcx]
0x18000dffa  mov     rax, [rax+10h]
0x18000dffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e003  nop
0x18000e004  test    r15, r15
0x18000e007  jz      short loc_18000E019
0x18000e009  mov     rax, [r15]
0x18000e00c  mov     rcx, r15
0x18000e00f  mov     rax, [rax+10h]
0x18000e013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e018  nop
0x18000e019  mov     rcx, [rbp+57h+var_90]
0x18000e01d  test    rcx, rcx
0x18000e020  jz      short loc_18000E02F
0x18000e022  mov     rax, [rcx]
0x18000e025  mov     rax, [rax+10h]
0x18000e029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e02e  nop
0x18000e02f  mov     eax, ebx
0x18000e031  mov     rbx, [rsp+0E0h+arg_0]
0x18000e039  add     rsp, 0B0h
0x18000e040  pop     r15
0x18000e042  pop     r14
0x18000e044  pop     r13
0x18000e046  pop     r12
0x18000e048  pop     rdi
0x18000e049  pop     rsi
0x18000e04a  pop     rbp
0x18000e04b  retn
0x18000e04c  xor     ebx, ebx
0x18000e04e  mov     [rbp+57h+var_88], ebx
0x18000e051  lea     r9, [rbp+57h+var_A0]; int *
0x18000e055  lea     r8, [rbp+57h+var_50]; struct IXMLDOMNodeList **
0x18000e059  lea     rdx, aWlanprofilev2S_1; "WLANProfileV2:SSID"
0x18000e060  mov     rcx, [rbp+57h+var_90]; struct IXMLDOMNode *
0x18000e064  call    ?XcGetNodes@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJ@Z; XcGetNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *)
0x18000e069  mov     edx, [rbp+57h+var_A0]
0x18000e06c  xor     ecx, ecx
0x18000e06e  test    eax, eax
0x18000e070  cmovnz  edx, ecx
0x18000e073  mov     [rbp+57h+var_A0], edx
0x18000e076  lea     r8, [rbp+57h+var_40]; struct IXMLDOMNode **
0x18000e07a  lea     rdx, aWlanprofilev2S; "WLANProfileV2:SSIDBinaryList"
0x18000e081  mov     rcx, [rbp+57h+var_90]; struct IXMLDOMNode *
0x18000e085  call    ?XcGetFirstNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetFirstNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000e08a  mov     r15, [rbp+57h+var_60]
0x18000e08e  test    eax, eax
0x18000e090  jnz     short loc_18000E0EC
0x18000e092  lea     r9, [rbp+57h+var_84]; unsigned int *
0x18000e096  lea     r8, [rbp+57h+lpMem]; unsigned __int8 **
0x18000e09a  lea     rdx, aWlanprofilev2S; "WLANProfileV2:SSIDBinaryList"
0x18000e0a1  mov     rcx, [rbp+57h+var_90]; struct IXMLDOMNode *
0x18000e0a5  call    ?XcGetNodeHexBinaryValue@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAEPEAK@Z; XcGetNodeHexBinaryValue(IXMLDOMNode *,ushort const *,uchar * *,ulong *)
0x18000e0aa  mov     ebx, eax
0x18000e0ac  mov     r13, [rbp+57h+lpMem]
0x18000e0b0  test    eax, eax
0x18000e0b2  jnz     loc_18000E271
0x18000e0b8  xor     ecx, ecx
0x18000e0ba  mov     r14d, [rbp+57h+var_84]
0x18000e0be  mov     ebx, ecx
0x18000e0c0  cmp     ecx, r14d
0x18000e0c3  jnb     short loc_18000E0EC
0x18000e0c5  movzx   edx, byte ptr [rcx+r13]
0x18000e0ca  lea     eax, [rdx-1]
0x18000e0cd  cmp     eax, 1Fh
0x18000e0d0  ja      short loc_18000E0E2
0x18000e0d2  add     ecx, edx
0x18000e0d4  cmp     ecx, r14d
0x18000e0d7  jnb     short loc_18000E0E2
0x18000e0d9  inc     ebx
0x18000e0db  mov     [rbp+57h+var_88], ebx
0x18000e0de  inc     ecx
0x18000e0e0  jmp     short loc_18000E0C0
0x18000e0e2  mov     ebx, 4B6h
0x18000e0e7  jmp     loc_18000E271
0x18000e0ec  mov     eax, [rbp+57h+var_A0]
0x18000e0ef  add     eax, ebx
0x18000e0f1  add     eax, dword ptr [rbp+57h+arg_18]
0x18000e0f4  mov     dword ptr [rbp+57h+lpMem], eax
0x18000e0f7  cmp     eax, 2810h
0x18000e0fc  ja      short loc_18000E0E2
0x18000e0fe  movsxd  rdx, eax; unsigned __int64
0x18000e101  lea     r9, [rbp+57h+dwBytes]; unsigned __int64 *
0x18000e105  mov     ecx, 0Ch; unsigned __int64
0x18000e10a  lea     r8d, [rcx+18h]; unsigned __int64
0x18000e10e  call    ?VariableListSize@@YAK_K00PEA_K@Z; VariableListSize(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000e113  mov     ebx, eax
0x18000e115  test    eax, eax
0x18000e117  jnz     loc_18000E271
0x18000e11d  mov     rcx, [rbp+57h+dwBytes]; dwBytes
0x18000e121  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x18000e126  mov     r14, rax
0x18000e129  mov     qword ptr [rbp+57h+var_58], rax
0x18000e12d  test    rax, rax
0x18000e130  jz      loc_18000E2EA
0x18000e136  mov     dword ptr [rax], 300180h
0x18000e13c  mov     eax, dword ptr [rbp+57h+lpMem]
0x18000e13f  mov     [r14+4], eax
0x18000e143  mov     [r14+8], eax
0x18000e147  mov     qword ptr [rbp+57h+var_80], r15
0x18000e14b  test    r15, r15
0x18000e14e  jz      short loc_18000E160
0x18000e150  mov     rax, [r15]
0x18000e153  mov     rcx, r15
0x18000e156  mov     rax, [rax+8]
0x18000e15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e15f  nop
0x18000e160  lea     rax, [rbp+57h+lpMem]
0x18000e164  mov     [rsp+0E0h+var_B0], rax; struct IXMLDOMNode *
0x18000e169  mov     rax, [rbp+57h+arg_10]
0x18000e16d  mov     [rsp+0E0h+var_B8], rax; __int64
0x18000e172  mov     dword ptr [rsp+0E0h+var_C0], 1; int
0x18000e17a  xor     r9d, r9d; int
0x18000e17d  lea     r8, [rbp+57h+var_58]; int
0x18000e181  lea     rdx, [rbp+57h+var_80]; int
0x18000e185  mov     ecx, dword ptr [rbp+57h+arg_18]; int
0x18000e188  call    ?XwpParseSSIDConfigSSIDNodes@@YAKKV?$CComPtr@UIXMLDOMNodeList@@@ATL@@PEAPEAUDOT11_SSID_LIST@@KHPEAKPEAH@Z; XwpParseSSIDConfigSSIDNodes(ulong,ATL::CComPtr<IXMLDOMNodeList>,DOT11_SSID_LIST * *,ulong,int,ulong *,int *)
0x18000e18d  mov     ebx, eax
0x18000e18f  test    eax, eax
0x18000e191  jnz     loc_18000E257
0x18000e197  mov     ebx, [rbp+57h+var_A0]
0x18000e19a  test    ebx, ebx
0x18000e19c  jle     short loc_18000E1EE
0x18000e19e  mov     rcx, [rbp+57h+var_50]
0x18000e1a2  mov     qword ptr [rbp+57h+var_80], rcx
0x18000e1a6  test    rcx, rcx
0x18000e1a9  jz      short loc_18000E1B8
0x18000e1ab  mov     rax, [rcx]
0x18000e1ae  mov     rax, [rax+8]
0x18000e1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1b7  nop
0x18000e1b8  lea     rax, [rbp+57h+lpMem]
0x18000e1bc  mov     [rsp+0E0h+var_B0], rax; struct IXMLDOMNode *
0x18000e1c1  mov     rax, [rbp+57h+arg_10]
0x18000e1c5  mov     [rsp+0E0h+var_B8], rax; __int64
0x18000e1ca  mov     dword ptr [rsp+0E0h+var_C0], 0; int
0x18000e1d2  mov     r9d, dword ptr [rbp+57h+arg_18]; int
0x18000e1d6  lea     r8, [rbp+57h+var_58]; int
0x18000e1da  lea     rdx, [rbp+57h+var_80]; int
0x18000e1de  mov     ecx, ebx; int
0x18000e1e0  call    ?XwpParseSSIDConfigSSIDNodes@@YAKKV?$CComPtr@UIXMLDOMNodeList@@@ATL@@PEAPEAUDOT11_SSID_LIST@@KHPEAKPEAH@Z; XwpParseSSIDConfigSSIDNodes(ulong,ATL::CComPtr<IXMLDOMNodeList>,DOT11_SSID_LIST * *,ulong,int,ulong *,int *)
0x18000e1e5  mov     ebx, eax
0x18000e1e7  test    eax, eax
0x18000e1e9  jnz     short loc_18000E257
0x18000e1eb  mov     ebx, [rbp+57h+var_A0]
0x18000e1ee  cmp     [rbp+57h+var_88], 0
0x18000e1f2  jle     loc_18000E287
0x18000e1f8  mov     r8d, dword ptr [rbp+57h+arg_18]
0x18000e1fc  add     r8d, ebx
0x18000e1ff  xor     ebx, ebx
0x18000e201  mov     ecx, [rbp+57h+var_84]
0x18000e204  cmp     ebx, ecx
0x18000e206  jnb     short loc_18000E287
0x18000e208  movzx   edx, byte ptr [rbx+r13]
0x18000e20d  mov     dword ptr [rbp+57h+arg_18], edx
0x18000e210  lea     eax, [rdx-1]
0x18000e213  cmp     eax, 1Fh
0x18000e216  ja      short loc_18000E252
0x18000e218  lea     eax, [rdx+rbx]
0x18000e21b  cmp     eax, ecx
0x18000e21d  jnb     short loc_18000E252
0x18000e21f  inc     ebx
0x18000e221  mov     eax, r8d
0x18000e224  lea     rcx, [rax+rax*8]
0x18000e228  inc     r8d
0x18000e22b  mov     dword ptr [rbp+57h+lpMem], r8d
0x18000e22f  mov     [r14+rcx*4+0Ch], edx
0x18000e234  mov     r8d, edx; Size
0x18000e237  mov     edx, ebx
0x18000e239  add     rdx, r13; Src
0x18000e23c  lea     rcx, [rcx+4]
0x18000e240  lea     rcx, [r14+rcx*4]; void *
0x18000e244  call    memcpy_0
0x18000e249  add     ebx, dword ptr [rbp+57h+arg_18]
0x18000e24c  mov     r8d, dword ptr [rbp+57h+lpMem]
0x18000e250  jmp     short loc_18000E201
0x18000e252  mov     ebx, 4B6h
0x18000e257  test    r14, r14
0x18000e25a  jz      short loc_18000E264
0x18000e25c  mov     rcx, r14; lpMem
0x18000e25f  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18000e264  test    rdi, rdi
0x18000e267  jz      short loc_18000E271
0x18000e269  mov     rcx, rdi; lpMem
0x18000e26c  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18000e271  test    r13, r13
0x18000e274  jz      loc_18000DFC2
0x18000e27a  mov     rcx, r13; lpMem
0x18000e27d  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18000e282  jmp     loc_18000DFC2
0x18000e287  lea     r9, [rbp+57h+var_78]; int *
0x18000e28b  lea     r8, [rbp+57h+var_48]; struct IXMLDOMNodeList **
0x18000e28f  lea     rdx, aWlanprofilev2S_0; "WLANProfileV2:SSIDPrefix"
0x18000e296  mov     rcx, [rbp+57h+var_90]; struct IXMLDOMNode *
0x18000e29a  call    ?XcGetNodes@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJ@Z; XcGetNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *)
0x18000e29f  mov     r12, [rbp+57h+var_48]
0x18000e2a3  test    eax, eax
0x18000e2a5  jnz     loc_18000E35F
0x18000e2ab  movsxd  rsi, [rbp+57h+var_78]
0x18000e2af  test    esi, esi
0x18000e2b1  jle     loc_18000E35B
0x18000e2b7  cmp     esi, 20h ; ' '
0x18000e2ba  ja      short loc_18000E252
0x18000e2bc  mov     rdx, rsi; unsigned __int64
0x18000e2bf  lea     r9, [rbp+57h+dwBytes]; unsigned __int64 *
0x18000e2c3  lea     ecx, [rax+0Ch]; unsigned __int64
0x18000e2c6  lea     r8d, [rax+24h]; unsigned __int64
0x18000e2ca  call    ?VariableListSize@@YAK_K00PEA_K@Z; VariableListSize(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000e2cf  mov     ebx, eax
0x18000e2d1  test    eax, eax
0x18000e2d3  jnz     short loc_18000E257
0x18000e2d5  mov     rcx, [rbp+57h+dwBytes]; dwBytes
0x18000e2d9  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x18000e2de  mov     rdi, rax
0x18000e2e1  mov     qword ptr [rbp+57h+var_58], rax
0x18000e2e5  test    rax, rax
0x18000e2e8  jnz     short loc_18000E2FF
0x18000e2ea  call    cs:__imp_GetLastError
0x18000e2f0  mov     ebx, eax
0x18000e2f2  test    eax, eax
0x18000e2f4  jnz     loc_18000E257
0x18000e2fa  jmp     loc_18000E271
0x18000e2ff  mov     dword ptr [rax], 300180h
0x18000e305  mov     [rax+4], esi
0x18000e308  mov     [rax+8], esi
0x18000e30b  mov     [rbp+57h+arg_18], r12
0x18000e30f  test    r12, r12
0x18000e312  jz      short loc_18000E325
  ... truncated ...
```
