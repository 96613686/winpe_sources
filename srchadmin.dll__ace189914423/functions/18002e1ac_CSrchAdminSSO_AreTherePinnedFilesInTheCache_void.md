# CSrchAdminSSO::_AreTherePinnedFilesInTheCache(void)

- ea: `0x18002e1ac`
- end: `0x18002e3d8`
- name: `?_AreTherePinnedFilesInTheCache@CSrchAdminSSO@@AEAAJXZ`
- size: `556`
- prototype: `__int64 __fastcall(CSrchAdminSSO *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002270`

## callees

- `0x1800038ac`
- `0x18000de7c`
- `0x18002e1ac`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e1e1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e1e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CSrchAdminSSO::_AreTherePinnedFilesInTheCache(CSrchAdminSSO *this)
{
  int v1; // ebx
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-30h] BYREF
  __int64 v4; // [rsp+38h] [rbp-28h] BYREF
  __int64 v5; // [rsp+40h] [rbp-20h] BYREF
  __int64 v6; // [rsp+48h] [rbp-18h] BYREF
  __int64 v7; // [rsp+50h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-8h] BYREF
  int v9; // [rsp+80h] [rbp+20h] BYREF
  int v10; // [rsp+84h] [rbp+24h]
  int v11; // [rsp+88h] [rbp+28h] BYREF
  __int64 v12; // [rsp+90h] [rbp+30h] BYREF
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // [rsp+98h] [rbp+38h] BYREF

  v10 = HIDWORD(this);
  v9 = 0;
  ppv = 0;
  v1 = CoCreateInstance(&CLSID_OfflineFilesCache, 0, 0x15u, &GUID_855d6203_7914_48b9_8d40_4c56f5acffc5, &ppv);
  if ( v1 >= 0 )
  {
    v7 = 0;
    v1 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
           ppv,
           &GUID_3836f049_9413_45dd_bf46_b5aaa82dc310,
           &v7);
    if ( v1 >= 0 )
    {
      v6 = 0;
      v1 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v7 + 24LL))(v7, 0, &v6);
      if ( v1 >= 0 )
      {
        v11 = 0;
        v3 = 0;
        while ( !v9 )
        {
          if ( v1 < 0 )
            break;
          v1 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v6 + 24LL))(
                 v6,
                 1,
                 &v3,
                 &v11);
          if ( v1 )
            break;
          v5 = 0;
          v1 = (**v3)(v3, &GUID_3836f049_9413_45dd_bf46_b5aaa82dc310, &v5);
          if ( v1 >= 0 )
          {
            v4 = 0;
            v1 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 24LL))(v5, 0, &v4);
            if ( v1 >= 0 )
            {
              v13 = 0;
              while ( !v9 )
              {
                if ( v1 < 0 )
                  break;
                v1 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v4 + 24LL))(
                       v4,
                       1,
                       &v13,
                       &v11);
                if ( v1 )
                  break;
                v12 = 0;
                v1 = (**v13)(v13, &GUID_623c58a2_42ed_4ad7_b69a_0f1b30a72d0d, &v12);
                if ( v1 >= 0 )
                {
                  v1 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 24LL))(v12, &v9);
                  if ( v1 >= 0 && !v9 )
                    v1 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 64LL))(v12, &v9);
                }
                ATL::CComPtrBase<ISearchRoot>::Release(&v13);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
              }
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
            }
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v4);
          }
          ATL::CComPtrBase<ISearchRoot>::Release(&v3);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v5);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v3);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
    if ( v1 >= 0 )
      v1 = v9 == 0;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18002e1ac  mov     [rsp-18h+arg_0], rcx
0x18002e1b1  push    rbp
0x18002e1b2  push    rbx
0x18002e1b3  push    rdi
0x18002e1b4  mov     rbp, rsp
0x18002e1b7  sub     rsp, 60h
0x18002e1bb  xor     edi, edi
0x18002e1bd  mov     dword ptr [rbp+arg_0], edi
0x18002e1c0  mov     [rbp+var_8], rdi
0x18002e1c4  lea     rax, [rbp+var_8]
0x18002e1c8  mov     [rsp+60h+ppv], rax; ppv
0x18002e1cd  lea     r9, _GUID_855d6203_7914_48b9_8d40_4c56f5acffc5; riid
0x18002e1d4  xor     edx, edx; pUnkOuter
0x18002e1d6  lea     r8d, [rdi+15h]; dwClsContext
0x18002e1da  lea     rcx, CLSID_OfflineFilesCache; rclsid
0x18002e1e1  call    cs:__imp_CoCreateInstance
0x18002e1e7  mov     ebx, eax
0x18002e1e9  test    eax, eax
0x18002e1eb  js      loc_18002E3C5
0x18002e1f1  mov     [rbp+var_10], rdi
0x18002e1f5  mov     rcx, [rbp+var_8]
0x18002e1f9  mov     rax, [rcx]
0x18002e1fc  lea     r8, [rbp+var_10]
0x18002e200  lea     rdx, _GUID_3836f049_9413_45dd_bf46_b5aaa82dc310
0x18002e207  mov     rax, [rax]
0x18002e20a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e20f  mov     ebx, eax
0x18002e211  test    eax, eax
0x18002e213  js      loc_18002E3B0
0x18002e219  mov     [rbp+var_18], rdi
0x18002e21d  mov     rcx, [rbp+var_10]
0x18002e221  mov     rax, [rcx]
0x18002e224  lea     r8, [rbp+var_18]
0x18002e228  xor     edx, edx
0x18002e22a  mov     rax, [rax+18h]
0x18002e22e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e233  mov     ebx, eax
0x18002e235  test    eax, eax
0x18002e237  js      loc_18002E3A6
0x18002e23d  mov     [rbp+arg_8], edi
0x18002e240  mov     [rbp+var_30], rdi
0x18002e244  jmp     loc_18002E393
0x18002e249  test    ebx, ebx
0x18002e24b  js      loc_18002E39C
0x18002e251  mov     rcx, [rbp+var_18]
0x18002e255  mov     rax, [rcx]
0x18002e258  lea     r9, [rbp+arg_8]
0x18002e25c  lea     r8, [rbp+var_30]
0x18002e260  mov     edx, 1
0x18002e265  mov     rax, [rax+18h]
0x18002e269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e26e  mov     ebx, eax
0x18002e270  test    eax, eax
0x18002e272  jnz     loc_18002E39C
0x18002e278  mov     [rbp+var_20], rdi
0x18002e27c  mov     rcx, [rbp+var_30]
0x18002e280  mov     rax, [rcx]
0x18002e283  lea     r8, [rbp+var_20]
0x18002e287  lea     rdx, _GUID_3836f049_9413_45dd_bf46_b5aaa82dc310
0x18002e28e  mov     rax, [rax]
0x18002e291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e296  mov     ebx, eax
0x18002e298  test    eax, eax
0x18002e29a  js      loc_18002E380
0x18002e2a0  mov     [rbp+var_28], rdi
0x18002e2a4  mov     rcx, [rbp+var_20]
0x18002e2a8  mov     rax, [rcx]
0x18002e2ab  lea     r8, [rbp+var_28]
0x18002e2af  xor     edx, edx
0x18002e2b1  mov     rax, [rax+18h]
0x18002e2b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2ba  mov     ebx, eax
0x18002e2bc  test    eax, eax
0x18002e2be  js      loc_18002E377
0x18002e2c4  mov     [rbp+arg_18], rdi
0x18002e2c8  jmp     loc_18002E364
0x18002e2cd  test    ebx, ebx
0x18002e2cf  js      loc_18002E36D
0x18002e2d5  mov     rcx, [rbp+var_28]
0x18002e2d9  mov     rax, [rcx]
0x18002e2dc  lea     r9, [rbp+arg_8]
0x18002e2e0  lea     r8, [rbp+arg_18]
0x18002e2e4  mov     edx, 1
0x18002e2e9  mov     rax, [rax+18h]
0x18002e2ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2f2  mov     ebx, eax
0x18002e2f4  test    eax, eax
0x18002e2f6  jnz     short loc_18002E36D
0x18002e2f8  mov     [rbp+arg_10], rdi
0x18002e2fc  mov     rcx, [rbp+arg_18]
0x18002e300  mov     rax, [rcx]
0x18002e303  lea     r8, [rbp+arg_10]
0x18002e307  lea     rdx, _GUID_623c58a2_42ed_4ad7_b69a_0f1b30a72d0d
0x18002e30e  mov     rax, [rax]
0x18002e311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e316  mov     ebx, eax
0x18002e318  test    eax, eax
0x18002e31a  js      short loc_18002E351
0x18002e31c  mov     rcx, [rbp+arg_10]
0x18002e320  mov     rax, [rcx]
0x18002e323  lea     rdx, [rbp+arg_0]
0x18002e327  mov     rax, [rax+18h]
0x18002e32b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e330  mov     ebx, eax
0x18002e332  test    eax, eax
0x18002e334  js      short loc_18002E351
0x18002e336  cmp     dword ptr [rbp+arg_0], edi
0x18002e339  jnz     short loc_18002E351
0x18002e33b  mov     rcx, [rbp+arg_10]
0x18002e33f  mov     rax, [rcx]
0x18002e342  lea     rdx, [rbp+arg_0]
0x18002e346  mov     rax, [rax+40h]
0x18002e34a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e34f  mov     ebx, eax
0x18002e351  lea     rcx, [rbp+arg_18]
0x18002e355  call    ?Release@?$CComPtrBase@UISearchRoot@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISearchRoot>::Release(void)
0x18002e35a  nop
0x18002e35b  lea     rcx, [rbp+arg_10]
0x18002e35f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e364  cmp     dword ptr [rbp+arg_0], edi
0x18002e367  jz      loc_18002E2CD
0x18002e36d  lea     rcx, [rbp+arg_18]
0x18002e371  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e376  nop
0x18002e377  lea     rcx, [rbp+var_28]
0x18002e37b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e380  lea     rcx, [rbp+var_30]
0x18002e384  call    ?Release@?$CComPtrBase@UISearchRoot@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISearchRoot>::Release(void)
0x18002e389  nop
0x18002e38a  lea     rcx, [rbp+var_20]
0x18002e38e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e393  cmp     dword ptr [rbp+arg_0], edi
0x18002e396  jz      loc_18002E249
0x18002e39c  lea     rcx, [rbp+var_30]
0x18002e3a0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e3a5  nop
0x18002e3a6  lea     rcx, [rbp+var_18]
0x18002e3aa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e3af  nop
0x18002e3b0  lea     rcx, [rbp+var_10]
0x18002e3b4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e3b9  test    ebx, ebx
0x18002e3bb  js      short loc_18002E3C5
0x18002e3bd  mov     ebx, edi
0x18002e3bf  cmp     dword ptr [rbp+arg_0], edi
0x18002e3c2  setz    bl
0x18002e3c5  lea     rcx, [rbp+var_8]
0x18002e3c9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e3ce  mov     eax, ebx
0x18002e3d0  add     rsp, 60h
0x18002e3d4  pop     rdi
0x18002e3d5  pop     rbx
0x18002e3d6  pop     rbp
0x18002e3d7  retn
```
