# CommenceNtsKE(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18003ad30`
- end: `0x18003af1c`
- name: `?CommenceNtsKE@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `7`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180052f64`
- `0x180054058`
- `0x18005450c`
- `0x1800556a4`
- `0x180055a28`
- `0x180055bfc`
- `0x180055e44`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x180034488`
- `0x18003a6b8`
- `0x18003ad30`
- `0x18003af24`
- `0x180045abc`
- `0x180056b14`
- `0x180056e70`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003aebf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003aebf`

## string_xrefs

- `0x18003add2`: `ResetKeyExchangeEvent: Server %s has no keyExchangeCompleteEvent\n`
- `0x18003adeb`: `onecore\ds\security\services\w32time\nts\nts.cpp`
- `0x18003ad91`: `CommenceNtsKE: Failed to find server %s.\n`
- `0x18003ae2b`: `CommenceNtsKE: Server %s has no keyExchangeTimer\n`
- `0x18003ae81`: `CommenceNtsKE: Setting timer for server %s to trigger in %d seconds\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall CommenceNtsKE(_QWORD *a1)
{
  void *v2; // rdx
  __int64 v3; // rbx
  unsigned int v4; // esi
  wil::details *v5; // rcx
  unsigned __int64 v6; // r8
  int v7; // ecx
  __int64 v8; // r8
  unsigned int v9; // ecx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-18h] BYREF
  struct _RTL_CRITICAL_SECTION *v12[2]; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  wil::critical_section::lock(&g_NtsState, v12);
  std::_Tree<std::_Tmap_traits<std::wstring,NtsForNtpInfoInternal,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,NtsForNtpInfoInternal>>,0>>::find(
    &qword_1800A4928,
    &v14,
    a1);
  v3 = v14;
  if ( v14 == qword_1800A4928 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(200) )
    {
      if ( a1[3] > 7u )
        a1 = (_QWORD *)*a1;
      FileLogAdd(L"CommenceNtsKE: Failed to find server %s.\n", a1);
    }
    v4 = -2147023728;
  }
  else
  {
    v5 = *(wil::details **)(v14 + 328);
    v4 = 0;
    if ( v5 )
    {
      wil::details::ResetEvent(v5, v2);
      if ( *(_QWORD *)(v3 + 336) )
      {
        if ( (unsigned __int8)FileLogAllowEntry(200) )
        {
          v6 = NtsPollInfo::timeRemaining((NtsPollInfo *)(v3 + 248)) / 0x3E8;
          if ( a1[3] > 7u )
            a1 = (_QWORD *)*a1;
          FileLogAdd(L"CommenceNtsKE: Setting timer for server %s to trigger in %d seconds\n", a1, v6);
        }
        pftDueTime = (struct _FILETIME)(-10000LL * NtsPollInfo::timeRemaining((NtsPollInfo *)(v3 + 248)));
        SetThreadpoolTimer(*(PTP_TIMER *)(v3 + 336), &pftDueTime, 0, 0);
        v7 = dword_1800A494C;
        v8 = *(_QWORD *)(v3 + 248);
        *(_QWORD *)(v3 + 240) = v8;
        v9 = *(_DWORD *)(v3 + 260) + v7;
        if ( v9 > 0xF )
          LOBYTE(v9) = 15;
        *(_QWORD *)(v3 + 248) = v8 + 1000 * (1 << v9);
      }
      else
      {
        if ( (unsigned __int8)FileLogAllowEntry(200) )
        {
          if ( a1[3] > 7u )
            a1 = (_QWORD *)*a1;
          FileLogAdd(L"CommenceNtsKE: Server %s has no keyExchangeTimer\n", a1);
        }
        v4 = -2147024890;
      }
    }
    else
    {
      if ( (unsigned __int8)FileLogAllowEntry(200) )
        FileLogAdd(L"ResetKeyExchangeEvent: Server %s has no keyExchangeCompleteEvent\n");
      v4 = -2147024890;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15F,
        (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\nts.cpp",
        (const char *)0x80070006LL,
        pftDueTime.dwLowDateTime);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v12);
  return v4;
}

```

## disassembly

```asm
0x18003ad30  mov     [rsp+arg_0], rbx
0x18003ad35  mov     [rsp+arg_10], rsi
0x18003ad3a  push    rdi
0x18003ad3b  sub     rsp, 30h
0x18003ad3f  mov     rdi, rcx
0x18003ad42  lea     rdx, [rsp+38h+var_10]
0x18003ad47  lea     rcx, ?g_NtsState@@3UNtsState@@A; NtsState g_NtsState
0x18003ad4e  call    ?lock@critical_section@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::critical_section::lock(void)
0x18003ad53  nop
0x18003ad54  mov     r8, rdi
0x18003ad57  lea     rdx, [rsp+38h+arg_8]
0x18003ad5c  lea     rcx, qword_1800A4928
0x18003ad63  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,NtsForNtpInfoInternal,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,NtsForNtpInfoInternal>>,0>>::find(std::wstring const &)
0x18003ad68  mov     rbx, [rsp+38h+arg_8]
0x18003ad6d  cmp     rbx, cs:qword_1800A4928
0x18003ad74  jnz     short loc_18003ADA8
0x18003ad76  mov     ecx, 0C8h
0x18003ad7b  call    FileLogAllowEntry
0x18003ad80  test    al, al
0x18003ad82  jz      short loc_18003AD9E
0x18003ad84  cmp     qword ptr [rdi+18h], 7
0x18003ad89  jbe     short loc_18003AD8E
0x18003ad8b  mov     rdi, [rdi]
0x18003ad8e  mov     rdx, rdi
0x18003ad91  lea     rcx, aCommencentskeF; "CommenceNtsKE: Failed to find server %s"...
0x18003ad98  call    FileLogAdd
0x18003ad9d  nop
0x18003ad9e  mov     esi, 80070490h
0x18003ada3  jmp     loc_18003AEFF
0x18003ada8  mov     rcx, [rbx+148h]; this
0x18003adaf  xor     esi, esi
0x18003adb1  test    rcx, rcx
0x18003adb4  jnz     short loc_18003AE02
0x18003adb6  mov     ecx, 0C8h
0x18003adbb  call    FileLogAllowEntry
0x18003adc0  test    al, al
0x18003adc2  jz      short loc_18003ADDE
0x18003adc4  lea     rdx, [rbx+48h]
0x18003adc8  cmp     qword ptr [rdx+18h], 7
0x18003adcd  jbe     short loc_18003ADD2
0x18003adcf  mov     rdx, [rdx]
0x18003add2  lea     rcx, aResetkeyexchan; "ResetKeyExchangeEvent: Server %s has no"...
0x18003add9  call    FileLogAdd
0x18003adde  mov     rcx, [rsp+38h]; this
0x18003ade3  mov     esi, 80070006h
0x18003ade8  mov     r9d, esi; char *
0x18003adeb  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\services\\w32tim"...
0x18003adf2  mov     edx, 15Fh; void *
0x18003adf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003adfc  nop
0x18003adfd  jmp     loc_18003AEFF
0x18003ae02  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x18003ae07  mov     ecx, 0C8h
0x18003ae0c  cmp     [rbx+150h], rsi
0x18003ae13  jnz     short loc_18003AE42
0x18003ae15  call    FileLogAllowEntry
0x18003ae1a  test    al, al
0x18003ae1c  jz      short loc_18003AE38
0x18003ae1e  cmp     qword ptr [rdi+18h], 7
0x18003ae23  jbe     short loc_18003AE28
0x18003ae25  mov     rdi, [rdi]
0x18003ae28  mov     rdx, rdi
0x18003ae2b  lea     rcx, aCommencentskeS_0; "CommenceNtsKE: Server %s has no keyExch"...
0x18003ae32  call    FileLogAdd
0x18003ae37  nop
0x18003ae38  mov     esi, 80070006h
0x18003ae3d  jmp     loc_18003AEFF
0x18003ae42  call    FileLogAllowEntry
0x18003ae47  test    al, al
0x18003ae49  jz      short loc_18003AE8D
0x18003ae4b  lea     rcx, [rbx+0F8h]; this
0x18003ae52  call    ?timeRemaining@NtsPollInfo@@QEAA_KXZ; NtsPollInfo::timeRemaining(void)
0x18003ae57  mov     r8, rax
0x18003ae5a  mov     rax, 624DD2F1A9FBE77h
0x18003ae64  mul     r8
0x18003ae67  sub     r8, rdx
0x18003ae6a  shr     r8, 1
0x18003ae6d  add     r8, rdx
0x18003ae70  shr     r8, 9
0x18003ae74  cmp     qword ptr [rdi+18h], 7
0x18003ae79  jbe     short loc_18003AE7E
0x18003ae7b  mov     rdi, [rdi]
0x18003ae7e  mov     rdx, rdi
0x18003ae81  lea     rcx, aCommencentskeS; "CommenceNtsKE: Setting timer for server"...
0x18003ae88  call    FileLogAdd
0x18003ae8d  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rsi
0x18003ae92  lea     rdi, [rbx+0F8h]
0x18003ae99  mov     rcx, rdi; this
0x18003ae9c  call    ?timeRemaining@NtsPollInfo@@QEAA_KXZ; NtsPollInfo::timeRemaining(void)
0x18003aea1  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x18003aea8  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rcx
0x18003aead  xor     r9d, r9d; msWindowLength
0x18003aeb0  xor     r8d, r8d; msPeriod
0x18003aeb3  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18003aeb8  mov     rcx, [rbx+150h]; pti
0x18003aebf  call    cs:__imp_SetThreadpoolTimer
0x18003aec6  nop     dword ptr [rax+rax+00h]
0x18003aecb  mov     ecx, cs:dword_1800A494C
0x18003aed1  mov     r8, [rdi]
0x18003aed4  mov     [rbx+0F0h], r8
0x18003aedb  add     ecx, [rbx+104h]
0x18003aee1  mov     eax, 0Fh
0x18003aee6  cmp     ecx, eax
0x18003aee8  cmova   ecx, eax
0x18003aeeb  lea     edx, [rax-0Eh]
0x18003aeee  shl     edx, cl
0x18003aef0  imul    ecx, edx, 3E8h
0x18003aef6  movsxd  rdx, ecx
0x18003aef9  add     rdx, r8
0x18003aefc  mov     [rdi], rdx
0x18003aeff  lea     rcx, [rsp+38h+var_10]
0x18003af04  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003af09  mov     eax, esi
0x18003af0b  mov     rbx, [rsp+38h+arg_0]
0x18003af10  mov     rsi, [rsp+38h+arg_10]
0x18003af15  add     rsp, 30h
0x18003af19  pop     rdi
0x18003af1a  retn
```
