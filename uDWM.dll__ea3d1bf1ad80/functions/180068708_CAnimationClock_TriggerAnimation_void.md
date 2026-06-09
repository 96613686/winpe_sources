# CAnimationClock::_TriggerAnimation(void)

- ea: `0x180068708`
- end: `0x1800688c6`
- name: `?_TriggerAnimation@CAnimationClock@@AEAAJXZ`
- size: `446`
- prototype: `__int64 __fastcall(CAnimationClock *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800255e8`

## callees

- `0x18001ce00`
- `0x1800251d8`
- `0x18002586c`
- `0x18002592c`
- `0x180025994`
- `0x180025ad0`
- `0x180025b70`
- `0x180045c20`
- `0x180068708`
- `0x1800688cc`
- `0x1800688e0`
- `0x18008b854`
- `0x18008dac8`
- `0x18008ea04`
- `0x180090664`
- `0x180095130`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068863`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068863`
- `win32u!NtDCompositionCommitSynchronizationObject` at `0x180068880`
- `win32u!NtDCompositionCommitSynchronizationObject` at `0x180068880`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CAnimationClock::_TriggerAnimation(CAnimationClock *this)
{
  int AnimationTriggerProxyFromSharedHandle; // edi
  __int64 v3; // rdx
  CBaseObject *v5; // rbx
  int v6; // eax
  unsigned int v7; // ebx
  HANDLE hObject[2]; // [rsp+20h] [rbp-E0h] BYREF
  struct _GUID v9; // [rsp+30h] [rbp-D0h] BYREF
  void **v10; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v11[272]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v12[8]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v13[48]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>(
    &v10,
    "TriggerClock");
  v10 = &AnimationClockLoggingTelemetry::TriggerClock::`vftable';
  v9 = *(struct _GUID *)((char *)this + 120);
  AnimationClockLoggingTelemetry::TriggerClock::StartActivity((AnimationClockLoggingTelemetry::TriggerClock *)&v10, &v9);
  if ( (unsigned __int8)wil::operator!=<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>((char *)this + 112) )
  {
    v6 = NtDCompositionCommitSynchronizationObject(*((_QWORD *)this + 14));
    if ( v6 < 0 )
    {
      v7 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0xDA,
             (unsigned int)"clientcore\\windows\\dwm\\udwm\\animationclock.cpp",
             (const char *)(unsigned int)v6,
             (int)hObject[0]);
      AnimationClockLoggingTelemetry::TriggerClock::~TriggerClock((AnimationClockLoggingTelemetry::TriggerClock *)&v10);
      return v7;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=((char *)this + 112);
  }
  AnimationTriggerProxyFromSharedHandle = 0;
  v3 = *((_QWORD *)this + 13);
  if ( v3 )
  {
    hObject[0] = 0;
    AnimationTriggerProxyFromSharedHandle = (*(__int64 (__fastcall **)(_QWORD, __int64, HANDLE *))(**(_QWORD **)(*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 6) + 32LL)
                                                                                                 + 224LL))(
                                              *(_QWORD *)(*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 6)
                                                        + 32LL),
                                              v3,
                                              hObject);
    if ( AnimationTriggerProxyFromSharedHandle >= 0 )
    {
      *(_QWORD *)&v9.Data1 = 0;
      AnimationTriggerProxyFromSharedHandle = CCompositor::CreateAnimationTriggerProxyFromSharedHandle(
                                                *((CCompositor **)CDesktopManager::s_pDesktopManagerInstance + 6),
                                                hObject[0],
                                                (struct CAnimationTriggerProxy **)&v9);
      v5 = *(CBaseObject **)&v9.Data1;
      if ( AnimationTriggerProxyFromSharedHandle >= 0 )
        AnimationTriggerProxyFromSharedHandle = CAnimationTriggerProxy::Trigger(
                                                  *(CAnimationTriggerProxy **)&v9.Data1,
                                                  *((_QWORD *)this + 11));
      CloseHandle(hObject[0]);
      if ( v5 )
        CBaseObject::Release(v5);
    }
  }
  wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    &v10,
    (unsigned int)AnimationTriggerProxyFromSharedHandle);
  v10 = &AnimationClockLoggingTelemetry::TriggerClock::`vftable';
  wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v10);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v13);
  wil::details::shared_object<wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AnimationClockLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v12);
  wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AnimationClockLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<AnimationClockLogging,_TlgReflectorTag_Param0IsProviderType>(v11);
  return (unsigned int)AnimationTriggerProxyFromSharedHandle;
}

```

## disassembly

```asm
0x180068708  mov     [rsp-8+arg_8], rbx
0x18006870d  mov     [rsp-8+arg_10], rsi
0x180068712  push    rbp
0x180068713  push    rdi
0x180068714  push    r14
0x180068716  lea     rbp, [rsp-0A0h]
0x18006871e  sub     rsp, 1A0h
0x180068725  mov     rax, cs:__security_cookie
0x18006872c  xor     rax, rsp
0x18006872f  mov     [rbp+0B0h+var_20], rax
0x180068736  mov     rsi, rcx
0x180068739  lea     rdx, aTriggerclock; "TriggerClock"
0x180068740  lea     rcx, [rsp+1B0h+var_170]
0x180068745  call    ??0?$ActivityBase@VAnimationClockLogging@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18006874a  lea     r14, ??_7TriggerClock@AnimationClockLoggingTelemetry@@6B@; const AnimationClockLoggingTelemetry::TriggerClock::`vftable'
0x180068751  mov     [rsp+1B0h+var_170], r14
0x180068756  movups  xmm0, xmmword ptr [rsi+78h]
0x18006875a  movdqu  xmmword ptr [rsp+1B0h+var_180.Data1], xmm0
0x180068760  lea     rdx, [rsp+1B0h+var_180]; struct _GUID
0x180068765  lea     rcx, [rsp+1B0h+var_170]; this
0x18006876a  call    ?StartActivity@TriggerClock@AnimationClockLoggingTelemetry@@QEAAXU_GUID@@@Z; AnimationClockLoggingTelemetry::TriggerClock::StartActivity(_GUID)
0x18006876f  nop
0x180068770  lea     rbx, [rsi+70h]
0x180068774  mov     rcx, rbx
0x180068777  call    ??$?9V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@0@$$T@Z; wil::operator!=<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,std::nullptr_t)
0x18006877c  test    al, al
0x18006877e  jnz     loc_18006887D
0x180068784  xor     edi, edi
0x180068786  mov     rdx, [rsi+68h]
0x18006878a  test    rdx, rdx
0x18006878d  jnz     short loc_1800687F0
0x18006878f  mov     edx, edi
0x180068791  lea     rcx, [rsp+1B0h+var_170]
0x180068796  call    ?Stop@?$ActivityBase@VAnimationClockLogging@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18006879b  nop
0x18006879c  mov     [rsp+1B0h+var_170], r14
0x1800687a1  lea     rcx, [rsp+1B0h+var_170]
0x1800687a6  call    ?Destroy@?$ActivityBase@VAnimationClockLogging@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800687ab  lea     rcx, [rbp+0B0h+var_50]; this
0x1800687af  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800687b4  lea     rcx, [rbp+0B0h+var_58]
0x1800687b8  call    ?reset@?$shared_object@V?$ActivityData@VAnimationClockLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VAnimationClockLogging@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AnimationClockLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800687bd  lea     rcx, [rsp+1B0h+var_168]
0x1800687c2  call    ??1?$ActivityData@VAnimationClockLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VAnimationClockLogging@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AnimationClockLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<AnimationClockLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800687c7  mov     eax, edi
0x1800687c9  mov     rcx, [rbp+0B0h+var_20]
0x1800687d0  xor     rcx, rsp; StackCookie
0x1800687d3  call    __security_check_cookie
0x1800687d8  lea     r11, [rsp+1B0h+var_10]
0x1800687e0  mov     rbx, [r11+28h]
0x1800687e4  mov     rsi, [r11+30h]
0x1800687e8  mov     rsp, r11
0x1800687eb  pop     r14
0x1800687ed  pop     rdi
0x1800687ee  pop     rbp
0x1800687ef  retn
0x1800687f0  mov     [rsp+1B0h+hObject], rdi
0x1800687f5  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800687fc  mov     rcx, [rax+30h]
0x180068800  mov     rcx, [rcx+20h]
0x180068804  mov     rax, [rcx]
0x180068807  lea     r8, [rsp+1B0h+hObject]
0x18006880c  mov     rax, [rax+0E0h]
0x180068813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068818  mov     edi, eax
0x18006881a  test    eax, eax
0x18006881c  js      loc_18006878F
0x180068822  mov     qword ptr [rsp+1B0h+var_180.Data1], 0
0x18006882b  lea     r8, [rsp+1B0h+var_180]; struct CAnimationTriggerProxy **
0x180068830  mov     rdx, [rsp+1B0h+hObject]; void *
0x180068835  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18006883c  mov     rcx, [rcx+30h]; this
0x180068840  call    ?CreateAnimationTriggerProxyFromSharedHandle@CCompositor@@QEAAJPEAXPEAPEAVCAnimationTriggerProxy@@@Z; CCompositor::CreateAnimationTriggerProxyFromSharedHandle(void *,CAnimationTriggerProxy * *)
0x180068845  mov     edi, eax
0x180068847  mov     rbx, qword ptr [rsp+1B0h+var_180.Data1]
0x18006884c  test    eax, eax
0x18006884e  js      short loc_18006885E
0x180068850  mov     rdx, [rsi+58h]; unsigned __int64
0x180068854  mov     rcx, rbx; this
0x180068857  call    ?Trigger@CAnimationTriggerProxy@@QEAAJ_K@Z; CAnimationTriggerProxy::Trigger(unsigned __int64)
0x18006885c  mov     edi, eax
0x18006885e  mov     rcx, [rsp+1B0h+hObject]; hObject
0x180068863  call    cs:__imp_CloseHandle
0x180068869  nop
0x18006886a  test    rbx, rbx
0x18006886d  jz      short loc_180068878
0x18006886f  mov     rcx, rbx; this
0x180068872  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x180068877  nop
0x180068878  jmp     loc_18006878F
0x18006887d  mov     rcx, [rbx]
0x180068880  call    cs:__imp_NtDCompositionCommitSynchronizationObject
0x180068886  test    eax, eax
0x180068888  jns     short loc_1800688B8
0x18006888a  mov     rcx, [rbp+0B8h]; this
0x180068891  mov     r9d, eax; char *
0x180068894  lea     r8, aClientcoreWind_83; "clientcore\\windows\\dwm\\udwm\\animati"...
0x18006889b  mov     edx, 0DAh; void *
0x1800688a0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800688a5  mov     ebx, eax
0x1800688a7  lea     rcx, [rsp+1B0h+var_170]; this
0x1800688ac  call    ??1TriggerClock@AnimationClockLoggingTelemetry@@QEAA@XZ; AnimationClockLoggingTelemetry::TriggerClock::~TriggerClock(void)
0x1800688b1  mov     eax, ebx
0x1800688b3  jmp     loc_1800687C9
0x1800688b8  mov     rcx, rbx
0x1800688bb  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$T@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(std::nullptr_t)
0x1800688c0  jmp     loc_180068784
```
