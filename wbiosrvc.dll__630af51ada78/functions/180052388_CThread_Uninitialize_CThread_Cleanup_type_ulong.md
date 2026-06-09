# CThread::Uninitialize(CThread::Cleanup::type,ulong)

- ea: `0x180052388`
- end: `0x1800525c9`
- name: `?Uninitialize@CThread@@SAJW4type@Cleanup@1@K@Z`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18003ea90`

## callees

- `0x18000367c`
- `0x1800056e0`
- `0x180013810`
- `0x180014f54`
- `0x180038998`
- `0x180039404`
- `0x1800488d0`
- `0x180052388`
- `0x180053024`
- `0x1800530c4`
- `0x180060964`
- `0x18006f510`
- `0x18006f548`
- `0x18006f6f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800524ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800524ff`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180052490`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180052490`

## string_xrefs

- `0x18005246f`: `onecore\ds\security\biometrics\credprov\common\threads.cpp`
- `0x1800524a2`: `onecore\ds\security\biometrics\credprov\common\threads.cpp`
- `0x180052513`: `onecore\ds\security\biometrics\credprov\common\threads.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 CThread::Uninitialize()
{
  __int64 result; // rax
  __int64 *v1; // rdi
  __int64 *i; // rbx
  const char *v3; // r9
  unsigned __int64 v4; // rcx
  const char *v5; // r9
  DWORD CurrentThreadId; // eax
  const char *v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  CSynchLock *v10[2]; // [rsp+20h] [rbp-48h] BYREF
  handle_thread *v11; // [rsp+30h] [rbp-38h] BYREF
  __int128 v12; // [rsp+38h] [rbp-30h]
  HANDLE *lpHandles; // [rsp+48h] [rbp-20h] BYREF
  char *v14; // [rsp+50h] [rbp-18h]
  char *v15; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v17; // [rsp+80h] [rbp+18h] BYREF

  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&lpHandles);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v11);
  *(_OWORD *)v10 = 0;
  try
  {
    CThread::thread_list(v10);
    if ( *((_QWORD *)v10[0] + 1) )
    {
      v1 = *(__int64 **)v10[0];
      for ( i = **(__int64 ***)v10[0]; i != v1; i = (__int64 *)*i )
      {
        CurrentThreadId = GetCurrentThreadId();
        v8 = i[2];
        if ( *(_DWORD *)(v8 + 16) == CurrentThreadId )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x67,
            (unsigned int)"onecore\\ds\\security\\biometrics\\credprov\\common\\threads.cpp",
            v7);
        v17 = i[2];
        if ( v8 )
          _InterlockedIncrement((volatile signed __int32 *)v8);
        if ( (_QWORD)v12 == *((_QWORD *)&v12 + 1) )
        {
          std::vector<handle_thread>::_Emplace_reallocate<handle_thread>(
            (__int64)&v11,
            (const struct handle_thread *)v12,
            (const struct handle_thread *)&v17);
        }
        else
        {
          std::_Default_allocator_traits<std::allocator<handle_thread>>::construct<handle_thread,handle_thread>(
            (__int64)retaddr,
            (handle_thread *)v12,
            (const struct handle_thread *)&v17);
          *(_QWORD *)&v12 = v12 + 8;
        }
        handle_thread::Close((handle_thread *)&v17);
        CThread::Stop((CThread *)i[2]);
        v9 = *(_QWORD *)(i[2] + 120);
        v17 = v9;
        if ( v14 == v15 )
        {
          std::vector<_WINBIO_IDENTITY *>::_Emplace_reallocate<_WINBIO_IDENTITY * const &>(&lpHandles, v14, &v17);
        }
        else
        {
          *(_QWORD *)v14 = v9;
          v14 += 8;
        }
      }
      locked_pointer<std::list<CThread *>>::~locked_pointer<std::list<CThread *>>(v10);
      v4 = (v14 - (char *)lpHandles) >> 3;
      if ( v4 > 0xFFFFFFFF )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x78,
          (unsigned int)"onecore\\ds\\security\\biometrics\\credprov\\common\\threads.cpp",
          v3);
      if ( WaitForMultipleObjects(v4, lpHandles, 1, 0x4E20u) == 258 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x8D,
          (unsigned int)"onecore\\ds\\security\\biometrics\\credprov\\common\\threads.cpp",
          v5);
      if ( v11 )
      {
        std::_Destroy_range<std::allocator<handle_thread>>(v11, (handle_thread *)v12);
        std::_Deallocate<16>(v11, (*((_QWORD *)&v12 + 1) - (_QWORD)v11) & 0xFFFFFFFFFFFFFFF8uLL);
        v11 = 0;
        v12 = 0;
      }
      std::vector<void *>::_Tidy(&lpHandles);
      result = 0;
    }
    else
    {
      if ( v10[1] )
        CSynchLock::Unlock(v10[1]);
      if ( v11 )
      {
        std::_Destroy_range<std::allocator<handle_thread>>(v11, (handle_thread *)v12);
        std::_Deallocate<16>(v11, (*((_QWORD *)&v12 + 1) - (_QWORD)v11) & 0xFFFFFFFFFFFFFFF8uLL);
        v11 = 0;
        v12 = 0;
      }
      if ( lpHandles )
        std::_Deallocate<16>(lpHandles, (v15 - (char *)lpHandles) & 0xFFFFFFFFFFFFFFF8uLL);
      result = 0;
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180052388  mov     [rsp+arg_0], rbx
0x18005238d  push    rdi
0x18005238e  sub     rsp, 60h
0x180052392  lea     rcx, [rsp+68h+lpHandles]
0x180052397  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18005239c  nop
0x18005239d  lea     rcx, [rsp+68h+var_38]
0x1800523a2  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1800523a7  nop
0x1800523a8  xorps   xmm0, xmm0
0x1800523ab  movdqu  xmmword ptr [rsp+68h+var_48], xmm0
0x1800523b1  lea     rcx, [rsp+68h+var_48]
0x1800523b6  call    ?thread_list@CThread@@CAJPEAV?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@@Z; CThread::thread_list(locked_pointer<std::list<CThread *>> *)
0x1800523bb  mov     rdi, [rsp+68h+var_48]
0x1800523c0  cmp     qword ptr [rdi+8], 0
0x1800523c5  jnz     short loc_180052435
0x1800523c7  mov     rcx, [rsp+68h+var_48+8]; this
0x1800523cc  test    rcx, rcx
0x1800523cf  jz      short loc_1800523D7
0x1800523d1  call    ?Unlock@CSynchLock@@QEAAXXZ; CSynchLock::Unlock(void)
0x1800523d6  nop
0x1800523d7  mov     rcx, [rsp+68h+var_38]; this
0x1800523dc  test    rcx, rcx
0x1800523df  jz      short loc_180052413
0x1800523e1  mov     rdx, qword ptr [rsp+68h+var_30]
0x1800523e6  call    ??$_Destroy_range@V?$allocator@Vhandle_thread@@@std@@@std@@YAXPEAVhandle_thread@@QEAV1@AEAV?$allocator@Vhandle_thread@@@0@@Z; std::_Destroy_range<std::allocator<handle_thread>>(handle_thread *,handle_thread * const,std::allocator<handle_thread> &)
0x1800523eb  mov     rcx, [rsp+68h+var_38]
0x1800523f0  mov     rdx, qword ptr [rsp+68h+var_30+8]
0x1800523f5  sub     rdx, rcx
0x1800523f8  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800523fc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180052401  mov     [rsp+68h+var_38], 0
0x18005240a  xorps   xmm0, xmm0
0x18005240d  movdqu  [rsp+68h+var_30], xmm0
0x180052413  mov     rcx, [rsp+68h+lpHandles]
0x180052418  test    rcx, rcx
0x18005241b  jz      short loc_18005242E
0x18005241d  mov     rdx, [rsp+68h+var_10]
0x180052422  sub     rdx, rcx
0x180052425  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180052429  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005242e  xor     eax, eax
0x180052430  jmp     loc_1800525BD
0x180052435  mov     rdi, [rdi]
0x180052438  mov     rbx, [rdi]
0x18005243b  cmp     rbx, rdi
0x18005243e  jnz     loc_1800524FF
0x180052444  lea     rcx, [rsp+68h+var_48]
0x180052449  call    ??1?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@QEAA@XZ; locked_pointer<std::list<CThread *>>::~locked_pointer<std::list<CThread *>>(void)
0x18005244e  mov     rdx, [rsp+68h+lpHandles]; lpHandles
0x180052453  mov     rcx, [rsp+68h+var_18]
0x180052458  sub     rcx, rdx
0x18005245b  sar     rcx, 3; nCount
0x18005245f  mov     rax, [rsp+68h]
0x180052464  mov     r8d, 0FFFFFFFFh
0x18005246a  cmp     rcx, r8
0x18005246d  jbe     short loc_180052484
0x18005246f  lea     r8, aOnecoreDsSecur_40; "onecore\\ds\\security\\biometrics\\cred"...
0x180052476  mov     edx, 78h ; 'x'; void *
0x18005247b  mov     rcx, rax; this
0x18005247e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180052484  mov     r9d, 4E20h; dwMilliseconds
0x18005248a  mov     r8d, 1; bWaitAll
0x180052490  call    cs:__imp_WaitForMultipleObjects
0x180052496  cmp     eax, 102h
0x18005249b  jnz     short loc_1800524B2
0x18005249d  mov     rcx, [rsp+68h]; this
0x1800524a2  lea     r8, aOnecoreDsSecur_40; "onecore\\ds\\security\\biometrics\\cred"...
0x1800524a9  lea     edx, [rax-75h]; void *
0x1800524ac  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800524b2  mov     rcx, [rsp+68h+var_38]; this
0x1800524b7  test    rcx, rcx
0x1800524ba  jz      short loc_1800524EE
0x1800524bc  mov     rdx, qword ptr [rsp+68h+var_30]
0x1800524c1  call    ??$_Destroy_range@V?$allocator@Vhandle_thread@@@std@@@std@@YAXPEAVhandle_thread@@QEAV1@AEAV?$allocator@Vhandle_thread@@@0@@Z; std::_Destroy_range<std::allocator<handle_thread>>(handle_thread *,handle_thread * const,std::allocator<handle_thread> &)
0x1800524c6  mov     rcx, [rsp+68h+var_38]
0x1800524cb  mov     rdx, qword ptr [rsp+68h+var_30+8]
0x1800524d0  sub     rdx, rcx
0x1800524d3  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800524d7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800524dc  mov     [rsp+68h+var_38], 0
0x1800524e5  xorps   xmm0, xmm0
0x1800524e8  movdqu  [rsp+68h+var_30], xmm0
0x1800524ee  lea     rcx, [rsp+68h+lpHandles]
0x1800524f3  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x1800524f8  xor     eax, eax
0x1800524fa  jmp     loc_1800525BD
0x1800524ff  call    cs:__imp_GetCurrentThreadId
0x180052505  mov     rdx, [rbx+10h]
0x180052509  mov     rcx, [rsp+68h]; this
0x18005250e  cmp     [rdx+10h], eax
0x180052511  jnz     short loc_180052525
0x180052513  lea     r8, aOnecoreDsSecur_40; "onecore\\ds\\security\\biometrics\\cred"...
0x18005251a  mov     edx, 67h ; 'g'; void *
0x18005251f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180052525  mov     [rsp+68h+arg_10], rdx
0x18005252d  test    rdx, rdx
0x180052530  jz      short loc_180052535
0x180052532  lock inc dword ptr [rdx]
0x180052535  mov     rdx, qword ptr [rsp+68h+var_30]
0x18005253a  lea     r8, [rsp+68h+arg_10]
0x180052542  cmp     rdx, qword ptr [rsp+68h+var_30+8]
0x180052547  jz      short loc_180052556
0x180052549  call    ??$construct@Vhandle_thread@@V1@@?$_Default_allocator_traits@V?$allocator@Vhandle_thread@@@std@@@std@@SAXAEAV?$allocator@Vhandle_thread@@@1@QEAVhandle_thread@@$$QEAV3@@Z; std::_Default_allocator_traits<std::allocator<handle_thread>>::construct<handle_thread,handle_thread>(std::allocator<handle_thread> &,handle_thread * const,handle_thread &&)
0x18005254e  add     qword ptr [rsp+68h+var_30], 8
0x180052554  jmp     short loc_180052561
0x180052556  lea     rcx, [rsp+68h+var_38]
0x18005255b  call    ??$_Emplace_reallocate@Vhandle_thread@@@?$vector@Vhandle_thread@@V?$allocator@Vhandle_thread@@@std@@@std@@AEAAPEAVhandle_thread@@QEAV2@$$QEAV2@@Z; std::vector<handle_thread>::_Emplace_reallocate<handle_thread>(handle_thread * const,handle_thread &&)
0x180052560  nop
0x180052561  lea     rcx, [rsp+68h+arg_10]; this
0x180052569  call    ?Close@handle_thread@@QEAAXXZ; handle_thread::Close(void)
0x18005256e  mov     rcx, [rbx+10h]; this
0x180052572  call    ?Stop@CThread@@AEAAXXZ; CThread::Stop(void)
0x180052577  mov     rax, [rbx+10h]
0x18005257b  mov     rcx, [rax+78h]
0x18005257f  mov     [rsp+68h+arg_10], rcx
0x180052587  mov     rdx, [rsp+68h+var_18]
0x18005258c  cmp     rdx, [rsp+68h+var_10]
0x180052591  jz      short loc_18005259E
0x180052593  mov     [rdx], rcx
0x180052596  add     [rsp+68h+var_18], 8
0x18005259c  jmp     short loc_1800525B0
0x18005259e  lea     r8, [rsp+68h+arg_10]
0x1800525a6  lea     rcx, [rsp+68h+lpHandles]
0x1800525ab  call    ??$_Emplace_reallocate@AEBQEAU_WINBIO_IDENTITY@@@?$vector@PEAU_WINBIO_IDENTITY@@V?$allocator@PEAU_WINBIO_IDENTITY@@@std@@@std@@AEAAPEAPEAU_WINBIO_IDENTITY@@QEAPEAU2@AEBQEAU2@@Z; std::vector<_WINBIO_IDENTITY *>::_Emplace_reallocate<_WINBIO_IDENTITY * const &>(_WINBIO_IDENTITY * * const,_WINBIO_IDENTITY * const &)
0x1800525b0  mov     rbx, [rbx]
0x1800525b3  jmp     loc_18005243B
0x1800525b8  mov     eax, 8007000Eh
0x1800525bd  mov     rbx, [rsp+68h+arg_0]
0x1800525c2  add     rsp, 60h
0x1800525c6  pop     rdi
0x1800525c7  retn
```
