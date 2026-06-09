# p9fs::Plan9VirtioDevice::CreateDevice(std::shared_ptr<p9fs::Plan9DeviceHost>,std::unique_ptr<p9fs::IHandler,std::default_delete<p9fs::IHandler>> &&,std::basic_string_view<char,std::char_traits<char>>,_GUID *)

- ea: `0x18002d9ac`
- end: `0x18002db2c`
- name: `?CreateDevice@Plan9VirtioDevice@p9fs@@SA?AV?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@V?$shared_ptr@VPlan9DeviceHost@p9fs@@@std@@$$QEAV?$unique_ptr@VIHandler@p9fs@@U?$default_delete@VIHandler@p9fs@@@std@@@6@V?$basic_string_view@DU?$char_traits@D@std@@@6@PEAU_GUID@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(int, int, int, int, GUID *deviceInstanceId)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002d76c`

## callees

- `0x180004120`
- `0x18001c75c`
- `0x18002cb94`
- `0x18002d9ac`
- `0x18002e4d0`
- `0x18002e920`
- `0x180034010`

## import_xrefs

- `vmdevicehost!HdvCreateDeviceInstance` at `0x18002da77`
- `vmdevicehost!HdvCreateDeviceInstance` at `0x18002da77`

## string_xrefs

- `0x18002db05`: `onecore\vm\dv\storage\plan9\dll\windows\p9virtio.cpp`
- `0x18002db1a`: `onecore\vm\dv\storage\plan9\dll\windows\p9virtio.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall p9fs::Plan9VirtioDevice::CreateDevice(
        _QWORD *a1,
        HDV_HOST **a2,
        int a3,
        int a4,
        GUID *deviceInstanceId)
{
  GUID *p_deviceClassId; // rsi
  int Interface; // eax
  HRESULT v9; // eax
  volatile signed __int32 *v10; // rbx
  int deviceInterface; // [rsp+20h] [rbp-31h]
  int deviceInterfacea; // [rsp+20h] [rbp-31h]
  void *deviceContext; // [rsp+40h] [rbp-11h] BYREF
  int v15; // [rsp+48h] [rbp-9h]
  _QWORD *v16; // [rsp+50h] [rbp-1h]
  HDV_DEVICE deviceHandle[2]; // [rsp+58h] [rbp+7h] BYREF
  GUID deviceClassId; // [rsp+68h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+57h]

  v16 = a1;
  deviceHandle[1] = a2;
  v15 = 0;
  deviceClassId = GUID_fc36c5c6_7a87_4841_a47a_1d352987055b;
  p_deviceClassId = &deviceClassId;
  if ( deviceInstanceId )
    p_deviceClassId = deviceInstanceId;
  deviceContext = 0;
  wil::MakeOrThrow<p9fs::Plan9VirtioDevice,std::shared_ptr<p9fs::Plan9DeviceHost> &,std::unique_ptr<p9fs::IHandler>,std::string_view &,_GUID &>(
    (unsigned int)&deviceContext,
    (_DWORD)a2,
    a3,
    a4,
    (__int64)p_deviceClassId);
  v15 = 1;
  *a1 = 0;
  Interface = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IVmFiovGuestMemoryAccess,IVmFiovGuestMsiAccess,IVmFiovGuestMemoryFastNotification>::QueryInterface(
                deviceContext,
                &GUID_00000000_0000_0000_c000_000000000046,
                a1);
  if ( Interface < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9virtio.cpp",
      (const char *)(unsigned int)Interface,
      deviceInterface);
  deviceHandle[0] = 0;
  v9 = HdvCreateDeviceInstance(
         **a2,
         HdvDeviceTypePCI,
         &deviceClassId,
         p_deviceClassId,
         &p9fs::PciDeviceBase<p9fs::Plan9VirtioDevice>::m_deviceInterface,
         deviceContext,
         deviceHandle);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9virtio.cpp",
      (const char *)(unsigned int)v9,
      deviceInterfacea);
  *((HDV_DEVICE *)deviceContext + 4) = deviceHandle[0];
  if ( deviceContext )
  {
    deviceContext = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IVmFiovGuestMemoryAccess,IVmFiovGuestMsiAccess,IVmFiovGuestMemoryFastNotification>::Release();
  }
  v10 = (volatile signed __int32 *)a2[1];
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002d9ac  push    rbp
0x18002d9ae  push    rbx
0x18002d9af  push    rsi
0x18002d9b0  push    rdi
0x18002d9b1  lea     rbp, [rsp-37h]
0x18002d9b6  sub     rsp, 88h
0x18002d9bd  mov     rax, cs:__security_cookie
0x18002d9c4  xor     rax, rsp
0x18002d9c7  mov     [rbp+4Fh+var_28], rax
0x18002d9cb  mov     rbx, rdx
0x18002d9ce  mov     rdi, rcx
0x18002d9d1  mov     rax, [rbp+4Fh+deviceInstanceId]
0x18002d9d5  mov     [rbp+4Fh+var_50], rcx
0x18002d9d9  mov     [rbp+4Fh+var_40], rdx
0x18002d9dd  mov     [rbp+4Fh+var_58], 0
0x18002d9e4  movups  xmm0, xmmword ptr cs:_GUID_fc36c5c6_7a87_4841_a47a_1d352987055b.Data1
0x18002d9eb  movdqu  xmmword ptr [rbp+4Fh+deviceClassId.Data1], xmm0
0x18002d9f0  lea     rsi, [rbp+4Fh+deviceClassId]
0x18002d9f4  test    rax, rax
0x18002d9f7  cmovnz  rsi, rax
0x18002d9fb  mov     [rbp+4Fh+var_60], 0
0x18002da03  mov     [rsp+0A0h+deviceInterface], rsi; int
0x18002da08  lea     rcx, [rbp+4Fh+var_60]
0x18002da0c  call    ??$MakeOrThrow@VPlan9VirtioDevice@p9fs@@AEAV?$shared_ptr@VPlan9DeviceHost@p9fs@@@std@@V?$unique_ptr@VIHandler@p9fs@@U?$default_delete@VIHandler@p9fs@@@std@@@4@AEAV?$basic_string_view@DU?$char_traits@D@std@@@4@AEAU_GUID@@@wil@@YA?AV?$ComPtr@VPlan9VirtioDevice@p9fs@@@WRL@Microsoft@@AEAV?$shared_ptr@VPlan9DeviceHost@p9fs@@@std@@$$QEAV?$unique_ptr@VIHandler@p9fs@@U?$default_delete@VIHandler@p9fs@@@std@@@5@AEAV?$basic_string_view@DU?$char_traits@D@std@@@5@AEAU_GUID@@@Z; wil::MakeOrThrow<p9fs::Plan9VirtioDevice,std::shared_ptr<p9fs::Plan9DeviceHost> &,std::unique_ptr<p9fs::IHandler>,std::string_view &,_GUID &>(std::shared_ptr<p9fs::Plan9DeviceHost> &,std::unique_ptr<p9fs::IHandler> &&,std::string_view &,_GUID &)
0x18002da11  nop
0x18002da12  mov     [rbp+4Fh+var_58], 1
0x18002da19  mov     qword ptr [rdi], 0
0x18002da20  mov     r8, rdi
0x18002da23  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18002da2a  mov     rcx, [rbp+4Fh+var_60]
0x18002da2e  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIVmFiovGuestMemoryAccess@@UIVmFiovGuestMsiAccess@@UIVmFiovGuestMemoryFastNotification@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IVmFiovGuestMemoryAccess,IVmFiovGuestMsiAccess,IVmFiovGuestMemoryFastNotification>::QueryInterface(_GUID const &,void * *)
0x18002da33  mov     rcx, [rbp+57h]; this
0x18002da37  test    eax, eax
0x18002da39  js      loc_18002DB17
0x18002da3f  mov     [rbp+4Fh+var_48], 0
0x18002da47  mov     rax, [rbp+4Fh+var_60]
0x18002da4b  mov     rcx, [rbx]
0x18002da4e  lea     r8, [rbp+4Fh+var_48]
0x18002da52  mov     [rsp+0A0h+deviceHandle], r8; deviceHandle
0x18002da57  mov     [rsp+0A0h+deviceContext], rax; deviceContext
0x18002da5c  lea     rax, ?m_deviceInterface@?$PciDeviceBase@VPlan9VirtioDevice@p9fs@@@p9fs@@0UHDV_PCI_DEVICE_INTERFACE@@B; HDV_PCI_DEVICE_INTERFACE const p9fs::PciDeviceBase<p9fs::Plan9VirtioDevice>::m_deviceInterface
0x18002da63  mov     [rsp+0A0h+deviceInterface], rax; int
0x18002da68  mov     r9, rsi; deviceInstanceId
0x18002da6b  lea     r8, [rbp+4Fh+deviceClassId]; deviceClassId
0x18002da6f  mov     edx, 1; deviceType
0x18002da74  mov     rcx, [rcx]; deviceHostHandle
0x18002da77  call    cs:__imp_HdvCreateDeviceInstance
0x18002da7d  mov     rcx, [rbp+57h]; this
0x18002da81  test    eax, eax
0x18002da83  js      short loc_18002DB02
0x18002da85  mov     rcx, [rbp+4Fh+var_60]
0x18002da89  mov     rax, [rbp+4Fh+var_48]
0x18002da8d  mov     [rcx+20h], rax
0x18002da91  mov     rcx, [rbp+4Fh+var_60]
0x18002da95  test    rcx, rcx
0x18002da98  jz      short loc_18002DAA8
0x18002da9a  mov     [rbp+4Fh+var_60], 0
0x18002daa2  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIVmFiovGuestMemoryAccess@@UIVmFiovGuestMsiAccess@@UIVmFiovGuestMemoryFastNotification@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IVmFiovGuestMemoryAccess,IVmFiovGuestMsiAccess,IVmFiovGuestMemoryFastNotification>::Release(void)
0x18002daa7  nop
0x18002daa8  mov     rbx, [rbx+8]
0x18002daac  test    rbx, rbx
0x18002daaf  jz      short loc_18002DAE7
0x18002dab1  or      esi, 0FFFFFFFFh
0x18002dab4  mov     eax, esi
0x18002dab6  lock xadd [rbx+8], eax
0x18002dabb  add     eax, esi
0x18002dabd  jnz     short loc_18002DAE7
0x18002dabf  mov     rax, [rbx]
0x18002dac2  mov     rcx, rbx
0x18002dac5  mov     rax, [rax]
0x18002dac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dacd  mov     edx, esi
0x18002dacf  lock xadd [rbx+0Ch], edx
0x18002dad4  add     edx, esi
0x18002dad6  jnz     short loc_18002DAE7
0x18002dad8  mov     rdx, [rbx]
0x18002dadb  mov     rcx, rbx
0x18002dade  mov     rax, [rdx+8]
0x18002dae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dae7  mov     rax, rdi
0x18002daea  mov     rcx, [rbp+4Fh+var_28]
0x18002daee  xor     rcx, rsp; StackCookie
0x18002daf1  call    __security_check_cookie
0x18002daf6  add     rsp, 88h
0x18002dafd  pop     rdi
0x18002dafe  pop     rsi
0x18002daff  pop     rbx
0x18002db00  pop     rbp
0x18002db01  retn
0x18002db02  mov     r9d, eax; char *
0x18002db05  lea     r8, aOnecoreVmDvSto_0; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002db0c  mov     edx, 50h ; 'P'; void *
0x18002db11  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002db17  mov     r9d, eax; char *
0x18002db1a  lea     r8, aOnecoreVmDvSto_0; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002db21  mov     edx, 4Ch ; 'L'; void *
0x18002db26  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
