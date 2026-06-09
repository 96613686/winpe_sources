# WFDSConMgr::CMaUsbHelper::InitializeDatarateInformation(WFDSConMgr::MaUsbDatarateInfo const &,std::unique_ptr<_MiracastDatarateRegistrationHandle,WFDSConMgr::MiracastDatarateUnregisterDeleter>)

- ea: `0x18004d71c`
- end: `0x18004d8d7`
- name: `?InitializeDatarateInformation@CMaUsbHelper@WFDSConMgr@@QEAAXAEBUMaUsbDatarateInfo@2@V?$unique_ptr@U_MiracastDatarateRegistrationHandle@@UMiracastDatarateUnregisterDeleter@WFDSConMgr@@@std@@@Z`
- size: `443`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180057b48`

## callees

- `0x18000475c`
- `0x1800059c0`
- `0x180006eb0`
- `0x180009ba8`
- `0x180029f8c`
- `0x18003669c`
- `0x18004d71c`
- `0x18005c888`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d810`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d810`

## string_xrefs

- `0x18004d8ac`: `Attempt to initialize MA-USB datarate when not started`
- `0x18004d848`: `MA-USB SendDatarateUpdate failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall WFDSConMgr::CMaUsbHelper::InitializeDatarateInformation(char *a1, _QWORD *a2, __int64 *a3)
{
  int v6; // eax
  std::_Ref_count_base *v7[2]; // [rsp+30h] [rbp-18h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp+8h] BYREF
  __int64 *v9; // [rsp+60h] [rbp+18h]

  v9 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids,
      a1,
      *a2,
      a2[1]);
  }
  *(_OWORD *)v7 = 0;
  WFDSConMgr::CriticalSection::Lock(a1 + 8, &lpCriticalSection);
  if ( a1[368] )
    WFDSConMgr::CException::Throw(
      199,
      "WFDSConMgr::CMaUsbHelper::InitializeDatarateInformation",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      213,
      L"Operation was canceled before starting",
      a1);
  if ( !a1[369] || a1[371] || !*((_QWORD *)a1 + 33) )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CMaUsbHelper::InitializeDatarateInformation",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      217,
      L"Attempt to initialize MA-USB datarate when not started",
      a1);
  std::shared_ptr<WFDSConMgr::CNotificationEvent>::operator=(v7, a1 + 264);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  v6 = (*(__int64 (__fastcall **)(_QWORD, std::_Ref_count_base *, _QWORD, _QWORD *))(**((_QWORD **)a1 + 6) + 72LL))(
         *((_QWORD *)a1 + 6),
         v7[0],
         *((_QWORD *)a1 + 43),
         a2);
  if ( v6 )
    WFDSConMgr::CException::Throw(
      v6,
      "WFDSConMgr::CMaUsbHelper::InitializeDatarateInformation",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      226,
      L"MA-USB SendDatarateUpdate failed",
      a1);
  std::unique_ptr<void *,WFDSConMgr::WFDVmgrRegistrationDeleter>::operator=<WFDSConMgr::WFDVmgrRegistrationDeleter,0>(
    (_QWORD *)a1 + 30,
    a3);
  if ( v7[1] )
    std::_Ref_count_base::_Decref(v7[1]);
  std::unique_ptr<DAF_ASSOCIATION_HANDLE__ *,WFDSConMgr::DafAssociationContextDeleter>::~unique_ptr<DAF_ASSOCIATION_HANDLE__ *,WFDSConMgr::DafAssociationContextDeleter>(a3);
}

```

## disassembly

```asm
0x18004d71c  mov     r11, rsp
0x18004d71f  mov     [r11+10h], rbx
0x18004d723  mov     [r11+20h], rsi
0x18004d727  mov     [r11+18h], r8
0x18004d72b  push    rdi
0x18004d72c  sub     rsp, 40h
0x18004d730  mov     rdi, r8
0x18004d733  mov     rsi, rdx
0x18004d736  mov     rbx, rcx
0x18004d739  lea     rax, WPP_GLOBAL_Control
0x18004d740  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d747  cmp     rcx, rax
0x18004d74a  jz      short loc_18004D77F
0x18004d74c  cmp     byte ptr [rcx+19h], 4
0x18004d750  jb      short loc_18004D77F
0x18004d752  test    byte ptr [rcx+1Ch], 1
0x18004d756  jz      short loc_18004D77F
0x18004d758  mov     edx, 16h
0x18004d75d  mov     rax, [rsi+8]
0x18004d761  mov     [r11-20h], rax
0x18004d765  mov     rax, [rsi]
0x18004d768  mov     [r11-28h], rax
0x18004d76c  mov     r9, rbx
0x18004d76f  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004d776  mov     rcx, [rcx+10h]
0x18004d77a  call    WPP_SF_qqq
0x18004d77f  xorps   xmm0, xmm0
0x18004d782  movdqu  xmmword ptr [rsp+48h+var_18], xmm0
0x18004d788  lea     rcx, [rbx+8]
0x18004d78c  lea     rdx, [rsp+48h+lpCriticalSection]
0x18004d791  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18004d796  nop
0x18004d797  cmp     byte ptr [rbx+170h], 0
0x18004d79e  jz      short loc_18004D7D0
0x18004d7a0  mov     [rsp+48h+var_20], rbx; void *
0x18004d7a5  lea     rax, aOperationWasCa; "Operation was canceled before starting"
0x18004d7ac  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18004d7b1  mov     r9d, 2D5h; char
0x18004d7b7  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004d7be  lea     rdx, aWfdsconmgrCmau_5; "WFDSConMgr::CMaUsbHelper::InitializeDat"...
0x18004d7c5  mov     ecx, 800704C7h; char
0x18004d7ca  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004d7d0  cmp     byte ptr [rbx+171h], 0
0x18004d7d7  jz      loc_18004D8A7
0x18004d7dd  cmp     byte ptr [rbx+173h], 0
0x18004d7e4  jnz     loc_18004D8A7
0x18004d7ea  lea     rdx, [rbx+108h]
0x18004d7f1  cmp     qword ptr [rdx], 0
0x18004d7f5  jz      loc_18004D8A7
0x18004d7fb  lea     rcx, [rsp+48h+var_18]
0x18004d800  call    ??4?$shared_ptr@VCNotificationEvent@WFDSConMgr@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<WFDSConMgr::CNotificationEvent>::operator=(std::shared_ptr<WFDSConMgr::CNotificationEvent> const &)
0x18004d805  nop
0x18004d806  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x18004d80b  test    rcx, rcx
0x18004d80e  jz      short loc_18004D816
0x18004d810  call    cs:__imp_LeaveCriticalSection
0x18004d816  mov     rcx, [rbx+30h]
0x18004d81a  mov     rax, [rcx]
0x18004d81d  mov     r9, rsi
0x18004d820  mov     r8, [rbx+158h]
0x18004d827  mov     rdx, [rsp+48h+var_18]
0x18004d82c  mov     rax, [rax+48h]
0x18004d830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d835  test    eax, eax
0x18004d837  jz      short loc_18004D870
0x18004d839  jle     short loc_18004D843
0x18004d83b  movzx   eax, ax
0x18004d83e  or      eax, 80070000h
0x18004d843  mov     [rsp+48h+var_20], rbx; void *
0x18004d848  lea     rcx, aMaUsbSenddatar; "MA-USB SendDatarateUpdate failed"
0x18004d84f  mov     [rsp+48h+var_28], rcx; unsigned __int16 *
0x18004d854  mov     r9d, 2E2h; char
0x18004d85a  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004d861  lea     rdx, aWfdsconmgrCmau_5; "WFDSConMgr::CMaUsbHelper::InitializeDat"...
0x18004d868  mov     ecx, eax; char
0x18004d86a  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004d870  lea     rcx, [rbx+0F0h]
0x18004d877  mov     rdx, rdi
0x18004d87a  call    ??$?4UWFDVmgrRegistrationDeleter@WFDSConMgr@@$0A@@?$unique_ptr@PEAXUWFDVmgrRegistrationDeleter@WFDSConMgr@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<void *,WFDSConMgr::WFDVmgrRegistrationDeleter>::operator=<WFDSConMgr::WFDVmgrRegistrationDeleter,0>(std::unique_ptr<void *,WFDSConMgr::WFDVmgrRegistrationDeleter> &&)
0x18004d87f  nop
0x18004d880  mov     rcx, [rsp+48h+var_18+8]; this
0x18004d885  test    rcx, rcx
0x18004d888  jz      short loc_18004D890
0x18004d88a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004d88f  nop
0x18004d890  mov     rcx, rdi
0x18004d893  mov     rbx, [rsp+48h+arg_8]
0x18004d898  mov     rsi, [rsp+48h+arg_18]
0x18004d89d  add     rsp, 40h
0x18004d8a1  pop     rdi
0x18004d8a2  jmp     ??1?$unique_ptr@PEAUDAF_ASSOCIATION_HANDLE__@@UDafAssociationContextDeleter@WFDSConMgr@@@std@@QEAA@XZ; std::unique_ptr<DAF_ASSOCIATION_HANDLE__ *,WFDSConMgr::DafAssociationContextDeleter>::~unique_ptr<DAF_ASSOCIATION_HANDLE__ *,WFDSConMgr::DafAssociationContextDeleter>(void)
0x18004d8a7  mov     [rsp+48h+var_20], rbx; void *
0x18004d8ac  lea     rax, aAttemptToIniti; "Attempt to initialize MA-USB datarate w"...
0x18004d8b3  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18004d8b8  mov     r9d, 2D9h; char
0x18004d8be  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004d8c5  lea     rdx, aWfdsconmgrCmau_5; "WFDSConMgr::CMaUsbHelper::InitializeDat"...
0x18004d8cc  mov     ecx, 8007139Fh; char
0x18004d8d1  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
```
