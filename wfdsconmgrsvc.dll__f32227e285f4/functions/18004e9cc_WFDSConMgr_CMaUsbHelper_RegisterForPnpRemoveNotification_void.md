# WFDSConMgr::CMaUsbHelper::RegisterForPnpRemoveNotification(void)

- ea: `0x18004e9cc`
- end: `0x18004eb39`
- name: `?RegisterForPnpRemoveNotification@CMaUsbHelper@WFDSConMgr@@AEAAXXZ`
- size: `365`
- prototype: `void __fastcall(WFDSConMgr::CMaUsbHelper *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004ed3c`

## callees

- `0x180002600`
- `0x180002ffc`
- `0x1800059c0`
- `0x180006740`
- `0x18004e9cc`
- `0x18005c888`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004eb12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004eb12`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18004ea98`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18004ea98`

## string_xrefs

- `0x18004eac8`: `WFDSConMgr::CMaUsbHelper::RegisterForPnpRemoveNotification`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WFDSConMgr::CMaUsbHelper::RegisterForPnpRemoveNotification(WFDSConMgr::CMaUsbHelper *this)
{
  CONFIGRET v2; // eax
  char v3; // al
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+30h] [rbp-1C8h] BYREF
  _DWORD v5[4]; // [rsp+40h] [rbp-1B8h] BYREF
  __int64 v6; // [rsp+50h] [rbp-1A8h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, this);
  }
  WFDSConMgr::CriticalSection::Lock((char *)this + 8, lpCriticalSection);
  memset_0(v5, 0, 0x1A0u);
  v5[0] = 416;
  v5[2] = 1;
  v6 = *((_QWORD *)this + 33);
  v2 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, WFDSConMgr::CMaUsbHelper *, void *, char *))(**((_QWORD **)this + 8)
                                                                                               + 8LL))(
         *((_QWORD *)this + 8),
         v5,
         this,
         &WFDSConMgr::CMaUsbHelper::PnpNotificationCallback,
         (char *)this + 360);
  if ( v2 )
  {
    v3 = CM_MapCrToWin32Err(v2, 0x306u);
    WFDSConMgr::CException::Throw(
      v3,
      "WFDSConMgr::CMaUsbHelper::RegisterForPnpRemoveNotification",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      132,
      L"CM_Register_Notification failed",
      this);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, this);
  }
  if ( lpCriticalSection[0] )
    LeaveCriticalSection(lpCriticalSection[0]);
}

```

## disassembly

```asm
0x18004e9cc  mov     [rsp+arg_8], rbx
0x18004e9d1  push    rsi
0x18004e9d2  sub     rsp, 1F0h
0x18004e9d9  mov     rax, cs:__security_cookie
0x18004e9e0  xor     rax, rsp
0x18004e9e3  mov     [rsp+1F8h+var_18], rax
0x18004e9eb  mov     rbx, rcx
0x18004e9ee  lea     rsi, WPP_GLOBAL_Control
0x18004e9f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e9fc  cmp     rcx, rsi
0x18004e9ff  jz      short loc_18004EA25
0x18004ea01  cmp     byte ptr [rcx+19h], 4
0x18004ea05  jb      short loc_18004EA25
0x18004ea07  test    byte ptr [rcx+1Ch], 1
0x18004ea0b  jz      short loc_18004EA25
0x18004ea0d  mov     edx, 2Fh ; '/'
0x18004ea12  mov     r9, rbx
0x18004ea15  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004ea1c  mov     rcx, [rcx+10h]
0x18004ea20  call    WPP_SF_q
0x18004ea25  lea     rcx, [rbx+8]
0x18004ea29  lea     rdx, [rsp+1F8h+lpCriticalSection]
0x18004ea2e  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18004ea33  nop
0x18004ea34  xor     edx, edx; Val
0x18004ea36  mov     r8d, 1A0h; Size
0x18004ea3c  lea     rcx, [rsp+1F8h+var_1B8]; void *
0x18004ea41  call    memset_0
0x18004ea46  mov     [rsp+1F8h+var_1B8], 1A0h
0x18004ea4e  mov     [rsp+1F8h+var_1B0], 1
0x18004ea56  mov     rax, [rbx+108h]
0x18004ea5d  mov     [rsp+1F8h+var_1A8], rax
0x18004ea62  mov     rcx, [rbx+40h]
0x18004ea66  mov     rax, [rcx]
0x18004ea69  lea     rdx, [rbx+168h]
0x18004ea70  mov     [rsp+1F8h+var_1D8], rdx
0x18004ea75  lea     r9, ?PnpNotificationCallback@CMaUsbHelper@WFDSConMgr@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; WFDSConMgr::CMaUsbHelper::PnpNotificationCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x18004ea7c  mov     r8, rbx
0x18004ea7f  lea     rdx, [rsp+1F8h+var_1B8]
0x18004ea84  mov     rax, [rax+8]
0x18004ea88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea8d  test    eax, eax
0x18004ea8f  jz      short loc_18004EAD7
0x18004ea91  mov     edx, 306h; DefaultErr
0x18004ea96  mov     ecx, eax; CmReturnCode
0x18004ea98  call    cs:__imp_CM_MapCrToWin32Err
0x18004ea9e  test    eax, eax
0x18004eaa0  jle     short loc_18004EAAA
0x18004eaa2  movzx   eax, ax
0x18004eaa5  or      eax, 80070000h
0x18004eaaa  mov     [rsp+1F8h+var_1D0], rbx; void *
0x18004eaaf  lea     rcx, aCmRegisterNoti; "CM_Register_Notification failed"
0x18004eab6  mov     [rsp+1F8h+var_1D8], rcx; unsigned __int16 *
0x18004eabb  mov     r9d, 484h; char
0x18004eac1  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004eac8  lea     rdx, aWfdsconmgrCmau_7; "WFDSConMgr::CMaUsbHelper::RegisterForPn"...
0x18004eacf  mov     ecx, eax; char
0x18004ead1  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004ead7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eade  cmp     rcx, rsi
0x18004eae1  jz      short loc_18004EB08
0x18004eae3  cmp     byte ptr [rcx+19h], 4
0x18004eae7  jb      short loc_18004EB08
0x18004eae9  test    byte ptr [rcx+1Ch], 1
0x18004eaed  jz      short loc_18004EB08
0x18004eaef  mov     edx, 30h ; '0'
0x18004eaf4  mov     r9, rbx
0x18004eaf7  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004eafe  mov     rcx, [rcx+10h]
0x18004eb02  call    WPP_SF_q
0x18004eb07  nop
0x18004eb08  mov     rcx, [rsp+1F8h+lpCriticalSection]; lpCriticalSection
0x18004eb0d  test    rcx, rcx
0x18004eb10  jz      short loc_18004EB18
0x18004eb12  call    cs:__imp_LeaveCriticalSection
0x18004eb18  mov     rcx, [rsp+1F8h+var_18]
0x18004eb20  xor     rcx, rsp; StackCookie
0x18004eb23  call    __security_check_cookie
0x18004eb28  mov     rbx, [rsp+1F8h+arg_8]
0x18004eb30  add     rsp, 1F0h
0x18004eb37  pop     rsi
0x18004eb38  retn
```
