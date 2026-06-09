# NotificationHandler::`vector deleting destructor'(uint)

- ea: `0x18000faf0`
- end: `0x18000fc2e`
- name: `??_ENotificationHandler@@UEAAPEAXI@Z`
- size: `318`
- prototype: `void *__fastcall(NotificationHandler *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004e38`
- `0x18000faf0`
- `0x1800b9ecc`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fbe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fbe6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
NotificationHandler *__fastcall NotificationHandler::`vector deleting destructor'(NotificationHandler *this, char a2)
{
  NotificationHandler v4; // rcx
  NotificationHandler v5; // rcx
  NotificationHandler v6; // rcx
  NotificationHandler v7; // rcx
  NotificationHandler v8; // rcx
  NotificationHandler v9; // rcx

  *this = (NotificationHandler)&NotificationHandler::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,INotificationHandler>>'};
  this[4] = (NotificationHandler)&NotificationHandler::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,INotificationHandler>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,INotificationHandler>>'};
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 26);
  v4 = this[22];
  if ( v4 )
  {
    CoTaskMemFree(v4);
    this[22] = 0;
  }
  this[23] = 0;
  this[24] = 0;
  v5 = this[18];
  if ( v5 )
  {
    CoTaskMemFree(v5);
    this[18] = 0;
  }
  this[19] = 0;
  this[20] = 0;
  v6 = this[15];
  if ( v6 )
  {
    CoTaskMemFree(v6);
    this[15] = 0;
  }
  this[16] = 0;
  this[17] = 0;
  v7 = this[12];
  if ( v7 )
  {
    CoTaskMemFree(v7);
    this[12] = 0;
  }
  this[13] = 0;
  this[14] = 0;
  v8 = this[11];
  if ( v8 )
  {
    this[11] = 0;
    (*(void (__fastcall **)(NotificationHandler))(*(_QWORD *)v8 + 16LL))(v8);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 10);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 9);
  v9 = this[6];
  if ( v9 )
  {
    CoTaskMemFree(v9);
    this[6] = 0;
  }
  this[7] = 0;
  this[8] = 0;
  *((_DWORD *)this + 11) = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 3);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000faf0  mov     [rsp+arg_0], rbx
0x18000faf5  mov     [rsp+arg_8], rsi
0x18000fafa  push    rdi
0x18000fafb  sub     rsp, 20h
0x18000faff  mov     edi, edx
0x18000fb01  mov     rbx, rcx
0x18000fb04  lea     rax, ??_7NotificationHandler@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UINotificationHandler@@@Details@23@@Details@WRL@Microsoft@@@; const NotificationHandler::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,INotificationHandler>>'}
0x18000fb0b  mov     [rcx], rax
0x18000fb0e  lea     rax, ??_7NotificationHandler@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UINotificationHandler@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UINotificationHandler@@@234@@Details@WRL@Microsoft@@@; const NotificationHandler::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,INotificationHandler>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,INotificationHandler>>'}
0x18000fb15  mov     [rcx+20h], rax
0x18000fb19  add     rcx, 0D0h
0x18000fb20  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fb25  mov     rcx, [rbx+0B0h]; pv
0x18000fb2c  xor     esi, esi
0x18000fb2e  test    rcx, rcx
0x18000fb31  jz      short loc_18000FB40
0x18000fb33  call    cs:__imp_CoTaskMemFree
0x18000fb39  mov     [rbx+0B0h], rsi
0x18000fb40  mov     [rbx+0B8h], rsi
0x18000fb47  mov     [rbx+0C0h], rsi
0x18000fb4e  mov     rcx, [rbx+90h]; pv
0x18000fb55  test    rcx, rcx
0x18000fb58  jz      short loc_18000FB67
0x18000fb5a  call    cs:__imp_CoTaskMemFree
0x18000fb60  mov     [rbx+90h], rsi
0x18000fb67  mov     [rbx+98h], rsi
0x18000fb6e  mov     [rbx+0A0h], rsi
0x18000fb75  mov     rcx, [rbx+78h]; pv
0x18000fb79  test    rcx, rcx
0x18000fb7c  jz      short loc_18000FB88
0x18000fb7e  call    cs:__imp_CoTaskMemFree
0x18000fb84  mov     [rbx+78h], rsi
0x18000fb88  mov     [rbx+80h], rsi
0x18000fb8f  mov     [rbx+88h], rsi
0x18000fb96  mov     rcx, [rbx+60h]; pv
0x18000fb9a  test    rcx, rcx
0x18000fb9d  jz      short loc_18000FBA9
0x18000fb9f  call    cs:__imp_CoTaskMemFree
0x18000fba5  mov     [rbx+60h], rsi
0x18000fba9  mov     [rbx+68h], rsi
0x18000fbad  mov     [rbx+70h], rsi
0x18000fbb1  mov     rcx, [rbx+58h]
0x18000fbb5  test    rcx, rcx
0x18000fbb8  jz      short loc_18000FBCB
0x18000fbba  mov     [rbx+58h], rsi
0x18000fbbe  mov     rax, [rcx]
0x18000fbc1  mov     rax, [rax+10h]
0x18000fbc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbca  nop
0x18000fbcb  lea     rcx, [rbx+50h]
0x18000fbcf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fbd4  lea     rcx, [rbx+48h]
0x18000fbd8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fbdd  mov     rcx, [rbx+30h]; pv
0x18000fbe1  test    rcx, rcx
0x18000fbe4  jz      short loc_18000FBF0
0x18000fbe6  call    cs:__imp_CoTaskMemFree
0x18000fbec  mov     [rbx+30h], rsi
0x18000fbf0  mov     [rbx+38h], rsi
0x18000fbf4  mov     [rbx+40h], rsi
0x18000fbf8  mov     dword ptr [rbx+2Ch], 0C0000001h
0x18000fbff  lea     rcx, [rbx+18h]
0x18000fc03  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fc08  test    dil, 1
0x18000fc0c  jz      short loc_18000FC1B
0x18000fc0e  mov     edx, 0E0h
0x18000fc13  mov     rcx, rbx; Block
0x18000fc16  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000fc1b  mov     rax, rbx
0x18000fc1e  mov     rbx, [rsp+28h+arg_0]
0x18000fc23  mov     rsi, [rsp+28h+arg_8]
0x18000fc28  add     rsp, 20h
0x18000fc2c  pop     rdi
0x18000fc2d  retn
```
