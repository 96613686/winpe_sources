# CWdsTransportSetupManager::RegisterContentProvider(ushort *,ushort *,ushort *,ushort *)

- ea: `0x18000a6e0`
- end: `0x18000a9c0`
- name: `?RegisterContentProvider@CWdsTransportSetupManager@@UEAAJPEAG000@Z`
- size: `736`
- prototype: `int(CWdsTransportSetupManager *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180009e20`
- `0x18000a6e0`
- `0x18000aa34`
- `0x18000b048`
- `0x18000b16c`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x18000a83f`
- `ADVAPI32!RegCreateKeyExW` at `0x18000a83f`
- `WdsCommonLib!?DeleteSubkey@CRegKey@@QEAAKPEBG@Z` at `0x18000a927`
- `WdsCommonLib!?DeleteSubkey@CRegKey@@QEAAKPEBG@Z` at `0x18000a927`
- `WdsCommonLib!?SetValueSz@CRegKey@@QEAAKPEBG0@Z` at `0x18000a88c`
- `WdsCommonLib!?SetValueSz@CRegKey@@QEAAKPEBG0@Z` at `0x18000a8e6`
- `WdsCommonLib!?SetValueSz@CRegKey@@QEAAKPEBG0@Z` at `0x18000a88c`
- `WdsCommonLib!?SetValueSz@CRegKey@@QEAAKPEBG0@Z` at `0x18000a8e6`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000a7c8`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000a7c8`
- `WdsCommonLib!?SetValueExpSz@CRegKey@@QEAAKPEBG0@Z` at `0x18000a8b9`
- `WdsCommonLib!?SetValueExpSz@CRegKey@@QEAAKPEBG0@Z` at `0x18000a8b9`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a736`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a7f0`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a951`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a97e`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a736`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a7f0`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a951`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a97e`

## string_xrefs

- `0x18000a7aa`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSMC\Providers`
- `0x18000a7dd`: `Failed to open the server content provider store with error 0x%lx\n`
- `0x18000a8ae`: `ProviderDll`

## pseudocode

```c
__int64 __fastcall CWdsTransportSetupManager::RegisterContentProvider(
        CWdsTransportSetupManager *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  const unsigned __int16 *v9; // r14
  __int64 v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // eax
  __int64 v14; // rbx
  HKEY v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned int v24; // eax
  __int64 dwOptions; // [rsp+20h] [rbp-50h]
  HKEY phkResult; // [rsp+50h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-18h] BYREF
  _BYTE v29[16]; // [rsp+60h] [rbp-10h] BYREF
  DWORD dwDisposition; // [rsp+B0h] [rbp+40h] BYREF
  int v31; // [rsp+B8h] [rbp+48h]

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v29, (char *)this + 80);
  hKey = 0;
  phkResult = 0;
  dwDisposition = 0;
  v31 = 0;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportSetupManager::RegisterContentProvider(0x%p)",
    this);
  if ( !a2 || !*a2 || !a3 || !a4 || !*a4 || (v9 = a5) == 0 || !*a5 )
  {
    LODWORD(v10) = -2147024809;
    goto LABEL_25;
  }
  v10 = (unsigned int)CWdsTransportSetupManager::ValidateContentProviderName(a2);
  if ( (int)ElValidateHr_2(v10, v11, v12, 707) < 0 )
    goto LABEL_20;
  v13 = CRegKey::RemoteOpen(
          (CRegKey *)&hKey,
          *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL),
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSMC\\Providers",
          0x20006u);
  LODWORD(v14) = v13;
  if ( v13 )
  {
    CTrace::Trace(
      (CTrace *)qword_18003B770,
      0x80000u,
      L"Failed to open the server content provider store with error 0x%lx\n",
      v13);
LABEL_17:
    if ( (int)v14 > 0 )
      LODWORD(v10) = (unsigned __int16)v14 | 0x80070000;
    else
      LODWORD(v10) = v14;
    goto LABEL_20;
  }
  v15 = hKey;
  CRegKey::Close((CRegKey *)&phkResult);
  v14 = (unsigned int)RegCreateKeyExW(v15, a2, 0, 0, 0, 0x20106u, 0, &phkResult, &dwDisposition);
  if ( (unsigned int)ElValidateWin32_2(v14, v16, v17, 736) )
    goto LABEL_17;
  if ( dwDisposition == 2 )
  {
    CRegKey::Close((CRegKey *)&phkResult);
    LODWORD(v10) = -1055915773;
    goto LABEL_25;
  }
  v31 = 1;
  v14 = CRegKey::SetValueSz((CRegKey *)&phkResult, L"Description", a3);
  if ( (unsigned int)ElValidateWin32_2(v14, v18, v19, 765) )
    goto LABEL_17;
  v14 = CRegKey::SetValueExpSz((CRegKey *)&phkResult, L"ProviderDll", a4);
  if ( (unsigned int)ElValidateWin32_2(v14, v20, v21, 769) )
    goto LABEL_17;
  v14 = CRegKey::SetValueSz((CRegKey *)&phkResult, L"InitRoutine", v9);
  if ( (unsigned int)ElValidateWin32_2(v14, v22, v23, 773) )
    goto LABEL_17;
LABEL_20:
  if ( (int)v10 < 0 )
  {
    if ( v31 )
    {
      v24 = CRegKey::DeleteSubkey((CRegKey *)&hKey, a2);
      if ( v24 )
      {
        LODWORD(dwOptions) = v24;
        CTrace::Trace(
          (CTrace *)qword_18003B770,
          0x40000u,
          L"Could not clean up failed content provider registration.\n"
           "Deletion of partial content provider %s failed with 0x%lx.\n",
          a2,
          dwOptions);
      }
    }
  }
LABEL_25:
  LODWORD(dwOptions) = v10;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportSetupManager::RegisterContentProvider(0x%p) =%x",
    this,
    dwOptions);
  CRegKey::Close((CRegKey *)&phkResult);
  CRegKey::Close((CRegKey *)&hKey);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v29);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000a6e0  mov     [rsp-38h+arg_10], rbx
0x18000a6e5  push    rbp
0x18000a6e6  push    rsi
0x18000a6e7  push    rdi
0x18000a6e8  push    r12
0x18000a6ea  push    r13
0x18000a6ec  push    r14
0x18000a6ee  push    r15
0x18000a6f0  mov     rbp, rsp
0x18000a6f3  sub     rsp, 70h
0x18000a6f7  mov     rsi, rdx
0x18000a6fa  mov     r13, rcx
0x18000a6fd  lea     rdx, [rcx+50h]
0x18000a701  mov     r15, r9
0x18000a704  lea     rcx, [rbp+var_10]
0x18000a708  mov     r12, r8
0x18000a70b  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000a710  xor     ebx, ebx
0x18000a712  lea     r8, aCwdstransports_50; "-> CWdsTransportSetupManager::RegisterC"...
0x18000a719  mov     r9, r13
0x18000a71c  mov     [rbp+hKey], rbx
0x18000a720  mov     edx, 10000h
0x18000a725  mov     [rbp+var_20], rbx
0x18000a729  lea     rcx, qword_18003B770
0x18000a730  mov     [rbp+dwDisposition], ebx
0x18000a733  mov     [rbp+arg_8], ebx
0x18000a736  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000a73d  nop     dword ptr [rax+rax+00h]
0x18000a742  test    rsi, rsi
0x18000a745  jz      loc_18000A95F
0x18000a74b  cmp     [rsi], bx
0x18000a74e  jz      loc_18000A95F
0x18000a754  test    r12, r12
0x18000a757  jz      loc_18000A95F
0x18000a75d  test    r15, r15
0x18000a760  jz      loc_18000A95F
0x18000a766  cmp     [r15], bx
0x18000a76a  jz      loc_18000A95F
0x18000a770  mov     r14, [rbp+arg_20]
0x18000a774  test    r14, r14
0x18000a777  jz      loc_18000A95F
0x18000a77d  cmp     [r14], bx
0x18000a781  jz      loc_18000A95F
0x18000a787  mov     rcx, rsi; unsigned __int16 *
0x18000a78a  call    ?ValidateContentProviderName@CWdsTransportSetupManager@@SAJPEAG@Z; CWdsTransportSetupManager::ValidateContentProviderName(ushort *)
0x18000a78f  mov     r9d, 2C3h
0x18000a795  mov     ecx, eax
0x18000a797  mov     edi, eax
0x18000a799  call    ElValidateHr_2
0x18000a79e  test    eax, eax
0x18000a7a0  js      loc_18000A916
0x18000a7a6  mov     rdx, [r13+40h]
0x18000a7aa  lea     r9, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\WD"...
0x18000a7b1  mov     r8, 0FFFFFFFF80000002h
0x18000a7b8  mov     dword ptr [rsp+70h+dwOptions], 20006h; dwOptions
0x18000a7c0  lea     rcx, [rbp+hKey]
0x18000a7c4  mov     rdx, [rdx+70h]
0x18000a7c8  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x18000a7cf  nop     dword ptr [rax+rax+00h]
0x18000a7d4  mov     ebx, eax
0x18000a7d6  test    eax, eax
0x18000a7d8  jz      short loc_18000A801
0x18000a7da  mov     r9d, eax
0x18000a7dd  lea     r8, aFailedToOpenTh; "Failed to open the server content provi"...
0x18000a7e4  mov     edx, 80000h
0x18000a7e9  lea     rcx, qword_18003B770
0x18000a7f0  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000a7f7  nop     dword ptr [rax+rax+00h]
0x18000a7fc  jmp     loc_18000A905
0x18000a801  mov     rbx, [rbp+hKey]
0x18000a805  lea     rcx, [rbp+var_20]; this
0x18000a809  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x18000a80e  lea     rax, [rbp+dwDisposition]
0x18000a812  xor     r9d, r9d; lpClass
0x18000a815  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x18000a81a  xor     r8d, r8d; Reserved
0x18000a81d  lea     rax, [rbp+var_20]
0x18000a821  mov     rdx, rsi; lpSubKey
0x18000a824  mov     [rsp+70h+phkResult], rax; phkResult
0x18000a829  mov     rcx, rbx; hKey
0x18000a82c  and     [rsp+70h+var_40], 0
0x18000a832  mov     [rsp+70h+samDesired], 20106h; samDesired
0x18000a83a  and     dword ptr [rsp+70h+dwOptions], 0
0x18000a83f  call    cs:__imp_RegCreateKeyExW
0x18000a846  nop     dword ptr [rax+rax+00h]
0x18000a84b  mov     ecx, eax
0x18000a84d  mov     r9d, 2E0h
0x18000a853  mov     ebx, eax
0x18000a855  call    ElValidateWin32_2
0x18000a85a  test    eax, eax
0x18000a85c  jnz     loc_18000A905
0x18000a862  cmp     [rbp+dwDisposition], 2
0x18000a866  lea     rcx, [rbp+var_20]; this
0x18000a86a  jnz     short loc_18000A87B
0x18000a86c  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x18000a871  mov     edi, 0C1100103h
0x18000a876  jmp     loc_18000A964
0x18000a87b  mov     r8, r12
0x18000a87e  mov     [rbp+arg_8], 1
0x18000a885  lea     rdx, aDescription; "Description"
0x18000a88c  call    cs:__imp_?SetValueSz@CRegKey@@QEAAKPEBG0@Z; CRegKey::SetValueSz(ushort const *,ushort const *)
0x18000a893  nop     dword ptr [rax+rax+00h]
0x18000a898  mov     ecx, eax
0x18000a89a  mov     r9d, 2FDh
0x18000a8a0  mov     ebx, eax
0x18000a8a2  call    ElValidateWin32_2
0x18000a8a7  test    eax, eax
0x18000a8a9  jnz     short loc_18000A905
0x18000a8ab  mov     r8, r15
0x18000a8ae  lea     rdx, aProviderdll; "ProviderDll"
0x18000a8b5  lea     rcx, [rbp+var_20]
0x18000a8b9  call    cs:__imp_?SetValueExpSz@CRegKey@@QEAAKPEBG0@Z; CRegKey::SetValueExpSz(ushort const *,ushort const *)
0x18000a8c0  nop     dword ptr [rax+rax+00h]
0x18000a8c5  mov     ecx, eax
0x18000a8c7  mov     r9d, 301h
0x18000a8cd  mov     ebx, eax
0x18000a8cf  call    ElValidateWin32_2
0x18000a8d4  test    eax, eax
0x18000a8d6  jnz     short loc_18000A905
0x18000a8d8  mov     r8, r14
0x18000a8db  lea     rdx, aInitroutine; "InitRoutine"
0x18000a8e2  lea     rcx, [rbp+var_20]
0x18000a8e6  call    cs:__imp_?SetValueSz@CRegKey@@QEAAKPEBG0@Z; CRegKey::SetValueSz(ushort const *,ushort const *)
0x18000a8ed  nop     dword ptr [rax+rax+00h]
0x18000a8f2  mov     ecx, eax
0x18000a8f4  mov     r9d, 305h
0x18000a8fa  mov     ebx, eax
0x18000a8fc  call    ElValidateWin32_2
0x18000a901  test    eax, eax
0x18000a903  jz      short loc_18000A916
0x18000a905  test    ebx, ebx
0x18000a907  jg      short loc_18000A90D
0x18000a909  mov     edi, ebx
0x18000a90b  jmp     short loc_18000A916
0x18000a90d  movzx   edi, bx
0x18000a910  or      edi, 80070000h
0x18000a916  test    edi, edi
0x18000a918  jns     short loc_18000A964
0x18000a91a  cmp     [rbp+arg_8], 0
0x18000a91e  jz      short loc_18000A964
0x18000a920  mov     rdx, rsi
0x18000a923  lea     rcx, [rbp+hKey]
0x18000a927  call    cs:__imp_?DeleteSubkey@CRegKey@@QEAAKPEBG@Z; CRegKey::DeleteSubkey(ushort const *)
0x18000a92e  nop     dword ptr [rax+rax+00h]
0x18000a933  test    eax, eax
0x18000a935  jz      short loc_18000A964
0x18000a937  mov     r9, rsi
0x18000a93a  mov     dword ptr [rsp+70h+dwOptions], eax
0x18000a93e  lea     r8, aCouldNotCleanU; "Could not clean up failed content provi"...
0x18000a945  mov     edx, 40000h
0x18000a94a  lea     rcx, qword_18003B770
0x18000a951  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000a958  nop     dword ptr [rax+rax+00h]
0x18000a95d  jmp     short loc_18000A964
0x18000a95f  mov     edi, 80070057h
0x18000a964  mov     r9, r13
0x18000a967  mov     dword ptr [rsp+70h+dwOptions], edi
0x18000a96b  lea     r8, aCwdstransports_35; "<- CWdsTransportSetupManager::RegisterC"...
0x18000a972  mov     edx, 10000h
0x18000a977  lea     rcx, qword_18003B770
0x18000a97e  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000a985  nop     dword ptr [rax+rax+00h]
0x18000a98a  lea     rcx, [rbp+var_20]; this
0x18000a98e  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x18000a993  lea     rcx, [rbp+hKey]; this
0x18000a997  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x18000a99c  lea     rcx, [rbp+var_10]
0x18000a9a0  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000a9a5  mov     rbx, [rsp+70h+arg_10]
0x18000a9ad  mov     eax, edi
0x18000a9af  add     rsp, 70h
0x18000a9b3  pop     r15
0x18000a9b5  pop     r14
0x18000a9b7  pop     r13
0x18000a9b9  pop     r12
0x18000a9bb  pop     rdi
0x18000a9bc  pop     rsi
0x18000a9bd  pop     rbp
0x18000a9be  retn
```
