# ValidateNtsNtpPacket(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,char *,ulong &)

- ea: `0x180055bfc`
- end: `0x180055e3c`
- name: `?ValidateNtsNtpPacket@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEADAEAK@Z`
- size: `576`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180035560`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x180034488`
- `0x18003a6a0`
- `0x18003ad30`
- `0x180055bfc`
- `0x180056b14`
- `0x180057d6c`
- `0x18005862c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180055d5d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180055d5d`

## string_xrefs

- `0x180055dd2`: `ValidateNtsNtpPacket: server %s has used up it's last cookie so attempt to queue a KE workitem to get more\n`
- `0x180055e0a`: `ValidateNtsNtpPacket: Unable to commenceNtsKE for %s due to error: 0x%08X. Ignoring error.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ValidateNtsNtpPacket(_QWORD *a1, unsigned __int8 *a2, unsigned int *a3)
{
  const char *v6; // r9
  __int64 result; // rax
  __int64 v8; // rsi
  _QWORD *v9; // rdx
  int v10; // r15d
  struct _TP_TIMER *v11; // rcx
  _QWORD *v12; // rdx
  _QWORD *v13; // rdx
  int v14; // esi
  _QWORD v15[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v17; // [rsp+88h] [rbp+20h] BYREF

  try
  {
    wil::critical_section::lock(&g_NtsState, &v17);
    std::_Tree<std::_Tmap_traits<std::wstring,NtsForNtpInfoInternal,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,NtsForNtpInfoInternal>>,0>>::find(
      &qword_1800A4928,
      v15,
      a1);
    v15[1] = qword_1800A4928;
    if ( v15[0] == qword_1800A4928 )
    {
      EmitValidateNtsNtpPacketTelemetry(-2147023728, (_DWORD)a1, *a3, 0, 0);
      if ( (unsigned __int8)FileLogAllowEntry(200) )
      {
        if ( a1[3] > 7u )
          a1 = (_QWORD *)*a1;
        FileLogAdd(L"ValidateNtsNtpPacket: couldn't find server %s\n", a1);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>();
      result = 2147943568LL;
    }
    else
    {
      v8 = v15[0] + 64LL;
      if ( *(_QWORD *)(v15[0] + 272LL) )
      {
        v10 = HandleReceivedNtsExtensions((struct NtsForNtpInfoInternal *)(v15[0] + 64LL), a2, *a3);
        EmitValidateNtsNtpPacketTelemetry(v10, (_DWORD)a1, *a3, *(_DWORD *)(v8 + 248), 0);
        if ( v10 >= 0 )
        {
          if ( *(_BYTE *)(v8 + 200) )
          {
            v11 = *(struct _TP_TIMER **)(v8 + 272);
            if ( v11 )
            {
              SetThreadpoolTimer(v11, 0, 0, 0);
            }
            else if ( (unsigned __int8)FileLogAllowEntry(200) )
            {
              if ( a1[3] <= 7u )
                v12 = a1;
              else
                v12 = (_QWORD *)*a1;
              FileLogAdd(L"ValidateNtsNtpPacket: server %s has no keyExchangeTimer\n", v12);
            }
            *(_BYTE *)(v8 + 200) = 0;
          }
          *(_DWORD *)(v8 + 196) = 0;
          if ( *(_QWORD *)(v8 + 216) == *(_QWORD *)(v8 + 224) )
          {
            if ( (unsigned __int8)FileLogAllowEntry(200) )
            {
              if ( a1[3] <= 7u )
                v13 = a1;
              else
                v13 = (_QWORD *)*a1;
              FileLogAdd(
                L"ValidateNtsNtpPacket: server %s has used up it's last cookie so attempt to queue a KE workitem to get more\n",
                v13);
            }
            v14 = CommenceNtsKE(a1);
            if ( v14 < 0 && (unsigned __int8)FileLogAllowEntry(200) )
            {
              if ( a1[3] > 7u )
                a1 = (_QWORD *)*a1;
              FileLogAdd(
                L"ValidateNtsNtpPacket: Unable to commenceNtsKE for %s due to error: 0x%08X. Ignoring error.\n",
                a1,
                (unsigned int)v14);
            }
          }
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>();
        result = (unsigned int)v10;
      }
      else
      {
        if ( (unsigned __int8)FileLogAllowEntry(200) )
        {
          if ( a1[3] <= 7u )
            v9 = a1;
          else
            v9 = (_QWORD *)*a1;
          FileLogAdd(L"ValidateNtsNtpPacket: server %s has no crypto wrapper\n", v9);
        }
        EmitValidateNtsNtpPacketTelemetry(-2147024809, (_DWORD)a1, *a3, *(_DWORD *)(v8 + 248), 0);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>();
        result = 2147942487LL;
      }
    }
  }
  catch ( ... )
  {
    LODWORD(v17) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x361,
                     (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\nts.cpp",
                     v6);
    return (unsigned int)v17;
  }
  return result;
}

```

## disassembly

```asm
0x180055bfc  mov     rax, rsp
0x180055bff  push    rbx
0x180055c00  push    rsi
0x180055c01  push    r14
0x180055c03  push    r15
0x180055c05  sub     rsp, 48h
0x180055c09  mov     r14, r8
0x180055c0c  mov     r15, rdx
0x180055c0f  mov     rbx, rcx
0x180055c12  lea     rdx, [rax+20h]
0x180055c16  lea     rcx, ?g_NtsState@@3UNtsState@@A; NtsState g_NtsState
0x180055c1d  call    ?lock@critical_section@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::critical_section::lock(void)
0x180055c22  nop
0x180055c23  mov     r8, rbx
0x180055c26  lea     rdx, [rsp+68h+var_38]
0x180055c2b  lea     rcx, qword_1800A4928
0x180055c32  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,NtsForNtpInfoInternal,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,NtsForNtpInfoInternal>>,0>>::find(std::wstring const &)
0x180055c37  mov     rcx, cs:qword_1800A4928
0x180055c3e  mov     [rsp+68h+var_30], rcx
0x180055c43  mov     rax, [rsp+68h+var_38]
0x180055c48  cmp     rax, rcx
0x180055c4b  jnz     short loc_180055CA3
0x180055c4d  mov     [rsp+68h+var_48], 0
0x180055c52  xor     r9d, r9d
0x180055c55  mov     r8d, [r14]
0x180055c58  mov     rdx, rbx
0x180055c5b  mov     esi, 80070490h
0x180055c60  mov     ecx, esi
0x180055c62  call    ?EmitValidateNtsNtpPacketTelemetry@@YAXJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KK_N@Z; EmitValidateNtsNtpPacketTelemetry(long,std::wstring &,ulong,ulong,bool)
0x180055c67  mov     ecx, 0C8h
0x180055c6c  call    FileLogAllowEntry
0x180055c71  test    al, al
0x180055c73  jz      short loc_180055C8F
0x180055c75  cmp     qword ptr [rbx+18h], 7
0x180055c7a  jbe     short loc_180055C7F
0x180055c7c  mov     rbx, [rbx]
0x180055c7f  mov     rdx, rbx
0x180055c82  lea     rcx, aValidatentsntp_0; "ValidateNtsNtpPacket: couldn't find ser"...
0x180055c89  call    FileLogAdd
0x180055c8e  nop
0x180055c8f  lea     rcx, [rsp+68h+arg_18]
0x180055c97  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180055c9c  mov     eax, esi
0x180055c9e  jmp     loc_180055E30
0x180055ca3  lea     rsi, [rax+40h]
0x180055ca7  cmp     qword ptr [rsi+0D0h], 0
0x180055caf  jnz     short loc_180055D0D
0x180055cb1  mov     ecx, 0C8h
0x180055cb6  call    FileLogAllowEntry
0x180055cbb  test    al, al
0x180055cbd  jz      short loc_180055CDA
0x180055cbf  cmp     qword ptr [rbx+18h], 7
0x180055cc4  jbe     short loc_180055CCB
0x180055cc6  mov     rdx, [rbx]
0x180055cc9  jmp     short loc_180055CCE
0x180055ccb  mov     rdx, rbx
0x180055cce  lea     rcx, aValidatentsntp_3; "ValidateNtsNtpPacket: server %s has no "...
0x180055cd5  call    FileLogAdd
0x180055cda  mov     [rsp+68h+var_48], 0
0x180055cdf  mov     r9d, [rsi+0F8h]
0x180055ce6  mov     r8d, [r14]
0x180055ce9  mov     rdx, rbx
0x180055cec  mov     ebx, 80070057h
0x180055cf1  mov     ecx, ebx
0x180055cf3  call    ?EmitValidateNtsNtpPacketTelemetry@@YAXJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KK_N@Z; EmitValidateNtsNtpPacketTelemetry(long,std::wstring &,ulong,ulong,bool)
0x180055cf8  nop
0x180055cf9  lea     rcx, [rsp+68h+arg_18]
0x180055d01  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180055d06  mov     eax, ebx
0x180055d08  jmp     loc_180055E30
0x180055d0d  mov     r8d, [r14]; unsigned int
0x180055d10  mov     rdx, r15; unsigned __int8 *
0x180055d13  mov     rcx, rsi; struct NtsForNtpInfoInternal *
0x180055d16  call    ?HandleReceivedNtsExtensions@@YAJAEAUNtsForNtpInfoInternal@@PEAXK@Z; HandleReceivedNtsExtensions(NtsForNtpInfoInternal &,void *,ulong)
0x180055d1b  mov     r15d, eax
0x180055d1e  mov     [rsp+68h+var_48], 0
0x180055d23  mov     r9d, [rsi+0F8h]
0x180055d2a  mov     r8d, [r14]
0x180055d2d  mov     rdx, rbx
0x180055d30  mov     ecx, eax
0x180055d32  call    ?EmitValidateNtsNtpPacketTelemetry@@YAXJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KK_N@Z; EmitValidateNtsNtpPacketTelemetry(long,std::wstring &,ulong,ulong,bool)
0x180055d37  test    r15d, r15d
0x180055d3a  js      loc_180055E17
0x180055d40  cmp     byte ptr [rsi+0C8h], 0
0x180055d47  jz      short loc_180055D9B
0x180055d49  mov     rcx, [rsi+110h]; pti
0x180055d50  test    rcx, rcx
0x180055d53  jz      short loc_180055D6B
0x180055d55  xor     r9d, r9d; msWindowLength
0x180055d58  xor     r8d, r8d; msPeriod
0x180055d5b  xor     edx, edx; pftDueTime
0x180055d5d  call    cs:__imp_SetThreadpoolTimer
0x180055d64  nop     dword ptr [rax+rax+00h]
0x180055d69  jmp     short loc_180055D94
0x180055d6b  mov     ecx, 0C8h
0x180055d70  call    FileLogAllowEntry
0x180055d75  test    al, al
0x180055d77  jz      short loc_180055D94
0x180055d79  cmp     qword ptr [rbx+18h], 7
0x180055d7e  jbe     short loc_180055D85
0x180055d80  mov     rdx, [rbx]
0x180055d83  jmp     short loc_180055D88
0x180055d85  mov     rdx, rbx
0x180055d88  lea     rcx, aValidatentsntp; "ValidateNtsNtpPacket: server %s has no "...
0x180055d8f  call    FileLogAdd
0x180055d94  mov     byte ptr [rsi+0C8h], 0
0x180055d9b  mov     dword ptr [rsi+0C4h], 0
0x180055da5  mov     rax, [rsi+0E0h]
0x180055dac  cmp     [rsi+0D8h], rax
0x180055db3  jnz     short loc_180055E17
0x180055db5  mov     ecx, 0C8h
0x180055dba  call    FileLogAllowEntry
0x180055dbf  test    al, al
0x180055dc1  jz      short loc_180055DDE
0x180055dc3  cmp     qword ptr [rbx+18h], 7
0x180055dc8  jbe     short loc_180055DCF
0x180055dca  mov     rdx, [rbx]
0x180055dcd  jmp     short loc_180055DD2
0x180055dcf  mov     rdx, rbx
0x180055dd2  lea     rcx, aValidatentsntp_1; "ValidateNtsNtpPacket: server %s has use"...
0x180055dd9  call    FileLogAdd
0x180055dde  mov     rcx, rbx
0x180055de1  call    ?CommenceNtsKE@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CommenceNtsKE(std::wstring const &)
0x180055de6  mov     esi, eax
0x180055de8  test    eax, eax
0x180055dea  jns     short loc_180055E17
0x180055dec  mov     ecx, 0C8h
0x180055df1  call    FileLogAllowEntry
0x180055df6  test    al, al
0x180055df8  jz      short loc_180055E17
0x180055dfa  cmp     qword ptr [rbx+18h], 7
0x180055dff  jbe     short loc_180055E04
0x180055e01  mov     rbx, [rbx]
0x180055e04  mov     r8d, esi
0x180055e07  mov     rdx, rbx
0x180055e0a  lea     rcx, aValidatentsntp_2; "ValidateNtsNtpPacket: Unable to commenc"...
0x180055e11  call    FileLogAdd
0x180055e16  nop
0x180055e17  lea     rcx, [rsp+68h+arg_18]
0x180055e1f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180055e24  mov     eax, r15d
0x180055e27  jmp     short loc_180055E30
0x180055e29  mov     eax, dword ptr [rsp+68h+arg_18]
0x180055e30  add     rsp, 48h
0x180055e34  pop     r15
0x180055e36  pop     r14
0x180055e38  pop     rsi
0x180055e39  pop     rbx
0x180055e3a  retn
```
