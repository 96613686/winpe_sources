# std::for_each<std::execution::parallel_unsequenced_policy const &,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>>,std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>,0>(std::execution::parallel_unsequenced_policy const &,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>>,std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>)

- ea: `0x1400e2a3c`
- end: `0x1400e2c0d`
- name: `??$for_each@AEBVparallel_unsequenced_policy@execution@std@@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@@3@V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@3@$0A@@std@@YAXAEBVparallel_unsequenced_policy@execution@0@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@@0@1V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@0@@Z`
- size: `465`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x14006d5cc`

## callees

- `0x140024504`
- `0x1400e2a3c`
- `0x1400e2c14`
- `0x14011ea40`
- `0x140225ea8`
- `0x140225f50`
- `0x140226300`
- `0x14022f884`
- `0x14022fb0c`
- `0x1402cb010`

## import_xrefs

- `msvcp_win!__std_parallel_algorithms_hw_threads` at `0x1400e2a73`
- `msvcp_win!__std_parallel_algorithms_hw_threads` at `0x1400e2a73`
- `msvcp_win!__std_bulk_submit_threadpool_work` at `0x1400e2b3a`
- `msvcp_win!__std_bulk_submit_threadpool_work` at `0x1400e2b3a`
- `msvcp_win!__std_create_threadpool_work` at `0x1400e2b08`
- `msvcp_win!__std_create_threadpool_work` at `0x1400e2b08`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall std::for_each<std::execution::parallel_unsequenced_policy const &,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>>,std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>,0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rsi
  __int64 v5; // rdi
  __int64 v6; // rbx
  unsigned __int64 v7; // r14
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // [rsp+20h] [rbp-78h] BYREF
  __int64 v17; // [rsp+28h] [rbp-70h]
  __int64 v18; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int64 v19; // [rsp+38h] [rbp-60h]
  __int64 v20; // [rsp+40h] [rbp-58h]
  __int64 v21; // [rsp+48h] [rbp-50h]
  __int64 v22; // [rsp+50h] [rbp-48h]
  __int128 v23; // [rsp+58h] [rbp-40h] BYREF
  __int64 v24; // [rsp+68h] [rbp-30h]
  __int64 v25; // [rsp+70h] [rbp-28h]

  v4 = a4;
  v5 = a3;
  v6 = a2;
  v17 = a4;
  v7 = (unsigned int)__std_parallel_algorithms_hw_threads();
  if ( v7 <= 1
    || (v8 = std::distance<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>>(
               v6,
               v5),
        v8 < 2) )
  {
LABEL_14:
    std::_For_each_ivdep<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>>(
      v6,
      v5,
      v4);
    v15 = *(_QWORD *)(v4 + 56);
    if ( v15 )
    {
      LOBYTE(v14) = v15 != v4;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 32LL))(v15, v14);
      *(_QWORD *)(v4 + 56) = 0;
    }
  }
  else
  {
    v9 = 32LL * (unsigned int)v7;
    if ( v8 < (unsigned __int64)v9 )
      v9 = v8;
    try
    {
      v18 = 0;
      v19 = v9;
      v20 = v8;
      v21 = v8 / v9;
      v22 = v8 % v9;
      v23 = 0;
      v24 = 0;
      v25 = v4;
      std::_Static_partition_range<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,__int64,0>::_Populate(
        &v23,
        &v16,
        &v18,
        v6);
      v10 = __std_create_threadpool_work(
              std::_Static_partitioned_for_each2<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,__int64,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>>::_Threadpool_callback,
              &v18,
              0);
      v16 = v10;
      if ( !v10 )
        std::_Throw_parallelism_resources_exhausted();
      v11 = 4 * v7;
      if ( v19 < 4 * v7 )
        v11 = v19;
      __std_bulk_submit_threadpool_work(v10, v11);
      std::_Run_available_chunked_work<std::_Static_partitioned_for_each2<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,__int64,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>>>(&v18);
      std::_Work_ptr::~_Work_ptr((std::_Work_ptr *)&v16);
      if ( (_QWORD)v23 )
      {
        std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF8uLL);
        v23 = 0;
        v24 = 0;
      }
      v13 = *(_QWORD *)(v4 + 56);
      if ( v13 )
      {
        LOBYTE(v12) = v13 != v4;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 32LL))(v13, v12);
        *(_QWORD *)(v4 + 56) = 0;
      }
    }
    catch ( std::_Parallelism_resources_exhausted )
    {
      v5 = a3;
      v6 = a2;
      v4 = v17;
      goto LABEL_14;
    }
  }
}

```

## disassembly

```asm
0x1400e2a3c  mov     [rsp+arg_0], rbx
0x1400e2a41  mov     [rsp+arg_10], r8
0x1400e2a46  mov     [rsp+arg_8], rdx
0x1400e2a4b  push    rsi
0x1400e2a4c  push    rdi
0x1400e2a4d  push    r14
0x1400e2a4f  sub     rsp, 80h
0x1400e2a56  mov     rax, cs:__security_cookie
0x1400e2a5d  xor     rax, rsp
0x1400e2a60  mov     [rsp+98h+var_20], rax
0x1400e2a65  mov     rsi, r9
0x1400e2a68  mov     rdi, r8
0x1400e2a6b  mov     rbx, rdx
0x1400e2a6e  mov     [rsp+98h+var_70], r9
0x1400e2a73  call    cs:__imp___std_parallel_algorithms_hw_threads
0x1400e2a7a  nop     dword ptr [rax+rax+00h]
0x1400e2a7f  mov     r14d, eax
0x1400e2a82  cmp     r14, 1
0x1400e2a86  jbe     loc_1400E2BBB
0x1400e2a8c  mov     rdx, rdi
0x1400e2a8f  mov     rcx, rbx
0x1400e2a92  call    ??$distance@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@YA_JV?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@0@0@Z; std::distance<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>>(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>)
0x1400e2a97  cmp     rax, 2
0x1400e2a9b  jl      loc_1400E2BBB
0x1400e2aa1  mov     ecx, r14d
0x1400e2aa4  shl     rcx, 5
0x1400e2aa8  cmp     rax, rcx
0x1400e2aab  cmovb   rcx, rax
0x1400e2aaf  xor     edi, edi
0x1400e2ab1  mov     [rsp+98h+var_68], rdi
0x1400e2ab6  mov     [rsp+98h+var_60], rcx
0x1400e2abb  mov     [rsp+98h+var_58], rax
0x1400e2ac0  cqo
0x1400e2ac2  idiv    rcx
0x1400e2ac5  mov     [rsp+98h+var_50], rax
0x1400e2aca  mov     [rsp+98h+var_48], rdx
0x1400e2acf  xorps   xmm0, xmm0
0x1400e2ad2  movdqu  [rsp+98h+var_40], xmm0
0x1400e2ad8  mov     [rsp+98h+var_30], rdi
0x1400e2add  mov     [rsp+98h+var_28], rsi
0x1400e2ae2  mov     r9, rbx
0x1400e2ae5  lea     r8, [rsp+98h+var_68]
0x1400e2aea  lea     rdx, [rsp+98h+var_78]
0x1400e2aef  lea     rcx, [rsp+98h+var_40]
0x1400e2af4  call    ?_Populate@?$_Static_partition_range@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@_J$0A@@std@@QEAA?AV?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@AEBU?$_Static_partition_team@_J@2@V32@@Z; std::_Static_partition_range<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,__int64,0>::_Populate(std::_Static_partition_team<__int64> const &,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>)
0x1400e2af9  xor     r8d, r8d
0x1400e2afc  lea     rdx, [rsp+98h+var_68]
0x1400e2b01  lea     rcx, ?_Threadpool_callback@?$_Static_partitioned_for_each2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@_JU?$_Ref_fn@V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@std@@@2@@std@@SAXPEAU__std_TP_CALLBACK_INSTANCE@@QEAXPEAU__std_TP_WORK@@@Z; std::_Static_partitioned_for_each2<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,__int64,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>>::_Threadpool_callback(__std_TP_CALLBACK_INSTANCE *,void * const,__std_TP_WORK *)
0x1400e2b08  call    cs:__imp___std_create_threadpool_work
0x1400e2b0f  nop     dword ptr [rax+rax+00h]
0x1400e2b14  mov     [rsp+98h+var_78], rax
0x1400e2b19  test    rax, rax
0x1400e2b1c  jnz     short loc_1400E2B24
0x1400e2b1e  call    ?_Throw_parallelism_resources_exhausted@std@@YAXXZ; std::_Throw_parallelism_resources_exhausted(void)
0x1400e2b24  lea     rdx, ds:0[r14*4]
0x1400e2b2c  cmp     [rsp+98h+var_60], rdx
0x1400e2b31  cmovb   rdx, [rsp+98h+var_60]
0x1400e2b37  mov     rcx, rax
0x1400e2b3a  call    cs:__imp___std_bulk_submit_threadpool_work
0x1400e2b41  nop     dword ptr [rax+rax+00h]
0x1400e2b46  lea     rcx, [rsp+98h+var_68]
0x1400e2b4b  call    ??$_Run_available_chunked_work@U?$_Static_partitioned_for_each2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@_JU?$_Ref_fn@V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@std@@@2@@std@@@std@@YAXAEAU?$_Static_partitioned_for_each2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@_JU?$_Ref_fn@V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@std@@@2@@0@@Z; std::_Run_available_chunked_work<std::_Static_partitioned_for_each2<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,__int64,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>>>(std::_Static_partitioned_for_each2<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,__int64,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>> &)
0x1400e2b50  nop
0x1400e2b51  lea     rcx, [rsp+98h+var_78]; this
0x1400e2b56  call    ??1_Work_ptr@std@@QEAA@XZ; std::_Work_ptr::~_Work_ptr(void)
0x1400e2b5b  nop
0x1400e2b5c  mov     rcx, qword ptr [rsp+98h+var_40]
0x1400e2b61  test    rcx, rcx
0x1400e2b64  jz      short loc_1400E2B85
0x1400e2b66  mov     rdx, [rsp+98h+var_30]
0x1400e2b6b  sub     rdx, rcx
0x1400e2b6e  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1400e2b72  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400e2b77  xorps   xmm0, xmm0
0x1400e2b7a  movdqu  [rsp+98h+var_40], xmm0
0x1400e2b80  mov     [rsp+98h+var_30], rdi
0x1400e2b85  mov     rcx, [rsi+38h]
0x1400e2b89  test    rcx, rcx
0x1400e2b8c  jz      short loc_1400E2BA4
0x1400e2b8e  mov     rax, [rcx]
0x1400e2b91  cmp     rcx, rsi
0x1400e2b94  setnz   dl
0x1400e2b97  mov     rax, [rax+20h]
0x1400e2b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400e2ba0  mov     [rsi+38h], rdi
0x1400e2ba4  jmp     short loc_1400E2BEB
0x1400e2ba6  mov     rdi, [rsp+98h+arg_10]
0x1400e2bae  mov     rbx, [rsp+98h+arg_8]
0x1400e2bb6  mov     rsi, [rsp+98h+var_70]
0x1400e2bbb  mov     r8, rsi
0x1400e2bbe  mov     rdx, rdi
0x1400e2bc1  mov     rcx, rbx
0x1400e2bc4  call    ??$_For_each_ivdep@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@U?$_Ref_fn@V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@std@@@2@@std@@YAXV?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@0@V10@U?$_Ref_fn@V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@std@@@0@@Z; std::_For_each_ivdep<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>>(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>)
0x1400e2bc9  nop
0x1400e2bca  mov     rcx, [rsi+38h]
0x1400e2bce  xor     edi, edi
0x1400e2bd0  test    rcx, rcx
0x1400e2bd3  jz      short loc_1400E2BEB
0x1400e2bd5  mov     rax, [rcx]
0x1400e2bd8  cmp     rcx, rsi
0x1400e2bdb  setnz   dl
0x1400e2bde  mov     rax, [rax+20h]
0x1400e2be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400e2be7  mov     [rsi+38h], rdi
0x1400e2beb  mov     rcx, [rsp+98h+var_20]
0x1400e2bf0  xor     rcx, rsp; StackCookie
0x1400e2bf3  call    __security_check_cookie
0x1400e2bf8  mov     rbx, [rsp+98h+arg_0]
0x1400e2c00  add     rsp, 80h
0x1400e2c07  pop     r14
0x1400e2c09  pop     rdi
0x1400e2c0a  pop     rsi
0x1400e2c0b  retn
```
