# SBFThunk::CSBFEventCache::Active(IFilterGraph *)

- ea: `0x180047040`
- end: `0x18004720e`
- name: `?Active@CSBFEventCache@SBFThunk@@UEAAJPEAUIFilterGraph@@@Z`
- size: `462`
- prototype: `__int64 __fastcall(SBFThunk::CSBFEventCache *__hidden this, struct IFilterGraph *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001c00`
- `0x180047040`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800471e4`
- `KERNEL32!LeaveCriticalSection` at `0x1800471e4`
- `KERNEL32!EnterCriticalSection` at `0x18004706b`
- `KERNEL32!EnterCriticalSection` at `0x18004706b`
- `ole32!CoCreateInstance` at `0x18004711e`
- `ole32!CoCreateInstance` at `0x18004711e`

## pseudocode

```c
__int64 __fastcall SBFThunk::CSBFEventCache::Active(LPVOID *this, struct IFilterGraph *a2)
{
  HRESULT Instance; // ebx
  _QWORD *v5; // r14
  __int64 v7; // [rsp+30h] [rbp-38h] BYREF
  __int64 v8; // [rsp+38h] [rbp-30h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)(this + 7));
  v7 = 0;
  v8 = 0;
  if ( a2 )
  {
    Instance = (*((__int64 (__fastcall **)(LPVOID *))*this + 4))(this);
    if ( Instance < 0
      || (Instance = ((__int64 (__fastcall *)(struct IFilterGraph *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
                       a2,
                       &IID_IServiceProvider,
                       &v7),
          Instance < 0)
      || ((v5 = this + 12,
           Instance = (*(__int64 (__fastcall **)(__int64, GUID *, GUID *, char *))(*(_QWORD *)v7 + 24LL))(
                        v7,
                        &CLSID_BroadcastEventService,
                        &IID_IBroadcastEventEx,
                        (char *)this + 96),
           Instance < 0)
       || !*v5)
      && ((Instance = CoCreateInstance(&CLSID_BroadcastEventService, 0, 1u, &IID_IBroadcastEventEx, this + 12),
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
                        (char *)this + 96),
           Instance < 0)) )
    {
      (*((void (__fastcall **)(LPVOID *))*this + 4))(this);
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
  LeaveCriticalSection((LPCRITICAL_SECTION)(this + 7));
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180047040  mov     [rsp+arg_10], rbx
0x180047045  mov     [rsp+arg_18], rbp
0x18004704a  push    rsi
0x18004704b  push    rdi
0x18004704c  push    r14
0x18004704e  sub     rsp, 50h
0x180047052  mov     rax, cs:__security_cookie
0x180047059  xor     rax, rsp
0x18004705c  mov     [rsp+68h+var_28], rax
0x180047061  mov     rdi, rcx
0x180047064  mov     rsi, rdx
0x180047067  add     rcx, 38h ; '8'; lpCriticalSection
0x18004706b  call    cs:__imp_EnterCriticalSection
0x180047071  mov     [rsp+68h+var_38], 0
0x18004707a  mov     [rsp+68h+var_30], 0
0x180047083  test    rsi, rsi
0x180047086  jnz     short loc_180047092
0x180047088  mov     ebx, 80070057h
0x18004708d  jmp     loc_1800471E0
0x180047092  mov     rax, [rdi]
0x180047095  mov     rcx, rdi
0x180047098  mov     rax, [rax+20h]
0x18004709c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470a1  mov     ebx, eax
0x1800470a3  test    eax, eax
0x1800470a5  js      loc_180047193
0x1800470ab  mov     rax, [rsi]
0x1800470ae  lea     r8, [rsp+68h+var_38]
0x1800470b3  lea     rdx, IID_IServiceProvider
0x1800470ba  mov     rcx, rsi
0x1800470bd  mov     rax, [rax]
0x1800470c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470c5  mov     ebx, eax
0x1800470c7  test    eax, eax
0x1800470c9  js      loc_180047193
0x1800470cf  mov     rcx, [rsp+68h+var_38]
0x1800470d4  lea     r14, [rdi+60h]
0x1800470d8  mov     r9, r14
0x1800470db  lea     r8, IID_IBroadcastEventEx
0x1800470e2  lea     rdx, CLSID_BroadcastEventService
0x1800470e9  mov     rax, [rcx]
0x1800470ec  mov     rax, [rax+18h]
0x1800470f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470f5  mov     ebx, eax
0x1800470f7  test    eax, eax
0x1800470f9  js      short loc_180047105
0x1800470fb  cmp     qword ptr [r14], 0
0x1800470ff  jnz     loc_1800471A2
0x180047105  xor     edx, edx; pUnkOuter
0x180047107  mov     [rsp+68h+ppv], r14; ppv
0x18004710c  lea     r9, IID_IBroadcastEventEx; riid
0x180047113  lea     rcx, CLSID_BroadcastEventService; rclsid
0x18004711a  lea     r8d, [rdx+1]; dwClsContext
0x18004711e  call    cs:__imp_CoCreateInstance
0x180047124  mov     ebx, eax
0x180047126  test    eax, eax
0x180047128  js      short loc_180047193
0x18004712a  mov     rax, [rsi]
0x18004712d  lea     r8, [rsp+68h+var_30]
0x180047132  lea     rdx, IID_IRegisterServiceProvider
0x180047139  mov     rcx, rsi
0x18004713c  mov     rax, [rax]
0x18004713f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047144  mov     ebx, eax
0x180047146  test    eax, eax
0x180047148  js      short loc_180047193
0x18004714a  mov     rcx, [rsp+68h+var_30]
0x18004714f  lea     rdx, CLSID_BroadcastEventService
0x180047156  mov     r8, [r14]
0x180047159  mov     rax, [rcx]
0x18004715c  mov     rax, [rax+18h]
0x180047160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047165  mov     ebx, eax
0x180047167  test    eax, eax
0x180047169  jns     short loc_1800471A2
0x18004716b  mov     rcx, [rsp+68h+var_38]
0x180047170  lea     r8, IID_IBroadcastEventEx
0x180047177  mov     r9, r14
0x18004717a  lea     rdx, CLSID_BroadcastEventService
0x180047181  mov     rax, [rcx]
0x180047184  mov     rax, [rax+18h]
0x180047188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004718d  mov     ebx, eax
0x18004718f  test    eax, eax
0x180047191  jns     short loc_1800471A2
0x180047193  mov     rax, [rdi]
0x180047196  mov     rcx, rdi
0x180047199  mov     rax, [rax+20h]
0x18004719d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471a2  mov     rcx, [rsp+68h+var_38]
0x1800471a7  test    rcx, rcx
0x1800471aa  jz      short loc_1800471C1
0x1800471ac  mov     rax, [rcx]
0x1800471af  mov     rax, [rax+10h]
0x1800471b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471b8  mov     [rsp+68h+var_38], 0
0x1800471c1  mov     rcx, [rsp+68h+var_30]
0x1800471c6  test    rcx, rcx
0x1800471c9  jz      short loc_1800471E0
0x1800471cb  mov     rax, [rcx]
0x1800471ce  mov     rax, [rax+10h]
0x1800471d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471d7  mov     [rsp+68h+var_30], 0
0x1800471e0  lea     rcx, [rdi+38h]; lpCriticalSection
0x1800471e4  call    cs:__imp_LeaveCriticalSection
0x1800471ea  mov     eax, ebx
0x1800471ec  mov     rcx, [rsp+68h+var_28]
0x1800471f1  xor     rcx, rsp; StackCookie
0x1800471f4  call    __security_check_cookie
0x1800471f9  lea     r11, [rsp+68h+var_18]
0x1800471fe  mov     rbx, [r11+30h]
0x180047202  mov     rbp, [r11+38h]
0x180047206  mov     rsp, r11
0x180047209  pop     r14
0x18004720b  pop     rdi
0x18004720c  pop     rsi
0x18004720d  retn
```
