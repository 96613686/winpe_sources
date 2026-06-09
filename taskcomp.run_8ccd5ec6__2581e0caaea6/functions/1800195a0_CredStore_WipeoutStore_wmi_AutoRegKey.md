# CredStore::WipeoutStore(wmi::AutoRegKey &)

- ea: `0x1800195a0`
- end: `0x18001968f`
- name: `?WipeoutStore@CredStore@@AEAAXAEAVAutoRegKey@wmi@@@Z`
- size: `239`
- prototype: `void(CredStore *__hidden this, struct wmi::AutoRegKey *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019064`

## callees

- `0x18000525c`
- `0x1800187f0`
- `0x1800195a0`

## import_xrefs

- `msvcrt!wcsstr` at `0x180019612`
- `msvcrt!wcsstr` at `0x180019612`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001966d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001966d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019653`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019653`
- `api-ms-win-security-credentials-l1-1-0!CredEnumerateW` at `0x1800195d5`
- `api-ms-win-security-credentials-l1-1-0!CredEnumerateW` at `0x1800195d5`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x1800195eb`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18001962e`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18001962e`

## string_xrefs

- `0x180019607`: `TaskScheduler:Task:`

## pseudocode

```c
void __fastcall CredStore::WipeoutStore(CredStore *this, HKEY *a2)
{
  PCREDENTIALW *v3; // rcx
  __int64 v4; // rbx
  PCREDENTIALW v5; // rsi
  CredStore *v6; // rcx
  _BYTE v7[8]; // [rsp+20h] [rbp-20h] BYREF
  void (__stdcall *v8)(PVOID); // [rsp+28h] [rbp-18h]
  PCREDENTIALW *v9; // [rsp+30h] [rbp-10h]
  DWORD Count; // [rsp+60h] [rbp+20h] BYREF
  int v11; // [rsp+64h] [rbp+24h]
  PCREDENTIALW *Credential; // [rsp+68h] [rbp+28h] BYREF

  v11 = HIDWORD(this);
  Count = 0;
  Credential = 0;
  if ( CredEnumerateW(0, 1u, &Count, &Credential) )
  {
    v3 = Credential;
    v4 = 0;
    v7[0] = 0;
    v8 = CredFree;
    v9 = Credential;
    if ( Count )
    {
      while ( 1 )
      {
        v5 = v3[v4];
        if ( wcsstr(v5->TargetName, L"TaskScheduler:Task:") )
          CredDeleteW(v5->TargetName, 2u, 0);
        v4 = (unsigned int)(v4 + 1);
        if ( (unsigned int)v4 >= Count )
          break;
        v3 = Credential;
      }
    }
    wmi::ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>(v7);
  }
  RegCloseKey(*a2);
  RegDeleteTreeW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\CredWom");
  CredStore::OpenCredManagerKey(v6, (struct wmi::AutoRegKey *)a2);
}

```

## disassembly

```asm
0x1800195a0  mov     [rsp-18h+arg_10], rbx
0x1800195a5  mov     qword ptr [rsp-18h+Count], rcx
0x1800195aa  push    rbp
0x1800195ab  push    rsi
0x1800195ac  push    rdi
0x1800195ad  mov     rbp, rsp
0x1800195b0  sub     rsp, 40h
0x1800195b4  mov     rdi, rdx
0x1800195b7  mov     [rbp+Count], 0
0x1800195be  mov     edx, 1; Flags
0x1800195c3  mov     [rbp+Credential], 0
0x1800195cb  lea     r9, [rbp+Credential]; Credential
0x1800195cf  xor     ecx, ecx; Filter
0x1800195d1  lea     r8, [rbp+Count]; Count
0x1800195d5  call    cs:__imp_CredEnumerateW
0x1800195dc  nop     dword ptr [rax+rax+00h]
0x1800195e1  test    eax, eax
0x1800195e3  jz      short loc_180019650
0x1800195e5  mov     rcx, [rbp+Credential]
0x1800195e9  xor     ebx, ebx
0x1800195eb  mov     rax, cs:__imp_CredFree
0x1800195f2  mov     [rbp+var_20], 0
0x1800195f6  mov     [rbp+var_18], rax
0x1800195fa  mov     [rbp+var_10], rcx
0x1800195fe  cmp     [rbp+Count], ebx
0x180019601  jbe     short loc_180019647
0x180019603  mov     rsi, [rcx+rbx*8]
0x180019607  lea     rdx, aTaskschedulerT; "TaskScheduler:Task:"
0x18001960e  mov     rcx, [rsi+8]; Str
0x180019612  call    cs:__imp_wcsstr
0x180019619  nop     dword ptr [rax+rax+00h]
0x18001961e  test    rax, rax
0x180019621  jz      short loc_18001963A
0x180019623  mov     rcx, [rsi+8]; TargetName
0x180019627  xor     r8d, r8d; Flags
0x18001962a  lea     edx, [r8+2]; Type
0x18001962e  call    cs:__imp_CredDeleteW
0x180019635  nop     dword ptr [rax+rax+00h]
0x18001963a  inc     ebx
0x18001963c  cmp     ebx, [rbp+Count]
0x18001963f  jnb     short loc_180019647
0x180019641  mov     rcx, [rbp+Credential]
0x180019645  jmp     short loc_180019603
0x180019647  lea     rcx, [rbp+var_20]
0x18001964b  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x180019650  mov     rcx, [rdi]; hKey
0x180019653  call    cs:__imp_RegCloseKey
0x18001965a  nop     dword ptr [rax+rax+00h]
0x18001965f  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180019666  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001966d  call    cs:__imp_RegDeleteTreeW
0x180019674  nop     dword ptr [rax+rax+00h]
0x180019679  mov     rdx, rdi; struct wmi::AutoRegKey *
0x18001967c  call    ?OpenCredManagerKey@CredStore@@AEAAJAEAVAutoRegKey@wmi@@@Z; CredStore::OpenCredManagerKey(wmi::AutoRegKey &)
0x180019681  mov     rbx, [rsp+40h+arg_10]
0x180019686  add     rsp, 40h
0x18001968a  pop     rdi
0x18001968b  pop     rsi
0x18001968c  pop     rbp
0x18001968d  retn
```
