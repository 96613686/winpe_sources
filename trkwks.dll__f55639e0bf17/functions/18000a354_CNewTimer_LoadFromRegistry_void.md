# CNewTimer::LoadFromRegistry(void)

- ea: `0x18000a354`
- end: `0x18000a4b0`
- name: `?LoadFromRegistry@CNewTimer@@AEAAXXZ`
- size: `348`
- prototype: `void __fastcall(CNewTimer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000a27c`

## callees

- `0x18000a354`
- `0x18001011c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a37b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a37b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a4a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800116cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a4a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800116cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a432`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a432`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a499`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a499`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116bb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000a47e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000a47e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a3c5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a3c5`

## string_xrefs

- `0x18000a3b7`: `System\CurrentControlSet\Services\TrkWks\Parameters`

## pseudocode

```c
void __fastcall CNewTimer::LoadFromRegistry(CNewTimer *this)
{
  BYTE Data[8]; // [rsp+58h] [rbp-30h] BYREF
  __int64 v3; // [rsp+60h] [rbp-28h]
  int v4; // [rsp+68h] [rbp-20h]
  DWORD Type; // [rsp+98h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+20h] BYREF

  hKey = 0;
  if ( *((_QWORD *)this + 8) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    if ( RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\TrkWks\\Parameters",
           0,
           0,
           0,
           0x2000000u,
           0,
           &hKey,
           0) )
    {
      hKey = 0;
    }
    else
    {
      CNewTimer::PersistentState::PersistentState((CNewTimer::PersistentState *)Data);
      cbData = 24;
      Type = 0;
      if ( !RegQueryValueExW(hKey, *((LPCWSTR *)this + 8), 0, &Type, Data, &cbData) )
      {
        if ( Type == 3 && cbData == 24 )
        {
          *((_QWORD *)this + 15) = v3;
          *((_QWORD *)this + 16) = *(_QWORD *)Data;
          *((_DWORD *)this + 29) = v4;
        }
        else
        {
          RegDeleteValueW(hKey, *((LPCWSTR *)this + 8));
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x18000a354  mov     rax, rsp
0x18000a357  mov     [rax+8], rcx
0x18000a35b  push    rbx
0x18000a35c  push    rdi
0x18000a35d  sub     rsp, 78h
0x18000a361  mov     rbx, rcx
0x18000a364  mov     qword ptr [rax+20h], 0
0x18000a36c  cmp     qword ptr [rcx+40h], 0
0x18000a371  jz      loc_18000A4A9
0x18000a377  add     rcx, 10h; lpCriticalSection
0x18000a37b  call    cs:__imp_EnterCriticalSection
0x18000a381  nop
0x18000a382  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x18000a38b  lea     rax, [rsp+88h+hKey]
0x18000a393  mov     [rsp+88h+phkResult], rax; phkResult
0x18000a398  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000a3a1  mov     [rsp+88h+samDesired], 2000000h; samDesired
0x18000a3a9  mov     [rsp+88h+dwOptions], 0; dwOptions
0x18000a3b1  xor     r9d, r9d; lpClass
0x18000a3b4  xor     r8d, r8d; Reserved
0x18000a3b7  lea     rdx, ?s_tszKeyNameLinkTrack@@3QBGB; "System\\CurrentControlSet\\Services\\Tr"...
0x18000a3be  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a3c5  call    cs:__imp_RegCreateKeyExW
0x18000a3cb  mov     [rsp+88h+var_38], eax
0x18000a3cf  test    eax, eax
0x18000a3d1  jz      short loc_18000A3E4
0x18000a3d3  mov     [rsp+88h+hKey], 0
0x18000a3df  jmp     loc_18000A48C
0x18000a3e4  lea     rcx, [rsp+88h+Data]; this
0x18000a3e9  call    ??0PersistentState@CNewTimer@@QEAA@XZ; CNewTimer::PersistentState::PersistentState(void)
0x18000a3ee  mov     [rsp+88h+cbData], 18h
0x18000a3f9  mov     [rsp+88h+Type], 0
0x18000a404  lea     rax, [rsp+88h+cbData]
0x18000a40c  mov     qword ptr [rsp+88h+samDesired], rax; lpcbData
0x18000a411  lea     rax, [rsp+88h+Data]
0x18000a416  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x18000a41b  lea     r9, [rsp+88h+Type]; lpType
0x18000a423  xor     r8d, r8d; lpReserved
0x18000a426  mov     rdx, [rbx+40h]; lpValueName
0x18000a42a  mov     rcx, [rsp+88h+hKey]; hKey
0x18000a432  call    cs:__imp_RegQueryValueExW
0x18000a438  mov     [rsp+88h+var_38], eax
0x18000a43c  test    eax, eax
0x18000a43e  jnz     short loc_18000A48C
0x18000a440  cmp     [rsp+88h+Type], 3
0x18000a448  jnz     short loc_18000A472
0x18000a44a  cmp     [rsp+88h+cbData], 18h
0x18000a452  jnz     short loc_18000A472
0x18000a454  mov     rax, [rsp+88h+var_28]
0x18000a459  mov     [rbx+78h], rax
0x18000a45d  mov     rax, qword ptr [rsp+88h+Data]
0x18000a462  mov     [rbx+80h], rax
0x18000a469  mov     eax, [rsp+88h+var_20]
0x18000a46d  mov     [rbx+74h], eax
0x18000a470  jmp     short loc_18000A48C
0x18000a472  mov     rdx, [rbx+40h]; lpValueName
0x18000a476  mov     rcx, [rsp+88h+hKey]; hKey
0x18000a47e  call    cs:__imp_RegDeleteValueW
0x18000a484  mov     [rsp+88h+var_38], 2
0x18000a48c  mov     rcx, [rsp+88h+hKey]; hKey
0x18000a494  test    rcx, rcx
0x18000a497  jz      short loc_18000A49F
0x18000a499  call    cs:__imp_RegCloseKey
0x18000a49f  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000a4a3  call    cs:__imp_LeaveCriticalSection
0x18000a4a9  add     rsp, 78h
0x18000a4ad  pop     rdi
0x18000a4ae  pop     rbx
0x18000a4af  retn
0x1800116a6  push    rbp
0x1800116a8  sub     rsp, 50h
0x1800116ac  mov     rbp, rdx
0x1800116af  mov     rcx, [rbp+0A8h]; hKey
0x1800116b6  test    rcx, rcx
0x1800116b9  jz      short loc_1800116C2
0x1800116bb  call    cs:__imp_RegCloseKey
0x1800116c1  nop
0x1800116c2  mov     rcx, [rbp+90h]
0x1800116c9  add     rcx, 10h; lpCriticalSection
0x1800116cd  call    cs:__imp_LeaveCriticalSection
0x1800116d3  nop
0x1800116d4  add     rsp, 50h
0x1800116d8  pop     rbp
0x1800116d9  retn
```
