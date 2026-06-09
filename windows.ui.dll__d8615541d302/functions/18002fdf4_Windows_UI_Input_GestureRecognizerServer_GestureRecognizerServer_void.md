# Windows::UI::Input::GestureRecognizerServer::~GestureRecognizerServer(void)

- ea: `0x18002fdf4`
- end: `0x18002ff4c`
- name: `??1GestureRecognizerServer@Input@UI@Windows@@EEAA@XZ`
- size: `344`
- prototype: `void __fastcall(Windows::UI::Input::GestureRecognizerServer *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002f680`

## callees

- `0x1800038e0`
- `0x1800050b0`
- `0x18000db18`
- `0x180015764`
- `0x18002fdf4`
- `0x180055344`
- `0x180055560`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002fe6e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002fe6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fe36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fe36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fe65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fe65`
- `NInput!DestroyInteractionContext` at `0x18002ff1a`
- `NInput!DestroyInteractionContext` at `0x18002ff1a`

## pseudocode

```c
void __fastcall Windows::UI::Input::GestureRecognizerServer::~GestureRecognizerServer(
        Windows::UI::Input::GestureRecognizerServer *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 v3; // rcx

  *(_QWORD *)this = &Windows::UI::Input::GestureRecognizerServer::`vftable'{for `Windows::UI::Input::IGestureRecognizer'};
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 584);
  *((_QWORD *)this + 1) = &Windows::UI::Input::GestureRecognizerServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::UI::Input::IGestureRecognizer2,Microsoft::WRL::CloakedIid<INoMarshal>>'};
  *((_QWORD *)this + 2) = &Windows::UI::Input::GestureRecognizerServer::`vftable'{for `Windows::UI::Input::IGestureRecognizer2'};
  *((_QWORD *)this + 3) = &Windows::UI::Input::GestureRecognizerServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<INoMarshal>>'};
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 584));
  if ( *((_QWORD *)this + 37) )
  {
    DestroyInteractionContext();
    *((_QWORD *)this + 37) = 0;
  }
  Windows::UI::Input::GestureRecognizerServer::RemoveTimer(*((_QWORD *)this + 52), 1);
  if ( v2 )
    LeaveCriticalSection(v2);
  DeleteCriticalSection(v2);
  Map<unsigned int,Windows::UI::Input::GestureRecognizerServer::ACTIVE_POINTER_INFO,Less<unsigned int>>::~Map<unsigned int,Windows::UI::Input::GestureRecognizerServer::ACTIVE_POINTER_INFO,Less<unsigned int>>((char *)this + 376);
  v3 = *((_QWORD *)this + 35);
  if ( v3 )
  {
    *((_QWORD *)this + 35) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  Microsoft::WRL::ComPtr<Windows::UI::Input::IPointerPointTransform>::InternalRelease((char *)this + 272);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 264);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 240);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 216);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 192);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 168);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 144);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 120);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 96);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 72);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 48);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::Input::IManipulationStartedEventArgs,Windows::UI::Input::IManipulationStartedEventArgs2,Microsoft::WRL::CloakedIid<INoMarshal>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::Input::IManipulationStartedEventArgs,Windows::UI::Input::IManipulationStartedEventArgs2,Microsoft::WRL::CloakedIid<INoMarshal>>(this);
}

```

## disassembly

```asm
0x18002fdf4  mov     [rsp+arg_0], rbx
0x18002fdf9  push    rdi
0x18002fdfa  sub     rsp, 20h
0x18002fdfe  lea     rax, ??_7GestureRecognizerServer@Input@UI@Windows@@6BIGestureRecognizer@123@@; const Windows::UI::Input::GestureRecognizerServer::`vftable'{for `Windows::UI::Input::IGestureRecognizer'}
0x18002fe05  mov     rbx, rcx
0x18002fe08  mov     [rcx], rax
0x18002fe0b  lea     rdi, [rcx+248h]
0x18002fe12  lea     rax, ??_7GestureRecognizerServer@Input@UI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIGestureRecognizer2@Input@UI@Windows@@U?$CloakedIid@UINoMarshal@@@23@@Details@WRL@Microsoft@@@; const Windows::UI::Input::GestureRecognizerServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::UI::Input::IGestureRecognizer2,Microsoft::WRL::CloakedIid<INoMarshal>>'}
0x18002fe19  mov     [rcx+8], rax
0x18002fe1d  lea     rax, ??_7GestureRecognizerServer@Input@UI@Windows@@6BIGestureRecognizer2@123@@; const Windows::UI::Input::GestureRecognizerServer::`vftable'{for `Windows::UI::Input::IGestureRecognizer2'}
0x18002fe24  mov     [rcx+10h], rax
0x18002fe28  lea     rax, ??_7GestureRecognizerServer@Input@UI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UINoMarshal@@@23@@Details@WRL@Microsoft@@@; const Windows::UI::Input::GestureRecognizerServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<INoMarshal>>'}
0x18002fe2f  mov     [rcx+18h], rax
0x18002fe33  mov     rcx, rdi; lpCriticalSection
0x18002fe36  call    cs:__imp_EnterCriticalSection
0x18002fe3c  mov     rcx, [rbx+128h]
0x18002fe43  test    rcx, rcx
0x18002fe46  jnz     loc_18002FF1A
0x18002fe4c  mov     rcx, [rbx+1A0h]; uIDEvent
0x18002fe53  mov     edx, 1; int
0x18002fe58  call    ?RemoveTimer@GestureRecognizerServer@Input@UI@Windows@@CAX_KH@Z; Windows::UI::Input::GestureRecognizerServer::RemoveTimer(unsigned __int64,int)
0x18002fe5d  test    rdi, rdi
0x18002fe60  jz      short loc_18002FE6B
0x18002fe62  mov     rcx, rdi; lpCriticalSection
0x18002fe65  call    cs:__imp_LeaveCriticalSection
0x18002fe6b  mov     rcx, rdi; lpCriticalSection
0x18002fe6e  call    cs:__imp_DeleteCriticalSection
0x18002fe74  lea     rcx, [rbx+178h]
0x18002fe7b  call    ??1?$Map@IUACTIVE_POINTER_INFO@GestureRecognizerServer@Input@UI@Windows@@V?$Less@I@@@@QEAA@XZ; Map<uint,Windows::UI::Input::GestureRecognizerServer::ACTIVE_POINTER_INFO,Less<uint>>::~Map<uint,Windows::UI::Input::GestureRecognizerServer::ACTIVE_POINTER_INFO,Less<uint>>(void)
0x18002fe80  mov     rcx, [rbx+118h]
0x18002fe87  test    rcx, rcx
0x18002fe8a  jnz     loc_18002FF30
0x18002fe90  lea     rcx, [rbx+110h]
0x18002fe97  call    ?InternalRelease@?$ComPtr@UIPointerPointTransform@Input@UI@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::UI::Input::IPointerPointTransform>::InternalRelease(void)
0x18002fe9c  lea     rcx, [rbx+108h]
0x18002fea3  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002fea8  lea     rcx, [rbx+0F0h]
0x18002feaf  call    ??1?$EventSource@U?$ITypedEventHandler@PEAVRadialController@Input@UI@Windows@@PEAVRadialControllerButtonPressedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x18002feb4  lea     rcx, [rbx+0D8h]
0x18002febb  call    ??1?$EventSource@U?$ITypedEventHandler@PEAVRadialController@Input@UI@Windows@@PEAVRadialControllerButtonPressedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x18002fec0  lea     rcx, [rbx+0C0h]
0x18002fec7  call    ??1?$EventSource@U?$ITypedEventHandler@PEAVRadialController@Input@UI@Windows@@PEAVRadialControllerButtonPressedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x18002fecc  lea     rcx, [rbx+0A8h]
0x18002fed3  call    ??1?$EventSource@U?$ITypedEventHandler@PEAVRadialController@Input@UI@Windows@@PEAVRadialControllerButtonPressedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x18002fed8  lea     rcx, [rbx+90h]
0x18002fedf  call    ??1?$EventSource@U?$ITypedEventHandler@PEAVRadialController@Input@UI@Windows@@PEAVRadialControllerButtonPressedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x18002fee4  lea     rcx, [rbx+78h]
0x18002fee8  call    ??1?$EventSource@U?$ITypedEventHandler@PEAVRadialController@Input@UI@Windows@@PEAVRadialControllerButtonPressedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x18002feed  lea     rcx, [rbx+60h]
0x18002fef1  call    ??1?$EventSource@U?$ITypedEventHandler@PEAVRadialController@Input@UI@Windows@@PEAVRadialControllerButtonPressedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x18002fef6  lea     rcx, [rbx+48h]
0x18002fefa  call    ??1?$EventSource@U?$ITypedEventHandler@PEAVRadialController@Input@UI@Windows@@PEAVRadialControllerButtonPressedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x18002feff  lea     rcx, [rbx+30h]
0x18002ff03  call    ??1?$EventSource@U?$ITypedEventHandler@PEAVRadialController@Input@UI@Windows@@PEAVRadialControllerButtonPressedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Input::RadialController *,Windows::UI::Input::RadialControllerButtonPressedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x18002ff08  mov     rcx, rbx
0x18002ff0b  mov     rbx, [rsp+28h+arg_0]
0x18002ff10  add     rsp, 20h
0x18002ff14  pop     rdi
0x18002ff15  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIManipulationStartedEventArgs@Input@UI@Windows@@UIManipulationStartedEventArgs2@567@U?$CloakedIid@UINoMarshal@@@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::Input::IManipulationStartedEventArgs,Windows::UI::Input::IManipulationStartedEventArgs2,Microsoft::WRL::CloakedIid<INoMarshal>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::Input::IManipulationStartedEventArgs,Windows::UI::Input::IManipulationStartedEventArgs2,Microsoft::WRL::CloakedIid<INoMarshal>>(void)
0x18002ff1a  call    cs:__imp_DestroyInteractionContext
0x18002ff20  mov     qword ptr [rbx+128h], 0
0x18002ff2b  jmp     loc_18002FE4C
0x18002ff30  mov     qword ptr [rbx+118h], 0
0x18002ff3b  mov     rax, [rcx]
0x18002ff3e  mov     rax, [rax+10h]
0x18002ff42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff47  jmp     loc_18002FE90
```
