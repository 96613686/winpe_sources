# CSchedule::IncrementAndSaveID(void)

- ea: `0x180029560`
- end: `0x180029651`
- name: `?IncrementAndSaveID@CSchedule@@QEAAJXZ`
- size: `241`
- prototype: `__int64 __fastcall(CSchedule *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800148d0`
- `0x180028990`

## callees

- `0x180029560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029579`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029579`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029632`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029632`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029606`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029621`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029606`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029621`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800295af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800295af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800295ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800295ed`

## string_xrefs

- `0x1800295a1`: `System\CurrentControlSet\Services\Schedule`

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
0x180029560  mov     [rsp+arg_8], rbx
0x180029565  mov     [rsp+arg_10], rsi
0x18002956a  push    rdi
0x18002956b  sub     rsp, 30h
0x18002956f  lea     rsi, [rcx+8]
0x180029573  mov     rdi, rcx
0x180029576  mov     rcx, rsi; lpCriticalSection
0x180029579  call    cs:__imp_EnterCriticalSection
0x180029580  nop     dword ptr [rax+rax+00h]
0x180029585  lea     rax, [rsp+38h+hKey]
0x18002958a  mov     [rsp+38h+hKey], 0
0x180029593  mov     r9d, 2; samDesired
0x180029599  mov     [rsp+38h+phkResult], rax; phkResult
0x18002959e  xor     r8d, r8d; ulOptions
0x1800295a1  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Sc"...
0x1800295a8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800295af  call    cs:__imp_RegOpenKeyExW
0x1800295b6  nop     dword ptr [rax+rax+00h]
0x1800295bb  mov     ebx, eax
0x1800295bd  test    eax, eax
0x1800295bf  jz      short loc_1800295C8
0x1800295c1  jle     short loc_18002962F
0x1800295c3  movzx   ebx, ax
0x1800295c6  jmp     short loc_180029619
0x1800295c8  mov     rcx, [rsp+38h+hKey]; hKey
0x1800295cd  lea     rdx, aNextatjobid; "NextAtJobId"
0x1800295d4  add     rdi, 30h ; '0'
0x1800295d8  mov     r9d, 4; dwType
0x1800295de  mov     [rsp+38h+cbData], r9d; cbData
0x1800295e3  xor     r8d, r8d; Reserved
0x1800295e6  mov     [rsp+38h+phkResult], rdi; lpData
0x1800295eb  inc     dword ptr [rdi]
0x1800295ed  call    cs:__imp_RegSetValueExW
0x1800295f4  nop     dword ptr [rax+rax+00h]
0x1800295f9  mov     rcx, [rsp+38h+hKey]; hKey
0x1800295fe  mov     ebx, eax
0x180029600  test    eax, eax
0x180029602  jz      short loc_180029621
0x180029604  dec     dword ptr [rdi]
0x180029606  call    cs:__imp_RegCloseKey
0x18002960d  nop     dword ptr [rax+rax+00h]
0x180029612  test    ebx, ebx
0x180029614  jle     short loc_18002962F
0x180029616  movzx   ebx, bx
0x180029619  or      ebx, 80070000h
0x18002961f  jmp     short loc_18002962F
0x180029621  call    cs:__imp_RegCloseKey
0x180029628  nop     dword ptr [rax+rax+00h]
0x18002962d  xor     ebx, ebx
0x18002962f  mov     rcx, rsi; lpCriticalSection
0x180029632  call    cs:__imp_LeaveCriticalSection
0x180029639  nop     dword ptr [rax+rax+00h]
0x18002963e  mov     rsi, [rsp+38h+arg_10]
0x180029643  mov     eax, ebx
0x180029645  mov     rbx, [rsp+38h+arg_8]
0x18002964a  add     rsp, 30h
0x18002964e  pop     rdi
0x18002964f  retn
```
