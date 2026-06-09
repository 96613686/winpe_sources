# CWwanAdditionalContextController::~CWwanAdditionalContextController(void)

- ea: `0x18004cd38`
- end: `0x18004ce78`
- name: `??1CWwanAdditionalContextController@@UEAA@XZ`
- size: `320`
- prototype: `void __fastcall(CWwanAdditionalContextController *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800273f0`

## callees

- `0x180014f1c`
- `0x180018abc`
- `0x180021df8`
- `0x180027110`
- `0x180047784`
- `0x18004cd38`
- `0x180050640`
- `0x1800aa424`

## import_xrefs

- `WwanPrfl!WwanProfileCleanup` at `0x18004ce45`
- `WwanPrfl!WwanProfileCleanup` at `0x18004ce45`
- `WwanPrfl!WwanProfileDeinit` at `0x18004ce4f`
- `WwanPrfl!WwanProfileDeinit` at `0x18004ce4f`
- `MobileNetworking!StopTimer` at `0x18004cd9a`
- `MobileNetworking!StopTimer` at `0x18004cd9a`
- `MobileNetworking!DeleteReadWriteLock` at `0x18004cdda`
- `MobileNetworking!DeleteReadWriteLock` at `0x18004cdda`
- `MobileNetworking!AcquireWriteLock` at `0x18004cd8a`
- `MobileNetworking!AcquireWriteLock` at `0x18004cd8a`
- `MobileNetworking!ReleaseWriteLock` at `0x18004cdb3`
- `MobileNetworking!ReleaseWriteLock` at `0x18004cdb3`
- `MobileNetworking!DeleteTimer` at `0x18004cdd1`
- `MobileNetworking!DeleteTimer` at `0x18004cdd1`

## string_xrefs

- `0x18004cdb9`: ` Timer Stop Completed`
- `0x18004cde0`: ` Timer Deinitialization Completed`

## pseudocode

```c
void __fastcall CWwanAdditionalContextController::~CWwanAdditionalContextController(
        CWwanAdditionalContextController *this)
{
  __int64 v2; // rbx
  std::_Ref_count_base *v3[2]; // [rsp+20h] [rbp-18h] BYREF

  *(_QWORD *)this = &CWwanAdditionalContextController::`vftable';
  CWWANContextControllerBase::SendConnectionIStreamDeletedEvent(this, 0x20u);
  if ( *((_DWORD *)this + 2046) )
  {
    AcquireWriteLock(
      *((_QWORD *)this + 1022),
      (char *)this + 8072,
      "CWwanAdditionalContextController::~CWwanAdditionalContextController",
      66);
    StopTimer(*((_QWORD *)this + 1022), "CWwanAdditionalContextController::~CWwanAdditionalContextController");
    ReleaseWriteLock(
      *((_QWORD *)this + 1022),
      (char *)this + 8072,
      "CWwanAdditionalContextController::~CWwanAdditionalContextController",
      68);
    WwanLog::Info("CWwanAdditionalContextController::~CWwanAdditionalContextController", 0, L" Timer Stop Completed");
    DeleteTimer(*((_QWORD *)this + 1022));
    DeleteReadWriteLock((char *)this + 8072);
    WwanLog::Info(
      "CWwanAdditionalContextController::~CWwanAdditionalContextController",
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
  WwanProfileCleanup((char *)this + 16);
  WwanProfileDeinit((char *)this + 16);
  CWwanContextLifeCycle::~CWwanContextLifeCycle((CWwanAdditionalContextController *)((char *)this + 8200));
  CWWANContextControllerBase::~CWWANContextControllerBase(this);
}

```

## disassembly

```asm
0x18004cd38  mov     [rsp+arg_0], rbx
0x18004cd3d  mov     [rsp+arg_8], rsi
0x18004cd42  push    rdi
0x18004cd43  sub     rsp, 30h
0x18004cd47  mov     rdi, rcx
0x18004cd4a  lea     rax, ??_7CWwanAdditionalContextController@@6B@; const CWwanAdditionalContextController::`vftable'
0x18004cd51  mov     [rcx], rax
0x18004cd54  mov     edx, 20h ; ' '; unsigned int
0x18004cd59  call    ?SendConnectionIStreamDeletedEvent@CWWANContextControllerBase@@IEAAXK@Z; CWWANContextControllerBase::SendConnectionIStreamDeletedEvent(ulong)
0x18004cd5e  lea     rbx, [rdi+1F88h]
0x18004cd65  mov     eax, [rbx+70h]
0x18004cd68  test    eax, eax
0x18004cd6a  jz      loc_18004CDF1
0x18004cd70  mov     r9d, 42h ; 'B'
0x18004cd76  lea     rsi, aCwwanadditiona_35; "CWwanAdditionalContextController::~CWwa"...
0x18004cd7d  mov     r8, rsi
0x18004cd80  mov     rdx, rbx
0x18004cd83  mov     rcx, [rdi+1FF0h]
0x18004cd8a  call    cs:__imp_AcquireWriteLock
0x18004cd90  mov     rdx, rsi
0x18004cd93  mov     rcx, [rdi+1FF0h]
0x18004cd9a  call    cs:__imp_StopTimer
0x18004cda0  mov     r9d, 44h ; 'D'
0x18004cda6  mov     r8, rsi
0x18004cda9  mov     rdx, rbx
0x18004cdac  mov     rcx, [rdi+1FF0h]
0x18004cdb3  call    cs:__imp_ReleaseWriteLock
0x18004cdb9  lea     r8, aTimerStopCompl_0; " Timer Stop Completed"
0x18004cdc0  xor     edx, edx; struct _GUID *
0x18004cdc2  mov     rcx, rsi; char *
0x18004cdc5  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18004cdca  mov     rcx, [rdi+1FF0h]
0x18004cdd1  call    cs:__imp_DeleteTimer
0x18004cdd7  mov     rcx, rbx
0x18004cdda  call    cs:__imp_DeleteReadWriteLock
0x18004cde0  lea     r8, aTimerDeinitial; " Timer Deinitialization Completed"
0x18004cde7  xor     edx, edx; struct _GUID *
0x18004cde9  mov     rcx, rsi; char *
0x18004cdec  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18004cdf1  lea     rsi, [rdi+1F40h]
0x18004cdf8  mov     rbx, [rsi]
0x18004cdfb  test    rbx, rbx
0x18004cdfe  jz      short loc_18004CE41
0x18004ce00  lea     rdx, [rbx+8]; struct _GUID *
0x18004ce04  mov     rcx, [rbx+28h]; this
0x18004ce08  call    ?RemoveProfileHandler@ProfileHolder@@QEAAXAEBU_GUID@@@Z; ProfileHolder::RemoveProfileHandler(_GUID const &)
0x18004ce0d  mov     qword ptr [rbx+28h], 0
0x18004ce15  mov     qword ptr [rbx], 0
0x18004ce1c  xorps   xmm0, xmm0
0x18004ce1f  movdqu  xmmword ptr [rsp+38h+var_18], xmm0
0x18004ce25  lea     rdx, [rsp+38h+var_18]
0x18004ce2a  mov     rcx, rsi
0x18004ce2d  call    ??4?$shared_ptr@VProfileHolder@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ProfileHolder>::operator=(std::shared_ptr<ProfileHolder> &&)
0x18004ce32  mov     rcx, [rsp+38h+var_18+8]; this
0x18004ce37  test    rcx, rcx
0x18004ce3a  jz      short loc_18004CE41
0x18004ce3c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004ce41  lea     rcx, [rdi+10h]
0x18004ce45  call    cs:__imp_WwanProfileCleanup
0x18004ce4b  lea     rcx, [rdi+10h]
0x18004ce4f  call    cs:__imp_WwanProfileDeinit
0x18004ce55  lea     rcx, [rdi+2008h]; this
0x18004ce5c  call    ??1CWwanContextLifeCycle@@QEAA@XZ; CWwanContextLifeCycle::~CWwanContextLifeCycle(void)
0x18004ce61  mov     rcx, rdi; this
0x18004ce64  mov     rbx, [rsp+38h+arg_0]
0x18004ce69  mov     rsi, [rsp+38h+arg_8]
0x18004ce6e  add     rsp, 30h
0x18004ce72  pop     rdi
0x18004ce73  jmp     ??1CWWANContextControllerBase@@UEAA@XZ; CWWANContextControllerBase::~CWWANContextControllerBase(void)
```
