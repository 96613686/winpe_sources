# CReportManager::AddDefaultReportDataToReport(void)

- ea: `0x18007c77c`
- end: `0x18007cc6b`
- name: `?AddDefaultReportDataToReport@CReportManager@@AEAAXXZ`
- size: `1263`
- prototype: `void __fastcall(CReportManager *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180030058`

## callees

- `0x18000db80`
- `0x180020680`
- `0x1800318c8`
- `0x180033844`
- `0x1800479ac`
- `0x18004c134`
- `0x18004f4b4`
- `0x180053300`
- `0x180053d3c`
- `0x180070138`
- `0x180070728`
- `0x180073c8c`
- `0x180074490`
- `0x18007babc`
- `0x18007c3fc`
- `0x18007c4b0`
- `0x18007c58c`
- `0x18007c77c`
- `0x18007d260`
- `0x180081028`
- `0x180081774`
- `0x180081964`
- `0x180082834`
- `0x180082bb8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18007c7e3`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18007c8cf`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18007c7e3`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18007c8cf`
- `ntdll!RtlQueryHeapInformation` at `0x18007c981`
- `ntdll!RtlQueryHeapInformation` at `0x18007c981`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x18007c816`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x18007c888`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x18007c816`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x18007c888`

## string_xrefs

- `0x18007cbe5`: `onecore\windows\feedback\core\werdll\lib\reportmanager.cpp`

## pseudocode

```c
void __fastcall CReportManager::AddDefaultReportDataToReport(CReportManager *this)
{
  __int64 v2; // rcx
  HANDLE v3; // rsi
  DWORD ProcessId; // r14d
  __int64 v5; // rcx
  signed int Snapshot; // eax
  wchar_t *v7; // rcx
  __int64 v8; // rdx
  DWORD v9; // eax
  unsigned int v10; // r9d
  int v11; // eax
  unsigned int v12; // r9d
  int v13; // eax
  __int64 v14; // rcx
  __int64 string_tag; // rax
  __int64 v16; // xmm1_8
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // xmm1_8
  __int64 v21; // rax
  bool v22; // zf
  __int16 v23; // ax
  int v24; // eax
  __int64 v25; // rbx
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  __int64 v27; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Process; // [rsp+38h] [rbp-C8h] BYREF
  const char *v29; // [rsp+40h] [rbp-C0h] BYREF
  char v30; // [rsp+48h] [rbp-B8h]
  __int128 *v31; // [rsp+50h] [rbp-B0h]
  unsigned __int64 Buffer; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 HeapInformation; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v34; // [rsp+68h] [rbp-98h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h]
  _QWORD v36[2]; // [rsp+80h] [rbp-80h] BYREF
  _WORD v37[8]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v38[3]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v39; // [rsp+B8h] [rbp-48h]
  int v40; // [rsp+BAh] [rbp-46h]
  __int16 v41; // [rsp+BEh] [rbp-42h]
  _BYTE v42[56]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v43; // [rsp+F8h] [rbp-8h]
  _BYTE v44[160]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v45; // [rsp+1A0h] [rbp+A0h] BYREF
  char v46; // [rsp+1A8h] [rbp+A8h]
  int v47; // [rsp+1A9h] [rbp+A9h] BYREF
  char v48; // [rsp+1ADh] [rbp+ADh]
  char v49; // [rsp+1AEh] [rbp+AEh] BYREF
  char v50; // [rsp+9A9h] [rbp+8A9h] BYREF
  int *v51; // [rsp+9B0h] [rbp+8B0h]
  char *v52; // [rsp+9B8h] [rbp+8B8h]
  char *v53; // [rsp+9C0h] [rbp+8C0h]
  _BYTE v54[704]; // [rsp+9D0h] [rbp+8D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+CD8h] [rbp+BD8h]

  Buffer = 0;
  HeapInformation = 0;
  memset_0(v54, 0, sizeof(v54));
  v2 = *((_QWORD *)this + 1);
  Process = 0;
  v3 = *(HANDLE *)(v2 + 6640);
  if ( v3 )
  {
    ProcessId = GetProcessId(*(HANDLE *)(v2 + 6640));
    goto LABEL_18;
  }
  v5 = *(_QWORD *)(v2 + 9112);
  v3 = 0;
  if ( !v5 )
  {
LABEL_32:
    CReport::AddMemBlock(*((CReport **)this + 1), 0, 0x7FFE0000u, 0xAA0u, 0);
    if ( (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 1) + 5872LL) - 2) <= 1 )
    {
      CReportManager::AddLoadedModulesToReport(this);
      if ( *(_DWORD *)(*((_QWORD *)this + 1) + 5872LL) == 3 )
        CReportManager::AddUiThreadInfoToReport(this);
      v27 = 0;
      tip2::tip_test<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>>::start_and_watch_errors(
        &v27,
        v42);
      wil::com_ptr_t<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>,wil::err_returncode_policy>(&v27);
      v45 = 0;
      v51 = &v47;
      v46 = 0;
      v53 = &v50;
      v47 = -2143256512;
      v52 = &v49;
      v48 = 0;
      tson::output_archive::output_archive((tson::output_archive *)v44, (struct tson::write_buffer *)&v45, 0);
      v14 = *((_QWORD *)this + 1);
      v36[0] = v37;
      v37[0] = 0;
      v36[1] = v37;
      if ( (int)CReport::GetUniqueIdentifier(v14, v36) >= 0 && v36[0] )
      {
        string_tag = tson::make_string_tag(&v29);
        v34 = *(_OWORD *)string_tag;
        v16 = *(_QWORD *)(string_tag + 16);
        v29 = "ReportId";
        v31 = &v34;
        v35 = v16;
        v30 = 8;
        tson::output_archive::operator()<tson::nvp<tson::string_tag &>>(v44, &v29);
      }
      v17 = *((_QWORD *)this + 1);
      v18 = *(_QWORD *)(v17 + 5912);
      if ( v18 != *(_QWORD *)(v17 + 5920) && v18 )
      {
        v19 = tson::make_string_tag(&v29);
        v34 = *(_OWORD *)v19;
        v20 = *(_QWORD *)(v19 + 16);
        v29 = "IntegratorReportId";
        v31 = &v34;
        v35 = v20;
        v30 = 18;
        tson::output_archive::operator()<tson::nvp<tson::string_tag &>>(v44, &v29);
      }
      tson::output_archive::finish((tson::output_archive *)v44);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v36);
      v38[0] = v3;
      v38[2] = v52 - (char *)v51;
      v21 = *((_QWORD *)this + 1);
      v38[1] = v51;
      v22 = *(_DWORD *)(v21 + 5872) == 2;
      v23 = 16408;
      if ( !v22 )
        v23 = 16409;
      v39 = v23;
      v40 = 0;
      v41 = 0;
      v24 = TestRecoverResults(v38);
      if ( v24 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xA18,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportmanager.cpp",
          (const char *)(unsigned int)v24,
          ReturnLength);
      v25 = v43;
      wil::EnterCriticalSection(&v27, v43 + 200);
      *(_DWORD *)(v25 + 72) |= 0x300u;
      if ( *(_QWORD *)(v25 + 248) )
        tip2::details::shared_data<0,0,0>::complete_helper(v25 + 8, 2);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v27);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v45);
      tip2::test_watcher<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>>::~test_watcher<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>>(v42);
    }
    return;
  }
  Snapshot = PssQuerySnapshot(v5, 0, v54);
  if ( Snapshot )
  {
    if ( Snapshot > 0 )
      Snapshot = (unsigned __int16)Snapshot | 0x80070000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v8 = 67;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, (unsigned int)Snapshot);
      return;
    }
    return;
  }
  Snapshot = PssQuerySnapshot(*(_QWORD *)(*((_QWORD *)this + 1) + 9112LL), 1, &Process);
  if ( !Snapshot )
  {
    v9 = GetProcessId(Process);
    v3 = Process;
    ProcessId = v9;
    if ( Process )
    {
LABEL_18:
      if ( (unsigned int)CReport::DumpsRequested(*((CReport **)this + 1)) )
      {
        if ( (int)WerpReadPebFromProcess(v3, &Buffer, 0x360u, v10) >= 0 )
        {
          if ( Buffer )
          {
            v11 = CReport::AddMemBlock(*((CReport **)this + 1), ProcessId, Buffer, 0x2000u, 0);
            if ( v11 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                69,
                WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids,
                (unsigned int)v11);
          }
        }
        if ( RtlQueryHeapInformation(0, (HEAP_INFORMATION_CLASS)-2147483647, &HeapInformation, 8u, 0) >= 0 )
        {
          if ( HeapInformation )
          {
            v12 = *(_DWORD *)(HeapInformation + 4);
            if ( v12 )
            {
              v13 = CReport::AddMemBlock(*((CReport **)this + 1), 0, HeapInformation, v12, 0);
              if ( v13 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  70,
                  WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids,
                  (unsigned int)v13);
            }
          }
        }
      }
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  if ( Snapshot > 0 )
    Snapshot = (unsigned __int16)Snapshot | 0x80070000;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v8 = 68;
    goto LABEL_10;
  }
}

```

## disassembly

```asm
0x18007c77c  push    rbp
0x18007c77e  push    rbx
0x18007c77f  push    rsi
0x18007c780  push    rdi
0x18007c781  push    r14
0x18007c783  push    r15
0x18007c785  lea     rbp, [rsp-0BA8h]
0x18007c78d  sub     rsp, 0CA8h
0x18007c794  mov     rax, cs:__security_cookie
0x18007c79b  xor     rax, rsp
0x18007c79e  mov     [rbp+0BD0h+var_40], rax
0x18007c7a5  mov     rbx, rcx
0x18007c7a8  xor     r15d, r15d
0x18007c7ab  mov     edi, 2C0h
0x18007c7b0  mov     [rsp+0CD0h+Buffer], r15
0x18007c7b5  mov     r8d, edi; Size
0x18007c7b8  mov     [rsp+0CD0h+HeapInformation], r15
0x18007c7bd  xor     edx, edx; Val
0x18007c7bf  lea     rcx, [rbp+0BD0h+var_300]; void *
0x18007c7c6  call    memset_0
0x18007c7cb  mov     rcx, [rbx+8]
0x18007c7cf  mov     [rsp+0CD0h+Process], r15
0x18007c7d4  mov     rsi, [rcx+19F0h]
0x18007c7db  test    rsi, rsi
0x18007c7de  jz      short loc_18007C7F7
0x18007c7e0  mov     rcx, rsi; Process
0x18007c7e3  call    cs:__imp_GetProcessId
0x18007c7ea  nop     dword ptr [rax+rax+00h]
0x18007c7ef  mov     r14d, eax
0x18007c7f2  jmp     loc_18007C8EC
0x18007c7f7  mov     rcx, [rcx+2398h]
0x18007c7fe  mov     rsi, r15
0x18007c801  test    rcx, rcx
0x18007c804  jz      loc_18007C9E2
0x18007c80a  mov     r9d, edi
0x18007c80d  lea     r8, [rbp+0BD0h+var_300]
0x18007c814  xor     edx, edx
0x18007c816  call    cs:__imp_PssQuerySnapshot
0x18007c81d  nop     dword ptr [rax+rax+00h]
0x18007c822  test    eax, eax
0x18007c824  jz      short loc_18007C86E
0x18007c826  jle     short loc_18007C830
0x18007c828  movzx   eax, ax
0x18007c82b  or      eax, 80070000h
0x18007c830  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c837  lea     rdi, WPP_GLOBAL_Control
0x18007c83e  cmp     rcx, rdi
0x18007c841  jz      loc_18007CC4B
0x18007c847  test    byte ptr [rcx+1Ch], 1
0x18007c84b  jz      loc_18007CC4B
0x18007c851  mov     edx, 43h ; 'C'
0x18007c856  mov     rcx, [rcx+10h]
0x18007c85a  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18007c861  mov     r9d, eax
0x18007c864  call    WPP_SF_d
0x18007c869  jmp     loc_18007CC4B
0x18007c86e  mov     rcx, [rbx+8]
0x18007c872  lea     r8, [rsp+0CD0h+Process]
0x18007c877  mov     r9d, 8
0x18007c87d  mov     rcx, [rcx+2398h]
0x18007c884  lea     edx, [r9-7]
0x18007c888  call    cs:__imp_PssQuerySnapshot
0x18007c88f  nop     dword ptr [rax+rax+00h]
0x18007c894  test    eax, eax
0x18007c896  jz      short loc_18007C8CA
0x18007c898  jle     short loc_18007C8A2
0x18007c89a  movzx   eax, ax
0x18007c89d  or      eax, 80070000h
0x18007c8a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c8a9  lea     rdi, WPP_GLOBAL_Control
0x18007c8b0  cmp     rcx, rdi
0x18007c8b3  jz      loc_18007CC4B
0x18007c8b9  test    byte ptr [rcx+1Ch], 1
0x18007c8bd  jz      loc_18007CC4B
0x18007c8c3  mov     edx, 44h ; 'D'
0x18007c8c8  jmp     short loc_18007C856
0x18007c8ca  mov     rcx, [rsp+0CD0h+Process]; Process
0x18007c8cf  call    cs:__imp_GetProcessId
0x18007c8d6  nop     dword ptr [rax+rax+00h]
0x18007c8db  mov     rsi, [rsp+0CD0h+Process]
0x18007c8e0  mov     r14d, eax
0x18007c8e3  test    rsi, rsi
0x18007c8e6  jz      loc_18007C9E2
0x18007c8ec  mov     rcx, [rbx+8]; this
0x18007c8f0  call    ?DumpsRequested@CReport@@QEAAHXZ; CReport::DumpsRequested(void)
0x18007c8f5  test    eax, eax
0x18007c8f7  jz      loc_18007C9E2
0x18007c8fd  mov     r8d, 360h; unsigned int
0x18007c903  lea     rdx, [rsp+0CD0h+Buffer]; lpBuffer
0x18007c908  mov     rcx, rsi; hProcess
0x18007c90b  call    ?WerpReadPebFromProcess@@YAJPEAX0KK@Z; WerpReadPebFromProcess(void *,void *,ulong,ulong)
0x18007c910  lea     rdi, WPP_GLOBAL_Control
0x18007c917  test    eax, eax
0x18007c919  js      short loc_18007C96A
0x18007c91b  mov     r8, [rsp+0CD0h+Buffer]; unsigned __int64
0x18007c920  test    r8, r8
0x18007c923  jz      short loc_18007C96A
0x18007c925  mov     rcx, [rbx+8]; this
0x18007c929  mov     r9d, 2000h; unsigned int
0x18007c92f  mov     edx, r14d; unsigned int
0x18007c932  mov     [rsp+0CD0h+ReturnLength], r15d; unsigned int
0x18007c937  call    ?AddMemBlock@CReport@@QEAAJK_KKK@Z; CReport::AddMemBlock(ulong,unsigned __int64,ulong,ulong)
0x18007c93c  test    eax, eax
0x18007c93e  jns     short loc_18007C96A
0x18007c940  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c947  cmp     rcx, rdi
0x18007c94a  jz      short loc_18007C96A
0x18007c94c  test    byte ptr [rcx+1Ch], 2
0x18007c950  jz      short loc_18007C96A
0x18007c952  mov     rcx, [rcx+10h]
0x18007c956  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18007c95d  mov     edx, 45h ; 'E'
0x18007c962  mov     r9d, eax
0x18007c965  call    WPP_SF_d
0x18007c96a  mov     r9d, 8; HeapInformationLength
0x18007c970  mov     qword ptr [rsp+0CD0h+ReturnLength], r15; ReturnLength
0x18007c975  lea     r8, [rsp+0CD0h+HeapInformation]; HeapInformation
0x18007c97a  mov     edx, 80000001h; HeapInformationClass
0x18007c97f  xor     ecx, ecx; HeapHandle
0x18007c981  call    cs:__imp_RtlQueryHeapInformation
0x18007c988  nop     dword ptr [rax+rax+00h]
0x18007c98d  test    eax, eax
0x18007c98f  js      short loc_18007C9E2
0x18007c991  mov     r8, [rsp+0CD0h+HeapInformation]; unsigned __int64
0x18007c996  test    r8, r8
0x18007c999  jz      short loc_18007C9E2
0x18007c99b  mov     r9d, [r8+4]; unsigned int
0x18007c99f  test    r9d, r9d
0x18007c9a2  jz      short loc_18007C9E2
0x18007c9a4  mov     rcx, [rbx+8]; this
0x18007c9a8  xor     edx, edx; unsigned int
0x18007c9aa  mov     [rsp+0CD0h+ReturnLength], r15d; unsigned int
0x18007c9af  call    ?AddMemBlock@CReport@@QEAAJK_KKK@Z; CReport::AddMemBlock(ulong,unsigned __int64,ulong,ulong)
0x18007c9b4  test    eax, eax
0x18007c9b6  jns     short loc_18007C9E2
0x18007c9b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c9bf  cmp     rcx, rdi
0x18007c9c2  jz      short loc_18007C9E2
0x18007c9c4  test    byte ptr [rcx+1Ch], 2
0x18007c9c8  jz      short loc_18007C9E2
0x18007c9ca  mov     rcx, [rcx+10h]
0x18007c9ce  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18007c9d5  mov     edx, 46h ; 'F'
0x18007c9da  mov     r9d, eax
0x18007c9dd  call    WPP_SF_d
0x18007c9e2  mov     rcx, [rbx+8]; this
0x18007c9e6  xor     edx, edx; unsigned int
0x18007c9e8  mov     r9d, 0AA0h; unsigned int
0x18007c9ee  mov     [rsp+0CD0h+ReturnLength], r15d; int
0x18007c9f3  mov     r8d, 7FFE0000h; unsigned __int64
0x18007c9f9  call    ?AddMemBlock@CReport@@QEAAJK_KKK@Z; CReport::AddMemBlock(ulong,unsigned __int64,ulong,ulong)
0x18007c9fe  mov     rax, [rbx+8]
0x18007ca02  mov     ecx, [rax+16F0h]
0x18007ca08  sub     ecx, 2
0x18007ca0b  cmp     ecx, 1
0x18007ca0e  ja      loc_18007CC4B
0x18007ca14  mov     rcx, rbx; this
0x18007ca17  call    ?AddLoadedModulesToReport@CReportManager@@AEAAJXZ; CReportManager::AddLoadedModulesToReport(void)
0x18007ca1c  mov     rax, [rbx+8]
0x18007ca20  cmp     dword ptr [rax+16F0h], 3
0x18007ca27  jnz     short loc_18007CA31
0x18007ca29  mov     rcx, rbx; this
0x18007ca2c  call    ?AddUiThreadInfoToReport@CReportManager@@AEAAJXZ; CReportManager::AddUiThreadInfoToReport(void)
0x18007ca31  lea     rdx, [rbp+0BD0h+var_C10]
0x18007ca35  mov     [rsp+0CD0h+var_CA0], r15
0x18007ca3a  lea     rcx, [rsp+0CD0h+var_CA0]
0x18007ca3f  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_TipWerHandlerTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_TipWerHandlerTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>>::start_and_watch_errors(void)
0x18007ca44  lea     rcx, [rsp+0CD0h+var_CA0]
0x18007ca49  call    ??1?$com_ptr_t@V?$merged_data@U_tip_TipWerHandlerTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>,wil::err_returncode_policy>(void)
0x18007ca4e  lea     rax, [rbp+0BD0h+var_B27]
0x18007ca55  mov     [rbp+0BD0h+var_B30], r15
0x18007ca5c  mov     [rbp+0BD0h+var_320], rax
0x18007ca63  lea     rdx, [rbp+0BD0h+var_B30]; struct tson::write_buffer *
0x18007ca6a  lea     rax, [rbp+0BD0h+var_327]
0x18007ca71  mov     [rbp+0BD0h+var_B28], r15b
0x18007ca78  mov     [rbp+0BD0h+var_310], rax
0x18007ca7f  lea     rcx, [rbp+0BD0h+var_BD0]; this
0x18007ca83  lea     rax, [rbp+0BD0h+var_B22]
0x18007ca8a  mov     [rbp+0BD0h+var_B27], 80408040h
0x18007ca94  xor     r8d, r8d; unsigned __int8
0x18007ca97  mov     [rbp+0BD0h+var_318], rax
0x18007ca9e  mov     [rbp+0BD0h+var_B23], r15b
0x18007caa5  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x18007caaa  mov     rcx, [rbx+8]
0x18007caae  lea     rax, [rbp+0BD0h+var_C40]
0x18007cab2  mov     [rbp+0BD0h+var_C50], rax
0x18007cab6  lea     rdx, [rbp+0BD0h+var_C50]
0x18007caba  lea     rax, [rbp+0BD0h+var_C40]
0x18007cabe  mov     [rbp+0BD0h+var_C40], r15w
0x18007cac3  mov     [rbp+0BD0h+var_C48], rax
0x18007cac7  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18007cacc  test    eax, eax
0x18007cace  js      short loc_18007CB1F
0x18007cad0  mov     rdx, [rbp+0BD0h+var_C50]
0x18007cad4  test    rdx, rdx
0x18007cad7  jz      short loc_18007CB1F
0x18007cad9  lea     rcx, [rsp+0CD0h+var_C90]
0x18007cade  call    ?make_string_tag@tson@@YA?AUstring_tag@1@PEB_W@Z; tson::make_string_tag(wchar_t const *)
0x18007cae3  lea     rdx, [rsp+0CD0h+var_C90]
0x18007cae8  lea     rcx, [rbp+0BD0h+var_BD0]
0x18007caec  movups  xmm0, xmmword ptr [rax]
0x18007caef  movups  [rsp+0CD0h+var_C68], xmm0
0x18007caf4  movsd   xmm1, qword ptr [rax+10h]
0x18007caf9  lea     rax, aReportid; "ReportId"
0x18007cb00  mov     [rsp+0CD0h+var_C90], rax
0x18007cb05  lea     rax, [rsp+0CD0h+var_C68]
0x18007cb0a  mov     [rsp+0CD0h+var_C80], rax
0x18007cb0f  movsd   [rsp+0CD0h+var_C58], xmm1
0x18007cb15  mov     [rsp+0CD0h+var_C88], 8
0x18007cb1a  call    ??$?RV?$nvp@AEAUstring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAUstring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::string_tag &>>(tson::nvp<tson::string_tag &> &&)
0x18007cb1f  mov     rax, [rbx+8]
0x18007cb23  mov     rdx, [rax+1718h]
0x18007cb2a  cmp     rdx, [rax+1720h]
0x18007cb31  jz      short loc_18007CB7E
0x18007cb33  test    rdx, rdx
0x18007cb36  jz      short loc_18007CB7E
0x18007cb38  lea     rcx, [rsp+0CD0h+var_C90]
0x18007cb3d  call    ?make_string_tag@tson@@YA?AUstring_tag@1@PEB_W@Z; tson::make_string_tag(wchar_t const *)
0x18007cb42  lea     rdx, [rsp+0CD0h+var_C90]
0x18007cb47  lea     rcx, [rbp+0BD0h+var_BD0]
0x18007cb4b  movups  xmm0, xmmword ptr [rax]
0x18007cb4e  movups  [rsp+0CD0h+var_C68], xmm0
0x18007cb53  movsd   xmm1, qword ptr [rax+10h]
0x18007cb58  lea     rax, aIntegratorrepo_0; "IntegratorReportId"
0x18007cb5f  mov     [rsp+0CD0h+var_C90], rax
0x18007cb64  lea     rax, [rsp+0CD0h+var_C68]
0x18007cb69  mov     [rsp+0CD0h+var_C80], rax
0x18007cb6e  movsd   [rsp+0CD0h+var_C58], xmm1
0x18007cb74  mov     [rsp+0CD0h+var_C88], 12h
0x18007cb79  call    ??$?RV?$nvp@AEAUstring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAUstring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::string_tag &>>(tson::nvp<tson::string_tag &> &&)
0x18007cb7e  lea     rcx, [rbp+0BD0h+var_BD0]; this
0x18007cb82  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x18007cb87  lea     rcx, [rbp+0BD0h+var_C50]; void *
0x18007cb8b  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007cb90  mov     rcx, [rbp+0BD0h+var_320]
0x18007cb97  mov     rax, [rbp+0BD0h+var_318]
0x18007cb9e  sub     rax, rcx
0x18007cba1  mov     [rbp+0BD0h+var_C30], rsi
0x18007cba5  mov     [rbp+0BD0h+var_C20], rax
0x18007cba9  mov     rax, [rbx+8]
0x18007cbad  mov     [rbp+0BD0h+var_C28], rcx
0x18007cbb1  cmp     dword ptr [rax+16F0h], 2
0x18007cbb8  mov     eax, 4018h
0x18007cbbd  jz      short loc_18007CBC4
0x18007cbbf  mov     eax, 4019h
0x18007cbc4  mov     [rbp+0BD0h+var_C18], ax
0x18007cbc8  lea     rcx, [rbp+0BD0h+var_C30]
0x18007cbcc  xor     eax, eax
0x18007cbce  mov     [rbp+0BD0h+var_C16], eax
0x18007cbd1  mov     [rbp+0BD0h+var_C12], ax
0x18007cbd5  call    TestRecoverResults
0x18007cbda  test    eax, eax
0x18007cbdc  jns     short loc_18007CBF9
0x18007cbde  mov     rcx, [rbp+0BD8h]; this
0x18007cbe5  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werdl"...
0x18007cbec  mov     r9d, eax; char *
0x18007cbef  mov     edx, 0A18h; void *
0x18007cbf4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007cbf9  mov     rbx, [rbp+0BD0h+var_BD8]
0x18007cbfd  lea     rcx, [rsp+0CD0h+var_CA0]
0x18007cc02  lea     rdx, [rbx+0C8h]
0x18007cc09  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18007cc0e  or      dword ptr [rbx+48h], 300h
0x18007cc15  cmp     [rbx+0F8h], r15
0x18007cc1c  jz      short loc_18007CC2C
0x18007cc1e  mov     edx, 2
0x18007cc23  lea     rcx, [rbx+8]
0x18007cc27  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18007cc2c  lea     rcx, [rsp+0CD0h+var_CA0]
0x18007cc31  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18007cc36  lea     rcx, [rbp+0BD0h+var_B30]
0x18007cc3d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007cc42  lea     rcx, [rbp+0BD0h+var_C10]
0x18007cc46  call    ??1?$test_watcher@V?$merged_data@U_tip_TipWerHandlerTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>>::~test_watcher<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>>(void)
0x18007cc4b  mov     rcx, [rbp+0BD0h+var_40]
0x18007cc52  xor     rcx, rsp; StackCookie
0x18007cc55  call    __security_check_cookie
0x18007cc5a  add     rsp, 0CA8h
0x18007cc61  pop     r15
0x18007cc63  pop     r14
0x18007cc65  pop     rdi
0x18007cc66  pop     rsi
0x18007cc67  pop     rbx
0x18007cc68  pop     rbp
0x18007cc69  retn
```
