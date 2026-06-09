# CSchedule::ResetAtID(void)

- ea: `0x180029680`
- end: `0x180029760`
- name: `?ResetAtID@CSchedule@@QEAAJXZ`
- size: `224`
- prototype: `__int64 __fastcall(CSchedule *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180016bf0`
- `0x180028a3c`

## callees

- `0x180029680`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800296a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800296a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002970c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002970c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800296fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800296fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800296d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800296d6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002974a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002974a`

## string_xrefs

- `0x1800296c8`: `System\CurrentControlSet\Services\Schedule`

## pseudocode

```c
__int64 __fastcall CSchedule::ResetAtID(CSchedule *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  BYTE *v2; // rsi
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  hKey = 0;
  v2 = (BYTE *)this + 48;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  *(_DWORD *)v2 = 1;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Schedule", 0, 0x2001Fu, &hKey);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 <= 0 )
      goto LABEL_4;
    goto LABEL_3;
  }
  v4 = 0;
  v3 = RegSetValueExW(hKey, L"NextAtJobId", 0, 4u, v2, 4u);
  if ( v3 )
  {
    if ( v3 > 0 )
    {
LABEL_3:
      v4 = (unsigned __int16)v3 | 0x80070000;
      goto LABEL_4;
    }
    v4 = v3;
  }
LABEL_4:
  if ( hKey )
    RegCloseKey(hKey);
  LeaveCriticalSection(v1);
  return v4;
}

```

## disassembly

```asm
0x180029680  mov     [rsp+arg_8], rbx
0x180029685  mov     [rsp+arg_10], rsi
0x18002968a  push    rdi
0x18002968b  sub     rsp, 30h
0x18002968f  lea     rdi, [rcx+8]
0x180029693  mov     [rsp+38h+hKey], 0
0x18002969c  lea     rsi, [rcx+30h]
0x1800296a0  mov     rcx, rdi; lpCriticalSection
0x1800296a3  call    cs:__imp_EnterCriticalSection
0x1800296aa  nop     dword ptr [rax+rax+00h]
0x1800296af  lea     rax, [rsp+38h+hKey]
0x1800296b4  mov     dword ptr [rsi], 1
0x1800296ba  mov     r9d, 2001Fh; samDesired
0x1800296c0  mov     [rsp+38h+phkResult], rax; phkResult
0x1800296c5  xor     r8d, r8d; ulOptions
0x1800296c8  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Sc"...
0x1800296cf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800296d6  call    cs:__imp_RegOpenKeyExW
0x1800296dd  nop     dword ptr [rax+rax+00h]
0x1800296e2  mov     ebx, eax
0x1800296e4  test    eax, eax
0x1800296e6  jz      short loc_18002972B
0x1800296e8  jle     short loc_1800296F3
0x1800296ea  movzx   ebx, ax
0x1800296ed  or      ebx, 80070000h
0x1800296f3  mov     rcx, [rsp+38h+hKey]; hKey
0x1800296f8  test    rcx, rcx
0x1800296fb  jz      short loc_180029709
0x1800296fd  call    cs:__imp_RegCloseKey
0x180029704  nop     dword ptr [rax+rax+00h]
0x180029709  mov     rcx, rdi; lpCriticalSection
0x18002970c  call    cs:__imp_LeaveCriticalSection
0x180029713  nop     dword ptr [rax+rax+00h]
0x180029718  mov     rsi, [rsp+38h+arg_10]
0x18002971d  mov     eax, ebx
0x18002971f  mov     rbx, [rsp+38h+arg_8]
0x180029724  add     rsp, 30h
0x180029728  pop     rdi
0x180029729  retn
0x18002972b  mov     rcx, [rsp+38h+hKey]; hKey
0x180029730  lea     rdx, aNextatjobid; "NextAtJobId"
0x180029737  xor     ebx, ebx
0x180029739  xor     r8d, r8d; Reserved
0x18002973c  lea     r9d, [rbx+4]; dwType
0x180029740  mov     [rsp+38h+cbData], r9d; cbData
0x180029745  mov     [rsp+38h+phkResult], rsi; lpData
0x18002974a  call    cs:__imp_RegSetValueExW
0x180029751  nop     dword ptr [rax+rax+00h]
0x180029756  test    eax, eax
0x180029758  jz      short loc_1800296F3
0x18002975a  jg      short loc_1800296EA
0x18002975c  mov     ebx, eax
0x18002975e  jmp     short loc_1800296F3
```
