# CredStore::WipeoutStore(wmi::AutoRegKey &)

- ea: `0x180018444`
- end: `0x180018514`
- name: `?WipeoutStore@CredStore@@AEAAXAEAVAutoRegKey@wmi@@@Z`
- size: `208`
- prototype: `void(CredStore *__hidden this, struct wmi::AutoRegKey *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017f74`

## callees

- `0x180004fbc`
- `0x180017758`
- `0x180018444`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800184b0`
- `msvcrt!wcsstr` at `0x1800184b0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800184f9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800184f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800184e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800184e5`
- `api-ms-win-security-credentials-l1-1-0!CredEnumerateW` at `0x180018479`
- `api-ms-win-security-credentials-l1-1-0!CredEnumerateW` at `0x180018479`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x180018489`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x1800184c6`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x1800184c6`

## string_xrefs

- `0x1800184a5`: `TaskScheduler:Task:`

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
    wmi::ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>((__int64)v7);
  }
  RegCloseKey(*a2);
  RegDeleteTreeW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\CredWom");
  CredStore::OpenCredManagerKey(v6, (struct wmi::AutoRegKey *)a2);
}

```

## disassembly

```asm
0x180018444  mov     [rsp-18h+arg_10], rbx
0x180018449  mov     qword ptr [rsp-18h+Count], rcx
0x18001844e  push    rbp
0x18001844f  push    rsi
0x180018450  push    rdi
0x180018451  mov     rbp, rsp
0x180018454  sub     rsp, 40h
0x180018458  mov     rdi, rdx
0x18001845b  mov     [rbp+Count], 0
0x180018462  mov     edx, 1; Flags
0x180018467  mov     [rbp+Credential], 0
0x18001846f  lea     r9, [rbp+Credential]; Credential
0x180018473  xor     ecx, ecx; Filter
0x180018475  lea     r8, [rbp+Count]; Count
0x180018479  call    cs:__imp_CredEnumerateW
0x18001847f  test    eax, eax
0x180018481  jz      short loc_1800184E2
0x180018483  mov     rcx, [rbp+Credential]
0x180018487  xor     ebx, ebx
0x180018489  mov     rax, cs:__imp_CredFree
0x180018490  mov     [rbp+var_20], 0
0x180018494  mov     [rbp+var_18], rax
0x180018498  mov     [rbp+var_10], rcx
0x18001849c  cmp     [rbp+Count], ebx
0x18001849f  jbe     short loc_1800184D9
0x1800184a1  mov     rsi, [rcx+rbx*8]
0x1800184a5  lea     rdx, aTaskschedulerT; "TaskScheduler:Task:"
0x1800184ac  mov     rcx, [rsi+8]; Str
0x1800184b0  call    cs:__imp_wcsstr
0x1800184b6  test    rax, rax
0x1800184b9  jz      short loc_1800184CC
0x1800184bb  mov     rcx, [rsi+8]; TargetName
0x1800184bf  xor     r8d, r8d; Flags
0x1800184c2  lea     edx, [r8+2]; Type
0x1800184c6  call    cs:__imp_CredDeleteW
0x1800184cc  inc     ebx
0x1800184ce  cmp     ebx, [rbp+Count]
0x1800184d1  jnb     short loc_1800184D9
0x1800184d3  mov     rcx, [rbp+Credential]
0x1800184d7  jmp     short loc_1800184A1
0x1800184d9  lea     rcx, [rbp+var_20]
0x1800184dd  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x1800184e2  mov     rcx, [rdi]; hKey
0x1800184e5  call    cs:__imp_RegCloseKey
0x1800184eb  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800184f2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800184f9  call    cs:__imp_RegDeleteTreeW
0x1800184ff  mov     rdx, rdi; struct wmi::AutoRegKey *
0x180018502  call    ?OpenCredManagerKey@CredStore@@AEAAJAEAVAutoRegKey@wmi@@@Z; CredStore::OpenCredManagerKey(wmi::AutoRegKey &)
0x180018507  mov     rbx, [rsp+40h+arg_10]
0x18001850c  add     rsp, 40h
0x180018510  pop     rdi
0x180018511  pop     rsi
0x180018512  pop     rbp
0x180018513  retn
```
