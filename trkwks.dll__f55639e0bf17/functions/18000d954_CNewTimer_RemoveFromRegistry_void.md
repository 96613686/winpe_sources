# CNewTimer::RemoveFromRegistry(void)

- ea: `0x18000d954`
- end: `0x18000d9dc`
- name: `?RemoveFromRegistry@CNewTimer@@AEAAXXZ`
- size: `136`
- prototype: `void __fastcall(CNewTimer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18000c014`

## callees

- `0x18000d954`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d97a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d97a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d9cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011949`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d9cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011949`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d9a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d9a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d9c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d9c0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000d9b5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000d9b5`

## string_xrefs

- `0x18000d994`: `System\CurrentControlSet\Services\TrkWks\Parameters`

## pseudocode

```c
void __fastcall CNewTimer::RemoveFromRegistry(CNewTimer *this)
{
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  if ( *((_QWORD *)this + 8) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\TrkWks\\Parameters",
            0,
            0x2000000u,
            &hKey) )
    {
      RegDeleteValueW(hKey, *((LPCWSTR *)this + 8));
      RegCloseKey(hKey);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x18000d954  mov     [rsp+arg_10], rbx
0x18000d959  mov     [rsp+arg_0], rcx
0x18000d95e  push    rdi
0x18000d95f  sub     rsp, 30h
0x18000d963  mov     rbx, rcx
0x18000d966  mov     [rsp+38h+hKey], 0
0x18000d96f  cmp     qword ptr [rcx+40h], 0
0x18000d974  jz      short loc_18000D9D1
0x18000d976  add     rcx, 10h; lpCriticalSection
0x18000d97a  call    cs:__imp_EnterCriticalSection
0x18000d980  nop
0x18000d981  lea     rax, [rsp+38h+hKey]
0x18000d986  mov     [rsp+38h+phkResult], rax; phkResult
0x18000d98b  mov     r9d, 2000000h; samDesired
0x18000d991  xor     r8d, r8d; ulOptions
0x18000d994  lea     rdx, ?s_tszKeyNameLinkTrack@@3QBGB; "System\\CurrentControlSet\\Services\\Tr"...
0x18000d99b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d9a2  call    cs:__imp_RegOpenKeyExW
0x18000d9a8  test    eax, eax
0x18000d9aa  jnz     short loc_18000D9C7
0x18000d9ac  mov     rdx, [rbx+40h]; lpValueName
0x18000d9b0  mov     rcx, [rsp+38h+hKey]; hKey
0x18000d9b5  call    cs:__imp_RegDeleteValueW
0x18000d9bb  mov     rcx, [rsp+38h+hKey]; hKey
0x18000d9c0  call    cs:__imp_RegCloseKey
0x18000d9c6  nop
0x18000d9c7  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000d9cb  call    cs:__imp_LeaveCriticalSection
0x18000d9d1  mov     rbx, [rsp+38h+arg_10]
0x18000d9d6  add     rsp, 30h
0x18000d9da  pop     rdi
0x18000d9db  retn
0x180011938  push    rbp
0x18001193a  sub     rsp, 30h
0x18001193e  mov     rbp, rdx
0x180011941  mov     rcx, [rbp+40h]
0x180011945  add     rcx, 10h; lpCriticalSection
0x180011949  call    cs:__imp_LeaveCriticalSection
0x18001194f  nop
0x180011950  add     rsp, 30h
0x180011954  pop     rbp
0x180011955  retn
```
