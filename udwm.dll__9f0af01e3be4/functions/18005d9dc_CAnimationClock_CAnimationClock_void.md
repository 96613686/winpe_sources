# CAnimationClock::~CAnimationClock(void)

- ea: `0x18005d9dc`
- end: `0x18005da69`
- name: `??1CAnimationClock@@UEAA@XZ`
- size: `141`
- prototype: `void __fastcall(CAnimationClock *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18005d9a0`

## callees

- `0x18001ce00`
- `0x18001ce3c`
- `0x18005d9dc`
- `0x18005da70`
- `0x18006ea4c`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005da37`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005da37`

## pseudocode

```c
void __fastcall CAnimationClock::~CAnimationClock(CAnimationClock *this)
{
  CTimer *v2; // rcx
  CBaseObject *v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &CAnimationClock::`vftable'{for `CBaseObject'};
  *((_QWORD *)this + 2) = &CAnimationClock::`vftable'{for `ITimerCallbackListener'};
  v2 = (CTimer *)*((_QWORD *)this + 8);
  if ( v2 )
    CTimer::SetTimerCallback(v2, 0);
  v3 = (CBaseObject *)*((_QWORD *)this + 8);
  if ( v3 )
  {
    CBaseObject::Release(v3);
    *((_QWORD *)this + 8) = 0;
  }
  v4 = *((_QWORD *)this + 13);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 13) = 0;
  }
  *((_QWORD *)this + 9) = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 112);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  CBaseObject::~CBaseObject(this);
}

```

## disassembly

```asm
0x18005d9dc  push    rbx
0x18005d9de  sub     rsp, 20h
0x18005d9e2  mov     rbx, rcx
0x18005d9e5  lea     rax, ??_7CAnimationClock@@6BCBaseObject@@@; const CAnimationClock::`vftable'{for `CBaseObject'}
0x18005d9ec  mov     [rcx], rax
0x18005d9ef  lea     rax, ??_7CAnimationClock@@6BITimerCallbackListener@@@; const CAnimationClock::`vftable'{for `ITimerCallbackListener'}
0x18005d9f6  mov     [rcx+10h], rax
0x18005d9fa  mov     rcx, [rcx+40h]; this
0x18005d9fe  test    rcx, rcx
0x18005da01  jnz     short loc_18005DA60
0x18005da03  mov     rcx, [rbx+40h]; this
0x18005da07  test    rcx, rcx
0x18005da0a  jz      short loc_18005DA19
0x18005da0c  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x18005da11  mov     qword ptr [rbx+40h], 0
0x18005da19  mov     rcx, [rbx+68h]
0x18005da1d  test    rcx, rcx
0x18005da20  jnz     short loc_18005DA4A
0x18005da22  mov     qword ptr [rbx+48h], 0
0x18005da2a  lea     rcx, [rbx+70h]
0x18005da2e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005da33  lea     rcx, [rbx+18h]; lpCriticalSection
0x18005da37  call    cs:__imp_DeleteCriticalSection
0x18005da3d  mov     rcx, rbx; this
0x18005da40  add     rsp, 20h
0x18005da44  pop     rbx
0x18005da45  jmp     ??1CBaseObject@@UEAA@XZ; CBaseObject::~CBaseObject(void)
0x18005da4a  mov     rax, [rcx]
0x18005da4d  mov     rax, [rax+10h]
0x18005da51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da56  mov     qword ptr [rbx+68h], 0
0x18005da5e  jmp     short loc_18005DA22
0x18005da60  xor     edx, edx; struct ITimerCallbackListener *
0x18005da62  call    ?SetTimerCallback@CTimer@@QEAAJPEAUITimerCallbackListener@@@Z; CTimer::SetTimerCallback(ITimerCallbackListener *)
0x18005da67  jmp     short loc_18005DA03
```
