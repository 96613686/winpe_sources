# CredStore::WipeoutStore(wmi::AutoRegKey &)

- ea: `0x1800700a0`
- end: `0x180070170`
- name: `?WipeoutStore@CredStore@@AEAAXAEAVAutoRegKey@wmi@@@Z`
- size: `208`
- prototype: `void __fastcall(CredStore *this, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006fbd0`

## callees

- `0x1800538cc`
- `0x18006f99c`
- `0x1800700a0`

## import_xrefs

- `msvcrt!wcsstr` at `0x18007010c`
- `msvcrt!wcsstr` at `0x18007010c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180070155`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180070155`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070141`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070141`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180070122`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180070122`
- `api-ms-win-security-credentials-l1-1-0!CredEnumerateW` at `0x1800700d5`
- `api-ms-win-security-credentials-l1-1-0!CredEnumerateW` at `0x1800700d5`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x1800700e5`

## string_xrefs

- `0x180070101`: `TaskScheduler:Task:`

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
    wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(v7);
  }
  RegCloseKey(*a2);
  RegDeleteTreeW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\CredWom");
  CredStore::OpenCredManagerKey(v6, a2);
}

```

## disassembly

```asm
0x1800700a0  mov     [rsp-18h+arg_10], rbx
0x1800700a5  mov     qword ptr [rsp-18h+Count], rcx
0x1800700aa  push    rbp
0x1800700ab  push    rsi
0x1800700ac  push    rdi
0x1800700ad  mov     rbp, rsp
0x1800700b0  sub     rsp, 40h
0x1800700b4  mov     rdi, rdx
0x1800700b7  mov     [rbp+Count], 0
0x1800700be  mov     edx, 1; Flags
0x1800700c3  mov     [rbp+Credential], 0
0x1800700cb  lea     r9, [rbp+Credential]; Credential
0x1800700cf  xor     ecx, ecx; Filter
0x1800700d1  lea     r8, [rbp+Count]; Count
0x1800700d5  call    cs:__imp_CredEnumerateW
0x1800700db  test    eax, eax
0x1800700dd  jz      short loc_18007013E
0x1800700df  mov     rcx, [rbp+Credential]
0x1800700e3  xor     ebx, ebx
0x1800700e5  mov     rax, cs:__imp_CredFree
0x1800700ec  mov     [rbp+var_20], 0
0x1800700f0  mov     [rbp+var_18], rax
0x1800700f4  mov     [rbp+var_10], rcx
0x1800700f8  cmp     [rbp+Count], ebx
0x1800700fb  jbe     short loc_180070135
0x1800700fd  mov     rsi, [rcx+rbx*8]
0x180070101  lea     rdx, aTaskschedulerT; "TaskScheduler:Task:"
0x180070108  mov     rcx, [rsi+8]; Str
0x18007010c  call    cs:__imp_wcsstr
0x180070112  test    rax, rax
0x180070115  jz      short loc_180070128
0x180070117  mov     rcx, [rsi+8]; TargetName
0x18007011b  xor     r8d, r8d; Flags
0x18007011e  lea     edx, [r8+2]; Type
0x180070122  call    cs:__imp_CredDeleteW
0x180070128  inc     ebx
0x18007012a  cmp     ebx, [rbp+Count]
0x18007012d  jnb     short loc_180070135
0x18007012f  mov     rcx, [rbp+Credential]
0x180070133  jmp     short loc_1800700FD
0x180070135  lea     rcx, [rbp+var_20]
0x180070139  call    ??1?$ScopeGuardImpl1@P6AJPEAX@ZPEAX@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<long (*)(void *),void *>::~ScopeGuardImpl1<long (*)(void *),void *>(void)
0x18007013e  mov     rcx, [rdi]; hKey
0x180070141  call    cs:__imp_RegCloseKey
0x180070147  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18007014e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180070155  call    cs:__imp_RegDeleteTreeW
0x18007015b  mov     rdx, rdi; struct wmi::AutoRegKey *
0x18007015e  call    ?OpenCredManagerKey@CredStore@@AEAAJAEAVAutoRegKey@wmi@@@Z; CredStore::OpenCredManagerKey(wmi::AutoRegKey &)
0x180070163  mov     rbx, [rsp+40h+arg_10]
0x180070168  add     rsp, 40h
0x18007016c  pop     rdi
0x18007016d  pop     rsi
0x18007016e  pop     rbp
0x18007016f  retn
```
