# CredStore::Upgrade(void)

- ea: `0x180017f74`
- end: `0x180018102`
- name: `?Upgrade@CredStore@@AEAAJXZ`
- size: `398`
- prototype: `__int64 __fastcall(CredStore *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001733c`

## callees

- `0x180004ec0`
- `0x180004fbc`
- `0x1800055d0`
- `0x180017ab4`
- `0x180017f74`
- `0x180018108`
- `0x180018444`

## import_xrefs

- `msvcrt!wcsstr` at `0x18001801b`
- `msvcrt!wcsstr` at `0x18001801b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001805e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001805e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800180dc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800180dc`
- `api-ms-win-security-credentials-l1-1-0!CredEnumerateW` at `0x180017fe3`
- `api-ms-win-security-credentials-l1-1-0!CredEnumerateW` at `0x180017fe3`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x180017ff3`

## string_xrefs

- `0x180018010`: `TaskScheduler:Task:`
- `0x1800180b9`: `Completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CredStore::Upgrade(CredStore *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // r15
  int started; // edi
  unsigned int v3; // ebx
  PCREDENTIALW *v4; // rcx
  __int64 v5; // rsi
  PCREDENTIALW v6; // r14
  wchar_t *v7; // rax
  CredStore *v8; // rcx
  signed int LastError; // eax
  void *v10; // r9
  const wchar_t *lpData; // rax
  _BYTE v13[8]; // [rsp+30h] [rbp-20h] BYREF
  void (__stdcall *v14)(PVOID); // [rsp+38h] [rbp-18h]
  PCREDENTIALW *v15; // [rsp+40h] [rbp-10h]
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
      v13[0] = 0;
      v14 = CredFree;
      v15 = Credential;
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
      wmi::ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>((__int64)v13);
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
          lpData = L"Stage_One";
        else
          lpData = L"Completed";
        RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)lpData, 0x14u);
        goto LABEL_24;
      }
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( (v3 & 0x80000000) != 0 )
    {
      CredStore::WipeoutStore(v8, &hKey);
      if ( g_pEventManager )
        EventManager::EvtReport(g_pEventManager, &VISTA_BETA2_CREDSTORE_UPGRADE_FAILED, v3, v10);
    }
    goto LABEL_20;
  }
LABEL_24:
  wmi::AutoRegKey::Close(&hKey);
  return v3;
}

```

## disassembly

```asm
0x180017f74  mov     [rsp-28h+arg_18], rbx
0x180017f79  mov     [rsp-28h+Count], rcx
0x180017f7e  push    rbp
0x180017f7f  push    rsi
0x180017f80  push    rdi
0x180017f81  push    r14
0x180017f83  push    r15
0x180017f85  mov     rbp, rsp
0x180017f88  sub     rsp, 50h
0x180017f8c  mov     r15, cs:?g_pCommonStore@CredStore@@0PEAV1@EA; CredStore * CredStore::g_pCommonStore
0x180017f93  mov     [rbp+hKey], 0
0x180017f9b  lea     rdx, [rbp+hKey]
0x180017f9f  call    ?StartUpgrade@CredStore@@AEAA?AW4UpgradeStages@1@AEAVAutoRegKey@wmi@@@Z; CredStore::StartUpgrade(wmi::AutoRegKey &)
0x180017fa4  mov     edi, eax
0x180017fa6  cmp     eax, 3
0x180017fa9  jnz     short loc_180017FB2
0x180017fab  xor     ebx, ebx
0x180017fad  jmp     loc_1800180E3
0x180017fb2  cmp     edi, 1
0x180017fb5  jz      short loc_180017FC5
0x180017fb7  mov     ebx, 80004005h
0x180017fbc  cmp     edi, 2
0x180017fbf  jnz     loc_1800180E3
0x180017fc5  mov     dword ptr [rbp+Count], 0
0x180017fcc  mov     [rbp+Credential], 0
0x180017fd4  lea     r9, [rbp+Credential]; Credential
0x180017fd8  lea     r8, [rbp+Count]; Count
0x180017fdc  mov     edx, 1; Flags
0x180017fe1  xor     ecx, ecx; Filter
0x180017fe3  call    cs:__imp_CredEnumerateW
0x180017fe9  test    eax, eax
0x180017feb  jz      short loc_18001805E
0x180017fed  xor     ebx, ebx
0x180017fef  mov     rcx, [rbp+Credential]
0x180017ff3  mov     rax, cs:__imp_CredFree
0x180017ffa  mov     [rbp+var_20], bl
0x180017ffd  mov     [rbp+var_18], rax
0x180018001  mov     [rbp+var_10], rcx
0x180018005  xor     esi, esi
0x180018007  cmp     esi, dword ptr [rbp+Count]
0x18001800a  jnb     short loc_180018053
0x18001800c  mov     r14, [rcx+rsi*8]
0x180018010  lea     rdx, aTaskschedulerT; "TaskScheduler:Task:"
0x180018017  mov     rcx, [r14+8]; Str
0x18001801b  call    cs:__imp_wcsstr
0x180018021  test    rax, rax
0x180018024  jz      short loc_180018046
0x180018026  mov     rcx, [r14+48h]
0x18001802a  mov     [rsp+50h+lpData], rcx; unsigned __int16 *
0x18001802f  mov     r9, [r14+8]; unsigned __int16 *
0x180018033  mov     r8, rax; unsigned __int16 *
0x180018036  mov     rdx, [rbp+hKey]; hKey
0x18001803a  mov     rcx, r15; lpCriticalSection
0x18001803d  call    ?UpgradeCred@CredStore@@AEAAHPEAUHKEY__@@PEBG11@Z; CredStore::UpgradeCred(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180018042  test    eax, eax
0x180018044  jz      short loc_18001804E
0x180018046  inc     esi
0x180018048  mov     rcx, [rbp+Credential]
0x18001804c  jmp     short loc_180018007
0x18001804e  mov     ebx, 8000FFFFh
0x180018053  lea     rcx, [rbp+var_20]
0x180018057  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x18001805c  jmp     short loc_18001807E
0x18001805e  call    cs:__imp_GetLastError
0x180018064  mov     ebx, eax
0x180018066  cmp     eax, 490h
0x18001806b  jnz     short loc_180018071
0x18001806d  xor     ebx, ebx
0x18001806f  jmp     short loc_1800180A6
0x180018071  test    eax, eax
0x180018073  jle     short loc_18001807E
0x180018075  movzx   ebx, ax
0x180018078  or      ebx, 80070000h
0x18001807e  test    ebx, ebx
0x180018080  jns     short loc_1800180A6
0x180018082  lea     rdx, [rbp+hKey]; struct wmi::AutoRegKey *
0x180018086  call    ?WipeoutStore@CredStore@@AEAAXAEAVAutoRegKey@wmi@@@Z; CredStore::WipeoutStore(wmi::AutoRegKey &)
0x18001808b  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x180018092  test    rcx, rcx
0x180018095  jz      short loc_1800180A6
0x180018097  mov     r8d, ebx; unsigned int
0x18001809a  lea     rdx, VISTA_BETA2_CREDSTORE_UPGRADE_FAILED; struct _EVENT_DESCRIPTOR *
0x1800180a1  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x1800180a6  cmp     edi, 1
0x1800180a9  jnz     short loc_1800180B4
0x1800180ab  lea     rax, aStageOne; "Stage_One"
0x1800180b2  jmp     short loc_1800180C0
0x1800180b4  cmp     edi, 2
0x1800180b7  jnz     short loc_1800180E3
0x1800180b9  lea     rax, aCompleted; "Completed"
0x1800180c0  mov     [rsp+50h+cbData], 14h; cbData
0x1800180c8  mov     [rsp+50h+lpData], rax; lpData
0x1800180cd  mov     r9d, 1; dwType
0x1800180d3  xor     r8d, r8d; Reserved
0x1800180d6  xor     edx, edx; lpValueName
0x1800180d8  mov     rcx, [rbp+hKey]; hKey
0x1800180dc  call    cs:__imp_RegSetValueExW
0x1800180e2  nop
0x1800180e3  lea     rcx, [rbp+hKey]; this
0x1800180e7  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800180ec  mov     eax, ebx
0x1800180ee  mov     rbx, [rsp+50h+arg_18]
0x1800180f6  add     rsp, 50h
0x1800180fa  pop     r15
0x1800180fc  pop     r14
0x1800180fe  pop     rdi
0x1800180ff  pop     rsi
0x180018100  pop     rbp
0x180018101  retn
```
