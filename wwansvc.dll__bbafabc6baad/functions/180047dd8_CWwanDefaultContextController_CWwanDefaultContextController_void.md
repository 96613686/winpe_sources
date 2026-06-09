# CWwanDefaultContextController::~CWwanDefaultContextController(void)

- ea: `0x180047dd8`
- end: `0x180047f31`
- name: `??1CWwanDefaultContextController@@UEAA@XZ`
- size: `345`
- prototype: `void __fastcall(CWwanDefaultContextController *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180047f80`

## callees

- `0x180014f1c`
- `0x180018abc`
- `0x180021df8`
- `0x180027110`
- `0x180047784`
- `0x180047dd8`
- `0x180050640`
- `0x1800aa424`

## import_xrefs

- `WwanPrfl!WwanProfileCleanup` at `0x180047e02`
- `WwanPrfl!WwanProfileCleanup` at `0x180047e1c`
- `WwanPrfl!WwanProfileCleanup` at `0x180047e02`
- `WwanPrfl!WwanProfileCleanup` at `0x180047e1c`
- `WwanPrfl!WwanProfileDeinit` at `0x180047e0c`
- `WwanPrfl!WwanProfileDeinit` at `0x180047e25`
- `WwanPrfl!WwanProfileDeinit` at `0x180047e0c`
- `WwanPrfl!WwanProfileDeinit` at `0x180047e25`
- `MobileNetworking!StopTimer` at `0x180047e67`
- `MobileNetworking!StopTimer` at `0x180047e67`
- `MobileNetworking!DeleteReadWriteLock` at `0x180047ea7`
- `MobileNetworking!DeleteReadWriteLock` at `0x180047ea7`
- `MobileNetworking!AcquireWriteLock` at `0x180047e57`
- `MobileNetworking!AcquireWriteLock` at `0x180047e57`
- `MobileNetworking!ReleaseWriteLock` at `0x180047e80`
- `MobileNetworking!ReleaseWriteLock` at `0x180047e80`
- `MobileNetworking!DeleteTimer` at `0x180047e9e`
- `MobileNetworking!DeleteTimer` at `0x180047e9e`

## string_xrefs

- `0x180047e86`: ` Timer Stop Completed`
- `0x180047ead`: ` Timer Deinitialization Completed`

## pseudocode

```c
void __fastcall CWwanDefaultContextController::~CWwanDefaultContextController(CWwanDefaultContextController *this)
{
  __int64 v2; // rbx
  std::_Ref_count_base *v3[2]; // [rsp+20h] [rbp-18h] BYREF

  *(_QWORD *)this = &CWwanDefaultContextController::`vftable';
  CWWANContextControllerBase::SendConnectionIStreamDeletedEvent(this, 2u);
  WwanProfileCleanup((char *)this + 16);
  WwanProfileDeinit((char *)this + 16);
  WwanProfileCleanup((char *)this + 11000);
  WwanProfileDeinit((char *)this + 11000);
  if ( *((_DWORD *)this + 2046) )
  {
    AcquireWriteLock(
      *((_QWORD *)this + 1022),
      (char *)this + 8072,
      "CWwanDefaultContextController::~CWwanDefaultContextController",
      134);
    StopTimer(*((_QWORD *)this + 1022), "CWwanDefaultContextController::~CWwanDefaultContextController");
    ReleaseWriteLock(
      *((_QWORD *)this + 1022),
      (char *)this + 8072,
      "CWwanDefaultContextController::~CWwanDefaultContextController",
      136);
    WwanLog::Info("CWwanDefaultContextController::~CWwanDefaultContextController", 0, L" Timer Stop Completed");
    DeleteTimer(*((_QWORD *)this + 1022));
    DeleteReadWriteLock((char *)this + 8072);
    WwanLog::Info(
      "CWwanDefaultContextController::~CWwanDefaultContextController",
      0,
      L" Timer Deinitialization Completed");
  }
  v2 = *((_QWORD *)this + 1000);
  if ( v2 )
  {
    ProfileHolder::RemoveProfileHandler(*(ProfileHolder **)(v2 + 40), (const struct _GUID *)(v2 + 8));
    *(_QWORD *)(v2 + 40) = 0;
    *(_QWORD *)v2 = 0;
    *(_OWORD *)v3 = 0;
    std::shared_ptr<ProfileHolder>::operator=((char *)this + 8000, v3);
    if ( v3[1] )
      std::_Ref_count_base::_Decref(v3[1]);
  }
  CWwanContextLifeCycle::~CWwanContextLifeCycle((CWwanDefaultContextController *)((char *)this + 8200));
  CWWANContextControllerBase::~CWWANContextControllerBase(this);
}

```

## disassembly

```asm
0x180047dd8  mov     [rsp+arg_0], rbx
0x180047ddd  mov     [rsp+arg_8], rsi
0x180047de2  push    rdi
0x180047de3  sub     rsp, 30h
0x180047de7  mov     rdi, rcx
0x180047dea  lea     rax, ??_7CWwanDefaultContextController@@6B@; const CWwanDefaultContextController::`vftable'
0x180047df1  mov     [rcx], rax
0x180047df4  mov     edx, 2; unsigned int
0x180047df9  call    ?SendConnectionIStreamDeletedEvent@CWWANContextControllerBase@@IEAAXK@Z; CWWANContextControllerBase::SendConnectionIStreamDeletedEvent(ulong)
0x180047dfe  lea     rcx, [rdi+10h]
0x180047e02  call    cs:__imp_WwanProfileCleanup
0x180047e08  lea     rcx, [rdi+10h]
0x180047e0c  call    cs:__imp_WwanProfileDeinit
0x180047e12  lea     rbx, [rdi+2AF8h]
0x180047e19  mov     rcx, rbx
0x180047e1c  call    cs:__imp_WwanProfileCleanup
0x180047e22  mov     rcx, rbx
0x180047e25  call    cs:__imp_WwanProfileDeinit
0x180047e2b  lea     rbx, [rdi+1F88h]
0x180047e32  mov     eax, [rbx+70h]
0x180047e35  test    eax, eax
0x180047e37  jz      loc_180047EBE
0x180047e3d  mov     r9d, 86h
0x180047e43  lea     rsi, aCwwandefaultco_34; "CWwanDefaultContextController::~CWwanDe"...
0x180047e4a  mov     r8, rsi
0x180047e4d  mov     rdx, rbx
0x180047e50  mov     rcx, [rdi+1FF0h]
0x180047e57  call    cs:__imp_AcquireWriteLock
0x180047e5d  mov     rdx, rsi
0x180047e60  mov     rcx, [rdi+1FF0h]
0x180047e67  call    cs:__imp_StopTimer
0x180047e6d  mov     r9d, 88h
0x180047e73  mov     r8, rsi
0x180047e76  mov     rdx, rbx
0x180047e79  mov     rcx, [rdi+1FF0h]
0x180047e80  call    cs:__imp_ReleaseWriteLock
0x180047e86  lea     r8, aTimerStopCompl_0; " Timer Stop Completed"
0x180047e8d  xor     edx, edx; struct _GUID *
0x180047e8f  mov     rcx, rsi; char *
0x180047e92  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180047e97  mov     rcx, [rdi+1FF0h]
0x180047e9e  call    cs:__imp_DeleteTimer
0x180047ea4  mov     rcx, rbx
0x180047ea7  call    cs:__imp_DeleteReadWriteLock
0x180047ead  lea     r8, aTimerDeinitial; " Timer Deinitialization Completed"
0x180047eb4  xor     edx, edx; struct _GUID *
0x180047eb6  mov     rcx, rsi; char *
0x180047eb9  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180047ebe  lea     rsi, [rdi+1F40h]
0x180047ec5  mov     rbx, [rsi]
0x180047ec8  test    rbx, rbx
0x180047ecb  jz      short loc_180047F0E
0x180047ecd  lea     rdx, [rbx+8]; struct _GUID *
0x180047ed1  mov     rcx, [rbx+28h]; this
0x180047ed5  call    ?RemoveProfileHandler@ProfileHolder@@QEAAXAEBU_GUID@@@Z; ProfileHolder::RemoveProfileHandler(_GUID const &)
0x180047eda  mov     qword ptr [rbx+28h], 0
0x180047ee2  mov     qword ptr [rbx], 0
0x180047ee9  xorps   xmm0, xmm0
0x180047eec  movdqu  xmmword ptr [rsp+38h+var_18], xmm0
0x180047ef2  lea     rdx, [rsp+38h+var_18]
0x180047ef7  mov     rcx, rsi
0x180047efa  call    ??4?$shared_ptr@VProfileHolder@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ProfileHolder>::operator=(std::shared_ptr<ProfileHolder> &&)
0x180047eff  mov     rcx, [rsp+38h+var_18+8]; this
0x180047f04  test    rcx, rcx
0x180047f07  jz      short loc_180047F0E
0x180047f09  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180047f0e  lea     rcx, [rdi+2008h]; this
0x180047f15  call    ??1CWwanContextLifeCycle@@QEAA@XZ; CWwanContextLifeCycle::~CWwanContextLifeCycle(void)
0x180047f1a  mov     rcx, rdi; this
0x180047f1d  mov     rbx, [rsp+38h+arg_0]
0x180047f22  mov     rsi, [rsp+38h+arg_8]
0x180047f27  add     rsp, 30h
0x180047f2b  pop     rdi
0x180047f2c  jmp     ??1CWWANContextControllerBase@@UEAA@XZ; CWWANContextControllerBase::~CWWANContextControllerBase(void)
```
