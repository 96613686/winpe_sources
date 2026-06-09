# SubscriptionManager::OnSubscriptionExpiration(void)

- ea: `0x18000ec24`
- end: `0x18000ef3d`
- name: `?OnSubscriptionExpiration@SubscriptionManager@@AEAAXXZ`
- size: `793`
- prototype: `void __fastcall(char *Parameter)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x1800103a0`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180003d10`
- `0x180006b04`
- `0x180007814`
- `0x180008014`
- `0x1800085a0`
- `0x18000b1f8`
- `0x18000ec24`
- `0x18001075c`
- `0x180010b20`
- `0x18001fe50`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ec5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ec5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ef0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ef0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000ec85`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000ec85`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000ee34`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000ee34`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000ee67`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000ee67`

## string_xrefs

- `0x18000eec2`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SubscriptionManager::OnSubscriptionExpiration(char *Parameter)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  char v3; // r15
  __int64 *v4; // rsi
  _QWORD *v5; // rbx
  _QWORD *v6; // rdx
  unsigned __int64 v7; // rax
  unsigned int v8; // eax
  _QWORD *v9; // rax
  const wchar_t *v10; // rax
  const wchar_t *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  _QWORD *i; // rax
  __int64 v15; // rcx
  _QWORD *v16; // rax
  _QWORD *v17; // r8
  __int64 j; // rcx
  void *v19; // rdx
  DWORD LastError; // ebx
  char v21; // [rsp+40h] [rbp-49h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-41h] BYREF
  _QWORD v23[2]; // [rsp+50h] [rbp-39h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-29h] BYREF
  char v25; // [rsp+68h] [rbp-21h]
  const char *v26; // [rsp+70h] [rbp-19h]
  __int64 v27; // [rsp+78h] [rbp-11h]
  __int64 v28; // [rsp+80h] [rbp-9h]
  DWORD v29; // [rsp+88h] [rbp-1h]
  int v30; // [rsp+8Ch] [rbp+3h]
  int v31; // [rsp+90h] [rbp+7h]
  char *v32; // [rsp+98h] [rbp+Fh]
  struct _FILETIME v33[2]; // [rsp+A0h] [rbp+17h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)(Parameter + 16);
  v32 = Parameter + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 16));
  std::map<std::wstring,wmi::AutoRef<BoundSubscription>>::map<std::wstring,wmi::AutoRef<BoundSubscription>>(v23);
  v3 = 0;
  *((_DWORD *)Parameter + 30) = -1;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v4 = (__int64 *)(Parameter + 96);
  v5 = (_QWORD *)**((_QWORD **)Parameter + 12);
  while ( v5 != (_QWORD *)*v4 )
  {
    v6 = (_QWORD *)v5[8];
    v7 = v6[11];
    v33[0] = (struct _FILETIME)v7;
    if ( !v7 )
      goto LABEL_8;
    if ( v7 > *(_QWORD *)&SystemTimeAsFileTime )
    {
      v8 = CalculateExpirationMsec(v33);
      if ( v8 < *((_DWORD *)Parameter + 30) )
        *((_DWORD *)Parameter + 30) = v8;
      v3 = 1;
LABEL_8:
      v9 = (_QWORD *)std::map<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>>::operator[](
                       v23,
                       v5 + 4);
      wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(v9, v5[8]);
      goto LABEL_16;
    }
    (*(void (__fastcall **)(_QWORD *))(*v6 + 24LL))(v6);
    *(_OWORD *)&v33[0].dwLowDateTime = 0;
    v10 = (const wchar_t *)(v5[8] + 56LL);
    if ( *(_QWORD *)(v5[8] + 80LL) >= 8u )
      v10 = *(const wchar_t **)v10;
    v11 = &word_180026AD8;
    if ( v10 )
      v11 = v10;
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
    v33[0] = (struct _FILETIME)v11;
    v33[1].dwLowDateTime = 2 * v12 + 2;
    v33[1].dwHighDateTime = 0;
    (*(void (__fastcall **)(_QWORD, __int64 *, __int64, struct _FILETIME *))(**((_QWORD **)Parameter + 17) + 8LL))(
      *((_QWORD *)Parameter + 17),
      EVTCOLL_SUBSCRIPTION_EXPIRED,
      1,
      v33);
LABEL_16:
    if ( !*((_BYTE *)v5 + 25) )
    {
      v13 = v5[2];
      if ( *(_BYTE *)(v13 + 25) )
      {
        for ( i = (_QWORD *)v5[1]; !*((_BYTE *)i + 25) && v5 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
          v5 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>>::_Min((_QWORD *)v13);
      }
      v5 = i;
    }
  }
  if ( v4 != v23 )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::clear(Parameter + 96);
    *(_QWORD *)(*v4 + 8) = std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(
                             (__int64 *)Parameter + 12,
                             *(_QWORD *)(v23[0] + 8LL),
                             *v4,
                             v21);
    *((_QWORD *)Parameter + 13) = v23[1];
    v15 = *(_QWORD *)(*v4 + 8);
    if ( *(_BYTE *)(v15 + 25) )
    {
      *(_QWORD *)*v4 = *v4;
      *(_QWORD *)(*v4 + 16) = *v4;
    }
    else
    {
      v16 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>>::_Min((_QWORD *)v15);
      *v17 = v16;
      for ( j = *(_QWORD *)(*v4 + 8); !*(_BYTE *)(*(_QWORD *)(j + 16) + 25LL); j = *(_QWORD *)(j + 16) )
        ;
      *(_QWORD *)(*v4 + 16) = j;
    }
  }
  v19 = (void *)*((_QWORD *)Parameter + 14);
  if ( v19 )
  {
    DeleteTimerQueueTimer(0, v19, 0);
    *((_QWORD *)Parameter + 14) = 0;
    if ( v3 )
    {
      if ( !CreateTimerQueueTimer(
              (PHANDLE)Parameter + 14,
              0,
              SubscriptionManager::SubscriptionExpirationCallback,
              Parameter,
              *((_DWORD *)Parameter + 30),
              0,
              0) )
      {
        LastError = GetLastError();
        if ( !LastError )
          LastError = 1287;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, LastError);
        }
        v25 = 0;
        v26 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
        v27 = 0;
        v28 = 0;
        v29 = LastError;
        v30 = -1;
        v31 = 3435;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::GenericException *)&pExceptionObject;
      }
    }
  }
  std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>,0>>(v23);
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x18000ec24  mov     [rsp-8+arg_8], rbx
0x18000ec29  mov     [rsp-8+arg_10], rsi
0x18000ec2e  push    rbp
0x18000ec2f  push    rdi
0x18000ec30  push    r12
0x18000ec32  push    r14
0x18000ec34  push    r15
0x18000ec36  lea     rbp, [rsp-37h]
0x18000ec3b  sub     rsp, 0C0h
0x18000ec42  mov     rax, cs:__security_cookie
0x18000ec49  xor     rax, rsp
0x18000ec4c  mov     [rbp+57h+var_30], rax
0x18000ec50  mov     r14, rcx
0x18000ec53  lea     rdi, [rcx+10h]
0x18000ec57  mov     [rbp+57h+var_48], rdi
0x18000ec5b  mov     rcx, rdi; lpCriticalSection
0x18000ec5e  call    cs:__imp_EnterCriticalSection
0x18000ec64  nop
0x18000ec65  lea     rcx, [rbp+57h+var_90]
0x18000ec69  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,wmi::AutoRef<BoundSubscription>>::map<std::wstring,wmi::AutoRef<BoundSubscription>>(void)
0x18000ec6e  nop
0x18000ec6f  xor     r12d, r12d
0x18000ec72  mov     r15b, r12b
0x18000ec75  mov     dword ptr [r14+78h], 0FFFFFFFFh
0x18000ec7d  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r12
0x18000ec81  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000ec85  call    cs:__imp_GetSystemTimeAsFileTime
0x18000ec8b  lea     rsi, [r14+60h]
0x18000ec8f  mov     rbx, [rsi]
0x18000ec92  mov     rbx, [rbx]
0x18000ec95  cmp     rbx, [rsi]
0x18000ec98  jz      loc_18000EDAC
0x18000ec9e  mov     rdx, [rbx+40h]
0x18000eca2  mov     rax, [rdx+58h]
0x18000eca6  mov     qword ptr [rbp+57h+var_40.dwLowDateTime], rax
0x18000ecaa  mov     rcx, rax
0x18000ecad  shr     rcx, 20h
0x18000ecb1  test    ecx, ecx
0x18000ecb3  jnz     short loc_18000ECB9
0x18000ecb5  test    eax, eax
0x18000ecb7  jz      short loc_18000ECDB
0x18000ecb9  cmp     ecx, [rbp+57h+SystemTimeAsFileTime.dwHighDateTime]
0x18000ecbc  jb      short loc_18000ECF6
0x18000ecbe  jnz     short loc_18000ECC5
0x18000ecc0  cmp     eax, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18000ecc3  jbe     short loc_18000ECF6
0x18000ecc5  lea     rcx, [rbp+57h+var_40]; struct _FILETIME *
0x18000ecc9  call    ?CalculateExpirationMsec@@YAKAEAU_FILETIME@@@Z; CalculateExpirationMsec(_FILETIME &)
0x18000ecce  cmp     eax, [r14+78h]
0x18000ecd2  jnb     short loc_18000ECD8
0x18000ecd4  mov     [r14+78h], eax
0x18000ecd8  mov     r15b, 1
0x18000ecdb  lea     rdx, [rbx+20h]
0x18000ecdf  lea     rcx, [rbp+57h+var_90]
0x18000ece3  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@VCaseInsensitiveLess@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@@2@@std@@QEAAAEAV?$AutoRef@VSubscription@@@wmi@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>>::operator[](std::wstring const &)
0x18000ece8  mov     rdx, [rbx+40h]
0x18000ecec  mov     rcx, rax
0x18000ecef  call    ??4?$AutoRef@VSubscriptionConfigSnapshot@@@wmi@@QEAAAEAV01@PEAVSubscriptionConfigSnapshot@@@Z; wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(SubscriptionConfigSnapshot *)
0x18000ecf4  jmp     short loc_18000ED70
0x18000ecf6  mov     rax, [rdx]
0x18000ecf9  mov     rcx, rdx
0x18000ecfc  mov     rax, [rax+18h]
0x18000ed00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed05  xorps   xmm0, xmm0
0x18000ed08  movups  xmmword ptr [rbp+57h+var_40.dwLowDateTime], xmm0
0x18000ed0c  mov     rax, [rbx+40h]
0x18000ed10  add     rax, 38h ; '8'
0x18000ed14  cmp     qword ptr [rax+18h], 8
0x18000ed19  jb      short loc_18000ED1E
0x18000ed1b  mov     rax, [rax]
0x18000ed1e  lea     rcx, word_180026AD8
0x18000ed25  test    rax, rax
0x18000ed28  cmovnz  rcx, rax
0x18000ed2c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ed30  inc     rax
0x18000ed33  cmp     [rcx+rax*2], r12w
0x18000ed38  jnz     short loc_18000ED30
0x18000ed3a  mov     qword ptr [rbp+57h+var_40.dwLowDateTime], rcx
0x18000ed3e  lea     eax, ds:2[rax*2]
0x18000ed45  mov     [rbp+57h+var_40.dwLowDateTime+8], eax
0x18000ed48  mov     [rbp+57h+var_40.dwHighDateTime+8], r12d
0x18000ed4c  mov     rcx, [r14+88h]
0x18000ed53  mov     rax, [rcx]
0x18000ed56  lea     r9, [rbp+57h+var_40]
0x18000ed5a  mov     r8d, 1
0x18000ed60  lea     rdx, EVTCOLL_SUBSCRIPTION_EXPIRED
0x18000ed67  mov     rax, [rax+8]
0x18000ed6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed70  cmp     [rbx+19h], r12b
0x18000ed74  jnz     loc_18000EC95
0x18000ed7a  mov     rcx, [rbx+10h]
0x18000ed7e  cmp     [rcx+19h], r12b
0x18000ed82  jnz     short loc_18000ED8B
0x18000ed84  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>>::_Min(std::_Tree_node<std::pair<std::wstring const,wmi::AutoRef<Subscription>>,void *> *)
0x18000ed89  jmp     short loc_18000EDA4
0x18000ed8b  mov     rax, [rbx+8]
0x18000ed8f  jmp     short loc_18000ED9E
0x18000ed91  cmp     rbx, [rax+10h]
0x18000ed95  jnz     short loc_18000EDA4
0x18000ed97  mov     rbx, rax
0x18000ed9a  mov     rax, [rax+8]
0x18000ed9e  cmp     [rax+19h], r12b
0x18000eda2  jz      short loc_18000ED91
0x18000eda4  mov     rbx, rax
0x18000eda7  jmp     loc_18000EC95
0x18000edac  lea     rax, [rbp+57h+var_90]
0x18000edb0  cmp     rsi, rax
0x18000edb3  jz      short loc_18000EE1F
0x18000edb5  mov     rcx, rsi
0x18000edb8  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::clear(void)
0x18000edbd  mov     r9b, [rbp+57h+var_A0]
0x18000edc1  mov     r8, [rsi]
0x18000edc4  mov     rdx, [rbp+57h+var_90]
0x18000edc8  mov     rdx, [rdx+8]
0x18000edcc  mov     rcx, rsi
0x18000edcf  call    ??$_Copy_nodes@U?$integral_constant@_N$0A@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@PEAX@1@PEAU21@0U?$integral_constant@_N$0A@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(std::_Tree_node<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>,void *> *,std::_Tree_node<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>,void *> *,std::integral_constant<bool,0>)
0x18000edd4  mov     rcx, [rsi]
0x18000edd7  mov     [rcx+8], rax
0x18000eddb  mov     rax, [rbp+57h+var_88]
0x18000eddf  mov     [rsi+8], rax
0x18000ede3  mov     r8, [rsi]
0x18000ede6  mov     rcx, [r8+8]
0x18000edea  cmp     [rcx+19h], r12b
0x18000edee  jnz     short loc_18000EE15
0x18000edf0  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>>::_Min(std::_Tree_node<std::pair<std::wstring const,wmi::AutoRef<Subscription>>,void *> *)
0x18000edf5  mov     [r8], rax
0x18000edf8  mov     rdx, [rsi]
0x18000edfb  mov     rcx, [rdx+8]
0x18000edff  jmp     short loc_18000EE05
0x18000ee01  mov     rcx, [rcx+10h]
0x18000ee05  mov     rax, [rcx+10h]
0x18000ee09  cmp     [rax+19h], r12b
0x18000ee0d  jz      short loc_18000EE01
0x18000ee0f  mov     [rdx+10h], rcx
0x18000ee13  jmp     short loc_18000EE1F
0x18000ee15  mov     [r8], r8
0x18000ee18  mov     rax, [rsi]
0x18000ee1b  mov     [rax+10h], rax
0x18000ee1f  lea     rbx, [r14+70h]
0x18000ee23  mov     rdx, [rbx]; Timer
0x18000ee26  test    rdx, rdx
0x18000ee29  jz      loc_18000EF02
0x18000ee2f  xor     r8d, r8d; CompletionEvent
0x18000ee32  xor     ecx, ecx; TimerQueue
0x18000ee34  call    cs:__imp_DeleteTimerQueueTimer
0x18000ee3a  mov     [rbx], r12
0x18000ee3d  test    r15b, r15b
0x18000ee40  jz      loc_18000EF02
0x18000ee46  mov     [rsp+0E0h+Flags], r12d; Flags
0x18000ee4b  mov     [rsp+0E0h+Period], r12d; Period
0x18000ee50  mov     eax, [r14+78h]
0x18000ee54  mov     [rsp+0E0h+DueTime], eax; DueTime
0x18000ee58  mov     r9, r14; Parameter
0x18000ee5b  lea     r8, ?SubscriptionExpirationCallback@SubscriptionManager@@CAXPEAXE@Z; Callback
0x18000ee62  xor     edx, edx; TimerQueue
0x18000ee64  mov     rcx, rbx; phNewTimer
0x18000ee67  call    cs:__imp_CreateTimerQueueTimer
0x18000ee6d  test    eax, eax
0x18000ee6f  jnz     loc_18000EF02
0x18000ee75  call    cs:__imp_GetLastError
0x18000ee7b  mov     ebx, eax
0x18000ee7d  mov     eax, 507h
0x18000ee82  test    ebx, ebx
0x18000ee84  cmovz   ebx, eax
0x18000ee87  lea     rax, WPP_GLOBAL_Control
0x18000ee8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee95  cmp     rcx, rax
0x18000ee98  jz      short loc_18000EEBE
0x18000ee9a  test    byte ptr [rcx+1Ch], 10h
0x18000ee9e  jz      short loc_18000EEBE
0x18000eea0  cmp     byte ptr [rcx+19h], 2
0x18000eea4  jb      short loc_18000EEBE
0x18000eea6  mov     edx, 54h ; 'T'
0x18000eeab  mov     r9d, ebx
0x18000eeae  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000eeb5  mov     rcx, [rcx+10h]
0x18000eeb9  call    WPP_SF_D
0x18000eebe  mov     [rbp+57h+var_78], r12b
0x18000eec2  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000eec9  mov     [rbp+57h+var_70], rax
0x18000eecd  mov     [rbp+57h+var_68], r12
0x18000eed1  mov     [rbp+57h+var_60], r12
0x18000eed5  mov     [rbp+57h+var_58], ebx
0x18000eed8  mov     [rbp+57h+var_54], 0FFFFFFFFh
0x18000eedf  mov     [rbp+57h+var_50], 0D6Bh
0x18000eee6  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000eeed  mov     [rbp+57h+pExceptionObject], rax
0x18000eef1  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000eef8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000eefc  call    _CxxThrowException_0
0x18000ef02  lea     rcx, [rbp+57h+var_90]
0x18000ef06  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@VCaseInsensitiveLess@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>,0>>(void)
0x18000ef0b  nop
0x18000ef0c  mov     rcx, rdi; lpCriticalSection
0x18000ef0f  call    cs:__imp_LeaveCriticalSection
0x18000ef15  mov     rcx, [rbp+57h+var_30]
0x18000ef19  xor     rcx, rsp; StackCookie
0x18000ef1c  call    __security_check_cookie
0x18000ef21  lea     r11, [rsp+0E0h+var_20]
0x18000ef29  mov     rbx, [r11+38h]
0x18000ef2d  mov     rsi, [r11+40h]
0x18000ef31  mov     rsp, r11
0x18000ef34  pop     r15
0x18000ef36  pop     r14
0x18000ef38  pop     r12
0x18000ef3a  pop     rdi
0x18000ef3b  pop     rbp
0x18000ef3c  retn
```
