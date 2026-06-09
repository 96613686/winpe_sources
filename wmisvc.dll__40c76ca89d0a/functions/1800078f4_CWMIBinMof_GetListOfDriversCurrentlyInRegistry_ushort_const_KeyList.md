# CWMIBinMof::GetListOfDriversCurrentlyInRegistry(ushort const *,_KeyList &)

- ea: `0x1800078f4`
- end: `0x1800079e7`
- name: `?GetListOfDriversCurrentlyInRegistry@CWMIBinMof@@QEAAHPEBGAEAU_KeyList@@@Z`
- size: `243`
- prototype: `__int64 __fastcall(CWMIBinMof *__hidden this, const unsigned __int16 *, struct _KeyList *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005048`

## callees

- `0x1800078f4`
- `0x18001d3a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180007995`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180007995`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007945`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007945`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800079b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800079b6`
- `wbemcomn!?Add@CWStringArray@@QEAAHPEBG@Z` at `0x1800079a7`
- `wbemcomn!?Add@CWStringArray@@QEAAHPEBG@Z` at `0x1800079a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CWMIBinMof::GetListOfDriversCurrentlyInRegistry(
        CWMIBinMof *this,
        const unsigned __int16 *a2,
        struct _KeyList *a3)
{
  unsigned int v4; // ebx
  DWORD i; // edi
  DWORD cchValueName; // [rsp+40h] [rbp-238h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-230h] BYREF
  WCHAR ValueName[264]; // [rsp+50h] [rbp-228h] BYREF

  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WBEM\\WDM\\DREDGE", 0, 0x20019u, &hKey) )
  {
    return 0;
  }
  else
  {
    v4 = 1;
    for ( i = 0; ; ++i )
    {
      cchValueName = 262;
      if ( RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, 0, 0, 0) )
        break;
      CWStringArray::Add(a3, ValueName);
    }
    RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x1800078f4  mov     [rsp+arg_0], rbx
0x1800078f9  mov     [rsp+arg_8], rsi
0x1800078fe  push    rdi
0x1800078ff  sub     rsp, 270h
0x180007906  mov     rax, cs:__security_cookie
0x18000790d  xor     rax, rsp
0x180007910  mov     [rsp+278h+var_18], rax
0x180007918  mov     rsi, r8
0x18000791b  mov     [rsp+278h+hKey], 0
0x180007924  lea     rax, [rsp+278h+hKey]
0x180007929  xor     r8d, r8d; ulOptions
0x18000792c  mov     r9d, 20019h; samDesired
0x180007932  mov     [rsp+278h+phkResult], rax; phkResult
0x180007937  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\WBEM\\WDM\\DREDGE"
0x18000793e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007945  call    cs:__imp_RegOpenKeyExW
0x18000794b  test    eax, eax
0x18000794d  jnz     loc_1800079E3
0x180007953  lea     ebx, [rax+1]
0x180007956  xor     edi, edi
0x180007958  mov     rcx, [rsp+278h+hKey]; hKey
0x18000795d  lea     r9, [rsp+278h+cchValueName]; lpcchValueName
0x180007962  mov     [rsp+278h+lpcbData], 0; lpcbData
0x18000796b  lea     r8, [rsp+278h+ValueName]; lpValueName
0x180007970  mov     [rsp+278h+lpData], 0; lpData
0x180007979  mov     edx, edi; dwIndex
0x18000797b  mov     [rsp+278h+lpType], 0; lpType
0x180007984  mov     [rsp+278h+phkResult], 0; lpReserved
0x18000798d  mov     [rsp+278h+cchValueName], 106h
0x180007995  call    cs:__imp_RegEnumValueW
0x18000799b  test    eax, eax
0x18000799d  jnz     short loc_1800079B1
0x18000799f  lea     rdx, [rsp+278h+ValueName]
0x1800079a4  mov     rcx, rsi
0x1800079a7  call    cs:__imp_?Add@CWStringArray@@QEAAHPEBG@Z; CWStringArray::Add(ushort const *)
0x1800079ad  add     edi, ebx
0x1800079af  jmp     short loc_180007958
0x1800079b1  mov     rcx, [rsp+278h+hKey]; hKey
0x1800079b6  call    cs:__imp_RegCloseKey
0x1800079bc  mov     eax, ebx
0x1800079be  mov     rcx, [rsp+278h+var_18]
0x1800079c6  xor     rcx, rsp; StackCookie
0x1800079c9  call    __security_check_cookie
0x1800079ce  lea     r11, [rsp+278h+var_8]
0x1800079d6  mov     rbx, [r11+10h]
0x1800079da  mov     rsi, [r11+18h]
0x1800079de  mov     rsp, r11
0x1800079e1  pop     rdi
0x1800079e2  retn
0x1800079e3  xor     ebx, ebx
0x1800079e5  jmp     short loc_1800079BC
```
