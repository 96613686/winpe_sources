# ComputeService::Management::ComputeSystemManager::RemoveComputeSystem(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14007ba70`
- end: `0x14007bbfc`
- name: `?RemoveComputeSystem@ComputeSystemManager@Management@ComputeService@@UEAA?AV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z`
- size: `396`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1400056c4`
- `0x140008760`
- `0x14002e120`
- `0x140038644`
- `0x140065b60`
- `0x1400727b0`
- `0x14007ba70`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007baec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007baec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007bbdf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007bbdf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14007baa0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14007baa0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007baa6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007baa6`

## pseudocode

```c
_QWORD *__fastcall ComputeService::Management::ComputeSystemManager::RemoveComputeSystem(
        RTL_SRWLOCK *a1,
        _QWORD *a2,
        const WCHAR *a3)
{
  RTL_SRWLOCK *v3; // r15
  RTL_SRWLOCK *v4; // rsi
  _QWORD *v7; // rbx
  _QWORD *v8; // rdx
  const WCHAR *v9; // rcx
  __int64 **v10; // rcx
  _QWORD *v11; // rdx
  __int64 i; // rax
  __int64 *j; // rcx
  _QWORD *v14; // rsi
  volatile signed __int32 *v15; // rbx
  char v17[8]; // [rsp+20h] [rbp-58h] BYREF
  const WCHAR *v18; // [rsp+28h] [rbp-50h] BYREF
  char v19[16]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v20; // [rsp+40h] [rbp-38h]

  v3 = a1 + 11;
  *a2 = 0;
  v4 = a1 + 9;
  a2[1] = 0;
  AcquireSRWLockExclusive(a1 + 11);
  LODWORD(v3[1].Ptr) = GetCurrentThreadId();
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
    v4,
    v19,
    a3);
  v7 = (_QWORD *)v20;
  if ( !*(_BYTE *)(v20 + 25) )
  {
    v8 = (_QWORD *)(v20 + 32);
    if ( *(_QWORD *)(v20 + 56) > 7u )
      v8 = (_QWORD *)*v8;
    if ( *((_QWORD *)a3 + 3) <= 7u )
      v9 = a3;
    else
      v9 = *(const WCHAR **)a3;
    if ( (int)_o__wcsicmp(v9, v8) >= 0 && v7 != v4->Ptr )
    {
      std::shared_ptr<TransportIoContext>::operator=(a2, v7 + 8);
      v10 = (__int64 **)v7[2];
      v11 = v7;
      if ( *((_BYTE *)v10 + 25) )
      {
        for ( i = v7[1]; !*(_BYTE *)(i + 25) && v7 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
          v7 = (_QWORD *)i;
      }
      else
      {
        for ( j = *v10; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          ;
      }
      v14 = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<std::pair<TransportIoContext * const,std::shared_ptr<TransportIoContext>>>>::_Extract(
                        v4,
                        v11);
      v15 = (volatile signed __int32 *)v14[9];
      if ( v15 )
      {
        if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
      std::wstring::~wstring(v14 + 4);
      operator delete(v14, 0x50u);
    }
  }
  v17[0] = *a2 != 0;
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const WCHAR **)a3;
  v18 = a3;
  ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_RemoveSystem<unsigned short const *,bool>(&v18, v17);
  LODWORD(v3[1].Ptr) = 0;
  ReleaseSRWLockExclusive(v3);
  return a2;
}

```

## disassembly

```asm
0x14007ba70  mov     [rsp+arg_18], rbx
0x14007ba75  push    rbp
0x14007ba76  push    rsi
0x14007ba77  push    rdi
0x14007ba78  push    r14
0x14007ba7a  push    r15
0x14007ba7c  sub     rsp, 50h
0x14007ba80  lea     r15, [rcx+58h]
0x14007ba84  mov     qword ptr [rdx], 0
0x14007ba8b  lea     rsi, [rcx+48h]
0x14007ba8f  mov     qword ptr [rdx+8], 0
0x14007ba97  mov     rcx, r15; SRWLock
0x14007ba9a  mov     rdi, r8
0x14007ba9d  mov     r14, rdx
0x14007baa0  call    cs:__imp_AcquireSRWLockExclusive
0x14007baa6  call    cs:__imp_GetCurrentThreadId
0x14007baac  mov     r8, rdi
0x14007baaf  lea     rdx, [rsp+78h+var_48]
0x14007bab4  mov     rcx, rsi
0x14007bab7  mov     [r15+8], eax
0x14007babb  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x14007bac0  mov     rbx, [rsp+78h+var_38]
0x14007bac5  cmp     byte ptr [rbx+19h], 0
0x14007bac9  jnz     loc_14007BBAD
0x14007bacf  lea     rdx, [rbx+20h]
0x14007bad3  cmp     qword ptr [rdx+18h], 7
0x14007bad8  jbe     short loc_14007BADD
0x14007bada  mov     rdx, [rdx]
0x14007badd  cmp     qword ptr [rdi+18h], 7
0x14007bae2  jbe     short loc_14007BAE9
0x14007bae4  mov     rcx, [rdi]
0x14007bae7  jmp     short loc_14007BAEC
0x14007bae9  mov     rcx, rdi
0x14007baec  call    cs:__imp__o__wcsicmp
0x14007baf2  test    eax, eax
0x14007baf4  js      loc_14007BBAD
0x14007bafa  cmp     rbx, [rsi]
0x14007bafd  jz      loc_14007BBAD
0x14007bb03  lea     rdx, [rbx+40h]
0x14007bb07  mov     rcx, r14
0x14007bb0a  call    ??4?$shared_ptr@VTransportIoContext@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<TransportIoContext>::operator=(std::shared_ptr<TransportIoContext> &&)
0x14007bb0f  mov     rcx, [rbx+10h]
0x14007bb13  mov     rdx, rbx
0x14007bb16  cmp     byte ptr [rcx+19h], 0
0x14007bb1a  jz      short loc_14007BB37
0x14007bb1c  mov     rax, [rbx+8]
0x14007bb20  jmp     short loc_14007BB2F
0x14007bb22  cmp     rbx, [rax+10h]
0x14007bb26  jnz     short loc_14007BB4C
0x14007bb28  mov     rbx, rax
0x14007bb2b  mov     rax, [rax+8]
0x14007bb2f  cmp     byte ptr [rax+19h], 0
0x14007bb33  jz      short loc_14007BB22
0x14007bb35  jmp     short loc_14007BB4C
0x14007bb37  mov     rcx, [rcx]
0x14007bb3a  cmp     byte ptr [rcx+19h], 0
0x14007bb3e  jnz     short loc_14007BB4C
0x14007bb40  mov     rax, [rcx]
0x14007bb43  mov     rcx, rax
0x14007bb46  cmp     byte ptr [rax+19h], 0
0x14007bb4a  jz      short loc_14007BB40
0x14007bb4c  mov     rcx, rsi
0x14007bb4f  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAVTransportIoContext@@V?$shared_ptr@VTransportIoContext@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAVTransportIoContext@@V?$shared_ptr@VTransportIoContext@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAVTransportIoContext@@V?$shared_ptr@VTransportIoContext@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<TransportIoContext * const,std::shared_ptr<TransportIoContext>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<TransportIoContext * const,std::shared_ptr<TransportIoContext>>>>,std::_Iterator_base0>)
0x14007bb54  mov     rsi, rax
0x14007bb57  mov     rbx, [rax+48h]
0x14007bb5b  test    rbx, rbx
0x14007bb5e  jz      short loc_14007BB97
0x14007bb60  or      ecx, 0FFFFFFFFh
0x14007bb63  lock xadd [rbx+8], ecx
0x14007bb68  cmp     ecx, 1
0x14007bb6b  jnz     short loc_14007BB97
0x14007bb6d  mov     rdx, [rbx]
0x14007bb70  mov     rcx, rbx
0x14007bb73  mov     rax, [rdx]
0x14007bb76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bb7b  or      eax, 0FFFFFFFFh
0x14007bb7e  lock xadd [rbx+0Ch], eax
0x14007bb83  cmp     eax, 1
0x14007bb86  jnz     short loc_14007BB97
0x14007bb88  mov     rax, [rbx]
0x14007bb8b  mov     rcx, rbx
0x14007bb8e  mov     rax, [rax+8]
0x14007bb92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007bb97  lea     rcx, [rsi+20h]; void *
0x14007bb9b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14007bba0  mov     edx, 50h ; 'P'; unsigned __int64
0x14007bba5  mov     rcx, rsi; void *
0x14007bba8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14007bbad  cmp     qword ptr [r14], 0
0x14007bbb1  setnz   [rsp+78h+var_58]
0x14007bbb6  cmp     qword ptr [rdi+18h], 7
0x14007bbbb  jbe     short loc_14007BBC0
0x14007bbbd  mov     rdi, [rdi]
0x14007bbc0  lea     rdx, [rsp+78h+var_58]
0x14007bbc5  mov     [rsp+78h+var_50], rdi
0x14007bbca  lea     rcx, [rsp+78h+var_50]
0x14007bbcf  call    ??$ComputeSystemManager_RemoveSystem@PEBG_N@TraceProvider@Diagnostics@ComputeService@@SAX$$QEAPEBG$$QEA_N@Z; ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_RemoveSystem<ushort const *,bool>(ushort const * &&,bool &&)
0x14007bbd4  mov     rcx, r15; SRWLock
0x14007bbd7  mov     dword ptr [r15+8], 0
0x14007bbdf  call    cs:__imp_ReleaseSRWLockExclusive
0x14007bbe5  mov     rbx, [rsp+78h+arg_18]
0x14007bbed  mov     rax, r14
0x14007bbf0  add     rsp, 50h
0x14007bbf4  pop     r15
0x14007bbf6  pop     r14
0x14007bbf8  pop     rdi
0x14007bbf9  pop     rsi
0x14007bbfa  pop     rbp
0x14007bbfb  retn
```
