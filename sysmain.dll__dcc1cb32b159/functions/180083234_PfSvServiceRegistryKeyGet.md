# PfSvServiceRegistryKeyGet

- ea: `0x180083234`
- end: `0x18008348b`
- name: `PfSvServiceRegistryKeyGet`
- size: `599`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180081b6c`
- `0x180083b00`
- `0x180084640`
- `0x180084948`

## callees

- `0x1800382e0`
- `0x1800383e8`
- `0x180083234`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008343c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008344c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008345c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008343c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008344c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008345c`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x1800833e7`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x1800833e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800832a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800832a4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800832cb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008330e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180083390`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800832cb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008330e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180083390`

## string_xrefs

- `0x1800832ea`: `StaticConfig`
- `0x180083337`: `ServiceKeyPath`
- `0x1800833bd`: `MigratedServiceKey`
- `0x180083410`: `MigratedServiceKey`

## pseudocode

```c
__int64 __fastcall PfSvServiceRegistryKeyGet(HKEY *a1, int a2)
{
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  unsigned int Value; // eax
  HKEY v6; // rax
  unsigned int v7; // eax
  int v9; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKeyDest; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v12; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  v9 = 0;
  hKey = 0;
  hKeyDest = 0;
  v12 = 0;
  if ( a2 )
    v3 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Superfetch",
           0,
           0xF003Fu,
           &hKey);
  else
    v3 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Superfetch",
           0,
           0,
           0,
           0xF003Fu,
           0,
           &hKey,
           0);
  v4 = v3;
  if ( !v3 )
  {
    v4 = RegCreateKeyExW(hKey, L"StaticConfig", 0, 0, 0, 0x20019u, 0, &v12, 0);
    if ( !v4 )
    {
      Value = PfsRegQueryValue((_DWORD)v12, (unsigned int)L"ServiceKeyPath", 1, 520, (__int64)SubKey);
      v4 = Value;
      if ( Value == 2 )
      {
        v6 = hKey;
        hKey = 0;
LABEL_16:
        v4 = 0;
        *a1 = v6;
        goto LABEL_17;
      }
      if ( !Value )
      {
        v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKeyDest, 0);
        if ( !v4 )
        {
          v9 = 0;
          v7 = PfsRegQueryValue((_DWORD)hKeyDest, (unsigned int)L"MigratedServiceKey", 4, 4, (__int64)&v9);
          v4 = v7;
          if ( v9
            || (!v7 || v7 == 2)
            && (v4 = RegCopyTreeW(hKey, 0, hKeyDest)) == 0
            && (v9 = 1, (v4 = PfsRegSetValue(hKeyDest, L"MigratedServiceKey", 4, 4, &v9)) == 0) )
          {
            v6 = hKeyDest;
            hKeyDest = 0;
            goto LABEL_16;
          }
        }
      }
    }
  }
LABEL_17:
  if ( v12 )
    RegCloseKey(v12);
  if ( hKey )
    RegCloseKey(hKey);
  if ( hKeyDest )
    RegCloseKey(hKeyDest);
  return v4;
}

```

## disassembly

```asm
0x180083234  mov     [rsp-8+arg_8], rbx
0x180083239  mov     [rsp-8+arg_10], rsi
0x18008323e  push    rbp
0x18008323f  push    rdi
0x180083240  push    r14
0x180083242  lea     rbp, [rsp-190h]
0x18008324a  sub     rsp, 290h
0x180083251  mov     rax, cs:__security_cookie
0x180083258  xor     rax, rsp
0x18008325b  mov     [rbp+1A0h+var_20], rax
0x180083262  xor     r14d, r14d
0x180083265  lea     rax, [rsp+2A0h+hKey]
0x18008326a  xor     r8d, r8d; Reserved
0x18008326d  mov     [rsp+2A0h+var_250], r14d
0x180083272  mov     rdi, 0FFFFFFFF80000002h
0x180083279  mov     [rsp+2A0h+hKey], r14
0x18008327e  test    edx, edx
0x180083280  mov     [rsp+2A0h+hKeyDest], r14
0x180083285  mov     rsi, rcx
0x180083288  mov     [rsp+2A0h+var_238], r14
0x18008328d  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180083294  mov     rcx, rdi; hKey
0x180083297  jz      short loc_1800832AC
0x180083299  mov     r9d, 0F003Fh; samDesired
0x18008329f  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800832a4  call    cs:__imp_RegOpenKeyExW
0x1800832aa  jmp     short loc_1800832D1
0x1800832ac  mov     [rsp+2A0h+lpdwDisposition], r14; lpdwDisposition
0x1800832b1  xor     r9d, r9d; lpClass
0x1800832b4  mov     [rsp+2A0h+var_268], rax; phkResult
0x1800832b9  mov     [rsp+2A0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800832be  mov     [rsp+2A0h+samDesired], 0F003Fh; samDesired
0x1800832c6  mov     dword ptr [rsp+2A0h+phkResult], r14d; dwOptions
0x1800832cb  call    cs:__imp_RegCreateKeyExW
0x1800832d1  mov     ebx, eax
0x1800832d3  test    eax, eax
0x1800832d5  jnz     loc_180083432
0x1800832db  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800832e0  lea     rax, [rsp+2A0h+var_238]
0x1800832e5  mov     [rsp+2A0h+lpdwDisposition], r14; lpdwDisposition
0x1800832ea  lea     rdx, aStaticconfig; "StaticConfig"
0x1800832f1  mov     [rsp+2A0h+var_268], rax; phkResult
0x1800832f6  xor     r9d, r9d; lpClass
0x1800832f9  mov     [rsp+2A0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800832fe  xor     r8d, r8d; Reserved
0x180083301  mov     [rsp+2A0h+samDesired], 20019h; samDesired
0x180083309  mov     dword ptr [rsp+2A0h+phkResult], r14d; dwOptions
0x18008330e  call    cs:__imp_RegCreateKeyExW
0x180083314  mov     ebx, eax
0x180083316  test    eax, eax
0x180083318  jnz     loc_180083432
0x18008331e  mov     rcx, [rsp+2A0h+var_238]
0x180083323  lea     rax, [rsp+2A0h+SubKey]
0x180083328  mov     r9d, 208h
0x18008332e  mov     [rsp+2A0h+phkResult], rax
0x180083333  lea     r8d, [rbx+1]
0x180083337  lea     rdx, aServicekeypath; "ServiceKeyPath"
0x18008333e  call    PfsRegQueryValue
0x180083343  mov     ebx, eax
0x180083345  cmp     eax, 2
0x180083348  jnz     short loc_180083359
0x18008334a  mov     rax, [rsp+2A0h+hKey]
0x18008334f  mov     [rsp+2A0h+hKey], r14
0x180083354  jmp     loc_18008342C
0x180083359  test    eax, eax
0x18008335b  jnz     loc_180083432
0x180083361  mov     [rsp+2A0h+lpdwDisposition], r14; lpdwDisposition
0x180083366  lea     rax, [rsp+2A0h+hKeyDest]
0x18008336b  mov     [rsp+2A0h+var_268], rax; phkResult
0x180083370  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x180083375  mov     [rsp+2A0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18008337a  xor     r9d, r9d; lpClass
0x18008337d  mov     [rsp+2A0h+samDesired], 0F003Fh; samDesired
0x180083385  xor     r8d, r8d; Reserved
0x180083388  mov     rcx, rdi; hKey
0x18008338b  mov     dword ptr [rsp+2A0h+phkResult], r14d; dwOptions
0x180083390  call    cs:__imp_RegCreateKeyExW
0x180083396  mov     ebx, eax
0x180083398  test    eax, eax
0x18008339a  jnz     loc_180083432
0x1800833a0  mov     rcx, [rsp+2A0h+hKeyDest]
0x1800833a5  lea     edi, [rbx+4]
0x1800833a8  lea     rax, [rsp+2A0h+var_250]
0x1800833ad  mov     [rsp+2A0h+var_250], r14d
0x1800833b2  mov     r9d, edi
0x1800833b5  mov     [rsp+2A0h+phkResult], rax
0x1800833ba  mov     r8d, edi
0x1800833bd  lea     rdx, aMigratedservic; "MigratedServiceKey"
0x1800833c4  call    PfsRegQueryValue
0x1800833c9  mov     ebx, eax
0x1800833cb  cmp     [rsp+2A0h+var_250], r14d
0x1800833d0  jnz     short loc_180083422
0x1800833d2  test    eax, eax
0x1800833d4  jz      short loc_1800833DB
0x1800833d6  cmp     eax, 2
0x1800833d9  jnz     short loc_180083432
0x1800833db  mov     r8, [rsp+2A0h+hKeyDest]; hKeyDest
0x1800833e0  xor     edx, edx; lpSubKey
0x1800833e2  mov     rcx, [rsp+2A0h+hKey]; hKeySrc
0x1800833e7  call    cs:__imp_RegCopyTreeW
0x1800833ed  mov     ebx, eax
0x1800833ef  test    eax, eax
0x1800833f1  jnz     short loc_180083432
0x1800833f3  mov     rcx, [rsp+2A0h+hKeyDest]
0x1800833f8  lea     rax, [rsp+2A0h+var_250]
0x1800833fd  mov     r9d, edi
0x180083400  mov     [rsp+2A0h+phkResult], rax
0x180083405  mov     r8d, edi
0x180083408  mov     [rsp+2A0h+var_250], 1
0x180083410  lea     rdx, aMigratedservic; "MigratedServiceKey"
0x180083417  call    PfsRegSetValue
0x18008341c  mov     ebx, eax
0x18008341e  test    eax, eax
0x180083420  jnz     short loc_180083432
0x180083422  mov     rax, [rsp+2A0h+hKeyDest]
0x180083427  mov     [rsp+2A0h+hKeyDest], r14
0x18008342c  mov     ebx, r14d
0x18008342f  mov     [rsi], rax
0x180083432  mov     rcx, [rsp+2A0h+var_238]; hKey
0x180083437  test    rcx, rcx
0x18008343a  jz      short loc_180083442
0x18008343c  call    cs:__imp_RegCloseKey
0x180083442  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180083447  test    rcx, rcx
0x18008344a  jz      short loc_180083452
0x18008344c  call    cs:__imp_RegCloseKey
0x180083452  mov     rcx, [rsp+2A0h+hKeyDest]; hKey
0x180083457  test    rcx, rcx
0x18008345a  jz      short loc_180083462
0x18008345c  call    cs:__imp_RegCloseKey
0x180083462  mov     eax, ebx
0x180083464  mov     rcx, [rbp+1A0h+var_20]
0x18008346b  xor     rcx, rsp; StackCookie
0x18008346e  call    __security_check_cookie
0x180083473  lea     r11, [rsp+2A0h+var_10]
0x18008347b  mov     rbx, [r11+28h]
0x18008347f  mov     rsi, [r11+30h]
0x180083483  mov     rsp, r11
0x180083486  pop     r14
0x180083488  pop     rdi
0x180083489  pop     rbp
0x18008348a  retn
```
