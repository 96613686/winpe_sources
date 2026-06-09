# SubscriptionManager::AssertSubscription(ushort const *,ushort const *,SubscriptionReadData const &)

- ea: `0x18000a938`
- end: `0x18000ad98`
- name: `?AssertSubscription@SubscriptionManager@@QEAAXPEBG0AEBVSubscriptionReadData@@@Z`
- size: `1120`
- prototype: `void __fastcall(SubscriptionManager *this, const unsigned __int16 *, const unsigned __int16 *, const struct tag_EcRpcMetadataPropertyList **)`
- caller_count: `3`
- callee_count: `19`
- tags: `registry_config, service_task`

## callers

- `0x180004b80`
- `0x1800052cc`
- `0x180005ad0`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180003430`
- `0x180003810`
- `0x180003d10`
- `0x18000526c`
- `0x1800062d4`
- `0x180007814`
- `0x180007b64`
- `0x180007c00`
- `0x1800084e0`
- `0x18000a938`
- `0x18000b1f8`
- `0x180010c48`
- `0x180010fdc`
- `0x18001e660`
- `0x18001f000`
- `0x18001fe50`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a984`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a984`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a9d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aa3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a9d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aa3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac8c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000aa4e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000aa4e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000acfd`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000acfd`

## string_xrefs

- `0x18000ad58`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SubscriptionManager::AssertSubscription(
        SubscriptionManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct tag_EcRpcMetadataPropertyList **a4)
{
  const unsigned __int16 *v5; // rdi
  __int64 v8; // rbx
  struct _RTL_CRITICAL_SECTION *v9; // r14
  __int64 *v10; // rsi
  __int64 v11; // rdx
  void *v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rbx
  const struct tag_EcRpcMetadataPropertyList *v15; // rcx
  __int64 v16; // rdi
  int v17; // eax
  Subscription *v18; // rax
  SourceInitiatedSubscription *v19; // rbx
  SourceInitiatedSubscription *v20; // rax
  __int64 v21; // rax
  const unsigned __int16 *v22; // rbx
  __int64 v23; // rdx
  __int64 v24; // rbx
  __int64 v25; // rdx
  DWORD DueTime; // eax
  DWORD LastError; // ebx
  bool v28; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v29[2]; // [rsp+48h] [rbp-61h] BYREF
  struct _FILETIME v30; // [rsp+50h] [rbp-59h] BYREF
  const unsigned __int16 *v31; // [rsp+58h] [rbp-51h] BYREF
  _QWORD v32[3]; // [rsp+60h] [rbp-49h] BYREF
  void **pExceptionObject; // [rsp+78h] [rbp-31h] BYREF
  char v34; // [rsp+80h] [rbp-29h]
  const char *v35; // [rsp+88h] [rbp-21h]
  __int64 v36; // [rsp+90h] [rbp-19h]
  __int64 v37; // [rsp+98h] [rbp-11h]
  DWORD v38; // [rsp+A0h] [rbp-9h]
  int v39; // [rsp+A4h] [rbp-5h]
  int v40; // [rsp+A8h] [rbp-1h]

  v5 = a3;
  v31 = a3;
  v30 = (struct _FILETIME)a2;
  v8 = 0;
  v32[0] = 0;
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  *(_QWORD *)v29 = (char *)this + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v10 = (__int64 *)((char *)this + 96);
  std::wstring::wstring(&pExceptionObject, a2);
  std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>,0>>::find(
    (char *)this + 96,
    v29,
    &pExceptionObject);
  LOBYTE(v11) = 1;
  std::wstring::_Tidy(&pExceptionObject, v11, 0);
  if ( *(_QWORD *)v29 != *((_QWORD *)this + 12) )
  {
    wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(v32, *(_QWORD *)(*(_QWORD *)v29 + 64LL));
    v8 = v32[0];
  }
  LeaveCriticalSection(v9);
  if ( v8 )
  {
    if ( v5 && *v5 )
      (*(void (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v8 + 16LL))(v8, v5);
    else
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8);
  }
  v32[1] = (char *)this + 56;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  EnterCriticalSection(v9);
  v12 = (void *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  LeaveCriticalSection(v9);
  if ( v12 )
    DeleteTimerQueueTimer(0, v12, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v32[2] = v9;
  EnterCriticalSection(v9);
  ((void (__fastcall *)(_QWORD, _QWORD))std::wstring::wstring)(&pExceptionObject, v30);
  std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>,0>>::find(
    (char *)this + 96,
    v29,
    &pExceptionObject);
  LOBYTE(v13) = 1;
  std::wstring::_Tidy(&pExceptionObject, v13, 0);
  v14 = *(_QWORD *)v29;
  v28 = 0;
  v15 = *a4;
  if ( *(_QWORD *)v29 == *v10 )
  {
    ReadMetadataProp(v15, 0, &v28);
    if ( !v28 )
      goto LABEL_32;
  }
  else
  {
    ReadMetadataProp(v15, 0, &v28);
    if ( !v28 )
    {
      std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::erase(
        (char *)this + 96,
        &v31,
        v14);
      goto LABEL_32;
    }
    v16 = *(_QWORD *)(v14 + 64);
    v29[0] = 1;
    ReadMetadataProp(*a4, 0x1Bu, v29);
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 48LL))(v16);
    if ( v29[0] != v17 )
    {
      std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::erase(
        (char *)this + 96,
        v29,
        v14);
      v14 = *v10;
    }
    v5 = v31;
  }
  v31 = 0;
  if ( v14 == *v10 )
  {
    v29[0] = 1;
    ReadMetadataProp(*a4, 0x1Bu, v29);
    if ( v29[0] == 1 )
    {
      v18 = (Subscription *)operator new(0xE0u);
      v19 = v18;
      *(_QWORD *)v29 = v18;
      if ( v18 )
      {
        Subscription::Subscription(v18, this, *(const unsigned __int16 **)&v30);
        *(_QWORD *)v19 = &CollectorInitiatedSubscription::`vftable';
        std::map<std::wstring,wmi::AutoRef<BoundSubscription>>::map<std::wstring,wmi::AutoRef<BoundSubscription>>((char *)v19 + 208);
      }
      else
      {
        v19 = 0;
      }
    }
    else
    {
      v20 = (SourceInitiatedSubscription *)operator new(0x158u);
      *(_QWORD *)v29 = v20;
      if ( v20 )
        v19 = SourceInitiatedSubscription::SourceInitiatedSubscription(v20, this, *(const unsigned __int16 **)&v30);
      else
        v19 = 0;
    }
    wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(&v31, v19);
    ((void (__fastcall *)(_QWORD, _QWORD))std::wstring::wstring)(&pExceptionObject, v30);
    v21 = std::map<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>>::operator[](
            (char *)this + 96,
            &pExceptionObject);
    v22 = v31;
    wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(v21, v31);
    LOBYTE(v23) = 1;
    std::wstring::_Tidy(&pExceptionObject, v23, 0);
  }
  else
  {
    wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(&v31, *(_QWORD *)(v14 + 64));
    v22 = v31;
  }
  (*(void (__fastcall **)(const unsigned __int16 *, const unsigned __int16 *, const struct tag_EcRpcMetadataPropertyList **))(*(_QWORD *)v22 + 8LL))(
    v22,
    v5,
    a4);
  if ( *((_BYTE *)v22 + 96) )
  {
    v30 = (struct _FILETIME)*((_QWORD *)v22 + 11);
    DueTime = CalculateExpirationMsec(&v30);
    if ( DueTime >= *((_DWORD *)this + 30) )
      DueTime = *((_DWORD *)this + 30);
    else
      *((_DWORD *)this + 30) = DueTime;
    if ( !CreateTimerQueueTimer(
            (PHANDLE)this + 14,
            0,
            SubscriptionManager::SubscriptionExpirationCallback,
            this,
            DueTime,
            0,
            0x10u) )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, LastError);
      }
      v34 = 0;
      v35 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
      v36 = 0;
      v37 = 0;
      v38 = LastError;
      v39 = -1;
      v40 = 3591;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
  else
  {
    ((void (__fastcall *)(_QWORD, _QWORD))std::wstring::wstring)(&pExceptionObject, v30);
    v24 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>,0>>::find(
                       (char *)this + 96,
                       &v30,
                       &pExceptionObject);
    LOBYTE(v25) = 1;
    std::wstring::_Tidy(&pExceptionObject, v25, 0);
    if ( v24 != *v10 )
      std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::erase(
        (char *)this + 96,
        &v30,
        v24);
  }
  wmi::AutoRef<AbstractEventProcessor>::Release(&v31);
LABEL_32:
  LeaveCriticalSection(v9);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  wmi::AutoRef<AbstractEventProcessor>::Release(v32);
}

```

## disassembly

```asm
0x18000a938  push    rbp
0x18000a93a  push    rbx
0x18000a93b  push    rsi
0x18000a93c  push    rdi
0x18000a93d  push    r12
0x18000a93f  push    r13
0x18000a941  push    r14
0x18000a943  push    r15
0x18000a945  lea     rbp, [rsp-1Fh]
0x18000a94a  sub     rsp, 0C8h
0x18000a951  mov     rax, cs:__security_cookie
0x18000a958  xor     rax, rsp
0x18000a95b  mov     [rbp+57h+var_50], rax
0x18000a95f  mov     r13, r9
0x18000a962  mov     rdi, r8
0x18000a965  mov     [rbp+57h+var_A8], r8
0x18000a969  mov     r12, rdx
0x18000a96c  mov     qword ptr [rbp+57h+var_B0.dwLowDateTime], rdx
0x18000a970  mov     r15, rcx
0x18000a973  xor     ebx, ebx
0x18000a975  mov     [rbp+57h+var_A0], rbx
0x18000a979  lea     r14, [rcx+10h]
0x18000a97d  mov     qword ptr [rbp+57h+var_B8], r14
0x18000a981  mov     rcx, r14; lpCriticalSection
0x18000a984  call    cs:__imp_EnterCriticalSection
0x18000a98a  nop
0x18000a98b  lea     rsi, [r15+60h]
0x18000a98f  mov     rdx, r12
0x18000a992  lea     rcx, [rbp+57h+pExceptionObject]
0x18000a996  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000a99b  lea     r8, [rbp+57h+pExceptionObject]
0x18000a99f  lea     rdx, [rbp+57h+var_B8]
0x18000a9a3  mov     rcx, rsi
0x18000a9a6  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@VCaseInsensitiveLess@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>,0>>::find(std::wstring const &)
0x18000a9ab  xor     r8d, r8d
0x18000a9ae  mov     dl, 1
0x18000a9b0  lea     rcx, [rbp+57h+pExceptionObject]
0x18000a9b4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000a9b9  mov     rdx, qword ptr [rbp+57h+var_B8]
0x18000a9bd  cmp     rdx, [rsi]
0x18000a9c0  jz      short loc_18000A9D3
0x18000a9c2  mov     rdx, [rdx+40h]
0x18000a9c6  lea     rcx, [rbp+57h+var_A0]
0x18000a9ca  call    ??4?$AutoRef@VSubscriptionConfigSnapshot@@@wmi@@QEAAAEAV01@PEAVSubscriptionConfigSnapshot@@@Z; wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(SubscriptionConfigSnapshot *)
0x18000a9cf  mov     rbx, [rbp+57h+var_A0]
0x18000a9d3  mov     rcx, r14; lpCriticalSection
0x18000a9d6  call    cs:__imp_LeaveCriticalSection
0x18000a9dc  xor     eax, eax
0x18000a9de  test    rbx, rbx
0x18000a9e1  jz      short loc_18000AA10
0x18000a9e3  test    rdi, rdi
0x18000a9e6  jz      short loc_18000AA01
0x18000a9e8  cmp     [rdi], ax
0x18000a9eb  jz      short loc_18000AA01
0x18000a9ed  mov     rax, [rbx]
0x18000a9f0  mov     rdx, rdi
0x18000a9f3  mov     rcx, rbx
0x18000a9f6  mov     rax, [rax+10h]
0x18000a9fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9ff  jmp     short loc_18000AA10
0x18000aa01  mov     rax, [rbx]
0x18000aa04  mov     rcx, rbx
0x18000aa07  mov     rax, [rax+18h]
0x18000aa0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa10  lea     r12, [r15+38h]
0x18000aa14  mov     [rbp+57h+var_98], r12
0x18000aa18  mov     rcx, r12; lpCriticalSection
0x18000aa1b  call    cs:__imp_EnterCriticalSection
0x18000aa21  nop
0x18000aa22  mov     rcx, r14; lpCriticalSection
0x18000aa25  call    cs:__imp_EnterCriticalSection
0x18000aa2b  mov     rbx, [r15+70h]
0x18000aa2f  mov     qword ptr [r15+70h], 0
0x18000aa37  mov     rcx, r14; lpCriticalSection
0x18000aa3a  call    cs:__imp_LeaveCriticalSection
0x18000aa40  test    rbx, rbx
0x18000aa43  jz      short loc_18000AA54
0x18000aa45  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000aa49  mov     rdx, rbx; Timer
0x18000aa4c  xor     ecx, ecx; TimerQueue
0x18000aa4e  call    cs:__imp_DeleteTimerQueueTimer
0x18000aa54  mov     [rbp+57h+var_90], r14
0x18000aa58  mov     rcx, r14; lpCriticalSection
0x18000aa5b  call    cs:__imp_EnterCriticalSection
0x18000aa61  nop
0x18000aa62  mov     rdx, qword ptr [rbp+57h+var_B0.dwLowDateTime]
0x18000aa66  lea     rcx, [rbp+57h+pExceptionObject]
0x18000aa6a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000aa6f  lea     r8, [rbp+57h+pExceptionObject]
0x18000aa73  lea     rdx, [rbp+57h+var_B8]
0x18000aa77  mov     rcx, rsi
0x18000aa7a  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@VCaseInsensitiveLess@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>,0>>::find(std::wstring const &)
0x18000aa7f  xor     r8d, r8d
0x18000aa82  mov     dl, 1
0x18000aa84  lea     rcx, [rbp+57h+pExceptionObject]
0x18000aa88  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000aa8d  mov     rbx, qword ptr [rbp+57h+var_B8]
0x18000aa91  mov     [rbp+57h+var_C0], 0
0x18000aa95  lea     r8, [rbp+57h+var_C0]; bool *
0x18000aa99  xor     edx, edx; unsigned int
0x18000aa9b  mov     rcx, [r13+0]; struct tag_EcRpcMetadataPropertyList *
0x18000aa9f  cmp     rbx, [rsi]
0x18000aaa2  jz      loc_18000AB7D
0x18000aaa8  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEA_N@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,bool &)
0x18000aaad  cmp     [rbp+57h+var_C0], 0
0x18000aab1  jnz     short loc_18000AAC7
0x18000aab3  mov     r8, rbx
0x18000aab6  lea     rdx, [rbp+57h+var_A8]
0x18000aaba  mov     rcx, rsi
0x18000aabd  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>>>)
0x18000aac2  jmp     loc_18000AC7F
0x18000aac7  mov     rdi, [rbx+40h]
0x18000aacb  mov     [rbp+57h+var_B8], 1
0x18000aad2  lea     r8, [rbp+57h+var_B8]; unsigned int *
0x18000aad6  mov     edx, 1Bh; unsigned int
0x18000aadb  mov     rcx, [r13+0]; struct tag_EcRpcMetadataPropertyList *
0x18000aadf  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAK@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,ulong &)
0x18000aae4  mov     rax, [rdi]
0x18000aae7  mov     rcx, rdi
0x18000aaea  mov     rax, [rax+30h]
0x18000aaee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaf3  cmp     [rbp+57h+var_B8], eax
0x18000aaf6  jz      short loc_18000AB0A
0x18000aaf8  mov     r8, rbx
0x18000aafb  lea     rdx, [rbp+57h+var_B8]
0x18000aaff  mov     rcx, rsi
0x18000ab02  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>>>)
0x18000ab07  mov     rbx, [rsi]
0x18000ab0a  mov     rdi, [rbp+57h+var_A8]
0x18000ab0e  mov     [rbp+57h+var_A8], 0
0x18000ab16  cmp     rbx, [rsi]
0x18000ab19  jnz     loc_18000AC00
0x18000ab1f  mov     [rbp+57h+var_B8], 1
0x18000ab26  lea     r8, [rbp+57h+var_B8]; unsigned int *
0x18000ab2a  mov     edx, 1Bh; unsigned int
0x18000ab2f  mov     rcx, [r13+0]; struct tag_EcRpcMetadataPropertyList *
0x18000ab33  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAK@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,ulong &)
0x18000ab38  cmp     [rbp+57h+var_B8], 1
0x18000ab3c  jnz     short loc_18000AB91
0x18000ab3e  mov     ecx, 0E0h; dwBytes
0x18000ab43  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ab48  mov     rbx, rax
0x18000ab4b  mov     qword ptr [rbp+57h+var_B8], rax
0x18000ab4f  test    rax, rax
0x18000ab52  jz      short loc_18000AB8D
0x18000ab54  mov     r8, qword ptr [rbp+57h+var_B0.dwLowDateTime]; unsigned __int16 *
0x18000ab58  mov     rdx, r15; struct SubscriptionManager *
0x18000ab5b  mov     rcx, rax; this
0x18000ab5e  call    ??0Subscription@@QEAA@AEAVSubscriptionManager@@PEBG@Z; Subscription::Subscription(SubscriptionManager &,ushort const *)
0x18000ab63  nop
0x18000ab64  lea     rax, ??_7CollectorInitiatedSubscription@@6B@; const CollectorInitiatedSubscription::`vftable'
0x18000ab6b  mov     [rbx], rax
0x18000ab6e  lea     rcx, [rbx+0D0h]
0x18000ab75  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,wmi::AutoRef<BoundSubscription>>::map<std::wstring,wmi::AutoRef<BoundSubscription>>(void)
0x18000ab7a  nop
0x18000ab7b  jmp     short loc_18000AB8F
0x18000ab7d  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEA_N@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,bool &)
0x18000ab82  cmp     [rbp+57h+var_C0], 0
0x18000ab86  jnz     short loc_18000AB0E
0x18000ab88  jmp     loc_18000AC7F
0x18000ab8d  xor     ebx, ebx
0x18000ab8f  jmp     short loc_18000ABBA
0x18000ab91  mov     ecx, 158h; dwBytes
0x18000ab96  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ab9b  mov     qword ptr [rbp+57h+var_B8], rax
0x18000ab9f  test    rax, rax
0x18000aba2  jz      short loc_18000ABB8
0x18000aba4  mov     r8, qword ptr [rbp+57h+var_B0.dwLowDateTime]; unsigned __int16 *
0x18000aba8  mov     rdx, r15; struct SubscriptionManager *
0x18000abab  mov     rcx, rax; this
0x18000abae  call    ??0SourceInitiatedSubscription@@QEAA@AEAVSubscriptionManager@@PEBG@Z; SourceInitiatedSubscription::SourceInitiatedSubscription(SubscriptionManager &,ushort const *)
0x18000abb3  mov     rbx, rax
0x18000abb6  jmp     short loc_18000ABBA
0x18000abb8  xor     ebx, ebx
0x18000abba  mov     rdx, rbx
0x18000abbd  lea     rcx, [rbp+57h+var_A8]
0x18000abc1  call    ??4?$AutoRef@VSubscriptionConfigSnapshot@@@wmi@@QEAAAEAV01@PEAVSubscriptionConfigSnapshot@@@Z; wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(SubscriptionConfigSnapshot *)
0x18000abc6  mov     rdx, qword ptr [rbp+57h+var_B0.dwLowDateTime]
0x18000abca  lea     rcx, [rbp+57h+pExceptionObject]
0x18000abce  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000abd3  nop
0x18000abd4  lea     rdx, [rbp+57h+pExceptionObject]
0x18000abd8  mov     rcx, rsi
0x18000abdb  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@VCaseInsensitiveLess@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@@2@@std@@QEAAAEAV?$AutoRef@VSubscription@@@wmi@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>>::operator[](std::wstring &&)
0x18000abe0  mov     rbx, [rbp+57h+var_A8]
0x18000abe4  mov     rdx, rbx
0x18000abe7  mov     rcx, rax
0x18000abea  call    ??4?$AutoRef@VSubscriptionConfigSnapshot@@@wmi@@QEAAAEAV01@PEAVSubscriptionConfigSnapshot@@@Z; wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(SubscriptionConfigSnapshot *)
0x18000abef  nop
0x18000abf0  xor     r8d, r8d
0x18000abf3  mov     dl, 1
0x18000abf5  lea     rcx, [rbp+57h+pExceptionObject]
0x18000abf9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000abfe  jmp     short loc_18000AC11
0x18000ac00  mov     rdx, [rbx+40h]
0x18000ac04  lea     rcx, [rbp+57h+var_A8]
0x18000ac08  call    ??4?$AutoRef@VSubscriptionConfigSnapshot@@@wmi@@QEAAAEAV01@PEAVSubscriptionConfigSnapshot@@@Z; wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(SubscriptionConfigSnapshot *)
0x18000ac0d  mov     rbx, [rbp+57h+var_A8]
0x18000ac11  mov     rax, [rbx]
0x18000ac14  mov     r8, r13
0x18000ac17  mov     rdx, rdi
0x18000ac1a  mov     rcx, rbx
0x18000ac1d  mov     rax, [rax+8]
0x18000ac21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac26  xor     edi, edi
0x18000ac28  cmp     [rbx+60h], dil
0x18000ac2c  jnz     loc_18000ACBC
0x18000ac32  mov     rdx, qword ptr [rbp+57h+var_B0.dwLowDateTime]
0x18000ac36  lea     rcx, [rbp+57h+pExceptionObject]
0x18000ac3a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000ac3f  lea     r8, [rbp+57h+pExceptionObject]
0x18000ac43  lea     rdx, [rbp+57h+var_B0]
0x18000ac47  mov     rcx, rsi
0x18000ac4a  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@VCaseInsensitiveLess@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>,0>>::find(std::wstring const &)
0x18000ac4f  mov     rbx, [rax]
0x18000ac52  xor     r8d, r8d
0x18000ac55  mov     dl, 1
0x18000ac57  lea     rcx, [rbp+57h+pExceptionObject]
0x18000ac5b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000ac60  cmp     rbx, [rsi]
0x18000ac63  jz      short loc_18000AC75
0x18000ac65  mov     r8, rbx
0x18000ac68  lea     rdx, [rbp+57h+var_B0]
0x18000ac6c  mov     rcx, rsi
0x18000ac6f  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>>>)
0x18000ac74  nop
0x18000ac75  lea     rcx, [rbp+57h+var_A8]
0x18000ac79  call    ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
0x18000ac7e  nop
0x18000ac7f  mov     rcx, r14; lpCriticalSection
0x18000ac82  call    cs:__imp_LeaveCriticalSection
0x18000ac88  nop
0x18000ac89  mov     rcx, r12; lpCriticalSection
0x18000ac8c  call    cs:__imp_LeaveCriticalSection
0x18000ac92  nop
0x18000ac93  lea     rcx, [rbp+57h+var_A0]
0x18000ac97  call    ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
0x18000ac9c  mov     rcx, [rbp+57h+var_50]
0x18000aca0  xor     rcx, rsp; StackCookie
0x18000aca3  call    __security_check_cookie
0x18000aca8  add     rsp, 0C8h
0x18000acaf  pop     r15
0x18000acb1  pop     r14
0x18000acb3  pop     r13
0x18000acb5  pop     r12
0x18000acb7  pop     rdi
0x18000acb8  pop     rsi
0x18000acb9  pop     rbx
0x18000acba  pop     rbp
0x18000acbb  retn
0x18000acbc  mov     rax, [rbx+58h]
0x18000acc0  mov     qword ptr [rbp+57h+var_B0.dwLowDateTime], rax
0x18000acc4  lea     rcx, [rbp+57h+var_B0]; struct _FILETIME *
0x18000acc8  call    ?CalculateExpirationMsec@@YAKAEAU_FILETIME@@@Z; CalculateExpirationMsec(_FILETIME &)
0x18000accd  cmp     eax, [r15+78h]
0x18000acd1  jnb     short loc_18000ACD9
0x18000acd3  mov     [r15+78h], eax
0x18000acd7  jmp     short loc_18000ACDD
0x18000acd9  mov     eax, [r15+78h]
0x18000acdd  mov     [rsp+100h+Flags], 10h; Flags
0x18000ace5  mov     [rsp+100h+Period], edi; Period
0x18000ace9  mov     [rsp+100h+DueTime], eax; DueTime
0x18000aced  mov     r9, r15; Parameter
0x18000acf0  lea     r8, ?SubscriptionExpirationCallback@SubscriptionManager@@CAXPEAXE@Z; Callback
0x18000acf7  xor     edx, edx; TimerQueue
0x18000acf9  lea     rcx, [r15+70h]; phNewTimer
0x18000acfd  call    cs:__imp_CreateTimerQueueTimer
0x18000ad03  test    eax, eax
0x18000ad05  jnz     loc_18000AC75
0x18000ad0b  call    cs:__imp_GetLastError
0x18000ad11  mov     ebx, eax
0x18000ad13  mov     eax, 507h
0x18000ad18  test    ebx, ebx
0x18000ad1a  cmovz   ebx, eax
0x18000ad1d  lea     rax, WPP_GLOBAL_Control
0x18000ad24  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad2b  cmp     rcx, rax
0x18000ad2e  jz      short loc_18000AD54
0x18000ad30  test    byte ptr [rcx+1Ch], 10h
0x18000ad34  jz      short loc_18000AD54
0x18000ad36  cmp     byte ptr [rcx+19h], 2
0x18000ad3a  jb      short loc_18000AD54
0x18000ad3c  mov     edx, 55h ; 'U'
0x18000ad41  mov     r9d, ebx
0x18000ad44  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000ad4b  mov     rcx, [rcx+10h]
0x18000ad4f  call    WPP_SF_D
0x18000ad54  mov     [rbp+57h+var_80], dil
0x18000ad58  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000ad5f  mov     [rbp+57h+var_78], rax
0x18000ad63  mov     [rbp+57h+var_70], rdi
0x18000ad67  mov     [rbp+57h+var_68], rdi
0x18000ad6b  mov     [rbp+57h+var_60], ebx
0x18000ad6e  mov     [rbp+57h+var_5C], 0FFFFFFFFh
0x18000ad75  mov     [rbp+57h+var_58], 0E07h
0x18000ad7c  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000ad83  mov     [rbp+57h+pExceptionObject], rax
0x18000ad87  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000ad8e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000ad92  call    _CxxThrowException_0
  ... truncated ...
```
