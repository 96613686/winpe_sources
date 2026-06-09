# CMSSAdmin::ForceSaveCrawlScopeManager(void)

- ea: `0x18001fed4`
- end: `0x18001ffd0`
- name: `?ForceSaveCrawlScopeManager@CMSSAdmin@@QEAAJXZ`
- size: `252`
- prototype: `__int64 __fastcall(CMSSAdmin *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800129c0`

## callees

- `0x1800038ac`
- `0x18001fed4`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ff07`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ff07`

## pseudocode

```c
__int64 __fastcall CMSSAdmin::ForceSaveCrawlScopeManager(CMSSAdmin *this)
{
  HRESULT v1; // ebx
  __int64 (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // r9
  __int64 v3; // rcx
  CMSSAdmin *v5; // [rsp+50h] [rbp+18h] BYREF
  __int64 v6; // [rsp+58h] [rbp+20h] BYREF
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp+28h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+30h] BYREF

  v5 = this;
  ppv = 0;
  v1 = CoCreateInstance(
         &GUID_7d096c5f_ac08_4f1f_beb7_5c22c517ce39,
         0,
         0x15u,
         &GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69,
         &ppv);
  v2 = 0;
  v7 = 0;
  if ( v1 >= 0 )
  {
    v1 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, _QWORD *))(*(_QWORD *)ppv + 80LL))(
           ppv,
           L"SystemIndex",
           &v7);
    v2 = v7;
  }
  v3 = 0;
  v6 = 0;
  if ( v1 >= 0 )
  {
    v1 = (**v2)(v2, &GUID_8ada2082_613c_4f68_860e_1d1730883abc, &v6);
    v3 = v6;
  }
  v5 = 0;
  if ( v1 >= 0 )
  {
    v1 = (*(__int64 (__fastcall **)(__int64, __int64, CMSSAdmin **))(*(_QWORD *)v3 + 24LL))(v3, 5, &v5);
    if ( v1 >= 0 )
      v1 = (*(__int64 (__fastcall **)(CMSSAdmin *))(*(_QWORD *)v5 + 128LL))(v5);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v5);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001fed4  mov     [rsp-10h+arg_0], rcx
0x18001fed9  push    rbp
0x18001feda  push    rbx
0x18001fedb  mov     rbp, rsp
0x18001fede  sub     rsp, 38h
0x18001fee2  mov     [rbp+arg_18], 0
0x18001feea  lea     rax, [rbp+arg_18]
0x18001feee  mov     [rsp+38h+ppv], rax; ppv
0x18001fef3  lea     r9, _GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69; riid
0x18001fefa  xor     edx, edx; pUnkOuter
0x18001fefc  lea     r8d, [rdx+15h]; dwClsContext
0x18001ff00  lea     rcx, _GUID_7d096c5f_ac08_4f1f_beb7_5c22c517ce39; rclsid
0x18001ff07  call    cs:__imp_CoCreateInstance
0x18001ff0d  mov     ebx, eax
0x18001ff0f  xor     r9d, r9d
0x18001ff12  mov     [rbp+arg_10], r9
0x18001ff16  test    eax, eax
0x18001ff18  js      short loc_18001FF3B
0x18001ff1a  mov     rcx, [rbp+arg_18]
0x18001ff1e  mov     rax, [rcx]
0x18001ff21  lea     r8, [rbp+arg_10]
0x18001ff25  lea     rdx, aSystemindex; "SystemIndex"
0x18001ff2c  mov     rax, [rax+50h]
0x18001ff30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff35  mov     ebx, eax
0x18001ff37  mov     r9, [rbp+arg_10]
0x18001ff3b  xor     ecx, ecx
0x18001ff3d  mov     [rbp+arg_8], rcx
0x18001ff41  test    ebx, ebx
0x18001ff43  js      short loc_18001FF64
0x18001ff45  mov     rax, [r9]
0x18001ff48  lea     r8, [rbp+arg_8]
0x18001ff4c  lea     rdx, _GUID_8ada2082_613c_4f68_860e_1d1730883abc
0x18001ff53  mov     rcx, r9
0x18001ff56  mov     rax, [rax]
0x18001ff59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff5e  mov     ebx, eax
0x18001ff60  mov     rcx, [rbp+arg_8]
0x18001ff64  mov     [rbp+arg_0], 0
0x18001ff6c  test    ebx, ebx
0x18001ff6e  js      short loc_18001FFA0
0x18001ff70  mov     rax, [rcx]
0x18001ff73  lea     r8, [rbp+arg_0]
0x18001ff77  mov     edx, 5
0x18001ff7c  mov     rax, [rax+18h]
0x18001ff80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff85  mov     ebx, eax
0x18001ff87  test    eax, eax
0x18001ff89  js      short loc_18001FFA0
0x18001ff8b  mov     rcx, [rbp+arg_0]
0x18001ff8f  mov     rax, [rcx]
0x18001ff92  mov     rax, [rax+80h]
0x18001ff99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff9e  mov     ebx, eax
0x18001ffa0  lea     rcx, [rbp+arg_0]
0x18001ffa4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ffa9  nop
0x18001ffaa  lea     rcx, [rbp+arg_8]
0x18001ffae  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ffb3  nop
0x18001ffb4  lea     rcx, [rbp+arg_10]
0x18001ffb8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ffbd  nop
0x18001ffbe  lea     rcx, [rbp+arg_18]
0x18001ffc2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ffc7  mov     eax, ebx
0x18001ffc9  add     rsp, 38h
0x18001ffcd  pop     rbx
0x18001ffce  pop     rbp
0x18001ffcf  retn
```
