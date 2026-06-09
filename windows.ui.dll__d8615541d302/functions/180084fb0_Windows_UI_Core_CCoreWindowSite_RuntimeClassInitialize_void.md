# Windows::UI::Core::CCoreWindowSite::RuntimeClassInitialize(void)

- ea: `0x180084fb0`
- end: `0x180085055`
- name: `?RuntimeClassInitialize@CCoreWindowSite@Core@UI@Windows@@UEAAJXZ`
- size: `165`
- prototype: `int(Windows::UI::Core::CCoreWindowSite *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800038e0`
- `0x180014754`
- `0x180014e44`
- `0x180016064`
- `0x18004afd8`
- `0x180084fb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180084fbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180084fbd`
- `CoreMessaging!CoreUICreate` at `0x180085015`
- `CoreMessaging!CoreUICreate` at `0x180085015`

## string_xrefs

- `0x18008502b`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::CCoreWindowSite::RuntimeClassInitialize(Windows::UI::Core::CCoreWindowSite *this)
{
  DWORD CurrentThreadId; // eax
  __int64 v3; // rax
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  Windows::UI::Core::CCoreWindowSite *v10; // [rsp+30h] [rbp+8h] BYREF
  char *v11; // [rsp+38h] [rbp+10h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  v10 = this;
  *((_DWORD *)this + 26) = CurrentThreadId;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v10);
  v11 = (char *)this + 192;
  v3 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v11);
  v4 = Microsoft::WRL::AsWeak<Windows::Foundation::Private::IComponentSite>(this, v3);
  v5 = v4;
  if ( v4 >= 0 )
  {
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 560);
    v4 = CoreUICreate((char *)this + 560);
    v5 = v4;
    if ( v4 >= 0 )
    {
      v5 = 0;
      goto LABEL_7;
    }
    v6 = 74;
  }
  else
  {
    v6 = 72;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
    (const char *)(unsigned int)v4,
    v8);
LABEL_7:
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v10);
  return v5;
}

```

## disassembly

```asm
0x180084fb0  mov     [rsp+arg_10], rbx
0x180084fb5  push    rdi; int
0x180084fb6  sub     rsp, 20h
0x180084fba  mov     rdi, rcx
0x180084fbd  call    cs:__imp_GetCurrentThreadId
0x180084fc3  lea     rcx, [rsp+28h+arg_0]
0x180084fc8  mov     [rsp+28h+arg_0], rdi
0x180084fcd  mov     [rdi+68h], eax
0x180084fd0  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180084fd5  lea     rax, [rdi+0C0h]
0x180084fdc  lea     rcx, [rsp+28h+arg_8]
0x180084fe1  mov     [rsp+28h+arg_8], rax
0x180084fe6  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x180084feb  mov     rdx, rax
0x180084fee  mov     rcx, rdi
0x180084ff1  call    ??$AsWeak@UIComponentSite@Private@Foundation@Windows@@@WRL@Microsoft@@YAJPEAUIComponentSite@Private@Foundation@Windows@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<Windows::Foundation::Private::IComponentSite>(Windows::Foundation::Private::IComponentSite *,Microsoft::WRL::WeakRef *)
0x180084ff6  mov     ebx, eax
0x180084ff8  test    eax, eax
0x180084ffa  jns     short loc_180085003
0x180084ffc  mov     edx, 48h ; 'H'
0x180085001  jmp     short loc_180085026
0x180085003  lea     rbx, [rdi+230h]
0x18008500a  mov     rcx, rbx
0x18008500d  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180085012  mov     rcx, rbx
0x180085015  call    cs:__imp_CoreUICreate
0x18008501b  mov     ebx, eax
0x18008501d  test    eax, eax
0x18008501f  jns     short loc_18008503C
0x180085021  mov     edx, 4Ah ; 'J'; void *
0x180085026  mov     rcx, [rsp+28h]; this
0x18008502b  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180085032  mov     r9d, eax; char *
0x180085035  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008503a  jmp     short loc_18008503E
0x18008503c  xor     ebx, ebx
0x18008503e  lea     rcx, [rsp+28h+arg_0]
0x180085043  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180085048  mov     eax, ebx
0x18008504a  mov     rbx, [rsp+28h+arg_10]
0x18008504f  add     rsp, 20h
0x180085053  pop     rdi
0x180085054  retn
```
