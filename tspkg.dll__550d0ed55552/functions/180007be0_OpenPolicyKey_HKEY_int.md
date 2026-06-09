# OpenPolicyKey(HKEY__ * *,int)

- ea: `0x180007be0`
- end: `0x180007c36`
- name: `?OpenPolicyKey@@YAJPEAPEAUHKEY__@@H@Z`
- size: `86`
- prototype: `__int64 __fastcall(PHKEY phkResult, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bae0`

## callees

- `0x180007be0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007c16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007c16`

## pseudocode

```c
LSTATUS __fastcall OpenPolicyKey(PHKEY phkResult, int a2)
{
  bool v2; // zf
  const WCHAR *v3; // rdx
  LSTATUS result; // eax

  *phkResult = 0;
  v2 = a2 == 0;
  v3 = L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Credssp\\PolicyDefaults";
  if ( v2 )
    v3 = L"SOFTWARE\\Policies\\Microsoft\\Windows\\CredentialsDelegation";
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, phkResult);
  if ( result == 2 )
    return 0;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180007be0  sub     rsp, 38h
0x180007be4  mov     eax, edx
0x180007be6  mov     qword ptr [rcx], 0
0x180007bed  lea     r8, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180007bf4  mov     [rsp+38h+phkResult], rcx; phkResult
0x180007bf9  test    eax, eax
0x180007bfb  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x180007c02  mov     r9d, 20019h; samDesired
0x180007c08  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007c0f  cmovz   rdx, r8; lpSubKey
0x180007c13  xor     r8d, r8d; ulOptions
0x180007c16  call    cs:__imp_RegOpenKeyExW
0x180007c1c  cmp     eax, 2
0x180007c1f  jnz     short loc_180007C28
0x180007c21  xor     eax, eax
0x180007c23  add     rsp, 38h
0x180007c27  retn
0x180007c28  test    eax, eax
0x180007c2a  jle     short loc_180007C23
0x180007c2c  movzx   eax, ax
0x180007c2f  or      eax, 80070000h
0x180007c34  jmp     short loc_180007C23
```
