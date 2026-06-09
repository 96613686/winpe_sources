# CredStore::InitAliasesKey(void)

- ea: `0x180017454`
- end: `0x180017510`
- name: `?InitAliasesKey@CredStore@@AEAAJXZ`
- size: `188`
- prototype: `__int64 __fastcall(CredStore *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005b98`
- `0x1800177d0`

## callees

- `0x180017454`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017476`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017476`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800174fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800174fa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800174dc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800174dc`

## pseudocode

```c
__int64 __fastcall CredStore::InitAliasesKey(CredStore *this)
{
  HKEY *phkResult; // rbx
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+50h] [rbp-28h] BYREF

  phkResult = (HKEY *)((char *)this + 40);
  if ( *((_QWORD *)this + 5) )
    return 0;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *phkResult
    || (SecurityAttributes.lpSecurityDescriptor = tsched::StoreSecurity::g_pRestrictedKeySecurity,
        *(_QWORD *)&SecurityAttributes.nLength = 24,
        *(_QWORD *)&SecurityAttributes.bInheritHandle = 0,
        v4 = RegCreateKeyExW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Aliases",
               0,
               0,
               0,
               0x2001Fu,
               &SecurityAttributes,
               phkResult,
               0),
        (v5 = v4) == 0) )
  {
    v5 = 0;
  }
  else if ( v4 > 0 )
  {
    v5 = (unsigned __int16)v4 | 0x80070000;
  }
  LeaveCriticalSection(v3);
  return v5;
}

```

## disassembly

```asm
0x180017454  mov     [rsp+arg_0], rbx
0x180017459  push    rdi
0x18001745a  sub     rsp, 70h
0x18001745e  lea     rbx, [rcx+28h]
0x180017462  cmp     qword ptr [rbx], 0
0x180017466  jz      short loc_18001746F
0x180017468  xor     eax, eax
0x18001746a  jmp     loc_180017502
0x18001746f  lea     rdi, [rcx+30h]
0x180017473  mov     rcx, rdi; lpCriticalSection
0x180017476  call    cs:__imp_EnterCriticalSection
0x18001747c  cmp     qword ptr [rbx], 0
0x180017480  jnz     short loc_1800174F5
0x180017482  mov     rax, cs:?g_pRestrictedKeySecurity@StoreSecurity@tsched@@3PEAXEA; void * tsched::StoreSecurity::g_pRestrictedKeySecurity
0x180017489  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180017490  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x180017499  xor     r9d, r9d; lpClass
0x18001749c  mov     [rsp+78h+phkResult], rbx; phkResult
0x1800174a1  xor     r8d, r8d; Reserved
0x1800174a4  mov     [rsp+78h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800174a9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800174b0  lea     rax, [rsp+78h+SecurityAttributes]
0x1800174b5  mov     qword ptr [rsp+78h+SecurityAttributes.nLength], 18h
0x1800174be  mov     [rsp+78h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800174c3  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x1800174cb  mov     [rsp+78h+dwOptions], 0; dwOptions
0x1800174d3  mov     qword ptr [rsp+78h+SecurityAttributes.bInheritHandle], 0
0x1800174dc  call    cs:__imp_RegCreateKeyExW
0x1800174e2  mov     ebx, eax
0x1800174e4  test    eax, eax
0x1800174e6  jz      short loc_1800174F5
0x1800174e8  jle     short loc_1800174F7
0x1800174ea  movzx   ebx, ax
0x1800174ed  or      ebx, 80070000h
0x1800174f3  jmp     short loc_1800174F7
0x1800174f5  xor     ebx, ebx
0x1800174f7  mov     rcx, rdi; lpCriticalSection
0x1800174fa  call    cs:__imp_LeaveCriticalSection
0x180017500  mov     eax, ebx
0x180017502  mov     rbx, [rsp+78h+arg_0]
0x18001750a  add     rsp, 70h
0x18001750e  pop     rdi
0x18001750f  retn
```
