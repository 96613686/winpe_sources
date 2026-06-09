# ?Start@?QIMaintenanceScheduler@@TaskServiceImpl@@UEAAJXZ

- ea: `0x18004a920`
- end: `0x18004abec`
- name: `?Start@?QIMaintenanceScheduler@@TaskServiceImpl@@UEAAJXZ`
- size: `716`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001880`
- `0x180032b34`
- `0x180047cd8`
- `0x180049130`
- `0x18004a920`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a9c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004aa25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004abb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a9c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004aa25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004abb9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a94b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a94b`
- `OLEAUT32!__imp_VariantInit` at `0x18004ab11`
- `OLEAUT32!__imp_VariantInit` at `0x18004ab11`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall _Start__QIMaintenanceScheduler__TaskServiceImpl__UEAAJXZ(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // r8
  int v5; // edi
  __int64 v7; // rax
  int v8; // esi
  int i; // r15d
  __int64 *v10; // r12
  __int64 v11; // rdi
  __int64 v12; // r12
  __int64 (__fastcall *v13)(__int64, VARIANTARG *, __int64); // rdi
  int v14; // edi
  int v15; // ecx
  __int64 v16[2]; // [rsp+40h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-78h] BYREF
  VARIANTARG v18[3]; // [rsp+70h] [rbp-58h] BYREF
  int v19; // [rsp+D8h] [rbp+10h] BYREF
  __int64 v20; // [rsp+E0h] [rbp+18h] BYREF
  struct IRegisteredTaskCollection *v21; // [rsp+E8h] [rbp+20h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 248);
  v16[1] = a1 + 248;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 248));
  v21 = 0;
  v16[0] = 0;
  v19 = 0;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v21);
  v21 = 0;
  v5 = RegisteredTaskCollectionImpl::CreateNewObject((const struct UniSession *)(a1 + 288), v3, v4, &v21);
  if ( v5 >= 0 )
  {
    v7 = _com_ptr_t<_com_IIID<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e>>::operator->(&v21);
    v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v7 + 56LL))(v7, &v19);
    if ( v8 >= 0 )
    {
      for ( i = 1; ; ++i )
      {
        LODWORD(v20) = i;
        if ( i > v19 )
          break;
        v10 = (__int64 *)_com_ptr_t<_com_IIID<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e>>::operator->(&v21);
        v11 = *v10;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v16);
        v16[0] = 0;
        pvarg.vt = 3;
        pvarg.iVal = i;
        WORD1(pvarg.decVal.Lo64) = WORD1(v20);
        v18[0] = pvarg;
        LODWORD(v11) = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, __int64 *))(v11 + 64))(v10, v18, v16);
        _variant_t::~_variant_t((_variant_t *)&pvarg);
        if ( (int)v11 >= 0 )
        {
          v20 = 0;
          v12 = _com_ptr_t<_com_IIID<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e>>::operator->(v16);
          v13 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, __int64))(*(_QWORD *)v12 + 104LL);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
          v20 = 0;
          VariantInit(&pvarg);
          v18[0] = pvarg;
          v14 = v13(v12, v18, 2);
          _variant_t::~_variant_t((_variant_t *)&pvarg);
          v15 = 0;
          if ( v14 != -2147216602 )
            v15 = v14;
          if ( v15 < 0 && v8 >= 0 )
            v8 = v15;
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
        }
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v16);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v21);
      LeaveCriticalSection(v2);
      if ( v8 >= 0 )
        return 0;
      return (unsigned int)v8;
    }
    else
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v16);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v21);
      LeaveCriticalSection(v2);
      return (unsigned int)v8;
    }
  }
  else
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v16);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v21);
    LeaveCriticalSection(v2);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x18004a920  mov     rax, rsp
0x18004a923  push    rbx
0x18004a924  push    rsi
0x18004a925  push    rdi
0x18004a926  push    r12
0x18004a928  push    r14
0x18004a92a  push    r15
0x18004a92c  sub     rsp, 98h
0x18004a933  mov     rdi, rcx
0x18004a936  mov     dword ptr [rax+8], 1
0x18004a93d  lea     rbx, [rcx+0F8h]
0x18004a944  mov     [rax-80h], rbx
0x18004a948  mov     rcx, rbx; lpCriticalSection
0x18004a94b  call    cs:__imp_EnterCriticalSection
0x18004a952  nop     dword ptr [rax+rax+00h]
0x18004a957  nop
0x18004a958  xor     r14d, r14d
0x18004a95b  mov     [rsp+0C8h+arg_18], r14
0x18004a963  mov     [rsp+0C8h+var_88], r14
0x18004a968  mov     [rsp+0C8h+arg_8], r14d
0x18004a970  lea     rcx, [rsp+0C8h+arg_18]
0x18004a978  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004a97d  mov     [rsp+0C8h+arg_18], r14
0x18004a985  lea     rcx, [rdi+120h]; struct UniSession *
0x18004a98c  lea     r9, [rsp+0C8h+arg_18]; struct IRegisteredTaskCollection **
0x18004a994  call    ?CreateNewObject@RegisteredTaskCollectionImpl@@SAJAEBVUniSession@@KKPEAPEAUIRegisteredTaskCollection@@@Z; RegisteredTaskCollectionImpl::CreateNewObject(UniSession const &,ulong,ulong,IRegisteredTaskCollection * *)
0x18004a999  mov     edi, eax
0x18004a99b  mov     [rsp+0C8h+arg_0], eax
0x18004a9a2  test    eax, eax
0x18004a9a4  jns     short loc_18004A9D5
0x18004a9a6  lea     rcx, [rsp+0C8h+var_88]
0x18004a9ab  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004a9b0  nop
0x18004a9b1  lea     rcx, [rsp+0C8h+arg_18]
0x18004a9b9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004a9be  nop
0x18004a9bf  mov     rcx, rbx; lpCriticalSection
0x18004a9c2  call    cs:__imp_LeaveCriticalSection
0x18004a9c9  nop     dword ptr [rax+rax+00h]
0x18004a9ce  mov     eax, edi
0x18004a9d0  jmp     loc_18004ABDA
0x18004a9d5  lea     rcx, [rsp+0C8h+arg_18]
0x18004a9dd  call    ??C?$_com_ptr_t@V?$_com_IIID@UIRegisteredTask@@$1?_GUID_9c86f320_dee3_4dd1_b972_a303f26b061e@@3U__s_GUID@@B@@@@QEBAPEAUIRegisteredTask@@XZ; _com_ptr_t<_com_IIID<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e>>::operator->(void)
0x18004a9e2  mov     r8, rax
0x18004a9e5  mov     rcx, [rax]
0x18004a9e8  mov     rax, [rcx+38h]
0x18004a9ec  lea     rdx, [rsp+0C8h+arg_8]
0x18004a9f4  mov     rcx, r8
0x18004a9f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a9fc  mov     esi, eax
0x18004a9fe  mov     [rsp+0C8h+arg_0], eax
0x18004aa05  test    eax, eax
0x18004aa07  jns     short loc_18004AA38
0x18004aa09  lea     rcx, [rsp+0C8h+var_88]
0x18004aa0e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004aa13  nop
0x18004aa14  lea     rcx, [rsp+0C8h+arg_18]
0x18004aa1c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004aa21  nop
0x18004aa22  mov     rcx, rbx; lpCriticalSection
0x18004aa25  call    cs:__imp_LeaveCriticalSection
0x18004aa2c  nop     dword ptr [rax+rax+00h]
0x18004aa31  mov     eax, esi
0x18004aa33  jmp     loc_18004ABDA
0x18004aa38  mov     r15d, 1
0x18004aa3e  mov     dword ptr [rsp+0C8h+arg_10], r15d
0x18004aa46  cmp     r15d, [rsp+0C8h+arg_8]
0x18004aa4e  jg      loc_18004AB9D
0x18004aa54  lea     rcx, [rsp+0C8h+arg_18]
0x18004aa5c  call    ??C?$_com_ptr_t@V?$_com_IIID@UIRegisteredTask@@$1?_GUID_9c86f320_dee3_4dd1_b972_a303f26b061e@@3U__s_GUID@@B@@@@QEBAPEAUIRegisteredTask@@XZ; _com_ptr_t<_com_IIID<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e>>::operator->(void)
0x18004aa61  mov     r12, rax
0x18004aa64  mov     rdi, [rax]
0x18004aa67  lea     rcx, [rsp+0C8h+var_88]
0x18004aa6c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004aa71  mov     [rsp+0C8h+var_88], r14
0x18004aa76  mov     eax, 3
0x18004aa7b  mov     word ptr [rsp+0C8h+pvarg], ax
0x18004aa80  mov     word ptr [rsp+0C8h+pvarg+8], r15w
0x18004aa86  movzx   ecx, word ptr [rsp+0C8h+arg_10+2]
0x18004aa8e  mov     word ptr [rsp+0C8h+pvarg+0Ah], cx
0x18004aa93  movups  xmm0, xmmword ptr [rsp+0C8h+pvarg]
0x18004aa98  movaps  [rsp+0C8h+var_58], xmm0
0x18004aa9d  movsd   xmm1, qword ptr [rsp+0C8h+pvarg+10h]
0x18004aaa3  movsd   [rsp+0C8h+var_48], xmm1
0x18004aaac  lea     r8, [rsp+0C8h+var_88]
0x18004aab1  lea     rdx, [rsp+0C8h+var_58]
0x18004aab6  mov     rcx, r12
0x18004aab9  mov     rax, [rdi+40h]
0x18004aabd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aac2  mov     edi, eax
0x18004aac4  lea     rcx, [rsp+0C8h+pvarg]; this
0x18004aac9  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004aace  shr     edi, 1Fh
0x18004aad1  xor     dil, 1
0x18004aad5  jz      loc_18004AB95
0x18004aadb  mov     [rsp+0C8h+arg_10], r14
0x18004aae3  lea     rcx, [rsp+0C8h+var_88]
0x18004aae8  call    ??C?$_com_ptr_t@V?$_com_IIID@UIRegisteredTask@@$1?_GUID_9c86f320_dee3_4dd1_b972_a303f26b061e@@3U__s_GUID@@B@@@@QEBAPEAUIRegisteredTask@@XZ; _com_ptr_t<_com_IIID<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e>>::operator->(void)
0x18004aaed  mov     r12, rax
0x18004aaf0  mov     rcx, [rax]
0x18004aaf3  mov     rdi, [rcx+68h]
0x18004aaf7  lea     rcx, [rsp+0C8h+arg_10]
0x18004aaff  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ab04  mov     [rsp+0C8h+arg_10], r14
0x18004ab0c  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x18004ab11  call    cs:__imp_VariantInit
0x18004ab18  nop     dword ptr [rax+rax+00h]
0x18004ab1d  nop
0x18004ab1e  movups  xmm0, xmmword ptr [rsp+0C8h+pvarg]
0x18004ab23  movaps  [rsp+0C8h+var_58], xmm0
0x18004ab28  movsd   xmm1, qword ptr [rsp+0C8h+pvarg+10h]
0x18004ab2e  movsd   [rsp+0C8h+var_48], xmm1
0x18004ab37  lea     rax, [rsp+0C8h+arg_10]
0x18004ab3f  mov     [rsp+0C8h+var_A0], rax
0x18004ab44  mov     [rsp+0C8h+var_A8], r14
0x18004ab49  xor     r9d, r9d
0x18004ab4c  lea     r8d, [r9+2]
0x18004ab50  lea     rdx, [rsp+0C8h+var_58]
0x18004ab55  mov     rcx, r12
0x18004ab58  mov     rax, rdi
0x18004ab5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab60  mov     edi, eax
0x18004ab62  lea     rcx, [rsp+0C8h+pvarg]; this
0x18004ab67  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004ab6c  mov     ecx, r14d
0x18004ab6f  cmp     edi, 80041326h
0x18004ab75  cmovnz  ecx, edi
0x18004ab78  test    ecx, ecx
0x18004ab7a  jns     short loc_18004AB88
0x18004ab7c  test    esi, esi
0x18004ab7e  cmovns  esi, ecx
0x18004ab81  mov     [rsp+0C8h+arg_0], esi
0x18004ab88  lea     rcx, [rsp+0C8h+arg_10]
0x18004ab90  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ab95  inc     r15d
0x18004ab98  jmp     loc_18004AA3E
0x18004ab9d  lea     rcx, [rsp+0C8h+var_88]
0x18004aba2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004aba7  nop
0x18004aba8  lea     rcx, [rsp+0C8h+arg_18]
0x18004abb0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004abb5  nop
0x18004abb6  mov     rcx, rbx; lpCriticalSection
0x18004abb9  call    cs:__imp_LeaveCriticalSection
0x18004abc0  nop     dword ptr [rax+rax+00h]
0x18004abc5  nop
0x18004abc6  jmp     short loc_18004ABD2
0x18004abc8  xor     r14d, r14d
0x18004abcb  mov     esi, [rsp+0C8h+arg_0]
0x18004abd2  test    esi, esi
0x18004abd4  cmovns  esi, r14d
0x18004abd8  mov     eax, esi
0x18004abda  add     rsp, 98h
0x18004abe1  pop     r15
0x18004abe3  pop     r14
0x18004abe5  pop     r12
0x18004abe7  pop     rdi
0x18004abe8  pop     rsi
0x18004abe9  pop     rbx
0x18004abea  retn
```
