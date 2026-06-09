# CredStore::InitAliasesKey(void)

- ea: `0x18001845c`
- end: `0x18001852b`
- name: `?InitAliasesKey@CredStore@@AEAAJXZ`
- size: `207`
- prototype: `__int64 __fastcall(CredStore *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005efc`
- `0x180018870`

## callees

- `0x18001845c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001847e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001847e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001850e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001850e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800184ea`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800184ea`

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
0x18001845c  mov     [rsp+arg_0], rbx
0x180018461  push    rdi
0x180018462  sub     rsp, 70h
0x180018466  lea     rbx, [rcx+28h]
0x18001846a  cmp     qword ptr [rbx], 0
0x18001846e  jz      short loc_180018477
0x180018470  xor     eax, eax
0x180018472  jmp     loc_18001851C
0x180018477  lea     rdi, [rcx+30h]
0x18001847b  mov     rcx, rdi; lpCriticalSection
0x18001847e  call    cs:__imp_EnterCriticalSection
0x180018485  nop     dword ptr [rax+rax+00h]
0x18001848a  cmp     qword ptr [rbx], 0
0x18001848e  jnz     short loc_180018509
0x180018490  mov     rax, cs:?g_pRestrictedKeySecurity@StoreSecurity@tsched@@3PEAXEA; void * tsched::StoreSecurity::g_pRestrictedKeySecurity
0x180018497  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001849e  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x1800184a7  xor     r9d, r9d; lpClass
0x1800184aa  mov     [rsp+78h+phkResult], rbx; phkResult
0x1800184af  xor     r8d, r8d; Reserved
0x1800184b2  mov     [rsp+78h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800184b7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800184be  lea     rax, [rsp+78h+SecurityAttributes]
0x1800184c3  mov     qword ptr [rsp+78h+SecurityAttributes.nLength], 18h
0x1800184cc  mov     [rsp+78h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800184d1  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x1800184d9  mov     [rsp+78h+dwOptions], 0; dwOptions
0x1800184e1  mov     qword ptr [rsp+78h+SecurityAttributes.bInheritHandle], 0
0x1800184ea  call    cs:__imp_RegCreateKeyExW
0x1800184f1  nop     dword ptr [rax+rax+00h]
0x1800184f6  mov     ebx, eax
0x1800184f8  test    eax, eax
0x1800184fa  jz      short loc_180018509
0x1800184fc  jle     short loc_18001850B
0x1800184fe  movzx   ebx, ax
0x180018501  or      ebx, 80070000h
0x180018507  jmp     short loc_18001850B
0x180018509  xor     ebx, ebx
0x18001850b  mov     rcx, rdi; lpCriticalSection
0x18001850e  call    cs:__imp_LeaveCriticalSection
0x180018515  nop     dword ptr [rax+rax+00h]
0x18001851a  mov     eax, ebx
0x18001851c  mov     rbx, [rsp+78h+arg_0]
0x180018524  add     rsp, 70h
0x180018528  pop     rdi
0x180018529  retn
```
