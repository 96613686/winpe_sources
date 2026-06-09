# CRunningShareManager::~CRunningShareManager(void)

- ea: `0x1800141e0`
- end: `0x1800143ac`
- name: `??1CRunningShareManager@@EEAA@XZ`
- size: `460`
- prototype: `void __fastcall(CRunningShareManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800627f8`

## callees

- `0x1800141e0`
- `0x180020d20`
- `0x180062834`
- `0x180062860`
- `0x1800656b8`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014336`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014369`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014336`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014369`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRunningShareManager::~CRunningShareManager(CRunningShareManager *this, unsigned int a2)
{
  unsigned __int64 v3; // rsi
  __int64 i; // rdi
  RUNNING_SHARE_SINK *v5; // rcx
  unsigned __int64 v6; // rsi
  __int64 j; // rdi
  RUNNING_SHARE_ENTRY *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  void *v12; // rcx
  void *v13; // rcx

  *(_QWORD *)this = &CRunningShareManager::`vftable'{for `IRunningShareManager'};
  *((_QWORD *)this + 1) = &CRunningShareManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IImmersiveApplicationNotification,CImmersiveShellComponentWithGITSite,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &CRunningShareManager::`vftable'{for `Microsoft::WRL::Details::Selector<CImmersiveShellComponentWithGITSite,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 7) = &CRunningShareManager::`vftable'{for `IImmersiveShellComponent'};
  *((_QWORD *)this + 8) = &CRunningShareManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IServiceProvider>'};
  *((_QWORD *)this + 15) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRunningShareManager,IImmersiveApplicationNotification,CImmersiveShellComponentWithGITSite,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,Microsoft::WRL::FtmBase>>'};
  v3 = *((_QWORD *)this + 22);
  for ( i = 0; (unsigned int)i < v3; i = (unsigned int)(i + 1) )
  {
    v5 = *(RUNNING_SHARE_SINK **)(*((_QWORD *)this + 21) + 8 * i);
    if ( v5 )
      RUNNING_SHARE_SINK::`scalar deleting destructor'(v5, a2);
  }
  v6 = *((_QWORD *)this + 26);
  for ( j = 0; (unsigned int)j < v6; j = (unsigned int)(j + 1) )
  {
    v8 = *(RUNNING_SHARE_ENTRY **)(*((_QWORD *)this + 25) + 8 * j);
    if ( v8 )
      RUNNING_SHARE_ENTRY::`scalar deleting destructor'(v8, a2);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_371d9ea80e6f358a8b76d1652c28dcea_Traceguids, this);
  }
  v9 = *((_QWORD *)this + 33);
  if ( v9 )
  {
    *((_QWORD *)this + 33) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v10 = *((_QWORD *)this + 32);
  if ( v10 )
  {
    *((_QWORD *)this + 32) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = *((_QWORD *)this + 31);
  if ( v11 )
  {
    *((_QWORD *)this + 31) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v12 = (void *)*((_QWORD *)this + 25);
  if ( v12 )
  {
    CoTaskMemFree(v12);
    *((_QWORD *)this + 25) = 0;
  }
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 28) = 0;
  v13 = (void *)*((_QWORD *)this + 21);
  if ( v13 )
  {
    CoTaskMemFree(v13);
    *((_QWORD *)this + 21) = 0;
  }
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_DWORD *)this + 39) = -1073741823;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,Microsoft::WRL::FtmBase>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,Microsoft::WRL::FtmBase>((CRunningShareManager *)((char *)this + 16));
}

```

## disassembly

```asm
0x1800141e0  push    rbx
0x1800141e2  push    rsi
0x1800141e3  push    rdi
0x1800141e4  push    r14
0x1800141e6  sub     rsp, 28h
0x1800141ea  mov     rbx, rcx
0x1800141ed  lea     rax, ??_7CRunningShareManager@@6BIRunningShareManager@@@; const CRunningShareManager::`vftable'{for `IRunningShareManager'}
0x1800141f4  mov     [rcx], rax
0x1800141f7  lea     rax, ??_7CRunningShareManager@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIImmersiveApplicationNotification@@VCImmersiveShellComponentWithGITSite@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CRunningShareManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IImmersiveApplicationNotification,CImmersiveShellComponentWithGITSite,Microsoft::WRL::FtmBase>'}
0x1800141fe  mov     [rcx+8], rax
0x180014202  lea     rax, ??_7CRunningShareManager@@6B?$Selector@VCImmersiveShellComponentWithGITSite@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VCImmersiveShellComponentWithGITSite@@@Details@23@VFtmBase@23@@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@@; const CRunningShareManager::`vftable'{for `Microsoft::WRL::Details::Selector<CImmersiveShellComponentWithGITSite,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,Microsoft::WRL::FtmBase>>'}
0x180014209  mov     [rcx+10h], rax
0x18001420d  lea     rax, ??_7CRunningShareManager@@6BIImmersiveShellComponent@@@; const CRunningShareManager::`vftable'{for `IImmersiveShellComponent'}
0x180014214  mov     [rcx+38h], rax
0x180014218  lea     rax, ??_7CRunningShareManager@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIServiceProvider@@@Details@WRL@Microsoft@@@; const CRunningShareManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IServiceProvider>'}
0x18001421f  mov     [rcx+40h], rax
0x180014223  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIRunningShareManager@@UIImmersiveApplicationNotification@@VCImmersiveShellComponentWithGITSite@@VFtmBase@23@@WRL@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VCImmersiveShellComponentWithGITSite@@@Details@23@VFtmBase@23@@234@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRunningShareManager,IImmersiveApplicationNotification,CImmersiveShellComponentWithGITSite,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,Microsoft::WRL::FtmBase>>'}
0x18001422a  mov     [rcx+78h], rax
0x18001422e  mov     rsi, [rcx+0B0h]
0x180014235  xor     edi, edi
0x180014237  test    rsi, rsi
0x18001423a  jz      short loc_18001425A
0x18001423c  mov     rax, [rbx+0A8h]
0x180014243  mov     rcx, [rax+rdi*8]; this
0x180014247  test    rcx, rcx
0x18001424a  jz      short loc_180014251
0x18001424c  call    ??_GRUNNING_SHARE_SINK@@QEAAPEAXI@Z; RUNNING_SHARE_SINK::`scalar deleting destructor'(uint)
0x180014251  inc     edi
0x180014253  mov     eax, edi
0x180014255  cmp     rax, rsi
0x180014258  jb      short loc_18001423C
0x18001425a  mov     rsi, [rbx+0D0h]
0x180014261  xor     edi, edi
0x180014263  test    rsi, rsi
0x180014266  jz      short loc_180014286
0x180014268  mov     rax, [rbx+0C8h]
0x18001426f  mov     rcx, [rax+rdi*8]; this
0x180014273  test    rcx, rcx
0x180014276  jz      short loc_18001427D
0x180014278  call    ??_GRUNNING_SHARE_ENTRY@@QEAAPEAXI@Z; RUNNING_SHARE_ENTRY::`scalar deleting destructor'(uint)
0x18001427d  inc     edi
0x18001427f  mov     eax, edi
0x180014281  cmp     rax, rsi
0x180014284  jb      short loc_180014268
0x180014286  lea     rax, WPP_GLOBAL_Control
0x18001428d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014294  cmp     rcx, rax
0x180014297  jz      short loc_1800142BE
0x180014299  test    byte ptr [rcx+44h], 1
0x18001429d  jz      short loc_1800142BE
0x18001429f  cmp     byte ptr [rcx+41h], 4
0x1800142a3  jb      short loc_1800142BE
0x1800142a5  mov     edx, 0Bh
0x1800142aa  mov     r9, rbx
0x1800142ad  lea     r8, WPP_371d9ea80e6f358a8b76d1652c28dcea_Traceguids
0x1800142b4  mov     rcx, [rcx+38h]
0x1800142b8  call    WPP_SF_q
0x1800142bd  nop
0x1800142be  mov     rcx, [rbx+108h]
0x1800142c5  test    rcx, rcx
0x1800142c8  jz      short loc_1800142E2
0x1800142ca  mov     qword ptr [rbx+108h], 0
0x1800142d5  mov     rax, [rcx]
0x1800142d8  mov     rax, [rax+10h]
0x1800142dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142e1  nop
0x1800142e2  mov     rcx, [rbx+100h]
0x1800142e9  test    rcx, rcx
0x1800142ec  jz      short loc_180014306
0x1800142ee  mov     qword ptr [rbx+100h], 0
0x1800142f9  mov     rax, [rcx]
0x1800142fc  mov     rax, [rax+10h]
0x180014300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014305  nop
0x180014306  mov     rcx, [rbx+0F8h]
0x18001430d  test    rcx, rcx
0x180014310  jz      short loc_18001432A
0x180014312  mov     qword ptr [rbx+0F8h], 0
0x18001431d  mov     rax, [rcx]
0x180014320  mov     rax, [rax+10h]
0x180014324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014329  nop
0x18001432a  mov     rcx, [rbx+0C8h]; pv
0x180014331  test    rcx, rcx
0x180014334  jz      short loc_180014347
0x180014336  call    cs:__imp_CoTaskMemFree
0x18001433c  mov     qword ptr [rbx+0C8h], 0
0x180014347  mov     qword ptr [rbx+0D0h], 0
0x180014352  mov     qword ptr [rbx+0E0h], 0
0x18001435d  mov     rcx, [rbx+0A8h]; pv
0x180014364  test    rcx, rcx
0x180014367  jz      short loc_18001437A
0x180014369  call    cs:__imp_CoTaskMemFree
0x18001436f  mov     qword ptr [rbx+0A8h], 0
0x18001437a  mov     qword ptr [rbx+0B0h], 0
0x180014385  mov     qword ptr [rbx+0C0h], 0
0x180014390  mov     dword ptr [rbx+9Ch], 0C0000001h
0x18001439a  lea     rcx, [rbx+10h]; this
0x18001439e  add     rsp, 28h
0x1800143a2  pop     r14
0x1800143a4  pop     rdi
0x1800143a5  pop     rsi
0x1800143a6  pop     rbx
0x1800143a7  jmp     ??1?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VCImmersiveShellComponentWithGITSite@@@Details@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,Microsoft::WRL::FtmBase>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,Microsoft::WRL::FtmBase>(void)
```
