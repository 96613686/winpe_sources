# WFDSConMgr::CMaUsbHelper::DisableIpSession(WFDSConMgr::IImpersonationProvider const &)

- ea: `0x18004d0d8`
- end: `0x18004d2e1`
- name: `?DisableIpSession@CMaUsbHelper@WFDSConMgr@@QEAAXAEBVIImpersonationProvider@2@@Z`
- size: `521`
- prototype: `void __fastcall(WFDSConMgr::CMaUsbHelper *__hidden this, const struct WFDSConMgr::IImpersonationProvider *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180056790`

## callees

- `0x18000475c`
- `0x180004f38`
- `0x1800059c0`
- `0x180006740`
- `0x180006eb0`
- `0x180028a10`
- `0x18004d0d8`
- `0x18005c888`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d1b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d261`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d1b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d261`

## string_xrefs

- `0x18004d2b6`: `Attempt to disable MA-USB when not started`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall WFDSConMgr::CMaUsbHelper::DisableIpSession(
        void **this,
        const struct WFDSConMgr::IImpersonationProvider *a2)
{
  int v4; // eax
  std::_Ref_count_base *v5[2]; // [rsp+30h] [rbp-38h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+70h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, this);
  }
  *(_OWORD *)v5 = 0;
  WFDSConMgr::CriticalSection::Lock(this + 1, &lpCriticalSection);
  if ( *((_BYTE *)this + 368) )
    WFDSConMgr::CException::Throw(
      199,
      "WFDSConMgr::CMaUsbHelper::DisableIpSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      32,
      L"Operation was canceled before starting",
      this);
  if ( !*((_BYTE *)this + 369) || *((_BYTE *)this + 371) || !this[33] )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CMaUsbHelper::DisableIpSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      36,
      L"Attempt to disable MA-USB when not started",
      this);
  std::shared_ptr<WFDSConMgr::CNotificationEvent>::operator=(v5, this + 33);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  (*(void (__fastcall **)(const struct WFDSConMgr::IImpersonationProvider *, LPCRITICAL_SECTION *))(*(_QWORD *)a2 + 8LL))(
    a2,
    &lpCriticalSection);
  WFDSConMgr::CDevQueryHelper::SetMaUsbDeviceRemoteInputAllowed(this[12], (__int64)(this + 39), 0);
  std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(&lpCriticalSection);
  v4 = (*(__int64 (__fastcall **)(void *, std::_Ref_count_base *, void *))(*(_QWORD *)this[6] + 56LL))(
         this[6],
         v5[0],
         this[43]);
  if ( v4 )
    WFDSConMgr::CException::Throw(
      v4,
      "WFDSConMgr::CMaUsbHelper::DisableIpSession",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      52,
      L"MA-USB DisableIpSession failed",
      this);
  WFDSConMgr::CriticalSection::Lock(this + 1, &lpCriticalSection);
  *((_WORD *)this + 186) = 1;
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, this);
  }
  if ( v5[1] )
    std::_Ref_count_base::_Decref(v5[1]);
}

```

## disassembly

```asm
0x18004d0d8  push    rbx
0x18004d0da  push    rsi
0x18004d0db  push    rdi
0x18004d0dc  push    r14
0x18004d0de  sub     rsp, 48h
0x18004d0e2  mov     rsi, rdx
0x18004d0e5  mov     rbx, rcx
0x18004d0e8  lea     r14, WPP_GLOBAL_Control
0x18004d0ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d0f6  cmp     rcx, r14
0x18004d0f9  jz      short loc_18004D11F
0x18004d0fb  cmp     byte ptr [rcx+19h], 4
0x18004d0ff  jb      short loc_18004D11F
0x18004d101  test    byte ptr [rcx+1Ch], 1
0x18004d105  jz      short loc_18004D11F
0x18004d107  mov     edx, 19h
0x18004d10c  mov     r9, rbx
0x18004d10f  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004d116  mov     rcx, [rcx+10h]
0x18004d11a  call    WPP_SF_q
0x18004d11f  xorps   xmm0, xmm0
0x18004d122  movdqu  xmmword ptr [rsp+68h+var_38], xmm0
0x18004d128  lea     rdx, [rsp+68h+lpCriticalSection]
0x18004d12d  lea     rcx, [rbx+8]
0x18004d131  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18004d136  nop
0x18004d137  cmp     byte ptr [rbx+170h], 0
0x18004d13e  jz      short loc_18004D170
0x18004d140  mov     [rsp+68h+var_40], rbx; void *
0x18004d145  lea     rax, aOperationWasCa; "Operation was canceled before starting"
0x18004d14c  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18004d151  mov     r9d, 320h; char
0x18004d157  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004d15e  lea     rdx, aWfdsconmgrCmau; "WFDSConMgr::CMaUsbHelper::DisableIpSess"...
0x18004d165  mov     ecx, 800704C7h; char
0x18004d16a  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004d170  cmp     byte ptr [rbx+171h], 0
0x18004d177  jz      loc_18004D2B1
0x18004d17d  cmp     byte ptr [rbx+173h], 0
0x18004d184  jnz     loc_18004D2B1
0x18004d18a  lea     rdx, [rbx+108h]
0x18004d191  cmp     qword ptr [rdx], 0
0x18004d195  jz      loc_18004D2B1
0x18004d19b  lea     rcx, [rsp+68h+var_38]
0x18004d1a0  call    ??4?$shared_ptr@VCNotificationEvent@WFDSConMgr@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<WFDSConMgr::CNotificationEvent>::operator=(std::shared_ptr<WFDSConMgr::CNotificationEvent> const &)
0x18004d1a5  nop
0x18004d1a6  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x18004d1ab  test    rcx, rcx
0x18004d1ae  jz      short loc_18004D1B6
0x18004d1b0  call    cs:__imp_LeaveCriticalSection
0x18004d1b6  mov     rax, [rsi]
0x18004d1b9  lea     rdx, [rsp+68h+lpCriticalSection]
0x18004d1be  mov     rcx, rsi
0x18004d1c1  mov     rax, [rax+8]
0x18004d1c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d1ca  nop
0x18004d1cb  lea     rdx, [rbx+138h]
0x18004d1d2  xor     r8d, r8d
0x18004d1d5  mov     rcx, [rbx+60h]; void *
0x18004d1d9  call    ?SetMaUsbDeviceRemoteInputAllowed@CDevQueryHelper@WFDSConMgr@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; WFDSConMgr::CDevQueryHelper::SetMaUsbDeviceRemoteInputAllowed(std::wstring const &,bool)
0x18004d1de  nop
0x18004d1df  lea     rcx, [rsp+68h+lpCriticalSection]
0x18004d1e4  call    ??1?$unique_ptr@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@U?$default_delete@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(void)
0x18004d1e9  mov     rcx, [rbx+30h]
0x18004d1ed  mov     rax, [rcx]
0x18004d1f0  mov     r8, [rbx+158h]
0x18004d1f7  mov     rdx, [rsp+68h+var_38]
0x18004d1fc  mov     rax, [rax+38h]
0x18004d200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d205  test    eax, eax
0x18004d207  jz      short loc_18004D240
0x18004d209  jle     short loc_18004D213
0x18004d20b  movzx   eax, ax
0x18004d20e  or      eax, 80070000h
0x18004d213  mov     [rsp+68h+var_40], rbx; void *
0x18004d218  lea     rcx, aMaUsbDisableip; "MA-USB DisableIpSession failed"
0x18004d21f  mov     [rsp+68h+var_48], rcx; unsigned __int16 *
0x18004d224  mov     r9d, 334h; char
0x18004d22a  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004d231  lea     rdx, aWfdsconmgrCmau; "WFDSConMgr::CMaUsbHelper::DisableIpSess"...
0x18004d238  mov     ecx, eax; char
0x18004d23a  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004d240  lea     rdx, [rsp+68h+lpCriticalSection]
0x18004d245  lea     rcx, [rbx+8]
0x18004d249  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18004d24e  mov     word ptr [rbx+174h], 1
0x18004d257  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x18004d25c  test    rcx, rcx
0x18004d25f  jz      short loc_18004D267
0x18004d261  call    cs:__imp_LeaveCriticalSection
0x18004d267  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d26e  cmp     rcx, r14
0x18004d271  jz      short loc_18004D298
0x18004d273  cmp     byte ptr [rcx+19h], 4
0x18004d277  jb      short loc_18004D298
0x18004d279  test    byte ptr [rcx+1Ch], 1
0x18004d27d  jz      short loc_18004D298
0x18004d27f  mov     edx, 1Ah
0x18004d284  mov     r9, rbx
0x18004d287  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004d28e  mov     rcx, [rcx+10h]
0x18004d292  call    WPP_SF_q
0x18004d297  nop
0x18004d298  mov     rcx, [rsp+68h+var_38+8]; this
0x18004d29d  test    rcx, rcx
0x18004d2a0  jz      short loc_18004D2A7
0x18004d2a2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004d2a7  add     rsp, 48h
0x18004d2ab  pop     r14
0x18004d2ad  pop     rdi
0x18004d2ae  pop     rsi
0x18004d2af  pop     rbx
0x18004d2b0  retn
0x18004d2b1  mov     [rsp+68h+var_40], rbx; void *
0x18004d2b6  lea     rax, aAttemptToDisab; "Attempt to disable MA-USB when not star"...
0x18004d2bd  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18004d2c2  mov     r9d, 324h; char
0x18004d2c8  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004d2cf  lea     rdx, aWfdsconmgrCmau; "WFDSConMgr::CMaUsbHelper::DisableIpSess"...
0x18004d2d6  mov     ecx, 8007139Fh; char
0x18004d2db  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
```
