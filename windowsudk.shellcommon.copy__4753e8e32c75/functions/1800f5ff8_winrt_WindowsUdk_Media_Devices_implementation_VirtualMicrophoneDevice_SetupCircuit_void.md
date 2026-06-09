# winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice::SetupCircuit(void)

- ea: `0x1800f5ff8`
- end: `0x1800f62bf`
- name: `?SetupCircuit@VirtualMicrophoneDevice@implementation@Devices@Media@WindowsUdk@winrt@@AEAAXXZ`
- size: `711`
- prototype: `void __fastcall(winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800f5a98`

## callees

- `0x180025348`
- `0x1800f5e5c`
- `0x1800f5ff8`
- `0x18027758c`
- `0x1802775f4`
- `0x1802e42f0`

## import_xrefs

- `Apx01000!imp_ApxCircuitCreate` at `0x1800f6289`
- `Apx01000!imp_ApxCircuitCreate` at `0x1800f6289`
- `Apx01000!imp_ApxCircuitInitAssignPacketSizeConstraints` at `0x1800f6248`
- `Apx01000!imp_ApxCircuitInitAssignPacketSizeConstraints` at `0x1800f6248`
- `Apx01000!imp_ApxCircuitFactoryCreate` at `0x1800f6033`
- `Apx01000!imp_ApxCircuitFactoryCreate` at `0x1800f6033`
- `Apx01000!imp_ApxCircuitInitAllocate` at `0x1800f6069`
- `Apx01000!imp_ApxCircuitInitAllocate` at `0x1800f6069`
- `Apx01000!imp_ApxCircuitInitSetCallbacks` at `0x1800f60c8`
- `Apx01000!imp_ApxCircuitInitSetCallbacks` at `0x1800f60c8`
- `Apx01000!imp_ApxCircuitInitSetCircuitType` at `0x1800f60d9`
- `Apx01000!imp_ApxCircuitInitSetCircuitType` at `0x1800f60d9`
- `Apx01000!imp_ApxCircuitInitSetComponentId` at `0x1800f60eb`
- `Apx01000!imp_ApxCircuitInitSetComponentId` at `0x1800f60eb`
- `Apx01000!imp_ApxCircuitInitAssignName` at `0x1800f6102`
- `Apx01000!imp_ApxCircuitInitAssignName` at `0x1800f6102`
- `Apx01000!imp_ApxCircuitInitAssignFriendlyName` at `0x1800f6146`
- `Apx01000!imp_ApxCircuitInitAssignFriendlyName` at `0x1800f6146`

## string_xrefs

- `0x1800f604d`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\virtualmicrophonedevice.cpp`
- `0x1800f6041`: `ApxCircuitFactoryCreate failed`
- `0x1800f6297`: `ApxCircuitCreate failed`

## pseudocode

```c
void __fastcall winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice::SetupCircuit(
        winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice *this)
{
  _QWORD *v1; // r14
  unsigned int v3; // eax
  __int64 v4; // rax
  __int64 v5; // rdx
  const wchar_t *v6; // rax
  unsigned int inited; // eax
  const wchar_t *v8; // rax
  unsigned int v9; // eax
  __int64 v10; // rbx
  unsigned int v11; // eax
  unsigned int v12; // eax
  const char *v13; // [rsp+28h] [rbp-60h]
  const char *v14; // [rsp+28h] [rbp-60h]
  const char *v15; // [rsp+28h] [rbp-60h]
  const char *v16; // [rsp+28h] [rbp-60h]
  const char *v17; // [rsp+28h] [rbp-60h]
  _QWORD v18[3]; // [rsp+30h] [rbp-58h] BYREF
  _QWORD v19[8]; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v1 = (_QWORD *)((char *)this + 208);
  v18[0] = 24;
  v18[2] = 0;
  v18[1] = (char *)this + 88;
  v3 = imp_ApxCircuitFactoryCreate(0, 0, v18, (char *)this + 208);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x18C,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    (const char *)v3,
    (int)"ApxCircuitFactoryCreate failed",
    v13);
  v4 = imp_ApxCircuitInitAllocate(0, *v1);
  *((_QWORD *)this + 27) = v4;
  wil::details::in1diag3::Throw_IfNullAllocMsg<APXDEVICE_INIT__ *,0>(
    retaddr,
    399,
    "shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    v4,
    "ApxCircuitInitAllocate failed");
  v5 = *((_QWORD *)this + 27);
  v19[1] = winrt::WindowsUdk::Media::Devices::implementation::ApxService::EvtCreateStream;
  v19[0] = 24;
  v19[2] = winrt::WindowsUdk::Media::Devices::implementation::ApxService::EvtDeleteStream;
  imp_ApxCircuitInitSetCallbacks(0, v5, v19);
  imp_ApxCircuitInitSetCircuitType(0, *((_QWORD *)this + 27), 2);
  imp_ApxCircuitInitSetComponentId(0, *((_QWORD *)this + 27), (char *)this + 272);
  v6 = winrt::hstring::c_str((winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice *)((char *)this + 80));
  inited = imp_ApxCircuitInitAssignName(0, *((_QWORD *)this + 27), v6);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x19F,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    (const char *)inited,
    (int)"ApxCircuitInitAssignName failed",
    v14);
  v8 = winrt::hstring::c_str((winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice *)((char *)this + 136));
  v9 = imp_ApxCircuitInitAssignFriendlyName(0, *((_QWORD *)this + 27), v8, 1);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x1A2,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    (const char *)v9,
    (int)"ApxCircuitInitAssignFriendlyName failed",
    v15);
  v10 = *((_QWORD *)this + 19) / 10000LL;
  if ( dword_1805F0908 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1805F0908);
    if ( dword_1805F0908 == -1 )
    {
      dword_1805EC924 = 0;
      dword_1805EC928 = 0x100000;
      dword_1805EC92C = 1;
      dword_1805EC930 = -1634670048;
      dword_1805EC920 = 10000 * v10;
      dword_1805EC944 = 10000 * v10;
      dword_1805EC934 = 1339143315;
      dword_1805EC938 = 327067809;
      dword_1805EC93C = -816404127;
      dword_1805EC940 = 0;
      Init_thread_footer(&dword_1805F0908);
    }
  }
  v11 = imp_ApxCircuitInitAssignPacketSizeConstraints(0, *((_QWORD *)this + 27), &dword_1805EC920);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x1BD,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    (const char *)v11,
    (int)"ApxCircuitInitAssignPacketSizeConstraints failed",
    v16);
  v12 = imp_ApxCircuitCreate(0, *v1, 0, (char *)this + 216, (char *)this + 224);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x1C5,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    (const char *)v12,
    (int)"ApxCircuitCreate failed",
    v17);
}

```

## disassembly

```asm
0x1800f5ff8  mov     r11, rsp
0x1800f5ffb  push    rbx
0x1800f5ffc  push    rsi
0x1800f5ffd  push    rdi
0x1800f5ffe  push    r14
0x1800f6000  push    r15
0x1800f6002  sub     rsp, 60h
0x1800f6006  lea     r14, [rcx+0D0h]
0x1800f600d  mov     qword ptr [r11-58h], 18h
0x1800f6015  lea     rax, [rcx+58h]
0x1800f6019  mov     qword ptr [r11-48h], 0
0x1800f6021  mov     rsi, rcx
0x1800f6024  mov     [r11-50h], rax
0x1800f6028  mov     r9, r14
0x1800f602b  lea     r8, [r11-58h]
0x1800f602f  xor     edx, edx
0x1800f6031  xor     ecx, ecx
0x1800f6033  call    cs:__imp_imp_ApxCircuitFactoryCreate
0x1800f6039  mov     rcx, [rsp+88h]; this
0x1800f6041  lea     rdx, aApxcircuitfact_0; "ApxCircuitFactoryCreate failed"
0x1800f6048  mov     qword ptr [rsp+88h+var_68], rdx; int
0x1800f604d  lea     r15, aShellcommonUnd_146; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800f6054  mov     edx, 18Ch; void *
0x1800f6059  mov     r9d, eax; char *
0x1800f605c  mov     r8, r15; unsigned int
0x1800f605f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f6064  mov     rdx, [r14]
0x1800f6067  xor     ecx, ecx
0x1800f6069  call    cs:__imp_imp_ApxCircuitInitAllocate
0x1800f606f  mov     rcx, [rsp+88h]
0x1800f6077  lea     rdx, aApxcircuitinit_2; "ApxCircuitInitAllocate failed"
0x1800f607e  mov     qword ptr [rsp+88h+var_68], rdx
0x1800f6083  lea     rdi, [rsi+0D8h]
0x1800f608a  mov     edx, 18Fh
0x1800f608f  mov     [rdi], rax
0x1800f6092  mov     r9, rax
0x1800f6095  mov     r8, r15
0x1800f6098  call    ??$Throw_IfNullAllocMsg@PEAUAPXDEVICE_INIT__@@$0A@@in1diag3@details@wil@@YAPEAUAPXDEVICE_INIT__@@PEAXIPEBDPEAU3@1ZZ; wil::details::in1diag3::Throw_IfNullAllocMsg<APXDEVICE_INIT__ *,0>(void *,uint,char const *,APXDEVICE_INIT__ *,char const *,...)
0x1800f609d  mov     rdx, [rdi]
0x1800f60a0  lea     rax, ?EvtCreateStream@ApxService@implementation@Devices@Media@WindowsUdk@winrt@@SAJPEAUAPXCIRCUIT__@@PEAUAPXSTREAM_INIT__@@PEAUAPXDATAFORMAT__@@PEBU_GUID@@PEAUAPXOBJECTBAG__@@@Z; winrt::WindowsUdk::Media::Devices::implementation::ApxService::EvtCreateStream(APXCIRCUIT__ *,APXSTREAM_INIT__ *,APXDATAFORMAT__ *,_GUID const *,APXOBJECTBAG__ *)
0x1800f60a7  mov     [rsp+88h+var_38], rax
0x1800f60ac  lea     r8, [rsp+88h+var_40]
0x1800f60b1  lea     rax, ?EvtDeleteStream@ApxService@implementation@Devices@Media@WindowsUdk@winrt@@SAXPEAUAPXCIRCUIT__@@PEAUAPXSTREAM__@@@Z; winrt::WindowsUdk::Media::Devices::implementation::ApxService::EvtDeleteStream(APXCIRCUIT__ *,APXSTREAM__ *)
0x1800f60b8  mov     [rsp+88h+var_40], 18h
0x1800f60c1  xor     ecx, ecx
0x1800f60c3  mov     [rsp+88h+var_30], rax
0x1800f60c8  call    cs:__imp_imp_ApxCircuitInitSetCallbacks
0x1800f60ce  mov     rdx, [rdi]
0x1800f60d1  mov     r8d, 2
0x1800f60d7  xor     ecx, ecx
0x1800f60d9  call    cs:__imp_imp_ApxCircuitInitSetCircuitType
0x1800f60df  mov     rdx, [rdi]
0x1800f60e2  lea     r8, [rsi+110h]
0x1800f60e9  xor     ecx, ecx
0x1800f60eb  call    cs:__imp_imp_ApxCircuitInitSetComponentId
0x1800f60f1  lea     rcx, [rsi+50h]; this
0x1800f60f5  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1800f60fa  mov     rdx, [rdi]
0x1800f60fd  mov     r8, rax
0x1800f6100  xor     ecx, ecx
0x1800f6102  call    cs:__imp_imp_ApxCircuitInitAssignName
0x1800f6108  mov     rcx, [rsp+88h]; this
0x1800f6110  lea     rdx, aApxcircuitinit_1; "ApxCircuitInitAssignName failed"
0x1800f6117  mov     qword ptr [rsp+88h+var_68], rdx; int
0x1800f611c  mov     r9d, eax; char *
0x1800f611f  mov     edx, 19Fh; void *
0x1800f6124  mov     r8, r15; unsigned int
0x1800f6127  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f612c  lea     rcx, [rsi+88h]; this
0x1800f6133  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1800f6138  mov     rdx, [rdi]
0x1800f613b  mov     r8, rax
0x1800f613e  mov     r9d, 1
0x1800f6144  xor     ecx, ecx
0x1800f6146  call    cs:__imp_imp_ApxCircuitInitAssignFriendlyName
0x1800f614c  mov     rcx, [rsp+88h]; this
0x1800f6154  lea     rdx, aApxcircuitinit; "ApxCircuitInitAssignFriendlyName failed"
0x1800f615b  mov     qword ptr [rsp+88h+var_68], rdx; int
0x1800f6160  mov     r9d, eax; char *
0x1800f6163  mov     edx, 1A2h; void *
0x1800f6168  mov     r8, r15; unsigned int
0x1800f616b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f6170  mov     rax, 346DC5D63886594Bh
0x1800f617a  imul    qword ptr [rsi+98h]
0x1800f6181  mov     rbx, rdx
0x1800f6184  sar     rbx, 0Bh
0x1800f6188  mov     rax, rbx
0x1800f618b  shr     rax, 3Fh
0x1800f618f  mov     ecx, cs:_tls_index
0x1800f6195  add     rbx, rax
0x1800f6198  mov     rax, gs:58h
0x1800f61a1  mov     edx, 4
0x1800f61a6  mov     rax, [rax+rcx*8]
0x1800f61aa  mov     eax, [rdx+rax]
0x1800f61ad  cmp     cs:dword_1805F0908, eax
0x1800f61b3  jle     loc_1800F623C
0x1800f61b9  lea     rcx, dword_1805F0908
0x1800f61c0  call    _Init_thread_header
0x1800f61c5  cmp     cs:dword_1805F0908, 0FFFFFFFFh
0x1800f61cc  jnz     short loc_1800F623C
0x1800f61ce  imul    eax, ebx, 2710h
0x1800f61d4  lea     rcx, dword_1805F0908
0x1800f61db  mov     cs:dword_1805EC924, 0
0x1800f61e5  mov     cs:dword_1805EC928, 100000h
0x1800f61ef  mov     cs:dword_1805EC92C, 1
0x1800f61f9  mov     cs:dword_1805EC930, 9E90EA20h
0x1800f6203  mov     cs:dword_1805EC920, eax
0x1800f6209  mov     cs:dword_1805EC944, eax
0x1800f620f  mov     cs:dword_1805EC934, 4FD1B493h
0x1800f6219  mov     cs:dword_1805EC938, 137EA8A1h
0x1800f6223  mov     cs:dword_1805EC93C, 0CF56A961h
0x1800f622d  mov     cs:dword_1805EC940, 0
0x1800f6237  call    _Init_thread_footer
0x1800f623c  mov     rdx, [rdi]
0x1800f623f  lea     r8, dword_1805EC920
0x1800f6246  xor     ecx, ecx
0x1800f6248  call    cs:__imp_imp_ApxCircuitInitAssignPacketSizeConstraints
0x1800f624e  mov     rcx, [rsp+88h]; this
0x1800f6256  lea     rdx, aApxcircuitinit_0; "ApxCircuitInitAssignPacketSizeConstrain"...
0x1800f625d  mov     qword ptr [rsp+88h+var_68], rdx; int
0x1800f6262  mov     r9d, eax; char *
0x1800f6265  mov     edx, 1BDh; void *
0x1800f626a  mov     r8, r15; unsigned int
0x1800f626d  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f6272  mov     rdx, [r14]
0x1800f6275  lea     rax, [rsi+0E0h]
0x1800f627c  mov     r9, rdi
0x1800f627f  mov     qword ptr [rsp+88h+var_68], rax
0x1800f6284  xor     r8d, r8d
0x1800f6287  xor     ecx, ecx
0x1800f6289  call    cs:__imp_imp_ApxCircuitCreate
0x1800f628f  mov     rcx, [rsp+88h]; this
0x1800f6297  lea     rdx, aApxcircuitcrea; "ApxCircuitCreate failed"
0x1800f629e  mov     qword ptr [rsp+88h+var_68], rdx; int
0x1800f62a3  mov     r9d, eax; char *
0x1800f62a6  mov     edx, 1C5h; void *
0x1800f62ab  mov     r8, r15; unsigned int
0x1800f62ae  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f62b3  add     rsp, 60h
0x1800f62b7  pop     r15
0x1800f62b9  pop     r14
0x1800f62bb  pop     rdi
0x1800f62bc  pop     rsi
0x1800f62bd  pop     rbx
0x1800f62be  retn
```
