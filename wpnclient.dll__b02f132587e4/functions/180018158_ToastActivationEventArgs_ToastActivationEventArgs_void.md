# ToastActivationEventArgs::~ToastActivationEventArgs(void)

- ea: `0x180018158`
- end: `0x18001819b`
- name: `??1ToastActivationEventArgs@@UEAA@XZ`
- size: `67`
- prototype: `void __fastcall(ToastActivationEventArgs *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800160e0`

## callees

- `0x180005670`
- `0x1800181a4`
- `0x1800181e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018174`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018174`

## pseudocode

```c
void __fastcall ToastActivationEventArgs::~ToastActivationEventArgs(HSTRING *this)
{
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 35);
  WindowsDeleteString(this[34]);
  this[34] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsWithViewIdBase,Windows::ApplicationModel::Activation::IToastNotificationActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsWithViewIdBase,Windows::ApplicationModel::Activation::IToastNotificationActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>>((CActivatedEventArgsWithViewIdBase *)(this + 2));
  CThreadRefTaker::~CThreadRefTaker((CThreadRefTaker *)this);
}

```

## disassembly

```asm
0x180018158  push    rbx
0x18001815a  sub     rsp, 20h
0x18001815e  mov     rbx, rcx
0x180018161  add     rcx, 118h
0x180018168  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001816d  mov     rcx, [rbx+110h]; string
0x180018174  call    cs:__imp_WindowsDeleteString
0x18001817a  lea     rcx, [rbx+10h]; this
0x18001817e  mov     qword ptr [rbx+110h], 0
0x180018189  call    ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VCActivatedEventArgsWithViewIdBase@@UIToastNotificationActivatedEventArgs@Activation@ApplicationModel@Windows@@U?$CloakedIid@UIValueMarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsWithViewIdBase,Windows::ApplicationModel::Activation::IToastNotificationActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsWithViewIdBase,Windows::ApplicationModel::Activation::IToastNotificationActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>>(void)
0x18001818e  mov     rcx, rbx; this
0x180018191  add     rsp, 20h
0x180018195  pop     rbx
0x180018196  jmp     ??1CThreadRefTaker@@UEAA@XZ; CThreadRefTaker::~CThreadRefTaker(void)
```
