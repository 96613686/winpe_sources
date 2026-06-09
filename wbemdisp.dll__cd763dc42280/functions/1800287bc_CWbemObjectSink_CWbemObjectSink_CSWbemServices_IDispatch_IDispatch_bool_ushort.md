# CWbemObjectSink::CWbemObjectSink(CSWbemServices *,IDispatch *,IDispatch *,bool,ushort *)

- ea: `0x1800287bc`
- end: `0x180028999`
- name: `??0CWbemObjectSink@@QEAA@PEAVCSWbemServices@@PEAUIDispatch@@1_NPEAG@Z`
- size: `477`
- prototype: `CWbemObjectSink *(CWbemObjectSink *__hidden this, struct CSWbemServices *, struct IDispatch *, struct IDispatch *, bool, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180028d54`

## callees

- `0x180007bd0`
- `0x18001d9e0`
- `0x1800287bc`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002890e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002890e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180028847`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180028847`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180028808`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180028808`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180028816`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180028922`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180028816`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180028922`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CWbemObjectSink *__fastcall CWbemObjectSink::CWbemObjectSink(
        CWbemObjectSink *this,
        struct CSWbemServices *a2,
        struct IDispatch *a3,
        struct IDispatch *a4,
        bool a5,
        unsigned __int16 *psz)
{
  _DWORD *Value; // rax
  _QWORD *v11; // rax
  unsigned __int16 *v12; // rax
  CSWbemServices *v13; // rcx
  __int64 v14; // rcx
  _QWORD *v16; // [rsp+50h] [rbp+8h] BYREF
  __int64 v17; // [rsp+58h] [rbp+10h] BYREF

  *(_QWORD *)this = &CWbemObjectSink::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  if ( CIWbemObjectSinkMethodCache::sm_dwTlsForInterfaceCache != -1 )
  {
    Value = TlsGetValue(CIWbemObjectSinkMethodCache::sm_dwTlsForInterfaceCache);
    if ( Value )
    {
      ++*Value;
    }
    else
    {
      v11 = CWin32DefaultArena::WbemMemAlloc(0x20u);
      v16 = v11;
      if ( v11 )
      {
        *v11 = 1;
        v11[1] = 0;
        v11[2] = 0;
        v11[3] = 0;
      }
      else
      {
        v11 = 0;
      }
      TlsSetValue(CIWbemObjectSinkMethodCache::sm_dwTlsForInterfaceCache, v11);
    }
  }
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_BYTE *)this + 56) = a5;
  *((_QWORD *)this + 4) = a4;
  *((_QWORD *)this + 6) = 0;
  *(_WORD *)((char *)this + 57) = 1;
  if ( a3 )
  {
    v17 = 0;
    if ( ((__int64 (__fastcall *)(struct IDispatch *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
           a3,
           &IID_ISWbemPrivateSinkLocator,
           &v17) >= 0 )
    {
      if ( v17 )
      {
        v16 = 0;
        if ( (*(int (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v17 + 24LL))(v17, &v16) >= 0 && v16 )
        {
          (*(void (__fastcall **)(_QWORD *, GUID *, char *))*v16)(v16, &IID_ISWbemPrivateSink, (char *)this + 24);
          (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
  }
  if ( psz )
    *((_QWORD *)this + 6) = SysAllocString(psz);
  if ( a2 )
  {
    v12 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0xA8u);
    psz = v12;
    if ( v12 )
      v13 = CSWbemServices::CSWbemServices((CSWbemServices *)v12, a2, 0);
    else
      v13 = 0;
    *((_QWORD *)this + 1) = v13;
    if ( v13 )
      (*(void (__fastcall **)(CSWbemServices *))(*(_QWORD *)v13 + 8LL))(v13);
    *((_QWORD *)this + 2) = CSWbemServices::GetCachedUnsecuredApartment(a2);
  }
  v14 = *((_QWORD *)this + 4);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  _InterlockedIncrement(&g_cObj);
  return this;
}

```

## disassembly

```asm
0x1800287bc  mov     [rsp+arg_10], rbx
0x1800287c1  push    rbp
0x1800287c2  push    rsi
0x1800287c3  push    rdi
0x1800287c4  push    r14
0x1800287c6  push    r15
0x1800287c8  sub     rsp, 20h
0x1800287cc  mov     rbp, r9
0x1800287cf  mov     rsi, r8
0x1800287d2  mov     rdi, rdx
0x1800287d5  mov     rbx, rcx
0x1800287d8  lea     rax, ??_7CWbemObjectSink@@6B@; const CWbemObjectSink::`vftable'
0x1800287df  mov     [rcx], rax
0x1800287e2  xor     r15d, r15d
0x1800287e5  mov     [rcx+8], r15
0x1800287e9  mov     [rcx+10h], r15
0x1800287ed  mov     [rcx+40h], r15
0x1800287f1  mov     [rcx+48h], r15
0x1800287f5  mov     [rcx+50h], r15
0x1800287f9  mov     [rcx+58h], r15
0x1800287fd  mov     ecx, cs:?sm_dwTlsForInterfaceCache@CIWbemObjectSinkMethodCache@@1KA; dwTlsIndex
0x180028803  cmp     ecx, 0FFFFFFFFh
0x180028806  jz      short loc_180028851
0x180028808  call    cs:__imp_TlsGetValue
0x18002880e  test    rax, rax
0x180028811  jnz     short loc_18002884F
0x180028813  lea     ecx, [rax+20h]
0x180028816  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002881c  mov     [rsp+48h+arg_0], rax
0x180028821  test    rax, rax
0x180028824  jz      short loc_18002883B
0x180028826  mov     qword ptr [rax], 1
0x18002882d  mov     [rax+8], r15
0x180028831  mov     [rax+10h], r15
0x180028835  mov     [rax+18h], r15
0x180028839  jmp     short loc_18002883E
0x18002883b  mov     rax, r15
0x18002883e  mov     rdx, rax; lpTlsValue
0x180028841  mov     ecx, cs:?sm_dwTlsForInterfaceCache@CIWbemObjectSinkMethodCache@@1KA; dwTlsIndex
0x180028847  call    cs:__imp_TlsSetValue
0x18002884d  jmp     short loc_180028851
0x18002884f  inc     dword ptr [rax]
0x180028851  mov     [rbx+60h], r15d
0x180028855  mov     [rbx+28h], r15
0x180028859  mov     [rbx+18h], r15
0x18002885d  mov     al, [rsp+48h+arg_20]
0x180028861  mov     [rbx+38h], al
0x180028864  mov     [rbx+20h], rbp
0x180028868  mov     [rbx+30h], r15
0x18002886c  mov     word ptr [rbx+39h], 1
0x180028872  test    rsi, rsi
0x180028875  jz      loc_180028904
0x18002887b  mov     [rsp+48h+arg_8], r15
0x180028880  mov     rax, [rsi]
0x180028883  lea     r8, [rsp+48h+arg_8]
0x180028888  lea     rdx, IID_ISWbemPrivateSinkLocator
0x18002888f  mov     rcx, rsi
0x180028892  mov     rax, [rax]
0x180028895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002889a  test    eax, eax
0x18002889c  js      short loc_180028904
0x18002889e  mov     rcx, [rsp+48h+arg_8]
0x1800288a3  test    rcx, rcx
0x1800288a6  jz      short loc_180028904
0x1800288a8  mov     [rsp+48h+arg_0], r15
0x1800288ad  mov     rax, [rcx]
0x1800288b0  lea     rdx, [rsp+48h+arg_0]
0x1800288b5  mov     rax, [rax+18h]
0x1800288b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288be  test    eax, eax
0x1800288c0  js      short loc_1800288F3
0x1800288c2  mov     rcx, [rsp+48h+arg_0]
0x1800288c7  test    rcx, rcx
0x1800288ca  jz      short loc_1800288F3
0x1800288cc  mov     rax, [rcx]
0x1800288cf  lea     r8, [rbx+18h]
0x1800288d3  lea     rdx, IID_ISWbemPrivateSink
0x1800288da  mov     rax, [rax]
0x1800288dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288e2  mov     rcx, [rsp+48h+arg_0]
0x1800288e7  mov     rax, [rcx]
0x1800288ea  mov     rax, [rax+10h]
0x1800288ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288f3  mov     rcx, [rsp+48h+arg_8]
0x1800288f8  mov     rax, [rcx]
0x1800288fb  mov     rax, [rax+10h]
0x1800288ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028904  mov     rcx, [rsp+48h+psz]; psz
0x180028909  test    rcx, rcx
0x18002890c  jz      short loc_180028918
0x18002890e  call    cs:__imp_SysAllocString
0x180028914  mov     [rbx+30h], rax
0x180028918  test    rdi, rdi
0x18002891b  jz      short loc_180028969
0x18002891d  mov     ecx, 0A8h
0x180028922  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180028928  mov     [rsp+48h+psz], rax
0x18002892d  test    rax, rax
0x180028930  jz      short loc_180028945
0x180028932  xor     r8d, r8d; struct CSWbemSecurity *
0x180028935  mov     rdx, rdi; struct CSWbemServices *
0x180028938  mov     rcx, rax; this
0x18002893b  call    ??0CSWbemServices@@QEAA@PEAV0@PEAVCSWbemSecurity@@@Z; CSWbemServices::CSWbemServices(CSWbemServices *,CSWbemSecurity *)
0x180028940  mov     rcx, rax
0x180028943  jmp     short loc_180028948
0x180028945  mov     rcx, r15
0x180028948  mov     [rbx+8], rcx
0x18002894c  test    rcx, rcx
0x18002894f  jz      short loc_18002895D
0x180028951  mov     rax, [rcx]
0x180028954  mov     rax, [rax+8]
0x180028958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002895d  mov     rcx, rdi; this
0x180028960  call    ?GetCachedUnsecuredApartment@CSWbemServices@@QEAAPEAUIUnsecuredApartment@@XZ; CSWbemServices::GetCachedUnsecuredApartment(void)
0x180028965  mov     [rbx+10h], rax
0x180028969  mov     rcx, [rbx+20h]
0x18002896d  test    rcx, rcx
0x180028970  jz      short loc_18002897E
0x180028972  mov     rax, [rcx]
0x180028975  mov     rax, [rax+8]
0x180028979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002897e  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180028985  mov     rax, rbx
0x180028988  mov     rbx, [rsp+48h+arg_10]
0x18002898d  add     rsp, 20h
0x180028991  pop     r15
0x180028993  pop     r14
0x180028995  pop     rdi
0x180028996  pop     rsi
0x180028997  pop     rbp
0x180028998  retn
```
