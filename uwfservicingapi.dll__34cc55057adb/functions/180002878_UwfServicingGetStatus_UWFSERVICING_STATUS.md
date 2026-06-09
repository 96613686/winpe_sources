# UwfServicingGetStatus(UWFSERVICING_STATUS *)

- ea: `0x180002878`
- end: `0x180002959`
- name: `?UwfServicingGetStatus@@YAJPEAW4UWFSERVICING_STATUS@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(enum UWFSERVICING_STATUS *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180003358`

## callees

- `0x180002878`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002922`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002922`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002933`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002933`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800028cc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800028cc`

## string_xrefs

- `0x1800028c5`: `SYSTEM\CurrentControlSet\Services\UwfServicingSvc\Servicing`
- `0x1800028ec`: `SYSTEM\CurrentControlSet\Services\UwfServicingSvc\Servicing`

## pseudocode

```c
__int64 __fastcall UwfServicingGetStatus(enum UWFSERVICING_STATUS *a1)
{
  LSTATUS ValueW; // ebx
  DWORD v4; // [rsp+60h] [rbp+8h] BYREF
  DWORD v5; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  *(_DWORD *)a1 = 3;
  v5 = 0;
  v4 = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\UwfServicingSvc\\Servicing",
             L"Status",
             0x20000010u,
             &v5,
             a1,
             &v4);
  if ( ValueW == 2 )
  {
    hKey = 0;
    ValueW = RegCreateKeyExW(
               HKEY_LOCAL_MACHINE,
               L"SYSTEM\\CurrentControlSet\\Services\\UwfServicingSvc\\Servicing",
               0,
               0,
               0,
               0x2001Fu,
               0,
               &hKey,
               0);
    if ( !ValueW )
      RegCloseKey(hKey);
    *(_DWORD *)a1 = 0;
  }
  if ( ValueW > 0 )
    return (unsigned __int16)ValueW | 0x80070000;
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x180002878  mov     r11, rsp
0x18000287b  mov     [r11+20h], rbx
0x18000287f  push    rdi
0x180002880  sub     rsp, 50h
0x180002884  lea     rax, [r11+8]
0x180002888  mov     dword ptr [rcx], 3
0x18000288e  mov     [r11-28h], rax
0x180002892  lea     r8, ValueName; "Status"
0x180002899  mov     [r11-30h], rcx
0x18000289d  lea     rax, [r11+10h]
0x1800028a1  mov     rdi, rcx
0x1800028a4  mov     [r11-38h], rax
0x1800028a8  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800028af  mov     [rsp+58h+arg_8], 0
0x1800028b7  mov     r9d, 20000010h; dwFlags
0x1800028bd  mov     [rsp+58h+arg_0], 4
0x1800028c5  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Uw"...
0x1800028cc  call    cs:__imp_RegGetValueW
0x1800028d2  mov     ebx, eax
0x1800028d4  cmp     eax, 2
0x1800028d7  jnz     short loc_18000293F
0x1800028d9  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800028e2  lea     rax, [rsp+58h+hKey]
0x1800028e7  mov     [rsp+58h+phkResult], rax; phkResult
0x1800028ec  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Uw"...
0x1800028f3  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800028fc  xor     r9d, r9d; lpClass
0x1800028ff  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180002907  xor     r8d, r8d; Reserved
0x18000290a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002911  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180002919  mov     [rsp+58h+hKey], 0
0x180002922  call    cs:__imp_RegCreateKeyExW
0x180002928  mov     ebx, eax
0x18000292a  test    eax, eax
0x18000292c  jnz     short loc_180002939
0x18000292e  mov     rcx, [rsp+58h+hKey]; hKey
0x180002933  call    cs:__imp_RegCloseKey
0x180002939  mov     dword ptr [rdi], 0
0x18000293f  test    ebx, ebx
0x180002941  jle     short loc_18000294C
0x180002943  movzx   ebx, bx
0x180002946  or      ebx, 80070000h
0x18000294c  mov     eax, ebx
0x18000294e  mov     rbx, [rsp+58h+arg_18]
0x180002953  add     rsp, 50h
0x180002957  pop     rdi
0x180002958  retn
```
