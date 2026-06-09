# CVdsIscsiPortal::SetIpsecSecurityLocal(unsigned __int64,_VDS_ISCSI_IPSEC_KEY *)

- ea: `0x14004ea00`
- end: `0x14004ed40`
- name: `?SetIpsecSecurityLocal@CVdsIscsiPortal@@UEAAJ_KPEAU_VDS_ISCSI_IPSEC_KEY@@@Z`
- size: `832`
- prototype: `__int64 __fastcall(CVdsIscsiPortal *__hidden this, unsigned __int64, struct _VDS_ISCSI_IPSEC_KEY *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140012c48`
- `0x14001f220`
- `0x14002e123`
- `0x14004ea00`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004ea45`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004ea45`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14004ed17`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14004ed17`
- `vdsutil!VdsTraceW` at `0x14004ec52`
- `vdsutil!VdsTraceW` at `0x14004ec6e`
- `vdsutil!VdsTraceW` at `0x14004ecc9`
- `vdsutil!VdsTraceW` at `0x14004ec52`
- `vdsutil!VdsTraceW` at `0x14004ec6e`
- `vdsutil!VdsTraceW` at `0x14004ecc9`

## string_xrefs

- `0x14004ea34`: `CVdsIscsiPortal::SetIpsecSecurityLocal`
- `0x14004eac2`: `CVdsIscsiPortal::SetIpsecSecurityLocal, 1, hr = %lX`
- `0x14004ecbd`: `CVdsIscsiPortal::SetIpsecSecurityLocal, 2, hr = %lX`
- `0x14004ec9a`: `CVdsIscsiPortal::SetIpsecSecurityLocal, 3, hr = %lX`
- `0x14004ec91`: `CVdsIscsiPortal::SetIpsecSecurityLocal, 4, hr = %lX`
- `0x14004ec88`: `CVdsIscsiPortal::SetIpsecSecurityLocal, 5, hr = %lX`
- `0x14004ec7f`: `CVdsIscsiPortal::SetIpsecSecurityLocal, 6, hr = %lX`
- `0x14004ec76`: `CVdsIscsiPortal::SetIpsecSecurityLocal, 7, hr = %lX`
- `0x14004ec62`: `CVdsIscsiPortal::SetIpsecSecurityLocal, 8`
- `0x14004ec46`: `CVdsIscsiPortal::SetIpsecSecurityLocal, 9, hr = %lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CVdsIscsiPortal::SetIpsecSecurityLocal(
        CVdsIscsiPortal *this,
        __int64 a2,
        struct _VDS_ISCSI_IPSEC_KEY *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // edi
  int v9; // esi
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v22)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v26[24]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v27[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v28[560]; // [rsp+90h] [rbp-70h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v26, 0x5Eu, "CVdsIscsiPortal::SetIpsecSecurityLocal");
  memset_0(v27, 0, 0x23Cu);
  v25 = 0;
  v24 = 0;
  v23 = 0;
  v22 = 0;
  v21 = 0;
  v20 = 0;
  v18 = 0;
  v19 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(*((_QWORD *)this + 9) + 16LL) + 32LL))(
         *((_QWORD *)this + 9) + 16LL,
         &v25);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = 0;
    v9 = 0;
    while ( 1 )
    {
      v18 = 0;
      ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v23);
      v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v25 + 24LL))(
              v25,
              1,
              &v23,
              &v18);
      v7 = v10;
      if ( v10 < 0 )
      {
        VdsTraceW(0, L"CVdsIscsiPortal::SetIpsecSecurityLocal, 2, hr = %lX", (unsigned int)v10);
        goto LABEL_26;
      }
      if ( v10 == 1 )
        break;
      ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v21);
      v11 = (**v23)(v23, &IID_IVdsIscsiInitiatorAdapter, &v21);
      v7 = v11;
      if ( v11 < 0 )
      {
        VdsTraceW(0, L"CVdsIscsiPortal::SetIpsecSecurityLocal, 3, hr = %lX", (unsigned int)v11);
        goto LABEL_26;
      }
      ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v24);
      v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 32LL))(v21, &v24);
      v7 = v12;
      if ( v12 < 0 )
      {
        VdsTraceW(0, L"CVdsIscsiPortal::SetIpsecSecurityLocal, 4, hr = %lX", (unsigned int)v12);
        goto LABEL_26;
      }
      while ( 1 )
      {
        v19 = 0;
        ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v22);
        v13 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v24 + 24LL))(
                v24,
                1,
                &v22,
                &v19);
        v7 = v13;
        if ( v13 == 1 )
          break;
        if ( v13 < 0 )
        {
          VdsTraceW(0, L"CVdsIscsiPortal::SetIpsecSecurityLocal, 5, hr = %lX", (unsigned int)v13);
          goto LABEL_26;
        }
        ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v20);
        v14 = (**v22)(v22, &IID_IVdsIscsiInitiatorPortal, &v20);
        v7 = v14;
        if ( v14 < 0 )
        {
          VdsTraceW(0, L"CVdsIscsiPortal::SetIpsecSecurityLocal, 6, hr = %lX", (unsigned int)v14);
          goto LABEL_26;
        }
        memset_0(v27, 0, 0x23Cu);
        v15 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v20 + 24LL))(v20, v27);
        v7 = v15;
        if ( v15 < 0 )
        {
          VdsTraceW(0, L"CVdsIscsiPortal::SetIpsecSecurityLocal, 7, hr = %lX", (unsigned int)v15);
          goto LABEL_26;
        }
        v16 = (*(__int64 (__fastcall **)(char *, _BYTE *, __int64, struct _VDS_ISCSI_IPSEC_KEY *))(*((_QWORD *)this - 1)
                                                                                                 + 72LL))(
                (char *)this - 8,
                v28,
                a2,
                a3);
        v7 = v16;
        if ( v16 == -2147212288 )
        {
          VdsTraceW(2, L"CVdsIscsiPortal::SetIpsecSecurityLocal, 8");
          goto LABEL_26;
        }
        if ( v16 < 0 )
        {
          VdsTraceW(1, L"CVdsIscsiPortal::SetIpsecSecurityLocal, 9, hr = %lX", (unsigned int)v16);
          v9 = 1;
        }
        else
        {
          v8 = 1;
        }
      }
    }
    if ( v9 )
      v7 = v8 != 0 ? 272130 : -2147467259;
    else
      v7 = 0;
  }
  else
  {
    VdsTraceW(0, L"CVdsIscsiPortal::SetIpsecSecurityLocal, 1, hr = %lX", (unsigned int)v6);
  }
LABEL_26:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v22);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v23);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v26);
  return v7;
}

```

## disassembly

```asm
0x14004ea00  push    rbp
0x14004ea02  push    rbx
0x14004ea03  push    rsi
0x14004ea04  push    rdi
0x14004ea05  push    r12
0x14004ea07  push    r14
0x14004ea09  push    r15
0x14004ea0b  lea     rbp, [rsp-1D0h]
0x14004ea13  sub     rsp, 2D0h
0x14004ea1a  mov     rax, cs:__security_cookie
0x14004ea21  xor     rax, rsp
0x14004ea24  mov     [rbp+200h+var_40], rax
0x14004ea2b  mov     r12, r8
0x14004ea2e  mov     r15, rdx
0x14004ea31  mov     r14, rcx
0x14004ea34  lea     r8, aCvdsiscsiporta; "CVdsIscsiPortal::SetIpsecSecurityLocal"
0x14004ea3b  mov     edx, 5Eh ; '^'
0x14004ea40  lea     rcx, [rsp+300h+var_298]
0x14004ea45  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14004ea4b  nop
0x14004ea4c  xor     edx, edx; Val
0x14004ea4e  mov     r8d, 23Ch; Size
0x14004ea54  lea     rcx, [rbp+200h+var_280]; void *
0x14004ea58  call    memset_0
0x14004ea5d  mov     [rsp+300h+var_2A0], 0
0x14004ea66  mov     [rsp+300h+var_2A8], 0
0x14004ea6f  mov     [rsp+300h+var_2B0], 0
0x14004ea78  mov     [rsp+300h+var_2B8], 0
0x14004ea81  mov     [rsp+300h+var_2C0], 0
0x14004ea8a  mov     [rsp+300h+var_2C8], 0
0x14004ea93  mov     [rsp+300h+var_2D0], 0
0x14004ea9b  mov     [rsp+300h+var_2CC], 0
0x14004eaa3  mov     rcx, [r14+48h]
0x14004eaa7  add     rcx, 10h
0x14004eaab  mov     rax, [rcx]
0x14004eaae  lea     rdx, [rsp+300h+var_2A0]
0x14004eab3  mov     rax, [rax+20h]
0x14004eab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004eabc  mov     ebx, eax
0x14004eabe  test    eax, eax
0x14004eac0  jns     short loc_14004EACE
0x14004eac2  lea     rdx, aCvdsiscsiporta_21; "CVdsIscsiPortal::SetIpsecSecurityLocal,"...
0x14004eac9  jmp     loc_14004ECC4
0x14004eace  xor     edi, edi
0x14004ead0  xor     esi, esi
0x14004ead2  mov     [rsp+300h+var_2D0], 0
0x14004eada  lea     rcx, [rsp+300h+var_2B0]
0x14004eadf  call    ?Release@?$CComPtrBase@UIVdsIscsiPortal@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVdsIscsiPortal>::Release(void)
0x14004eae4  mov     rcx, [rsp+300h+var_2A0]
0x14004eae9  mov     rax, [rcx]
0x14004eaec  lea     r9, [rsp+300h+var_2D0]
0x14004eaf1  lea     r8, [rsp+300h+var_2B0]
0x14004eaf6  mov     edx, 1
0x14004eafb  mov     rax, [rax+18h]
0x14004eaff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004eb04  mov     ebx, eax
0x14004eb06  test    eax, eax
0x14004eb08  js      loc_14004ECBD
0x14004eb0e  cmp     eax, 1
0x14004eb11  jz      loc_14004ECA3
0x14004eb17  lea     rcx, [rsp+300h+var_2C0]
0x14004eb1c  call    ?Release@?$CComPtrBase@UIVdsIscsiPortal@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVdsIscsiPortal>::Release(void)
0x14004eb21  mov     rcx, [rsp+300h+var_2B0]
0x14004eb26  mov     rax, [rcx]
0x14004eb29  lea     r8, [rsp+300h+var_2C0]
0x14004eb2e  lea     rdx, IID_IVdsIscsiInitiatorAdapter
0x14004eb35  mov     rax, [rax]
0x14004eb38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004eb3d  mov     ebx, eax
0x14004eb3f  test    eax, eax
0x14004eb41  js      loc_14004EC9A
0x14004eb47  lea     rcx, [rsp+300h+var_2A8]
0x14004eb4c  call    ?Release@?$CComPtrBase@UIVdsIscsiPortal@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVdsIscsiPortal>::Release(void)
0x14004eb51  mov     rcx, [rsp+300h+var_2C0]
0x14004eb56  mov     rax, [rcx]
0x14004eb59  lea     rdx, [rsp+300h+var_2A8]
0x14004eb5e  mov     rax, [rax+20h]
0x14004eb62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004eb67  mov     ebx, eax
0x14004eb69  test    eax, eax
0x14004eb6b  js      loc_14004EC91
0x14004eb71  mov     [rsp+300h+var_2CC], 0
0x14004eb79  lea     rcx, [rsp+300h+var_2B8]
0x14004eb7e  call    ?Release@?$CComPtrBase@UIVdsIscsiPortal@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVdsIscsiPortal>::Release(void)
0x14004eb83  mov     rcx, [rsp+300h+var_2A8]
0x14004eb88  mov     rax, [rcx]
0x14004eb8b  lea     r9, [rsp+300h+var_2CC]
0x14004eb90  lea     r8, [rsp+300h+var_2B8]
0x14004eb95  mov     edx, 1
0x14004eb9a  mov     rax, [rax+18h]
0x14004eb9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004eba3  mov     ebx, eax
0x14004eba5  cmp     eax, 1
0x14004eba8  jz      loc_14004EAD2
0x14004ebae  test    eax, eax
0x14004ebb0  js      loc_14004EC88
0x14004ebb6  lea     rcx, [rsp+300h+var_2C8]
0x14004ebbb  call    ?Release@?$CComPtrBase@UIVdsIscsiPortal@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVdsIscsiPortal>::Release(void)
0x14004ebc0  mov     rcx, [rsp+300h+var_2B8]
0x14004ebc5  mov     rax, [rcx]
0x14004ebc8  lea     r8, [rsp+300h+var_2C8]
0x14004ebcd  lea     rdx, IID_IVdsIscsiInitiatorPortal
0x14004ebd4  mov     rax, [rax]
0x14004ebd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ebdc  mov     ebx, eax
0x14004ebde  test    eax, eax
0x14004ebe0  js      loc_14004EC7F
0x14004ebe6  xor     edx, edx; Val
0x14004ebe8  mov     r8d, 23Ch; Size
0x14004ebee  lea     rcx, [rbp+200h+var_280]; void *
0x14004ebf2  call    memset_0
0x14004ebf7  mov     rcx, [rsp+300h+var_2C8]
0x14004ebfc  mov     rax, [rcx]
0x14004ebff  lea     rdx, [rbp+200h+var_280]
0x14004ec03  mov     rax, [rax+18h]
0x14004ec07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ec0c  mov     ebx, eax
0x14004ec0e  test    eax, eax
0x14004ec10  js      short loc_14004EC76
0x14004ec12  lea     rcx, [r14-8]
0x14004ec16  mov     rax, [rcx]
0x14004ec19  mov     r9, r12
0x14004ec1c  mov     r8, r15
0x14004ec1f  lea     rdx, [rbp+200h+var_270]
0x14004ec23  mov     rax, [rax+48h]
0x14004ec27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ec2c  mov     ebx, eax
0x14004ec2e  cmp     eax, 80042400h
0x14004ec33  jz      short loc_14004EC62
0x14004ec35  test    eax, eax
0x14004ec37  js      short loc_14004EC43
0x14004ec39  mov     edi, 1
0x14004ec3e  jmp     loc_14004EB71
0x14004ec43  mov     r8d, eax
0x14004ec46  lea     rdx, aCvdsiscsiporta_5; "CVdsIscsiPortal::SetIpsecSecurityLocal,"...
0x14004ec4d  mov     ecx, 1
0x14004ec52  call    cs:__imp_VdsTraceW
0x14004ec58  mov     esi, 1
0x14004ec5d  jmp     loc_14004EB71
0x14004ec62  lea     rdx, aCvdsiscsiporta_35; "CVdsIscsiPortal::SetIpsecSecurityLocal,"...
0x14004ec69  mov     ecx, 2
0x14004ec6e  call    cs:__imp_VdsTraceW
0x14004ec74  jmp     short loc_14004ECD0
0x14004ec76  lea     rdx, aCvdsiscsiporta_12; "CVdsIscsiPortal::SetIpsecSecurityLocal,"...
0x14004ec7d  jmp     short loc_14004ECC4
0x14004ec7f  lea     rdx, aCvdsiscsiporta_39; "CVdsIscsiPortal::SetIpsecSecurityLocal,"...
0x14004ec86  jmp     short loc_14004ECC4
0x14004ec88  lea     rdx, aCvdsiscsiporta_25; "CVdsIscsiPortal::SetIpsecSecurityLocal,"...
0x14004ec8f  jmp     short loc_14004ECC4
0x14004ec91  lea     rdx, aCvdsiscsiporta_11; "CVdsIscsiPortal::SetIpsecSecurityLocal,"...
0x14004ec98  jmp     short loc_14004ECC4
0x14004ec9a  lea     rdx, aCvdsiscsiporta_27; "CVdsIscsiPortal::SetIpsecSecurityLocal,"...
0x14004eca1  jmp     short loc_14004ECC4
0x14004eca3  test    esi, esi
0x14004eca5  jz      short loc_14004ECB9
0x14004eca7  neg     edi
0x14004eca9  sbb     ebx, ebx
0x14004ecab  and     ebx, 8003E6FDh
0x14004ecb1  add     ebx, 80004005h
0x14004ecb7  jmp     short loc_14004ECD0
0x14004ecb9  xor     ebx, ebx
0x14004ecbb  jmp     short loc_14004ECD0
0x14004ecbd  lea     rdx, aCvdsiscsiporta_19; "CVdsIscsiPortal::SetIpsecSecurityLocal,"...
0x14004ecc4  mov     r8d, eax
0x14004ecc7  xor     ecx, ecx
0x14004ecc9  call    cs:__imp_VdsTraceW
0x14004eccf  nop
0x14004ecd0  lea     rcx, [rsp+300h+var_2C8]
0x14004ecd5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004ecda  nop
0x14004ecdb  lea     rcx, [rsp+300h+var_2C0]
0x14004ece0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004ece5  nop
0x14004ece6  lea     rcx, [rsp+300h+var_2B8]
0x14004eceb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004ecf0  nop
0x14004ecf1  lea     rcx, [rsp+300h+var_2B0]
0x14004ecf6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004ecfb  nop
0x14004ecfc  lea     rcx, [rsp+300h+var_2A8]
0x14004ed01  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004ed06  nop
0x14004ed07  lea     rcx, [rsp+300h+var_2A0]
0x14004ed0c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004ed11  nop
0x14004ed12  lea     rcx, [rsp+300h+var_298]
0x14004ed17  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14004ed1d  mov     eax, ebx
0x14004ed1f  mov     rcx, [rbp+200h+var_40]
0x14004ed26  xor     rcx, rsp; StackCookie
0x14004ed29  call    __security_check_cookie
0x14004ed2e  add     rsp, 2D0h
0x14004ed35  pop     r15
0x14004ed37  pop     r14
0x14004ed39  pop     r12
0x14004ed3b  pop     rdi
0x14004ed3c  pop     rsi
0x14004ed3d  pop     rbx
0x14004ed3e  pop     rbp
0x14004ed3f  retn
```
