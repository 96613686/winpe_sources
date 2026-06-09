# WFDSConMgr::CMaUsbHelper::StartIpSession(WFDSConMgr::IMaUsbListener *,sockaddr_in const &,WFDSConMgr::MaUsbTelemetryInfo const &,ushort &)

- ea: `0x18004ed3c`
- end: `0x18004f15a`
- name: `?StartIpSession@CMaUsbHelper@WFDSConMgr@@QEAAXPEAVIMaUsbListener@2@AEBUsockaddr_in@@AEBUMaUsbTelemetryInfo@2@AEAG@Z`
- size: `1054`
- prototype: `void __fastcall(WFDSConMgr::CMaUsbHelper *this, struct WFDSConMgr::IMaUsbListener *, const struct sockaddr_in *, const struct WFDSConMgr::MaUsbTelemetryInfo *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task`

## callers

- `0x180056050`

## callees

- `0x18000421c`
- `0x18000475c`
- `0x1800051f8`
- `0x1800059c0`
- `0x18000665c`
- `0x180006780`
- `0x180006eb0`
- `0x180009b5c`
- `0x18004c418`
- `0x18004c668`
- `0x18004e9cc`
- `0x18004ed3c`
- `0x18004f160`
- `0x18004f664`
- `0x18005c888`
- `0x18005d6c0`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ee34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004efb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f067`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ee34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004efb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f067`
- `WS2_32!__imp_ntohs` at `0x18004f037`
- `WS2_32!__imp_ntohs` at `0x18004f037`

## string_xrefs

- `0x18004f12f`: `Attempt to start MA-USB multiple times`
- `0x18004eef4`: `MA-USB OpenDriverHandle failed`
- `0x18004f00c`: `MA-USB OpenIpSession failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall WFDSConMgr::CMaUsbHelper::StartIpSession(
        WFDSConMgr::CMaUsbHelper *this,
        struct WFDSConMgr::IMaUsbListener *a2,
        const struct sockaddr_in *a3,
        const struct WFDSConMgr::MaUsbTelemetryInfo *a4,
        unsigned __int16 *a5)
{
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // r10
  __int64 v12; // r9
  int v13; // ebx
  __int64 v14; // rax
  volatile signed __int32 *v15; // rcx
  __m128i si128; // xmm1
  unsigned __int16 *v17; // rsi
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rdx
  void **v21; // rbx
  unsigned int v22; // r8d
  __int64 v23; // [rsp+40h] [rbp-40h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-38h] BYREF
  __m128i v25; // [rsp+50h] [rbp-30h] BYREF
  std::_Ref_count_base *v26[2]; // [rsp+60h] [rbp-20h] BYREF
  std::_Ref_count_base *v27[2]; // [rsp+70h] [rbp-10h] BYREF
  __int64 v28; // [rsp+B0h] [rbp+30h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 280);
    WPP_SF_qSD_guid_(*(_QWORD *)(v11 + 16), v9, *(_DWORD *)(v10 + 4), v12);
  }
  WFDSConMgr::CriticalSection::Lock((char *)this + 8, &lpCriticalSection);
  if ( *((_BYTE *)this + 368) )
    WFDSConMgr::CException::Throw(
      199,
      "WFDSConMgr::CMaUsbHelper::StartIpSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      136,
      L"Operation was canceled before starting",
      this);
  if ( *((_BYTE *)this + 369) || *((_BYTE *)this + 371) || *((_QWORD *)this + 33) )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CMaUsbHelper::StartIpSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      140,
      L"Attempt to start MA-USB multiple times",
      this);
  *((_QWORD *)this + 44) = a2;
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  v28 = 0;
  v13 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64 *))(**((_QWORD **)this + 6) + 16LL))(
          *((_QWORD *)this + 6),
          (char *)this + 280,
          &v28);
  v14 = *((_QWORD *)this + 7);
  if ( v14 )
    _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
  v27[0] = *((std::_Ref_count_base **)this + 6);
  v15 = (volatile signed __int32 *)*((_QWORD *)this + 7);
  v27[1] = (std::_Ref_count_base *)v15;
  *(_OWORD *)v26 = 0;
  if ( v15 )
    _InterlockedIncrement(v15 + 2);
  si128 = *(__m128i *)v27;
  *(_OWORD *)v26 = *(_OWORD *)v27;
  if ( v15 )
  {
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v15);
    si128 = _mm_load_si128((const __m128i *)v26);
  }
  lpCriticalSection = (LPCRITICAL_SECTION)v26;
  *(_OWORD *)v27 = 0;
  v25 = si128;
  *(_OWORD *)v26 = 0;
  std::shared_ptr<void>::_Setpd<void *,WFDSConMgr::DriverHandleDeleter>(v27, v28, &v25);
  if ( v26[1] )
    std::_Ref_count_base::_Decref(v26[1]);
  if ( v13 )
    WFDSConMgr::CException::Throw(
      v13,
      "WFDSConMgr::CMaUsbHelper::StartIpSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      154,
      L"MA-USB OpenDriverHandle failed",
      this);
  WFDSConMgr::CriticalSection::Lock((char *)this + 8, &lpCriticalSection);
  if ( *((_BYTE *)this + 368) )
    WFDSConMgr::CException::Throw(
      199,
      "WFDSConMgr::CMaUsbHelper::StartIpSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      162,
      L"Operation was canceled before starting",
      this);
  std::shared_ptr<WFDSConMgr::CNotificationEvent>::operator=((char *)this + 264, v27);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids,
      this,
      *((_QWORD *)this + 33));
  }
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  WFDSConMgr::CMaUsbHelper::RegisterForPnpRemoveNotification(this);
  v23 = 0;
  v17 = a5;
  v18 = (*(__int64 (__fastcall **)(_QWORD, std::_Ref_count_base *, const struct sockaddr_in *, const struct WFDSConMgr::MaUsbTelemetryInfo *, __int64 *, unsigned __int16 *))(**((_QWORD **)this + 6) + 32LL))(
          *((_QWORD *)this + 6),
          v27[0],
          a3,
          a4,
          &v23,
          a5);
  if ( v18 )
    WFDSConMgr::CException::Throw(
      v18,
      "WFDSConMgr::CMaUsbHelper::StartIpSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      179,
      L"MA-USB OpenIpSession failed",
      this);
  *v17 = ntohs(*v17);
  WFDSConMgr::CriticalSection::Lock((char *)this + 8, &lpCriticalSection);
  *((_QWORD *)this + 43) = v23;
  *((_BYTE *)this + 369) = 1;
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  v25.m128i_i64[0] = (__int64)operator new(0xF8u);
  v19 = WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter::CMaUsbNotificationWaiter(
          (WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter *)v25.m128i_i64[0],
          (WFDSConMgr::CMaUsbHelper *)((char *)this + 112),
          this);
  v20 = *((_QWORD *)this + 29);
  *((_QWORD *)this + 29) = v19;
  if ( v20 )
    std::default_delete<WFDSConMgr::RPC::IServiceLifetimeToken>::operator()();
  v21 = (void **)*((_QWORD *)this + 29);
  WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter::StartPendingRequest((WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter *)v21);
  WFDSConMgr::SingleObjectWaiter::Wait((WFDSConMgr::SingleObjectWaiter *)v21, v21[20], v22);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, this, *v17);
  }
  if ( v27[1] )
    std::_Ref_count_base::_Decref(v27[1]);
}

```

## disassembly

```asm
0x18004ed3c  mov     [rsp-28h+arg_8], rbx
0x18004ed41  mov     [rsp-28h+arg_10], rsi
0x18004ed46  push    rbp
0x18004ed47  push    rdi
0x18004ed48  push    r13
0x18004ed4a  push    r14
0x18004ed4c  push    r15
0x18004ed4e  mov     rbp, rsp
0x18004ed51  sub     rsp, 80h
0x18004ed58  mov     r15, r9
0x18004ed5b  mov     r13, r8
0x18004ed5e  mov     rbx, rdx
0x18004ed61  mov     rdi, rcx
0x18004ed64  lea     rax, WPP_GLOBAL_Control
0x18004ed6b  mov     r10, cs:WPP_GLOBAL_Control
0x18004ed72  cmp     r10, rax
0x18004ed75  jz      short loc_18004EDAF
0x18004ed77  cmp     byte ptr [r10+19h], 4
0x18004ed7c  jb      short loc_18004EDAF
0x18004ed7e  test    byte ptr [r10+1Ch], 1
0x18004ed83  jz      short loc_18004EDAF
0x18004ed85  add     rcx, 118h
0x18004ed8c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004ed91  mov     [rsp+80h+var_50], r9; __int64
0x18004ed96  mov     edx, [r8+4]
0x18004ed9a  mov     dword ptr [rsp+80h+var_58], edx; char
0x18004ed9e  mov     [rsp+80h+var_60], rax; __int64
0x18004eda3  mov     r9, rdi
0x18004eda6  mov     rcx, [r10+10h]; LoggerHandle
0x18004edaa  call    WPP_SF_qSD_guid_
0x18004edaf  lea     r14, [rdi+8]
0x18004edb3  lea     rdx, [rbp+lpCriticalSection]
0x18004edb7  mov     rcx, r14
0x18004edba  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18004edbf  nop
0x18004edc0  cmp     byte ptr [rdi+170h], 0
0x18004edc7  jz      short loc_18004EDF9
0x18004edc9  mov     [rsp+80h+var_58], rdi; void *
0x18004edce  lea     rax, aOperationWasCa; "Operation was canceled before starting"
0x18004edd5  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x18004edda  mov     r9d, 288h; char
0x18004ede0  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004ede7  lea     rdx, aWfdsconmgrCmau_10; "WFDSConMgr::CMaUsbHelper::StartIpSessio"...
0x18004edee  mov     ecx, 800704C7h; char
0x18004edf3  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004edf9  cmp     byte ptr [rdi+171h], 0
0x18004ee00  jnz     loc_18004F12A
0x18004ee06  cmp     byte ptr [rdi+173h], 0
0x18004ee0d  jnz     loc_18004F12A
0x18004ee13  lea     rsi, [rdi+108h]
0x18004ee1a  cmp     qword ptr [rsi], 0
0x18004ee1e  jnz     loc_18004F12A
0x18004ee24  mov     [rdi+160h], rbx
0x18004ee2b  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18004ee2f  test    rcx, rcx
0x18004ee32  jz      short loc_18004EE3A
0x18004ee34  call    cs:__imp_LeaveCriticalSection
0x18004ee3a  mov     [rbp+arg_0], 0
0x18004ee42  mov     rcx, [rdi+30h]
0x18004ee46  mov     rax, [rcx]
0x18004ee49  lea     rdx, [rdi+118h]
0x18004ee50  lea     r8, [rbp+arg_0]
0x18004ee54  mov     rax, [rax+10h]
0x18004ee58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee5d  mov     ebx, eax
0x18004ee5f  mov     rax, [rdi+38h]
0x18004ee63  test    rax, rax
0x18004ee66  jz      short loc_18004EE6C
0x18004ee68  lock inc dword ptr [rax+8]
0x18004ee6c  mov     rax, [rdi+30h]
0x18004ee70  mov     [rbp+var_10], rax
0x18004ee74  mov     rcx, [rdi+38h]; this
0x18004ee78  mov     [rbp+var_10+8], rcx
0x18004ee7c  xorps   xmm0, xmm0
0x18004ee7f  movdqa  xmmword ptr [rbp+var_20], xmm0
0x18004ee84  test    rcx, rcx
0x18004ee87  jz      short loc_18004EE8D
0x18004ee89  lock inc dword ptr [rcx+8]
0x18004ee8d  movaps  xmm1, xmmword ptr [rbp+var_10]
0x18004ee91  movdqa  xmmword ptr [rbp+var_20], xmm1
0x18004ee96  test    rcx, rcx
0x18004ee99  jz      short loc_18004EEA5
0x18004ee9b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004eea0  movdqa  xmm1, xmmword ptr [rbp+var_20]
0x18004eea5  lea     rax, [rbp+var_20]
0x18004eea9  mov     [rbp+lpCriticalSection], rax
0x18004eead  xorps   xmm0, xmm0
0x18004eeb0  movdqu  xmmword ptr [rbp+var_10], xmm0
0x18004eeb5  movdqa  [rbp+var_30], xmm1
0x18004eeba  movdqa  xmmword ptr [rbp+var_20], xmm0
0x18004eebf  lea     r8, [rbp+var_30]
0x18004eec3  mov     rdx, [rbp+arg_0]
0x18004eec7  lea     rcx, [rbp+var_10]
0x18004eecb  call    ??$_Setpd@PEAXUDriverHandleDeleter@WFDSConMgr@@@?$shared_ptr@X@std@@AEAAXQEAXUDriverHandleDeleter@WFDSConMgr@@@Z; std::shared_ptr<void>::_Setpd<void *,WFDSConMgr::DriverHandleDeleter>(void * const,WFDSConMgr::DriverHandleDeleter)
0x18004eed0  nop
0x18004eed1  mov     rcx, [rbp+var_20+8]; this
0x18004eed5  test    rcx, rcx
0x18004eed8  jz      short loc_18004EEE0
0x18004eeda  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004eedf  nop
0x18004eee0  test    ebx, ebx
0x18004eee2  jz      short loc_18004EF1C
0x18004eee4  jle     short loc_18004EEEF
0x18004eee6  movzx   ebx, bx
0x18004eee9  or      ebx, 80070000h
0x18004eeef  mov     [rsp+80h+var_58], rdi; void *
0x18004eef4  lea     rax, aMaUsbOpendrive; "MA-USB OpenDriverHandle failed"
0x18004eefb  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x18004ef00  mov     r9d, 29Ah; char
0x18004ef06  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004ef0d  lea     rdx, aWfdsconmgrCmau_10; "WFDSConMgr::CMaUsbHelper::StartIpSessio"...
0x18004ef14  mov     ecx, ebx; char
0x18004ef16  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004ef1c  lea     rdx, [rbp+lpCriticalSection]
0x18004ef20  mov     rcx, r14
0x18004ef23  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18004ef28  nop
0x18004ef29  cmp     byte ptr [rdi+170h], 0
0x18004ef30  jz      short loc_18004EF62
0x18004ef32  mov     [rsp+80h+var_58], rdi; void *
0x18004ef37  lea     rax, aOperationWasCa; "Operation was canceled before starting"
0x18004ef3e  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x18004ef43  mov     r9d, 2A2h; char
0x18004ef49  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004ef50  lea     rdx, aWfdsconmgrCmau_10; "WFDSConMgr::CMaUsbHelper::StartIpSessio"...
0x18004ef57  mov     ecx, 800704C7h; char
0x18004ef5c  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004ef62  lea     rdx, [rbp+var_10]
0x18004ef66  mov     rcx, rsi
0x18004ef69  call    ??4?$shared_ptr@VCNotificationEvent@WFDSConMgr@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<WFDSConMgr::CNotificationEvent>::operator=(std::shared_ptr<WFDSConMgr::CNotificationEvent> const &)
0x18004ef6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ef75  lea     rax, WPP_GLOBAL_Control
0x18004ef7c  cmp     rcx, rax
0x18004ef7f  jz      short loc_18004EFAE
0x18004ef81  cmp     byte ptr [rcx+19h], 4
0x18004ef85  jb      short loc_18004EFAE
0x18004ef87  test    byte ptr [rcx+1Ch], 1
0x18004ef8b  jz      short loc_18004EFAE
0x18004ef8d  mov     edx, 14h
0x18004ef92  mov     rax, [rsi]
0x18004ef95  mov     [rsp+80h+var_60], rax
0x18004ef9a  mov     r9, rdi
0x18004ef9d  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004efa4  mov     rcx, [rcx+10h]
0x18004efa8  call    WPP_SF_qq
0x18004efad  nop
0x18004efae  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18004efb2  test    rcx, rcx
0x18004efb5  jz      short loc_18004EFBD
0x18004efb7  call    cs:__imp_LeaveCriticalSection
0x18004efbd  mov     rcx, rdi; this
0x18004efc0  call    ?RegisterForPnpRemoveNotification@CMaUsbHelper@WFDSConMgr@@AEAAXXZ; WFDSConMgr::CMaUsbHelper::RegisterForPnpRemoveNotification(void)
0x18004efc5  mov     [rbp+var_40], 0
0x18004efcd  mov     rcx, [rdi+30h]
0x18004efd1  mov     rax, [rcx]
0x18004efd4  mov     rsi, [rbp+arg_20]
0x18004efd8  mov     [rsp+80h+var_58], rsi
0x18004efdd  lea     rdx, [rbp+var_40]
0x18004efe1  mov     [rsp+80h+var_60], rdx
0x18004efe6  mov     r9, r15
0x18004efe9  mov     r8, r13
0x18004efec  mov     rdx, [rbp+var_10]
0x18004eff0  mov     rax, [rax+20h]
0x18004eff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eff9  test    eax, eax
0x18004effb  jz      short loc_18004F034
0x18004effd  jle     short loc_18004F007
0x18004efff  movzx   eax, ax
0x18004f002  or      eax, 80070000h
0x18004f007  mov     [rsp+80h+var_58], rdi; void *
0x18004f00c  lea     rcx, aMaUsbOpenipses; "MA-USB OpenIpSession failed"
0x18004f013  mov     [rsp+80h+var_60], rcx; unsigned __int16 *
0x18004f018  mov     r9d, 2B3h; char
0x18004f01e  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004f025  lea     rdx, aWfdsconmgrCmau_10; "WFDSConMgr::CMaUsbHelper::StartIpSessio"...
0x18004f02c  mov     ecx, eax; char
0x18004f02e  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004f034  movzx   ecx, word ptr [rsi]; netshort
0x18004f037  call    cs:__imp_ntohs
0x18004f03d  mov     [rsi], ax
0x18004f040  lea     rdx, [rbp+lpCriticalSection]
0x18004f044  mov     rcx, r14
0x18004f047  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18004f04c  mov     rax, [rbp+var_40]
0x18004f050  mov     [rdi+158h], rax
0x18004f057  mov     byte ptr [rdi+171h], 1
0x18004f05e  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18004f062  test    rcx, rcx
0x18004f065  jz      short loc_18004F06D
0x18004f067  call    cs:__imp_LeaveCriticalSection
0x18004f06d  mov     ecx, 0F8h; Size
0x18004f072  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f077  mov     qword ptr [rbp+var_30], rax
0x18004f07b  lea     rdx, [rdi+70h]; struct WFDSConMgr::CThreadpoolEnvironment *
0x18004f07f  mov     r8, rdi; struct WFDSConMgr::CMaUsbHelper *
0x18004f082  mov     rcx, rax; this
0x18004f085  call    ??0CMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@QEAA@PEAVCThreadpoolEnvironment@2@PEAV12@@Z; WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter::CMaUsbNotificationWaiter(WFDSConMgr::CThreadpoolEnvironment *,WFDSConMgr::CMaUsbHelper *)
0x18004f08a  nop
0x18004f08b  mov     rdx, [rdi+0E8h]
0x18004f092  mov     [rdi+0E8h], rax
0x18004f099  test    rdx, rdx
0x18004f09c  jz      short loc_18004F0A3
0x18004f09e  call    ??R?$default_delete@VIServiceLifetimeToken@RPC@WFDSConMgr@@@std@@QEBAXPEAVIServiceLifetimeToken@RPC@WFDSConMgr@@@Z; std::default_delete<WFDSConMgr::RPC::IServiceLifetimeToken>::operator()(WFDSConMgr::RPC::IServiceLifetimeToken *)
0x18004f0a3  mov     rbx, [rdi+0E8h]
0x18004f0aa  mov     rcx, rbx; this
0x18004f0ad  call    ?StartPendingRequest@CMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@AEAAXXZ; WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter::StartPendingRequest(void)
0x18004f0b2  mov     rdx, [rbx+0A0h]; void *
0x18004f0b9  mov     rcx, rbx; this
0x18004f0bc  call    ?Wait@SingleObjectWaiter@WFDSConMgr@@QEAAXPEAXK@Z; WFDSConMgr::SingleObjectWaiter::Wait(void *,ulong)
0x18004f0c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f0c8  lea     rax, WPP_GLOBAL_Control
0x18004f0cf  cmp     rcx, rax
0x18004f0d2  jz      short loc_18004F100
0x18004f0d4  cmp     byte ptr [rcx+19h], 4
0x18004f0d8  jb      short loc_18004F100
0x18004f0da  test    byte ptr [rcx+1Ch], 1
0x18004f0de  jz      short loc_18004F100
0x18004f0e0  movzx   eax, word ptr [rsi]
0x18004f0e3  mov     edx, 15h
0x18004f0e8  mov     dword ptr [rsp+80h+var_60], eax
0x18004f0ec  mov     r9, rdi
0x18004f0ef  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004f0f6  mov     rcx, [rcx+10h]
0x18004f0fa  call    WPP_SF_qD
0x18004f0ff  nop
0x18004f100  mov     rcx, [rbp+var_10+8]; this
0x18004f104  test    rcx, rcx
0x18004f107  jz      short loc_18004F10E
0x18004f109  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004f10e  lea     r11, [rsp+80h+var_s0]
0x18004f116  mov     rbx, [r11+38h]
0x18004f11a  mov     rsi, [r11+40h]
0x18004f11e  mov     rsp, r11
0x18004f121  pop     r15
0x18004f123  pop     r14
0x18004f125  pop     r13
0x18004f127  pop     rdi
0x18004f128  pop     rbp
0x18004f129  retn
0x18004f12a  mov     [rsp+80h+var_58], rdi; void *
0x18004f12f  lea     rax, aAttemptToStart_0; "Attempt to start MA-USB multiple times"
0x18004f136  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x18004f13b  mov     r9d, 28Ch; char
0x18004f141  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004f148  lea     rdx, aWfdsconmgrCmau_10; "WFDSConMgr::CMaUsbHelper::StartIpSessio"...
0x18004f14f  mov     ecx, 8007139Fh; char
0x18004f154  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
```
