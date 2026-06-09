# winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream::Initialize(APXSTREAM_INIT__ *,APXCIRCUIT__ *)

- ea: `0x1800f713c`
- end: `0x1800f742d`
- name: `?Initialize@VirtualAudioStream@implementation@Devices@Media@WindowsUdk@winrt@@QEAAXPEAUAPXSTREAM_INIT__@@PEAUAPXCIRCUIT__@@@Z`
- size: `753`
- prototype: `void __fastcall(winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream *__hidden this, struct APXSTREAM_INIT__ *, struct APXCIRCUIT__ *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f5860`

## callees

- `0x18000b428`
- `0x180011f98`
- `0x180028978`
- `0x18003b61c`
- `0x1800f5e5c`
- `0x1800f6c24`
- `0x1800f713c`
- `0x1800f7434`
- `0x1800f747c`
- `0x1800f76c0`
- `0x18015cfdc`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800f7414`
- `msvcp_win!_Mtx_unlock` at `0x1800f7414`
- `Apx01000!imp_ApxStreamCreate` at `0x1800f736e`
- `Apx01000!imp_ApxStreamCreate` at `0x1800f736e`
- `Apx01000!imp_ApxStreamInitSetCallbacks` at `0x1800f734b`
- `Apx01000!imp_ApxStreamInitSetCallbacks` at `0x1800f734b`

## string_xrefs

- `0x1800f7378`: `ApxStreamCreate failed`
- `0x1800f7387`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\virtualaudiostream.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream::Initialize(
        winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream *this,
        struct APXSTREAM_INIT__ *a2,
        struct APXCIRCUIT__ *a3)
{
  __int64 v5; // rbx
  __int64 v6; // rbx
  __int64 v7; // rbx
  __int64 v8; // rbx
  unsigned int v9; // eax
  winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStreamOutputImpl *v10; // rbx
  const char *v11; // [rsp+28h] [rbp-58h]
  void (__fastcall *v12)(winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream *__hidden, const struct winrt::WindowsUdk::Media::Devices::implementation::ApxService *, const struct winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs *); // [rsp+30h] [rbp-50h] BYREF
  int v13; // [rsp+38h] [rbp-48h]
  int v14; // [rsp+3Ch] [rbp-44h]
  _BYTE v15[8]; // [rsp+40h] [rbp-40h] BYREF
  std::_Ref_count_base *v16; // [rsp+48h] [rbp-38h]
  _QWORD v17[6]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  char *v19; // [rsp+A0h] [rbp+20h] BYREF
  struct APXSTREAM_INIT__ *v20; // [rsp+A8h] [rbp+28h] BYREF
  __int64 v21; // [rsp+B8h] [rbp+38h] BYREF

  v20 = a2;
  v5 = *(_QWORD *)winrt::WindowsUdk::Media::Devices::implementation::ApxService::GetInstance(v15);
  v12 = winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream::OnPreparingHardware;
  v13 = 0;
  v14 = HIDWORD(v16);
  winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>(
    &v19,
    this,
    &v12);
  winrt::event<winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>>::add(
    v5 + 144,
    &v12,
    &v19);
  *((_QWORD *)this + 29) = v12;
  winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v19);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  v6 = *(_QWORD *)winrt::WindowsUdk::Media::Devices::implementation::ApxService::GetInstance(v15);
  v12 = winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream::OnRunning;
  v13 = 0;
  v14 = HIDWORD(v16);
  winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>(
    &v19,
    this,
    &v12);
  winrt::event<winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>>::add(
    v6 + 192,
    &v12,
    &v19);
  *((_QWORD *)this + 30) = v12;
  winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v19);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  v7 = *(_QWORD *)winrt::WindowsUdk::Media::Devices::implementation::ApxService::GetInstance(v15);
  v12 = winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream::OnPausing;
  v13 = 0;
  v14 = HIDWORD(v16);
  winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>(
    &v19,
    this,
    &v12);
  winrt::event<winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>>::add(
    v7 + 216,
    &v12,
    &v19);
  *((_QWORD *)this + 31) = v12;
  winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v19);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  v8 = *(_QWORD *)winrt::WindowsUdk::Media::Devices::implementation::ApxService::GetInstance(v15);
  v12 = winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream::OnReleasingHardware;
  v13 = 0;
  v14 = HIDWORD(v16);
  winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>(
    &v19,
    this,
    &v12);
  winrt::event<winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>>::add(
    v8 + 168,
    &v12,
    &v19);
  *((_QWORD *)this + 32) = v12;
  winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v19);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  v17[0] = 40;
  v17[1] = winrt::WindowsUdk::Media::Devices::implementation::ApxService::EvtStreamPrepareHardware;
  v17[2] = winrt::WindowsUdk::Media::Devices::implementation::ApxService::EvtStreamReleaseHardware;
  v17[3] = winrt::WindowsUdk::Media::Devices::implementation::ApxService::EvtStreamRun;
  v17[4] = winrt::WindowsUdk::Media::Devices::implementation::ApxService::EvtStreamPause;
  imp_ApxStreamInitSetCallbacks(0, v20, v17);
  v21 = 0;
  v9 = imp_ApxStreamCreate(0, a3, 0, &v20, &v21);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x6D,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualaudiostream.cpp",
    (const char *)v9,
    (int)"ApxStreamCreate failed",
    v11);
  v19 = (char *)this + 136;
  std::_Mutex_base::lock((winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream *)((char *)this + 136));
  *((_QWORD *)this + 27) = v21;
  v10 = (winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStreamOutputImpl *)operator new(0x88u);
  v12 = (void (__fastcall *)(winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream *__hidden, const struct winrt::WindowsUdk::Media::Devices::implementation::ApxService *, const struct winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs *))v10;
  winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStreamOutputImpl::VirtualAudioStreamOutputImpl(
    v10,
    *((struct APXSTREAM__ **)this + 27),
    *((_BYTE *)this + 224),
    *((_BYTE *)this + 225));
  *(_QWORD *)v10 = &winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStreamOutputImpl::`vftable';
  v19 = (char *)v10 + 16;
  winrt::Windows::Foundation::IUnknown::operator=((char *)this + 128, &v19);
  winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v19);
  _Mtx_unlock((winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream *)((char *)this + 136));
}

```

## disassembly

```asm
0x1800f713c  mov     [rsp-18h+arg_10], rbx
0x1800f7141  mov     [rsp-18h+arg_8], rdx
0x1800f7146  push    rbp
0x1800f7147  push    rsi
0x1800f7148  push    rdi
0x1800f7149  mov     rbp, rsp
0x1800f714c  sub     rsp, 80h
0x1800f7153  mov     rdi, r8
0x1800f7156  mov     rsi, rcx
0x1800f7159  lea     rcx, [rbp+var_40]
0x1800f715d  call    ?GetInstance@ApxService@implementation@Devices@Media@WindowsUdk@winrt@@SA?AV?$shared_ptr@VApxService@implementation@Devices@Media@WindowsUdk@winrt@@@std@@XZ; winrt::WindowsUdk::Media::Devices::implementation::ApxService::GetInstance(void)
0x1800f7162  nop
0x1800f7163  mov     rbx, [rax]
0x1800f7166  lea     rax, ?OnPreparingHardware@VirtualAudioStream@implementation@Devices@Media@WindowsUdk@winrt@@AEAAXAEBVApxService@23456@AEBUStreamStateEventArgs@23456@@Z; winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream::OnPreparingHardware(winrt::WindowsUdk::Media::Devices::implementation::ApxService const &,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs const &)
0x1800f716d  mov     [rbp+var_50], rax
0x1800f7171  mov     [rbp+var_48], 0
0x1800f7178  mov     eax, [rbp+var_34]
0x1800f717b  mov     [rbp+var_44], eax
0x1800f717e  lea     r8, [rbp+var_50]
0x1800f7182  mov     rdx, rsi
0x1800f7185  lea     rcx, [rbp+arg_0]
0x1800f7189  call    ??$?0UVirtualAudioStream@implementation@Devices@Media@WindowsUdk@winrt@@P8012345@EAAXAEBVApxService@12345@AEBUStreamStateEventArgs@12345@@Z@?$delegate@VApxService@implementation@Devices@Media@WindowsUdk@winrt@@UStreamStateEventArgs@23456@@winrt@@QEAA@PEAUVirtualAudioStream@implementation@Devices@Media@WindowsUdk@1@P8234561@EAAXAEBVApxService@34561@AEBUStreamStateEventArgs@34561@@Z@Z; winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>(winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream *,void (winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream::*)(winrt::WindowsUdk::Media::Devices::implementation::ApxService const &,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs const &))
0x1800f718e  nop
0x1800f718f  lea     rcx, [rbx+90h]
0x1800f7196  lea     r8, [rbp+arg_0]
0x1800f719a  lea     rdx, [rbp+var_50]
0x1800f719e  call    ?add@?$event@U?$delegate@VApxService@implementation@Devices@Media@WindowsUdk@winrt@@UStreamStateEventArgs@23456@@winrt@@@winrt@@QEAA?AUevent_token@2@AEBU?$delegate@VApxService@implementation@Devices@Media@WindowsUdk@winrt@@UStreamStateEventArgs@23456@@2@@Z; winrt::event<winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>>::add(winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs> const &)
0x1800f71a3  mov     rax, [rbp+var_50]
0x1800f71a7  mov     [rsi+0E8h], rax
0x1800f71ae  lea     rcx, [rbp+arg_0]; this
0x1800f71b2  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1800f71b7  nop
0x1800f71b8  mov     rcx, [rbp-38h]; this
0x1800f71bc  test    rcx, rcx
0x1800f71bf  jz      short loc_1800F71C6
0x1800f71c1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800f71c6  lea     rcx, [rbp+var_40]
0x1800f71ca  call    ?GetInstance@ApxService@implementation@Devices@Media@WindowsUdk@winrt@@SA?AV?$shared_ptr@VApxService@implementation@Devices@Media@WindowsUdk@winrt@@@std@@XZ; winrt::WindowsUdk::Media::Devices::implementation::ApxService::GetInstance(void)
0x1800f71cf  nop
0x1800f71d0  mov     rbx, [rax]
0x1800f71d3  lea     rax, ?OnRunning@VirtualAudioStream@implementation@Devices@Media@WindowsUdk@winrt@@AEAAXAEBVApxService@23456@AEBUStreamStateEventArgs@23456@@Z; winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream::OnRunning(winrt::WindowsUdk::Media::Devices::implementation::ApxService const &,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs const &)
0x1800f71da  mov     [rbp+var_50], rax
0x1800f71de  mov     [rbp+var_48], 0
0x1800f71e5  mov     eax, [rbp+var_34]
0x1800f71e8  mov     [rbp+var_44], eax
0x1800f71eb  lea     r8, [rbp+var_50]
0x1800f71ef  mov     rdx, rsi
0x1800f71f2  lea     rcx, [rbp+arg_0]
0x1800f71f6  call    ??$?0UVirtualAudioStream@implementation@Devices@Media@WindowsUdk@winrt@@P8012345@EAAXAEBVApxService@12345@AEBUStreamStateEventArgs@12345@@Z@?$delegate@VApxService@implementation@Devices@Media@WindowsUdk@winrt@@UStreamStateEventArgs@23456@@winrt@@QEAA@PEAUVirtualAudioStream@implementation@Devices@Media@WindowsUdk@1@P8234561@EAAXAEBVApxService@34561@AEBUStreamStateEventArgs@34561@@Z@Z; winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>(winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream *,void (winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream::*)(winrt::WindowsUdk::Media::Devices::implementation::ApxService const &,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs const &))
0x1800f71fb  nop
0x1800f71fc  lea     rcx, [rbx+0C0h]
0x1800f7203  lea     r8, [rbp+arg_0]
0x1800f7207  lea     rdx, [rbp+var_50]
0x1800f720b  call    ?add@?$event@U?$delegate@VApxService@implementation@Devices@Media@WindowsUdk@winrt@@UStreamStateEventArgs@23456@@winrt@@@winrt@@QEAA?AUevent_token@2@AEBU?$delegate@VApxService@implementation@Devices@Media@WindowsUdk@winrt@@UStreamStateEventArgs@23456@@2@@Z; winrt::event<winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>>::add(winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs> const &)
0x1800f7210  mov     rax, [rbp+var_50]
0x1800f7214  mov     [rsi+0F0h], rax
0x1800f721b  lea     rcx, [rbp+arg_0]; this
0x1800f721f  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1800f7224  nop
0x1800f7225  mov     rcx, [rbp-38h]; this
0x1800f7229  test    rcx, rcx
0x1800f722c  jz      short loc_1800F7233
0x1800f722e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800f7233  lea     rcx, [rbp+var_40]
0x1800f7237  call    ?GetInstance@ApxService@implementation@Devices@Media@WindowsUdk@winrt@@SA?AV?$shared_ptr@VApxService@implementation@Devices@Media@WindowsUdk@winrt@@@std@@XZ; winrt::WindowsUdk::Media::Devices::implementation::ApxService::GetInstance(void)
0x1800f723c  nop
0x1800f723d  mov     rbx, [rax]
0x1800f7240  lea     rax, ?OnPausing@VirtualAudioStream@implementation@Devices@Media@WindowsUdk@winrt@@AEAAXAEBVApxService@23456@AEBUStreamStateEventArgs@23456@@Z; winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream::OnPausing(winrt::WindowsUdk::Media::Devices::implementation::ApxService const &,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs const &)
0x1800f7247  mov     [rbp+var_50], rax
0x1800f724b  mov     [rbp+var_48], 0
0x1800f7252  mov     eax, [rbp+var_34]
0x1800f7255  mov     [rbp+var_44], eax
0x1800f7258  lea     r8, [rbp+var_50]
0x1800f725c  mov     rdx, rsi
0x1800f725f  lea     rcx, [rbp+arg_0]
0x1800f7263  call    ??$?0UVirtualAudioStream@implementation@Devices@Media@WindowsUdk@winrt@@P8012345@EAAXAEBVApxService@12345@AEBUStreamStateEventArgs@12345@@Z@?$delegate@VApxService@implementation@Devices@Media@WindowsUdk@winrt@@UStreamStateEventArgs@23456@@winrt@@QEAA@PEAUVirtualAudioStream@implementation@Devices@Media@WindowsUdk@1@P8234561@EAAXAEBVApxService@34561@AEBUStreamStateEventArgs@34561@@Z@Z; winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>(winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream *,void (winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream::*)(winrt::WindowsUdk::Media::Devices::implementation::ApxService const &,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs const &))
0x1800f7268  nop
0x1800f7269  lea     rcx, [rbx+0D8h]
0x1800f7270  lea     r8, [rbp+arg_0]
0x1800f7274  lea     rdx, [rbp+var_50]
0x1800f7278  call    ?add@?$event@U?$delegate@VApxService@implementation@Devices@Media@WindowsUdk@winrt@@UStreamStateEventArgs@23456@@winrt@@@winrt@@QEAA?AUevent_token@2@AEBU?$delegate@VApxService@implementation@Devices@Media@WindowsUdk@winrt@@UStreamStateEventArgs@23456@@2@@Z; winrt::event<winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>>::add(winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs> const &)
0x1800f727d  mov     rax, [rbp+var_50]
0x1800f7281  mov     [rsi+0F8h], rax
0x1800f7288  lea     rcx, [rbp+arg_0]; this
0x1800f728c  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1800f7291  nop
0x1800f7292  mov     rcx, [rbp-38h]; this
0x1800f7296  test    rcx, rcx
0x1800f7299  jz      short loc_1800F72A0
0x1800f729b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800f72a0  lea     rcx, [rbp+var_40]
0x1800f72a4  call    ?GetInstance@ApxService@implementation@Devices@Media@WindowsUdk@winrt@@SA?AV?$shared_ptr@VApxService@implementation@Devices@Media@WindowsUdk@winrt@@@std@@XZ; winrt::WindowsUdk::Media::Devices::implementation::ApxService::GetInstance(void)
0x1800f72a9  nop
0x1800f72aa  mov     rbx, [rax]
0x1800f72ad  lea     rax, ?OnReleasingHardware@VirtualAudioStream@implementation@Devices@Media@WindowsUdk@winrt@@AEAAXAEBVApxService@23456@AEBUStreamStateEventArgs@23456@@Z; winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream::OnReleasingHardware(winrt::WindowsUdk::Media::Devices::implementation::ApxService const &,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs const &)
0x1800f72b4  mov     [rbp+var_50], rax
0x1800f72b8  mov     [rbp+var_48], 0
0x1800f72bf  mov     eax, [rbp+var_34]
0x1800f72c2  mov     [rbp+var_44], eax
0x1800f72c5  lea     r8, [rbp+var_50]
0x1800f72c9  mov     rdx, rsi
0x1800f72cc  lea     rcx, [rbp+arg_0]
0x1800f72d0  call    ??$?0UVirtualAudioStream@implementation@Devices@Media@WindowsUdk@winrt@@P8012345@EAAXAEBVApxService@12345@AEBUStreamStateEventArgs@12345@@Z@?$delegate@VApxService@implementation@Devices@Media@WindowsUdk@winrt@@UStreamStateEventArgs@23456@@winrt@@QEAA@PEAUVirtualAudioStream@implementation@Devices@Media@WindowsUdk@1@P8234561@EAAXAEBVApxService@34561@AEBUStreamStateEventArgs@34561@@Z@Z; winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>(winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream *,void (winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStream::*)(winrt::WindowsUdk::Media::Devices::implementation::ApxService const &,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs const &))
0x1800f72d5  nop
0x1800f72d6  lea     rcx, [rbx+0A8h]
0x1800f72dd  lea     r8, [rbp+arg_0]
0x1800f72e1  lea     rdx, [rbp+var_50]
0x1800f72e5  call    ?add@?$event@U?$delegate@VApxService@implementation@Devices@Media@WindowsUdk@winrt@@UStreamStateEventArgs@23456@@winrt@@@winrt@@QEAA?AUevent_token@2@AEBU?$delegate@VApxService@implementation@Devices@Media@WindowsUdk@winrt@@UStreamStateEventArgs@23456@@2@@Z; winrt::event<winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs>>::add(winrt::delegate<winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamStateEventArgs> const &)
0x1800f72ea  mov     rax, [rbp+var_50]
0x1800f72ee  mov     [rsi+100h], rax
0x1800f72f5  lea     rcx, [rbp+arg_0]; this
0x1800f72f9  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1800f72fe  nop
0x1800f72ff  mov     rcx, [rbp-38h]; this
0x1800f7303  test    rcx, rcx
0x1800f7306  jz      short loc_1800F730D
0x1800f7308  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800f730d  mov     [rbp+var_30], 28h ; '('
0x1800f7315  lea     rax, ?EvtStreamPrepareHardware@ApxService@implementation@Devices@Media@WindowsUdk@winrt@@SAJPEAUAPXSTREAM__@@@Z; winrt::WindowsUdk::Media::Devices::implementation::ApxService::EvtStreamPrepareHardware(APXSTREAM__ *)
0x1800f731c  mov     [rbp+var_28], rax
0x1800f7320  lea     rax, ?EvtStreamReleaseHardware@ApxService@implementation@Devices@Media@WindowsUdk@winrt@@SAJPEAUAPXSTREAM__@@@Z; winrt::WindowsUdk::Media::Devices::implementation::ApxService::EvtStreamReleaseHardware(APXSTREAM__ *)
0x1800f7327  mov     [rbp+var_20], rax
0x1800f732b  lea     rax, ?EvtStreamRun@ApxService@implementation@Devices@Media@WindowsUdk@winrt@@SAJPEAUAPXSTREAM__@@@Z; winrt::WindowsUdk::Media::Devices::implementation::ApxService::EvtStreamRun(APXSTREAM__ *)
0x1800f7332  mov     [rbp+var_18], rax
0x1800f7336  lea     rax, ?EvtStreamPause@ApxService@implementation@Devices@Media@WindowsUdk@winrt@@SAJPEAUAPXSTREAM__@@@Z; winrt::WindowsUdk::Media::Devices::implementation::ApxService::EvtStreamPause(APXSTREAM__ *)
0x1800f733d  mov     [rbp+var_10], rax
0x1800f7341  lea     r8, [rbp+var_30]
0x1800f7345  mov     rdx, [rbp+arg_8]
0x1800f7349  xor     ecx, ecx
0x1800f734b  call    cs:__imp_imp_ApxStreamInitSetCallbacks
0x1800f7351  mov     [rbp+arg_18], 0
0x1800f7359  lea     rax, [rbp+arg_18]
0x1800f735d  mov     qword ptr [rsp+80h+var_60], rax
0x1800f7362  lea     r9, [rbp+arg_8]
0x1800f7366  xor     r8d, r8d
0x1800f7369  mov     rdx, rdi
0x1800f736c  xor     ecx, ecx
0x1800f736e  call    cs:__imp_imp_ApxStreamCreate
0x1800f7374  mov     rcx, [rbp+18h]; this
0x1800f7378  lea     rdx, aApxstreamcreat; "ApxStreamCreate failed"
0x1800f737f  mov     qword ptr [rsp+80h+var_60], rdx; int
0x1800f7384  mov     r9d, eax; char *
0x1800f7387  lea     r8, aShellcommonUnd_89; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800f738e  mov     edx, 6Dh ; 'm'; void *
0x1800f7393  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f7398  lea     rdi, [rsi+88h]
0x1800f739f  mov     [rbp+arg_0], rdi
0x1800f73a3  mov     rcx, rdi; this
0x1800f73a6  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800f73ab  nop
0x1800f73ac  mov     rax, [rbp+arg_18]
0x1800f73b0  mov     [rsi+0D8h], rax
0x1800f73b7  mov     ecx, 88h; Size
0x1800f73bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f73c1  mov     rbx, rax
0x1800f73c4  mov     [rbp+var_50], rax
0x1800f73c8  mov     r9b, [rsi+0E1h]; unsigned __int8
0x1800f73cf  mov     r8b, [rsi+0E0h]; unsigned __int8
0x1800f73d6  mov     rdx, [rsi+0D8h]; struct APXSTREAM__ *
0x1800f73dd  mov     rcx, rax; this
0x1800f73e0  call    ??0VirtualAudioStreamOutputImpl@implementation@Devices@Media@WindowsUdk@winrt@@QEAA@PEAUAPXSTREAM__@@EE@Z; winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStreamOutputImpl::VirtualAudioStreamOutputImpl(APXSTREAM__ *,uchar,uchar)
0x1800f73e5  lea     rax, ??_7VirtualAudioStreamOutputImpl@implementation@Devices@Media@WindowsUdk@winrt@@6B@; const winrt::WindowsUdk::Media::Devices::implementation::VirtualAudioStreamOutputImpl::`vftable'
0x1800f73ec  mov     [rbx], rax
0x1800f73ef  lea     rax, [rbx+10h]
0x1800f73f3  mov     [rbp+arg_0], rax
0x1800f73f7  lea     rcx, [rsi+80h]
0x1800f73fe  lea     rdx, [rbp+arg_0]
0x1800f7402  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1800f7407  lea     rcx, [rbp+arg_0]; this
0x1800f740b  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1800f7410  nop
0x1800f7411  mov     rcx, rdi; _Mtx_t
0x1800f7414  call    cs:__imp__Mtx_unlock
0x1800f741a  mov     rbx, [rsp+80h+arg_10]
0x1800f7422  add     rsp, 80h
0x1800f7429  pop     rdi
0x1800f742a  pop     rsi
0x1800f742b  pop     rbp
0x1800f742c  retn
```
