# SdpShouldValidateTrust(int *)

- ea: `0x1800077a0`
- end: `0x180007876`
- name: `?SdpShouldValidateTrust@@YAJPEAH@Z`
- size: `214`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011ba4`

## callees

- `0x1800077a0`
- `0x180026fa0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000780e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000780e`
- `ADVAPI32!RegCloseKey` at `0x180007863`
- `ADVAPI32!RegCloseKey` at `0x180007863`
- `ADVAPI32!RegQueryValueExW` at `0x180007843`
- `ADVAPI32!RegQueryValueExW` at `0x180007843`

## pseudocode

```c
__int64 __fastcall SdpShouldValidateTrust(int *a1)
{
  unsigned int v2; // edi
  int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  Data = 0;
  cbData = 4;
  if ( a1 )
  {
    v2 = 0;
    *a1 = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Policies\\Microsoft\\Windows\\ScriptedDiagnostics",
            0,
            0x20019u,
            &hKey) )
    {
      if ( !hKey )
        return v2;
      if ( !RegQueryValueExW(hKey, L"ValidateTrust", 0, 0, (LPBYTE)&Data, &cbData) && Data )
        *a1 = 1;
    }
  }
  else
  {
    v2 = -2147024809;
    SdpDebugTrace(1u, L"SdpShouldValidateTrust", 1099, -2147024809);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x1800077a0  mov     rax, rsp
0x1800077a3  mov     [rax+20h], rbx
0x1800077a7  push    rdi
0x1800077a8  sub     rsp, 30h
0x1800077ac  mov     qword ptr [rax+18h], 0
0x1800077b4  mov     rbx, rcx
0x1800077b7  mov     dword ptr [rax+8], 0
0x1800077be  mov     dword ptr [rax+10h], 4
0x1800077c5  test    rcx, rcx
0x1800077c8  jnz     short loc_1800077E9
0x1800077ca  mov     edi, 80070057h
0x1800077cf  lea     rdx, aSdpshouldvalid; "SdpShouldValidateTrust"
0x1800077d6  mov     r9d, edi; int
0x1800077d9  lea     ecx, [rbx+1]; Level
0x1800077dc  mov     r8d, 44Bh; int
0x1800077e2  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800077e7  jmp     short loc_180007859
0x1800077e9  lea     rax, [rsp+38h+hKey]
0x1800077ee  xor     edi, edi
0x1800077f0  mov     [rcx], edi
0x1800077f2  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x1800077f9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007800  mov     [rsp+38h+phkResult], rax; phkResult
0x180007805  mov     r9d, 20019h; samDesired
0x18000780b  xor     r8d, r8d; ulOptions
0x18000780e  call    cs:__imp_RegOpenKeyExW
0x180007814  test    eax, eax
0x180007816  jnz     short loc_180007859
0x180007818  mov     rcx, [rsp+38h+hKey]; hKey
0x18000781d  test    rcx, rcx
0x180007820  jz      short loc_180007869
0x180007822  lea     rax, [rsp+38h+cbData]
0x180007827  xor     r9d, r9d; lpType
0x18000782a  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000782f  lea     rdx, ValueName; "ValidateTrust"
0x180007836  lea     rax, [rsp+38h+Data]
0x18000783b  xor     r8d, r8d; lpReserved
0x18000783e  mov     [rsp+38h+phkResult], rax; lpData
0x180007843  call    cs:__imp_RegQueryValueExW
0x180007849  test    eax, eax
0x18000784b  jnz     short loc_180007859
0x18000784d  cmp     [rsp+38h+Data], edi
0x180007851  jz      short loc_180007859
0x180007853  mov     dword ptr [rbx], 1
0x180007859  mov     rcx, [rsp+38h+hKey]; hKey
0x18000785e  test    rcx, rcx
0x180007861  jz      short loc_180007869
0x180007863  call    cs:__imp_RegCloseKey
0x180007869  mov     rbx, [rsp+38h+arg_18]
0x18000786e  mov     eax, edi
0x180007870  add     rsp, 30h
0x180007874  pop     rdi
0x180007875  retn
```
