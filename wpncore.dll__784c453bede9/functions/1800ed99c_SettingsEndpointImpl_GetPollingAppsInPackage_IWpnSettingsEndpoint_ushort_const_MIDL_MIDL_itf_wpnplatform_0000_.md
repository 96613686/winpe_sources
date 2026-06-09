# SettingsEndpointImpl::GetPollingAppsInPackage(IWpnSettingsEndpoint *,ushort const *,__MIDL___MIDL_itf_wpnplatform_0000_0036_0001 * *)

- ea: `0x1800ed99c`
- end: `0x1800ede11`
- name: `?GetPollingAppsInPackage@SettingsEndpointImpl@@SAJPEAUIWpnSettingsEndpoint@@PEBGPEAPEAU__MIDL___MIDL_itf_wpnplatform_0000_0036_0001@@@Z`
- size: `1141`
- prototype: `static int(struct IWpnSettingsEndpoint *, const unsigned __int16 *, struct __MIDL___MIDL_itf_wpnplatform_0000_0036_0001 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800ecc90`

## callees

- `0x180024640`
- `0x18002ee38`
- `0x18002f224`
- `0x1800a6570`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x1800b9a20`
- `0x1800b9ecc`
- `0x1800bc541`
- `0x1800ed01c`
- `0x1800ed104`
- `0x1800ed99c`
- `0x1800ede18`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800edba7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800edba7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800edb14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800edb99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800eddba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800edb14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800edb99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800eddba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800edb22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800eddc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800edb22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800eddc8`
- `ntdll!RtlNtStatusToDosError` at `0x1800eda02`
- `ntdll!RtlNtStatusToDosError` at `0x1800edb54`
- `ntdll!RtlNtStatusToDosError` at `0x1800eda02`
- `ntdll!RtlNtStatusToDosError` at `0x1800edb54`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800edb88`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800edb88`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtQueryBrokeredEvent` at `0x1800edb44`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtQueryBrokeredEvent` at `0x1800edb44`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x1800edb01`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x1800edd90`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x1800edda7`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x1800edb01`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x1800edd90`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x1800edda7`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtEnumerateBrokeredEvents` at `0x1800ed9f6`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtEnumerateBrokeredEvents` at `0x1800ed9f6`

## pseudocode

```c
__int64 __fastcall SettingsEndpointImpl::GetPollingAppsInPackage(
        struct IWpnSettingsEndpoint *a1,
        const unsigned __int16 *a2,
        struct __MIDL___MIDL_itf_wpnplatform_0000_0036_0001 **a3)
{
  unsigned int v3; // ebx
  unsigned __int16 *v7; // r14
  PollingAppDataList *v8; // rdi
  NTSTATUS v9; // eax
  signed int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  int UserSid; // eax
  PollingAppDataList *v15; // rax
  unsigned int *v16; // rax
  unsigned int i; // esi
  HANDLE ProcessHeap; // rax
  NTSTATUS v19; // eax
  signed int v20; // eax
  bool v21; // zf
  unsigned int v22; // ebx
  HANDLE v23; // rax
  int v24; // eax
  int PollingDataList; // eax
  __int64 v26; // rcx
  HANDLE v27; // rax
  unsigned int *v29; // [rsp+20h] [rbp-59h] BYREF
  unsigned int v30; // [rsp+28h] [rbp-51h] BYREF
  int v31; // [rsp+2Ch] [rbp-4Dh] BYREF
  _QWORD v32[2]; // [rsp+30h] [rbp-49h] BYREF
  _BYTE pSid1[80]; // [rsp+40h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v3 = 0;
  *a3 = 0;
  v30 = 0;
  v32[0] = 0;
  v29 = 0;
  v31 = 0;
  v7 = 0;
  v8 = 0;
  v9 = BiPtEnumerateBrokeredEvents(qword_180132120, &v30, v32);
  if ( v9 < 0 )
  {
    v10 = RtlNtStatusToDosError(v9);
    v3 = v10;
    if ( v10 > 0 )
      v3 = (unsigned __int16)v10 | 0x80070000;
  }
  if ( (v3 & 0x80000000) == 0 )
  {
    if ( v30 && (UserSid = WpnGetUserSid(pSid1), v3 = UserSid, UserSid < 0) )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x370,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
        (const char *)(unsigned int)UserSid,
        (int)v29);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v12 = 51;
        goto LABEL_8;
      }
    }
    else
    {
      v15 = (PollingAppDataList *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
      v32[1] = v15;
      v8 = v15;
      if ( v15 )
      {
        *((_DWORD *)v15 + 4) = 0;
        *((_QWORD *)v15 + 1) = v15;
        *(_QWORD *)v15 = v15;
        v16 = v29;
        for ( i = 0; i < v30; ++i )
        {
          if ( v16 )
          {
            BiPtFreeMemory(v16);
            v29 = 0;
          }
          if ( v7 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v7);
            v7 = 0;
          }
          v31 = 0;
          v19 = BiPtQueryBrokeredEvent(v32[0] + 16LL * i, &v31, &v29);
          if ( v19 < 0 )
          {
            v20 = RtlNtStatusToDosError(v19);
            v3 = v20;
            if ( v20 > 0 )
              v3 = (unsigned __int16)v20 | 0x80070000;
          }
          else
          {
            v3 = 0;
          }
          if ( (v3 & 0x80000000) != 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x383,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
              (const char *)v3,
              (int)v29);
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            {
              v12 = 53;
              goto LABEL_8;
            }
            goto LABEL_53;
          }
          v16 = v29;
          if ( v29[12] == 4772 )
          {
            v21 = !EqualSid(pSid1, (char *)v29 + v29[10]);
            v16 = v29;
            if ( !v21 )
            {
              v22 = v29[12];
              v23 = GetProcessHeap();
              v7 = (unsigned __int16 *)HeapAlloc(v23, 0, v22);
              if ( !v7 )
              {
                v3 = -2147024882;
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x391,
                  (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
                  (const char *)0x8007000ELL,
                  (int)v29);
                v11 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                {
                  v12 = 54;
                  goto LABEL_51;
                }
                goto LABEL_53;
              }
              memcpy_0(v7, (char *)v29 + v29[11], v29[12]);
              if ( SettingsEndpointImpl::IsAppInPackage(a2, v7 + 40) )
              {
                v24 = PollingAppDataList::AddPollingDataToList(v8, (struct _PERSISTED_PERIODIC_UPDATE *)v7);
                v3 = v24;
                if ( v24 < 0 )
                {
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x39B,
                    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
                    (const char *)(unsigned int)v24,
                    (int)v29);
                  v11 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                  {
                    v12 = 55;
                    goto LABEL_8;
                  }
                  goto LABEL_53;
                }
              }
              v16 = v29;
            }
          }
        }
        PollingDataList = PollingAppDataList::GetPollingDataList(v8, a1, a3);
        v3 = PollingDataList;
        if ( PollingDataList >= 0 )
        {
          if ( (byte_18015DE46 & 8) != 0 )
            McTemplateU0z_EventWriteTransfer(v26, WPNEND_POLLING_PACKAGE_APP_LIST_REQUESTED, a2);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x3A3,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
            (const char *)(unsigned int)PollingDataList,
            (int)v29);
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v12 = 56;
            goto LABEL_8;
          }
        }
      }
      else
      {
        v8 = 0;
        v3 = -2147024882;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x374,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
          (const char *)0x8007000ELL,
          (int)v29);
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v12 = 52;
LABEL_51:
          v13 = 2147942414LL;
          goto LABEL_52;
        }
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x36C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
      (const char *)v3,
      (int)v29);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v12 = 50;
LABEL_8:
      v13 = v3;
LABEL_52:
      WPP_SF_d(v11[2], v12, WPP_00912b6861fc335f2cbb59491e908f50_Traceguids, v13);
    }
  }
LABEL_53:
  if ( v32[0] )
  {
    BiPtFreeMemory(v32[0]);
    v32[0] = 0;
  }
  if ( v29 )
  {
    BiPtFreeMemory(v29);
    v29 = 0;
  }
  if ( v7 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v7);
  }
  if ( v8 )
  {
    PollingAppDataList::~PollingAppDataList(v8);
    operator delete(v8);
  }
  return v3;
}

```

## disassembly

```asm
0x1800ed99c  mov     [rsp-8+arg_18], rbx
0x1800ed9a1  push    rbp
0x1800ed9a2  push    rsi
0x1800ed9a3  push    rdi
0x1800ed9a4  push    r12
0x1800ed9a6  push    r13
0x1800ed9a8  push    r14
0x1800ed9aa  push    r15
0x1800ed9ac  lea     rbp, [rsp-27h]
0x1800ed9b1  sub     rsp, 0A0h
0x1800ed9b8  mov     rax, cs:__security_cookie
0x1800ed9bf  xor     rax, rsp
0x1800ed9c2  mov     [rbp+57h+var_40], rax
0x1800ed9c6  xor     ebx, ebx
0x1800ed9c8  mov     r12, r8
0x1800ed9cb  mov     [r8], rbx
0x1800ed9ce  mov     r15, rdx
0x1800ed9d1  mov     r13, rcx
0x1800ed9d4  mov     [rbp+57h+var_A8], ebx
0x1800ed9d7  lea     r8, [rbp+57h+var_A0]
0x1800ed9db  mov     [rbp+57h+var_A0], rbx
0x1800ed9df  lea     rdx, [rbp+57h+var_A8]
0x1800ed9e3  mov     [rbp+57h+var_B0], rbx
0x1800ed9e7  lea     rcx, qword_180132120
0x1800ed9ee  mov     [rbp+57h+var_A4], ebx
0x1800ed9f1  mov     r14d, ebx
0x1800ed9f4  mov     edi, ebx
0x1800ed9f6  call    cs:__imp_BiPtEnumerateBrokeredEvents
0x1800ed9fc  test    eax, eax
0x1800ed9fe  jns     short loc_1800EDA17
0x1800eda00  mov     ecx, eax; Status
0x1800eda02  call    cs:__imp_RtlNtStatusToDosError
0x1800eda08  mov     ebx, eax
0x1800eda0a  test    eax, eax
0x1800eda0c  jle     short loc_1800EDA17
0x1800eda0e  movzx   ebx, ax
0x1800eda11  or      ebx, 80070000h
0x1800eda17  test    ebx, ebx
0x1800eda19  jns     short loc_1800EDA61
0x1800eda1b  mov     rcx, [rbp+5Fh]; this
0x1800eda1f  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800eda26  mov     r9d, ebx; char *
0x1800eda29  mov     edx, 36Ch; void *
0x1800eda2e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800eda33  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eda3a  lea     rax, WPP_GLOBAL_Control
0x1800eda41  cmp     rcx, rax
0x1800eda44  jz      loc_1800EDD87
0x1800eda4a  test    byte ptr [rcx+1Ch], 80h
0x1800eda4e  jz      loc_1800EDD87
0x1800eda54  mov     edx, 32h ; '2'
0x1800eda59  mov     r9d, ebx
0x1800eda5c  jmp     loc_1800EDD77
0x1800eda61  cmp     [rbp+57h+var_A8], edi
0x1800eda64  jbe     short loc_1800EDAB5
0x1800eda66  lea     rcx, [rbp+57h+pSid1]; void *
0x1800eda6a  call    ?WpnGetUserSid@@YAJPEAXK@Z; WpnGetUserSid(void *,ulong)
0x1800eda6f  mov     ebx, eax
0x1800eda71  test    eax, eax
0x1800eda73  jns     short loc_1800EDAB5
0x1800eda75  mov     rcx, [rbp+5Fh]; this
0x1800eda79  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800eda80  mov     r9d, eax; char *
0x1800eda83  mov     edx, 370h; void *
0x1800eda88  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800eda8d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eda94  lea     rax, WPP_GLOBAL_Control
0x1800eda9b  cmp     rcx, rax
0x1800eda9e  jz      loc_1800EDD87
0x1800edaa4  test    byte ptr [rcx+1Ch], 80h
0x1800edaa8  jz      loc_1800EDD87
0x1800edaae  mov     edx, 33h ; '3'
0x1800edab3  jmp     short loc_1800EDA59
0x1800edab5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800edabc  mov     ecx, 18h; unsigned __int64
0x1800edac1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800edac6  mov     [rbp+57h+var_98], rax
0x1800edaca  mov     rdi, rax
0x1800edacd  test    rax, rax
0x1800edad0  jz      loc_1800EDD33
0x1800edad6  mov     [rax+10h], r14d
0x1800edada  mov     [rax+8], rax
0x1800edade  mov     [rax], rax
0x1800edae1  test    rax, rax
0x1800edae4  jz      loc_1800EDD35
0x1800edaea  mov     rax, [rbp+57h+var_B0]
0x1800edaee  xor     esi, esi
0x1800edaf0  cmp     esi, [rbp+57h+var_A8]
0x1800edaf3  jnb     loc_1800EDCCA
0x1800edaf9  test    rax, rax
0x1800edafc  jz      short loc_1800EDB0F
0x1800edafe  mov     rcx, rax
0x1800edb01  call    cs:__imp_BiPtFreeMemory
0x1800edb07  mov     [rbp+57h+var_B0], 0
0x1800edb0f  test    r14, r14
0x1800edb12  jz      short loc_1800EDB2B
0x1800edb14  call    cs:__imp_GetProcessHeap
0x1800edb1a  mov     r8, r14; lpMem
0x1800edb1d  xor     edx, edx; dwFlags
0x1800edb1f  mov     rcx, rax; hHeap
0x1800edb22  call    cs:__imp_HeapFree
0x1800edb28  xor     r14d, r14d
0x1800edb2b  mov     ecx, esi
0x1800edb2d  lea     r8, [rbp+57h+var_B0]
0x1800edb31  shl     rcx, 4
0x1800edb35  lea     rdx, [rbp+57h+var_A4]
0x1800edb39  add     rcx, [rbp+57h+var_A0]
0x1800edb3d  mov     [rbp+57h+var_A4], 0
0x1800edb44  call    cs:__imp_BiPtQueryBrokeredEvent
0x1800edb4a  test    eax, eax
0x1800edb4c  js      short loc_1800EDB52
0x1800edb4e  xor     ebx, ebx
0x1800edb50  jmp     short loc_1800EDB69
0x1800edb52  mov     ecx, eax; Status
0x1800edb54  call    cs:__imp_RtlNtStatusToDosError
0x1800edb5a  mov     ebx, eax
0x1800edb5c  test    eax, eax
0x1800edb5e  jle     short loc_1800EDB69
0x1800edb60  movzx   ebx, ax
0x1800edb63  or      ebx, 80070000h
0x1800edb69  test    ebx, ebx
0x1800edb6b  js      loc_1800EDC87
0x1800edb71  mov     rax, [rbp+57h+var_B0]
0x1800edb75  cmp     dword ptr [rax+30h], 12A4h
0x1800edb7c  jnz     short loc_1800EDBF4
0x1800edb7e  mov     edx, [rax+28h]
0x1800edb81  lea     rcx, [rbp+57h+pSid1]; pSid1
0x1800edb85  add     rdx, rax; pSid2
0x1800edb88  call    cs:__imp_EqualSid
0x1800edb8e  test    eax, eax
0x1800edb90  mov     rax, [rbp+57h+var_B0]
0x1800edb94  jz      short loc_1800EDBF4
0x1800edb96  mov     ebx, [rax+30h]
0x1800edb99  call    cs:__imp_GetProcessHeap
0x1800edb9f  mov     r8d, ebx; dwBytes
0x1800edba2  xor     edx, edx; dwFlags
0x1800edba4  mov     rcx, rax; hHeap
0x1800edba7  call    cs:__imp_HeapAlloc
0x1800edbad  mov     r14, rax
0x1800edbb0  test    rax, rax
0x1800edbb3  jz      loc_1800EDC3E
0x1800edbb9  mov     rax, [rbp+57h+var_B0]
0x1800edbbd  mov     rcx, r14; void *
0x1800edbc0  mov     edx, [rax+2Ch]
0x1800edbc3  mov     r8d, [rax+30h]; Size
0x1800edbc7  add     rdx, rax; Src
0x1800edbca  call    memcpy_0
0x1800edbcf  lea     rdx, [r14+50h]; unsigned __int16 *
0x1800edbd3  mov     rcx, r15; lpString1
0x1800edbd6  call    ?IsAppInPackage@SettingsEndpointImpl@@SA_NPEBG0@Z; SettingsEndpointImpl::IsAppInPackage(ushort const *,ushort const *)
0x1800edbdb  test    al, al
0x1800edbdd  jz      short loc_1800EDBF0
0x1800edbdf  mov     rdx, r14; struct _PERSISTED_PERIODIC_UPDATE *
0x1800edbe2  mov     rcx, rdi; this
0x1800edbe5  call    ?AddPollingDataToList@PollingAppDataList@@QEAAJPEAU_PERSISTED_PERIODIC_UPDATE@@@Z; PollingAppDataList::AddPollingDataToList(_PERSISTED_PERIODIC_UPDATE *)
0x1800edbea  mov     ebx, eax
0x1800edbec  test    eax, eax
0x1800edbee  js      short loc_1800EDBFB
0x1800edbf0  mov     rax, [rbp+57h+var_B0]
0x1800edbf4  inc     esi
0x1800edbf6  jmp     loc_1800EDAF0
0x1800edbfb  mov     rcx, [rbp+5Fh]; this
0x1800edbff  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800edc06  mov     r9d, ebx; char *
0x1800edc09  mov     edx, 39Bh; void *
0x1800edc0e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800edc13  mov     rcx, cs:WPP_GLOBAL_Control
0x1800edc1a  lea     rax, WPP_GLOBAL_Control
0x1800edc21  cmp     rcx, rax
0x1800edc24  jz      loc_1800EDD87
0x1800edc2a  test    byte ptr [rcx+1Ch], 80h
0x1800edc2e  jz      loc_1800EDD87
0x1800edc34  mov     edx, 37h ; '7'
0x1800edc39  jmp     loc_1800EDA59
0x1800edc3e  mov     rcx, [rbp+5Fh]; this
0x1800edc42  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800edc49  mov     r9d, 8007000Eh; char *
0x1800edc4f  mov     edx, 391h; void *
0x1800edc54  mov     ebx, r9d
0x1800edc57  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800edc5c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800edc63  lea     rax, WPP_GLOBAL_Control
0x1800edc6a  cmp     rcx, rax
0x1800edc6d  jz      loc_1800EDD87
0x1800edc73  test    byte ptr [rcx+1Ch], 80h
0x1800edc77  jz      loc_1800EDD87
0x1800edc7d  mov     edx, 36h ; '6'
0x1800edc82  jmp     loc_1800EDD71
0x1800edc87  mov     rcx, [rbp+5Fh]; this
0x1800edc8b  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800edc92  mov     r9d, ebx; char *
0x1800edc95  mov     edx, 383h; void *
0x1800edc9a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800edc9f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800edca6  lea     rax, WPP_GLOBAL_Control
0x1800edcad  cmp     rcx, rax
0x1800edcb0  jz      loc_1800EDD87
0x1800edcb6  test    byte ptr [rcx+1Ch], 80h
0x1800edcba  jz      loc_1800EDD87
0x1800edcc0  mov     edx, 35h ; '5'
0x1800edcc5  jmp     loc_1800EDA59
0x1800edcca  mov     r8, r12; struct __MIDL___MIDL_itf_wpnplatform_0000_0036_0001 **
0x1800edccd  mov     rdx, r13; struct IWpnSettingsEndpoint *
0x1800edcd0  mov     rcx, rdi; this
0x1800edcd3  call    ?GetPollingDataList@PollingAppDataList@@QEAAJPEAUIWpnSettingsEndpoint@@PEAPEAU__MIDL___MIDL_itf_wpnplatform_0000_0036_0001@@@Z; PollingAppDataList::GetPollingDataList(IWpnSettingsEndpoint *,__MIDL___MIDL_itf_wpnplatform_0000_0036_0001 * *)
0x1800edcd8  mov     ebx, eax
0x1800edcda  test    eax, eax
0x1800edcdc  jns     short loc_1800EDD19
0x1800edcde  mov     rcx, [rbp+5Fh]; this
0x1800edce2  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800edce9  mov     r9d, eax; char *
0x1800edcec  mov     edx, 3A3h; void *
0x1800edcf1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800edcf6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800edcfd  lea     rax, WPP_GLOBAL_Control
0x1800edd04  cmp     rcx, rax
0x1800edd07  jz      short loc_1800EDD87
0x1800edd09  test    byte ptr [rcx+1Ch], 80h
0x1800edd0d  jz      short loc_1800EDD87
0x1800edd0f  mov     edx, 38h ; '8'
0x1800edd14  jmp     loc_1800EDA59
0x1800edd19  test    cs:byte_18015DE46, 8
0x1800edd20  jz      short loc_1800EDD87
0x1800edd22  mov     r8, r15
0x1800edd25  lea     rdx, WPNEND_POLLING_PACKAGE_APP_LIST_REQUESTED
0x1800edd2c  call    McTemplateU0z_EventWriteTransfer
0x1800edd31  jmp     short loc_1800EDD87
0x1800edd33  xor     edi, edi
0x1800edd35  mov     rcx, [rbp+5Fh]; this
0x1800edd39  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800edd40  mov     r9d, 8007000Eh; char *
0x1800edd46  mov     edx, 374h; void *
0x1800edd4b  mov     ebx, r9d
0x1800edd4e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800edd53  mov     rcx, cs:WPP_GLOBAL_Control
0x1800edd5a  lea     rax, WPP_GLOBAL_Control
0x1800edd61  cmp     rcx, rax
0x1800edd64  jz      short loc_1800EDD87
0x1800edd66  test    byte ptr [rcx+1Ch], 80h
0x1800edd6a  jz      short loc_1800EDD87
0x1800edd6c  mov     edx, 34h ; '4'
0x1800edd71  mov     r9d, 8007000Eh
0x1800edd77  mov     rcx, [rcx+10h]
0x1800edd7b  lea     r8, WPP_00912b6861fc335f2cbb59491e908f50_Traceguids
0x1800edd82  call    WPP_SF_d
0x1800edd87  mov     rcx, [rbp+57h+var_A0]
0x1800edd8b  test    rcx, rcx
0x1800edd8e  jz      short loc_1800EDD9E
0x1800edd90  call    cs:__imp_BiPtFreeMemory
0x1800edd96  mov     [rbp+57h+var_A0], 0
0x1800edd9e  mov     rcx, [rbp+57h+var_B0]
0x1800edda2  test    rcx, rcx
0x1800edda5  jz      short loc_1800EDDB5
0x1800edda7  call    cs:__imp_BiPtFreeMemory
0x1800eddad  mov     [rbp+57h+var_B0], 0
0x1800eddb5  test    r14, r14
0x1800eddb8  jz      short loc_1800EDDCE
0x1800eddba  call    cs:__imp_GetProcessHeap
0x1800eddc0  mov     r8, r14; lpMem
0x1800eddc3  xor     edx, edx; dwFlags
0x1800eddc5  mov     rcx, rax; hHeap
0x1800eddc8  call    cs:__imp_HeapFree
0x1800eddce  test    rdi, rdi
0x1800eddd1  jz      short loc_1800EDDE8
0x1800eddd3  mov     rcx, rdi; this
0x1800eddd6  call    ??1PollingAppDataList@@QEAA@XZ; PollingAppDataList::~PollingAppDataList(void)
0x1800edddb  mov     edx, 18h
0x1800edde0  mov     rcx, rdi; Block
0x1800edde3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800edde8  mov     eax, ebx
0x1800eddea  mov     rcx, [rbp+57h+var_40]
0x1800eddee  xor     rcx, rsp; StackCookie
0x1800eddf1  call    __security_check_cookie
0x1800eddf6  mov     rbx, [rsp+0D0h+arg_18]
0x1800eddfe  add     rsp, 0A0h
0x1800ede05  pop     r15
0x1800ede07  pop     r14
0x1800ede09  pop     r13
0x1800ede0b  pop     r12
0x1800ede0d  pop     rdi
0x1800ede0e  pop     rsi
0x1800ede0f  pop     rbp
0x1800ede10  retn
```
