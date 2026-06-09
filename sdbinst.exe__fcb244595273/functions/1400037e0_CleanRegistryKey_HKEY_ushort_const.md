# CleanRegistryKey(HKEY__ *,ushort const *)

- ea: `0x1400037e0`
- end: `0x1400038e9`
- name: `?CleanRegistryKey@@YAHPEAUHKEY__@@PEBG@Z`
- size: `265`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140008500`

## callees

- `0x1400037e0`
- `0x140006238`
- `0x14002e420`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x14000388b`
- `ADVAPI32!RegEnumValueW` at `0x14000388b`
- `ADVAPI32!RegDeleteValueW` at `0x140003854`
- `ADVAPI32!RegDeleteValueW` at `0x140003854`
- `ADVAPI32!RegOpenKeyExW` at `0x14000382a`
- `ADVAPI32!RegOpenKeyExW` at `0x14000382a`
- `ADVAPI32!RegCloseKey` at `0x1400038a7`
- `ADVAPI32!RegCloseKey` at `0x1400038a7`

## pseudocode

```c
__int64 __fastcall CleanRegistryKey(HKEY a1, const unsigned __int16 *a2)
{
  LSTATUS v2; // eax
  HKEY v3; // rcx
  unsigned int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // eax
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR ValueName[264]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  cchValueName = 0;
  v2 = RegOpenKeyExW(a1, a2, 0, 0x2011Bu, &hKey);
  v3 = hKey;
  if ( v2 || !hKey )
  {
LABEL_9:
    v4 = 1;
  }
  else
  {
    v4 = 0;
    while ( 1 )
    {
      cchValueName = 260;
      v6 = RegEnumValueW(v3, 0, ValueName, &cchValueName, 0, 0, 0, 0);
      if ( v6 == 259 )
      {
        v3 = hKey;
        goto LABEL_9;
      }
      if ( v6 )
        break;
      v5 = RegDeleteValueW(hKey, ValueName);
      if ( v5 )
      {
        PrintMessage(0x422u, v5);
        goto LABEL_15;
      }
      v3 = hKey;
    }
    PrintMessage(0x421u, v6);
LABEL_15:
    v3 = hKey;
  }
  if ( v3 )
    RegCloseKey(v3);
  return v4;
}

```

## disassembly

```asm
0x1400037e0  mov     [rsp-8+arg_10], rbx
0x1400037e5  push    rbp
0x1400037e6  lea     rbp, [rsp-170h]
0x1400037ee  sub     rsp, 270h
0x1400037f5  mov     rax, cs:__security_cookie
0x1400037fc  xor     rax, rsp
0x1400037ff  mov     [rbp+170h+var_10], rax
0x140003806  lea     rax, [rsp+270h+hKey]
0x14000380b  mov     [rsp+270h+hKey], 0
0x140003814  mov     r9d, 2011Bh; samDesired
0x14000381a  mov     [rsp+270h+phkResult], rax; phkResult
0x14000381f  xor     r8d, r8d; ulOptions
0x140003822  mov     [rsp+270h+cchValueName], 0
0x14000382a  call    cs:__imp_RegOpenKeyExW
0x140003830  mov     rcx, [rsp+270h+hKey]
0x140003835  test    eax, eax
0x140003837  jnz     short loc_14000389D
0x140003839  test    rcx, rcx
0x14000383c  jz      short loc_14000389D
0x14000383e  xor     ebx, ebx
0x140003840  jmp     short loc_140003863
0x140003842  test    eax, eax
0x140003844  jnz     loc_1400038D6
0x14000384a  mov     rcx, [rsp+270h+hKey]; hKey
0x14000384f  lea     rdx, [rsp+270h+ValueName]; lpValueName
0x140003854  call    cs:__imp_RegDeleteValueW
0x14000385a  test    eax, eax
0x14000385c  jnz     short loc_1400038CF
0x14000385e  mov     rcx, [rsp+270h+hKey]; hKey
0x140003863  mov     [rsp+270h+lpcbData], rbx; lpcbData
0x140003868  lea     r9, [rsp+270h+cchValueName]; lpcchValueName
0x14000386d  mov     [rsp+270h+lpData], rbx; lpData
0x140003872  lea     r8, [rsp+270h+ValueName]; lpValueName
0x140003877  mov     [rsp+270h+lpType], rbx; lpType
0x14000387c  xor     edx, edx; dwIndex
0x14000387e  mov     [rsp+270h+phkResult], rbx; lpReserved
0x140003883  mov     [rsp+270h+cchValueName], 104h
0x14000388b  call    cs:__imp_RegEnumValueW
0x140003891  cmp     eax, 103h
0x140003896  jnz     short loc_140003842
0x140003898  mov     rcx, [rsp+270h+hKey]; hKey
0x14000389d  mov     ebx, 1
0x1400038a2  test    rcx, rcx
0x1400038a5  jz      short loc_1400038AD
0x1400038a7  call    cs:__imp_RegCloseKey
0x1400038ad  mov     eax, ebx
0x1400038af  mov     rcx, [rbp+170h+var_10]
0x1400038b6  xor     rcx, rsp; StackCookie
0x1400038b9  call    __security_check_cookie
0x1400038be  mov     rbx, [rsp+270h+arg_10]
0x1400038c6  add     rsp, 270h
0x1400038cd  pop     rbp
0x1400038ce  retn
0x1400038cf  mov     ecx, 422h
0x1400038d4  jmp     short loc_1400038DB
0x1400038d6  mov     ecx, 421h; unsigned int
0x1400038db  mov     edx, eax
0x1400038dd  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400038e2  mov     rcx, [rsp+270h+hKey]
0x1400038e7  jmp     short loc_1400038A2
```
