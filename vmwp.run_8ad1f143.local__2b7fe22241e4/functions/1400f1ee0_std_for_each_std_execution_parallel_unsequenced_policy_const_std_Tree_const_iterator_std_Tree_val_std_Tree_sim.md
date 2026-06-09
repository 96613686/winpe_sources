# std::for_each<std::execution::parallel_unsequenced_policy const &,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>>,std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>,0>(std::execution::parallel_unsequenced_policy const &,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>>,std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>)

- ea: `0x1400f1ee0`
- end: `0x1400f20b1`
- name: `??$for_each@AEBVparallel_unsequenced_policy@execution@std@@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@@3@V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@3@$0A@@std@@YAXAEBVparallel_unsequenced_policy@execution@0@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@@0@1V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@0@@Z`
- size: `465`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1400b435c`

## callees

- `0x140023f94`
- `0x1400f1ee0`
- `0x1400f20b8`
- `0x140132960`
- `0x14022cf08`
- `0x14022cfb0`
- `0x14022d360`
- `0x1402368e4`
- `0x140236b6c`
- `0x1402c2010`

## import_xrefs

- `msvcp_win!__std_parallel_algorithms_hw_threads` at `0x1400f1f17`
- `msvcp_win!__std_parallel_algorithms_hw_threads` at `0x1400f1f17`
- `msvcp_win!__std_bulk_submit_threadpool_work` at `0x1400f1fde`
- `msvcp_win!__std_bulk_submit_threadpool_work` at `0x1400f1fde`
- `msvcp_win!__std_create_threadpool_work` at `0x1400f1fac`
- `msvcp_win!__std_create_threadpool_work` at `0x1400f1fac`

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
0x1400f1ee0  mov     [rsp+arg_0], rbx
0x1400f1ee5  mov     [rsp+arg_10], r8
0x1400f1eea  mov     [rsp+arg_8], rdx
0x1400f1eef  push    rsi
0x1400f1ef0  push    rdi
0x1400f1ef1  push    r14
0x1400f1ef3  sub     rsp, 80h
0x1400f1efa  mov     rax, cs:__security_cookie
0x1400f1f01  xor     rax, rsp
0x1400f1f04  mov     [rsp+98h+var_20], rax
0x1400f1f09  mov     rsi, r9
0x1400f1f0c  mov     rdi, r8
0x1400f1f0f  mov     rbx, rdx
0x1400f1f12  mov     [rsp+98h+var_70], r9
0x1400f1f17  call    cs:__imp___std_parallel_algorithms_hw_threads
0x1400f1f1e  nop     dword ptr [rax+rax+00h]
0x1400f1f23  mov     r14d, eax
0x1400f1f26  cmp     r14, 1
0x1400f1f2a  jbe     loc_1400F205F
0x1400f1f30  mov     rdx, rdi
0x1400f1f33  mov     rcx, rbx
0x1400f1f36  call    ??$distance@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@YA_JV?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@0@0@Z; std::distance<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>>(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>)
0x1400f1f3b  cmp     rax, 2
0x1400f1f3f  jl      loc_1400F205F
0x1400f1f45  mov     ecx, r14d
0x1400f1f48  shl     rcx, 5
0x1400f1f4c  cmp     rax, rcx
0x1400f1f4f  cmovb   rcx, rax
0x1400f1f53  xor     edi, edi
0x1400f1f55  mov     [rsp+98h+var_68], rdi
0x1400f1f5a  mov     [rsp+98h+var_60], rcx
0x1400f1f5f  mov     [rsp+98h+var_58], rax
0x1400f1f64  cqo
0x1400f1f66  idiv    rcx
0x1400f1f69  mov     [rsp+98h+var_50], rax
0x1400f1f6e  mov     [rsp+98h+var_48], rdx
0x1400f1f73  xorps   xmm0, xmm0
0x1400f1f76  movdqu  [rsp+98h+var_40], xmm0
0x1400f1f7c  mov     [rsp+98h+var_30], rdi
0x1400f1f81  mov     [rsp+98h+var_28], rsi
0x1400f1f86  mov     r9, rbx
0x1400f1f89  lea     r8, [rsp+98h+var_68]
0x1400f1f8e  lea     rdx, [rsp+98h+var_78]
0x1400f1f93  lea     rcx, [rsp+98h+var_40]
0x1400f1f98  call    ?_Populate@?$_Static_partition_range@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@_J$0A@@std@@QEAA?AV?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@AEBU?$_Static_partition_team@_J@2@V32@@Z; std::_Static_partition_range<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,__int64,0>::_Populate(std::_Static_partition_team<__int64> const &,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>)
0x1400f1f9d  xor     r8d, r8d
0x1400f1fa0  lea     rdx, [rsp+98h+var_68]
0x1400f1fa5  lea     rcx, ?_Threadpool_callback@?$_Static_partitioned_for_each2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@_JU?$_Ref_fn@V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@std@@@2@@std@@SAXPEAU__std_TP_CALLBACK_INSTANCE@@QEAXPEAU__std_TP_WORK@@@Z; std::_Static_partitioned_for_each2<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,__int64,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>>::_Threadpool_callback(__std_TP_CALLBACK_INSTANCE *,void * const,__std_TP_WORK *)
0x1400f1fac  call    cs:__imp___std_create_threadpool_work
0x1400f1fb3  nop     dword ptr [rax+rax+00h]
0x1400f1fb8  mov     [rsp+98h+var_78], rax
0x1400f1fbd  test    rax, rax
0x1400f1fc0  jnz     short loc_1400F1FC8
0x1400f1fc2  call    ?_Throw_parallelism_resources_exhausted@std@@YAXXZ; std::_Throw_parallelism_resources_exhausted(void)
0x1400f1fc8  lea     rdx, ds:0[r14*4]
0x1400f1fd0  cmp     [rsp+98h+var_60], rdx
0x1400f1fd5  cmovb   rdx, [rsp+98h+var_60]
0x1400f1fdb  mov     rcx, rax
0x1400f1fde  call    cs:__imp___std_bulk_submit_threadpool_work
0x1400f1fe5  nop     dword ptr [rax+rax+00h]
0x1400f1fea  lea     rcx, [rsp+98h+var_68]
0x1400f1fef  call    ??$_Run_available_chunked_work@U?$_Static_partitioned_for_each2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@_JU?$_Ref_fn@V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@std@@@2@@std@@@std@@YAXAEAU?$_Static_partitioned_for_each2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@_JU?$_Ref_fn@V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@std@@@2@@0@@Z; std::_Run_available_chunked_work<std::_Static_partitioned_for_each2<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,__int64,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>>>(std::_Static_partitioned_for_each2<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,__int64,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>> &)
0x1400f1ff4  nop
0x1400f1ff5  lea     rcx, [rsp+98h+var_78]; this
0x1400f1ffa  call    ??1_Work_ptr@std@@QEAA@XZ; std::_Work_ptr::~_Work_ptr(void)
0x1400f1fff  nop
0x1400f2000  mov     rcx, qword ptr [rsp+98h+var_40]
0x1400f2005  test    rcx, rcx
0x1400f2008  jz      short loc_1400F2029
0x1400f200a  mov     rdx, [rsp+98h+var_30]
0x1400f200f  sub     rdx, rcx
0x1400f2012  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1400f2016  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400f201b  xorps   xmm0, xmm0
0x1400f201e  movdqu  [rsp+98h+var_40], xmm0
0x1400f2024  mov     [rsp+98h+var_30], rdi
0x1400f2029  mov     rcx, [rsi+38h]
0x1400f202d  test    rcx, rcx
0x1400f2030  jz      short loc_1400F2048
0x1400f2032  mov     rax, [rcx]
0x1400f2035  cmp     rcx, rsi
0x1400f2038  setnz   dl
0x1400f203b  mov     rax, [rax+20h]
0x1400f203f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f2044  mov     [rsi+38h], rdi
0x1400f2048  jmp     short loc_1400F208F
0x1400f204a  mov     rdi, [rsp+98h+arg_10]
0x1400f2052  mov     rbx, [rsp+98h+arg_8]
0x1400f205a  mov     rsi, [rsp+98h+var_70]
0x1400f205f  mov     r8, rsi
0x1400f2062  mov     rdx, rdi
0x1400f2065  mov     rcx, rbx
0x1400f2068  call    ??$_For_each_ivdep@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@U?$_Ref_fn@V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@std@@@2@@std@@YAXV?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@0@V10@U?$_Ref_fn@V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@std@@@0@@Z; std::_For_each_ivdep<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>>(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>)
0x1400f206d  nop
0x1400f206e  mov     rcx, [rsi+38h]
0x1400f2072  xor     edi, edi
0x1400f2074  test    rcx, rcx
0x1400f2077  jz      short loc_1400F208F
0x1400f2079  mov     rax, [rcx]
0x1400f207c  cmp     rcx, rsi
0x1400f207f  setnz   dl
0x1400f2082  mov     rax, [rax+20h]
0x1400f2086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f208b  mov     [rsi+38h], rdi
0x1400f208f  mov     rcx, [rsp+98h+var_20]
0x1400f2094  xor     rcx, rsp; StackCookie
0x1400f2097  call    __security_check_cookie
0x1400f209c  mov     rbx, [rsp+98h+arg_0]
0x1400f20a4  add     rsp, 80h
0x1400f20ab  pop     r14
0x1400f20ad  pop     rdi
0x1400f20ae  pop     rsi
0x1400f20af  retn
```
