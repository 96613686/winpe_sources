# SQMBitLockerIfNeeded(void)

- ea: `0x18006ce30`
- end: `0x18006cfdb`
- name: `?SQMBitLockerIfNeeded@@YAXXZ`
- size: `427`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006c3f0`

## callees

- `0x18006a608`
- `0x18006ce30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cfd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cfd0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006ceed`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006ceed`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006ce82`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006ce82`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006cf80`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006cf80`
- `ntdll!WinSqmSetString` at `0x18006cfc0`
- `ntdll!WinSqmSetString` at `0x18006cfc0`

## string_xrefs

- `0x18006cf99`: `RegSetValueEx`
- `0x18006ce47`: `SQMBitLockerAlreadySet`
- `0x18006cf6b`: `SQMBitLockerAlreadySet`
- `0x18006cf1a`: `onecore\ds\security\eas\policyengine\utilregs.cxx`
- `0x18006cf06`: `RegCreateKeyEx(SYSTEM\CurrentControlSet\Control\EAS)`

## pseudocode

```c
void SQMBitLockerIfNeeded(void)
{
  unsigned int ValueW; // eax
  unsigned int v1; // eax
  unsigned int v2; // eax
  DWORD dwOptions[2]; // [rsp+20h] [rbp-38h]
  DWORD dwOptionsa[2]; // [rsp+20h] [rbp-38h]
  DWORD dwOptionsb[2]; // [rsp+20h] [rbp-38h]
  int v6; // [rsp+60h] [rbp+8h] BYREF
  DWORD v7; // [rsp+68h] [rbp+10h] BYREF
  int Data; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  v6 = 0;
  v7 = 4;
  hKey = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Control\\EAS",
             L"SQMBitLockerAlreadySet",
             0x10u,
             0,
             &v6,
             &v7);
  if ( ValueW - 2 <= 1 )
    goto LABEL_4;
  if ( ValueW )
  {
    dwOptions[0] = 679;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      ValueW,
      L"onecore\\ds\\security\\eas\\policyengine\\utilregs.cxx",
      *(_QWORD *)dwOptions,
      L"RegGetValueW(SYSTEM\\CurrentControlSet\\Control\\EAS)",
      &Class);
  }
  else if ( !v6 )
  {
LABEL_4:
    Data = 1;
    v1 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\EAS", 0, 0, 0, 3u, 0, &hKey, 0);
    if ( v1 )
    {
      dwOptionsa[0] = 656;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        v1,
        L"onecore\\ds\\security\\eas\\policyengine\\utilregs.cxx",
        *(_QWORD *)dwOptionsa,
        L"RegCreateKeyEx(SYSTEM\\CurrentControlSet\\Control\\EAS)",
        &Class);
    }
    else
    {
      v2 = RegSetValueExW(hKey, L"SQMBitLockerAlreadySet", 0, 4u, (const BYTE *)&Data, 4u);
      if ( v2 )
      {
        dwOptionsb[0] = 666;
        DbgPrintfW(
          1u,
          L"(0x%08x) %ws:%u : %ws:%ws\n",
          v2,
          L"onecore\\ds\\security\\eas\\policyengine\\utilregs.cxx",
          *(_QWORD *)dwOptionsb,
          L"RegSetValueEx",
          &Class);
      }
      else
      {
        WinSqmSetString(0, 11705, L"BitLocker");
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18006ce30  mov     r11, rsp
0x18006ce33  sub     rsp, 58h
0x18006ce37  lea     rax, [r11+10h]
0x18006ce3b  mov     [rsp+58h+arg_0], 0
0x18006ce43  mov     [r11-28h], rax
0x18006ce47  lea     r8, aSqmbitlockeral; "SQMBitLockerAlreadySet"
0x18006ce4e  lea     rax, [r11+8]
0x18006ce52  mov     [rsp+58h+arg_8], 4
0x18006ce5a  mov     [r11-30h], rax
0x18006ce5e  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\EAS"
0x18006ce65  mov     r9d, 10h; dwFlags
0x18006ce6b  mov     qword ptr [r11-38h], 0
0x18006ce73  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18006ce7a  mov     qword ptr [r11+20h], 0
0x18006ce82  call    cs:__imp_RegGetValueW
0x18006ce88  mov     r8d, eax
0x18006ce8b  lea     ecx, [rax-2]
0x18006ce8e  cmp     ecx, 1
0x18006ce91  jbe     short loc_18006CEA5
0x18006ce93  test    eax, eax
0x18006ce95  jnz     loc_18006CF37
0x18006ce9b  cmp     [rsp+58h+arg_0], eax
0x18006ce9f  jnz     loc_18006CFC6
0x18006cea5  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18006ceae  lea     rax, [rsp+58h+hKey]
0x18006ceb3  mov     [rsp+58h+phkResult], rax; phkResult
0x18006ceb8  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\EAS"
0x18006cebf  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006cec8  xor     r9d, r9d; lpClass
0x18006cecb  mov     [rsp+58h+samDesired], 3; samDesired
0x18006ced3  xor     r8d, r8d; Reserved
0x18006ced6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006cedd  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18006cee5  mov     [rsp+58h+Data], 1
0x18006ceed  call    cs:__imp_RegCreateKeyExW
0x18006cef3  mov     r8d, eax
0x18006cef6  test    eax, eax
0x18006cef8  jz      short loc_18006CF59
0x18006cefa  lea     rax, Class
0x18006cf01  mov     [rsp+58h+lpSecurityAttributes], rax
0x18006cf06  lea     rax, aRegcreatekeyex_0; "RegCreateKeyEx(SYSTEM\\CurrentControlSe"...
0x18006cf0d  mov     qword ptr [rsp+58h+samDesired], rax
0x18006cf12  mov     [rsp+58h+dwOptions], 290h
0x18006cf1a  lea     r9, aOnecoreDsSecur_4; "onecore\\ds\\security\\eas\\policyengin"...
0x18006cf21  mov     ecx, 1; unsigned int
0x18006cf26  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006cf2d  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006cf32  jmp     loc_18006CFC6
0x18006cf37  lea     rax, Class
0x18006cf3e  mov     [rsp+58h+lpSecurityAttributes], rax
0x18006cf43  lea     rax, aReggetvaluewSy; "RegGetValueW(SYSTEM\\CurrentControlSet"...
0x18006cf4a  mov     qword ptr [rsp+58h+samDesired], rax
0x18006cf4f  mov     [rsp+58h+dwOptions], 2A7h
0x18006cf57  jmp     short loc_18006CF1A
0x18006cf59  mov     rcx, [rsp+58h+hKey]; hKey
0x18006cf5e  lea     rax, [rsp+58h+Data]
0x18006cf63  mov     [rsp+58h+samDesired], 4; cbData
0x18006cf6b  lea     rdx, aSqmbitlockeral; "SQMBitLockerAlreadySet"
0x18006cf72  mov     r9d, 4; dwType
0x18006cf78  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18006cf7d  xor     r8d, r8d; Reserved
0x18006cf80  call    cs:__imp_RegSetValueExW
0x18006cf86  mov     r8d, eax
0x18006cf89  test    eax, eax
0x18006cf8b  jz      short loc_18006CFB2
0x18006cf8d  lea     rax, Class
0x18006cf94  mov     [rsp+58h+lpSecurityAttributes], rax
0x18006cf99  lea     rax, aRegsetvalueex; "RegSetValueEx"
0x18006cfa0  mov     qword ptr [rsp+58h+samDesired], rax
0x18006cfa5  mov     [rsp+58h+dwOptions], 29Ah
0x18006cfad  jmp     loc_18006CF1A
0x18006cfb2  lea     r8, aBitlocker; "BitLocker"
0x18006cfb9  mov     edx, 2DB9h
0x18006cfbe  xor     ecx, ecx
0x18006cfc0  call    cs:__imp_WinSqmSetString
0x18006cfc6  mov     rcx, [rsp+58h+hKey]; hKey
0x18006cfcb  test    rcx, rcx
0x18006cfce  jz      short loc_18006CFD6
0x18006cfd0  call    cs:__imp_RegCloseKey
0x18006cfd6  add     rsp, 58h
0x18006cfda  retn
```
