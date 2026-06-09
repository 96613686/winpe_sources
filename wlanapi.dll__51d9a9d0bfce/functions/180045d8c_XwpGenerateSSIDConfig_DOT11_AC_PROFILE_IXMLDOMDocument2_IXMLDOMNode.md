# XwpGenerateSSIDConfig(_DOT11_AC_PROFILE *,IXMLDOMDocument2 *,IXMLDOMNode *)

- ea: `0x180045d8c`
- end: `0x1800461aa`
- name: `?XwpGenerateSSIDConfig@@YAKPEAU_DOT11_AC_PROFILE@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z`
- size: `1054`
- prototype: `unsigned int(struct _DOT11_AC_PROFILE *, struct IXMLDOMDocument2 *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800450b4`

## callees

- `0x1800076c0`
- `0x180009654`
- `0x18000dea8`
- `0x18000ec9c`
- `0x180011bf8`
- `0x180014d9c`
- `0x180019a20`
- `0x180045d8c`
- `0x18004e46c`
- `0x18004e6ec`

## string_xrefs

- `0x180046031`: `http://www.microsoft.com/networking/WLAN/profile/v2`
- `0x18004609a`: `http://www.microsoft.com/networking/WLAN/profile/v2`
- `0x1800460ce`: `http://www.microsoft.com/networking/WLAN/profile/v2`
- `0x18004613b`: `http://www.microsoft.com/networking/WLAN/profile/v2`
- `0x180045dd3`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180045e5b`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180045e8f`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180045efd`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180045f45`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180045dda`: `SSIDConfig`
- `0x180046038`: `SSIDBinaryList`
- `0x1800460a1`: `SSIDPrefix`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall XwpGenerateSSIDConfig(
        struct _DOT11_AC_PROFILE *a1,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMNode *a3)
{
  unsigned int v5; // esi
  unsigned int v6; // edi
  unsigned int v7; // edx
  unsigned int v8; // ecx
  unsigned int v9; // r12d
  unsigned int i; // r15d
  __int64 v11; // rsi
  int v12; // eax
  __int64 v13; // rax
  unsigned int j; // r8d
  int v15; // ecx
  unsigned __int8 *v16; // r12
  unsigned int v17; // r8d
  unsigned int k; // r15d
  __int64 v19; // rdx
  __int64 v20; // rcx
  rsize_t v21; // r9
  __int64 v22; // rdx
  unsigned int v23; // r15d
  __int64 v24; // rsi
  __int64 v25; // rax
  struct IXMLDOMNode **v27; // [rsp+28h] [rbp-71h]
  struct IXMLDOMNode **v28; // [rsp+30h] [rbp-69h]
  int v29; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v30; // [rsp+44h] [rbp-55h]
  struct IXMLDOMNode *v31; // [rsp+48h] [rbp-51h] BYREF
  struct IXMLDOMNode *v32; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v33; // [rsp+58h] [rbp-41h]
  unsigned int v34; // [rsp+5Ch] [rbp-3Dh]
  OLECHAR v35[40]; // [rsp+60h] [rbp-39h] BYREF

  v5 = 0;
  v32 = 0;
  v31 = 0;
  v6 = XcAddChildElement(
         a2,
         a3,
         (OLECHAR *)L"SSIDConfig",
         (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v1",
         0,
         &v32);
  if ( !v6 )
  {
    v7 = *(_DWORD *)(*((_QWORD *)a1 + 1) + 4LL);
    v8 = v7;
    if ( v7 > 0x100 )
      v8 = 1;
    v30 = v8;
    v9 = v7 - 1;
    if ( v7 <= 0x100 )
      v9 = 0;
    v33 = v9;
    for ( i = 0; i < v8; ++i )
    {
      v11 = *((_QWORD *)a1 + 1) + 36LL * i;
      if ( (unsigned int)(*(_DWORD *)(v11 + 12) - 1) > 0x1F )
        goto LABEL_46;
      v6 = XcAddChildElement(
             a2,
             v32,
             (OLECHAR *)L"SSID",
             (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v1",
             0,
             &v31);
      if ( v6 )
        goto LABEL_47;
      v6 = XcAddChildElementHexBinary(
             a2,
             v31,
             (OLECHAR *)L"hex",
             (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v1",
             (unsigned __int8 *)(v11 + 16),
             *(_DWORD *)(v11 + 12),
             v28);
      if ( v6 )
        goto LABEL_47;
      v29 = 33;
      v12 = WlanUtf8SsidToDisplayName(v11 + 12, 0, v35, &v29);
      v5 = 0;
      if ( !v12 )
      {
        v13 = -1;
        do
          ++v13;
        while ( v35[v13] );
        if ( (unsigned __int64)(v13 - 1) <= 0xFE )
          XcAddChildElement(
            a2,
            v31,
            (OLECHAR *)L"name",
            (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v1",
            v35,
            0);
      }
      ATL::CComPtrBase<IXMLDOMNode>::Release(&v31);
      v8 = v30;
    }
    if ( (*((_BYTE *)a1 + 4) & 4) != 0 )
    {
      v6 = XcAddChildElementBoolean(
             a2,
             v32,
             L"nonBroadcast",
             L"http://www.microsoft.com/networking/WLAN/profile/v1",
             (*((_DWORD *)a1 + 6) >> 1) & 1,
             v27);
      if ( v6 )
        goto LABEL_47;
      v8 = v30;
    }
    if ( !v9 )
      goto LABEL_50;
    for ( j = 0; j < v9; ++j )
    {
      v15 = *(_DWORD *)(*((_QWORD *)a1 + 1) + 36LL * (v8 + j) + 12);
      if ( (unsigned int)(v15 - 1) > 0x1F )
        goto LABEL_46;
      v5 += v15 + 1;
      v8 = v30;
    }
    v16 = (unsigned __int8 *)Xc_Process_user_allocate(v5);
    if ( !v16 )
    {
      v6 = 14;
      goto LABEL_47;
    }
    v17 = 0;
    for ( k = 0; k < v33 && v17 < v5; ++k )
    {
      v19 = 9LL * (k + v30);
      v20 = *((_QWORD *)a1 + 1);
      v21 = *(unsigned int *)(v20 + 36LL * (k + v30) + 12);
      v29 = v21;
      v16[v17] = v21;
      v34 = v17 + 1;
      v6 = memcpy_s_0(&v16[v34], v5 - v34, (const void *const)(v20 + 16 + 4 * v19), v21);
      if ( v6 )
        goto LABEL_47;
      v17 = v34 + v29;
    }
    v6 = XcAddChildElementHexBinary(
           a2,
           v32,
           (OLECHAR *)L"SSIDBinaryList",
           (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v2",
           v16,
           v5,
           v28);
    if ( !v6 )
    {
LABEL_50:
      v22 = *((_QWORD *)a1 + 5);
      if ( v22 )
      {
        if ( *(_DWORD *)(v22 + 4) )
        {
          v23 = 0;
          while ( 1 )
          {
            v24 = v22 + 36LL * v23;
            if ( (unsigned int)(*(_DWORD *)(v24 + 12) - 1) > 0x1F )
              break;
            v6 = XcAddChildElement(
                   a2,
                   v32,
                   (OLECHAR *)L"SSIDPrefix",
                   (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v2",
                   0,
                   &v31);
            if ( !v6 )
            {
              v6 = XcAddChildElementHexBinary(
                     a2,
                     v31,
                     (OLECHAR *)L"hex",
                     (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v2",
                     (unsigned __int8 *)(v24 + 16),
                     *(_DWORD *)(v24 + 12),
                     v28);
              if ( !v6 )
              {
                v29 = 33;
                if ( !(unsigned int)WlanUtf8SsidToDisplayName(v24 + 12, 0, v35, &v29) )
                {
                  v25 = -1;
                  do
                    ++v25;
                  while ( v35[v25] );
                  if ( (unsigned __int64)(v25 - 1) <= 0xFE )
                    XcAddChildElement(
                      a2,
                      v31,
                      (OLECHAR *)L"name",
                      (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v2",
                      v35,
                      0);
                }
                ATL::CComPtrBase<IXMLDOMNode>::Release(&v31);
                ++v23;
                v22 = *((_QWORD *)a1 + 5);
                if ( v23 < *(_DWORD *)(v22 + 4) )
                  continue;
              }
            }
            goto LABEL_47;
          }
LABEL_46:
          v6 = 1206;
        }
      }
    }
  }
LABEL_47:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v31);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v32);
  return v6;
}

```

## disassembly

```asm
0x180045d8c  push    rbp
0x180045d8e  push    rsi
0x180045d8f  push    rdi
0x180045d90  push    r12
0x180045d92  push    r13
0x180045d94  push    r14
0x180045d96  push    r15
0x180045d98  lea     rbp, [rsp-27h]
0x180045d9d  sub     rsp, 0C0h
0x180045da4  mov     rax, cs:__security_cookie
0x180045dab  xor     rax, rsp
0x180045dae  mov     [rbp+57h+var_40], rax
0x180045db2  mov     rax, r8
0x180045db5  mov     r14, rdx
0x180045db8  mov     r13, rcx
0x180045dbb  xor     esi, esi
0x180045dbd  mov     [rbp+57h+var_A0], rsi
0x180045dc1  mov     [rbp+57h+var_A8], rsi
0x180045dc5  lea     rcx, [rbp+57h+var_A0]
0x180045dc9  mov     [rsp+0F0h+var_C8], rcx; struct IXMLDOMNode **
0x180045dce  mov     [rsp+0F0h+var_D0], rsi; OLECHAR *
0x180045dd3  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x180045dda  lea     r8, aSsidconfig; "SSIDConfig"
0x180045de1  mov     rdx, rax; struct IXMLDOMNode *
0x180045de4  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180045de7  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180045dec  mov     edi, eax
0x180045dee  test    eax, eax
0x180045df0  jnz     loc_180046176
0x180045df6  mov     rcx, [r13+8]
0x180045dfa  mov     edx, [rcx+4]
0x180045dfd  mov     ecx, edx
0x180045dff  lea     r9d, [rsi+1]
0x180045e03  mov     r8d, 100h
0x180045e09  cmp     edx, r8d
0x180045e0c  cmova   ecx, r9d
0x180045e10  mov     [rbp+57h+var_AC], ecx
0x180045e13  lea     r12d, [rdx-1]
0x180045e17  cmovbe  r12d, esi
0x180045e1b  mov     [rbp+57h+var_98], r12d
0x180045e1f  mov     r15d, esi
0x180045e22  cmp     r15d, ecx
0x180045e25  jnb     loc_180045F31
0x180045e2b  mov     eax, r15d
0x180045e2e  lea     rcx, [rax+rax*8]
0x180045e32  mov     rax, [r13+8]
0x180045e36  lea     rsi, [rax+rcx*4]
0x180045e3a  mov     eax, [rsi+0Ch]
0x180045e3d  sub     eax, r9d
0x180045e40  cmp     eax, 1Fh
0x180045e43  ja      loc_180046171
0x180045e49  lea     rax, [rbp+57h+var_A8]
0x180045e4d  mov     [rsp+0F0h+var_C8], rax; struct IXMLDOMNode **
0x180045e52  mov     [rsp+0F0h+var_D0], 0; OLECHAR *
0x180045e5b  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x180045e62  lea     r8, aSsid; "SSID"
0x180045e69  mov     rdx, [rbp+57h+var_A0]; struct IXMLDOMNode *
0x180045e6d  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180045e70  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180045e75  mov     edi, eax
0x180045e77  test    eax, eax
0x180045e79  jnz     loc_180046176
0x180045e7f  lea     rcx, [rsi+10h]
0x180045e83  mov     eax, [rsi+0Ch]
0x180045e86  mov     dword ptr [rsp+0F0h+var_C8], eax; unsigned int
0x180045e8a  mov     [rsp+0F0h+var_D0], rcx; unsigned __int8 *
0x180045e8f  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x180045e96  lea     r8, aHex; "hex"
0x180045e9d  mov     rdx, [rbp+57h+var_A8]; struct IXMLDOMNode *
0x180045ea1  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180045ea4  call    ?XcAddChildElementHexBinary@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2PEAEKPEAPEAU2@@Z; XcAddChildElementHexBinary(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,uchar *,ulong,IXMLDOMNode * *)
0x180045ea9  mov     edi, eax
0x180045eab  test    eax, eax
0x180045ead  jnz     loc_180046176
0x180045eb3  mov     [rbp+57h+var_B0], 21h ; '!'
0x180045eba  lea     r9, [rbp+57h+var_B0]
0x180045ebe  lea     r8, [rbp+57h+var_90]
0x180045ec2  xor     edx, edx
0x180045ec4  lea     rcx, [rsi+0Ch]
0x180045ec8  call    WlanUtf8SsidToDisplayName
0x180045ecd  xor     esi, esi
0x180045ecf  test    eax, eax
0x180045ed1  jnz     short loc_180045F17
0x180045ed3  lea     rcx, [rbp+57h+var_90]
0x180045ed7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180045edb  inc     rax
0x180045ede  cmp     [rcx+rax*2], si
0x180045ee2  jnz     short loc_180045EDB
0x180045ee4  dec     rax
0x180045ee7  cmp     rax, 0FEh
0x180045eed  ja      short loc_180045F17
0x180045eef  mov     [rsp+0F0h+var_C8], rsi; struct IXMLDOMNode **
0x180045ef4  lea     rax, [rbp+57h+var_90]
0x180045ef8  mov     [rsp+0F0h+var_D0], rax; OLECHAR *
0x180045efd  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x180045f04  lea     r8, aName; "name"
0x180045f0b  mov     rdx, [rbp+57h+var_A8]; struct IXMLDOMNode *
0x180045f0f  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180045f12  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180045f17  lea     rcx, [rbp+57h+var_A8]
0x180045f1b  call    ?Release@?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IXMLDOMNode>::Release(void)
0x180045f20  mov     r9d, 1
0x180045f26  add     r15d, r9d
0x180045f29  mov     ecx, [rbp+57h+var_AC]
0x180045f2c  jmp     loc_180045E22
0x180045f31  test    byte ptr [r13+4], 4
0x180045f36  jz      short loc_180045F70
0x180045f38  mov     eax, [r13+18h]
0x180045f3c  shr     eax, 1
0x180045f3e  and     eax, r9d
0x180045f41  mov     dword ptr [rsp+0F0h+var_D0], eax; int
0x180045f45  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x180045f4c  lea     r8, aNonbroadcast; "nonBroadcast"
0x180045f53  mov     rdx, [rbp+57h+var_A0]; struct IXMLDOMNode *
0x180045f57  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180045f5a  call    ?XcAddChildElementBoolean@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2HPEAPEAU2@@Z; XcAddChildElementBoolean(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,int,IXMLDOMNode * *)
0x180045f5f  mov     edi, eax
0x180045f61  test    eax, eax
0x180045f63  jnz     loc_180046176
0x180045f69  mov     ecx, [rbp+57h+var_AC]
0x180045f6c  lea     r9d, [rax+1]
0x180045f70  test    r12d, r12d
0x180045f73  jz      loc_180046057
0x180045f79  xor     edi, edi
0x180045f7b  mov     r8d, edi
0x180045f7e  cmp     r8d, r12d
0x180045f81  jnb     short loc_180045FAB
0x180045f83  lea     eax, [rcx+r8]
0x180045f87  lea     rdx, [rax+rax*8]
0x180045f8b  mov     rax, [r13+8]
0x180045f8f  mov     ecx, [rax+rdx*4+0Ch]
0x180045f93  lea     eax, [rcx-1]
0x180045f96  cmp     eax, 1Fh
0x180045f99  ja      loc_180046171
0x180045f9f  inc     ecx
0x180045fa1  add     esi, ecx
0x180045fa3  add     r8d, r9d
0x180045fa6  mov     ecx, [rbp+57h+var_AC]
0x180045fa9  jmp     short loc_180045F7E
0x180045fab  mov     ecx, esi; dwBytes
0x180045fad  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x180045fb2  mov     r12, rax
0x180045fb5  test    rax, rax
0x180045fb8  jnz     short loc_180045FC2
0x180045fba  lea     edi, [rax+0Eh]
0x180045fbd  jmp     loc_180046176
0x180045fc2  mov     r8d, edi
0x180045fc5  mov     r15d, edi
0x180045fc8  cmp     r15d, [rbp+57h+var_98]
0x180045fcc  jnb     short loc_180046028
0x180045fce  cmp     r8d, esi
0x180045fd1  jnb     short loc_180046028
0x180045fd3  mov     eax, [rbp+57h+var_AC]
0x180045fd6  add     eax, r15d
0x180045fd9  lea     rdx, [rax+rax*8]
0x180045fdd  mov     rcx, [r13+8]
0x180045fe1  mov     r9d, [rcx+rdx*4+0Ch]; SourceSize
0x180045fe6  mov     [rbp+57h+var_B0], r9d
0x180045fea  mov     eax, r8d
0x180045fed  mov     [rax+r12], r9b
0x180045ff1  lea     r10d, [r8+1]
0x180045ff5  mov     [rbp+57h+var_94], r10d
0x180045ff9  lea     r8, [rcx+10h]
0x180045ffd  lea     r8, [r8+rdx*4]; Source
0x180046001  mov     edx, esi
0x180046003  sub     edx, r10d; DestinationSize
0x180046006  mov     ecx, r10d
0x180046009  add     rcx, r12; Destination
0x18004600c  call    memcpy_s_0
0x180046011  mov     edi, eax
0x180046013  test    eax, eax
0x180046015  jnz     loc_180046176
0x18004601b  mov     r8d, [rbp+57h+var_B0]
0x18004601f  add     r8d, [rbp+57h+var_94]
0x180046023  inc     r15d
0x180046026  jmp     short loc_180045FC8
0x180046028  mov     dword ptr [rsp+0F0h+var_C8], esi; unsigned int
0x18004602c  mov     [rsp+0F0h+var_D0], r12; unsigned __int8 *
0x180046031  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WLA"...
0x180046038  lea     r8, aSsidbinarylist; "SSIDBinaryList"
0x18004603f  mov     rdx, [rbp+57h+var_A0]; struct IXMLDOMNode *
0x180046043  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180046046  call    ?XcAddChildElementHexBinary@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2PEAEKPEAPEAU2@@Z; XcAddChildElementHexBinary(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,uchar *,ulong,IXMLDOMNode * *)
0x18004604b  mov     edi, eax
0x18004604d  xor     esi, esi
0x18004604f  test    eax, eax
0x180046051  jnz     loc_180046176
0x180046057  mov     rdx, [r13+28h]
0x18004605b  test    rdx, rdx
0x18004605e  jz      loc_180046176
0x180046064  cmp     [rdx+4], esi
0x180046067  jbe     loc_180046176
0x18004606d  mov     r15d, esi
0x180046070  xor     r12d, r12d
0x180046073  mov     eax, r15d
0x180046076  lea     rcx, [rax+rax*8]
0x18004607a  lea     rsi, [rdx+rcx*4]
0x18004607e  mov     eax, [rsi+0Ch]
0x180046081  dec     eax
0x180046083  cmp     eax, 1Fh
0x180046086  ja      loc_180046171
0x18004608c  lea     rax, [rbp+57h+var_A8]
0x180046090  mov     [rsp+0F0h+var_C8], rax; struct IXMLDOMNode **
0x180046095  mov     [rsp+0F0h+var_D0], r12; OLECHAR *
0x18004609a  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WLA"...
0x1800460a1  lea     r8, aSsidprefix; "SSIDPrefix"
0x1800460a8  mov     rdx, [rbp+57h+var_A0]; struct IXMLDOMNode *
0x1800460ac  mov     rcx, r14; struct IXMLDOMDocument2 *
0x1800460af  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x1800460b4  mov     edi, eax
0x1800460b6  test    eax, eax
0x1800460b8  jnz     loc_180046176
0x1800460be  lea     rcx, [rsi+10h]
0x1800460c2  mov     eax, [rsi+0Ch]
0x1800460c5  mov     dword ptr [rsp+0F0h+var_C8], eax; unsigned int
0x1800460c9  mov     [rsp+0F0h+var_D0], rcx; unsigned __int8 *
0x1800460ce  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WLA"...
0x1800460d5  lea     r8, aHex; "hex"
0x1800460dc  mov     rdx, [rbp+57h+var_A8]; struct IXMLDOMNode *
0x1800460e0  mov     rcx, r14; struct IXMLDOMDocument2 *
0x1800460e3  call    ?XcAddChildElementHexBinary@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2PEAEKPEAPEAU2@@Z; XcAddChildElementHexBinary(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,uchar *,ulong,IXMLDOMNode * *)
0x1800460e8  mov     edi, eax
0x1800460ea  test    eax, eax
0x1800460ec  jnz     loc_180046176
0x1800460f2  mov     [rbp+57h+var_B0], 21h ; '!'
0x1800460f9  lea     r9, [rbp+57h+var_B0]
0x1800460fd  lea     r8, [rbp+57h+var_90]
0x180046101  xor     edx, edx
0x180046103  lea     rcx, [rsi+0Ch]
0x180046107  call    WlanUtf8SsidToDisplayName
0x18004610c  test    eax, eax
0x18004610e  jnz     short loc_180046155
0x180046110  lea     rcx, [rbp+57h+var_90]
0x180046114  or      rax, 0FFFFFFFFFFFFFFFFh
0x180046118  inc     rax
0x18004611b  cmp     [rcx+rax*2], r12w
0x180046120  jnz     short loc_180046118
0x180046122  dec     rax
0x180046125  cmp     rax, 0FEh
0x18004612b  ja      short loc_180046155
0x18004612d  mov     [rsp+0F0h+var_C8], r12; struct IXMLDOMNode **
0x180046132  lea     rax, [rbp+57h+var_90]
0x180046136  mov     [rsp+0F0h+var_D0], rax; OLECHAR *
0x18004613b  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WLA"...
0x180046142  lea     r8, aName; "name"
0x180046149  mov     rdx, [rbp+57h+var_A8]; struct IXMLDOMNode *
0x18004614d  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180046150  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180046155  lea     rcx, [rbp+57h+var_A8]
0x180046159  call    ?Release@?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IXMLDOMNode>::Release(void)
0x18004615e  inc     r15d
0x180046161  mov     rdx, [r13+28h]
0x180046165  cmp     r15d, [rdx+4]
0x180046169  jb      loc_180046073
0x18004616f  jmp     short loc_180046176
0x180046171  mov     edi, 4B6h
0x180046176  lea     rcx, [rbp+57h+var_A8]
0x18004617a  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18004617f  nop
0x180046180  lea     rcx, [rbp+57h+var_A0]
0x180046184  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180046189  mov     eax, edi
0x18004618b  mov     rcx, [rbp+57h+var_40]
0x18004618f  xor     rcx, rsp; StackCookie
0x180046192  call    __security_check_cookie
0x180046197  add     rsp, 0C0h
0x18004619e  pop     r15
0x1800461a0  pop     r14
0x1800461a2  pop     r13
0x1800461a4  pop     r12
0x1800461a6  pop     rdi
0x1800461a7  pop     rsi
0x1800461a8  pop     rbp
0x1800461a9  retn
```
