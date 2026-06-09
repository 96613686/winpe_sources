# ?Stop@?QIMaintenanceScheduler@@TaskServiceImpl@@UEAAJXZ

- ea: `0x18004ac00`
- end: `0x18004ae47`
- name: `?Stop@?QIMaintenanceScheduler@@TaskServiceImpl@@UEAAJXZ`
- size: `583`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001880`
- `0x180032b34`
- `0x180047cd8`
- `0x180049130`
- `0x18004ac00`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004aca2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ad05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ae14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004aca2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ad05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ae14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ac2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ac2b`

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
0x18004ac00  mov     rax, rsp
0x18004ac03  push    rbx
0x18004ac04  push    rsi
0x18004ac05  push    rdi
0x18004ac06  push    r12
0x18004ac08  push    r14
0x18004ac0a  push    r15
0x18004ac0c  sub     rsp, 88h
0x18004ac13  mov     rdi, rcx
0x18004ac16  mov     dword ptr [rax+8], 1
0x18004ac1d  lea     rbx, [rcx+0F8h]
0x18004ac24  mov     [rax-80h], rbx
0x18004ac28  mov     rcx, rbx; lpCriticalSection
0x18004ac2b  call    cs:__imp_EnterCriticalSection
0x18004ac32  nop     dword ptr [rax+rax+00h]
0x18004ac37  nop
0x18004ac38  xor     r14d, r14d
0x18004ac3b  mov     [rsp+0B8h+arg_18], r14
0x18004ac43  mov     [rsp+0B8h+var_88], r14
0x18004ac48  mov     [rsp+0B8h+arg_8], r14d
0x18004ac50  lea     rcx, [rsp+0B8h+arg_18]
0x18004ac58  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ac5d  mov     [rsp+0B8h+arg_18], r14
0x18004ac65  lea     rcx, [rdi+120h]; struct UniSession *
0x18004ac6c  lea     r9, [rsp+0B8h+arg_18]; struct IRegisteredTaskCollection **
0x18004ac74  call    ?CreateNewObject@RegisteredTaskCollectionImpl@@SAJAEBVUniSession@@KKPEAPEAUIRegisteredTaskCollection@@@Z; RegisteredTaskCollectionImpl::CreateNewObject(UniSession const &,ulong,ulong,IRegisteredTaskCollection * *)
0x18004ac79  mov     edi, eax
0x18004ac7b  mov     [rsp+0B8h+arg_0], eax
0x18004ac82  test    eax, eax
0x18004ac84  jns     short loc_18004ACB5
0x18004ac86  lea     rcx, [rsp+0B8h+var_88]
0x18004ac8b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ac90  nop
0x18004ac91  lea     rcx, [rsp+0B8h+arg_18]
0x18004ac99  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ac9e  nop
0x18004ac9f  mov     rcx, rbx; lpCriticalSection
0x18004aca2  call    cs:__imp_LeaveCriticalSection
0x18004aca9  nop     dword ptr [rax+rax+00h]
0x18004acae  mov     eax, edi
0x18004acb0  jmp     loc_18004AE35
0x18004acb5  lea     rcx, [rsp+0B8h+arg_18]
0x18004acbd  call    ??C?$_com_ptr_t@V?$_com_IIID@UIRegisteredTask@@$1?_GUID_9c86f320_dee3_4dd1_b972_a303f26b061e@@3U__s_GUID@@B@@@@QEBAPEAUIRegisteredTask@@XZ; _com_ptr_t<_com_IIID<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e>>::operator->(void)
0x18004acc2  mov     r8, rax
0x18004acc5  mov     rcx, [rax]
0x18004acc8  mov     rax, [rcx+38h]
0x18004accc  lea     rdx, [rsp+0B8h+arg_8]
0x18004acd4  mov     rcx, r8
0x18004acd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004acdc  mov     esi, eax
0x18004acde  mov     [rsp+0B8h+arg_0], eax
0x18004ace5  test    eax, eax
0x18004ace7  jns     short loc_18004AD18
0x18004ace9  lea     rcx, [rsp+0B8h+var_88]
0x18004acee  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004acf3  nop
0x18004acf4  lea     rcx, [rsp+0B8h+arg_18]
0x18004acfc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ad01  nop
0x18004ad02  mov     rcx, rbx; lpCriticalSection
0x18004ad05  call    cs:__imp_LeaveCriticalSection
0x18004ad0c  nop     dword ptr [rax+rax+00h]
0x18004ad11  mov     eax, esi
0x18004ad13  jmp     loc_18004AE35
0x18004ad18  mov     r15d, 1
0x18004ad1e  mov     [rsp+0B8h+arg_10], r15d
0x18004ad26  cmp     r15d, [rsp+0B8h+arg_8]
0x18004ad2e  jg      loc_18004ADF8
0x18004ad34  lea     rcx, [rsp+0B8h+arg_18]
0x18004ad3c  call    ??C?$_com_ptr_t@V?$_com_IIID@UIRegisteredTask@@$1?_GUID_9c86f320_dee3_4dd1_b972_a303f26b061e@@3U__s_GUID@@B@@@@QEBAPEAUIRegisteredTask@@XZ; _com_ptr_t<_com_IIID<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e>>::operator->(void)
0x18004ad41  mov     r12, rax
0x18004ad44  mov     rdi, [rax]
0x18004ad47  lea     rcx, [rsp+0B8h+var_88]
0x18004ad4c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ad51  mov     [rsp+0B8h+var_88], r14
0x18004ad56  mov     eax, 3
0x18004ad5b  mov     word ptr [rsp+0B8h+var_78], ax
0x18004ad60  mov     word ptr [rsp+0B8h+var_78+8], r15w
0x18004ad66  movzx   ecx, word ptr [rsp+0B8h+arg_10+2]
0x18004ad6e  mov     word ptr [rsp+0B8h+var_78+0Ah], cx
0x18004ad73  movups  xmm0, [rsp+0B8h+var_78]
0x18004ad78  movaps  [rsp+0B8h+var_58], xmm0
0x18004ad7d  movsd   xmm1, [rsp+0B8h+var_68]
0x18004ad83  movsd   [rsp+0B8h+var_48], xmm1
0x18004ad89  lea     r8, [rsp+0B8h+var_88]
0x18004ad8e  lea     rdx, [rsp+0B8h+var_58]
0x18004ad93  mov     rcx, r12
0x18004ad96  mov     rax, [rdi+40h]
0x18004ad9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad9f  mov     edi, eax
0x18004ada1  lea     rcx, [rsp+0B8h+var_78]; this
0x18004ada6  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004adab  shr     edi, 1Fh
0x18004adae  xor     dil, 1
0x18004adb2  jz      short loc_18004ADF0
0x18004adb4  lea     rcx, [rsp+0B8h+var_88]
0x18004adb9  call    ??C?$_com_ptr_t@V?$_com_IIID@UIRegisteredTask@@$1?_GUID_9c86f320_dee3_4dd1_b972_a303f26b061e@@3U__s_GUID@@B@@@@QEBAPEAUIRegisteredTask@@XZ; _com_ptr_t<_com_IIID<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e>>::operator->(void)
0x18004adbe  mov     r8, rax
0x18004adc1  mov     rcx, [rax]
0x18004adc4  mov     rax, [rcx+0B8h]
0x18004adcb  xor     edx, edx
0x18004adcd  mov     rcx, r8
0x18004add0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004add5  mov     ecx, r14d
0x18004add8  cmp     eax, 80041326h
0x18004addd  cmovnz  ecx, eax
0x18004ade0  test    ecx, ecx
0x18004ade2  jns     short loc_18004ADF0
0x18004ade4  test    esi, esi
0x18004ade6  cmovns  esi, ecx
0x18004ade9  mov     [rsp+0B8h+arg_0], esi
0x18004adf0  inc     r15d
0x18004adf3  jmp     loc_18004AD1E
0x18004adf8  lea     rcx, [rsp+0B8h+var_88]
0x18004adfd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ae02  nop
0x18004ae03  lea     rcx, [rsp+0B8h+arg_18]
0x18004ae0b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ae10  nop
0x18004ae11  mov     rcx, rbx; lpCriticalSection
0x18004ae14  call    cs:__imp_LeaveCriticalSection
0x18004ae1b  nop     dword ptr [rax+rax+00h]
0x18004ae20  nop
0x18004ae21  jmp     short loc_18004AE2D
0x18004ae23  xor     r14d, r14d
0x18004ae26  mov     esi, [rsp+0B8h+arg_0]
0x18004ae2d  test    esi, esi
0x18004ae2f  cmovns  esi, r14d
0x18004ae33  mov     eax, esi
0x18004ae35  add     rsp, 88h
0x18004ae3c  pop     r15
0x18004ae3e  pop     r14
0x18004ae40  pop     r12
0x18004ae42  pop     rdi
0x18004ae43  pop     rsi
0x18004ae44  pop     rbx
0x18004ae45  retn
```
