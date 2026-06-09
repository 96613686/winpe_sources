# SignNtsNtpPacket(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,NtpPacket const &,char *,ulong &)

- ea: `0x1800556a4`
- end: `0x1800559b4`
- name: `?SignNtsNtpPacket@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUNtpPacket@@PEADAEAK@Z`
- size: `784`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003163c`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x180034488`
- `0x18003a6a0`
- `0x18003ad30`
- `0x180052950`
- `0x1800556a4`
- `0x180056b14`
- `0x1800577b4`
- `0x180058538`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800557bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005587b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180055940`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800557bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005587b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180055940`

## string_xrefs

- `0x180055807`: `SignNtsNtpPacket: Unable to commenceNtsKE for %s due to error: 0x%08X. Ignoring error.\n`
- `0x1800558c3`: `SignNtsNtpPacket: Unable to commenceNtsKE for %s due to error: 0x%08X. Ignoring error.\n`
- `0x180055988`: `SignNtsNtpPacket: Unable to commenceNtsKE for %s due to error: 0x%08X. Ignoring error.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SignNtsNtpPacket(_QWORD *a1, const struct NtpPacket *a2, char *a3, unsigned int *a4)
{
  _QWORD *v8; // rdx
  const char *v9; // r9
  __int64 result; // rax
  struct NtsForNtpInfoInternal *v11; // rdi
  _QWORD *v12; // rdx
  int v13; // ebx
  _QWORD *v14; // rdx
  _QWORD *v15; // rdx
  int v16; // ebx
  _QWORD *v17; // rdx
  int v18; // esi
  char v19; // dl
  int v20; // ebx
  _QWORD *v21; // rdx
  struct _RTL_CRITICAL_SECTION *v22; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v23[2]; // [rsp+30h] [rbp-58h] BYREF
  unsigned __int64 v24; // [rsp+40h] [rbp-48h]
  __int64 v25; // [rsp+48h] [rbp-40h] BYREF
  _QWORD *v26; // [rsp+50h] [rbp-38h]
  char v27; // [rsp+58h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  try
  {
    wil::critical_section::lock(&g_NtsState, &v22);
    std::_Tree<std::_Tmap_traits<std::wstring,NtsForNtpInfoInternal,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,NtsForNtpInfoInternal>>,0>>::find(
      &qword_1800A4928,
      v23,
      a1);
    v24 = qword_1800A4928;
    if ( v23[0] == qword_1800A4928 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(200) )
      {
        if ( a1[3] <= 7u )
          v8 = a1;
        else
          v8 = (_QWORD *)*a1;
        FileLogAdd(L"SignNtsNtpPacket: server %s not found\n", v8);
      }
      EmitSignNtsNtpPacketTelemetry(2147943568LL, a1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>();
      result = 2147943568LL;
    }
    else
    {
      v23[0] += 64LL;
      v11 = (struct NtsForNtpInfoInternal *)v23[0];
      v23[1] = a1;
      wil::scope_exit__lambda_0303b96c273126584260df3d3423e319___(&v25, v23);
      if ( *((_QWORD *)v11 + 27) == *((_QWORD *)v11 + 28) )
      {
        if ( (unsigned __int8)FileLogAllowEntry(200) )
        {
          if ( a1[3] <= 7u )
            v12 = a1;
          else
            v12 = (_QWORD *)*a1;
          FileLogAdd(L"SignNtsNtpPacket: server %s has no cookies available\n", v12);
        }
        EmitSignNtsNtpPacketTelemetry(2147483658LL, a1);
        if ( v27 )
        {
          v27 = 0;
          *(_QWORD *)(v25 + 176) = GetTickCount64();
          v13 = CommenceNtsKE(v26);
          if ( v13 < 0 )
          {
            if ( (unsigned __int8)FileLogAllowEntry(200) )
            {
              v14 = v26;
              if ( v26[3] > 7u )
                v14 = (_QWORD *)*v26;
              FileLogAdd(
                L"SignNtsNtpPacket: Unable to commenceNtsKE for %s due to error: 0x%08X. Ignoring error.\n",
                v14,
                (unsigned int)v13);
            }
          }
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>();
        result = 2147483658LL;
      }
      else if ( *((_QWORD *)v11 + 26) )
      {
        v18 = AddNtsExtensions(a2, v11, a3, a4);
        v19 = v27;
        if ( v18 >= 0 )
          v19 = 0;
        v27 = v19;
        v24 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)v11 + 28) - *((_QWORD *)v11 + 27)) >> 3);
        EmitSignNtsNtpPacketTelemetry((unsigned int)v18, a1);
        if ( v27 )
        {
          v27 = 0;
          *(_QWORD *)(v25 + 176) = GetTickCount64();
          v20 = CommenceNtsKE(v26);
          if ( v20 < 0 )
          {
            if ( (unsigned __int8)FileLogAllowEntry(200) )
            {
              v21 = v26;
              if ( v26[3] > 7u )
                v21 = (_QWORD *)*v26;
              FileLogAdd(
                L"SignNtsNtpPacket: Unable to commenceNtsKE for %s due to error: 0x%08X. Ignoring error.\n",
                v21,
                (unsigned int)v20);
            }
          }
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>();
        result = (unsigned int)v18;
      }
      else
      {
        if ( (unsigned __int8)FileLogAllowEntry(200) )
        {
          if ( a1[3] <= 7u )
            v15 = a1;
          else
            v15 = (_QWORD *)*a1;
          FileLogAdd(L"SignNtsNtpPacket: server %s has no crypto wrapper\n", v15);
        }
        EmitSignNtsNtpPacketTelemetry(2147942487LL, a1);
        if ( v27 )
        {
          v27 = 0;
          *(_QWORD *)(v25 + 176) = GetTickCount64();
          v16 = CommenceNtsKE(v26);
          if ( v16 < 0 )
          {
            if ( (unsigned __int8)FileLogAllowEntry(200) )
            {
              v17 = v26;
              if ( v26[3] > 7u )
                v17 = (_QWORD *)*v26;
              FileLogAdd(
                L"SignNtsNtpPacket: Unable to commenceNtsKE for %s due to error: 0x%08X. Ignoring error.\n",
                v17,
                (unsigned int)v16);
            }
          }
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>();
        result = 2147942487LL;
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x324,
                           (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\nts.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800556a4  push    rbx
0x1800556a6  push    rsi
0x1800556a7  push    rdi
0x1800556a8  push    r14
0x1800556aa  push    r15
0x1800556ac  sub     rsp, 60h
0x1800556b0  mov     rsi, r9
0x1800556b3  mov     r14, r8
0x1800556b6  mov     r15, rdx
0x1800556b9  mov     rbx, rcx
0x1800556bc  lea     rdx, [rsp+88h+var_68]
0x1800556c1  lea     rcx, ?g_NtsState@@3UNtsState@@A; NtsState g_NtsState
0x1800556c8  call    ?lock@critical_section@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::critical_section::lock(void)
0x1800556cd  nop
0x1800556ce  mov     r8, rbx
0x1800556d1  lea     rdx, [rsp+88h+var_58]
0x1800556d6  lea     rcx, qword_1800A4928
0x1800556dd  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,NtsForNtpInfoInternal,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,NtsForNtpInfoInternal>>,0>>::find(std::wstring const &)
0x1800556e2  mov     rcx, cs:qword_1800A4928
0x1800556e9  mov     [rsp+88h+var_48], rcx
0x1800556ee  mov     rax, [rsp+88h+var_58]
0x1800556f3  cmp     rax, rcx
0x1800556f6  jnz     short loc_180055745
0x1800556f8  mov     ecx, 0C8h
0x1800556fd  call    FileLogAllowEntry
0x180055702  test    al, al
0x180055704  jz      short loc_180055721
0x180055706  cmp     qword ptr [rbx+18h], 7
0x18005570b  jbe     short loc_180055712
0x18005570d  mov     rdx, [rbx]
0x180055710  jmp     short loc_180055715
0x180055712  mov     rdx, rbx
0x180055715  lea     rcx, aSignntsntppack; "SignNtsNtpPacket: server %s not found\n"
0x18005571c  call    FileLogAdd
0x180055721  xor     r8d, r8d
0x180055724  mov     rdx, rbx
0x180055727  mov     ebx, 80070490h
0x18005572c  mov     ecx, ebx
0x18005572e  call    ?EmitSignNtsNtpPacketTelemetry@@YAXJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; EmitSignNtsNtpPacketTelemetry(long,std::wstring &,ulong)
0x180055733  nop
0x180055734  lea     rcx, [rsp+88h+var_68]
0x180055739  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18005573e  mov     eax, ebx
0x180055740  jmp     loc_1800559A7
0x180055745  lea     rdi, [rax+40h]
0x180055749  mov     [rsp+88h+var_58], rdi
0x18005574e  mov     [rsp+88h+var_50], rbx
0x180055753  lea     rdx, [rsp+88h+var_58]
0x180055758  lea     rcx, [rsp+88h+var_40]
0x18005575d  call    wil__scope_exit__lambda_0303b96c273126584260df3d3423e319___
0x180055762  nop
0x180055763  mov     rax, [rdi+0E0h]
0x18005576a  cmp     [rdi+0D8h], rax
0x180055771  jnz     loc_180055825
0x180055777  mov     ecx, 0C8h
0x18005577c  call    FileLogAllowEntry
0x180055781  test    al, al
0x180055783  jz      short loc_1800557A0
0x180055785  cmp     qword ptr [rbx+18h], 7
0x18005578a  jbe     short loc_180055791
0x18005578c  mov     rdx, [rbx]
0x18005578f  jmp     short loc_180055794
0x180055791  mov     rdx, rbx
0x180055794  lea     rcx, aSignntsntppack_0; "SignNtsNtpPacket: server %s has no cook"...
0x18005579b  call    FileLogAdd
0x1800557a0  xor     r8d, r8d
0x1800557a3  mov     rdx, rbx
0x1800557a6  mov     edi, 8000000Ah
0x1800557ab  mov     ecx, edi
0x1800557ad  call    ?EmitSignNtsNtpPacketTelemetry@@YAXJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; EmitSignNtsNtpPacketTelemetry(long,std::wstring &,ulong)
0x1800557b2  nop
0x1800557b3  cmp     [rsp+88h+var_30], 0
0x1800557b8  jz      short loc_180055814
0x1800557ba  mov     [rsp+88h+var_30], 0
0x1800557bf  call    cs:__imp_GetTickCount64
0x1800557c6  nop     dword ptr [rax+rax+00h]
0x1800557cb  mov     rcx, [rsp+88h+var_40]
0x1800557d0  mov     [rcx+0B0h], rax
0x1800557d7  mov     rcx, [rsp+88h+var_38]
0x1800557dc  call    ?CommenceNtsKE@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CommenceNtsKE(std::wstring const &)
0x1800557e1  mov     ebx, eax
0x1800557e3  test    eax, eax
0x1800557e5  jns     short loc_180055814
0x1800557e7  mov     ecx, 0C8h
0x1800557ec  call    FileLogAllowEntry
0x1800557f1  test    al, al
0x1800557f3  jz      short loc_180055814
0x1800557f5  mov     rdx, [rsp+88h+var_38]
0x1800557fa  cmp     qword ptr [rdx+18h], 7
0x1800557ff  jbe     short loc_180055804
0x180055801  mov     rdx, [rdx]
0x180055804  mov     r8d, ebx
0x180055807  lea     rcx, aSignntsntppack_2; "SignNtsNtpPacket: Unable to commenceNts"...
0x18005580e  call    FileLogAdd
0x180055813  nop
0x180055814  lea     rcx, [rsp+88h+var_68]
0x180055819  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18005581e  mov     eax, edi
0x180055820  jmp     loc_1800559A7
0x180055825  cmp     qword ptr [rdi+0D0h], 0
0x18005582d  jnz     loc_1800558E1
0x180055833  mov     ecx, 0C8h
0x180055838  call    FileLogAllowEntry
0x18005583d  test    al, al
0x18005583f  jz      short loc_18005585C
0x180055841  cmp     qword ptr [rbx+18h], 7
0x180055846  jbe     short loc_18005584D
0x180055848  mov     rdx, [rbx]
0x18005584b  jmp     short loc_180055850
0x18005584d  mov     rdx, rbx
0x180055850  lea     rcx, aSignntsntppack_1; "SignNtsNtpPacket: server %s has no cryp"...
0x180055857  call    FileLogAdd
0x18005585c  xor     r8d, r8d
0x18005585f  mov     rdx, rbx
0x180055862  mov     edi, 80070057h
0x180055867  mov     ecx, edi
0x180055869  call    ?EmitSignNtsNtpPacketTelemetry@@YAXJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; EmitSignNtsNtpPacketTelemetry(long,std::wstring &,ulong)
0x18005586e  nop
0x18005586f  cmp     [rsp+88h+var_30], 0
0x180055874  jz      short loc_1800558D0
0x180055876  mov     [rsp+88h+var_30], 0
0x18005587b  call    cs:__imp_GetTickCount64
0x180055882  nop     dword ptr [rax+rax+00h]
0x180055887  mov     rcx, [rsp+88h+var_40]
0x18005588c  mov     [rcx+0B0h], rax
0x180055893  mov     rcx, [rsp+88h+var_38]
0x180055898  call    ?CommenceNtsKE@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CommenceNtsKE(std::wstring const &)
0x18005589d  mov     ebx, eax
0x18005589f  test    eax, eax
0x1800558a1  jns     short loc_1800558D0
0x1800558a3  mov     ecx, 0C8h
0x1800558a8  call    FileLogAllowEntry
0x1800558ad  test    al, al
0x1800558af  jz      short loc_1800558D0
0x1800558b1  mov     rdx, [rsp+88h+var_38]
0x1800558b6  cmp     qword ptr [rdx+18h], 7
0x1800558bb  jbe     short loc_1800558C0
0x1800558bd  mov     rdx, [rdx]
0x1800558c0  mov     r8d, ebx
0x1800558c3  lea     rcx, aSignntsntppack_2; "SignNtsNtpPacket: Unable to commenceNts"...
0x1800558ca  call    FileLogAdd
0x1800558cf  nop
0x1800558d0  lea     rcx, [rsp+88h+var_68]
0x1800558d5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1800558da  mov     eax, edi
0x1800558dc  jmp     loc_1800559A7
0x1800558e1  mov     r9, rsi; unsigned int *
0x1800558e4  mov     r8, r14; char *
0x1800558e7  mov     rdx, rdi; struct NtsForNtpInfoInternal *
0x1800558ea  mov     rcx, r15; struct NtpPacket *
0x1800558ed  call    ?AddNtsExtensions@@YAJAEBUNtpPacket@@AEAUNtsForNtpInfoInternal@@PEADPEAK@Z; AddNtsExtensions(NtpPacket const &,NtsForNtpInfoInternal &,char *,ulong *)
0x1800558f2  mov     esi, eax
0x1800558f4  movzx   edx, [rsp+88h+var_30]
0x1800558f9  xor     ecx, ecx
0x1800558fb  test    eax, eax
0x1800558fd  cmovns  edx, ecx
0x180055900  mov     [rsp+88h+var_30], dl
0x180055904  mov     r8, [rdi+0E0h]
0x18005590b  sub     r8, [rdi+0D8h]
0x180055912  sar     r8, 3
0x180055916  mov     rax, 0AAAAAAAAAAAAAAABh
0x180055920  imul    r8, rax
0x180055924  mov     [rsp+88h+var_48], r8
0x180055929  mov     rdx, rbx
0x18005592c  mov     ecx, esi
0x18005592e  call    ?EmitSignNtsNtpPacketTelemetry@@YAXJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; EmitSignNtsNtpPacketTelemetry(long,std::wstring &,ulong)
0x180055933  nop
0x180055934  cmp     [rsp+88h+var_30], 0
0x180055939  jz      short loc_180055995
0x18005593b  mov     [rsp+88h+var_30], 0
0x180055940  call    cs:__imp_GetTickCount64
0x180055947  nop     dword ptr [rax+rax+00h]
0x18005594c  mov     rcx, [rsp+88h+var_40]
0x180055951  mov     [rcx+0B0h], rax
0x180055958  mov     rcx, [rsp+88h+var_38]
0x18005595d  call    ?CommenceNtsKE@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CommenceNtsKE(std::wstring const &)
0x180055962  mov     ebx, eax
0x180055964  test    eax, eax
0x180055966  jns     short loc_180055995
0x180055968  mov     ecx, 0C8h
0x18005596d  call    FileLogAllowEntry
0x180055972  test    al, al
0x180055974  jz      short loc_180055995
0x180055976  mov     rdx, [rsp+88h+var_38]
0x18005597b  cmp     qword ptr [rdx+18h], 7
0x180055980  jbe     short loc_180055985
0x180055982  mov     rdx, [rdx]
0x180055985  mov     r8d, ebx
0x180055988  lea     rcx, aSignntsntppack_2; "SignNtsNtpPacket: Unable to commenceNts"...
0x18005598f  call    FileLogAdd
0x180055994  nop
0x180055995  lea     rcx, [rsp+88h+var_68]
0x18005599a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18005599f  mov     eax, esi
0x1800559a1  jmp     short loc_1800559A7
0x1800559a3  mov     eax, dword ptr [rsp+88h+var_68]
0x1800559a7  add     rsp, 60h
0x1800559ab  pop     r15
0x1800559ad  pop     r14
0x1800559af  pop     rdi
0x1800559b0  pop     rsi
0x1800559b1  pop     rbx
0x1800559b2  retn
```
