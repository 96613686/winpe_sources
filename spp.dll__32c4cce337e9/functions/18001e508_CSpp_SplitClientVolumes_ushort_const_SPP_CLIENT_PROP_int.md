# CSpp::_SplitClientVolumes(ushort const *,_SPP_CLIENT_PROP *,int *)

- ea: `0x18001e508`
- end: `0x18001e890`
- name: `?_SplitClientVolumes@CSpp@@AEAAJPEBGPEAU_SPP_CLIENT_PROP@@PEAH@Z`
- size: `904`
- prototype: `__int64 __fastcall(CSpp *this, const unsigned __int16 *, struct _SPP_CLIENT_PROP *, int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800082f0`
- `0x18001be74`

## callees

- `0x1800037e4`
- `0x18000702c`
- `0x18000dd40`
- `0x18001e508`
- `0x180020908`
- `0x1800268b4`
- `0x1800269ac`
- `0x180029ce0`
- `0x18002cc28`
- `0x18002d1e0`
- `0x180034f10`
- `0x18003532c`
- `0x18003534c`
- `0x18003540c`
- `0x180035b00`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001e762`
- `msvcrt!_wcsicmp` at `0x18001e762`
- `msvcrt!wcschr` at `0x18001e670`
- `msvcrt!wcschr` at `0x18001e670`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e822`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e82c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e822`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e82c`

## pseudocode

```c
__int64 __fastcall CSpp::_SplitClientVolumes(
        CSpp *this,
        const unsigned __int16 *a2,
        struct _SPP_CLIENT_PROP *a3,
        int *a4)
{
  const wchar_t *v6; // rsi
  _DWORD *v7; // rbx
  _QWORD *v8; // rdi
  __int16 v9; // ax
  int v10; // eax
  int v11; // r15d
  __int64 v12; // r13
  wchar_t *v13; // rax
  wchar_t *v14; // r15
  bool v15; // sf
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rax
  unsigned int v19; // esi
  __int64 v20; // rdx
  __int64 v21; // r8
  int v23; // [rsp+20h] [rbp-59h] BYREF
  __int16 v24; // [rsp+24h] [rbp-55h]
  __int16 v25; // [rsp+26h] [rbp-53h]
  LPVOID pv; // [rsp+58h] [rbp-21h] BYREF
  wchar_t *String2[2]; // [rsp+60h] [rbp-19h] BYREF
  void *Block; // [rsp+70h] [rbp-9h] BYREF
  unsigned __int16 *v29; // [rsp+78h] [rbp-1h] BYREF
  unsigned __int16 *v30[2]; // [rsp+80h] [rbp+7h] BYREF
  wchar_t *String1[8]; // [rsp+90h] [rbp+17h] BYREF
  int v32; // [rsp+E0h] [rbp+67h]
  void *v33; // [rsp+E8h] [rbp+6Fh] BYREF

  v6 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids, a2);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v23, "CSpp::_SplitClientVolumes", 3085, 1);
  v30[0] = (unsigned __int16 *)&FileName;
  v7 = 0;
  String2[0] = (wchar_t *)&FileName;
  v8 = 0;
  String1[0] = (wchar_t *)&FileName;
  v9 = 3099;
  v33 = 0;
  Block = 0;
  v30[1] = 0;
  String2[1] = 0;
  String1[1] = 0;
  pv = 0;
  v29 = 0;
  if ( !v6 || (v24 = 3099, v9 = 3100, !a3) || (v24 = 3100, v9 = 3101, !a4) )
  {
    v23 = -2147024809;
    goto LABEL_32;
  }
  v23 = 0;
  v24 = 3101;
  *((_DWORD *)a3 + 6) = 0;
  *((_QWORD *)a3 + 4) = 0;
  *a4 = 0;
  v23 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::CreateInstance(&v33);
  v9 = 3108;
  if ( v23 < 0 )
  {
    v7 = v33;
LABEL_32:
    v25 = v9;
    goto LABEL_33;
  }
  v24 = 3108;
  v10 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::CreateInstance(&Block);
  v7 = v33;
  v15 = v10 < 0;
  v8 = Block;
  v23 = v10;
  v9 = 3109;
  if ( v15 )
    goto LABEL_32;
  v11 = 0;
  v32 = 0;
  v24 = 3109;
  while ( *v6 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v6[v12] );
    v13 = wcschr(v6, 0x3Au);
    v14 = v13;
    if ( v13 )
    {
      v23 = CBsString::Set((CBsString *)v30, v6, v13 - v6);
      v9 = 3117;
      if ( v23 < 0 )
        goto LABEL_32;
      v24 = 3117;
      v23 = CBsString::Set((CBsString *)String2, v14 + 1);
      v15 = v23 < 0;
      v9 = 3118;
    }
    else
    {
      v23 = CBsString::Set((CBsString *)v30, v6);
      v9 = 3123;
      if ( v23 < 0 )
        goto LABEL_32;
      v24 = 3123;
      v23 = CBsString::Set((CBsString *)String2, v6);
      v15 = v23 < 0;
      v9 = 3124;
    }
    if ( v15 )
      goto LABEL_32;
    v24 = v9;
    v23 = SxHexDecode((struct CBsString *)v30);
    v9 = 3126;
    if ( v23 < 0 )
      goto LABEL_32;
    v24 = 3126;
    v23 = SxHexDecode((struct CBsString *)String2);
    v9 = 3127;
    if ( v23 < 0 )
      goto LABEL_32;
    v24 = 3127;
    CBsString::Detach((CBsString *)v30, (unsigned __int16 **)&pv);
    if ( (unsigned int)SxIsWinPE()
      || (int)SxGetVolumeDescription((const unsigned __int16 *)pv, (struct CBsString *)String1) < 0
      || !_wcsicmp(String1[0], String2[0]) )
    {
      v11 = v32;
    }
    else
    {
      v11 = 1;
      v32 = 1;
      CBsString::Transfer((CBsString *)String1, (struct CBsString *)String2);
    }
    v23 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::Append(
            v7,
            &pv);
    v9 = 3149;
    if ( v23 < 0 )
      goto LABEL_32;
    v24 = 3149;
    CBsString::Detach((CBsString *)String2, &v29);
    v23 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::Append(
            v8,
            &v29);
    v9 = 3151;
    if ( v23 < 0 )
      goto LABEL_32;
    v24 = 3151;
    v6 += (unsigned int)(v12 + 1);
  }
  v16 = v7[4];
  v17 = *((_QWORD *)v7 + 1);
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 2) = 0;
  *((_QWORD *)a3 + 4) = v17;
  *((_DWORD *)a3 + 6) = v16;
  v18 = v8[1];
  v8[1] = 0;
  v8[2] = 0;
  *((_QWORD *)a3 + 5) = v18;
  *a4 = v11;
LABEL_33:
  CoTaskMemFree(pv);
  CoTaskMemFree(v29);
  v19 = v23;
  CBsString::_Release(String1);
  CBsString::_Release(String2);
  CBsString::_Release(v30);
  if ( v8 )
    CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::Release(v8);
  if ( v7 )
    CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::Release(v7);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v23, v20, v21);
  return v19;
}

```

## disassembly

```asm
0x18001e508  mov     [rsp-8+arg_10], rbx
0x18001e50d  mov     [rsp-8+arg_0], rcx
0x18001e512  push    rbp
0x18001e513  push    rsi
0x18001e514  push    rdi
0x18001e515  push    r12
0x18001e517  push    r13
0x18001e519  push    r14
0x18001e51b  push    r15
0x18001e51d  lea     rbp, [rsp-27h]
0x18001e522  sub     rsp, 0A0h
0x18001e529  mov     r12, r9
0x18001e52c  mov     r14, r8
0x18001e52f  mov     rsi, rdx
0x18001e532  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e539  lea     rax, WPP_GLOBAL_Control
0x18001e540  cmp     rcx, rax
0x18001e543  jz      short loc_18001E566
0x18001e545  test    dword ptr [rcx+1Ch], 20000000h
0x18001e54c  jz      short loc_18001E566
0x18001e54e  mov     rcx, [rcx+10h]
0x18001e552  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001e559  mov     edx, 23h ; '#'
0x18001e55e  mov     r9, rsi
0x18001e561  call    WPP_SF_S
0x18001e566  mov     r9d, 1; unsigned __int16
0x18001e56c  lea     rdx, aCsppSplitclien; "CSpp::_SplitClientVolumes"
0x18001e573  mov     r8d, 0C0Dh; unsigned __int16
0x18001e579  lea     rcx, [rbp+57h+var_B0]; this
0x18001e57d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001e582  xor     r13d, r13d
0x18001e585  lea     rax, FileName
0x18001e58c  mov     [rbp+57h+var_50], rax
0x18001e590  mov     ebx, r13d
0x18001e593  mov     [rbp+57h+String2], rax
0x18001e597  mov     edi, r13d
0x18001e59a  mov     [rbp+57h+String1], rax
0x18001e59e  mov     eax, 0C1Bh
0x18001e5a3  mov     [rbp+57h+arg_8], rbx
0x18001e5a7  mov     [rbp+57h+Block], r13
0x18001e5ab  mov     [rbp+57h+var_48], r13
0x18001e5af  mov     [rbp+57h+var_68], r13
0x18001e5b3  mov     [rbp+57h+var_38], r13
0x18001e5b7  mov     [rbp+57h+pv], r13
0x18001e5bb  mov     [rbp+57h+var_58], r13
0x18001e5bf  test    rsi, rsi
0x18001e5c2  jz      loc_18001E813
0x18001e5c8  mov     [rbp+57h+var_AC], ax
0x18001e5cc  mov     eax, 0C1Ch
0x18001e5d1  test    r14, r14
0x18001e5d4  jz      loc_18001E813
0x18001e5da  mov     [rbp+57h+var_AC], ax
0x18001e5de  mov     eax, 0C1Dh
0x18001e5e3  test    r12, r12
0x18001e5e6  jz      loc_18001E813
0x18001e5ec  lea     rcx, [rbp+57h+arg_8]
0x18001e5f0  mov     [rbp+57h+var_B0], r13d
0x18001e5f4  mov     [rbp+57h+var_AC], ax
0x18001e5f8  mov     [r14+18h], r13d
0x18001e5fc  mov     [r14+20h], r13
0x18001e600  mov     [r12], r13d
0x18001e604  call    ?CreateInstance@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@SAJPEAPEAV1@@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::CreateInstance(CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)> * *)
0x18001e609  mov     [rbp+57h+var_B0], eax
0x18001e60c  test    eax, eax
0x18001e60e  mov     eax, 0C24h
0x18001e613  jns     short loc_18001E61E
0x18001e615  mov     rbx, [rbp+57h+arg_8]
0x18001e619  jmp     loc_18001E81A
0x18001e61e  lea     rcx, [rbp+57h+Block]
0x18001e622  mov     [rbp+57h+var_AC], ax
0x18001e626  call    ?CreateInstance@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@SAJPEAPEAV1@@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::CreateInstance(CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)> * *)
0x18001e62b  mov     rbx, [rbp+57h+arg_8]
0x18001e62f  test    eax, eax
0x18001e631  mov     rdi, [rbp+57h+Block]
0x18001e635  mov     [rbp+57h+var_B0], eax
0x18001e638  mov     eax, 0C25h
0x18001e63d  js      loc_18001E81A
0x18001e643  mov     r15d, r13d
0x18001e646  mov     dword ptr [rbp+57h+arg_0], r13d
0x18001e64a  mov     [rbp+57h+var_AC], ax
0x18001e64e  cmp     [rsi], r13w
0x18001e652  jz      loc_18001E7DE
0x18001e658  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001e65c  xor     eax, eax
0x18001e65e  inc     r13
0x18001e661  cmp     [rsi+r13*2], ax
0x18001e666  jnz     short loc_18001E65E
0x18001e668  mov     edx, 3Ah ; ':'; Ch
0x18001e66d  mov     rcx, rsi; Str
0x18001e670  call    cs:__imp_wcschr
0x18001e676  mov     rdx, rsi; unsigned __int16 *
0x18001e679  lea     rcx, [rbp+57h+var_50]; this
0x18001e67d  mov     r15, rax
0x18001e680  test    rax, rax
0x18001e683  jz      short loc_18001E6C0
0x18001e685  mov     r8, rax
0x18001e688  sub     r8, rsi
0x18001e68b  sar     r8, 1; unsigned int
0x18001e68e  call    ?Set@CBsString@@QEAAJPEBGK@Z; CBsString::Set(ushort const *,ulong)
0x18001e693  mov     [rbp+57h+var_B0], eax
0x18001e696  test    eax, eax
0x18001e698  mov     eax, 0C2Dh
0x18001e69d  js      loc_18001E81A
0x18001e6a3  lea     rdx, [r15+2]; unsigned __int16 *
0x18001e6a7  mov     [rbp+57h+var_AC], ax
0x18001e6ab  lea     rcx, [rbp+57h+String2]; this
0x18001e6af  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18001e6b4  mov     [rbp+57h+var_B0], eax
0x18001e6b7  test    eax, eax
0x18001e6b9  mov     eax, 0C2Eh
0x18001e6be  jmp     short loc_18001E6EF
0x18001e6c0  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18001e6c5  mov     [rbp+57h+var_B0], eax
0x18001e6c8  test    eax, eax
0x18001e6ca  mov     eax, 0C33h
0x18001e6cf  js      loc_18001E81A
0x18001e6d5  mov     rdx, rsi; unsigned __int16 *
0x18001e6d8  mov     [rbp+57h+var_AC], ax
0x18001e6dc  lea     rcx, [rbp+57h+String2]; this
0x18001e6e0  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18001e6e5  mov     [rbp+57h+var_B0], eax
0x18001e6e8  test    eax, eax
0x18001e6ea  mov     eax, 0C34h
0x18001e6ef  js      loc_18001E81A
0x18001e6f5  lea     rcx, [rbp+57h+var_50]; struct CBsString *
0x18001e6f9  mov     [rbp+57h+var_AC], ax
0x18001e6fd  call    ?SxHexDecode@@YAJPEAVCBsString@@@Z; SxHexDecode(CBsString *)
0x18001e702  mov     [rbp+57h+var_B0], eax
0x18001e705  test    eax, eax
0x18001e707  mov     eax, 0C36h
0x18001e70c  js      loc_18001E81A
0x18001e712  lea     rcx, [rbp+57h+String2]; struct CBsString *
0x18001e716  mov     [rbp+57h+var_AC], ax
0x18001e71a  call    ?SxHexDecode@@YAJPEAVCBsString@@@Z; SxHexDecode(CBsString *)
0x18001e71f  mov     [rbp+57h+var_B0], eax
0x18001e722  test    eax, eax
0x18001e724  mov     eax, 0C37h
0x18001e729  js      loc_18001E81A
0x18001e72f  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x18001e733  mov     [rbp+57h+var_AC], ax
0x18001e737  lea     rcx, [rbp+57h+var_50]; this
0x18001e73b  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x18001e740  call    ?SxIsWinPE@@YAHXZ; SxIsWinPE(void)
0x18001e745  test    eax, eax
0x18001e747  jnz     short loc_18001E785
0x18001e749  mov     rcx, [rbp+57h+pv]; unsigned __int16 *
0x18001e74d  lea     rdx, [rbp+57h+String1]; this
0x18001e751  call    ?SxGetVolumeDescription@@YAJPEBGPEAVCBsString@@@Z; SxGetVolumeDescription(ushort const *,CBsString *)
0x18001e756  test    eax, eax
0x18001e758  js      short loc_18001E785
0x18001e75a  mov     rdx, [rbp+57h+String2]; String2
0x18001e75e  mov     rcx, [rbp+57h+String1]; String1
0x18001e762  call    cs:__imp__wcsicmp
0x18001e768  test    eax, eax
0x18001e76a  jz      short loc_18001E785
0x18001e76c  mov     r15d, 1
0x18001e772  lea     rdx, [rbp+57h+String2]; struct CBsString *
0x18001e776  lea     rcx, [rbp+57h+String1]; this
0x18001e77a  mov     dword ptr [rbp+57h+arg_0], r15d
0x18001e77e  call    ?Transfer@CBsString@@QEAAXPEAV1@@Z; CBsString::Transfer(CBsString *)
0x18001e783  jmp     short loc_18001E789
0x18001e785  mov     r15d, dword ptr [rbp+57h+arg_0]
0x18001e789  lea     rdx, [rbp+57h+pv]
0x18001e78d  mov     rcx, rbx
0x18001e790  call    ?Append@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@QEAAJPEAPEAG@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::Append(ushort * *)
0x18001e795  mov     [rbp+57h+var_B0], eax
0x18001e798  test    eax, eax
0x18001e79a  mov     eax, 0C4Dh
0x18001e79f  js      short loc_18001E81A
0x18001e7a1  lea     rdx, [rbp+57h+var_58]; unsigned __int16 **
0x18001e7a5  mov     [rbp+57h+var_AC], ax
0x18001e7a9  lea     rcx, [rbp+57h+String2]; this
0x18001e7ad  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x18001e7b2  lea     rdx, [rbp+57h+var_58]
0x18001e7b6  mov     rcx, rdi
0x18001e7b9  call    ?Append@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@QEAAJPEAPEAG@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::Append(ushort * *)
0x18001e7be  mov     [rbp+57h+var_B0], eax
0x18001e7c1  test    eax, eax
0x18001e7c3  mov     eax, 0C4Fh
0x18001e7c8  js      short loc_18001E81A
0x18001e7ca  mov     [rbp+57h+var_AC], ax
0x18001e7ce  lea     eax, [r13+1]
0x18001e7d2  lea     rsi, [rsi+rax*2]
0x18001e7d6  xor     r13d, r13d
0x18001e7d9  jmp     loc_18001E64E
0x18001e7de  mov     eax, [rbx+10h]
0x18001e7e1  mov     rcx, [rbx+8]
0x18001e7e5  mov     [rbx+8], r13
0x18001e7e9  mov     qword ptr [rbx+10h], 0
0x18001e7f1  mov     [r14+20h], rcx
0x18001e7f5  mov     [r14+18h], eax
0x18001e7f9  mov     rax, [rdi+8]
0x18001e7fd  mov     [rdi+8], r13
0x18001e801  mov     qword ptr [rdi+10h], 0
0x18001e809  mov     [r14+28h], rax
0x18001e80d  mov     [r12], r15d
0x18001e811  jmp     short loc_18001E81E
0x18001e813  mov     [rbp+57h+var_B0], 80070057h
0x18001e81a  mov     [rbp+57h+var_AA], ax
0x18001e81e  mov     rcx, [rbp+57h+pv]; pv
0x18001e822  call    cs:__imp_CoTaskMemFree
0x18001e828  mov     rcx, [rbp+57h+var_58]; pv
0x18001e82c  call    cs:__imp_CoTaskMemFree
0x18001e832  mov     esi, [rbp+57h+var_B0]
0x18001e835  lea     rcx, [rbp+57h+String1]; this
0x18001e839  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001e83e  lea     rcx, [rbp+57h+String2]; this
0x18001e842  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001e847  lea     rcx, [rbp+57h+var_50]; this
0x18001e84b  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001e850  test    rdi, rdi
0x18001e853  jz      short loc_18001E85D
0x18001e855  mov     rcx, rdi; Block
0x18001e858  call    ?Release@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@QEAAKXZ; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::Release(void)
0x18001e85d  test    rbx, rbx
0x18001e860  jz      short loc_18001E86A
0x18001e862  mov     rcx, rbx; Block
0x18001e865  call    ?Release@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@QEAAKXZ; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::Release(void)
0x18001e86a  lea     rcx, [rbp+57h+var_B0]; this
0x18001e86e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001e873  mov     rbx, [rsp+0D0h+arg_10]
0x18001e87b  mov     eax, esi
0x18001e87d  add     rsp, 0A0h
0x18001e884  pop     r15
0x18001e886  pop     r14
0x18001e888  pop     r13
0x18001e88a  pop     r12
0x18001e88c  pop     rdi
0x18001e88d  pop     rsi
0x18001e88e  pop     rbp
0x18001e88f  retn
```
