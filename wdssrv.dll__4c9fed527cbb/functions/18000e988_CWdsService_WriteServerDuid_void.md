# CWdsService::WriteServerDuid(void)

- ea: `0x18000e988`
- end: `0x18000eaab`
- name: `?WriteServerDuid@CWdsService@@AEAAKXZ`
- size: `291`
- prototype: `unsigned int __fastcall(CWdsService *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c3b4`

## callees

- `0x18000e988`
- `0x18000f0dc`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000ea8c`
- `KERNEL32!LeaveCriticalSection` at `0x18000ea8c`
- `KERNEL32!EnterCriticalSection` at `0x18000e9a4`
- `KERNEL32!EnterCriticalSection` at `0x18000e9a4`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ea10`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ea10`
- `ADVAPI32!RegCloseKey` at `0x18000e9e3`
- `ADVAPI32!RegCloseKey` at `0x18000ea77`
- `ADVAPI32!RegCloseKey` at `0x18000e9e3`
- `ADVAPI32!RegCloseKey` at `0x18000ea77`
- `WdsServerCommonLib!?SetValue@CRegKey@@QEAAKPEBGKPEBXK@Z` at `0x18000ea52`
- `WdsServerCommonLib!?SetValue@CRegKey@@QEAAKPEBGKPEBXK@Z` at `0x18000ea52`

## string_xrefs

- `0x18000ea02`: `System\CurrentControlSet\Services\WDSServer\Parameters`

## pseudocode

```c
__int64 __fastcall CWdsService::WriteServerDuid(CWdsService *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  __int64 v3; // rdx
  __int64 v4; // r8
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 67320);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1683);
  hKey = 0;
  if ( !*((_DWORD *)this + 16840) )
  {
    v5 = 13;
    if ( (unsigned int)ElValidateWin32_0(13, v3, v4, 1285) )
      goto LABEL_7;
    if ( hKey )
      RegCloseKey(hKey);
  }
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WDSServer\\Parameters",
         0,
         0x20106u,
         &hKey);
  if ( !(unsigned int)ElValidateWin32_0(v5, v6, v7, 1289) )
  {
    v5 = CRegKey::SetValue(
           (CRegKey *)&hKey,
           L"ServerDuid",
           3u,
           *((const void **)this + 8421),
           *((_DWORD *)this + 16840));
    ElValidateWin32_0(v5, v8, v9, 1295);
  }
LABEL_7:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  LeaveCriticalSection(v1);
  return v5;
}

```

## disassembly

```asm
0x18000e988  mov     [rsp+arg_8], rbx
0x18000e98d  mov     [rsp+arg_10], rsi
0x18000e992  push    rdi
0x18000e993  sub     rsp, 30h
0x18000e997  lea     rsi, [rcx+106F8h]
0x18000e99e  mov     rdi, rcx
0x18000e9a1  mov     rcx, rsi; lpCriticalSection
0x18000e9a4  call    cs:__imp_EnterCriticalSection
0x18000e9ab  nop     dword ptr [rax+rax+00h]
0x18000e9b0  and     [rsp+38h+hKey], 0
0x18000e9b6  cmp     dword ptr [rdi+10720h], 0
0x18000e9bd  jnz     short loc_18000E9EF
0x18000e9bf  mov     ebx, 0Dh
0x18000e9c4  mov     r9d, 505h
0x18000e9ca  mov     ecx, ebx
0x18000e9cc  call    ElValidateWin32_0
0x18000e9d1  test    eax, eax
0x18000e9d3  jnz     loc_18000EA6D
0x18000e9d9  mov     rcx, [rsp+38h+hKey]; hKey
0x18000e9de  test    rcx, rcx
0x18000e9e1  jz      short loc_18000E9EF
0x18000e9e3  call    cs:__imp_RegCloseKey
0x18000e9ea  nop     dword ptr [rax+rax+00h]
0x18000e9ef  lea     rax, [rsp+38h+hKey]
0x18000e9f4  mov     r9d, 20106h; samDesired
0x18000e9fa  xor     r8d, r8d; ulOptions
0x18000e9fd  mov     [rsp+38h+phkResult], rax; phkResult
0x18000ea02  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x18000ea09  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ea10  call    cs:__imp_RegOpenKeyExW
0x18000ea17  nop     dword ptr [rax+rax+00h]
0x18000ea1c  mov     ecx, eax
0x18000ea1e  mov     r9d, 509h
0x18000ea24  mov     ebx, eax
0x18000ea26  call    ElValidateWin32_0
0x18000ea2b  test    eax, eax
0x18000ea2d  jnz     short loc_18000EA6D
0x18000ea2f  mov     eax, [rdi+10720h]
0x18000ea35  lea     rdx, ValueName; "ServerDuid"
0x18000ea3c  mov     r9, [rdi+10728h]
0x18000ea43  lea     rcx, [rsp+38h+hKey]
0x18000ea48  mov     r8d, 3
0x18000ea4e  mov     dword ptr [rsp+38h+phkResult], eax
0x18000ea52  call    cs:__imp_?SetValue@CRegKey@@QEAAKPEBGKPEBXK@Z; CRegKey::SetValue(ushort const *,ulong,void const *,ulong)
0x18000ea59  nop     dword ptr [rax+rax+00h]
0x18000ea5e  mov     ecx, eax
0x18000ea60  mov     r9d, 50Fh
0x18000ea66  mov     ebx, eax
0x18000ea68  call    ElValidateWin32_0
0x18000ea6d  mov     rcx, [rsp+38h+hKey]; hKey
0x18000ea72  test    rcx, rcx
0x18000ea75  jz      short loc_18000EA89
0x18000ea77  call    cs:__imp_RegCloseKey
0x18000ea7e  nop     dword ptr [rax+rax+00h]
0x18000ea83  and     [rsp+38h+hKey], 0
0x18000ea89  mov     rcx, rsi; lpCriticalSection
0x18000ea8c  call    cs:__imp_LeaveCriticalSection
0x18000ea93  nop     dword ptr [rax+rax+00h]
0x18000ea98  mov     rsi, [rsp+38h+arg_10]
0x18000ea9d  mov     eax, ebx
0x18000ea9f  mov     rbx, [rsp+38h+arg_8]
0x18000eaa4  add     rsp, 30h
0x18000eaa8  pop     rdi
0x18000eaa9  retn
```
