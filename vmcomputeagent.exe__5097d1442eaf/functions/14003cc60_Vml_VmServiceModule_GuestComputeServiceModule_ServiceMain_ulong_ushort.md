# Vml::VmServiceModule<GuestComputeServiceModule>::ServiceMain(ulong,ushort * *)

- ea: `0x14003cc60`
- end: `0x14003cd5a`
- name: `?ServiceMain@?$VmServiceModule@VGuestComputeServiceModule@@@Vml@@CAXKPEAPEAG@Z`
- size: `250`
- prototype: `void()`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x140005e70`
- `0x140009f8c`
- `0x14000efd8`
- `0x14000f264`
- `0x14003cab4`
- `0x14003cc60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003ccbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003ccd6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003ccbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003ccd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003cd08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003cd08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003cd1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003cc99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003cc99`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14003ccff`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14003ccff`

## string_xrefs

- `0x14003cd48`: `onecore\vm\common\vml\VmModules.h`
- `0x14003cd35`: `A derivative of VmModuleBase has not been constructed!\n   This usually occurs because a portion of the VML has been\n   used in a component that is not built from one of the VML\n   module classes.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void Vml::VmServiceModule<GuestComputeServiceModule>::ServiceMain()
{
  char *v0; // rbx
  int v1; // esi
  DWORD CurrentThreadId; // eax
  const char *v3; // r9
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v0 = (char *)Vml::VmModuleBase::gm_ModuleBase;
  if ( !Vml::VmModuleBase::gm_ModuleBase )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(2) )
      VmlDebugTrace(
        2,
        L"A derivative of VmModuleBase has not been constructed!\n"
         "   This usually occurs because a portion of the VML has been\n"
         "   used in a component that is not built from one of the VML\n"
         "   module classes.\n");
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xA9,
      (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
      v4);
  }
  v1 = 0;
  _castguard_slow_path_check_fastfail(*(_QWORD *)Vml::VmModuleBase::gm_ModuleBase, 232, 0);
  CurrentThreadId = GetCurrentThreadId();
  try
  {
    *((_DWORD *)v0 + 20) = CurrentThreadId;
    Vml::VmExeModule<GuestComputeServiceModule>::Run(v0);
  }
  catch ( ... )
  {
    v1 = wil::details::in1diag3::Log_CaughtException(
           retaddr,
           (void *)0xC61,
           (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
           v3);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)v0 + 1);
  if ( *((_DWORD *)v0 + 27) != 1 && *((_QWORD *)v0 + 17) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)v0 + 1);
    if ( *((_DWORD *)v0 + 27) != 1 )
      *(_QWORD *)(v0 + 124) = 0;
    *((_DWORD *)v0 + 27) = 1;
    *((_DWORD *)v0 + 29) = v1;
    SetServiceStatus(*((SERVICE_STATUS_HANDLE *)v0 + 17), (LPSERVICE_STATUS)(v0 + 104));
    LeaveCriticalSection((LPCRITICAL_SECTION)v0 + 1);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v0 + 1);
}

```

## disassembly

```asm
0x14003cc60  mov     [rsp+arg_0], rbx
0x14003cc65  push    rsi
0x14003cc66  push    rdi
0x14003cc67  push    r14
0x14003cc69  sub     rsp, 20h
0x14003cc6d  mov     rbx, cs:?gm_ModuleBase@VmModuleBase@Vml@@1PEAV12@EA; Vml::VmModuleBase * Vml::VmModuleBase::gm_ModuleBase
0x14003cc74  test    rbx, rbx
0x14003cc77  jz      loc_14003CD25
0x14003cc7d  xor     esi, esi
0x14003cc7f  test    rbx, rbx
0x14003cc82  jz      short loc_14003CC94
0x14003cc84  xor     r8d, r8d
0x14003cc87  mov     edx, 0E8h
0x14003cc8c  mov     rcx, [rbx]
0x14003cc8f  call    __castguard_slow_path_check_fastfail
0x14003cc94  mov     [rsp+38h+arg_18], rbx
0x14003cc99  call    cs:__imp_GetCurrentThreadId
0x14003cc9f  mov     [rbx+50h], eax
0x14003cca2  mov     rcx, rbx; lpContext
0x14003cca5  call    ?Run@?$VmExeModule@VGuestComputeServiceModule@@@Vml@@QEAAHH@Z; Vml::VmExeModule<GuestComputeServiceModule>::Run(int)
0x14003ccaa  nop
0x14003ccab  jmp     short loc_14003CCB6
0x14003ccad  mov     esi, [rsp+38h+arg_10]
0x14003ccb1  mov     rbx, [rsp+38h+arg_18]
0x14003ccb6  lea     rdi, [rbx+28h]
0x14003ccba  mov     rcx, rdi; lpCriticalSection
0x14003ccbd  call    cs:__imp_EnterCriticalSection
0x14003ccc3  cmp     dword ptr [rbx+6Ch], 1
0x14003ccc7  jz      short loc_14003CD0E
0x14003ccc9  cmp     qword ptr [rbx+88h], 0
0x14003ccd1  jz      short loc_14003CD0E
0x14003ccd3  mov     rcx, rdi; lpCriticalSection
0x14003ccd6  call    cs:__imp_EnterCriticalSection
0x14003ccdc  cmp     dword ptr [rbx+6Ch], 1
0x14003cce0  jz      short loc_14003CCEA
0x14003cce2  mov     qword ptr [rbx+7Ch], 0
0x14003ccea  mov     dword ptr [rbx+6Ch], 1
0x14003ccf1  mov     [rbx+74h], esi
0x14003ccf4  lea     rdx, [rbx+68h]; lpServiceStatus
0x14003ccf8  mov     rcx, [rbx+88h]; hServiceStatus
0x14003ccff  call    cs:__imp_SetServiceStatus
0x14003cd05  mov     rcx, rdi; lpCriticalSection
0x14003cd08  call    cs:__imp_LeaveCriticalSection
0x14003cd0e  mov     rcx, rdi
0x14003cd11  mov     rbx, [rsp+38h+arg_0]
0x14003cd16  add     rsp, 20h
0x14003cd1a  pop     r14
0x14003cd1c  pop     rdi
0x14003cd1d  pop     rsi
0x14003cd1e  jmp     cs:__imp_LeaveCriticalSection
0x14003cd25  mov     ebx, 2
0x14003cd2a  mov     ecx, ebx
0x14003cd2c  call    VmlIsDebugTraceEnabled
0x14003cd31  test    eax, eax
0x14003cd33  jz      short loc_14003CD43
0x14003cd35  lea     rdx, aADerivativeOfV; "A derivative of VmModuleBase has not be"...
0x14003cd3c  mov     ecx, ebx
0x14003cd3e  call    VmlDebugTrace
0x14003cd43  mov     rcx, [rsp+38h]; this
0x14003cd48  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\vml\\VmModules.h"
0x14003cd4f  mov     edx, 0A9h; void *
0x14003cd54  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
