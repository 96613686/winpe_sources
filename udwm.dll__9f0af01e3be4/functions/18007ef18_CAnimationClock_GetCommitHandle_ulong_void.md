# CAnimationClock::GetCommitHandle(ulong,void * *)

- ea: `0x18007ef18`
- end: `0x18007f09e`
- name: `?GetCommitHandle@CAnimationClock@@QEAAJKPEAPEAX@Z`
- size: `390`
- prototype: `int(CAnimationClock *__hidden this, unsigned int, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009ddd8`

## callees

- `0x18002586c`
- `0x180025b70`
- `0x180044e30`
- `0x180044ec0`
- `0x18007eeec`
- `0x18007ef18`
- `0x1800802e8`
- `0x18008ea04`
- `0x180095130`
- `0x18009d52c`
- `0x18009d818`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ef4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ef4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007f004`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007f010`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007f004`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007f010`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007efc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007efc8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18007f03a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18007f03a`
- `win32u!NtDCompositionDuplicateHandleToProcess` at `0x18007efda`
- `win32u!NtDCompositionDuplicateHandleToProcess` at `0x18007efda`
- `win32u!NtDCompositionCreateSynchronizationObject` at `0x18007efb3`
- `win32u!NtDCompositionCreateSynchronizationObject` at `0x18007efb3`

## string_xrefs

- `0x18007ef54`: `GetCommitHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAnimationClock::GetCommitHandle(CAnimationClock *this, unsigned int a2, void **a3)
{
  _QWORD *v6; // rdi
  __int64 v7; // rcx
  int SynchronizationObject; // eax
  __int64 v9; // rdx
  int LastError; // eax
  unsigned int v11; // ebx
  HANDLE CurrentProcess; // rbx
  void *v13; // rdi
  HANDLE v14; // rax
  const char *v15; // r9
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-1B8h]
  char *v18; // [rsp+40h] [rbp-198h] BYREF
  struct _GUID v19; // [rsp+50h] [rbp-188h] BYREF
  _QWORD v20[42]; // [rsp+60h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  *a3 = 0;
  v18 = (char *)this + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v20,
    "GetCommitHandle");
  v20[0] = &AnimationClockLoggingTelemetry::GetCommitHandle::`vftable';
  v19 = *(struct _GUID *)((char *)this + 120);
  AnimationClockLoggingTelemetry::GetCommitHandle::StartActivity(
    (AnimationClockLoggingTelemetry::GetCommitHandle *)v20,
    &v19);
  if ( (unsigned int)(*((_DWORD *)this + 20) - 1) > 1 )
    goto LABEL_13;
  v6 = (_QWORD *)((char *)this + 112);
  if ( !(unsigned __int8)wil::operator==<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(v6)
    || (wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          v7,
          0),
        SynchronizationObject = NtDCompositionCreateSynchronizationObject(v6),
        SynchronizationObject >= 0) )
  {
    if ( !a2 || a2 == GetCurrentProcessId() )
    {
      CurrentProcess = GetCurrentProcess();
      v13 = (void *)*v6;
      v14 = GetCurrentProcess();
      if ( !DuplicateHandle(v14, v13, CurrentProcess, a3, 0, 0, 2u) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x27B,
                      (unsigned int)"clientcore\\windows\\dwm\\udwm\\animationclock.cpp",
                      v15);
        goto LABEL_10;
      }
    }
    else
    {
      SynchronizationObject = NtDCompositionDuplicateHandleToProcess(*v6, a2, a3);
      if ( SynchronizationObject < 0 )
      {
        v9 = 631;
        goto LABEL_9;
      }
    }
LABEL_13:
    wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v20, 0);
    v11 = 0;
    goto LABEL_14;
  }
  v9 = 623;
LABEL_9:
  LastError = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)v9,
                (unsigned int)"clientcore\\windows\\dwm\\udwm\\animationclock.cpp",
                (const char *)(unsigned int)SynchronizationObject,
                dwDesiredAccess);
LABEL_10:
  v11 = LastError;
LABEL_14:
  AnimationClockLoggingTelemetry::GetCommitHandle::~GetCommitHandle((AnimationClockLoggingTelemetry::GetCommitHandle *)v20);
  CGuard<CDwmCS>::~CGuard<CDwmCS>(&v18);
  return v11;
}

```

## disassembly

```asm
0x18007ef18  push    rbx
0x18007ef1a  push    rsi
0x18007ef1b  push    rdi
0x18007ef1c  sub     rsp, 1C0h
0x18007ef23  mov     rax, cs:__security_cookie
0x18007ef2a  xor     rax, rsp
0x18007ef2d  mov     [rsp+1D8h+var_28], rax
0x18007ef35  mov     rsi, r8
0x18007ef38  mov     ebx, edx
0x18007ef3a  mov     rdi, rcx
0x18007ef3d  mov     qword ptr [r8], 0
0x18007ef44  add     rcx, 18h; lpCriticalSection
0x18007ef48  mov     [rsp+1D8h+var_198], rcx
0x18007ef4d  call    cs:__imp_EnterCriticalSection
0x18007ef53  nop
0x18007ef54  lea     rdx, aGetcommithandl; "GetCommitHandle"
0x18007ef5b  lea     rcx, [rsp+1D8h+var_178]
0x18007ef60  call    ??0?$ActivityBase@VAnimationClockLogging@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18007ef65  lea     rax, ??_7GetCommitHandle@AnimationClockLoggingTelemetry@@6B@; const AnimationClockLoggingTelemetry::GetCommitHandle::`vftable'
0x18007ef6c  mov     [rsp+1D8h+var_178], rax
0x18007ef71  movups  xmm0, xmmword ptr [rdi+78h]
0x18007ef75  movdqu  xmmword ptr [rsp+1D8h+var_188.Data1], xmm0
0x18007ef7b  lea     rdx, [rsp+1D8h+var_188]; struct _GUID
0x18007ef80  lea     rcx, [rsp+1D8h+var_178]; this
0x18007ef85  call    ?StartActivity@GetCommitHandle@AnimationClockLoggingTelemetry@@QEAAXU_GUID@@@Z; AnimationClockLoggingTelemetry::GetCommitHandle::StartActivity(_GUID)
0x18007ef8a  nop
0x18007ef8b  mov     eax, [rdi+50h]
0x18007ef8e  dec     eax
0x18007ef90  cmp     eax, 1
0x18007ef93  ja      loc_18007F05F
0x18007ef99  add     rdi, 70h ; 'p'
0x18007ef9d  mov     rcx, rdi
0x18007efa0  call    ??$?8V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@0@$$T@Z; wil::operator==<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,std::nullptr_t)
0x18007efa5  test    al, al
0x18007efa7  jz      short loc_18007EFC4
0x18007efa9  xor     edx, edx
0x18007efab  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18007efb0  mov     rcx, rdi
0x18007efb3  call    cs:__imp_NtDCompositionCreateSynchronizationObject
0x18007efb9  test    eax, eax
0x18007efbb  jns     short loc_18007EFC4
0x18007efbd  mov     edx, 26Fh
0x18007efc2  jmp     short loc_18007EFE9
0x18007efc4  test    ebx, ebx
0x18007efc6  jz      short loc_18007F004
0x18007efc8  call    cs:__imp_GetCurrentProcessId
0x18007efce  cmp     ebx, eax
0x18007efd0  jz      short loc_18007F004
0x18007efd2  mov     r8, rsi
0x18007efd5  mov     edx, ebx
0x18007efd7  mov     rcx, [rdi]
0x18007efda  call    cs:__imp_NtDCompositionDuplicateHandleToProcess
0x18007efe0  test    eax, eax
0x18007efe2  jns     short loc_18007F05F
0x18007efe4  mov     edx, 277h; void *
0x18007efe9  lea     r8, aClientcoreWind_83; "clientcore\\windows\\dwm\\udwm\\animati"...
0x18007eff0  mov     r9d, eax; char *
0x18007eff3  mov     rcx, [rsp+1D8h]; this
0x18007effb  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007f000  mov     ebx, eax
0x18007f002  jmp     short loc_18007F06D
0x18007f004  call    cs:__imp_GetCurrentProcess
0x18007f00a  mov     rbx, rax
0x18007f00d  mov     rdi, [rdi]
0x18007f010  call    cs:__imp_GetCurrentProcess
0x18007f016  mov     [rsp+1D8h+dwOptions], 2; dwOptions
0x18007f01e  mov     [rsp+1D8h+bInheritHandle], 0; bInheritHandle
0x18007f026  mov     [rsp+1D8h+dwDesiredAccess], 0; dwDesiredAccess
0x18007f02e  mov     r9, rsi; lpTargetHandle
0x18007f031  mov     r8, rbx; hTargetProcessHandle
0x18007f034  mov     rdx, rdi; hSourceHandle
0x18007f037  mov     rcx, rax; hSourceProcessHandle
0x18007f03a  call    cs:__imp_DuplicateHandle
0x18007f040  test    eax, eax
0x18007f042  jnz     short loc_18007F05F
0x18007f044  mov     rcx, [rsp+1D8h]; this
0x18007f04c  lea     r8, aClientcoreWind_83; "clientcore\\windows\\dwm\\udwm\\animati"...
0x18007f053  mov     edx, 27Bh; void *
0x18007f058  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007f05d  jmp     short loc_18007F000
0x18007f05f  xor     edx, edx
0x18007f061  lea     rcx, [rsp+1D8h+var_178]
0x18007f066  call    ?Stop@?$ActivityBase@VAnimationClockLogging@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18007f06b  xor     ebx, ebx
0x18007f06d  lea     rcx, [rsp+1D8h+var_178]; this
0x18007f072  call    ??1GetCommitHandle@AnimationClockLoggingTelemetry@@QEAA@XZ; AnimationClockLoggingTelemetry::GetCommitHandle::~GetCommitHandle(void)
0x18007f077  lea     rcx, [rsp+1D8h+var_198]
0x18007f07c  call    ??1?$CGuard@VCDwmCS@@@@QEAA@XZ; CGuard<CDwmCS>::~CGuard<CDwmCS>(void)
0x18007f081  mov     eax, ebx
0x18007f083  mov     rcx, [rsp+1D8h+var_28]
0x18007f08b  xor     rcx, rsp; StackCookie
0x18007f08e  call    __security_check_cookie
0x18007f093  add     rsp, 1C0h
0x18007f09a  pop     rdi
0x18007f09b  pop     rsi
0x18007f09c  pop     rbx
0x18007f09d  retn
```
