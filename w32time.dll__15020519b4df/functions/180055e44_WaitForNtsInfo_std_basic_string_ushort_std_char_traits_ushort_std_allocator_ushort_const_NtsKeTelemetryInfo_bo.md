# WaitForNtsInfo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,NtsKeTelemetryInfo &,bool)

- ea: `0x180055e44`
- end: `0x180056138`
- name: `?WaitForNtsInfo@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUNtsKeTelemetryInfo@@_N@Z`
- size: `756`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180054690`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x180034488`
- `0x18003a6b8`
- `0x18003ad30`
- `0x180045abc`
- `0x180053658`
- `0x18005450c`
- `0x180055e44`
- `0x180056b14`
- `0x180056e70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180056014`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180056014`

## string_xrefs

- `0x180055f98`: `onecore\ds\security\services\w32time\nts\nts.cpp`
- `0x180055efb`: `WaitForNtsInfo: Server %s has no keyExchangeCompleteEvent\n`
- `0x180055f6b`: `WaitForNtsInfo: Forcing resync for server %s even though it wasn't scheduled to trigger for %d seconds\n`
- `0x180055fd8`: `WaitForNtsInfo: Not waiting for server %s as KE isn't scheduled to trigger for %d seconds.\n`
- `0x180056112`: `WaitForNtsInfo: Server %s failed while waiting for KE to complete with unexpected error: 0x%08X\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WaitForNtsInfo(_QWORD *a1, struct NtsKeTelemetryInfo *a2, char a3)
{
  __int64 v6; // rbx
  unsigned int NtsInfoWhenSignaled; // esi
  unsigned __int64 v8; // rsi
  char v9; // al
  _QWORD *v10; // rcx
  int v11; // eax
  struct _RTL_CRITICAL_SECTION **v12; // rcx
  void *v14; // rbx
  signed int v15; // ebx
  __int64 v16; // r8
  struct _RTL_CRITICAL_SECTION *v17; // [rsp+20h] [rbp-48h] BYREF
  struct _RTL_CRITICAL_SECTION *v18[8]; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v20; // [rsp+88h] [rbp+20h] BYREF

  wil::critical_section::lock(&g_NtsState, &v17);
  std::_Tree<std::_Tmap_traits<std::wstring,NtsForNtpInfoInternal,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,NtsForNtpInfoInternal>>,0>>::find(
    &qword_1800A4928,
    &v20,
    a1);
  v6 = v20;
  if ( v20 == qword_1800A4928 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(200) )
    {
      if ( a1[3] > 7u )
        a1 = (_QWORD *)*a1;
      FileLogAdd(L"WaitForNtsInfo: Failed to find server %s.\n", a1);
    }
    NtsInfoWhenSignaled = -2147023728;
    goto LABEL_27;
  }
  v8 = NtsPollInfo::timeRemaining((NtsPollInfo *)(v20 + 240));
  if ( !*(_QWORD *)(v6 + 328) )
  {
    if ( (unsigned __int8)FileLogAllowEntry(200) )
    {
      if ( a1[3] > 7u )
        a1 = (_QWORD *)*a1;
      FileLogAdd(L"WaitForNtsInfo: Server %s has no keyExchangeCompleteEvent\n", a1);
    }
    NtsInfoWhenSignaled = -2147024890;
    goto LABEL_27;
  }
  NtsForNtpInfo::operator=(a2, v6 + 64);
  if ( v8 > 0x1F4 )
  {
    v9 = FileLogAllowEntry(200);
    if ( !a3 )
    {
      if ( v9 )
      {
        if ( a1[3] > 7u )
          a1 = (_QWORD *)*a1;
        FileLogAdd(
          L"WaitForNtsInfo: Not waiting for server %s as KE isn't scheduled to trigger for %d seconds.\n",
          a1,
          v8 / 0x3E8);
      }
      NtsInfoWhenSignaled = -2147483638;
      goto LABEL_27;
    }
    if ( v9 )
    {
      if ( a1[3] <= 7u )
        v10 = a1;
      else
        v10 = (_QWORD *)*a1;
      FileLogAdd(
        L"WaitForNtsInfo: Forcing resync for server %s even though it wasn't scheduled to trigger for %d seconds\n",
        v10,
        v8 / 0x3E8);
    }
    *(_QWORD *)(v6 + 248) = 0;
    v11 = CommenceNtsKE(a1);
    NtsInfoWhenSignaled = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x29E,
        (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\nts.cpp",
        (const char *)(unsigned int)v11,
        (int)v17);
LABEL_27:
      v12 = &v17;
LABEL_28:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v12);
      return NtsInfoWhenSignaled;
    }
  }
  v14 = *(void **)(v6 + 328);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v17);
  v15 = WaitForSingleObject(v14, 0x1F4u);
  if ( v15 == 258 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(200) )
    {
      if ( a1[3] > 7u )
        a1 = (_QWORD *)*a1;
      FileLogAdd(L"WaitForNtsInfo: Timed out while waiting for server %s to finish KE.\n", a1);
    }
    return 2147483658LL;
  }
  else
  {
    if ( !v15 )
    {
      wil::critical_section::lock(&g_NtsState, v18);
      std::_Tree<std::_Tmap_traits<std::wstring,NtsForNtpInfoInternal,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,NtsForNtpInfoInternal>>,0>>::find(
        &qword_1800A4928,
        &v20,
        a1);
      if ( v20 == qword_1800A4928 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(200) )
        {
          if ( a1[3] > 7u )
            a1 = (_QWORD *)*a1;
          FileLogAdd(L"WaitForNtsInfo: Failed to find server %s.\n", a1);
        }
        NtsInfoWhenSignaled = -2147023728;
      }
      else
      {
        NtsInfoWhenSignaled = GetNtsInfoWhenSignaled((struct NtsForNtpInfoInternal *)(v20 + 64), a2);
      }
      v12 = v18;
      goto LABEL_28;
    }
    if ( (unsigned __int8)FileLogAllowEntry(200) )
    {
      if ( v15 > 0 )
        v16 = (unsigned __int16)v15 | 0x80070000;
      else
        v16 = (unsigned int)v15;
      if ( a1[3] > 7u )
        a1 = (_QWORD *)*a1;
      FileLogAdd(
        L"WaitForNtsInfo: Server %s failed while waiting for KE to complete with unexpected error: 0x%08X\n",
        a1,
        v16);
    }
    if ( v15 > 0 )
      return (unsigned __int16)v15 | 0x80070000;
    return (unsigned int)v15;
  }
}

```

## disassembly

```asm
0x180055e44  push    rbx
0x180055e46  push    rsi
0x180055e47  push    rdi
0x180055e48  push    r12
0x180055e4a  push    r14
0x180055e4c  push    r15
0x180055e4e  sub     rsp, 38h
0x180055e52  mov     r12b, r8b
0x180055e55  mov     r15, rdx
0x180055e58  mov     rdi, rcx
0x180055e5b  lea     rdx, [rsp+68h+var_48]
0x180055e60  lea     rcx, ?g_NtsState@@3UNtsState@@A; NtsState g_NtsState
0x180055e67  call    ?lock@critical_section@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::critical_section::lock(void)
0x180055e6c  nop
0x180055e6d  mov     r8, rdi
0x180055e70  lea     rdx, [rsp+68h+arg_18]
0x180055e78  lea     rcx, qword_1800A4928
0x180055e7f  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,NtsForNtpInfoInternal,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,NtsForNtpInfoInternal>>,0>>::find(std::wstring const &)
0x180055e84  mov     rbx, [rsp+68h+arg_18]
0x180055e8c  cmp     rbx, cs:qword_1800A4928
0x180055e93  jnz     short loc_180055EC7
0x180055e95  mov     ecx, 0C8h
0x180055e9a  call    FileLogAllowEntry
0x180055e9f  test    al, al
0x180055ea1  jz      short loc_180055EBD
0x180055ea3  cmp     qword ptr [rdi+18h], 7
0x180055ea8  jbe     short loc_180055EAD
0x180055eaa  mov     rdi, [rdi]
0x180055ead  mov     rdx, rdi
0x180055eb0  lea     rcx, aWaitforntsinfo_0; "WaitForNtsInfo: Failed to find server %"...
0x180055eb7  call    FileLogAdd
0x180055ebc  nop
0x180055ebd  mov     esi, 80070490h
0x180055ec2  jmp     loc_180055FEA
0x180055ec7  lea     rcx, [rbx+0F0h]; this
0x180055ece  call    ?timeRemaining@NtsPollInfo@@QEAA_KXZ; NtsPollInfo::timeRemaining(void)
0x180055ed3  mov     rsi, rax
0x180055ed6  cmp     qword ptr [rbx+148h], 0
0x180055ede  jnz     short loc_180055F12
0x180055ee0  mov     ecx, 0C8h
0x180055ee5  call    FileLogAllowEntry
0x180055eea  test    al, al
0x180055eec  jz      short loc_180055F08
0x180055eee  cmp     qword ptr [rdi+18h], 7
0x180055ef3  jbe     short loc_180055EF8
0x180055ef5  mov     rdi, [rdi]
0x180055ef8  mov     rdx, rdi
0x180055efb  lea     rcx, aWaitforntsinfo_3; "WaitForNtsInfo: Server %s has no keyExc"...
0x180055f02  call    FileLogAdd
0x180055f07  nop
0x180055f08  mov     esi, 80070006h
0x180055f0d  jmp     loc_180055FEA
0x180055f12  lea     rdx, [rbx+40h]
0x180055f16  mov     rcx, r15
0x180055f19  call    ??4NtsForNtpInfo@@QEAAAEAU0@AEBU0@@Z; NtsForNtpInfo::operator=(NtsForNtpInfo const &)
0x180055f1e  cmp     rsi, 1F4h
0x180055f25  jbe     loc_180055FFB
0x180055f2b  mov     ecx, 0C8h
0x180055f30  call    FileLogAllowEntry
0x180055f35  test    r12b, r12b
0x180055f38  jz      short loc_180055FAC
0x180055f3a  test    al, al
0x180055f3c  jz      short loc_180055F77
0x180055f3e  cmp     qword ptr [rdi+18h], 7
0x180055f43  jbe     short loc_180055F4A
0x180055f45  mov     rcx, [rdi]
0x180055f48  jmp     short loc_180055F4D
0x180055f4a  mov     rcx, rdi
0x180055f4d  mov     rax, 624DD2F1A9FBE77h
0x180055f57  mul     rsi
0x180055f5a  sub     rsi, rdx
0x180055f5d  shr     rsi, 1
0x180055f60  lea     r8, [rdx+rsi]
0x180055f64  shr     r8, 9
0x180055f68  mov     rdx, rcx
0x180055f6b  lea     rcx, aWaitforntsinfo; "WaitForNtsInfo: Forcing resync for serv"...
0x180055f72  call    FileLogAdd
0x180055f77  mov     qword ptr [rbx+0F8h], 0
0x180055f82  mov     rcx, rdi
0x180055f85  call    ?CommenceNtsKE@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CommenceNtsKE(std::wstring const &)
0x180055f8a  mov     esi, eax
0x180055f8c  test    eax, eax
0x180055f8e  jns     short loc_180055FFB
0x180055f90  mov     rcx, [rsp+68h]; this
0x180055f95  mov     r9d, eax; char *
0x180055f98  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\services\\w32tim"...
0x180055f9f  mov     edx, 29Eh; void *
0x180055fa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055fa9  nop
0x180055faa  jmp     short loc_180055FEA
0x180055fac  test    al, al
0x180055fae  jz      short loc_180055FE5
0x180055fb0  cmp     qword ptr [rdi+18h], 7
0x180055fb5  jbe     short loc_180055FBA
0x180055fb7  mov     rdi, [rdi]
0x180055fba  mov     rax, 624DD2F1A9FBE77h
0x180055fc4  mul     rsi
0x180055fc7  sub     rsi, rdx
0x180055fca  shr     rsi, 1
0x180055fcd  lea     r8, [rdx+rsi]
0x180055fd1  shr     r8, 9
0x180055fd5  mov     rdx, rdi
0x180055fd8  lea     rcx, aWaitforntsinfo_2; "WaitForNtsInfo: Not waiting for server "...
0x180055fdf  call    FileLogAdd
0x180055fe4  nop
0x180055fe5  mov     esi, 8000000Ah
0x180055fea  lea     rcx, [rsp+68h+var_48]
0x180055fef  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180055ff4  mov     eax, esi
0x180055ff6  jmp     loc_180056129
0x180055ffb  mov     rbx, [rbx+148h]
0x180056002  lea     rcx, [rsp+68h+var_48]
0x180056007  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18005600c  mov     edx, 1F4h; dwMilliseconds
0x180056011  mov     rcx, rbx; hHandle
0x180056014  call    cs:__imp_WaitForSingleObject
0x18005601b  nop     dword ptr [rax+rax+00h]
0x180056020  mov     ebx, eax
0x180056022  cmp     eax, 102h
0x180056027  jnz     short loc_180056058
0x180056029  lea     ecx, [rax-3Ah]
0x18005602c  call    FileLogAllowEntry
0x180056031  test    al, al
0x180056033  jz      short loc_18005604E
0x180056035  cmp     qword ptr [rdi+18h], 7
0x18005603a  jbe     short loc_18005603F
0x18005603c  mov     rdi, [rdi]
0x18005603f  mov     rdx, rdi
0x180056042  lea     rcx, aWaitforntsinfo_4; "WaitForNtsInfo: Timed out while waiting"...
0x180056049  call    FileLogAdd
0x18005604e  mov     eax, 8000000Ah
0x180056053  jmp     loc_180056129
0x180056058  test    ebx, ebx
0x18005605a  jnz     loc_1800560E2
0x180056060  lea     rdx, [rsp+68h+var_40]
0x180056065  lea     rcx, ?g_NtsState@@3UNtsState@@A; NtsState g_NtsState
0x18005606c  call    ?lock@critical_section@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::critical_section::lock(void)
0x180056071  nop
0x180056072  mov     r8, rdi
0x180056075  lea     rdx, [rsp+68h+arg_18]
0x18005607d  lea     rcx, qword_1800A4928
0x180056084  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,NtsForNtpInfoInternal,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,NtsForNtpInfoInternal>>,0>>::find(std::wstring const &)
0x180056089  mov     rcx, [rsp+68h+arg_18]
0x180056091  cmp     rcx, cs:qword_1800A4928
0x180056098  jnz     short loc_1800560C9
0x18005609a  mov     ecx, 0C8h
0x18005609f  call    FileLogAllowEntry
0x1800560a4  test    al, al
0x1800560a6  jz      short loc_1800560C2
0x1800560a8  cmp     qword ptr [rdi+18h], 7
0x1800560ad  jbe     short loc_1800560B2
0x1800560af  mov     rdi, [rdi]
0x1800560b2  mov     rdx, rdi
0x1800560b5  lea     rcx, aWaitforntsinfo_0; "WaitForNtsInfo: Failed to find server %"...
0x1800560bc  call    FileLogAdd
0x1800560c1  nop
0x1800560c2  mov     esi, 80070490h
0x1800560c7  jmp     short loc_1800560D8
0x1800560c9  add     rcx, 40h ; '@'; struct NtsForNtpInfoInternal *
0x1800560cd  mov     rdx, r15; struct NtsKeTelemetryInfo *
0x1800560d0  call    ?GetNtsInfoWhenSignaled@@YAJAEAUNtsForNtpInfoInternal@@AEAUNtsKeTelemetryInfo@@@Z; GetNtsInfoWhenSignaled(NtsForNtpInfoInternal &,NtsKeTelemetryInfo &)
0x1800560d5  nop
0x1800560d6  mov     esi, eax
0x1800560d8  lea     rcx, [rsp+68h+var_40]
0x1800560dd  jmp     loc_180055FEF
0x1800560e2  mov     ecx, 0C8h
0x1800560e7  call    FileLogAllowEntry
0x1800560ec  mov     esi, 80070000h
0x1800560f1  test    al, al
0x1800560f3  jz      short loc_18005611E
0x1800560f5  test    ebx, ebx
0x1800560f7  jg      short loc_1800560FE
0x1800560f9  mov     r8d, ebx
0x1800560fc  jmp     short loc_180056105
0x1800560fe  movzx   r8d, bx
0x180056102  or      r8d, esi
0x180056105  cmp     qword ptr [rdi+18h], 7
0x18005610a  jbe     short loc_18005610F
0x18005610c  mov     rdi, [rdi]
0x18005610f  mov     rdx, rdi
0x180056112  lea     rcx, aWaitforntsinfo_1; "WaitForNtsInfo: Server %s failed while "...
0x180056119  call    FileLogAdd
0x18005611e  test    ebx, ebx
0x180056120  jle     short loc_180056127
0x180056122  movzx   ebx, bx
0x180056125  or      ebx, esi
0x180056127  mov     eax, ebx
0x180056129  add     rsp, 38h
0x18005612d  pop     r15
0x18005612f  pop     r14
0x180056131  pop     r12
0x180056133  pop     rdi
0x180056134  pop     rsi
0x180056135  pop     rbx
0x180056136  retn
```
