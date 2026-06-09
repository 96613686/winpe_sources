# TetheringService::SendNotificationWorker(void)

- ea: `0x18001c32c`
- end: `0x18001c615`
- name: `?SendNotificationWorker@TetheringService@@AEAAXXZ`
- size: `745`
- prototype: `void __fastcall(TetheringService *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001c184`
- `0x18001c620`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x18001c32c`
- `0x1800214b0`
- `0x180021a54`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c5c8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c5c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c5d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c5d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c38e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c38e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c543`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c543`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c37b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c37b`
- `ntdll!RtlPublishWnfStateData` at `0x18001c439`
- `ntdll!RtlPublishWnfStateData` at `0x18001c439`
- `ntdll!RtlQueryWnfMetaNotification` at `0x18001c3ff`
- `ntdll!RtlQueryWnfMetaNotification` at `0x18001c3ff`

## pseudocode

```c
void __fastcall TetheringService::SendNotificationWorker(TetheringService *this)
{
  ULONGLONG TickCount64; // rbx
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  TetheringService **v4; // rax
  char *v5; // rbx
  TetheringService *v6; // rcx
  int v7; // eax
  unsigned int *v8; // rdi
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  unsigned int v17; // edi
  HRESULT v18; // eax
  TetheringServiceTelemetry *v19; // rcx
  __int64 v20; // rdx
  int v21; // [rsp+50h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 242, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  v21 = 0;
  TickCount64 = GetTickCount64();
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1304);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1304));
  if ( qword_180041F50 && TickCount64 - qword_180041F50 < 0x1E )
    WnfWaitForQuiescent(WNF_TETH_TETHERING_STATE, qword_180041F50 - TickCount64 + 30);
  qword_180041F50 = TickCount64;
  v4 = (TetheringService **)((char *)this + 1344);
  v5 = (char *)*((_QWORD *)this + 168);
  if ( *((TetheringService **)v5 + 1) != (TetheringService *)((char *)this + 1344)
    || (v6 = *(TetheringService **)v5, *(char **)(*(_QWORD *)v5 + 8LL) != v5) )
  {
    __fastfail(3u);
  }
  *v4 = v6;
  *((_QWORD *)v6 + 1) = v4;
  v7 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))RtlQueryWnfMetaNotification)(&v21, 1, WNF_TETH_TETHERING_STATE);
  if ( v7 < 0 )
    goto LABEL_23;
  if ( v21 == 1 )
  {
    v8 = (unsigned int *)(v5 + 16);
    v9 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))RtlPublishWnfStateData)(
           WNF_TETH_TETHERING_STATE,
           0,
           v5 + 16,
           212,
           0);
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ld(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, *v8, v9 | 0x10000000);
      }
    }
    else if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 243, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, *v8);
    }
    goto LABEL_25;
  }
  if ( v21 )
  {
LABEL_23:
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        246,
        &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
        v7 | 0x10000000u);
    }
  }
  else if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 245, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
LABEL_25:
  v12 = *((_DWORD *)v5 + 4);
  if ( !v12 || (v13 = v12 - 1) == 0 || (v14 = v13 - 1) == 0 )
  {
LABEL_31:
    v17 = 8;
    goto LABEL_32;
  }
  v15 = v14 - 1;
  if ( v15 )
  {
    v16 = v15 - 1;
    if ( v16 )
    {
      if ( (unsigned int)(v16 - 4) > 1 )
        goto LABEL_44;
      goto LABEL_31;
    }
  }
  v17 = 16;
LABEL_32:
  ppv = 0;
  v18 = CoCreateInstance(&CLSID_CNetworkListManager, 0, 0x17u, &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b, &ppv);
  if ( v18 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v20 = 248;
      goto LABEL_41;
    }
  }
  else
  {
    v18 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 168LL))(ppv, v17);
    if ( v18 < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v20 = 247;
LABEL_41:
        WPP_SF_d(*((_QWORD *)v19 + 2), v20, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, (unsigned int)v18);
      }
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_44:
  free(v5);
  LeaveCriticalSection(v3);
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 249, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
}

```

## disassembly

```asm
0x18001c32c  mov     [rsp+arg_10], rbx
0x18001c331  mov     [rsp+arg_18], rsi
0x18001c336  push    rdi
0x18001c337  push    r14
0x18001c339  push    r15
0x18001c33b  sub     rsp, 30h
0x18001c33f  mov     rdi, rcx
0x18001c342  lea     r14, WPP_GLOBAL_Control
0x18001c349  lea     r15, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001c350  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c357  cmp     rcx, r14
0x18001c35a  jz      short loc_18001C373
0x18001c35c  test    byte ptr [rcx+1Ch], 8
0x18001c360  jz      short loc_18001C373
0x18001c362  mov     edx, 0F2h
0x18001c367  mov     r8, r15
0x18001c36a  mov     rcx, [rcx+10h]
0x18001c36e  call    WPP_SF_
0x18001c373  mov     [rsp+48h+arg_0], 0
0x18001c37b  call    cs:__imp_GetTickCount64
0x18001c381  mov     rbx, rax
0x18001c384  lea     rsi, [rdi+518h]
0x18001c38b  mov     rcx, rsi; lpCriticalSection
0x18001c38e  call    cs:__imp_EnterCriticalSection
0x18001c394  mov     rdx, cs:qword_180041F50
0x18001c39b  test    rdx, rdx
0x18001c39e  jz      short loc_18001C3BD
0x18001c3a0  mov     rcx, rbx
0x18001c3a3  sub     rcx, rdx
0x18001c3a6  cmp     rcx, 1Eh
0x18001c3aa  jnb     short loc_18001C3BD
0x18001c3ac  sub     edx, ebx
0x18001c3ae  add     edx, 1Eh; unsigned int
0x18001c3b1  mov     rcx, qword ptr cs:WNF_TETH_TETHERING_STATE.Data; struct _WNF_STATE_NAME
0x18001c3b8  call    ?WnfWaitForQuiescent@@YAXU_WNF_STATE_NAME@@K@Z; WnfWaitForQuiescent(_WNF_STATE_NAME,ulong)
0x18001c3bd  mov     cs:qword_180041F50, rbx
0x18001c3c4  lea     rax, [rdi+540h]
0x18001c3cb  mov     rbx, [rax]
0x18001c3ce  cmp     [rbx+8], rax
0x18001c3d2  jnz     loc_18001C60E
0x18001c3d8  mov     rcx, [rbx]
0x18001c3db  cmp     [rcx+8], rbx
0x18001c3df  jnz     loc_18001C60E
0x18001c3e5  mov     [rax], rcx
0x18001c3e8  mov     [rcx+8], rax
0x18001c3ec  xor     r9d, r9d
0x18001c3ef  mov     r8, qword ptr cs:WNF_TETH_TETHERING_STATE.Data
0x18001c3f6  lea     edx, [r9+1]
0x18001c3fa  lea     rcx, [rsp+48h+arg_0]
0x18001c3ff  call    cs:__imp_RtlQueryWnfMetaNotification
0x18001c405  test    eax, eax
0x18001c407  js      loc_18001C4C4
0x18001c40d  mov     ecx, [rsp+48h+arg_0]
0x18001c411  cmp     ecx, 1
0x18001c414  jnz     loc_18001C49B
0x18001c41a  lea     rdi, [rbx+10h]
0x18001c41e  mov     [rsp+48h+ppv], 0
0x18001c427  mov     r9d, 0D4h
0x18001c42d  mov     r8, rdi
0x18001c430  xor     edx, edx
0x18001c432  mov     rcx, qword ptr cs:WNF_TETH_TETHERING_STATE.Data
0x18001c439  call    cs:__imp_RtlPublishWnfStateData
0x18001c43f  test    eax, eax
0x18001c441  js      short loc_18001C473
0x18001c443  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c44a  cmp     rcx, r14
0x18001c44d  jz      loc_18001C4EE
0x18001c453  test    byte ptr [rcx+1Ch], 4
0x18001c457  jz      loc_18001C4EE
0x18001c45d  mov     edx, 0F3h
0x18001c462  mov     r9d, [rdi]
0x18001c465  mov     r8, r15
0x18001c468  mov     rcx, [rcx+10h]
0x18001c46c  call    WPP_SF_d
0x18001c471  jmp     short loc_18001C4EE
0x18001c473  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c47a  cmp     rcx, r14
0x18001c47d  jz      short loc_18001C4EE
0x18001c47f  test    byte ptr [rcx+1Ch], 1
0x18001c483  jz      short loc_18001C4EE
0x18001c485  bts     eax, 1Ch
0x18001c489  mov     dword ptr [rsp+48h+ppv], eax
0x18001c48d  mov     r9d, [rdi]
0x18001c490  mov     rcx, [rcx+10h]
0x18001c494  call    WPP_SF_Ld
0x18001c499  jmp     short loc_18001C4EE
0x18001c49b  test    ecx, ecx
0x18001c49d  jnz     short loc_18001C4C4
0x18001c49f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c4a6  cmp     rcx, r14
0x18001c4a9  jz      short loc_18001C4EE
0x18001c4ab  test    byte ptr [rcx+1Ch], 4
0x18001c4af  jz      short loc_18001C4EE
0x18001c4b1  mov     edx, 0F5h
0x18001c4b6  mov     r8, r15
0x18001c4b9  mov     rcx, [rcx+10h]
0x18001c4bd  call    WPP_SF_
0x18001c4c2  jmp     short loc_18001C4EE
0x18001c4c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c4cb  cmp     rcx, r14
0x18001c4ce  jz      short loc_18001C4EE
0x18001c4d0  test    byte ptr [rcx+1Ch], 1
0x18001c4d4  jz      short loc_18001C4EE
0x18001c4d6  bts     eax, 1Ch
0x18001c4da  mov     edx, 0F6h
0x18001c4df  mov     r9d, eax
0x18001c4e2  mov     r8, r15
0x18001c4e5  mov     rcx, [rcx+10h]
0x18001c4e9  call    WPP_SF_d
0x18001c4ee  mov     ecx, [rbx+10h]
0x18001c4f1  test    ecx, ecx
0x18001c4f3  jz      short loc_18001C517
0x18001c4f5  sub     ecx, 1
0x18001c4f8  jz      short loc_18001C517
0x18001c4fa  sub     ecx, 1
0x18001c4fd  jz      short loc_18001C517
0x18001c4ff  sub     ecx, 1
0x18001c502  jz      short loc_18001C580
0x18001c504  sub     ecx, 1
0x18001c507  jz      short loc_18001C580
0x18001c509  sub     ecx, 4
0x18001c50c  jz      short loc_18001C517
0x18001c50e  cmp     ecx, 1
0x18001c511  jnz     loc_18001C5C5
0x18001c517  mov     edi, 8
0x18001c51c  mov     [rsp+48h+arg_8], 0
0x18001c525  lea     rax, [rsp+48h+arg_8]
0x18001c52a  mov     [rsp+48h+ppv], rax; ppv
0x18001c52f  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x18001c536  xor     edx, edx; pUnkOuter
0x18001c538  lea     r8d, [rdx+17h]; dwClsContext
0x18001c53c  lea     rcx, CLSID_CNetworkListManager; rclsid
0x18001c543  call    cs:__imp_CoCreateInstance
0x18001c549  test    eax, eax
0x18001c54b  js      short loc_18001C587
0x18001c54d  mov     rcx, [rsp+48h+arg_8]
0x18001c552  mov     rax, [rcx]
0x18001c555  mov     edx, edi
0x18001c557  mov     rax, [rax+0A8h]
0x18001c55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c563  test    eax, eax
0x18001c565  jns     short loc_18001C5AE
0x18001c567  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c56e  cmp     rcx, r14
0x18001c571  jz      short loc_18001C5AE
0x18001c573  test    byte ptr [rcx+1Ch], 1
0x18001c577  jz      short loc_18001C5AE
0x18001c579  mov     edx, 0F7h
0x18001c57e  jmp     short loc_18001C59E
0x18001c580  mov     edi, 10h
0x18001c585  jmp     short loc_18001C51C
0x18001c587  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c58e  cmp     rcx, r14
0x18001c591  jz      short loc_18001C5AE
0x18001c593  test    byte ptr [rcx+1Ch], 1
0x18001c597  jz      short loc_18001C5AE
0x18001c599  mov     edx, 0F8h
0x18001c59e  mov     r9d, eax
0x18001c5a1  mov     r8, r15
0x18001c5a4  mov     rcx, [rcx+10h]
0x18001c5a8  call    WPP_SF_d
0x18001c5ad  nop
0x18001c5ae  mov     rcx, [rsp+48h+arg_8]
0x18001c5b3  test    rcx, rcx
0x18001c5b6  jz      short loc_18001C5C5
0x18001c5b8  mov     rax, [rcx]
0x18001c5bb  mov     rax, [rax+10h]
0x18001c5bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5c4  nop
0x18001c5c5  mov     rcx, rbx; Block
0x18001c5c8  call    cs:__imp_free
0x18001c5ce  mov     rcx, rsi; lpCriticalSection
0x18001c5d1  call    cs:__imp_LeaveCriticalSection
0x18001c5d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5de  cmp     rcx, r14
0x18001c5e1  jz      short loc_18001C5FA
0x18001c5e3  test    byte ptr [rcx+1Ch], 8
0x18001c5e7  jz      short loc_18001C5FA
0x18001c5e9  mov     edx, 0F9h
0x18001c5ee  mov     r8, r15
0x18001c5f1  mov     rcx, [rcx+10h]
0x18001c5f5  call    WPP_SF_
0x18001c5fa  mov     rbx, [rsp+48h+arg_10]
0x18001c5ff  mov     rsi, [rsp+48h+arg_18]
0x18001c604  add     rsp, 30h
0x18001c608  pop     r15
0x18001c60a  pop     r14
0x18001c60c  pop     rdi
0x18001c60d  retn
0x18001c60e  mov     ecx, 3
0x18001c613  int     29h; Win8: RtlFailFast(ecx)
```
