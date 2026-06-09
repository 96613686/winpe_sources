# WFDSConMgr::CMaUsbHelper::EnableIpSession(WFDSConMgr::IImpersonationProvider const &,bool)

- ea: `0x18004d3b8`
- end: `0x18004d5dc`
- name: `?EnableIpSession@CMaUsbHelper@WFDSConMgr@@QEAAXAEBVIImpersonationProvider@2@_N@Z`
- size: `548`
- prototype: `void __fastcall(WFDSConMgr::CMaUsbHelper *__hidden this, const struct WFDSConMgr::IImpersonationProvider *, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18004d5e4`
- `0x180056790`

## callees

- `0x18000475c`
- `0x180004f38`
- `0x1800059c0`
- `0x180006740`
- `0x180006eb0`
- `0x180028a10`
- `0x18004d3b8`
- `0x18005c888`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d49c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d552`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d49c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d552`

## string_xrefs

- `0x18004d5b1`: `Attempt to enable MA-USB when not started`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall WFDSConMgr::CMaUsbHelper::EnableIpSession(
        void **this,
        const struct WFDSConMgr::IImpersonationProvider *a2,
        char a3)
{
  int v6; // eax
  std::_Ref_count_base *v7[2]; // [rsp+30h] [rbp-28h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, this);
  }
  *(_OWORD *)v7 = 0;
  WFDSConMgr::CriticalSection::Lock(this + 1, &lpCriticalSection);
  if ( *((_BYTE *)this + 368) )
    WFDSConMgr::CException::Throw(
      199,
      "WFDSConMgr::CMaUsbHelper::EnableIpSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      245,
      L"Operation was canceled before starting",
      this);
  if ( !*((_BYTE *)this + 369) || *((_BYTE *)this + 371) || !this[33] )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CMaUsbHelper::EnableIpSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      249,
      L"Attempt to enable MA-USB when not started",
      this);
  std::shared_ptr<WFDSConMgr::CNotificationEvent>::operator=(v7, this + 33);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  if ( a3 )
  {
    (*(void (__fastcall **)(const struct WFDSConMgr::IImpersonationProvider *, LPCRITICAL_SECTION *))(*(_QWORD *)a2 + 8LL))(
      a2,
      &lpCriticalSection);
    WFDSConMgr::CDevQueryHelper::SetMaUsbDeviceRemoteInputAllowed(this[12], (__int64)(this + 39), 1);
    std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(&lpCriticalSection);
  }
  v6 = (*(__int64 (__fastcall **)(void *, std::_Ref_count_base *, void *))(*(_QWORD *)this[6] + 48LL))(
         this[6],
         v7[0],
         this[43]);
  if ( v6 )
    WFDSConMgr::CException::Throw(
      v6,
      "WFDSConMgr::CMaUsbHelper::EnableIpSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      10,
      L"MA-USB EnableIpSession failed",
      this);
  WFDSConMgr::CriticalSection::Lock(this + 1, &lpCriticalSection);
  *((_WORD *)this + 186) = 257;
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, this);
  }
  if ( v7[1] )
    std::_Ref_count_base::_Decref(v7[1]);
}

```

## disassembly

```asm
0x18004d3b8  mov     [rsp+arg_8], rbx
0x18004d3bd  mov     [rsp+arg_10], rsi
0x18004d3c2  push    rdi
0x18004d3c3  push    r14
0x18004d3c5  push    r15
0x18004d3c7  sub     rsp, 40h
0x18004d3cb  mov     sil, r8b
0x18004d3ce  mov     r14, rdx
0x18004d3d1  mov     rbx, rcx
0x18004d3d4  lea     r15, WPP_GLOBAL_Control
0x18004d3db  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d3e2  cmp     rcx, r15
0x18004d3e5  jz      short loc_18004D40B
0x18004d3e7  cmp     byte ptr [rcx+19h], 4
0x18004d3eb  jb      short loc_18004D40B
0x18004d3ed  test    byte ptr [rcx+1Ch], 1
0x18004d3f1  jz      short loc_18004D40B
0x18004d3f3  mov     edx, 17h
0x18004d3f8  mov     r9, rbx
0x18004d3fb  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004d402  mov     rcx, [rcx+10h]
0x18004d406  call    WPP_SF_q
0x18004d40b  xorps   xmm0, xmm0
0x18004d40e  movdqu  xmmword ptr [rsp+58h+var_28], xmm0
0x18004d414  lea     rdx, [rsp+58h+lpCriticalSection]
0x18004d419  lea     rcx, [rbx+8]
0x18004d41d  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18004d422  nop
0x18004d423  cmp     byte ptr [rbx+170h], 0
0x18004d42a  jz      short loc_18004D45C
0x18004d42c  mov     [rsp+58h+var_30], rbx; void *
0x18004d431  lea     rax, aOperationWasCa; "Operation was canceled before starting"
0x18004d438  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x18004d43d  mov     r9d, 2F5h; char
0x18004d443  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004d44a  lea     rdx, aWfdsconmgrCmau_1; "WFDSConMgr::CMaUsbHelper::EnableIpSessi"...
0x18004d451  mov     ecx, 800704C7h; char
0x18004d456  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004d45c  cmp     byte ptr [rbx+171h], 0
0x18004d463  jz      loc_18004D5AC
0x18004d469  cmp     byte ptr [rbx+173h], 0
0x18004d470  jnz     loc_18004D5AC
0x18004d476  lea     rdx, [rbx+108h]
0x18004d47d  cmp     qword ptr [rdx], 0
0x18004d481  jz      loc_18004D5AC
0x18004d487  lea     rcx, [rsp+58h+var_28]
0x18004d48c  call    ??4?$shared_ptr@VCNotificationEvent@WFDSConMgr@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<WFDSConMgr::CNotificationEvent>::operator=(std::shared_ptr<WFDSConMgr::CNotificationEvent> const &)
0x18004d491  nop
0x18004d492  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x18004d497  test    rcx, rcx
0x18004d49a  jz      short loc_18004D4A2
0x18004d49c  call    cs:__imp_LeaveCriticalSection
0x18004d4a2  test    sil, sil
0x18004d4a5  jz      short loc_18004D4DA
0x18004d4a7  mov     rax, [r14]
0x18004d4aa  lea     rdx, [rsp+58h+lpCriticalSection]
0x18004d4af  mov     rcx, r14
0x18004d4b2  mov     rax, [rax+8]
0x18004d4b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4bb  nop
0x18004d4bc  lea     rdx, [rbx+138h]
0x18004d4c3  mov     r8b, 1
0x18004d4c6  mov     rcx, [rbx+60h]; void *
0x18004d4ca  call    ?SetMaUsbDeviceRemoteInputAllowed@CDevQueryHelper@WFDSConMgr@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; WFDSConMgr::CDevQueryHelper::SetMaUsbDeviceRemoteInputAllowed(std::wstring const &,bool)
0x18004d4cf  nop
0x18004d4d0  lea     rcx, [rsp+58h+lpCriticalSection]
0x18004d4d5  call    ??1?$unique_ptr@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@U?$default_delete@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(void)
0x18004d4da  mov     rcx, [rbx+30h]
0x18004d4de  mov     rax, [rcx]
0x18004d4e1  mov     r8, [rbx+158h]
0x18004d4e8  mov     rdx, [rsp+58h+var_28]
0x18004d4ed  mov     rax, [rax+30h]
0x18004d4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4f6  test    eax, eax
0x18004d4f8  jz      short loc_18004D531
0x18004d4fa  jle     short loc_18004D504
0x18004d4fc  movzx   eax, ax
0x18004d4ff  or      eax, 80070000h
0x18004d504  mov     [rsp+58h+var_30], rbx; void *
0x18004d509  lea     rcx, aMaUsbEnableips; "MA-USB EnableIpSession failed"
0x18004d510  mov     [rsp+58h+var_38], rcx; unsigned __int16 *
0x18004d515  mov     r9d, 30Ah; char
0x18004d51b  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004d522  lea     rdx, aWfdsconmgrCmau_1; "WFDSConMgr::CMaUsbHelper::EnableIpSessi"...
0x18004d529  mov     ecx, eax; char
0x18004d52b  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004d531  lea     rdx, [rsp+58h+lpCriticalSection]
0x18004d536  lea     rcx, [rbx+8]
0x18004d53a  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18004d53f  mov     word ptr [rbx+174h], 101h
0x18004d548  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x18004d54d  test    rcx, rcx
0x18004d550  jz      short loc_18004D558
0x18004d552  call    cs:__imp_LeaveCriticalSection
0x18004d558  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d55f  cmp     rcx, r15
0x18004d562  jz      short loc_18004D589
0x18004d564  cmp     byte ptr [rcx+19h], 4
0x18004d568  jb      short loc_18004D589
0x18004d56a  test    byte ptr [rcx+1Ch], 1
0x18004d56e  jz      short loc_18004D589
0x18004d570  mov     edx, 18h
0x18004d575  mov     r9, rbx
0x18004d578  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004d57f  mov     rcx, [rcx+10h]
0x18004d583  call    WPP_SF_q
0x18004d588  nop
0x18004d589  mov     rcx, [rsp+58h+var_28+8]; this
0x18004d58e  test    rcx, rcx
0x18004d591  jz      short loc_18004D598
0x18004d593  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004d598  mov     rbx, [rsp+58h+arg_8]
0x18004d59d  mov     rsi, [rsp+58h+arg_10]
0x18004d5a2  add     rsp, 40h
0x18004d5a6  pop     r15
0x18004d5a8  pop     r14
0x18004d5aa  pop     rdi
0x18004d5ab  retn
0x18004d5ac  mov     [rsp+58h+var_30], rbx; void *
0x18004d5b1  lea     rax, aAttemptToEnabl; "Attempt to enable MA-USB when not start"...
0x18004d5b8  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x18004d5bd  mov     r9d, 2F9h; char
0x18004d5c3  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004d5ca  lea     rdx, aWfdsconmgrCmau_1; "WFDSConMgr::CMaUsbHelper::EnableIpSessi"...
0x18004d5d1  mov     ecx, 8007139Fh; char
0x18004d5d6  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
```
