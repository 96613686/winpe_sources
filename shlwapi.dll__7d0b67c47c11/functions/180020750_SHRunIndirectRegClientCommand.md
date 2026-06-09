# SHRunIndirectRegClientCommand

- ea: `0x180020750`
- end: `0x180020945`
- name: `SHRunIndirectRegClientCommand`
- size: `501`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004e64`
- `0x180012550`
- `0x1800205a0`
- `0x180020750`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002083a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020916`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002083a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020916`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020808`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800208ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020808`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800208ee`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x1800207c3`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x18002082d`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x180020865`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x1800207c3`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x18002082d`
- `api-ms-win-core-registry-l2-1-0!RegQueryValueW` at `0x180020865`

## pseudocode

```c
__int64 __fastcall SHRunIndirectRegClientCommand(__int64 a1, __int64 a2)
{
  LSTATUS v4; // ebx
  LSTATUS v5; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  LONG cbData; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Data[80]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[256]; // [rsp+E0h] [rbp-20h] BYREF

  v4 = StringCchPrintfW(SubKey, 0x100u, L"Software\\Clients\\%s", a2);
  if ( v4 >= 0 )
  {
    cbData = 160;
    v5 = RegQueryValueW(HKEY_CURRENT_USER, SubKey, Data, &cbData);
    v4 = v5;
    if ( v5
      && (v5 == 234
       || ((hKey = 0, (v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20219u, &hKey)) != 0)
        || (cbData = 160, v4 = RegQueryValueW(hKey, 0, Data, &cbData), RegCloseKey(hKey), v4))
       && (v4 == 234 || (cbData = 160, (v4 = RegQueryValueW(HKEY_LOCAL_MACHINE, SubKey, Data, &cbData)) != 0))) )
    {
      if ( v4 > 0 )
        return (unsigned __int16)v4 | 0x80070000;
    }
    else
    {
      v4 = StringCchPrintfW(SubKey, 0x100u, L"Software\\Clients\\%s\\%s", a2, Data);
      if ( v4 >= 0 )
      {
        v4 = RunIndirectRegCommand(a1, -2147483646, SubKey, L"Open");
        if ( v4 < 0 )
        {
          hKey = 0;
          if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20219u, &hKey) )
          {
            v4 = RunIndirectRegCommand(a1, hKey, 0, L"Open");
            RegCloseKey(hKey);
          }
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180020750  mov     [rsp-8+arg_10], rbx
0x180020755  mov     [rsp-8+arg_18], rsi
0x18002075a  push    rbp
0x18002075b  push    rdi
0x18002075c  push    r15
0x18002075e  lea     rbp, [rsp-1F0h]
0x180020766  sub     rsp, 2F0h
0x18002076d  mov     rax, cs:__security_cookie
0x180020774  xor     rax, rsp
0x180020777  mov     [rbp+200h+var_20], rax
0x18002077e  mov     rsi, rdx
0x180020781  lea     r8, aSoftwareClient; "Software\\Clients\\%s"
0x180020788  mov     rdi, rcx
0x18002078b  mov     r9, rdx
0x18002078e  mov     edx, 100h; unsigned __int64
0x180020793  lea     rcx, [rbp+200h+SubKey]; unsigned __int16 *
0x180020797  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002079c  mov     ebx, eax
0x18002079e  test    eax, eax
0x1800207a0  js      loc_18002091C
0x1800207a6  lea     r9, [rsp+300h+cbData]; lpcbData
0x1800207ab  mov     [rsp+300h+cbData], 0A0h
0x1800207b3  lea     r8, [rsp+300h+Data]; lpData
0x1800207b8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800207bf  lea     rdx, [rbp+200h+SubKey]; lpSubKey
0x1800207c3  call    cs:__imp_RegQueryValueW
0x1800207c9  mov     ebx, eax
0x1800207cb  mov     r15, 0FFFFFFFF80000002h
0x1800207d2  test    eax, eax
0x1800207d4  jz      loc_180020887
0x1800207da  cmp     eax, 0EAh
0x1800207df  jz      loc_180020871
0x1800207e5  lea     rax, [rsp+300h+hKey]
0x1800207ea  mov     [rsp+300h+hKey], 0
0x1800207f3  mov     r9d, 20219h; samDesired
0x1800207f9  mov     [rsp+300h+phkResult], rax; phkResult
0x1800207fe  xor     r8d, r8d; ulOptions
0x180020801  lea     rdx, [rbp+200h+SubKey]; lpSubKey
0x180020805  mov     rcx, r15; hKey
0x180020808  call    cs:__imp_RegOpenKeyExW
0x18002080e  mov     ebx, eax
0x180020810  test    eax, eax
0x180020812  jnz     short loc_180020844
0x180020814  mov     rcx, [rsp+300h+hKey]; hKey
0x180020819  lea     r9, [rsp+300h+cbData]; lpcbData
0x18002081e  lea     r8, [rsp+300h+Data]; lpData
0x180020823  mov     [rsp+300h+cbData], 0A0h
0x18002082b  xor     edx, edx; lpSubKey
0x18002082d  call    cs:__imp_RegQueryValueW
0x180020833  mov     rcx, [rsp+300h+hKey]; hKey
0x180020838  mov     ebx, eax
0x18002083a  call    cs:__imp_RegCloseKey
0x180020840  test    ebx, ebx
0x180020842  jz      short loc_180020887
0x180020844  cmp     ebx, 0EAh
0x18002084a  jz      short loc_180020871
0x18002084c  lea     r9, [rsp+300h+cbData]; lpcbData
0x180020851  mov     [rsp+300h+cbData], 0A0h
0x180020859  lea     r8, [rsp+300h+Data]; lpData
0x18002085e  mov     rcx, r15; hKey
0x180020861  lea     rdx, [rbp+200h+SubKey]; lpSubKey
0x180020865  call    cs:__imp_RegQueryValueW
0x18002086b  mov     ebx, eax
0x18002086d  test    eax, eax
0x18002086f  jz      short loc_180020887
0x180020871  test    ebx, ebx
0x180020873  jle     loc_18002091C
0x180020879  movzx   ebx, bx
0x18002087c  or      ebx, 80070000h
0x180020882  jmp     loc_18002091C
0x180020887  lea     rax, [rsp+300h+Data]
0x18002088c  mov     r9, rsi
0x18002088f  lea     r8, aSoftwareClient_0; "Software\\Clients\\%s\\%s"
0x180020896  mov     [rsp+300h+phkResult], rax
0x18002089b  mov     edx, 100h; unsigned __int64
0x1800208a0  lea     rcx, [rbp+200h+SubKey]; unsigned __int16 *
0x1800208a4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800208a9  mov     ebx, eax
0x1800208ab  test    eax, eax
0x1800208ad  js      short loc_18002091C
0x1800208af  lea     r9, aOpen; "Open"
0x1800208b6  mov     rdx, r15
0x1800208b9  lea     r8, [rbp+200h+SubKey]
0x1800208bd  mov     rcx, rdi
0x1800208c0  call    RunIndirectRegCommand
0x1800208c5  mov     ebx, eax
0x1800208c7  test    eax, eax
0x1800208c9  jns     short loc_18002091C
0x1800208cb  lea     rax, [rsp+300h+hKey]
0x1800208d0  mov     [rsp+300h+hKey], 0
0x1800208d9  mov     r9d, 20219h; samDesired
0x1800208df  mov     [rsp+300h+phkResult], rax; phkResult
0x1800208e4  xor     r8d, r8d; ulOptions
0x1800208e7  lea     rdx, [rbp+200h+SubKey]; lpSubKey
0x1800208eb  mov     rcx, r15; hKey
0x1800208ee  call    cs:__imp_RegOpenKeyExW
0x1800208f4  test    eax, eax
0x1800208f6  jnz     short loc_18002091C
0x1800208f8  mov     rdx, [rsp+300h+hKey]
0x1800208fd  lea     r9, aOpen; "Open"
0x180020904  xor     r8d, r8d
0x180020907  mov     rcx, rdi
0x18002090a  call    RunIndirectRegCommand
0x18002090f  mov     rcx, [rsp+300h+hKey]; hKey
0x180020914  mov     ebx, eax
0x180020916  call    cs:__imp_RegCloseKey
0x18002091c  mov     eax, ebx
0x18002091e  mov     rcx, [rbp+200h+var_20]
0x180020925  xor     rcx, rsp; StackCookie
0x180020928  call    __security_check_cookie
0x18002092d  lea     r11, [rsp+300h+var_10]
0x180020935  mov     rbx, [r11+30h]
0x180020939  mov     rsi, [r11+38h]
0x18002093d  mov     rsp, r11
0x180020940  pop     r15
0x180020942  pop     rdi
0x180020943  pop     rbp
0x180020944  retn
```
