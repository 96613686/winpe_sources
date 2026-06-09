# SQMBitLockerIfNeeded(void)

- ea: `0x140099054`
- end: `0x1400991ff`
- name: `?SQMBitLockerIfNeeded@@YAXXZ`
- size: `427`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140037e2c`

## callees

- `0x140038250`
- `0x140099054`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400991a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400991a4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400990a6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400990a6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140099111`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140099111`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400991f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400991f4`
- `ntdll!WinSqmSetString` at `0x1400991e4`
- `ntdll!WinSqmSetString` at `0x1400991e4`

## string_xrefs

- `0x1400991bd`: `RegSetValueEx`
- `0x14009906b`: `SQMBitLockerAlreadySet`
- `0x14009918f`: `SQMBitLockerAlreadySet`
- `0x14009913e`: `onecore\ds\security\eas\policyengine\utilregs.cxx`
- `0x14009912a`: `RegCreateKeyEx(SYSTEM\CurrentControlSet\Control\EAS)`

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
      &pPassword);
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
        &pPassword);
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
          &pPassword);
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
0x140099054  mov     r11, rsp
0x140099057  sub     rsp, 58h
0x14009905b  lea     rax, [r11+10h]
0x14009905f  mov     [rsp+58h+arg_0], 0
0x140099067  mov     [r11-28h], rax
0x14009906b  lea     r8, aSqmbitlockeral; "SQMBitLockerAlreadySet"
0x140099072  lea     rax, [r11+8]
0x140099076  mov     [rsp+58h+arg_8], 4
0x14009907e  mov     [r11-30h], rax
0x140099082  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\EAS"
0x140099089  mov     r9d, 10h; dwFlags
0x14009908f  mov     qword ptr [r11-38h], 0
0x140099097  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14009909e  mov     qword ptr [r11+20h], 0
0x1400990a6  call    cs:__imp_RegGetValueW
0x1400990ac  mov     r8d, eax
0x1400990af  lea     ecx, [rax-2]
0x1400990b2  cmp     ecx, 1
0x1400990b5  jbe     short loc_1400990C9
0x1400990b7  test    eax, eax
0x1400990b9  jnz     loc_14009915B
0x1400990bf  cmp     [rsp+58h+arg_0], eax
0x1400990c3  jnz     loc_1400991EA
0x1400990c9  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1400990d2  lea     rax, [rsp+58h+hKey]
0x1400990d7  mov     [rsp+58h+phkResult], rax; phkResult
0x1400990dc  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\EAS"
0x1400990e3  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400990ec  xor     r9d, r9d; lpClass
0x1400990ef  mov     [rsp+58h+samDesired], 3; samDesired
0x1400990f7  xor     r8d, r8d; Reserved
0x1400990fa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140099101  mov     [rsp+58h+dwOptions], 0; dwOptions
0x140099109  mov     [rsp+58h+Data], 1
0x140099111  call    cs:__imp_RegCreateKeyExW
0x140099117  mov     r8d, eax
0x14009911a  test    eax, eax
0x14009911c  jz      short loc_14009917D
0x14009911e  lea     rax, pPassword
0x140099125  mov     [rsp+58h+lpSecurityAttributes], rax
0x14009912a  lea     rax, aRegcreatekeyex_0; "RegCreateKeyEx(SYSTEM\\CurrentControlSe"...
0x140099131  mov     qword ptr [rsp+58h+samDesired], rax
0x140099136  mov     [rsp+58h+dwOptions], 290h
0x14009913e  lea     r9, aOnecoreDsSecur_5; "onecore\\ds\\security\\eas\\policyengin"...
0x140099145  mov     ecx, 1; unsigned int
0x14009914a  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x140099151  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x140099156  jmp     loc_1400991EA
0x14009915b  lea     rax, pPassword
0x140099162  mov     [rsp+58h+lpSecurityAttributes], rax
0x140099167  lea     rax, aReggetvaluewSy; "RegGetValueW(SYSTEM\\CurrentControlSet"...
0x14009916e  mov     qword ptr [rsp+58h+samDesired], rax
0x140099173  mov     [rsp+58h+dwOptions], 2A7h
0x14009917b  jmp     short loc_14009913E
0x14009917d  mov     rcx, [rsp+58h+hKey]; hKey
0x140099182  lea     rax, [rsp+58h+Data]
0x140099187  mov     [rsp+58h+samDesired], 4; cbData
0x14009918f  lea     rdx, aSqmbitlockeral; "SQMBitLockerAlreadySet"
0x140099196  mov     r9d, 4; dwType
0x14009919c  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1400991a1  xor     r8d, r8d; Reserved
0x1400991a4  call    cs:__imp_RegSetValueExW
0x1400991aa  mov     r8d, eax
0x1400991ad  test    eax, eax
0x1400991af  jz      short loc_1400991D6
0x1400991b1  lea     rax, pPassword
0x1400991b8  mov     [rsp+58h+lpSecurityAttributes], rax
0x1400991bd  lea     rax, aRegsetvalueex; "RegSetValueEx"
0x1400991c4  mov     qword ptr [rsp+58h+samDesired], rax
0x1400991c9  mov     [rsp+58h+dwOptions], 29Ah
0x1400991d1  jmp     loc_14009913E
0x1400991d6  lea     r8, aBitlocker; "BitLocker"
0x1400991dd  mov     edx, 2DB9h
0x1400991e2  xor     ecx, ecx
0x1400991e4  call    cs:__imp_WinSqmSetString
0x1400991ea  mov     rcx, [rsp+58h+hKey]; hKey
0x1400991ef  test    rcx, rcx
0x1400991f2  jz      short loc_1400991FA
0x1400991f4  call    cs:__imp_RegCloseKey
0x1400991fa  add     rsp, 58h
0x1400991fe  retn
```
