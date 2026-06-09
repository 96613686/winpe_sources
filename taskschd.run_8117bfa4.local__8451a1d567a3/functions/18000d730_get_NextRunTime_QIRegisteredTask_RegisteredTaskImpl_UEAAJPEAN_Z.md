# ?get_NextRunTime@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAN@Z

- ea: `0x18000d730`
- end: `0x18000dad8`
- name: `?get_NextRunTime@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAN@Z`
- size: `936`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001880`
- `0x18000cd10`
- `0x18000d730`
- `0x18000deac`
- `0x18002e1a8`
- `0x180037cf0`
- `0x1800391c0`
- `0x18003b208`
- `0x18003e88c`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d841`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d8d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d841`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d8d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d7ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d7ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000d781`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000d781`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d99b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall _get_NextRunTime__QIRegisteredTask__RegisteredTaskImpl__UEAAJPEAN_Z(__int64 a1, _QWORD *a2)
{
  unsigned int v4; // edi
  __int64 v5; // rbx
  _QWORD *v6; // rdx
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // esi
  int v11; // esi
  void *v12; // rdx
  int v13; // r8d
  unsigned __int16 v14; // cx
  unsigned __int16 v15[2]; // [rsp+40h] [rbp-108h] BYREF
  int v16; // [rsp+44h] [rbp-104h]
  void *v17; // [rsp+48h] [rbp-100h]
  int v18; // [rsp+50h] [rbp-F8h]
  double v19; // [rsp+58h] [rbp-F0h] BYREF
  int v20; // [rsp+60h] [rbp-E8h]
  __int64 v21; // [rsp+68h] [rbp-E0h] BYREF
  void **pExceptionObject; // [rsp+70h] [rbp-D8h] BYREF
  char v23; // [rsp+78h] [rbp-D0h]
  __int64 *v24; // [rsp+80h] [rbp-C8h]
  __int64 v25; // [rsp+88h] [rbp-C0h]
  __int64 v26; // [rsp+90h] [rbp-B8h]
  int v27; // [rsp+98h] [rbp-B0h]
  __int64 v28; // [rsp+9Ch] [rbp-ACh]
  _BYTE v29[8]; // [rsp+E0h] [rbp-68h] BYREF
  void (__stdcall *v30)(LPVOID); // [rsp+E8h] [rbp-60h]
  double v31; // [rsp+F0h] [rbp-58h]
  struct _SYSTEMTIME v32; // [rsp+F8h] [rbp-50h] BYREF
  struct _SYSTEMTIME v33; // [rsp+108h] [rbp-40h] BYREF

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v4 = 0;
  v16 = 0;
  v33 = 0;
  GetLocalTime(&v33);
  v17 = 0;
  v18 = 0;
  v5 = (a1 + 16) & -(__int64)(a1 != 0);
  if ( v5 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  v21 = (a1 + 16) & -(__int64)(a1 != 0);
  v6 = (_QWORD *)(a1 + 80);
  if ( *(_QWORD *)(a1 + 104) >= 8u )
    v6 = (_QWORD *)*v6;
  if ( !*(_DWORD *)(a1 + 128) )
  {
    v4 = -2147023645;
    v16 = -2147023645;
    goto LABEL_31;
  }
  v7 = *(_QWORD *)(a1 + 136);
  if ( !v7 )
  {
    if ( v6 && *(_WORD *)v6 == 92 )
      v6 = (_QWORD *)((char *)v6 + 2);
    *(_QWORD *)&v32.wYear = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, GUID *, struct _SYSTEMTIME *))(**(_QWORD **)(a1 + 144) + 48LL))(
            *(_QWORD *)(a1 + 144),
            v6,
            &GUID_148bd524_a2ab_11ce_b11f_00aa00530503,
            &v32);
    if ( v11 >= 0 )
    {
      v15[0] = 1;
      v19 = 0.0;
      v11 = (*(__int64 (__fastcall **)(_QWORD, struct _SYSTEMTIME *, _QWORD, unsigned __int16 *, double *))(**(_QWORD **)&v32.wYear + 64LL))(
              *(_QWORD *)&v32.wYear,
              &v33,
              0,
              v15,
              &v19);
      if ( v11 >= 0 )
      {
        v29[0] = 0;
        v30 = CoTaskMemFree;
        v31 = v19;
        v12 = MIDL_user_allocate(16LL * v15[0]);
        v17 = v12;
        if ( !v12 )
        {
          v23 = 0;
          v24 = &qword_18007B2F0;
          v25 = 0;
          v26 = 0;
          v27 = 14;
          v28 = -1;
          pExceptionObject = &wmi::GenericException::`vftable';
          throw (wmi::OutOfMemoryException *)&pExceptionObject;
        }
        v13 = 0;
        v14 = v15[0];
        if ( v15[0] )
        {
          while ( 1 )
          {
            *((_OWORD *)v12 + v13) = *(_OWORD *)(*(_QWORD *)&v19 + 16LL * v13);
            ++v13;
            v14 = v15[0];
            if ( v13 >= v15[0] )
              break;
            v12 = v17;
          }
        }
        v18 = v14;
        wmi::ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>::~ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>(v29);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
        goto LABEL_36;
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
    v16 = v11;
    v4 = v11;
LABEL_31:
    ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(&v21);
    MIDL_user_free(v17);
    return v4;
  }
  v8 = RpcSession::Runtimes(v7, (_DWORD)v6, (unsigned int)&v33, 0);
  v4 = v8;
  v16 = v8;
  if ( v8 < 0 )
    goto LABEL_31;
  if ( v8 != 1 )
  {
    v9 = v8;
    goto LABEL_11;
  }
  v4 = 0;
  v16 = 0;
LABEL_36:
  v9 = 0;
LABEL_11:
  if ( v18 )
  {
    v32 = *(struct _SYSTEMTIME *)v17;
    v19 = 0.0;
    v20 = 0;
    ATL::AtlConvertSystemTimeToVariantTime(&v32, &v19);
    *a2 = *(_QWORD *)&v19;
    if ( v5 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
    MIDL_user_free(v17);
    return v4;
  }
  else
  {
    if ( !v9 )
    {
      v9 = 267012;
      v16 = 267012;
    }
    if ( v5 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
    MIDL_user_free(v17);
    return v9;
  }
}

```

## disassembly

```asm
0x18000d730  mov     r11, rsp
0x18000d733  mov     [r11+18h], rbx
0x18000d737  push    rsi
0x18000d738  push    rdi
0x18000d739  push    r12
0x18000d73b  push    r14
0x18000d73d  push    r15
0x18000d73f  sub     rsp, 120h
0x18000d746  mov     rax, cs:__security_cookie
0x18000d74d  xor     rax, rsp
0x18000d750  mov     [rsp+148h+var_30], rax
0x18000d758  mov     r15, rdx
0x18000d75b  mov     rsi, rcx
0x18000d75e  xor     r12d, r12d
0x18000d761  test    rdx, rdx
0x18000d764  jz      loc_18000D883
0x18000d76a  mov     [rdx], r12
0x18000d76d  mov     edi, r12d
0x18000d770  mov     [rsp+148h+var_104], r12d
0x18000d775  xorps   xmm0, xmm0
0x18000d778  movups  xmmword ptr [r11-40h], xmm0
0x18000d77d  lea     rcx, [r11-40h]; lpSystemTime
0x18000d781  call    cs:__imp_GetLocalTime
0x18000d788  nop     dword ptr [rax+rax+00h]
0x18000d78d  nop
0x18000d78e  mov     [rsp+148h+var_100], r12
0x18000d793  mov     [rsp+148h+var_F8], r12d
0x18000d798  mov     rax, rsi
0x18000d79b  lea     rcx, [rsi+10h]
0x18000d79f  neg     rax
0x18000d7a2  sbb     rbx, rbx
0x18000d7a5  and     rbx, rcx
0x18000d7a8  jz      short loc_18000D7BA
0x18000d7aa  lea     rcx, [rbx+8]; lpCriticalSection
0x18000d7ae  call    cs:__imp_EnterCriticalSection
0x18000d7b5  nop     dword ptr [rax+rax+00h]
0x18000d7ba  mov     [rsp+148h+var_E0], rbx
0x18000d7bf  lea     rdx, [rsi+50h]
0x18000d7c3  cmp     qword ptr [rdx+18h], 8
0x18000d7c8  jb      short loc_18000D7CD
0x18000d7ca  mov     rdx, [rdx]
0x18000d7cd  cmp     [rsi+80h], r12d
0x18000d7d4  jz      loc_18000D8EF
0x18000d7da  mov     rcx, [rsi+88h]
0x18000d7e1  test    rcx, rcx
0x18000d7e4  jz      loc_18000D90A
0x18000d7ea  lea     rax, [rsp+148h+var_100]
0x18000d7ef  mov     [rsp+148h+var_118], rax
0x18000d7f4  mov     r14d, 1
0x18000d7fa  mov     [rsp+148h+var_120], r14d
0x18000d7ff  xor     r9d, r9d
0x18000d802  lea     r8, [rsp+148h+var_40]
0x18000d80a  call    ?Runtimes@RpcSession@@QEBAJPEBGPEAU_SYSTEMTIME@@1KKAEAV?$RpcArray@U_SYSTEMTIME@@@@@Z; RpcSession::Runtimes(ushort const *,_SYSTEMTIME *,_SYSTEMTIME *,ulong,ulong,RpcArray<_SYSTEMTIME> &)
0x18000d80f  mov     edi, eax
0x18000d811  mov     [rsp+148h+var_104], eax
0x18000d815  test    eax, eax
0x18000d817  js      loc_18000DA45
0x18000d81d  cmp     eax, r14d
0x18000d820  jz      loc_18000D8FD
0x18000d826  mov     esi, eax
0x18000d828  mov     eax, [rsp+148h+var_F8]
0x18000d82c  test    eax, eax
0x18000d82e  jnz     short loc_18000D88A
0x18000d830  test    esi, esi
0x18000d832  jz      loc_18000DAC1
0x18000d838  test    rbx, rbx
0x18000d83b  jz      short loc_18000D84E
0x18000d83d  lea     rcx, [rbx+8]; lpCriticalSection
0x18000d841  call    cs:__imp_LeaveCriticalSection
0x18000d848  nop     dword ptr [rax+rax+00h]
0x18000d84d  nop
0x18000d84e  mov     rcx, [rsp+148h+var_100]; void *
0x18000d853  call    MIDL_user_free
0x18000d858  mov     eax, esi
0x18000d85a  mov     rcx, [rsp+148h+var_30]
0x18000d862  xor     rcx, rsp; StackCookie
0x18000d865  call    __security_check_cookie
0x18000d86a  mov     rbx, [rsp+148h+arg_10]
0x18000d872  add     rsp, 120h
0x18000d879  pop     r15
0x18000d87b  pop     r14
0x18000d87d  pop     r12
0x18000d87f  pop     rdi
0x18000d880  pop     rsi
0x18000d881  retn
0x18000d883  mov     eax, 80004003h
0x18000d888  jmp     short loc_18000D85A
0x18000d88a  mov     rax, [rsp+148h+var_100]
0x18000d88f  movups  xmm0, xmmword ptr [rax]
0x18000d892  movdqu  xmmword ptr [rsp+148h+var_50.wYear], xmm0
0x18000d89b  xorps   xmm1, xmm1
0x18000d89e  movsd   [rsp+148h+var_F0], xmm1
0x18000d8a4  mov     [rsp+148h+var_E8], r12d
0x18000d8a9  lea     rdx, [rsp+148h+var_F0]; double *
0x18000d8ae  lea     rcx, [rsp+148h+var_50]; struct _SYSTEMTIME *
0x18000d8b6  call    ?AtlConvertSystemTimeToVariantTime@ATL@@YAHAEBU_SYSTEMTIME@@PEAN@Z; ATL::AtlConvertSystemTimeToVariantTime(_SYSTEMTIME const &,double *)
0x18000d8bb  nop
0x18000d8bc  movsd   xmm0, [rsp+148h+var_F0]
0x18000d8c2  movsd   qword ptr [r15], xmm0
0x18000d8c7  test    rbx, rbx
0x18000d8ca  jz      short loc_18000D8DD
0x18000d8cc  lea     rcx, [rbx+8]; lpCriticalSection
0x18000d8d0  call    cs:__imp_LeaveCriticalSection
0x18000d8d7  nop     dword ptr [rax+rax+00h]
0x18000d8dc  nop
0x18000d8dd  mov     rcx, [rsp+148h+var_100]; void *
0x18000d8e2  call    MIDL_user_free
0x18000d8e7  nop
0x18000d8e8  mov     eax, edi
0x18000d8ea  jmp     loc_18000D85A
0x18000d8ef  mov     edi, 800704E3h
0x18000d8f4  mov     [rsp+148h+var_104], edi
0x18000d8f8  jmp     loc_18000DA45
0x18000d8fd  mov     edi, r12d
0x18000d900  mov     [rsp+148h+var_104], r12d
0x18000d905  jmp     loc_18000DAB9
0x18000d90a  test    rdx, rdx
0x18000d90d  jz      short loc_18000D919
0x18000d90f  cmp     word ptr [rdx], 5Ch ; '\'
0x18000d913  jnz     short loc_18000D919
0x18000d915  add     rdx, 2
0x18000d919  mov     qword ptr [rsp+148h+var_50.wYear], r12
0x18000d921  mov     rcx, [rsi+90h]
0x18000d928  mov     rax, [rcx]
0x18000d92b  lea     r9, [rsp+148h+var_50]
0x18000d933  lea     r8, _GUID_148bd524_a2ab_11ce_b11f_00aa00530503
0x18000d93a  mov     rax, [rax+30h]
0x18000d93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d943  mov     esi, eax
0x18000d945  test    eax, eax
0x18000d947  js      loc_18000DA32
0x18000d94d  mov     r14d, 1
0x18000d953  mov     [rsp+148h+var_108], r14w
0x18000d959  mov     [rsp+148h+var_F0], r12
0x18000d95e  mov     rcx, qword ptr [rsp+148h+var_50.wYear]
0x18000d966  mov     rax, [rcx]
0x18000d969  lea     rdx, [rsp+148h+var_F0]
0x18000d96e  mov     [rsp+148h+var_128], rdx
0x18000d973  lea     r9, [rsp+148h+var_108]
0x18000d978  xor     r8d, r8d
0x18000d97b  lea     rdx, [rsp+148h+var_40]
0x18000d983  mov     rax, [rax+40h]
0x18000d987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d98c  mov     esi, eax
0x18000d98e  test    eax, eax
0x18000d990  js      loc_18000DA32
0x18000d996  mov     rcx, [rsp+148h+var_F0]
0x18000d99b  mov     rax, cs:__imp_CoTaskMemFree
0x18000d9a2  mov     [rsp+148h+var_68], r12b
0x18000d9aa  mov     [rsp+148h+var_60], rax
0x18000d9b2  mov     [rsp+148h+var_58], rcx
0x18000d9ba  movzx   ecx, [rsp+148h+var_108]
0x18000d9bf  shl     rcx, 4; size
0x18000d9c3  call    MIDL_user_allocate
0x18000d9c8  mov     rdx, rax
0x18000d9cb  mov     [rsp+148h+var_100], rax
0x18000d9d0  test    rax, rax
0x18000d9d3  jnz     loc_18000DA61
0x18000d9d9  mov     [rsp+148h+var_D0], r12b
0x18000d9de  lea     rax, qword_18007B2F0
0x18000d9e5  mov     [rsp+148h+var_C8], rax
0x18000d9ed  mov     [rsp+148h+var_C0], r12
0x18000d9f5  mov     [rsp+148h+var_B8], r12
0x18000d9fd  mov     [rsp+148h+var_B0], 0Eh
0x18000da08  mov     [rsp+148h+var_AC], 0FFFFFFFFFFFFFFFFh
0x18000da14  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000da1b  mov     [rsp+148h+pExceptionObject], rax
0x18000da20  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18000da27  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x18000da2c  call    _CxxThrowException_0
0x18000da32  lea     rcx, [rsp+148h+var_50]
0x18000da3a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000da3f  mov     [rsp+148h+var_104], esi
0x18000da43  mov     edi, esi
0x18000da45  lea     rcx, [rsp+148h+var_E0]
0x18000da4a  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x18000da4f  nop
0x18000da50  mov     rcx, [rsp+148h+var_100]; void *
0x18000da55  call    MIDL_user_free
0x18000da5a  mov     eax, edi
0x18000da5c  jmp     loc_18000D85A
0x18000da61  mov     r8d, r12d
0x18000da64  movzx   ecx, [rsp+148h+var_108]
0x18000da69  cmp     r12w, cx
0x18000da6d  jnb     short loc_18000DA97
0x18000da6f  movsxd  rcx, r8d
0x18000da72  add     rcx, rcx
0x18000da75  mov     rax, [rsp+148h+var_F0]
0x18000da7a  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18000da7e  movdqu  xmmword ptr [rdx+rcx*8], xmm0
0x18000da83  add     r8d, r14d
0x18000da86  movzx   ecx, [rsp+148h+var_108]
0x18000da8b  cmp     r8d, ecx
0x18000da8e  jge     short loc_18000DA97
0x18000da90  mov     rdx, [rsp+148h+var_100]
0x18000da95  jmp     short loc_18000DA6F
0x18000da97  movzx   eax, cx
0x18000da9a  mov     [rsp+148h+var_F8], eax
0x18000da9e  lea     rcx, [rsp+148h+var_68]
0x18000daa6  call    ??1?$ScopeGuardImpl1@P6AXPEAX@ZPEAU_SYSTEMTIME@@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>::~ScopeGuardImpl1<void (*)(void *),_SYSTEMTIME *>(void)
0x18000daab  nop
0x18000daac  lea     rcx, [rsp+148h+var_50]
0x18000dab4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000dab9  mov     esi, r12d
0x18000dabc  jmp     loc_18000D828
0x18000dac1  mov     esi, 41304h
0x18000dac6  mov     [rsp+148h+var_104], esi
0x18000daca  jmp     loc_18000D838
0x18000dacf  mov     edi, [rsp+148h+var_104]
0x18000dad3  jmp     loc_18000D8E8
```
