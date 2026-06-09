# CredStore::Upgrade(void)

- ea: `0x180073408`
- end: `0x1800735af`
- name: `?Upgrade@CredStore@@AEAAJXZ`
- size: `423`
- prototype: `__int64 __fastcall(CredStore *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180072fa0`

## callees

- `0x18002db40`
- `0x1800527d0`
- `0x180056144`
- `0x180073238`
- `0x180073408`
- `0x1800735b8`
- `0x180073944`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800734b5`
- `msvcrt!wcsstr` at `0x1800734b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800734fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800734fe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073582`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073582`
- `api-ms-win-security-credentials-l1-1-0!CredEnumerateW` at `0x180073477`
- `api-ms-win-security-credentials-l1-1-0!CredEnumerateW` at `0x180073477`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18007348d`

## string_xrefs

- `0x1800734aa`: `TaskScheduler:Task:`
- `0x18007355f`: `Completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
      CredStore::WipeoutStore(v8, &hKey);
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
0x180073408  mov     [rsp-28h+arg_18], rbx
0x18007340d  mov     [rsp-28h+Count], rcx
0x180073412  push    rbp
0x180073413  push    rsi
0x180073414  push    rdi
0x180073415  push    r14
0x180073417  push    r15
0x180073419  mov     rbp, rsp
0x18007341c  sub     rsp, 50h
0x180073420  mov     r15, cs:?g_pCommonStore@CredStore@@0PEAV1@EA; CredStore * CredStore::g_pCommonStore
0x180073427  mov     [rbp+hKey], 0
0x18007342f  lea     rdx, [rbp+hKey]
0x180073433  call    ?StartUpgrade@CredStore@@AEAA?AW4UpgradeStages@1@AEAVAutoRegKey@wmi@@@Z; CredStore::StartUpgrade(wmi::AutoRegKey &)
0x180073438  mov     edi, eax
0x18007343a  cmp     eax, 3
0x18007343d  jnz     short loc_180073446
0x18007343f  xor     ebx, ebx
0x180073441  jmp     loc_18007358F
0x180073446  cmp     edi, 1
0x180073449  jz      short loc_180073459
0x18007344b  mov     ebx, 80004005h
0x180073450  cmp     edi, 2
0x180073453  jnz     loc_18007358F
0x180073459  mov     dword ptr [rbp+Count], 0
0x180073460  mov     [rbp+Credential], 0
0x180073468  lea     r9, [rbp+Credential]; Credential
0x18007346c  lea     r8, [rbp+Count]; Count
0x180073470  mov     edx, 1; Flags
0x180073475  xor     ecx, ecx; Filter
0x180073477  call    cs:__imp_CredEnumerateW
0x18007347e  nop     dword ptr [rax+rax+00h]
0x180073483  test    eax, eax
0x180073485  jz      short loc_1800734FE
0x180073487  xor     ebx, ebx
0x180073489  mov     rcx, [rbp+Credential]
0x18007348d  mov     rax, cs:__imp_CredFree
0x180073494  mov     [rbp+var_20], bl
0x180073497  mov     [rbp+var_18], rax
0x18007349b  mov     [rbp+var_10], rcx
0x18007349f  xor     esi, esi
0x1800734a1  cmp     esi, dword ptr [rbp+Count]
0x1800734a4  jnb     short loc_1800734F3
0x1800734a6  mov     r14, [rcx+rsi*8]
0x1800734aa  lea     rdx, aTaskschedulerT; "TaskScheduler:Task:"
0x1800734b1  mov     rcx, [r14+8]; Str
0x1800734b5  call    cs:__imp_wcsstr
0x1800734bc  nop     dword ptr [rax+rax+00h]
0x1800734c1  test    rax, rax
0x1800734c4  jz      short loc_1800734E6
0x1800734c6  mov     rcx, [r14+48h]
0x1800734ca  mov     [rsp+50h+lpData], rcx; unsigned __int16 *
0x1800734cf  mov     r9, [r14+8]; unsigned __int16 *
0x1800734d3  mov     r8, rax; unsigned __int16 *
0x1800734d6  mov     rdx, [rbp+hKey]; hKey
0x1800734da  mov     rcx, r15; lpCriticalSection
0x1800734dd  call    ?UpgradeCred@CredStore@@AEAAHPEAUHKEY__@@PEBG11@Z; CredStore::UpgradeCred(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800734e2  test    eax, eax
0x1800734e4  jz      short loc_1800734EE
0x1800734e6  inc     esi
0x1800734e8  mov     rcx, [rbp+Credential]
0x1800734ec  jmp     short loc_1800734A1
0x1800734ee  mov     ebx, 8000FFFFh
0x1800734f3  lea     rcx, [rbp+var_20]
0x1800734f7  call    ??1?$ScopeGuardImpl1@P6AJPEAX@ZPEAX@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(void)
0x1800734fc  jmp     short loc_180073524
0x1800734fe  call    cs:__imp_GetLastError
0x180073505  nop     dword ptr [rax+rax+00h]
0x18007350a  mov     ebx, eax
0x18007350c  cmp     eax, 490h
0x180073511  jnz     short loc_180073517
0x180073513  xor     ebx, ebx
0x180073515  jmp     short loc_18007354C
0x180073517  test    eax, eax
0x180073519  jle     short loc_180073524
0x18007351b  movzx   ebx, ax
0x18007351e  or      ebx, 80070000h
0x180073524  test    ebx, ebx
0x180073526  jns     short loc_18007354C
0x180073528  lea     rdx, [rbp+hKey]; struct wmi::AutoRegKey *
0x18007352c  call    ?WipeoutStore@CredStore@@AEAAXAEAVAutoRegKey@wmi@@@Z; CredStore::WipeoutStore(wmi::AutoRegKey &)
0x180073531  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x180073538  test    rcx, rcx
0x18007353b  jz      short loc_18007354C
0x18007353d  mov     r8d, ebx; unsigned int
0x180073540  lea     rdx, VISTA_BETA2_CREDSTORE_UPGRADE_FAILED; struct _EVENT_DESCRIPTOR *
0x180073547  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x18007354c  cmp     edi, 1
0x18007354f  jnz     short loc_18007355A
0x180073551  lea     rax, Data; "Stage_One"
0x180073558  jmp     short loc_180073566
0x18007355a  cmp     edi, 2
0x18007355d  jnz     short loc_18007358F
0x18007355f  lea     rax, aCompleted; "Completed"
0x180073566  mov     [rsp+50h+cbData], 14h; cbData
0x18007356e  mov     [rsp+50h+lpData], rax; lpData
0x180073573  mov     r9d, 1; dwType
0x180073579  xor     r8d, r8d; Reserved
0x18007357c  xor     edx, edx; lpValueName
0x18007357e  mov     rcx, [rbp+hKey]; hKey
0x180073582  call    cs:__imp_RegSetValueExW
0x180073589  nop     dword ptr [rax+rax+00h]
0x18007358e  nop
0x18007358f  lea     rcx, [rbp+hKey]; this
0x180073593  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180073598  mov     eax, ebx
0x18007359a  mov     rbx, [rsp+50h+arg_18]
0x1800735a2  add     rsp, 50h
0x1800735a6  pop     r15
0x1800735a8  pop     r14
0x1800735aa  pop     rdi
0x1800735ab  pop     rsi
0x1800735ac  pop     rbp
0x1800735ad  retn
```
