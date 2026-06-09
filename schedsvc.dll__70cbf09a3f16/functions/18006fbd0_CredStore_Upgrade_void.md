# CredStore::Upgrade(void)

- ea: `0x18006fbd0`
- end: `0x18006fd5e`
- name: `?Upgrade@CredStore@@AEAAJXZ`
- size: `398`
- prototype: `__int64 __fastcall(CredStore *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006f7c0`

## callees

- `0x180021300`
- `0x18004fea8`
- `0x1800538cc`
- `0x18006fa14`
- `0x18006fbd0`
- `0x18006fd64`
- `0x1800700a0`

## import_xrefs

- `msvcrt!wcsstr` at `0x18006fc77`
- `msvcrt!wcsstr` at `0x18006fc77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fcba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fcba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006fd38`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006fd38`
- `api-ms-win-security-credentials-l1-1-0!CredEnumerateW` at `0x18006fc3f`
- `api-ms-win-security-credentials-l1-1-0!CredEnumerateW` at `0x18006fc3f`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18006fc4f`

## string_xrefs

- `0x18006fc6c`: `TaskScheduler:Task:`
- `0x18006fd15`: `Completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CredStore::Upgrade(CredStore *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // r15
  int started; // edi
  int v3; // ebx
  PCREDENTIALW *v4; // rcx
  __int64 v5; // rsi
  PCREDENTIALW v6; // r14
  wchar_t *v7; // rax
  CredStore *v8; // rcx
  signed int LastError; // eax
  void *v10; // r9
  const wchar_t *v11; // rax
  BYTE *lpData; // [rsp+20h] [rbp-30h]
  _BYTE v14[8]; // [rsp+30h] [rbp-20h] BYREF
  void (__stdcall *v15)(PVOID); // [rsp+38h] [rbp-18h]
  PCREDENTIALW *v16; // [rsp+40h] [rbp-10h]
  CredStore *Count; // [rsp+80h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF
  PCREDENTIALW *Credential; // [rsp+90h] [rbp+40h] BYREF

  Count = this;
  v1 = CredStore::g_pCommonStore;
  hKey = 0;
  started = CredStore::StartUpgrade(this, &hKey);
  if ( started == 3 )
  {
    v3 = 0;
    goto LABEL_24;
  }
  if ( started == 1 || (v3 = -2147467259, started == 2) )
  {
    LODWORD(Count) = 0;
    Credential = 0;
    if ( CredEnumerateW(0, 1u, (DWORD *)&Count, &Credential) )
    {
      v3 = 0;
      v4 = Credential;
      v14[0] = 0;
      v15 = CredFree;
      v16 = Credential;
      v5 = 0;
      while ( (unsigned int)v5 < (unsigned int)Count )
      {
        v6 = v4[v5];
        v7 = wcsstr(v6->TargetName, L"TaskScheduler:Task:");
        if ( v7 && !(unsigned int)CredStore::UpgradeCred(v1, hKey, v7, v6->TargetName, v6->UserName) )
        {
          v3 = -2147418113;
          break;
        }
        v5 = (unsigned int)(v5 + 1);
        v4 = Credential;
      }
      wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(v14);
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError == 1168 )
      {
        v3 = 0;
LABEL_20:
        if ( started == 1 )
          v11 = L"Stage_One";
        else
          v11 = L"Completed";
        RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)v11, 0x14u);
        goto LABEL_24;
      }
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v3 < 0 )
    {
      CredStore::WipeoutStore(v8, (struct wmi::AutoRegKey *)&hKey);
      if ( g_pEventManager )
        EventManager::EvtReport(
          g_pEventManager,
          &VISTA_BETA2_CREDSTORE_UPGRADE_FAILED,
          v3,
          v10,
          (const struct _GUID *)lpData);
    }
    goto LABEL_20;
  }
LABEL_24:
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18006fbd0  mov     [rsp-28h+arg_18], rbx
0x18006fbd5  mov     [rsp-28h+Count], rcx
0x18006fbda  push    rbp
0x18006fbdb  push    rsi
0x18006fbdc  push    rdi
0x18006fbdd  push    r14
0x18006fbdf  push    r15
0x18006fbe1  mov     rbp, rsp
0x18006fbe4  sub     rsp, 50h
0x18006fbe8  mov     r15, cs:?g_pCommonStore@CredStore@@0PEAV1@EA; CredStore * CredStore::g_pCommonStore
0x18006fbef  mov     [rbp+hKey], 0
0x18006fbf7  lea     rdx, [rbp+hKey]
0x18006fbfb  call    ?StartUpgrade@CredStore@@AEAA?AW4UpgradeStages@1@AEAVAutoRegKey@wmi@@@Z; CredStore::StartUpgrade(wmi::AutoRegKey &)
0x18006fc00  mov     edi, eax
0x18006fc02  cmp     eax, 3
0x18006fc05  jnz     short loc_18006FC0E
0x18006fc07  xor     ebx, ebx
0x18006fc09  jmp     loc_18006FD3F
0x18006fc0e  cmp     edi, 1
0x18006fc11  jz      short loc_18006FC21
0x18006fc13  mov     ebx, 80004005h
0x18006fc18  cmp     edi, 2
0x18006fc1b  jnz     loc_18006FD3F
0x18006fc21  mov     dword ptr [rbp+Count], 0
0x18006fc28  mov     [rbp+Credential], 0
0x18006fc30  lea     r9, [rbp+Credential]; Credential
0x18006fc34  lea     r8, [rbp+Count]; Count
0x18006fc38  mov     edx, 1; Flags
0x18006fc3d  xor     ecx, ecx; Filter
0x18006fc3f  call    cs:__imp_CredEnumerateW
0x18006fc45  test    eax, eax
0x18006fc47  jz      short loc_18006FCBA
0x18006fc49  xor     ebx, ebx
0x18006fc4b  mov     rcx, [rbp+Credential]
0x18006fc4f  mov     rax, cs:__imp_CredFree
0x18006fc56  mov     [rbp+var_20], bl
0x18006fc59  mov     [rbp+var_18], rax
0x18006fc5d  mov     [rbp+var_10], rcx
0x18006fc61  xor     esi, esi
0x18006fc63  cmp     esi, dword ptr [rbp+Count]
0x18006fc66  jnb     short loc_18006FCAF
0x18006fc68  mov     r14, [rcx+rsi*8]
0x18006fc6c  lea     rdx, aTaskschedulerT; "TaskScheduler:Task:"
0x18006fc73  mov     rcx, [r14+8]; Str
0x18006fc77  call    cs:__imp_wcsstr
0x18006fc7d  test    rax, rax
0x18006fc80  jz      short loc_18006FCA2
0x18006fc82  mov     rcx, [r14+48h]
0x18006fc86  mov     [rsp+50h+lpData], rcx; unsigned __int16 *
0x18006fc8b  mov     r9, [r14+8]; unsigned __int16 *
0x18006fc8f  mov     r8, rax; unsigned __int16 *
0x18006fc92  mov     rdx, [rbp+hKey]; hKey
0x18006fc96  mov     rcx, r15; lpCriticalSection
0x18006fc99  call    ?UpgradeCred@CredStore@@AEAAHPEAUHKEY__@@PEBG11@Z; CredStore::UpgradeCred(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18006fc9e  test    eax, eax
0x18006fca0  jz      short loc_18006FCAA
0x18006fca2  inc     esi
0x18006fca4  mov     rcx, [rbp+Credential]
0x18006fca8  jmp     short loc_18006FC63
0x18006fcaa  mov     ebx, 8000FFFFh
0x18006fcaf  lea     rcx, [rbp+var_20]
0x18006fcb3  call    ??1?$ScopeGuardImpl1@P6AJPEAX@ZPEAX@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(void)
0x18006fcb8  jmp     short loc_18006FCDA
0x18006fcba  call    cs:__imp_GetLastError
0x18006fcc0  mov     ebx, eax
0x18006fcc2  cmp     eax, 490h
0x18006fcc7  jnz     short loc_18006FCCD
0x18006fcc9  xor     ebx, ebx
0x18006fccb  jmp     short loc_18006FD02
0x18006fccd  test    eax, eax
0x18006fccf  jle     short loc_18006FCDA
0x18006fcd1  movzx   ebx, ax
0x18006fcd4  or      ebx, 80070000h
0x18006fcda  test    ebx, ebx
0x18006fcdc  jns     short loc_18006FD02
0x18006fcde  lea     rdx, [rbp+hKey]; struct wmi::AutoRegKey *
0x18006fce2  call    ?WipeoutStore@CredStore@@AEAAXAEAVAutoRegKey@wmi@@@Z; CredStore::WipeoutStore(wmi::AutoRegKey &)
0x18006fce7  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x18006fcee  test    rcx, rcx
0x18006fcf1  jz      short loc_18006FD02
0x18006fcf3  mov     r8d, ebx; unsigned int
0x18006fcf6  lea     rdx, VISTA_BETA2_CREDSTORE_UPGRADE_FAILED; struct _EVENT_DESCRIPTOR *
0x18006fcfd  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x18006fd02  cmp     edi, 1
0x18006fd05  jnz     short loc_18006FD10
0x18006fd07  lea     rax, Data; "Stage_One"
0x18006fd0e  jmp     short loc_18006FD1C
0x18006fd10  cmp     edi, 2
0x18006fd13  jnz     short loc_18006FD3F
0x18006fd15  lea     rax, aCompleted; "Completed"
0x18006fd1c  mov     [rsp+50h+cbData], 14h; cbData
0x18006fd24  mov     [rsp+50h+lpData], rax; lpData
0x18006fd29  mov     r9d, 1; dwType
0x18006fd2f  xor     r8d, r8d; Reserved
0x18006fd32  xor     edx, edx; lpValueName
0x18006fd34  mov     rcx, [rbp+hKey]; hKey
0x18006fd38  call    cs:__imp_RegSetValueExW
0x18006fd3e  nop
0x18006fd3f  lea     rcx, [rbp+hKey]; this
0x18006fd43  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18006fd48  mov     eax, ebx
0x18006fd4a  mov     rbx, [rsp+50h+arg_18]
0x18006fd52  add     rsp, 50h
0x18006fd56  pop     r15
0x18006fd58  pop     r14
0x18006fd5a  pop     rdi
0x18006fd5b  pop     rsi
0x18006fd5c  pop     rbp
0x18006fd5d  retn
```
