# CUdpEndpoint::Initialize(CMulticastHandler *,CRegUdpEndpoint *,tagWDS_ENDPOINT *,tagWDS_INTERFACE_INFO *)

- ea: `0x180018cdc`
- end: `0x1800191c2`
- name: `?Initialize@CUdpEndpoint@@QEAAKPEAVCMulticastHandler@@PEAVCRegUdpEndpoint@@PEAUtagWDS_ENDPOINT@@PEAUtagWDS_INTERFACE_INFO@@@Z`
- size: `1254`
- prototype: `unsigned int(CUdpEndpoint *__hidden this, struct CMulticastHandler *, struct CRegUdpEndpoint *, struct tagWDS_ENDPOINT *, struct tagWDS_INTERFACE_INFO *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002c24`

## callees

- `0x180003944`
- `0x18000d9dc`
- `0x1800162d4`
- `0x18001784c`
- `0x180018b08`
- `0x180018cdc`
- `0x18001b0cc`
- `0x18001c112`
- `0x18001c11e`
- `0x18001c150`
- `0x18001d010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001906b`
- `KERNEL32!LeaveCriticalSection` at `0x18001906b`
- `KERNEL32!EnterCriticalSection` at `0x180018d29`
- `KERNEL32!EnterCriticalSection` at `0x180018d29`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001918c`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001918c`
- `WdsServerCommonLib!?IpAddressToString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAPEAG@Z` at `0x180018d97`
- `WdsServerCommonLib!?IpAddressToString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAPEAG@Z` at `0x180018d97`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180019050`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800190e4`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180019126`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180019050`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800190e4`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180019126`
- `WdsServerCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180018df8`
- `WdsServerCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180018df8`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180019177`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180019177`

## string_xrefs

- `0x180019038`: `[%s][UDP][Ep=%s][0x%p] Created`

## pseudocode

```c
__int64 __fastcall CUdpEndpoint::Initialize(
        CUdpEndpoint *this,
        struct CMulticastHandler *a2,
        struct CRegUdpEndpoint *a3,
        struct tagWDS_ENDPOINT *a4,
        struct tagWDS_INTERFACE_INFO *Src)
{
  __int64 Lease; // rbx
  __int64 v10; // rdx
  int v11; // esi
  const wchar_t *v12; // rdi
  int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // rcx
  struct IMulticastCallback *v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rcx
  unsigned int v23; // eax
  size_t v24; // r8
  size_t v25; // r8
  __int128 v26; // xmm0
  __int64 v27; // rcx
  unsigned int v28; // eax
  __int64 v29; // rdx
  bool v30; // zf
  int v31; // r8d
  __int64 v32; // rdx
  __int64 v33; // rcx
  const wchar_t *v34; // r9
  __int64 *v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rcx
  const wchar_t *v38; // r9
  __int64 v40; // [rsp+28h] [rbp-59h]
  void *v41; // [rsp+50h] [rbp-31h] BYREF
  __int128 v42; // [rsp+58h] [rbp-29h] BYREF
  unsigned int v43; // [rsp+68h] [rbp-19h]
  __int128 v44; // [rsp+70h] [rbp-11h] BYREF
  unsigned int v45; // [rsp+80h] [rbp-1h]

  v42 = 0u;
  v41 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *((_QWORD *)this + 9) = a3;
  *((_QWORD *)this + 10) = a2;
  memmove_0((char *)this + 988, a4, 0x41Cu);
  memmove_0((char *)this + 940, Src, 0x30u);
  v43 = *((_DWORD *)this + 239);
  memcpy_0(&v42, (char *)this + 940, v43);
  v45 = v43;
  v44 = v42;
  Lease = (unsigned int)CNetworkAddress::IpAddressToString(&v44, &v41);
  v11 = 0;
  v12 = L"<Unknown>";
  if ( (unsigned int)ElValidateWin32(Lease, v10, "base\\eco\\wds\\wdssrv\\server\\src\\udpendpoint.cpp", 113) )
    goto LABEL_32;
  v13 = StringCchPrintfW((unsigned __int16 *)this + 1020, 0x80u, L"%s:%u", v41, *((unsigned __int16 *)this + 500));
  if ( v13 < 0 )
  {
    v14 = WIN32_FROM_HRESULT(v13);
    LODWORD(Lease) = ElValidateWin32(v14, v15, "base\\eco\\wds\\wdssrv\\server\\src\\udpendpoint.cpp", 124);
    goto LABEL_32;
  }
  v16 = *((_QWORD *)this + 9);
  memmove_0((char *)this + 720, (const void *)(v16 + 1840), 0xD8u);
  if ( *(_DWORD *)(v16 + 2068) && *((_DWORD *)this + 239) == 16 )
    *((_DWORD *)this + 194) = 1;
  v11 = 0;
  if ( *((_DWORD *)this + 194) )
  {
    if ( *((_DWORD *)this + 204) )
      goto LABEL_20;
    v17 = *((_QWORD *)this + 10);
    v18 = (CUdpEndpoint *)((char *)this + 16);
    if ( *((_DWORD *)this + 239) == 16 )
    {
      Lease = CStaticMulticastLeaseHandler::GetLease(
                (LPCRITICAL_SECTION)(v17 + 128),
                (CUdpEndpoint *)((char *)this + 800));
      v21 = 269;
      v22 = Lease;
    }
    else
    {
      if ( *((_DWORD *)this + 239) != 4 )
      {
        LODWORD(Lease) = 13;
        goto LABEL_18;
      }
      if ( *(_DWORD *)v17 )
        v23 = CMadcapHandler::GetLease(
                (LPCRITICAL_SECTION)(v17 + 248),
                v18,
                (CUdpEndpoint *)((char *)this + 940),
                (CUdpEndpoint *)((char *)this + 800));
      else
        v23 = CStaticMulticastLeaseHandler::GetLease(
                (LPCRITICAL_SECTION)(v17 + 8),
                (CUdpEndpoint *)((char *)this + 800));
      LODWORD(Lease) = v23;
      v21 = 280;
      v22 = v23;
    }
    ElValidateWin32_9(v22, v19, v20, v21);
LABEL_18:
    if ( (unsigned int)ElValidateWin32(
                         (unsigned int)Lease,
                         v18,
                         "base\\eco\\wds\\wdssrv\\server\\src\\udpendpoint.cpp",
                         144) )
      goto LABEL_32;
    *((_DWORD *)this + 574) = 1;
LABEL_20:
    v24 = *((unsigned int *)this + 239);
    *((_DWORD *)this + 199) = v24;
    memmove_0((char *)this + 780, (char *)this + 940, v24);
    v25 = *((unsigned int *)this + 204);
    *((_DWORD *)this + 260) = v25;
    memmove_0((char *)this + 1024, (char *)this + 800, v25);
    if ( *((_DWORD *)this + 574) )
    {
      v26 = *((_OWORD *)this + 50);
      v27 = *((_QWORD *)this + 9);
      v45 = *((_DWORD *)this + 204);
      v44 = v26;
      v28 = (*(__int64 (__fastcall **)(__int64, char *, __int128 *))(*(_QWORD *)v27 + 64LL))(
              v27,
              (char *)this + 940,
              &v44);
      LODWORD(Lease) = v28;
      if ( v28 == 50
        || (unsigned int)ElValidateWin32(v28, v29, "base\\eco\\wds\\wdssrv\\server\\src\\udpendpoint.cpp", 180) )
      {
        v11 = 1;
        goto LABEL_32;
      }
    }
    goto LABEL_25;
  }
  *((_DWORD *)this + 260) = 0;
LABEL_25:
  v30 = *((_DWORD *)this + 255) == 4;
  *((_QWORD *)this + 93) = qword_180039238;
  *((_DWORD *)this + 193) = 1;
  *((_DWORD *)this + 184) = 0;
  v31 = 2;
  if ( !v30 )
    v31 = 23;
  Lease = (unsigned int)CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::Initialize(
                          (__int64)this + 96,
                          (__int64)this,
                          v31,
                          (char *)this + 720,
                          (__int64)this + 988);
  if ( !(unsigned int)ElValidateWin32(Lease, v32, "base\\eco\\wds\\wdssrv\\server\\src\\udpendpoint.cpp", 211) )
  {
    v33 = *(_QWORD *)(*((_QWORD *)this + 9) + 64LL);
    if ( v33 )
      v34 = *(const wchar_t **)(v33 + 16);
    else
      v34 = L"<Unknown>";
    CTrace::Trace(
      (CTrace *)qword_180039310,
      0x10000u,
      L"[%s][UDP][Ep=%s][0x%p] Created",
      v34,
      (char *)this + 2040,
      this);
    *((_DWORD *)this + 234) = 1;
  }
LABEL_32:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v35 = (__int64 *)*((_QWORD *)this + 9);
  v36 = *v35;
  if ( (_DWORD)Lease )
  {
    (*(void (__fastcall **)(__int64 *, struct tagWDS_INTERFACE_INFO *, _QWORD))(v36 + 56))(
      v35,
      Src,
      (unsigned int)Lease);
    v37 = *(_QWORD *)(*((_QWORD *)this + 9) + 64LL);
    if ( v11 )
    {
      if ( v37 )
        v12 = *(const wchar_t **)(v37 + 16);
      LODWORD(v40) = Lease;
      CTrace::Trace(
        (CTrace *)qword_180039310,
        0x10000u,
        L"[%s][UDP][Ep=%s] Creation canceled by provider (rc=%u)",
        v12,
        (char *)this + 2040,
        v40);
    }
    else
    {
      if ( v37 )
        v38 = *(const wchar_t **)(v37 + 16);
      else
        v38 = L"<Unknown>";
      LODWORD(v40) = Lease;
      CTrace::Trace(
        (CTrace *)qword_180039310,
        0x80000u,
        L"[%s][UDP][Ep=%s] Creation Failed (rc=%u)",
        v38,
        (char *)this + 2040,
        v40);
      CEventLog::Log((CEventLog *)qword_180039300, 0xC1010304, 3);
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64 *, char *, struct tagWDS_INTERFACE_INFO *))(v36 + 48))(v35, (char *)this + 988, Src);
  }
  if ( v41 )
    WdsPrivateHpFree(v41);
  return (unsigned int)Lease;
}

```

## disassembly

```asm
0x180018cdc  mov     [rsp-8+arg_8], rbx
0x180018ce1  push    rbp
0x180018ce2  push    rsi
0x180018ce3  push    rdi
0x180018ce4  push    r12
0x180018ce6  push    r13
0x180018ce8  push    r14
0x180018cea  push    r15
0x180018cec  lea     rbp, [rsp-1Fh]
0x180018cf1  sub     rsp, 0A0h
0x180018cf8  mov     rax, cs:__security_cookie
0x180018cff  xor     rax, rsp
0x180018d02  mov     [rbp+4Fh+var_40], rax
0x180018d06  mov     r12, [rbp+4Fh+Src]
0x180018d0a  mov     r14, rcx
0x180018d0d  and     qword ptr [rbp+4Fh+var_78], 0
0x180018d12  add     rcx, 18h; lpCriticalSection
0x180018d16  and     qword ptr [rbp+4Fh+var_78+8], 0
0x180018d1b  mov     rsi, r9
0x180018d1e  and     [rbp+4Fh+var_80], 0
0x180018d23  mov     rbx, r8
0x180018d26  mov     rdi, rdx
0x180018d29  call    cs:__imp_EnterCriticalSection
0x180018d30  nop     dword ptr [rax+rax+00h]
0x180018d35  lea     rcx, [r14+3DCh]; void *
0x180018d3c  mov     [r14+48h], rbx
0x180018d40  mov     r8d, 41Ch; Size
0x180018d46  mov     [r14+50h], rdi
0x180018d4a  mov     rdx, rsi; Src
0x180018d4d  call    memmove_0
0x180018d52  lea     r15, [r14+3ACh]
0x180018d59  mov     r8d, 30h ; '0'; Size
0x180018d5f  mov     rcx, r15; void *
0x180018d62  mov     rdx, r12; Src
0x180018d65  call    memmove_0
0x180018d6a  mov     r8d, [r14+3BCh]; Size
0x180018d71  lea     rcx, [rbp+4Fh+var_78]; void *
0x180018d75  mov     rdx, r15; Src
0x180018d78  mov     [rbp+4Fh+var_68], r8d
0x180018d7c  call    memcpy_0
0x180018d81  movups  xmm0, [rbp+4Fh+var_78]
0x180018d85  mov     eax, [rbp+4Fh+var_68]
0x180018d88  lea     rdx, [rbp+4Fh+var_80]
0x180018d8c  lea     rcx, [rbp+4Fh+var_60]
0x180018d90  mov     [rbp+4Fh+var_50], eax
0x180018d93  movaps  [rbp+4Fh+var_60], xmm0
0x180018d97  call    cs:__imp_?IpAddressToString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAPEAG@Z; CNetworkAddress::IpAddressToString(tagWDS_IP_ADDRESS6,ushort * *)
0x180018d9e  nop     dword ptr [rax+rax+00h]
0x180018da3  mov     r9d, 71h ; 'q'
0x180018da9  lea     r8, aBaseEcoWdsWdss_5; "base\\eco\\wds\\wdssrv\\server\\src\\ud"...
0x180018db0  mov     ecx, eax
0x180018db2  mov     ebx, eax
0x180018db4  call    ElValidateWin32
0x180018db9  xor     esi, esi
0x180018dbb  lea     rdi, aUnknown_0; "<Unknown>"
0x180018dc2  test    eax, eax
0x180018dc4  jnz     loc_180019067
0x180018dca  movzx   eax, word ptr [r14+3E8h]
0x180018dd2  lea     rcx, [r14+7F8h]; unsigned __int16 *
0x180018dd9  mov     r9, [rbp+4Fh+var_80]
0x180018ddd  lea     r8, aSU; "%s:%u"
0x180018de4  mov     edx, 80h; unsigned __int64
0x180018de9  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180018ded  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018df2  test    eax, eax
0x180018df4  jns     short loc_180018E1D
0x180018df6  mov     ecx, eax
0x180018df8  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180018dff  nop     dword ptr [rax+rax+00h]
0x180018e04  mov     ecx, eax
0x180018e06  lea     r9d, [rsi+7Ch]
0x180018e0a  lea     r8, aBaseEcoWdsWdss_5; "base\\eco\\wds\\wdssrv\\server\\src\\ud"...
0x180018e11  call    ElValidateWin32
0x180018e16  mov     ebx, eax
0x180018e18  jmp     loc_180019067
0x180018e1d  mov     rbx, [r14+48h]
0x180018e21  lea     rsi, [r14+2D0h]
0x180018e28  mov     r8d, 0D8h; Size
0x180018e2e  mov     rcx, rsi; void *
0x180018e31  lea     rdx, [rbx+730h]; Src
0x180018e38  call    memmove_0
0x180018e3d  cmp     dword ptr [rbx+814h], 0
0x180018e44  jz      short loc_180018E57
0x180018e46  cmp     dword ptr [r14+3BCh], 10h
0x180018e4e  jnz     short loc_180018E57
0x180018e50  mov     dword ptr [rsi+38h], 1
0x180018e57  xor     esi, esi
0x180018e59  cmp     [r14+308h], esi
0x180018e60  jz      loc_180018FA1
0x180018e66  cmp     [r14+330h], esi
0x180018e6d  jnz     loc_180018F06
0x180018e73  cmp     dword ptr [r15+10h], 10h
0x180018e78  lea     r9, [r14+320h]; struct tagWDS_IP_ADDRESS6 *
0x180018e7f  mov     rcx, [r14+50h]
0x180018e83  lea     rdx, [r14+10h]; struct IMulticastCallback *
0x180018e87  jnz     short loc_180018EA1
0x180018e89  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x180018e8d  mov     rdx, r9; struct tagWDS_IP_ADDRESS6 *
0x180018e90  call    ?GetLease@CStaticMulticastLeaseHandler@@QEAAKPEAUtagWDS_IP_ADDRESS6@@@Z; CStaticMulticastLeaseHandler::GetLease(tagWDS_IP_ADDRESS6 *)
0x180018e95  mov     ebx, eax
0x180018e97  mov     r9d, 10Dh
0x180018e9d  mov     ecx, eax
0x180018e9f  jmp     short loc_180018ED3
0x180018ea1  cmp     dword ptr [r15+10h], 4
0x180018ea6  jnz     short loc_180018EDA
0x180018ea8  cmp     [rcx], esi
0x180018eaa  jnz     short loc_180018EBA
0x180018eac  add     rcx, 8; lpCriticalSection
0x180018eb0  mov     rdx, r9; struct tagWDS_IP_ADDRESS6 *
0x180018eb3  call    ?GetLease@CStaticMulticastLeaseHandler@@QEAAKPEAUtagWDS_IP_ADDRESS6@@@Z; CStaticMulticastLeaseHandler::GetLease(tagWDS_IP_ADDRESS6 *)
0x180018eb8  jmp     short loc_180018EC9
0x180018eba  add     rcx, 0F8h; lpCriticalSection
0x180018ec1  mov     r8, r15; struct tagWDS_INTERFACE_INFO *
0x180018ec4  call    ?GetLease@CMadcapHandler@@QEAAKPEAVIMulticastCallback@@PEAUtagWDS_INTERFACE_INFO@@PEAUtagWDS_IP_ADDRESS6@@@Z; CMadcapHandler::GetLease(IMulticastCallback *,tagWDS_INTERFACE_INFO *,tagWDS_IP_ADDRESS6 *)
0x180018ec9  mov     ebx, eax
0x180018ecb  mov     r9d, 118h
0x180018ed1  mov     ecx, eax
0x180018ed3  call    ElValidateWin32_9
0x180018ed8  jmp     short loc_180018EDF
0x180018eda  mov     ebx, 0Dh
0x180018edf  mov     r9d, 90h
0x180018ee5  lea     r8, aBaseEcoWdsWdss_5; "base\\eco\\wds\\wdssrv\\server\\src\\ud"...
0x180018eec  mov     ecx, ebx
0x180018eee  call    ElValidateWin32
0x180018ef3  test    eax, eax
0x180018ef5  jnz     loc_180019067
0x180018efb  mov     dword ptr [r14+8F8h], 1
0x180018f06  mov     r8d, [r14+3BCh]; Size
0x180018f0d  lea     rcx, [r14+30Ch]; void *
0x180018f14  mov     rdx, r15; Src
0x180018f17  mov     [r14+31Ch], r8d
0x180018f1e  call    memmove_0
0x180018f23  mov     r8d, [r14+330h]; Size
0x180018f2a  lea     rbx, [r14+320h]
0x180018f31  mov     rdx, rbx; Src
0x180018f34  mov     [r14+410h], r8d
0x180018f3b  lea     rcx, [r14+400h]; void *
0x180018f42  call    memmove_0
0x180018f47  cmp     [r14+8F8h], esi
0x180018f4e  jz      short loc_180018FA8
0x180018f50  mov     eax, [rbx+10h]
0x180018f53  lea     rdx, [r14+3ACh]
0x180018f5a  movups  xmm0, xmmword ptr [rbx]
0x180018f5d  mov     rcx, [r14+48h]
0x180018f61  lea     r8, [rbp+4Fh+var_60]
0x180018f65  mov     [rbp+4Fh+var_50], eax
0x180018f68  movups  [rbp+4Fh+var_60], xmm0
0x180018f6c  mov     rax, [rcx]
0x180018f6f  mov     rax, [rax+40h]
0x180018f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f78  mov     ebx, eax
0x180018f7a  cmp     eax, 32h ; '2'
0x180018f7d  jz      short loc_180018F97
0x180018f7f  mov     r9d, 0B4h
0x180018f85  lea     r8, aBaseEcoWdsWdss_5; "base\\eco\\wds\\wdssrv\\server\\src\\ud"...
0x180018f8c  mov     ecx, eax
0x180018f8e  call    ElValidateWin32
0x180018f93  test    eax, eax
0x180018f95  jz      short loc_180018FA8
0x180018f97  mov     esi, 1
0x180018f9c  jmp     loc_180019067
0x180018fa1  mov     [r14+410h], esi
0x180018fa8  cmp     dword ptr [r14+3FCh], 4
0x180018fb0  lea     rax, qword_180039238
0x180018fb7  mov     ecx, 17h
0x180018fbc  mov     [r14+2E8h], rax
0x180018fc3  lea     rax, [r14+3DCh]
0x180018fca  mov     dword ptr [r14+304h], 1
0x180018fd5  lea     r9, [r14+2D0h]
0x180018fdc  mov     [r14+2E0h], esi
0x180018fe3  mov     rdx, r14
0x180018fe6  mov     [rsp+0D0h+var_B0], rax
0x180018feb  lea     r8d, [rcx-15h]
0x180018fef  cmovnz  r8d, ecx
0x180018ff3  lea     rcx, [r14+60h]
0x180018ff7  call    ?Initialize@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@QEAAKPEAVCUdpEndpoint@@HPEAUSocketSetup@@PEAUtagWDS_ENDPOINT@@@Z; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::Initialize(CUdpEndpoint *,int,SocketSetup *,tagWDS_ENDPOINT *)
0x180018ffc  mov     r9d, 0D3h
0x180019002  lea     r8, aBaseEcoWdsWdss_5; "base\\eco\\wds\\wdssrv\\server\\src\\ud"...
0x180019009  mov     ecx, eax
0x18001900b  mov     ebx, eax
0x18001900d  call    ElValidateWin32
0x180019012  test    eax, eax
0x180019014  jnz     short loc_180019067
0x180019016  mov     rax, [r14+48h]
0x18001901a  mov     rcx, [rax+40h]
0x18001901e  test    rcx, rcx
0x180019021  jz      short loc_180019029
0x180019023  mov     r9, [rcx+10h]
0x180019027  jmp     short loc_18001902C
0x180019029  mov     r9, rdi
0x18001902c  lea     rax, [r14+7F8h]
0x180019033  mov     [rsp+0D0h+var_A8], r14
0x180019038  lea     r8, aSUdpEpS0xPCrea; "[%s][UDP][Ep=%s][0x%p] Created"
0x18001903f  mov     [rsp+0D0h+var_B0], rax
0x180019044  mov     edx, 10000h
0x180019049  lea     rcx, qword_180039310
0x180019050  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180019057  nop     dword ptr [rax+rax+00h]
0x18001905c  mov     dword ptr [r14+3A8h], 1
0x180019067  lea     rcx, [r14+18h]; lpCriticalSection
0x18001906b  call    cs:__imp_LeaveCriticalSection
0x180019072  nop     dword ptr [rax+rax+00h]
0x180019077  mov     rcx, [r14+48h]
0x18001907b  mov     rax, [rcx]
0x18001907e  test    ebx, ebx
0x180019080  jnz     short loc_18001909A
0x180019082  mov     rax, [rax+30h]
0x180019086  lea     rdx, [r14+3DCh]
0x18001908d  mov     r8, r12
0x180019090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019095  jmp     loc_180019183
0x18001909a  mov     rax, [rax+38h]
0x18001909e  mov     r8d, ebx
0x1800190a1  mov     rdx, r12
0x1800190a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190a9  mov     rax, [r14+48h]
0x1800190ad  mov     rcx, [rax+40h]
0x1800190b1  test    esi, esi
0x1800190b3  jz      short loc_1800190F5
0x1800190b5  test    rcx, rcx
0x1800190b8  jz      short loc_1800190BE
0x1800190ba  mov     rdi, [rcx+10h]
0x1800190be  lea     rax, [r14+7F8h]
0x1800190c5  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x1800190c9  mov     r9, rdi
0x1800190cc  mov     [rsp+0D0h+var_B0], rax
0x1800190d1  lea     r8, aSUdpEpSCreatio; "[%s][UDP][Ep=%s] Creation canceled by p"...
0x1800190d8  mov     edx, 10000h
0x1800190dd  lea     rcx, qword_180039310
0x1800190e4  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800190eb  nop     dword ptr [rax+rax+00h]
0x1800190f0  jmp     loc_180019183
0x1800190f5  test    rcx, rcx
0x1800190f8  jz      short loc_180019100
0x1800190fa  mov     r9, [rcx+10h]
0x1800190fe  jmp     short loc_180019103
0x180019100  mov     r9, rdi
0x180019103  lea     rsi, [r14+7F8h]
0x18001910a  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x18001910e  lea     r8, aSUdpEpSCreatio_0; "[%s][UDP][Ep=%s] Creation Failed (rc=%u"...
0x180019115  mov     [rsp+0D0h+var_B0], rsi
0x18001911a  mov     edx, 80000h
0x18001911f  lea     rcx, qword_180039310
0x180019126  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18001912d  nop     dword ptr [rax+rax+00h]
0x180019132  mov     rax, [r14+48h]
0x180019136  mov     rcx, [rax+40h]
0x18001913a  test    rcx, rcx
0x18001913d  jz      short loc_180019143
0x18001913f  mov     rdi, [rcx+10h]
0x180019143  mov     [rsp+0D0h+var_90], ebx
0x180019147  lea     rcx, qword_180039300
0x18001914e  mov     [rsp+0D0h+var_98], 5
0x180019156  mov     r9d, 1
0x18001915c  mov     [rsp+0D0h+var_A0], rsi
0x180019161  mov     edx, 0C1010304h
0x180019166  mov     dword ptr [rsp+0D0h+var_A8], 1
0x18001916e  mov     [rsp+0D0h+var_B0], rdi
0x180019173  lea     r8d, [r9+2]
0x180019177  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18001917e  nop     dword ptr [rax+rax+00h]
0x180019183  mov     rcx, [rbp+4Fh+var_80]
0x180019187  test    rcx, rcx
0x18001918a  jz      short loc_180019198
0x18001918c  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180019193  nop     dword ptr [rax+rax+00h]
0x180019198  mov     eax, ebx
0x18001919a  mov     rcx, [rbp+4Fh+var_40]
0x18001919e  xor     rcx, rsp; StackCookie
0x1800191a1  call    __security_check_cookie
0x1800191a6  mov     rbx, [rsp+0D0h+arg_8]
0x1800191ae  add     rsp, 0A0h
0x1800191b5  pop     r15
0x1800191b7  pop     r14
0x1800191b9  pop     r13
0x1800191bb  pop     r12
0x1800191bd  pop     rdi
0x1800191be  pop     rsi
0x1800191bf  pop     rbp
0x1800191c0  retn
```
