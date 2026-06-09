# CredStore::Upgrade(void)

- ea: `0x180019064`
- end: `0x18001920b`
- name: `?Upgrade@CredStore@@AEAAJXZ`
- size: `423`
- prototype: `__int64 __fastcall(CredStore *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001831c`

## callees

- `0x180005150`
- `0x18000525c`
- `0x180005894`
- `0x180018b84`
- `0x180019064`
- `0x180019214`
- `0x1800195a0`

## import_xrefs

- `msvcrt!wcsstr` at `0x180019111`
- `msvcrt!wcsstr` at `0x180019111`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001915a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001915a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800191de`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800191de`
- `api-ms-win-security-credentials-l1-1-0!CredEnumerateW` at `0x1800190d3`
- `api-ms-win-security-credentials-l1-1-0!CredEnumerateW` at `0x1800190d3`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x1800190e9`

## string_xrefs

- `0x180019106`: `TaskScheduler:Task:`
- `0x1800191bb`: `Completed`

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
      wmi::ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>(v14);
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
0x180019064  mov     [rsp-28h+arg_18], rbx
0x180019069  mov     [rsp-28h+Count], rcx
0x18001906e  push    rbp
0x18001906f  push    rsi
0x180019070  push    rdi
0x180019071  push    r14
0x180019073  push    r15
0x180019075  mov     rbp, rsp
0x180019078  sub     rsp, 50h
0x18001907c  mov     r15, cs:?g_pCommonStore@CredStore@@0PEAV1@EA; CredStore * CredStore::g_pCommonStore
0x180019083  mov     [rbp+hKey], 0
0x18001908b  lea     rdx, [rbp+hKey]
0x18001908f  call    ?StartUpgrade@CredStore@@AEAA?AW4UpgradeStages@1@AEAVAutoRegKey@wmi@@@Z; CredStore::StartUpgrade(wmi::AutoRegKey &)
0x180019094  mov     edi, eax
0x180019096  cmp     eax, 3
0x180019099  jnz     short loc_1800190A2
0x18001909b  xor     ebx, ebx
0x18001909d  jmp     loc_1800191EB
0x1800190a2  cmp     edi, 1
0x1800190a5  jz      short loc_1800190B5
0x1800190a7  mov     ebx, 80004005h
0x1800190ac  cmp     edi, 2
0x1800190af  jnz     loc_1800191EB
0x1800190b5  mov     dword ptr [rbp+Count], 0
0x1800190bc  mov     [rbp+Credential], 0
0x1800190c4  lea     r9, [rbp+Credential]; Credential
0x1800190c8  lea     r8, [rbp+Count]; Count
0x1800190cc  mov     edx, 1; Flags
0x1800190d1  xor     ecx, ecx; Filter
0x1800190d3  call    cs:__imp_CredEnumerateW
0x1800190da  nop     dword ptr [rax+rax+00h]
0x1800190df  test    eax, eax
0x1800190e1  jz      short loc_18001915A
0x1800190e3  xor     ebx, ebx
0x1800190e5  mov     rcx, [rbp+Credential]
0x1800190e9  mov     rax, cs:__imp_CredFree
0x1800190f0  mov     [rbp+var_20], bl
0x1800190f3  mov     [rbp+var_18], rax
0x1800190f7  mov     [rbp+var_10], rcx
0x1800190fb  xor     esi, esi
0x1800190fd  cmp     esi, dword ptr [rbp+Count]
0x180019100  jnb     short loc_18001914F
0x180019102  mov     r14, [rcx+rsi*8]
0x180019106  lea     rdx, aTaskschedulerT; "TaskScheduler:Task:"
0x18001910d  mov     rcx, [r14+8]; Str
0x180019111  call    cs:__imp_wcsstr
0x180019118  nop     dword ptr [rax+rax+00h]
0x18001911d  test    rax, rax
0x180019120  jz      short loc_180019142
0x180019122  mov     rcx, [r14+48h]
0x180019126  mov     [rsp+50h+lpData], rcx; unsigned __int16 *
0x18001912b  mov     r9, [r14+8]; unsigned __int16 *
0x18001912f  mov     r8, rax; unsigned __int16 *
0x180019132  mov     rdx, [rbp+hKey]; hKey
0x180019136  mov     rcx, r15; lpCriticalSection
0x180019139  call    ?UpgradeCred@CredStore@@AEAAHPEAUHKEY__@@PEBG11@Z; CredStore::UpgradeCred(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001913e  test    eax, eax
0x180019140  jz      short loc_18001914A
0x180019142  inc     esi
0x180019144  mov     rcx, [rbp+Credential]
0x180019148  jmp     short loc_1800190FD
0x18001914a  mov     ebx, 8000FFFFh
0x18001914f  lea     rcx, [rbp+var_20]
0x180019153  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x180019158  jmp     short loc_180019180
0x18001915a  call    cs:__imp_GetLastError
0x180019161  nop     dword ptr [rax+rax+00h]
0x180019166  mov     ebx, eax
0x180019168  cmp     eax, 490h
0x18001916d  jnz     short loc_180019173
0x18001916f  xor     ebx, ebx
0x180019171  jmp     short loc_1800191A8
0x180019173  test    eax, eax
0x180019175  jle     short loc_180019180
0x180019177  movzx   ebx, ax
0x18001917a  or      ebx, 80070000h
0x180019180  test    ebx, ebx
0x180019182  jns     short loc_1800191A8
0x180019184  lea     rdx, [rbp+hKey]; struct wmi::AutoRegKey *
0x180019188  call    ?WipeoutStore@CredStore@@AEAAXAEAVAutoRegKey@wmi@@@Z; CredStore::WipeoutStore(wmi::AutoRegKey &)
0x18001918d  mov     rcx, cs:?g_pEventManager@@3PEAVEventManager@@EA; this
0x180019194  test    rcx, rcx
0x180019197  jz      short loc_1800191A8
0x180019199  mov     r8d, ebx; unsigned int
0x18001919c  lea     rdx, VISTA_BETA2_CREDSTORE_UPGRADE_FAILED; struct _EVENT_DESCRIPTOR *
0x1800191a3  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)
0x1800191a8  cmp     edi, 1
0x1800191ab  jnz     short loc_1800191B6
0x1800191ad  lea     rax, aStageOne; "Stage_One"
0x1800191b4  jmp     short loc_1800191C2
0x1800191b6  cmp     edi, 2
0x1800191b9  jnz     short loc_1800191EB
0x1800191bb  lea     rax, aCompleted; "Completed"
0x1800191c2  mov     [rsp+50h+cbData], 14h; cbData
0x1800191ca  mov     [rsp+50h+lpData], rax; lpData
0x1800191cf  mov     r9d, 1; dwType
0x1800191d5  xor     r8d, r8d; Reserved
0x1800191d8  xor     edx, edx; lpValueName
0x1800191da  mov     rcx, [rbp+hKey]; hKey
0x1800191de  call    cs:__imp_RegSetValueExW
0x1800191e5  nop     dword ptr [rax+rax+00h]
0x1800191ea  nop
0x1800191eb  lea     rcx, [rbp+hKey]; this
0x1800191ef  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800191f4  mov     eax, ebx
0x1800191f6  mov     rbx, [rsp+50h+arg_18]
0x1800191fe  add     rsp, 50h
0x180019202  pop     r15
0x180019204  pop     r14
0x180019206  pop     rdi
0x180019207  pop     rsi
0x180019208  pop     rbp
0x180019209  retn
```
