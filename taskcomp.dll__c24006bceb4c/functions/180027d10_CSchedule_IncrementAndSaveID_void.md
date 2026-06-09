# CSchedule::IncrementAndSaveID(void)

- ea: `0x180027d10`
- end: `0x180027ddc`
- name: `?IncrementAndSaveID@CSchedule@@QEAAJXZ`
- size: `204`
- prototype: `__int64 __fastcall(CSchedule *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180013c80`
- `0x180027180`

## callees

- `0x180027d10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027d29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027d29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027dc4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027dc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027da4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027db9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027da4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027db9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027d59`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027d59`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027d91`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027d91`

## string_xrefs

- `0x180027d4b`: `System\CurrentControlSet\Services\Schedule`

## pseudocode

```c
__int64 __fastcall CSchedule::IncrementAndSaveID(CSchedule *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  LSTATUS v3; // eax
  int v4; // ebx
  HKEY v5; // rcx
  const BYTE *v6; // rdi
  LSTATUS v7; // eax
  HKEY v8; // rcx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Schedule", 0, 2u, &hKey);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
    {
      v4 = (unsigned __int16)v3;
LABEL_7:
      v4 |= 0x80070000;
    }
  }
  else
  {
    v5 = hKey;
    v6 = (const BYTE *)this + 48;
    ++*(_DWORD *)v6;
    v7 = RegSetValueExW(v5, L"NextAtJobId", 0, 4u, v6, 4u);
    v8 = hKey;
    v4 = v7;
    if ( !v7 )
    {
      RegCloseKey(hKey);
      v4 = 0;
      goto LABEL_9;
    }
    --*(_DWORD *)v6;
    RegCloseKey(v8);
    if ( v4 > 0 )
    {
      v4 = (unsigned __int16)v4;
      goto LABEL_7;
    }
  }
LABEL_9:
  LeaveCriticalSection(v1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180027d10  mov     [rsp+arg_8], rbx
0x180027d15  mov     [rsp+arg_10], rsi
0x180027d1a  push    rdi
0x180027d1b  sub     rsp, 30h
0x180027d1f  lea     rsi, [rcx+8]
0x180027d23  mov     rdi, rcx
0x180027d26  mov     rcx, rsi; lpCriticalSection
0x180027d29  call    cs:__imp_EnterCriticalSection
0x180027d2f  lea     rax, [rsp+38h+hKey]
0x180027d34  mov     [rsp+38h+hKey], 0
0x180027d3d  mov     r9d, 2; samDesired
0x180027d43  mov     [rsp+38h+phkResult], rax; phkResult
0x180027d48  xor     r8d, r8d; ulOptions
0x180027d4b  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Sc"...
0x180027d52  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027d59  call    cs:__imp_RegOpenKeyExW
0x180027d5f  mov     ebx, eax
0x180027d61  test    eax, eax
0x180027d63  jz      short loc_180027D6C
0x180027d65  jle     short loc_180027DC1
0x180027d67  movzx   ebx, ax
0x180027d6a  jmp     short loc_180027DB1
0x180027d6c  mov     rcx, [rsp+38h+hKey]; hKey
0x180027d71  lea     rdx, aNextatjobid; "NextAtJobId"
0x180027d78  add     rdi, 30h ; '0'
0x180027d7c  mov     r9d, 4; dwType
0x180027d82  mov     [rsp+38h+cbData], r9d; cbData
0x180027d87  xor     r8d, r8d; Reserved
0x180027d8a  mov     [rsp+38h+phkResult], rdi; lpData
0x180027d8f  inc     dword ptr [rdi]
0x180027d91  call    cs:__imp_RegSetValueExW
0x180027d97  mov     rcx, [rsp+38h+hKey]; hKey
0x180027d9c  mov     ebx, eax
0x180027d9e  test    eax, eax
0x180027da0  jz      short loc_180027DB9
0x180027da2  dec     dword ptr [rdi]
0x180027da4  call    cs:__imp_RegCloseKey
0x180027daa  test    ebx, ebx
0x180027dac  jle     short loc_180027DC1
0x180027dae  movzx   ebx, bx
0x180027db1  or      ebx, 80070000h
0x180027db7  jmp     short loc_180027DC1
0x180027db9  call    cs:__imp_RegCloseKey
0x180027dbf  xor     ebx, ebx
0x180027dc1  mov     rcx, rsi; lpCriticalSection
0x180027dc4  call    cs:__imp_LeaveCriticalSection
0x180027dca  mov     rsi, [rsp+38h+arg_10]
0x180027dcf  mov     eax, ebx
0x180027dd1  mov     rbx, [rsp+38h+arg_8]
0x180027dd6  add     rsp, 30h
0x180027dda  pop     rdi
0x180027ddb  retn
```
