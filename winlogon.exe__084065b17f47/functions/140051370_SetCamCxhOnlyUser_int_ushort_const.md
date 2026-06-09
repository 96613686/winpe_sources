# SetCamCxhOnlyUser(int,ushort const *)

- ea: `0x140051370`
- end: `0x1400514a4`
- name: `?SetCamCxhOnlyUser@@YAJHPEBG@Z`
- size: `308`
- prototype: `int(int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14006cf20`

## callees

- `0x140051370`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14005146c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14005146c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400513c7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140051427`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400513c7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140051427`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051486`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051491`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051486`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051491`

## pseudocode

```c
__int64 __fastcall SetCamCxhOnlyUser(int a1, const unsigned __int16 *a2)
{
  LSTATUS v3; // eax
  signed int v4; // ebx
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  Data = a1;
  hKey = 0;
  v3 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\CandidateAccountManager",
         0,
         0,
         1u,
         0x2001Fu,
         0,
         &hKey,
         0);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    phkResult = 0;
    v5 = RegCreateKeyExW(hKey, a2, 0, 0, 1u, 0x2001Fu, 0, &phkResult, 0);
    v4 = v5;
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
    if ( v4 >= 0 )
    {
      Data = 1;
      v6 = RegSetValueExW(phkResult, L"CxhOnlyUse", 0, 4u, (const BYTE *)&Data, 4u);
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140051370  mov     r11, rsp
0x140051373  mov     [r11+10h], rbx
0x140051377  mov     [rsp+Data], ecx
0x14005137b  push    rdi
0x14005137c  sub     rsp, 50h
0x140051380  mov     qword ptr [r11-18h], 0
0x140051388  lea     rax, [r11+20h]
0x14005138c  mov     [r11-20h], rax
0x140051390  mov     rdi, rdx
0x140051393  mov     qword ptr [r11-28h], 0
0x14005139b  lea     rdx, aSoftwareMicros_14; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400513a2  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x1400513aa  xor     r9d, r9d; lpClass
0x1400513ad  xor     r8d, r8d; Reserved
0x1400513b0  mov     [rsp+58h+dwOptions], 1; dwOptions
0x1400513b8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400513bf  mov     qword ptr [r11+20h], 0
0x1400513c7  call    cs:__imp_RegCreateKeyExW
0x1400513cd  mov     ebx, eax
0x1400513cf  test    eax, eax
0x1400513d1  jle     short loc_1400513DC
0x1400513d3  movzx   ebx, ax
0x1400513d6  or      ebx, 80070000h
0x1400513dc  test    ebx, ebx
0x1400513de  js      loc_140051497
0x1400513e4  mov     rcx, [rsp+58h+hKey]; hKey
0x1400513e9  lea     rax, [rsp+58h+arg_10]
0x1400513ee  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1400513f7  xor     r9d, r9d; lpClass
0x1400513fa  mov     [rsp+58h+phkResult], rax; phkResult
0x1400513ff  xor     r8d, r8d; Reserved
0x140051402  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14005140b  mov     rdx, rdi; lpSubKey
0x14005140e  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x140051416  mov     [rsp+58h+dwOptions], 1; dwOptions
0x14005141e  mov     [rsp+58h+arg_10], 0
0x140051427  call    cs:__imp_RegCreateKeyExW
0x14005142d  mov     ebx, eax
0x14005142f  test    eax, eax
0x140051431  jle     short loc_14005143C
0x140051433  movzx   ebx, ax
0x140051436  or      ebx, 80070000h
0x14005143c  test    ebx, ebx
0x14005143e  js      short loc_14005148C
0x140051440  mov     rcx, [rsp+58h+arg_10]; hKey
0x140051445  lea     rax, [rsp+58h+Data]
0x14005144a  mov     r9d, 4; dwType
0x140051450  mov     [rsp+58h+Data], 1
0x140051458  mov     [rsp+58h+samDesired], r9d; cbData
0x14005145d  lea     rdx, aCxhonlyuse; "CxhOnlyUse"
0x140051464  xor     r8d, r8d; Reserved
0x140051467  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x14005146c  call    cs:__imp_RegSetValueExW
0x140051472  mov     ebx, eax
0x140051474  test    eax, eax
0x140051476  jle     short loc_140051481
0x140051478  movzx   ebx, ax
0x14005147b  or      ebx, 80070000h
0x140051481  mov     rcx, [rsp+58h+arg_10]; hKey
0x140051486  call    cs:__imp_RegCloseKey
0x14005148c  mov     rcx, [rsp+58h+hKey]; hKey
0x140051491  call    cs:__imp_RegCloseKey
0x140051497  mov     eax, ebx
0x140051499  mov     rbx, [rsp+58h+arg_8]
0x14005149e  add     rsp, 50h
0x1400514a2  pop     rdi
0x1400514a3  retn
```
