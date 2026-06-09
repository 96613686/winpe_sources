# OsEventsStart(void)

- ea: `0x18005e4e4`
- end: `0x18005e6c6`
- name: `?OsEventsStart@@YAJXZ`
- size: `482`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800813a4`

## callees

- `0x180003de0`
- `0x180006824`
- `0x180014bd0`
- `0x180017b60`
- `0x180019d28`
- `0x18001c320`
- `0x18002fa38`
- `0x18005e4e4`
- `0x18005eda4`
- `0x180087784`
- `0x18008cca0`
- `0x18008cde4`
- `0x180092008`
- `0x180092a68`
- `0x180093d78`
- `0x1800c2410`
- `0x1800c2528`
- `0x1800c4c70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005e63e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005e63e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e656`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18005e64b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18005e64b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 OsEventsStart(void)
{
  __int64 v0; // r8
  __int64 v1; // rdx
  __int64 v2; // r9
  __int64 *LegacyPublisher; // rbx
  unsigned int v4; // ebx
  DWORD LastError; // ebx
  __int64 result; // rax
  EvtException *v7; // rbx
  EvtException *v8; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v9[2]; // [rsp+40h] [rbp-58h] BYREF
  _QWORD v10[2]; // [rsp+50h] [rbp-48h] BYREF
  _QWORD v11[2]; // [rsp+60h] [rbp-38h] BYREF
  void *v12[2]; // [rsp+70h] [rbp-28h] BYREF
  char v13; // [rsp+80h] [rbp-18h] BYREF
  wmi::RefBase *Data; // [rsp+A0h] [rbp+8h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v12);
  if ( (g_compatFlags & 2) != 0 )
    GetLocalComputerNetBIOSName(v12);
  else
    GetLocalComputerDnsName((LPWSTR *)v12);
  try
  {
    v0 = *((_QWORD *)ElfModule + 4);
    v1 = *(_QWORD *)(v0 + 88);
    v2 = *(_QWORD *)ElfModule;
    v9[0] = v12[0];
    v9[1] = ((char *)v12[1] - (char *)v12[0]) >> 1;
    v10[0] = v1;
    v10[1] = (*(_QWORD *)(v0 + 96) - v1) >> 1;
    v11[0] = v2;
    v11[1] = (*((_QWORD *)ElfModule + 1) - v2) >> 1;
    LegacyPublisher = (__int64 *)PublisherManager::CreateLegacyPublisher(
                                   (int)g_service + 232,
                                   (unsigned int)&Data,
                                   (unsigned int)v11,
                                   (unsigned int)v10,
                                   (__int64)v9);
    wmi::AutoRef<PublisherMetadata>::Release(&g_EventLogPublisher);
    g_EventLogPublisher = *LegacyPublisher;
    *LegacyPublisher = 0;
    if ( Data )
      wmi::RefBase::Release(Data);
    if ( v12[0] != &v13 )
      operator delete(v12[0]);
    v4 = 0;
    OsEventsPublish6011();
    if ( (unsigned __int8)OsEventsFirstRunSinceBoot() )
    {
      OsEventsPublish6008();
      OsEventsPublish6009();
      OsEventsPublish6005();
      OsEventsPublish6013();
      if ( hKey )
      {
        LODWORD(Data) = 195934928;
        RegSetValueExW(hKey, L"LastAliveStamp", 0, 3u, (const BYTE *)&Data, 4u);
      }
    }
    if ( ResumeThread(hThread) == -1 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids, LastError);
      }
      v4 = DosErrorToNtStatus(LastError);
      OsEventsCleanup(0);
    }
    result = v4;
  }
  catch ( EvtException *v8 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      v7 = v8;
    }
    else
    {
      v7 = v8;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        &WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids,
        *((unsigned int *)v8 + 6));
    }
    LODWORD(Data) = DosErrorToNtStatus(*((_DWORD *)v7 + 6));
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v12);
    return (unsigned int)Data;
  }
  return result;
}

```

## disassembly

```asm
0x18005e4e4  push    rbx
0x18005e4e6  sub     rsp, 90h
0x18005e4ed  lea     rcx, [rsp+98h+var_28]; void *
0x18005e4f2  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18005e4f7  nop
0x18005e4f8  lea     rcx, [rsp+98h+var_28]
0x18005e4fd  test    byte ptr cs:?g_compatFlags@@3KA, 2; ulong g_compatFlags
0x18005e504  jz      short loc_18005E50D
0x18005e506  call    ?GetLocalComputerNetBIOSName@@YA_NAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; GetLocalComputerNetBIOSName(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18005e50b  jmp     short loc_18005E513
0x18005e50d  call    ?GetLocalComputerDnsName@@YA_NAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; GetLocalComputerDnsName(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18005e512  nop
0x18005e513  mov     r10, cs:?ElfModule@@3PEAULOGMODULE@@EA; LOGMODULE * ElfModule
0x18005e51a  mov     r8, [r10+20h]
0x18005e51e  mov     rdx, [r8+58h]
0x18005e522  mov     r9, [r10]
0x18005e525  mov     rax, [rsp+98h+var_28]
0x18005e52a  mov     [rsp+98h+var_58], rax
0x18005e52f  mov     rcx, [rsp+98h+var_20]
0x18005e534  sub     rcx, rax
0x18005e537  sar     rcx, 1
0x18005e53a  mov     [rsp+98h+var_50], rcx
0x18005e53f  mov     [rsp+98h+var_48], rdx
0x18005e544  mov     rax, [r8+60h]
0x18005e548  sub     rax, rdx
0x18005e54b  sar     rax, 1
0x18005e54e  mov     [rsp+98h+var_40], rax
0x18005e553  mov     [rsp+98h+var_38], r9
0x18005e558  mov     rax, [r10+8]
0x18005e55c  sub     rax, r9
0x18005e55f  sar     rax, 1
0x18005e562  mov     [rsp+98h+var_30], rax
0x18005e567  mov     rcx, cs:?g_service@@3PEAVEventService@@EA; EventService * g_service
0x18005e56e  add     rcx, 0E8h
0x18005e575  lea     rax, [rsp+98h+var_58]
0x18005e57a  mov     [rsp+98h+lpData], rax
0x18005e57f  lea     r9, [rsp+98h+var_48]
0x18005e584  lea     r8, [rsp+98h+var_38]
0x18005e589  lea     rdx, [rsp+98h+Data]
0x18005e591  call    ?CreateLegacyPublisher@PublisherManager@@QEAA?AV?$AutoRef@VPublisher@@@wmi@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@00@Z; PublisherManager::CreateLegacyPublisher(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18005e596  mov     rbx, rax
0x18005e599  lea     rcx, ?g_EventLogPublisher@@3V?$AutoRef@VPublisher@@@wmi@@A; wmi::AutoRef<Publisher> g_EventLogPublisher
0x18005e5a0  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x18005e5a5  mov     rcx, [rbx]
0x18005e5a8  mov     cs:?g_EventLogPublisher@@3V?$AutoRef@VPublisher@@@wmi@@A, rcx; wmi::AutoRef<Publisher> g_EventLogPublisher
0x18005e5af  mov     qword ptr [rbx], 0
0x18005e5b6  mov     rcx, [rsp+98h+Data]; this
0x18005e5be  test    rcx, rcx
0x18005e5c1  jz      short loc_18005E5C9
0x18005e5c3  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18005e5c8  nop
0x18005e5c9  lea     rax, [rsp+98h+var_18]
0x18005e5d1  mov     rcx, [rsp+98h+var_28]; void *
0x18005e5d6  cmp     rcx, rax
0x18005e5d9  jz      short loc_18005E5E0
0x18005e5db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005e5e0  xor     ebx, ebx
0x18005e5e2  call    OsEventsPublish6011
0x18005e5e7  call    OsEventsFirstRunSinceBoot
0x18005e5ec  test    al, al
0x18005e5ee  jz      short loc_18005E644
0x18005e5f0  call    OsEventsPublish6008
0x18005e5f5  call    OsEventsPublish6009
0x18005e5fa  call    OsEventsPublish6005
0x18005e5ff  call    OsEventsPublish6013
0x18005e604  mov     rcx, cs:hKey; hKey
0x18005e60b  test    rcx, rcx
0x18005e60e  jz      short loc_18005E644
0x18005e610  mov     dword ptr [rsp+98h+Data], 0BADBAD0h
0x18005e61b  mov     [rsp+98h+cbData], 4; cbData
0x18005e623  lea     rax, [rsp+98h+Data]
0x18005e62b  mov     [rsp+98h+lpData], rax; lpData
0x18005e630  lea     r9d, [rbx+3]; dwType
0x18005e634  xor     r8d, r8d; Reserved
0x18005e637  lea     rdx, aLastalivestamp; "LastAliveStamp"
0x18005e63e  call    cs:__imp_RegSetValueExW
0x18005e644  mov     rcx, cs:hThread; hThread
0x18005e64b  call    cs:__imp_ResumeThread
0x18005e651  cmp     eax, 0FFFFFFFFh
0x18005e654  jnz     short loc_18005E6A8
0x18005e656  call    cs:__imp_GetLastError
0x18005e65c  mov     ebx, eax
0x18005e65e  lea     rax, WPP_GLOBAL_Control
0x18005e665  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e66c  cmp     rcx, rax
0x18005e66f  jz      short loc_18005E698
0x18005e671  test    dword ptr [rcx+1Ch], 4000h
0x18005e678  jz      short loc_18005E698
0x18005e67a  cmp     byte ptr [rcx+19h], 2
0x18005e67e  jb      short loc_18005E698
0x18005e680  mov     edx, 3Ch ; '<'
0x18005e685  mov     r9d, ebx
0x18005e688  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x18005e68f  mov     rcx, [rcx+10h]
0x18005e693  call    WPP_SF_d
0x18005e698  mov     ecx, ebx; unsigned int
0x18005e69a  call    ?DosErrorToNtStatus@@YAJK@Z; DosErrorToNtStatus(ulong)
0x18005e69f  mov     ebx, eax
0x18005e6a1  xor     ecx, ecx; bool
0x18005e6a3  call    ?OsEventsCleanup@@YAJ_N@Z; OsEventsCleanup(bool)
0x18005e6a8  mov     eax, ebx
0x18005e6aa  jmp     short loc_18005E6BD
0x18005e6ac  lea     rcx, [rsp+98h+var_28]; void *
0x18005e6b1  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18005e6b6  mov     eax, dword ptr [rsp+98h+Data]
0x18005e6bd  add     rsp, 90h
0x18005e6c4  pop     rbx
0x18005e6c5  retn
```
