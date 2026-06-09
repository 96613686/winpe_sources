# CSchedule::ResetAtID(void)

- ea: `0x180027e08`
- end: `0x180027ec9`
- name: `?ResetAtID@CSchedule@@QEAAJXZ`
- size: `193`
- prototype: `__int64 __fastcall(CSchedule *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180015d80`
- `0x180027228`

## callees

- `0x180027e08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027e2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027e2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027e82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027e82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027e79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027e79`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027e58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027e58`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027eb9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027eb9`

## string_xrefs

- `0x180027e4a`: `System\CurrentControlSet\Services\Schedule`

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
0x180027e08  mov     [rsp+arg_8], rbx
0x180027e0d  mov     [rsp+arg_10], rsi
0x180027e12  push    rdi
0x180027e13  sub     rsp, 30h
0x180027e17  lea     rdi, [rcx+8]
0x180027e1b  mov     [rsp+38h+hKey], 0
0x180027e24  lea     rsi, [rcx+30h]
0x180027e28  mov     rcx, rdi; lpCriticalSection
0x180027e2b  call    cs:__imp_EnterCriticalSection
0x180027e31  lea     rax, [rsp+38h+hKey]
0x180027e36  mov     dword ptr [rsi], 1
0x180027e3c  mov     r9d, 2001Fh; samDesired
0x180027e42  mov     [rsp+38h+phkResult], rax; phkResult
0x180027e47  xor     r8d, r8d; ulOptions
0x180027e4a  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Sc"...
0x180027e51  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027e58  call    cs:__imp_RegOpenKeyExW
0x180027e5e  mov     ebx, eax
0x180027e60  test    eax, eax
0x180027e62  jz      short loc_180027E9A
0x180027e64  jle     short loc_180027E6F
0x180027e66  movzx   ebx, ax
0x180027e69  or      ebx, 80070000h
0x180027e6f  mov     rcx, [rsp+38h+hKey]; hKey
0x180027e74  test    rcx, rcx
0x180027e77  jz      short loc_180027E7F
0x180027e79  call    cs:__imp_RegCloseKey
0x180027e7f  mov     rcx, rdi; lpCriticalSection
0x180027e82  call    cs:__imp_LeaveCriticalSection
0x180027e88  mov     rsi, [rsp+38h+arg_10]
0x180027e8d  mov     eax, ebx
0x180027e8f  mov     rbx, [rsp+38h+arg_8]
0x180027e94  add     rsp, 30h
0x180027e98  pop     rdi
0x180027e99  retn
0x180027e9a  mov     rcx, [rsp+38h+hKey]; hKey
0x180027e9f  lea     rdx, aNextatjobid; "NextAtJobId"
0x180027ea6  xor     ebx, ebx
0x180027ea8  xor     r8d, r8d; Reserved
0x180027eab  lea     r9d, [rbx+4]; dwType
0x180027eaf  mov     [rsp+38h+cbData], r9d; cbData
0x180027eb4  mov     [rsp+38h+phkResult], rsi; lpData
0x180027eb9  call    cs:__imp_RegSetValueExW
0x180027ebf  test    eax, eax
0x180027ec1  jz      short loc_180027E6F
0x180027ec3  jg      short loc_180027E66
0x180027ec5  mov     ebx, eax
0x180027ec7  jmp     short loc_180027E6F
```
