# SBECoreUtil::CDShowBroadcastEvent::Active(IFilterGraph *)

- ea: `0x18000dd0c`
- end: `0x18000deae`
- name: `?Active@CDShowBroadcastEvent@SBECoreUtil@@QEAAJPEAUIFilterGraph@@@Z`
- size: `418`
- prototype: `__int64 __fastcall(SBECoreUtil::CDShowBroadcastEvent *__hidden this, struct IFilterGraph *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000f500`

## callees

- `0x18000dd0c`
- `0x18000ea14`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000de93`
- `KERNEL32!LeaveCriticalSection` at `0x18000de93`
- `KERNEL32!EnterCriticalSection` at `0x18000dd28`
- `KERNEL32!EnterCriticalSection` at `0x18000dd28`
- `ole32!CoCreateInstance` at `0x18000ddd4`
- `ole32!CoCreateInstance` at `0x18000ddd4`

## pseudocode

```c
__int64 __fastcall SBECoreUtil::CDShowBroadcastEvent::Active(
        SBECoreUtil::CDShowBroadcastEvent *this,
        struct IFilterGraph *a2)
{
  HRESULT Instance; // ebx
  _QWORD *v5; // r14
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v7 = 0;
  v8 = 0;
  if ( a2 )
  {
    Instance = SBECoreUtil::CDShowBroadcastEvent::Inactive(this);
    if ( Instance < 0
      || (Instance = ((__int64 (__fastcall *)(struct IFilterGraph *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
                       a2,
                       &IID_IServiceProvider,
                       &v7),
          Instance < 0)
      || ((v5 = (_QWORD *)((char *)this + 48),
           Instance = (*(__int64 (__fastcall **)(__int64, GUID *, GUID *, char *))(*(_QWORD *)v7 + 24LL))(
                        v7,
                        &CLSID_BroadcastEventService,
                        &IID_IBroadcastEventEx,
                        (char *)this + 48),
           Instance < 0)
       || !*v5)
      && ((Instance = CoCreateInstance(&CLSID_BroadcastEventService, 0, 1u, &IID_IBroadcastEventEx, (LPVOID *)this + 6),
           Instance < 0)
       || (Instance = ((__int64 (__fastcall *)(struct IFilterGraph *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
                        a2,
                        &IID_IRegisterServiceProvider,
                        &v8),
           Instance < 0)
       || (Instance = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        &CLSID_BroadcastEventService,
                        *v5),
           Instance < 0)
       && (Instance = (*(__int64 (__fastcall **)(__int64, GUID *, GUID *, char *))(*(_QWORD *)v7 + 24LL))(
                        v7,
                        &CLSID_BroadcastEventService,
                        &IID_IBroadcastEventEx,
                        (char *)this + 48),
           Instance < 0)) )
    {
      SBECoreUtil::CDShowBroadcastEvent::Inactive(this);
    }
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      v7 = 0;
    }
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      v8 = 0;
    }
  }
  else
  {
    Instance = -2147024809;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000dd0c  mov     [rsp+arg_10], rbx
0x18000dd11  mov     [rsp+arg_18], rbp
0x18000dd16  push    rsi
0x18000dd17  push    rdi
0x18000dd18  push    r14
0x18000dd1a  sub     rsp, 30h
0x18000dd1e  mov     rdi, rcx
0x18000dd21  mov     rsi, rdx
0x18000dd24  add     rcx, 8; lpCriticalSection
0x18000dd28  call    cs:__imp_EnterCriticalSection
0x18000dd2e  mov     [rsp+48h+arg_0], 0
0x18000dd37  mov     [rsp+48h+arg_8], 0
0x18000dd40  test    rsi, rsi
0x18000dd43  jnz     short loc_18000DD4F
0x18000dd45  mov     ebx, 80070057h
0x18000dd4a  jmp     loc_18000DE8F
0x18000dd4f  mov     rcx, rdi; this
0x18000dd52  call    ?Inactive@CDShowBroadcastEvent@SBECoreUtil@@QEAAJXZ; SBECoreUtil::CDShowBroadcastEvent::Inactive(void)
0x18000dd57  mov     ebx, eax
0x18000dd59  test    eax, eax
0x18000dd5b  js      loc_18000DE49
0x18000dd61  mov     rax, [rsi]
0x18000dd64  lea     r8, [rsp+48h+arg_0]
0x18000dd69  lea     rdx, IID_IServiceProvider
0x18000dd70  mov     rcx, rsi
0x18000dd73  mov     rax, [rax]
0x18000dd76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd7b  mov     ebx, eax
0x18000dd7d  test    eax, eax
0x18000dd7f  js      loc_18000DE49
0x18000dd85  mov     rcx, [rsp+48h+arg_0]
0x18000dd8a  lea     r14, [rdi+30h]
0x18000dd8e  mov     r9, r14
0x18000dd91  lea     r8, IID_IBroadcastEventEx
0x18000dd98  lea     rdx, CLSID_BroadcastEventService
0x18000dd9f  mov     rax, [rcx]
0x18000dda2  mov     rax, [rax+18h]
0x18000dda6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddab  mov     ebx, eax
0x18000ddad  test    eax, eax
0x18000ddaf  js      short loc_18000DDBB
0x18000ddb1  cmp     qword ptr [r14], 0
0x18000ddb5  jnz     loc_18000DE51
0x18000ddbb  xor     edx, edx; pUnkOuter
0x18000ddbd  mov     [rsp+48h+ppv], r14; ppv
0x18000ddc2  lea     r9, IID_IBroadcastEventEx; riid
0x18000ddc9  lea     rcx, CLSID_BroadcastEventService; rclsid
0x18000ddd0  lea     r8d, [rdx+1]; dwClsContext
0x18000ddd4  call    cs:__imp_CoCreateInstance
0x18000ddda  mov     ebx, eax
0x18000dddc  test    eax, eax
0x18000ddde  js      short loc_18000DE49
0x18000dde0  mov     rax, [rsi]
0x18000dde3  lea     r8, [rsp+48h+arg_8]
0x18000dde8  lea     rdx, IID_IRegisterServiceProvider
0x18000ddef  mov     rcx, rsi
0x18000ddf2  mov     rax, [rax]
0x18000ddf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddfa  mov     ebx, eax
0x18000ddfc  test    eax, eax
0x18000ddfe  js      short loc_18000DE49
0x18000de00  mov     rcx, [rsp+48h+arg_8]
0x18000de05  lea     rdx, CLSID_BroadcastEventService
0x18000de0c  mov     r8, [r14]
0x18000de0f  mov     rax, [rcx]
0x18000de12  mov     rax, [rax+18h]
0x18000de16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de1b  mov     ebx, eax
0x18000de1d  test    eax, eax
0x18000de1f  jns     short loc_18000DE51
0x18000de21  mov     rcx, [rsp+48h+arg_0]
0x18000de26  lea     r8, IID_IBroadcastEventEx
0x18000de2d  mov     r9, r14
0x18000de30  lea     rdx, CLSID_BroadcastEventService
0x18000de37  mov     rax, [rcx]
0x18000de3a  mov     rax, [rax+18h]
0x18000de3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de43  mov     ebx, eax
0x18000de45  test    eax, eax
0x18000de47  jns     short loc_18000DE51
0x18000de49  mov     rcx, rdi; this
0x18000de4c  call    ?Inactive@CDShowBroadcastEvent@SBECoreUtil@@QEAAJXZ; SBECoreUtil::CDShowBroadcastEvent::Inactive(void)
0x18000de51  mov     rcx, [rsp+48h+arg_0]
0x18000de56  test    rcx, rcx
0x18000de59  jz      short loc_18000DE70
0x18000de5b  mov     rax, [rcx]
0x18000de5e  mov     rax, [rax+10h]
0x18000de62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de67  mov     [rsp+48h+arg_0], 0
0x18000de70  mov     rcx, [rsp+48h+arg_8]
0x18000de75  test    rcx, rcx
0x18000de78  jz      short loc_18000DE8F
0x18000de7a  mov     rax, [rcx]
0x18000de7d  mov     rax, [rax+10h]
0x18000de81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de86  mov     [rsp+48h+arg_8], 0
0x18000de8f  lea     rcx, [rdi+8]; lpCriticalSection
0x18000de93  call    cs:__imp_LeaveCriticalSection
0x18000de99  mov     rbp, [rsp+48h+arg_18]
0x18000de9e  mov     eax, ebx
0x18000dea0  mov     rbx, [rsp+48h+arg_10]
0x18000dea5  add     rsp, 30h
0x18000dea9  pop     r14
0x18000deab  pop     rdi
0x18000deac  pop     rsi
0x18000dead  retn
```
