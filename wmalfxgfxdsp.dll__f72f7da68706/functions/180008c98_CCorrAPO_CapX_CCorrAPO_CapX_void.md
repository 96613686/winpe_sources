# CCorrAPO_CapX::~CCorrAPO_CapX(void)

- ea: `0x180008c98`
- end: `0x180008d28`
- name: `??1CCorrAPO_CapX@@UEAA@XZ`
- size: `144`
- prototype: `void __fastcall(CCorrAPO_CapX *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008c60`

## callees

- `0x180008d30`
- `0x1800098e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008cfd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008cfd`

## pseudocode

```c
void __fastcall CCorrAPO_CapX::~CCorrAPO_CapX(CCorrAPO_CapX *this)
{
  *(_QWORD *)this = &CCorrAPO::`vftable'{for `CWMDSPPropImpl'};
  *((_QWORD *)this + 11) = &CCorrAPO_CapX::`vftable'{for `CWMDSPComBase'};
  *((_QWORD *)this + 14) = &CCorrAPO_CapX::`vftable'{for `IAudioProcessingObject'};
  *((_QWORD *)this + 15) = &CCorrAPO::`vftable'{for `IAudioProcessingObjectRT'};
  *((_QWORD *)this + 16) = &CCorrAPOBase::`vftable'{for `IAudioProcessingObjectConfiguration'};
  *((_QWORD *)this + 50) = &CCorrAPO_CapX::`vftable'{for `IAudioSystemEffects3'};
  *((_QWORD *)this + 51) = &CCorrAPO_CapX::`vftable'{for `IAudioProcessingObjectNotifications'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 432));
  wil::com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>::~com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>((char *)this + 424);
  wil::com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>::~com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>((char *)this + 416);
  CCorrAPOBase::~CCorrAPOBase((struct _RTL_CRITICAL_SECTION *)this);
}

```

## disassembly

```asm
0x180008c98  push    rbx
0x180008c9a  sub     rsp, 20h
0x180008c9e  lea     rax, ??_7CCorrAPO@@6BCWMDSPPropImpl@@@; const CCorrAPO::`vftable'{for `CWMDSPPropImpl'}
0x180008ca5  mov     rbx, rcx
0x180008ca8  mov     [rcx], rax
0x180008cab  lea     rax, ??_7CCorrAPO_CapX@@6BCWMDSPComBase@@@; const CCorrAPO_CapX::`vftable'{for `CWMDSPComBase'}
0x180008cb2  mov     [rcx+58h], rax
0x180008cb6  lea     rax, ??_7CCorrAPO_CapX@@6BIAudioProcessingObject@@@; const CCorrAPO_CapX::`vftable'{for `IAudioProcessingObject'}
0x180008cbd  mov     [rcx+70h], rax
0x180008cc1  lea     rax, ??_7CCorrAPO@@6BIAudioProcessingObjectRT@@@; const CCorrAPO::`vftable'{for `IAudioProcessingObjectRT'}
0x180008cc8  mov     [rcx+78h], rax
0x180008ccc  lea     rax, ??_7CCorrAPOBase@@6BIAudioProcessingObjectConfiguration@@@; const CCorrAPOBase::`vftable'{for `IAudioProcessingObjectConfiguration'}
0x180008cd3  mov     [rcx+80h], rax
0x180008cda  lea     rax, ??_7CCorrAPO_CapX@@6BIAudioSystemEffects3@@@; const CCorrAPO_CapX::`vftable'{for `IAudioSystemEffects3'}
0x180008ce1  mov     [rcx+190h], rax
0x180008ce8  lea     rax, ??_7CCorrAPO_CapX@@6BIAudioProcessingObjectNotifications@@@; const CCorrAPO_CapX::`vftable'{for `IAudioProcessingObjectNotifications'}
0x180008cef  mov     [rcx+198h], rax
0x180008cf6  add     rcx, 1B0h; lpCriticalSection
0x180008cfd  call    cs:__imp_DeleteCriticalSection
0x180008d03  lea     rcx, [rbx+1A8h]
0x180008d0a  call    ??1?$com_ptr_t@UIAudioProcessingObjectLoggingService@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>::~com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>(void)
0x180008d0f  lea     rcx, [rbx+1A0h]
0x180008d16  call    ??1?$com_ptr_t@UIAudioProcessingObjectLoggingService@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>::~com_ptr_t<IAudioProcessingObjectLoggingService,wil::err_returncode_policy>(void)
0x180008d1b  mov     rcx, rbx; this
0x180008d1e  add     rsp, 20h
0x180008d22  pop     rbx
0x180008d23  jmp     ??1CCorrAPOBase@@UEAA@XZ; CCorrAPOBase::~CCorrAPOBase(void)
```
