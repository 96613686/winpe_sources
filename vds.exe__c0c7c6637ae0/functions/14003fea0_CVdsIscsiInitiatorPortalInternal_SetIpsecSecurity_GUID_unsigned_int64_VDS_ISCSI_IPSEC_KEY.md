# CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity(_GUID,unsigned __int64,_VDS_ISCSI_IPSEC_KEY *)

- ea: `0x14003fea0`
- end: `0x1400401a8`
- name: `?SetIpsecSecurity@CVdsIscsiInitiatorPortalInternal@@UEAAJU_GUID@@_KPEAU_VDS_ISCSI_IPSEC_KEY@@@Z`
- size: `776`
- prototype: `__int64 __fastcall(CVdsIscsiInitiatorPortalInternal *__hidden this, struct _GUID *__struct_ptr, unsigned __int64, struct _VDS_ISCSI_IPSEC_KEY *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14000dd3c`
- `0x140012c48`
- `0x14002e123`
- `0x14003fea0`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004013e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140040156`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004013e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140040156`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003ff6e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003ff6e`
- `vdsutil!VdsIscsiIpAddressToIpsecId` at `0x140040068`
- `vdsutil!VdsIscsiIpAddressToIpsecId` at `0x140040068`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003ff23`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003ff23`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140040169`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140040169`
- `vdsutil!VdsTraceW` at `0x14003ffa6`
- `vdsutil!VdsTraceW` at `0x1400400d3`
- `vdsutil!VdsTraceW` at `0x1400400f0`
- `vdsutil!VdsTraceW` at `0x14004010d`
- `vdsutil!VdsTraceW` at `0x14004012a`
- `vdsutil!VdsTraceW` at `0x14003ffa6`
- `vdsutil!VdsTraceW` at `0x1400400d3`
- `vdsutil!VdsTraceW` at `0x1400400f0`
- `vdsutil!VdsTraceW` at `0x14004010d`
- `vdsutil!VdsTraceW` at `0x14004012a`

## string_xrefs

- `0x140040104`: `CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: Could not retrieve target portal object from provider: %X`
- `0x1400400e7`: `CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: spPortalUnk->QueryInterface IID_IVdsIscsiPortal: %X`
- `0x14004003c`: `CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: spPortal->GetProperties: %X`
- `0x14003ff13`: `CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity()`
- `0x140040121`: `CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: Could not access necessary function in iSCSI library.`
- `0x14003ff9a`: `CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: m_pParentAdapter->GetProperties: %X`
- `0x140040074`: `CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: VdsIscsiIpAddressToIpsecId: %X`
- `0x1400400ca`: `CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: SetIScsiIKEInfoW failed: %X`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity(
        CVdsIscsiInitiatorPortalInternal *this,
        struct _GUID *a2,
        __int64 a3,
        struct _VDS_ISCSI_IPSEC_KEY *a4)
{
  FARPROC ProcAddress; // r14
  int v9; // eax
  int v10; // ebx
  int ObjectFromProviders; // eax
  int v12; // edi
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // r9
  unsigned int v17; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  struct IUnknown *v20; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v21; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v23; // [rsp+60h] [rbp-A0h]
  struct _GUID v24; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v25[16]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v26; // [rsp+90h] [rbp-70h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-60h]
  _BYTE v28[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v29[560]; // [rsp+C0h] [rbp-40h] BYREF

  v26 = 0;
  pv = 0;
  v20 = 0;
  v19 = 0;
  memset_0(v28, 0, 0x23Cu);
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v25, 0x5Eu, "CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity()");
  v26 = 0;
  pv = 0;
  memset_0(v28, 0, 0x23Cu);
  v21 = 0;
  *(_OWORD *)v22 = 0;
  v23 = 0;
  if ( CVdsService::m_hIscsidscModule
    && (ProcAddress = GetProcAddress(CVdsService::m_hIscsidscModule, "SetIScsiIKEInfoW")) != 0 )
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 8) + 24LL))(*((_QWORD *)this + 8), &v26);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v24 = *a2;
      ObjectFromProviders = CVdsService::GetObjectFromProviders(&v24, VDS_OT_PORTAL, &v20);
      v12 = ObjectFromProviders;
      if ( ObjectFromProviders == -2147212283 )
      {
        v10 = -2147024809;
      }
      else if ( ObjectFromProviders >= 0 && v20 )
      {
        v13 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v20->lpVtbl->QueryInterface)(
                v20,
                &IID_IVdsIscsiPortal,
                &v19);
        v10 = v13;
        if ( v13 >= 0 && v19 )
        {
          v14 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v19 + 24LL))(v19, v28);
          v10 = v14;
          if ( v14 >= 0 )
          {
            LODWORD(v21) = 1;
            *((_QWORD *)&v21 + 1) = a3;
            v15 = VdsIscsiIpAddressToIpsecId(v29, v22, (char *)v22 + 4, &v22[1]);
            v10 = v15;
            if ( v15 >= 0 )
            {
              if ( a4 )
              {
                LODWORD(v23) = a4->ulKeySize;
                *((_QWORD *)&v23 + 1) = a4->pKey;
              }
              LOBYTE(v16) = 1;
              v17 = ((__int64 (__fastcall *)(LPVOID, _QWORD, __int128 *, __int64))ProcAddress)(
                      pv,
                      *((unsigned int *)this + 160),
                      &v21,
                      v16);
              if ( v17 && ((v17 & 0xFFF0000) == 0 || (v17 & 0xC0000000) == 0xC0000000) )
              {
                VdsTraceW(0, L"CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: SetIScsiIKEInfoW failed: %X", v17);
                v10 = -2147211002;
              }
              else
              {
                v10 = 0;
              }
            }
            else
            {
              VdsTraceW(
                0,
                L"CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: VdsIscsiIpAddressToIpsecId: %X",
                (unsigned int)v15);
            }
          }
          else
          {
            VdsTraceW(
              0,
              L"CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: spPortal->GetProperties: %X",
              (unsigned int)v14);
          }
        }
        else
        {
          VdsTraceW(
            0,
            L"CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: spPortalUnk->QueryInterface IID_IVdsIscsiPortal: %X",
            (unsigned int)v13);
          if ( v10 >= 0 )
            v10 = -2147467259;
        }
      }
      else
      {
        VdsTraceW(
          0,
          L"CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: Could not retrieve target portal object from provider: %X",
          (unsigned int)ObjectFromProviders);
        if ( v12 >= 0 )
          v12 = -2147467259;
        v10 = v12;
      }
    }
    else
    {
      VdsTraceW(
        0,
        L"CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: m_pParentAdapter->GetProperties: %X",
        (unsigned int)v9);
    }
  }
  else
  {
    VdsTraceW(
      0,
      L"CVdsIscsiInitiatorPortalInternal::SetIpsecSecurity: Could not access necessary function in iSCSI library.");
    v10 = -2147212288;
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v22[1] )
  {
    CoTaskMemFree(v22[1]);
    v22[1] = 0;
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v25);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v20);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14003fea0  push    rbp
0x14003fea2  push    rbx
0x14003fea3  push    rsi
0x14003fea4  push    rdi
0x14003fea5  push    r12
0x14003fea7  push    r14
0x14003fea9  push    r15
0x14003feab  lea     rbp, [rsp-200h]
0x14003feb3  sub     rsp, 300h
0x14003feba  mov     rax, cs:__security_cookie
0x14003fec1  xor     rax, rsp
0x14003fec4  mov     [rbp+230h+var_40], rax
0x14003fecb  mov     rsi, r9
0x14003fece  mov     r12, r8
0x14003fed1  mov     rdi, rdx
0x14003fed4  mov     r15, rcx
0x14003fed7  xorps   xmm0, xmm0
0x14003feda  xor     eax, eax
0x14003fedc  movups  [rbp+230h+var_2A0], xmm0
0x14003fee0  mov     [rbp+230h+pv], rax
0x14003fee4  mov     [rsp+330h+var_2F8], rax
0x14003fee9  mov     [rsp+330h+var_300], rax
0x14003feee  mov     ebx, 23Ch
0x14003fef3  mov     r8d, ebx; Size
0x14003fef6  xor     edx, edx; Val
0x14003fef8  lea     rcx, [rbp+230h+var_280]; void *
0x14003fefc  call    memset_0
0x14003ff01  xorps   xmm0, xmm0
0x14003ff04  movups  [rsp+330h+var_2F0], xmm0
0x14003ff09  movups  xmmword ptr [rsp+330h+var_2E0], xmm0
0x14003ff0e  movups  [rsp+330h+var_2D0], xmm0
0x14003ff13  lea     r8, aCvdsiscsiiniti_69; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x14003ff1a  mov     edx, 5Eh ; '^'
0x14003ff1f  lea     rcx, [rbp+230h+var_2B0]
0x14003ff23  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003ff29  nop
0x14003ff2a  xorps   xmm0, xmm0
0x14003ff2d  xor     eax, eax
0x14003ff2f  movups  [rbp+230h+var_2A0], xmm0
0x14003ff33  mov     [rbp+230h+pv], rax
0x14003ff37  mov     r8d, ebx; Size
0x14003ff3a  xor     edx, edx; Val
0x14003ff3c  lea     rcx, [rbp+230h+var_280]; void *
0x14003ff40  call    memset_0
0x14003ff45  xorps   xmm0, xmm0
0x14003ff48  movups  [rsp+330h+var_2F0], xmm0
0x14003ff4d  movups  xmmword ptr [rsp+330h+var_2E0], xmm0
0x14003ff52  movups  [rsp+330h+var_2D0], xmm0
0x14003ff57  mov     rcx, cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x14003ff5e  test    rcx, rcx
0x14003ff61  jz      loc_140040121
0x14003ff67  lea     rdx, aSetiscsiikeinf; "SetIScsiIKEInfoW"
0x14003ff6e  call    cs:__imp_GetProcAddress
0x14003ff74  mov     r14, rax
0x14003ff77  test    rax, rax
0x14003ff7a  jz      loc_140040121
0x14003ff80  mov     rcx, [r15+40h]
0x14003ff84  mov     rdx, [rcx]
0x14003ff87  mov     rax, [rdx+18h]
0x14003ff8b  lea     rdx, [rbp+230h+var_2A0]
0x14003ff8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ff94  mov     ebx, eax
0x14003ff96  test    eax, eax
0x14003ff98  jns     short loc_14003FFB1
0x14003ff9a  lea     rdx, aCvdsiscsiiniti_21; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x14003ffa1  mov     r8d, eax
0x14003ffa4  xor     ecx, ecx
0x14003ffa6  call    cs:__imp_VdsTraceW
0x14003ffac  jmp     loc_140040135
0x14003ffb1  movups  xmm0, xmmword ptr [rdi]
0x14003ffb4  movdqu  xmmword ptr [rsp+330h+var_2C0.Data1], xmm0
0x14003ffba  lea     r8, [rsp+330h+var_2F8]; struct IUnknown **
0x14003ffbf  mov     edx, 24h ; '$'; enum _VDS_OBJECT_TYPE
0x14003ffc4  lea     rcx, [rsp+330h+var_2C0]; struct _GUID
0x14003ffc9  call    ?GetObjectFromProviders@CVdsService@@SAJU_GUID@@W4_VDS_OBJECT_TYPE@@PEAPEAUIUnknown@@@Z; CVdsService::GetObjectFromProviders(_GUID,_VDS_OBJECT_TYPE,IUnknown * *)
0x14003ffce  mov     edi, eax
0x14003ffd0  cmp     eax, 80042405h
0x14003ffd5  jnz     short loc_14003FFE1
0x14003ffd7  mov     ebx, 80070057h
0x14003ffdc  jmp     loc_140040135
0x14003ffe1  test    edi, edi
0x14003ffe3  js      loc_140040101
0x14003ffe9  mov     rcx, [rsp+330h+var_2F8]
0x14003ffee  test    rcx, rcx
0x14003fff1  jz      loc_140040101
0x14003fff7  mov     rax, [rcx]
0x14003fffa  lea     r8, [rsp+330h+var_300]
0x14003ffff  lea     rdx, IID_IVdsIscsiPortal
0x140040006  mov     rax, [rax]
0x140040009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004000e  mov     ebx, eax
0x140040010  test    eax, eax
0x140040012  js      loc_1400400E4
0x140040018  mov     rcx, [rsp+330h+var_300]
0x14004001d  test    rcx, rcx
0x140040020  jz      loc_1400400E4
0x140040026  mov     rax, [rcx]
0x140040029  lea     rdx, [rbp+230h+var_280]
0x14004002d  mov     rax, [rax+18h]
0x140040031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040036  mov     ebx, eax
0x140040038  test    eax, eax
0x14004003a  jns     short loc_140040048
0x14004003c  lea     rdx, aCvdsiscsiiniti_139; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x140040043  jmp     loc_14003FFA1
0x140040048  mov     dword ptr [rsp+330h+var_2F0], 1
0x140040050  mov     qword ptr [rsp+330h+var_2F0+8], r12
0x140040055  lea     r9, [rsp+330h+var_2E0+8]
0x14004005a  lea     r8, [rsp+330h+var_2E0+4]
0x14004005f  lea     rdx, [rsp+330h+var_2E0]
0x140040064  lea     rcx, [rbp+230h+var_270]
0x140040068  call    cs:__imp_VdsIscsiIpAddressToIpsecId
0x14004006e  mov     ebx, eax
0x140040070  test    eax, eax
0x140040072  jns     short loc_140040080
0x140040074  lea     rdx, aCvdsiscsiiniti_80; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x14004007b  jmp     loc_14003FFA1
0x140040080  test    rsi, rsi
0x140040083  jz      short loc_140040094
0x140040085  mov     eax, [rsi+8]
0x140040088  mov     dword ptr [rsp+330h+var_2D0], eax
0x14004008c  mov     rax, [rsi]
0x14004008f  mov     qword ptr [rsp+330h+var_2D0+8], rax
0x140040094  mov     r9b, 1
0x140040097  lea     r8, [rsp+330h+var_2F0]
0x14004009c  mov     edx, [r15+280h]
0x1400400a3  mov     rcx, [rbp+230h+pv]
0x1400400a7  mov     rax, r14
0x1400400aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400400af  test    eax, eax
0x1400400b1  jz      short loc_1400400E0
0x1400400b3  test    eax, 0FFF0000h
0x1400400b8  jz      short loc_1400400C7
0x1400400ba  mov     ecx, eax
0x1400400bc  mov     edx, 0C0000000h
0x1400400c1  and     ecx, edx
0x1400400c3  cmp     ecx, edx
0x1400400c5  jnz     short loc_1400400E0
0x1400400c7  mov     r8d, eax
0x1400400ca  lea     rdx, aCvdsiscsiiniti_102; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x1400400d1  xor     ecx, ecx
0x1400400d3  call    cs:__imp_VdsTraceW
0x1400400d9  mov     ebx, 80042906h
0x1400400de  jmp     short loc_140040135
0x1400400e0  xor     ebx, ebx
0x1400400e2  jmp     short loc_140040135
0x1400400e4  mov     r8d, ebx
0x1400400e7  lea     rdx, aCvdsiscsiiniti_46; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x1400400ee  xor     ecx, ecx
0x1400400f0  call    cs:__imp_VdsTraceW
0x1400400f6  test    ebx, ebx
0x1400400f8  js      short loc_140040135
0x1400400fa  mov     ebx, 80004005h
0x1400400ff  jmp     short loc_140040135
0x140040101  mov     r8d, edi
0x140040104  lea     rdx, aCvdsiscsiiniti_7; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x14004010b  xor     ecx, ecx
0x14004010d  call    cs:__imp_VdsTraceW
0x140040113  mov     ebx, 80004005h
0x140040118  test    edi, edi
0x14004011a  cmovns  edi, ebx
0x14004011d  mov     ebx, edi
0x14004011f  jmp     short loc_140040135
0x140040121  lea     rdx, aCvdsiscsiiniti_121; "CVdsIscsiInitiatorPortalInternal::SetIp"...
0x140040128  xor     ecx, ecx
0x14004012a  call    cs:__imp_VdsTraceW
0x140040130  mov     ebx, 80042400h
0x140040135  mov     rcx, [rbp+230h+pv]; pv
0x140040139  test    rcx, rcx
0x14004013c  jz      short loc_14004014C
0x14004013e  call    cs:__imp_CoTaskMemFree
0x140040144  mov     [rbp+230h+pv], 0
0x14004014c  mov     rcx, [rsp+330h+var_2E0+8]; pv
0x140040151  test    rcx, rcx
0x140040154  jz      short loc_140040165
0x140040156  call    cs:__imp_CoTaskMemFree
0x14004015c  mov     [rsp+330h+var_2E0+8], 0
0x140040165  lea     rcx, [rbp+230h+var_2B0]
0x140040169  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14004016f  nop
0x140040170  lea     rcx, [rsp+330h+var_300]
0x140040175  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004017a  nop
0x14004017b  lea     rcx, [rsp+330h+var_2F8]
0x140040180  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140040185  mov     eax, ebx
0x140040187  mov     rcx, [rbp+230h+var_40]
0x14004018e  xor     rcx, rsp; StackCookie
0x140040191  call    __security_check_cookie
0x140040196  add     rsp, 300h
0x14004019d  pop     r15
0x14004019f  pop     r14
0x1400401a1  pop     r12
0x1400401a3  pop     rdi
0x1400401a4  pop     rsi
0x1400401a5  pop     rbx
0x1400401a6  pop     rbp
0x1400401a7  retn
```
