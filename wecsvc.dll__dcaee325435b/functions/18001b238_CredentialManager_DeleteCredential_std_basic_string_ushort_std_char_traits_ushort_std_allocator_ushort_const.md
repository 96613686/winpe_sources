# CredentialManager::DeleteCredential(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001b238`
- end: `0x18001b2a3`
- name: `?DeleteCredential@CredentialManager@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `107`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800159e0`

## callees

- `0x180002510`
- `0x18001b3b4`
- `0x18001b560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b259`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b259`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b29c`

## pseudocode

```c
void __fastcall CredentialManager::DeleteCredential(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  _BYTE v4[8]; // [rsp+20h] [rbp-28h] BYREF
  void (__fastcall *v5)(HANDLE); // [rsp+28h] [rbp-20h]
  void *CurrentThreadTokenAndRevertToSelf; // [rsp+30h] [rbp-18h]

  EnterCriticalSection(&CriticalSection);
  v4[0] = 0;
  v5 = RestoreAndCloseThreadToken;
  CurrentThreadTokenAndRevertToSelf = GetCurrentThreadTokenAndRevertToSelf();
  CredentialManager::DeleteCredentialInt(v3, a2);
  wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v4);
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x18001b238  mov     [rsp+arg_8], rbx
0x18001b23d  mov     [rsp+arg_0], rcx
0x18001b242  push    rdi
0x18001b243  sub     rsp, 40h
0x18001b247  mov     rbx, rdx
0x18001b24a  lea     rdi, CriticalSection
0x18001b251  mov     [rsp+48h+arg_0], rdi
0x18001b256  mov     rcx, rdi; lpCriticalSection
0x18001b259  call    cs:__imp_EnterCriticalSection
0x18001b25f  nop
0x18001b260  call    GetCurrentThreadTokenAndRevertToSelf
0x18001b265  mov     [rsp+48h+var_28], 0
0x18001b26a  lea     rdx, RestoreAndCloseThreadToken
0x18001b271  mov     [rsp+48h+var_20], rdx
0x18001b276  mov     [rsp+48h+var_18], rax
0x18001b27b  mov     rdx, rbx
0x18001b27e  call    ?DeleteCredentialInt@CredentialManager@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CredentialManager::DeleteCredentialInt(std::wstring const &)
0x18001b283  nop
0x18001b284  lea     rcx, [rsp+48h+var_28]
0x18001b289  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x18001b28e  nop
0x18001b28f  mov     rcx, rdi
0x18001b292  mov     rbx, [rsp+48h+arg_8]
0x18001b297  add     rsp, 40h
0x18001b29b  pop     rdi
0x18001b29c  jmp     cs:__imp_LeaveCriticalSection
```
