# ThrottledThreadPool::Submit(ThrottledWorkItem *,ulong)

- ea: `0x18001bc28`
- end: `0x18001be6c`
- name: `?Submit@ThrottledThreadPool@@QEAAJPEAVThrottledWorkItem@@K@Z`
- size: `580`
- prototype: `__int64 __fastcall(PVOID pv, struct ThrottledWorkItem *, unsigned int)`
- caller_count: `7`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180018b10`
- `0x18001afac`
- `0x18008d380`
- `0x1800a17bc`
- `0x1800a7aa0`
- `0x1800b7ba0`
- `0x1800b7ca0`

## callees

- `0x18000e5f4`
- `0x18001bc28`
- `0x180028418`
- `0x180034624`
- `0x1800402b0`
- `0x18009eda4`
- `0x1800f66f8`
- `0x180118010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001bdf6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001bdf6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bc83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bc83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001be1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001be1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bd38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bd38`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001bd0e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001bd0e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001bdb3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001bdb3`

## string_xrefs

- `0x18001bc6b`: `onecoreuap\base\diagnosis\platform\notifications\platform\threadpool\throttledthreadpool.cpp`
- `0x18001bca0`: `onecoreuap\base\diagnosis\platform\notifications\platform\threadpool\throttledthreadpool.cpp`
- `0x18001bd56`: `onecoreuap\base\diagnosis\platform\notifications\platform\threadpool\throttledthreadpool.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ThrottledThreadPool::Submit(
        struct _RTL_CRITICAL_SECTION *pv,
        struct ThrottledWorkItem *a2,
        DWORD a3)
{
  struct ThrottledWorkItem *v6; // r14
  int v7; // eax
  const char *v8; // r9
  __int64 ***LockSemaphore; // rsi
  __int64 **i; // rbx
  bool v11; // bl
  signed int LastError; // eax
  _QWORD *v13; // rax
  __int64 v14; // rax
  __int64 result; // rax
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v17[2]; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v18[24]; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  PTP_TIMER pti; // [rsp+88h] [rbp+10h] BYREF
  struct ThrottledWorkItem *v21; // [rsp+98h] [rbp+20h] BYREF

  v6 = a2;
  v21 = a2;
  try
  {
    v7 = (*(__int64 (**)(void))(*(_QWORD *)a2 + 16LL))();
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\threadpool\\throttledthreadpool.cpp",
        (const char *)(unsigned int)v7,
        pftDueTime.dwLowDateTime);
    EnterCriticalSection(pv + 2);
    v17[1] = pv + 2;
    if ( LOBYTE(pv[3].DebugInfo) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\threadpool\\throttledthreadpool.cpp",
        (const char *)0x80004004LL,
        pftDueTime.dwLowDateTime);
    if ( LOBYTE(pv[3].LockSemaphore) )
    {
      pftDueTime.dwLowDateTime = a3;
      v6 = 0;
      v21 = 0;
      v17[0] = a2;
      std::list<std::pair<unsigned long,std::unique_ptr<ThrottledWorkItem>>>::push_back(&pv[3].LockCount, &pftDueTime);
      std::unique_ptr<CacheMetadataStorage>::~unique_ptr<CacheMetadataStorage>(v17);
    }
    else
    {
      LockSemaphore = (__int64 ***)pv->LockSemaphore;
      for ( i = *LockSemaphore; i != (__int64 **)LockSemaphore; i = (__int64 **)*i )
      {
        pti = (PTP_TIMER)(*(__int64 (__fastcall **)(struct ThrottledWorkItem *))(*(_QWORD *)a2 + 24LL))(a2);
        v14 = (*(__int64 (__fastcall **)(__int64 *))(*i[3] + 24))(i[3]);
        if ( !(unsigned int)_o__wcsicmp(v14, pti)
          && (*(unsigned __int8 (__fastcall **)(__int64 *, struct ThrottledWorkItem *))(*i[3] + 32))(i[3], a2) )
        {
          goto LABEL_18;
        }
      }
      pti = CreateThreadpoolTimer(ThrottledThreadPool::ThreadPoolProc, pv, 0);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TN309>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TN309>::GetImpl'::`2'::impl) )
      {
        v11 = pti == 0;
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( v11 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x66,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\threadpool\\throttledthreadpool.cpp",
            (const char *)(unsigned int)LastError,
            pftDueTime.dwLowDateTime);
      }
      v13 = (_QWORD *)std::_Hash<std::_Umap_traits<_TP_TIMER *,std::unique_ptr<ThrottledWorkItem>,std::_Uhash_compare<_TP_TIMER *,std::hash<_TP_TIMER *>,std::equal_to<_TP_TIMER *>>,std::allocator<std::pair<_TP_TIMER * const,std::unique_ptr<ThrottledWorkItem>>>,0>>::_Try_emplace<_TP_TIMER * const &,>(
                        &pv->OwningThread,
                        v18,
                        &pti);
      std::swap<ThrottledWorkItem,std::default_delete<ThrottledWorkItem>,0>(*v13 + 24LL, &v21);
      pftDueTime = (struct _FILETIME)-(__int64)(10000 * a3);
      SetThreadpoolTimer(pti, &pftDueTime, 0, a3);
      v6 = v21;
    }
LABEL_18:
    if ( pv != (struct _RTL_CRITICAL_SECTION *)-80LL )
      LeaveCriticalSection(pv + 2);
    if ( v6 )
      (**(void (__fastcall ***)(struct ThrottledWorkItem *, __int64))v6)(v6, 1);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(pti) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x72,
                     (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\threadpool\\throttledthreadpool.cpp",
                     v8);
    return (unsigned int)pti;
  }
  return result;
}

```

## disassembly

```asm
0x18001bc28  mov     rax, rsp
0x18001bc2b  mov     [rax+8], rbx
0x18001bc2f  mov     [rax+18h], rsi
0x18001bc33  push    rdi
0x18001bc34  push    r12
0x18001bc36  push    r13
0x18001bc38  push    r14
0x18001bc3a  push    r15
0x18001bc3c  sub     rsp, 50h
0x18001bc40  mov     r13d, r8d
0x18001bc43  mov     r12, rdx
0x18001bc46  mov     r15, rcx
0x18001bc49  mov     r14, rdx
0x18001bc4c  mov     [rax+20h], rdx
0x18001bc50  mov     rax, [rdx]
0x18001bc53  mov     rcx, rdx
0x18001bc56  mov     rax, [rax+10h]
0x18001bc5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc5f  mov     rcx, [rsp+78h]; this
0x18001bc64  test    eax, eax
0x18001bc66  jns     short loc_18001BC7C
0x18001bc68  mov     r9d, eax; char *
0x18001bc6b  lea     r8, aOnecoreuapBase_109; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001bc72  mov     edx, 46h ; 'F'; void *
0x18001bc77  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001bc7c  lea     rdi, [r15+50h]
0x18001bc80  mov     rcx, rdi; lpCriticalSection
0x18001bc83  call    cs:__imp_EnterCriticalSection
0x18001bc89  mov     [rsp+78h+var_48], rdi
0x18001bc8e  mov     rcx, [rsp+78h]; this
0x18001bc93  cmp     byte ptr [r15+78h], 0
0x18001bc98  jz      short loc_18001BCB1
0x18001bc9a  mov     r9d, 80004004h; char *
0x18001bca0  lea     r8, aOnecoreuapBase_109; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001bca7  mov     edx, 4Ch ; 'L'; void *
0x18001bcac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001bcb1  cmp     byte ptr [r15+90h], 0
0x18001bcb9  jz      short loc_18001BCF1
0x18001bcbb  mov     [rsp+78h+pftDueTime.dwLowDateTime], r13d
0x18001bcc0  xor     r14d, r14d
0x18001bcc3  mov     [rsp+78h+arg_18], r14
0x18001bccb  mov     [rsp+78h+var_50], r12
0x18001bcd0  lea     rcx, [r15+80h]
0x18001bcd7  lea     rdx, [rsp+78h+pftDueTime]
0x18001bcdc  call    ?push_back@?$list@U?$pair@KV?$unique_ptr@VThrottledWorkItem@@U?$default_delete@VThrottledWorkItem@@@std@@@std@@@std@@V?$allocator@U?$pair@KV?$unique_ptr@VThrottledWorkItem@@U?$default_delete@VThrottledWorkItem@@@std@@@std@@@std@@@2@@std@@QEAAX$$QEAU?$pair@KV?$unique_ptr@VThrottledWorkItem@@U?$default_delete@VThrottledWorkItem@@@std@@@std@@@2@@Z; std::list<std::pair<ulong,std::unique_ptr<ThrottledWorkItem>>>::push_back(std::pair<ulong,std::unique_ptr<ThrottledWorkItem>> &&)
0x18001bce1  nop
0x18001bce2  lea     rcx, [rsp+78h+var_50]
0x18001bce7  call    ??1?$unique_ptr@VCacheMetadataStorage@@U?$default_delete@VCacheMetadataStorage@@@std@@@std@@QEAA@XZ; std::unique_ptr<CacheMetadataStorage>::~unique_ptr<CacheMetadataStorage>(void)
0x18001bcec  jmp     loc_18001BE17
0x18001bcf1  mov     rsi, [r15+18h]
0x18001bcf5  mov     rbx, [rsi]
0x18001bcf8  cmp     rbx, rsi
0x18001bcfb  jnz     loc_18001BDC3
0x18001bd01  xor     r8d, r8d; pcbe
0x18001bd04  mov     rdx, r15; pv
0x18001bd07  lea     rcx, ?ThreadPoolProc@ThrottledThreadPool@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001bd0e  call    cs:__imp_CreateThreadpoolTimer
0x18001bd14  mov     [rsp+78h+pti], rax
0x18001bd1c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TN309@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TN309@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TN309> `wil::Feature<__WilFeatureTraits_Feature_TN309>::GetImpl(void)'::`2'::impl
0x18001bd23  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TN309@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TN309>::__private_IsEnabled(void)
0x18001bd28  test    al, al
0x18001bd2a  jz      short loc_18001BD67
0x18001bd2c  cmp     [rsp+78h+pti], 0
0x18001bd35  setz    bl
0x18001bd38  call    cs:__imp_GetLastError
0x18001bd3e  test    eax, eax
0x18001bd40  jle     short loc_18001BD4A
0x18001bd42  movzx   eax, ax
0x18001bd45  or      eax, 80070000h
0x18001bd4a  mov     rcx, [rsp+78h]; this
0x18001bd4f  test    bl, bl
0x18001bd51  jz      short loc_18001BD67
0x18001bd53  mov     r9d, eax; char *
0x18001bd56  lea     r8, aOnecoreuapBase_109; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001bd5d  mov     edx, 66h ; 'f'; void *
0x18001bd62  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001bd67  lea     rcx, [r15+10h]
0x18001bd6b  lea     r8, [rsp+78h+pti]
0x18001bd73  lea     rdx, [rsp+78h+var_40]
0x18001bd78  call    ??$_Try_emplace@AEBQEAU_TP_TIMER@@$$V@?$_Hash@V?$_Umap_traits@PEAU_TP_TIMER@@V?$unique_ptr@VThrottledWorkItem@@U?$default_delete@VThrottledWorkItem@@@std@@@std@@V?$_Uhash_compare@PEAU_TP_TIMER@@U?$hash@PEAU_TP_TIMER@@@std@@U?$equal_to@PEAU_TP_TIMER@@@3@@3@V?$allocator@U?$pair@QEAU_TP_TIMER@@V?$unique_ptr@VThrottledWorkItem@@U?$default_delete@VThrottledWorkItem@@@std@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@QEAU_TP_TIMER@@V?$unique_ptr@VThrottledWorkItem@@U?$default_delete@VThrottledWorkItem@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_TP_TIMER@@@Z; std::_Hash<std::_Umap_traits<_TP_TIMER *,std::unique_ptr<ThrottledWorkItem>,std::_Uhash_compare<_TP_TIMER *,std::hash<_TP_TIMER *>,std::equal_to<_TP_TIMER *>>,std::allocator<std::pair<_TP_TIMER * const,std::unique_ptr<ThrottledWorkItem>>>,0>>::_Try_emplace<_TP_TIMER * const &,>(_TP_TIMER * const &)
0x18001bd7d  mov     rcx, [rax]
0x18001bd80  add     rcx, 18h
0x18001bd84  lea     rdx, [rsp+78h+arg_18]
0x18001bd8c  call    ??$swap@VThrottledWorkItem@@U?$default_delete@VThrottledWorkItem@@@std@@$0A@@std@@YAXAEAV?$unique_ptr@VThrottledWorkItem@@U?$default_delete@VThrottledWorkItem@@@std@@@0@0@Z; std::swap<ThrottledWorkItem,std::default_delete<ThrottledWorkItem>,0>(std::unique_ptr<ThrottledWorkItem> &,std::unique_ptr<ThrottledWorkItem> &)
0x18001bd91  imul    eax, r13d, 2710h
0x18001bd98  neg     rax
0x18001bd9b  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], rax
0x18001bda0  mov     r9d, r13d; msWindowLength
0x18001bda3  xor     r8d, r8d; msPeriod
0x18001bda6  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18001bdab  mov     rcx, [rsp+78h+pti]; pti
0x18001bdb3  call    cs:__imp_SetThreadpoolTimer
0x18001bdb9  mov     r14, [rsp+78h+arg_18]
0x18001bdc1  jmp     short loc_18001BE17
0x18001bdc3  mov     rax, [r12]
0x18001bdc7  mov     rcx, r12
0x18001bdca  mov     rax, [rax+18h]
0x18001bdce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdd3  mov     [rsp+78h+pti], rax
0x18001bddb  mov     rcx, [rbx+18h]
0x18001bddf  mov     rdx, [rcx]
0x18001bde2  mov     rax, [rdx+18h]
0x18001bde6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdeb  mov     rdx, [rsp+78h+pti]
0x18001bdf3  mov     rcx, rax
0x18001bdf6  call    cs:__imp__o__wcsicmp
0x18001bdfc  test    eax, eax
0x18001bdfe  jnz     short loc_18001BE43
0x18001be00  mov     rcx, [rbx+18h]
0x18001be04  mov     rax, [rcx]
0x18001be07  mov     rdx, r12
0x18001be0a  mov     rax, [rax+20h]
0x18001be0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be13  test    al, al
0x18001be15  jz      short loc_18001BE43
0x18001be17  test    rdi, rdi
0x18001be1a  jz      short loc_18001BE26
0x18001be1c  mov     rcx, rdi; lpCriticalSection
0x18001be1f  call    cs:__imp_LeaveCriticalSection
0x18001be25  nop
0x18001be26  test    r14, r14
0x18001be29  jz      short loc_18001BE3F
0x18001be2b  mov     rax, [r14]
0x18001be2e  mov     edx, 1
0x18001be33  mov     rcx, r14
0x18001be36  mov     rax, [rax]
0x18001be39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be3e  nop
0x18001be3f  xor     eax, eax
0x18001be41  jmp     short loc_18001BE52
0x18001be43  mov     rbx, [rbx]
0x18001be46  jmp     loc_18001BCF8
0x18001be4b  mov     eax, dword ptr [rsp+78h+pti]
0x18001be52  lea     r11, [rsp+78h+var_28]
0x18001be57  mov     rbx, [r11+30h]
0x18001be5b  mov     rsi, [r11+40h]
0x18001be5f  mov     rsp, r11
0x18001be62  pop     r15
0x18001be64  pop     r14
0x18001be66  pop     r13
0x18001be68  pop     r12
0x18001be6a  pop     rdi
0x18001be6b  retn
```
