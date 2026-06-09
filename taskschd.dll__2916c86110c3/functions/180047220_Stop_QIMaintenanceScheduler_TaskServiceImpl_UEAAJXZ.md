# ?Stop@?QIMaintenanceScheduler@@TaskServiceImpl@@UEAAJXZ

- ea: `0x180047220`
- end: `0x18004744f`
- name: `?Stop@?QIMaintenanceScheduler@@TaskServiceImpl@@UEAAJXZ`
- size: `559`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800017f0`
- `0x180030314`
- `0x1800445f8`
- `0x1800459c4`
- `0x180047220`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800472bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047319`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047422`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800472bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047319`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047422`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004724b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004724b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall _Stop__QIMaintenanceScheduler__TaskServiceImpl__UEAAJXZ(__int64 a1)
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
  __int64 v12; // rax
  int v13; // eax
  int v14; // ecx
  __int64 v15[2]; // [rsp+30h] [rbp-88h] BYREF
  __int128 v16; // [rsp+40h] [rbp-78h] BYREF
  __int64 v17; // [rsp+50h] [rbp-68h]
  __int128 v18; // [rsp+60h] [rbp-58h] BYREF
  __int64 v19; // [rsp+70h] [rbp-48h]
  int v20; // [rsp+C8h] [rbp+10h] BYREF
  int v21; // [rsp+D0h] [rbp+18h]
  struct IRegisteredTaskCollection *v22; // [rsp+D8h] [rbp+20h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 248);
  v15[1] = a1 + 248;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 248));
  v22 = 0;
  v15[0] = 0;
  v20 = 0;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v22);
  v22 = 0;
  v5 = RegisteredTaskCollectionImpl::CreateNewObject((const struct UniSession *)(a1 + 288), v3, v4, &v22);
  if ( v5 >= 0 )
  {
    v7 = _com_ptr_t<_com_IIID<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e>>::operator->(&v22);
    v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v7 + 56LL))(v7, &v20);
    if ( v8 >= 0 )
    {
      for ( i = 1; ; ++i )
      {
        v21 = i;
        if ( i > v20 )
          break;
        v10 = (__int64 *)_com_ptr_t<_com_IIID<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e>>::operator->(&v22);
        v11 = *v10;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v15);
        v15[0] = 0;
        LOWORD(v16) = 3;
        WORD4(v16) = i;
        WORD5(v16) = HIWORD(v21);
        v18 = v16;
        v19 = v17;
        LODWORD(v11) = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64 *))(v11 + 64))(v10, &v18, v15);
        _variant_t::~_variant_t((_variant_t *)&v16);
        if ( (int)v11 >= 0 )
        {
          v12 = _com_ptr_t<_com_IIID<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e>>::operator->(v15);
          v13 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 184LL))(v12, 0);
          v14 = 0;
          if ( v13 != -2147216602 )
            v14 = v13;
          if ( v14 < 0 && v8 >= 0 )
            v8 = v14;
        }
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v15);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v22);
      LeaveCriticalSection(v2);
      if ( v8 >= 0 )
        return 0;
      return (unsigned int)v8;
    }
    else
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v15);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v22);
      LeaveCriticalSection(v2);
      return (unsigned int)v8;
    }
  }
  else
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v15);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v22);
    LeaveCriticalSection(v2);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x180047220  mov     rax, rsp
0x180047223  push    rbx
0x180047224  push    rsi
0x180047225  push    rdi
0x180047226  push    r12
0x180047228  push    r14
0x18004722a  push    r15
0x18004722c  sub     rsp, 88h
0x180047233  mov     rdi, rcx
0x180047236  mov     dword ptr [rax+8], 1
0x18004723d  lea     rbx, [rcx+0F8h]
0x180047244  mov     [rax-80h], rbx
0x180047248  mov     rcx, rbx; lpCriticalSection
0x18004724b  call    cs:__imp_EnterCriticalSection
0x180047251  nop
0x180047252  xor     r14d, r14d
0x180047255  mov     [rsp+0B8h+arg_18], r14
0x18004725d  mov     [rsp+0B8h+var_88], r14
0x180047262  mov     [rsp+0B8h+arg_8], r14d
0x18004726a  lea     rcx, [rsp+0B8h+arg_18]
0x180047272  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047277  mov     [rsp+0B8h+arg_18], r14
0x18004727f  lea     rcx, [rdi+120h]; struct UniSession *
0x180047286  lea     r9, [rsp+0B8h+arg_18]; struct IRegisteredTaskCollection **
0x18004728e  call    ?CreateNewObject@RegisteredTaskCollectionImpl@@SAJAEBVUniSession@@KKPEAPEAUIRegisteredTaskCollection@@@Z; RegisteredTaskCollectionImpl::CreateNewObject(UniSession const &,ulong,ulong,IRegisteredTaskCollection * *)
0x180047293  mov     edi, eax
0x180047295  mov     [rsp+0B8h+arg_0], eax
0x18004729c  test    eax, eax
0x18004729e  jns     short loc_1800472C9
0x1800472a0  lea     rcx, [rsp+0B8h+var_88]
0x1800472a5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800472aa  nop
0x1800472ab  lea     rcx, [rsp+0B8h+arg_18]
0x1800472b3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800472b8  nop
0x1800472b9  mov     rcx, rbx; lpCriticalSection
0x1800472bc  call    cs:__imp_LeaveCriticalSection
0x1800472c2  mov     eax, edi
0x1800472c4  jmp     loc_18004743D
0x1800472c9  lea     rcx, [rsp+0B8h+arg_18]
0x1800472d1  call    ??C?$_com_ptr_t@V?$_com_IIID@UIRegisteredTask@@$1?_GUID_9c86f320_dee3_4dd1_b972_a303f26b061e@@3U__s_GUID@@B@@@@QEBAPEAUIRegisteredTask@@XZ; _com_ptr_t<_com_IIID<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e>>::operator->(void)
0x1800472d6  mov     r8, rax
0x1800472d9  mov     rcx, [rax]
0x1800472dc  mov     rax, [rcx+38h]
0x1800472e0  lea     rdx, [rsp+0B8h+arg_8]
0x1800472e8  mov     rcx, r8
0x1800472eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472f0  mov     esi, eax
0x1800472f2  mov     [rsp+0B8h+arg_0], eax
0x1800472f9  test    eax, eax
0x1800472fb  jns     short loc_180047326
0x1800472fd  lea     rcx, [rsp+0B8h+var_88]
0x180047302  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047307  nop
0x180047308  lea     rcx, [rsp+0B8h+arg_18]
0x180047310  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047315  nop
0x180047316  mov     rcx, rbx; lpCriticalSection
0x180047319  call    cs:__imp_LeaveCriticalSection
0x18004731f  mov     eax, esi
0x180047321  jmp     loc_18004743D
0x180047326  mov     r15d, 1
0x18004732c  mov     [rsp+0B8h+arg_10], r15d
0x180047334  cmp     r15d, [rsp+0B8h+arg_8]
0x18004733c  jg      loc_180047406
0x180047342  lea     rcx, [rsp+0B8h+arg_18]
0x18004734a  call    ??C?$_com_ptr_t@V?$_com_IIID@UIRegisteredTask@@$1?_GUID_9c86f320_dee3_4dd1_b972_a303f26b061e@@3U__s_GUID@@B@@@@QEBAPEAUIRegisteredTask@@XZ; _com_ptr_t<_com_IIID<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e>>::operator->(void)
0x18004734f  mov     r12, rax
0x180047352  mov     rdi, [rax]
0x180047355  lea     rcx, [rsp+0B8h+var_88]
0x18004735a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004735f  mov     [rsp+0B8h+var_88], r14
0x180047364  mov     eax, 3
0x180047369  mov     word ptr [rsp+0B8h+var_78], ax
0x18004736e  mov     word ptr [rsp+0B8h+var_78+8], r15w
0x180047374  movzx   ecx, word ptr [rsp+0B8h+arg_10+2]
0x18004737c  mov     word ptr [rsp+0B8h+var_78+0Ah], cx
0x180047381  movups  xmm0, [rsp+0B8h+var_78]
0x180047386  movaps  [rsp+0B8h+var_58], xmm0
0x18004738b  movsd   xmm1, [rsp+0B8h+var_68]
0x180047391  movsd   [rsp+0B8h+var_48], xmm1
0x180047397  lea     r8, [rsp+0B8h+var_88]
0x18004739c  lea     rdx, [rsp+0B8h+var_58]
0x1800473a1  mov     rcx, r12
0x1800473a4  mov     rax, [rdi+40h]
0x1800473a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800473ad  mov     edi, eax
0x1800473af  lea     rcx, [rsp+0B8h+var_78]; this
0x1800473b4  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800473b9  shr     edi, 1Fh
0x1800473bc  xor     dil, 1
0x1800473c0  jz      short loc_1800473FE
0x1800473c2  lea     rcx, [rsp+0B8h+var_88]
0x1800473c7  call    ??C?$_com_ptr_t@V?$_com_IIID@UIRegisteredTask@@$1?_GUID_9c86f320_dee3_4dd1_b972_a303f26b061e@@3U__s_GUID@@B@@@@QEBAPEAUIRegisteredTask@@XZ; _com_ptr_t<_com_IIID<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e>>::operator->(void)
0x1800473cc  mov     r8, rax
0x1800473cf  mov     rcx, [rax]
0x1800473d2  mov     rax, [rcx+0B8h]
0x1800473d9  xor     edx, edx
0x1800473db  mov     rcx, r8
0x1800473de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800473e3  mov     ecx, r14d
0x1800473e6  cmp     eax, 80041326h
0x1800473eb  cmovnz  ecx, eax
0x1800473ee  test    ecx, ecx
0x1800473f0  jns     short loc_1800473FE
0x1800473f2  test    esi, esi
0x1800473f4  cmovns  esi, ecx
0x1800473f7  mov     [rsp+0B8h+arg_0], esi
0x1800473fe  inc     r15d
0x180047401  jmp     loc_18004732C
0x180047406  lea     rcx, [rsp+0B8h+var_88]
0x18004740b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047410  nop
0x180047411  lea     rcx, [rsp+0B8h+arg_18]
0x180047419  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004741e  nop
0x18004741f  mov     rcx, rbx; lpCriticalSection
0x180047422  call    cs:__imp_LeaveCriticalSection
0x180047428  nop
0x180047429  jmp     short loc_180047435
0x18004742b  xor     r14d, r14d
0x18004742e  mov     esi, [rsp+0B8h+arg_0]
0x180047435  test    esi, esi
0x180047437  cmovns  esi, r14d
0x18004743b  mov     eax, esi
0x18004743d  add     rsp, 88h
0x180047444  pop     r15
0x180047446  pop     r14
0x180047448  pop     r12
0x18004744a  pop     rdi
0x18004744b  pop     rsi
0x18004744c  pop     rbx
0x18004744d  retn
```
