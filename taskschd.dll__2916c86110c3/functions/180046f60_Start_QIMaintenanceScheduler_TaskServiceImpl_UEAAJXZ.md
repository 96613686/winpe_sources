# ?Start@?QIMaintenanceScheduler@@TaskServiceImpl@@UEAAJXZ

- ea: `0x180046f60`
- end: `0x18004720e`
- name: `?Start@?QIMaintenanceScheduler@@TaskServiceImpl@@UEAAJXZ`
- size: `686`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800017f0`
- `0x180030314`
- `0x1800445f8`
- `0x1800459c4`
- `0x180046f60`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046ffc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047059`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800471e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046ffc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047059`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800471e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046f8b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046f8b`
- `OLEAUT32!__imp_VariantInit` at `0x18004713f`
- `OLEAUT32!__imp_VariantInit` at `0x18004713f`

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
0x180046f60  mov     rax, rsp
0x180046f63  push    rbx
0x180046f64  push    rsi
0x180046f65  push    rdi
0x180046f66  push    r12
0x180046f68  push    r14
0x180046f6a  push    r15
0x180046f6c  sub     rsp, 98h
0x180046f73  mov     rdi, rcx
0x180046f76  mov     dword ptr [rax+8], 1
0x180046f7d  lea     rbx, [rcx+0F8h]
0x180046f84  mov     [rax-80h], rbx
0x180046f88  mov     rcx, rbx; lpCriticalSection
0x180046f8b  call    cs:__imp_EnterCriticalSection
0x180046f91  nop
0x180046f92  xor     r14d, r14d
0x180046f95  mov     [rsp+0C8h+arg_18], r14
0x180046f9d  mov     [rsp+0C8h+var_88], r14
0x180046fa2  mov     [rsp+0C8h+arg_8], r14d
0x180046faa  lea     rcx, [rsp+0C8h+arg_18]
0x180046fb2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180046fb7  mov     [rsp+0C8h+arg_18], r14
0x180046fbf  lea     rcx, [rdi+120h]; struct UniSession *
0x180046fc6  lea     r9, [rsp+0C8h+arg_18]; struct IRegisteredTaskCollection **
0x180046fce  call    ?CreateNewObject@RegisteredTaskCollectionImpl@@SAJAEBVUniSession@@KKPEAPEAUIRegisteredTaskCollection@@@Z; RegisteredTaskCollectionImpl::CreateNewObject(UniSession const &,ulong,ulong,IRegisteredTaskCollection * *)
0x180046fd3  mov     edi, eax
0x180046fd5  mov     [rsp+0C8h+arg_0], eax
0x180046fdc  test    eax, eax
0x180046fde  jns     short loc_180047009
0x180046fe0  lea     rcx, [rsp+0C8h+var_88]
0x180046fe5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180046fea  nop
0x180046feb  lea     rcx, [rsp+0C8h+arg_18]
0x180046ff3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180046ff8  nop
0x180046ff9  mov     rcx, rbx; lpCriticalSection
0x180046ffc  call    cs:__imp_LeaveCriticalSection
0x180047002  mov     eax, edi
0x180047004  jmp     loc_1800471FC
0x180047009  lea     rcx, [rsp+0C8h+arg_18]
0x180047011  call    ??C?$_com_ptr_t@V?$_com_IIID@UIRegisteredTask@@$1?_GUID_9c86f320_dee3_4dd1_b972_a303f26b061e@@3U__s_GUID@@B@@@@QEBAPEAUIRegisteredTask@@XZ; _com_ptr_t<_com_IIID<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e>>::operator->(void)
0x180047016  mov     r8, rax
0x180047019  mov     rcx, [rax]
0x18004701c  mov     rax, [rcx+38h]
0x180047020  lea     rdx, [rsp+0C8h+arg_8]
0x180047028  mov     rcx, r8
0x18004702b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047030  mov     esi, eax
0x180047032  mov     [rsp+0C8h+arg_0], eax
0x180047039  test    eax, eax
0x18004703b  jns     short loc_180047066
0x18004703d  lea     rcx, [rsp+0C8h+var_88]
0x180047042  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047047  nop
0x180047048  lea     rcx, [rsp+0C8h+arg_18]
0x180047050  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047055  nop
0x180047056  mov     rcx, rbx; lpCriticalSection
0x180047059  call    cs:__imp_LeaveCriticalSection
0x18004705f  mov     eax, esi
0x180047061  jmp     loc_1800471FC
0x180047066  mov     r15d, 1
0x18004706c  mov     dword ptr [rsp+0C8h+arg_10], r15d
0x180047074  cmp     r15d, [rsp+0C8h+arg_8]
0x18004707c  jg      loc_1800471C5
0x180047082  lea     rcx, [rsp+0C8h+arg_18]
0x18004708a  call    ??C?$_com_ptr_t@V?$_com_IIID@UIRegisteredTask@@$1?_GUID_9c86f320_dee3_4dd1_b972_a303f26b061e@@3U__s_GUID@@B@@@@QEBAPEAUIRegisteredTask@@XZ; _com_ptr_t<_com_IIID<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e>>::operator->(void)
0x18004708f  mov     r12, rax
0x180047092  mov     rdi, [rax]
0x180047095  lea     rcx, [rsp+0C8h+var_88]
0x18004709a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004709f  mov     [rsp+0C8h+var_88], r14
0x1800470a4  mov     eax, 3
0x1800470a9  mov     word ptr [rsp+0C8h+pvarg], ax
0x1800470ae  mov     word ptr [rsp+0C8h+pvarg+8], r15w
0x1800470b4  movzx   ecx, word ptr [rsp+0C8h+arg_10+2]
0x1800470bc  mov     word ptr [rsp+0C8h+pvarg+0Ah], cx
0x1800470c1  movups  xmm0, xmmword ptr [rsp+0C8h+pvarg]
0x1800470c6  movaps  [rsp+0C8h+var_58], xmm0
0x1800470cb  movsd   xmm1, qword ptr [rsp+0C8h+pvarg+10h]
0x1800470d1  movsd   [rsp+0C8h+var_48], xmm1
0x1800470da  lea     r8, [rsp+0C8h+var_88]
0x1800470df  lea     rdx, [rsp+0C8h+var_58]
0x1800470e4  mov     rcx, r12
0x1800470e7  mov     rax, [rdi+40h]
0x1800470eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470f0  mov     edi, eax
0x1800470f2  lea     rcx, [rsp+0C8h+pvarg]; this
0x1800470f7  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800470fc  shr     edi, 1Fh
0x1800470ff  xor     dil, 1
0x180047103  jz      loc_1800471BD
0x180047109  mov     [rsp+0C8h+arg_10], r14
0x180047111  lea     rcx, [rsp+0C8h+var_88]
0x180047116  call    ??C?$_com_ptr_t@V?$_com_IIID@UIRegisteredTask@@$1?_GUID_9c86f320_dee3_4dd1_b972_a303f26b061e@@3U__s_GUID@@B@@@@QEBAPEAUIRegisteredTask@@XZ; _com_ptr_t<_com_IIID<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e>>::operator->(void)
0x18004711b  mov     r12, rax
0x18004711e  mov     rcx, [rax]
0x180047121  mov     rdi, [rcx+68h]
0x180047125  lea     rcx, [rsp+0C8h+arg_10]
0x18004712d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047132  mov     [rsp+0C8h+arg_10], r14
0x18004713a  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x18004713f  call    cs:__imp_VariantInit
0x180047145  nop
0x180047146  movups  xmm0, xmmword ptr [rsp+0C8h+pvarg]
0x18004714b  movaps  [rsp+0C8h+var_58], xmm0
0x180047150  movsd   xmm1, qword ptr [rsp+0C8h+pvarg+10h]
0x180047156  movsd   [rsp+0C8h+var_48], xmm1
0x18004715f  lea     rax, [rsp+0C8h+arg_10]
0x180047167  mov     [rsp+0C8h+var_A0], rax
0x18004716c  mov     [rsp+0C8h+var_A8], r14
0x180047171  xor     r9d, r9d
0x180047174  lea     r8d, [r9+2]
0x180047178  lea     rdx, [rsp+0C8h+var_58]
0x18004717d  mov     rcx, r12
0x180047180  mov     rax, rdi
0x180047183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047188  mov     edi, eax
0x18004718a  lea     rcx, [rsp+0C8h+pvarg]; this
0x18004718f  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180047194  mov     ecx, r14d
0x180047197  cmp     edi, 80041326h
0x18004719d  cmovnz  ecx, edi
0x1800471a0  test    ecx, ecx
0x1800471a2  jns     short loc_1800471B0
0x1800471a4  test    esi, esi
0x1800471a6  cmovns  esi, ecx
0x1800471a9  mov     [rsp+0C8h+arg_0], esi
0x1800471b0  lea     rcx, [rsp+0C8h+arg_10]
0x1800471b8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800471bd  inc     r15d
0x1800471c0  jmp     loc_18004706C
0x1800471c5  lea     rcx, [rsp+0C8h+var_88]
0x1800471ca  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800471cf  nop
0x1800471d0  lea     rcx, [rsp+0C8h+arg_18]
0x1800471d8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800471dd  nop
0x1800471de  mov     rcx, rbx; lpCriticalSection
0x1800471e1  call    cs:__imp_LeaveCriticalSection
0x1800471e7  nop
0x1800471e8  jmp     short loc_1800471F4
0x1800471ea  xor     r14d, r14d
0x1800471ed  mov     esi, [rsp+0C8h+arg_0]
0x1800471f4  test    esi, esi
0x1800471f6  cmovns  esi, r14d
0x1800471fa  mov     eax, esi
0x1800471fc  add     rsp, 98h
0x180047203  pop     r15
0x180047205  pop     r14
0x180047207  pop     r12
0x180047209  pop     rdi
0x18004720a  pop     rsi
0x18004720b  pop     rbx
0x18004720c  retn
```
