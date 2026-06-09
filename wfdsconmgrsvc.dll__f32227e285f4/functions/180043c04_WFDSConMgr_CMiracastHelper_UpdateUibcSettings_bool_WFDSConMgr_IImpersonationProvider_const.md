# WFDSConMgr::CMiracastHelper::UpdateUibcSettings(bool,WFDSConMgr::IImpersonationProvider const &)

- ea: `0x180043c04`
- end: `0x180043e4d`
- name: `?UpdateUibcSettings@CMiracastHelper@WFDSConMgr@@QEAAX_NAEBVIImpersonationProvider@2@@Z`
- size: `585`
- prototype: `void __fastcall(WFDSConMgr::CMiracastHelper *__hidden this, bool, const struct WFDSConMgr::IImpersonationProvider *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x180056790`

## callees

- `0x180004f38`
- `0x1800059c0`
- `0x18000665c`
- `0x180006740`
- `0x180028b60`
- `0x1800296f0`
- `0x180043c04`
- `0x18005c888`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043d24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043dd4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043d24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043dd4`

## string_xrefs

- `0x180043cd4`: `WFDSConMgr::CMiracastHelper::UpdateUibcSettings`
- `0x180043d9c`: `WFDSConMgr::CMiracastHelper::UpdateUibcSettings`
- `0x180043e0b`: `WFDSConMgr::CMiracastHelper::UpdateUibcSettings`
- `0x180043e3b`: `WFDSConMgr::CMiracastHelper::UpdateUibcSettings`
- `0x180043e22`: `Attempt to set UIBC settings from bad state`
- `0x180043df2`: `Attempt to set UIBC settings but not allowed`
- `0x180043d83`: `UpdateMiracastDisplayDeviceUibcSettings failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WFDSConMgr::CMiracastHelper::UpdateUibcSettings(
        void **this,
        char a2,
        const struct WFDSConMgr::IImpersonationProvider *a3)
{
  PVOID *v5; // r10
  __int64 v6; // rax
  __int64 v7; // r10
  char v8; // r9
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // eax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp+8h] BYREF
  char v14; // [rsp+58h] [rbp+10h] BYREF
  __int64 v15; // [rsp+68h] [rbp+20h] BYREF

  v14 = a2;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids, this);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && *((_BYTE *)v5 + 25) >= 4u && (*((_BYTE *)v5 + 28) & 1) != 0 )
    {
      v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this + 20);
      WPP_SF_qSD(
        *(_QWORD *)(v7 + 16),
        27,
        (unsigned int)&WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids,
        (_DWORD)this,
        v6,
        v8);
    }
  }
  WFDSConMgr::CriticalSection::Lock(this + 13, &lpCriticalSection);
  if ( *((_BYTE *)this + 144) )
    WFDSConMgr::CException::Throw(
      199,
      "WFDSConMgr::CMiracastHelper::UpdateUibcSettings",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\miracasthelper.cpp",
      125,
      L"Operation was canceled before starting",
      this);
  if ( !*((_BYTE *)this + 257) || *((_BYTE *)this + 258) )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CMiracastHelper::UpdateUibcSettings",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\miracasthelper.cpp",
      129,
      L"Attempt to set UIBC settings from bad state",
      this);
  if ( !*((_BYTE *)this + 285) || *((_BYTE *)this + 288) )
    WFDSConMgr::CException::Throw(
      50,
      "WFDSConMgr::CMiracastHelper::UpdateUibcSettings",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\miracasthelper.cpp",
      134,
      L"Attempt to set UIBC settings but not allowed",
      this);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  (*(void (__fastcall **)(const struct WFDSConMgr::IImpersonationProvider *, __int64 *))(*(_QWORD *)a3 + 8LL))(a3, &v15);
  WFDSConMgr::CDevQueryHelper::SetMiracastDisplayDeviceUibc(this[9]);
  v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this + 24);
  v12 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(v10 + 40))(v11, v9, &v14);
  if ( v12 < 0 )
    WFDSConMgr::CException::Throw(
      v12,
      "WFDSConMgr::CMiracastHelper::UpdateUibcSettings",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\miracasthelper.cpp",
      145,
      L"UpdateMiracastDisplayDeviceUibcSettings failed",
      this);
  WFDSConMgr::CriticalSection::Lock(this + 13, &lpCriticalSection);
  *((_BYTE *)this + 286) = 1;
  *((_BYTE *)this + 287) = v14;
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(&v15);
}

```

## disassembly

```asm
0x180043c04  mov     [rsp+arg_8], dl
0x180043c08  push    rbx
0x180043c09  push    rsi
0x180043c0a  push    rdi
0x180043c0b  sub     rsp, 30h
0x180043c0f  mov     rbx, r8
0x180043c12  mov     rdi, rcx
0x180043c15  lea     rsi, WPP_GLOBAL_Control
0x180043c1c  mov     r10, cs:WPP_GLOBAL_Control
0x180043c23  cmp     r10, rsi
0x180043c26  jz      short loc_180043C9E
0x180043c28  cmp     byte ptr [r10+19h], 4
0x180043c2d  jb      short loc_180043C59
0x180043c2f  test    byte ptr [r10+1Ch], 1
0x180043c34  jz      short loc_180043C59
0x180043c36  mov     edx, 1Ah
0x180043c3b  mov     r9, rcx
0x180043c3e  lea     r8, WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids
0x180043c45  mov     rcx, [r10+10h]
0x180043c49  call    WPP_SF_q
0x180043c4e  mov     dl, [rsp+48h+arg_8]
0x180043c52  mov     r10, cs:WPP_GLOBAL_Control
0x180043c59  cmp     r10, rsi
0x180043c5c  jz      short loc_180043C9E
0x180043c5e  cmp     byte ptr [r10+19h], 4
0x180043c63  jb      short loc_180043C9E
0x180043c65  test    byte ptr [r10+1Ch], 1
0x180043c6a  jz      short loc_180043C9E
0x180043c6c  movzx   r9d, dl
0x180043c70  lea     rcx, [rdi+0A0h]
0x180043c77  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043c7c  mov     edx, 1Bh
0x180043c81  mov     dword ptr [rsp+48h+var_20], r9d
0x180043c86  mov     [rsp+48h+var_28], rax
0x180043c8b  mov     r9, rdi
0x180043c8e  lea     r8, WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids
0x180043c95  mov     rcx, [r10+10h]
0x180043c99  call    WPP_SF_qSD
0x180043c9e  lea     rdx, [rsp+48h+lpCriticalSection]
0x180043ca3  lea     rcx, [rdi+68h]
0x180043ca7  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x180043cac  nop
0x180043cad  cmp     byte ptr [rdi+90h], 0
0x180043cb4  jz      short loc_180043CE6
0x180043cb6  mov     [rsp+48h+var_20], rdi; void *
0x180043cbb  lea     rax, aOperationWasCa; "Operation was canceled before starting"
0x180043cc2  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180043cc7  mov     r9d, 17Dh; char
0x180043ccd  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180043cd4  lea     rdx, aWfdsconmgrCmir_0; "WFDSConMgr::CMiracastHelper::UpdateUibc"...
0x180043cdb  mov     ecx, 800704C7h; char
0x180043ce0  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180043ce6  cmp     byte ptr [rdi+101h], 0
0x180043ced  jz      loc_180043E1D
0x180043cf3  cmp     byte ptr [rdi+102h], 0
0x180043cfa  jnz     loc_180043E1D
0x180043d00  cmp     byte ptr [rdi+11Dh], 0
0x180043d07  jz      loc_180043DED
0x180043d0d  cmp     byte ptr [rdi+120h], 0
0x180043d14  jnz     loc_180043DED
0x180043d1a  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x180043d1f  test    rcx, rcx
0x180043d22  jz      short loc_180043D2A
0x180043d24  call    cs:__imp_LeaveCriticalSection
0x180043d2a  mov     rax, [rbx]
0x180043d2d  lea     rdx, [rsp+48h+arg_18]
0x180043d32  mov     rcx, rbx
0x180043d35  mov     rax, [rax+8]
0x180043d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d3e  nop
0x180043d3f  lea     rbx, [rdi+0C0h]
0x180043d46  mov     r8b, [rsp+48h+arg_8]
0x180043d4b  mov     rdx, rbx
0x180043d4e  mov     rcx, [rdi+48h]; void *
0x180043d52  call    ?SetMiracastDisplayDeviceUibc@CDevQueryHelper@WFDSConMgr@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; WFDSConMgr::CDevQueryHelper::SetMiracastDisplayDeviceUibc(std::wstring const &,bool)
0x180043d57  mov     r9, [rdi+18h]
0x180043d5b  mov     r8, [r9]
0x180043d5e  mov     rcx, rbx
0x180043d61  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043d66  mov     rdx, rax
0x180043d69  mov     rax, [r8+28h]
0x180043d6d  lea     r8, [rsp+48h+arg_8]
0x180043d72  mov     rcx, r9
0x180043d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d7a  test    eax, eax
0x180043d7c  jns     short loc_180043DAB
0x180043d7e  mov     [rsp+48h+var_20], rdi; void *
0x180043d83  lea     rcx, aUpdatemiracast; "UpdateMiracastDisplayDeviceUibcSettings"...
0x180043d8a  mov     [rsp+48h+var_28], rcx; unsigned __int16 *
0x180043d8f  mov     r9d, 191h; char
0x180043d95  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180043d9c  lea     rdx, aWfdsconmgrCmir_0; "WFDSConMgr::CMiracastHelper::UpdateUibc"...
0x180043da3  mov     ecx, eax; char
0x180043da5  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180043dab  lea     rdx, [rsp+48h+lpCriticalSection]
0x180043db0  lea     rcx, [rdi+68h]
0x180043db4  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x180043db9  mov     byte ptr [rdi+11Eh], 1
0x180043dc0  mov     al, [rsp+48h+arg_8]
0x180043dc4  mov     [rdi+11Fh], al
0x180043dca  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x180043dcf  test    rcx, rcx
0x180043dd2  jz      short loc_180043DDB
0x180043dd4  call    cs:__imp_LeaveCriticalSection
0x180043dda  nop
0x180043ddb  lea     rcx, [rsp+48h+arg_18]
0x180043de0  call    ??1?$unique_ptr@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@U?$default_delete@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(void)
0x180043de5  add     rsp, 30h
0x180043de9  pop     rdi
0x180043dea  pop     rsi
0x180043deb  pop     rbx
0x180043dec  retn
0x180043ded  mov     [rsp+48h+var_20], rdi; void *
0x180043df2  lea     rax, aAttemptToSetUi; "Attempt to set UIBC settings but not al"...
0x180043df9  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180043dfe  mov     r9d, 186h; char
0x180043e04  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180043e0b  lea     rdx, aWfdsconmgrCmir_0; "WFDSConMgr::CMiracastHelper::UpdateUibc"...
0x180043e12  mov     ecx, 80070032h; char
0x180043e17  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180043e1d  mov     [rsp+48h+var_20], rdi; void *
0x180043e22  lea     rax, aAttemptToSetUi_0; "Attempt to set UIBC settings from bad s"...
0x180043e29  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180043e2e  mov     r9d, 181h; char
0x180043e34  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180043e3b  lea     rdx, aWfdsconmgrCmir_0; "WFDSConMgr::CMiracastHelper::UpdateUibc"...
0x180043e42  mov     ecx, 8007139Fh; char
0x180043e47  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
```
