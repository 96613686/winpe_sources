# MachineKeyWasCreatedAfterInstall(HKEY__ *)

- ea: `0x18004734c`
- end: `0x18004741c`
- name: `?MachineKeyWasCreatedAfterInstall@@YAHPEAUHKEY__@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180046c40`

## callees

- `0x18000d56c`
- `0x18004734c`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x1800473f4`
- `KERNEL32!CompareFileTime` at `0x1800473f4`
- `ADVAPI32!RegCloseKey` at `0x18004740c`
- `ADVAPI32!RegCloseKey` at `0x18004740c`
- `ADVAPI32!RegQueryValueExW` at `0x1800473a8`
- `ADVAPI32!RegQueryValueExW` at `0x1800473d6`
- `ADVAPI32!RegQueryValueExW` at `0x1800473a8`
- `ADVAPI32!RegQueryValueExW` at `0x1800473d6`

## string_xrefs

- `0x1800473ca`: `LastInstallTime`

## pseudocode

```c
__int64 __fastcall MachineKeyWasCreatedAfterInstall(HKEY hKey)
{
  unsigned int v2; // ebx
  DWORD Type; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-18h] BYREF
  FILETIME Data; // [rsp+40h] [rbp-10h] BYREF
  FILETIME lpData; // [rsp+48h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+28h] BYREF
  DWORD lpcbData; // [rsp+80h] [rbp+30h] BYREF
  DWORD v10; // [rsp+88h] [rbp+38h] BYREF

  hKeya = 0;
  cbData = 8;
  lpcbData = 8;
  v2 = 0;
  if ( !(unsigned int)CRegInfo::OpenCurrentVersionKey(&hKeya, 0x20019u, 1, 0)
    && !RegQueryValueExW(hKey, L"AutoGenKeyCreationTime", 0, &Type, (LPBYTE)&Data, &cbData)
    && (RegQueryValueExW(hKeya, L"LastInstallTime", 0, &v10, (LPBYTE)&lpData, &lpcbData)
     || v10 == 11 && Type == 11 && CompareFileTime(&lpData, &Data) < 0) )
  {
    v2 = 1;
  }
  if ( hKeya )
    RegCloseKey(hKeya);
  return v2;
}

```

## disassembly

```asm
0x18004734c  push    rbp
0x18004734e  push    rbx
0x18004734f  push    rdi
0x180047350  mov     rbp, rsp
0x180047353  sub     rsp, 50h
0x180047357  and     [rbp+hKey], 0
0x18004735c  mov     eax, 8
0x180047361  mov     rdi, rcx
0x180047364  mov     [rbp+cbData], eax
0x180047367  xor     r9d, r9d; int
0x18004736a  mov     [rbp+arg_10], eax
0x18004736d  mov     edx, 20019h; samDesired
0x180047372  lea     rcx, [rbp+hKey]; dwOptions
0x180047376  lea     r8d, [rax-7]; int
0x18004737a  xor     ebx, ebx
0x18004737c  call    ?OpenCurrentVersionKey@CRegInfo@@SAJPEAPEAUHKEY__@@KHH@Z; CRegInfo::OpenCurrentVersionKey(HKEY__ * *,ulong,int,int)
0x180047381  test    eax, eax
0x180047383  jnz     short loc_180047403
0x180047385  lea     rax, [rbp+cbData]
0x180047389  xor     r8d, r8d; lpReserved
0x18004738c  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180047391  lea     r9, [rbp+Type]; lpType
0x180047395  lea     rax, [rbp+Data]
0x180047399  mov     rcx, rdi; hKey
0x18004739c  lea     rdx, aAutogenkeycrea; "AutoGenKeyCreationTime"
0x1800473a3  mov     [rsp+50h+lpData], rax; lpData
0x1800473a8  call    cs:__imp_RegQueryValueExW
0x1800473ae  test    eax, eax
0x1800473b0  jnz     short loc_180047403
0x1800473b2  mov     rcx, [rbp+hKey]; hKey
0x1800473b6  lea     rax, [rbp+arg_10]
0x1800473ba  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800473bf  lea     r9, [rbp+arg_18]; lpType
0x1800473c3  lea     rax, [rbp+var_8]
0x1800473c7  xor     r8d, r8d; lpReserved
0x1800473ca  lea     rdx, aLastinstalltim; "LastInstallTime"
0x1800473d1  mov     [rsp+50h+lpData], rax; lpData
0x1800473d6  call    cs:__imp_RegQueryValueExW
0x1800473dc  test    eax, eax
0x1800473de  jnz     short loc_1800473FE
0x1800473e0  cmp     [rbp+arg_18], 0Bh
0x1800473e4  jnz     short loc_180047403
0x1800473e6  cmp     [rbp+Type], 0Bh
0x1800473ea  jnz     short loc_180047403
0x1800473ec  lea     rdx, [rbp+Data]; lpFileTime2
0x1800473f0  lea     rcx, [rbp+var_8]; lpFileTime1
0x1800473f4  call    cs:__imp_CompareFileTime
0x1800473fa  test    eax, eax
0x1800473fc  jns     short loc_180047403
0x1800473fe  mov     ebx, 1
0x180047403  mov     rcx, [rbp+hKey]; hKey
0x180047407  test    rcx, rcx
0x18004740a  jz      short loc_180047412
0x18004740c  call    cs:__imp_RegCloseKey
0x180047412  mov     eax, ebx
0x180047414  add     rsp, 50h
0x180047418  pop     rdi
0x180047419  pop     rbx
0x18004741a  pop     rbp
0x18004741b  retn
```
