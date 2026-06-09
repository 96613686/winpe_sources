# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180003398`
- end: `0x1800034e8`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `336`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003398`
- `0x1800038f0`

## callees

- `0x180001470`
- `0x180002cf8`
- `0x180003398`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000341f`
- `ADVAPI32!RegCloseKey` at `0x180003495`
- `ADVAPI32!RegCloseKey` at `0x1800034b9`
- `ADVAPI32!RegCloseKey` at `0x18000341f`
- `ADVAPI32!RegCloseKey` at `0x180003495`
- `ADVAPI32!RegCloseKey` at `0x1800034b9`
- `ADVAPI32!RegOpenKeyExW` at `0x180003402`
- `ADVAPI32!RegOpenKeyExW` at `0x180003402`
- `ADVAPI32!RegEnumKeyExW` at `0x180003481`
- `ADVAPI32!RegEnumKeyExW` at `0x180003481`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  DWORD v4; // ebx
  HKEY v5; // rcx
  HKEY v6; // rcx
  DWORD cchName[2]; // [rsp+48h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+50h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+70h] [rbp-98h] BYREF
  __int64 v12; // [rsp+78h] [rbp-90h]
  WCHAR Name[256]; // [rsp+88h] [rbp-80h] BYREF

  v12 = -2;
  memset(hKey, 0, sizeof(hKey));
  phkResult = 0;
  v4 = RegOpenKeyExW(*this, a2, 0, 0x2001Fu, &phkResult);
  v5 = 0;
  if ( !v4 )
  {
    v6 = phkResult;
    hKey[0] = phkResult;
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName[0] = 256;
      if ( RegEnumKeyExW(v6, 0, Name, cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v4 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      if ( v4 )
        goto LABEL_9;
      v6 = hKey[0];
    }
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
LABEL_9:
    v5 = hKey[0];
  }
  if ( v5 )
    RegCloseKey(v5);
  return v4;
}

```

## disassembly

```asm
0x180003398  mov     rax, rsp
0x18000339b  push    rbp
0x18000339c  push    rdi
0x18000339d  push    r14
0x18000339f  lea     rbp, [rax-1A8h]
0x1800033a6  sub     rsp, 290h
0x1800033ad  mov     [rsp+2A0h+var_230], 0FFFFFFFFFFFFFFFEh
0x1800033b6  mov     [rax+18h], rbx
0x1800033ba  mov     [rax+20h], rsi
0x1800033be  mov     rax, cs:__security_cookie
0x1800033c5  xor     rax, rsp
0x1800033c8  mov     [rbp+1A0h+var_20], rax
0x1800033cf  mov     rsi, rdx
0x1800033d2  mov     rdi, rcx
0x1800033d5  xor     r14d, r14d
0x1800033d8  mov     [rsp+2A0h+hKey], r14
0x1800033dd  mov     [rsp+2A0h+var_250], r14
0x1800033e2  mov     [rsp+2A0h+var_248], r14
0x1800033e7  mov     [rsp+2A0h+var_240], r14
0x1800033ec  lea     rax, [rsp+2A0h+var_240]
0x1800033f1  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800033f6  mov     r9d, 2001Fh; samDesired
0x1800033fc  xor     r8d, r8d; ulOptions
0x1800033ff  mov     rcx, [rcx]; hKey
0x180003402  call    cs:__imp_RegOpenKeyExW
0x180003408  mov     ebx, eax
0x18000340a  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000340f  test    eax, eax
0x180003411  jnz     loc_1800034B4
0x180003417  mov     ebx, r14d
0x18000341a  test    rcx, rcx
0x18000341d  jz      short loc_180003427
0x18000341f  call    cs:__imp_RegCloseKey
0x180003425  mov     ebx, eax
0x180003427  mov     rcx, [rsp+2A0h+var_240]
0x18000342c  mov     [rsp+2A0h+hKey], rcx
0x180003431  test    ebx, ebx
0x180003433  jnz     short loc_1800034B4
0x180003435  mov     qword ptr [rsp+2A0h+ftLastWriteTime.dwLowDateTime], r14
0x18000343a  jmp     short loc_180003455
0x18000343c  lea     rdx, [rbp+1A0h+Name]; unsigned __int16 *
0x180003440  lea     rcx, [rsp+2A0h+hKey]; this
0x180003445  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000344a  mov     ebx, eax
0x18000344c  test    eax, eax
0x18000344e  jnz     short loc_1800034AD
0x180003450  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180003455  lea     rax, [rsp+2A0h+ftLastWriteTime]
0x18000345a  mov     [rsp+2A0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000345f  mov     [rsp+2A0h+lpcchClass], r14; lpcchClass
0x180003464  mov     [rsp+2A0h+lpClass], r14; lpClass
0x180003469  mov     [rsp+2A0h+phkResult], r14; lpReserved
0x18000346e  mov     [rsp+2A0h+cchName], 100h
0x180003476  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x18000347b  lea     r8, [rbp+1A0h+Name]; lpName
0x18000347f  xor     edx, edx; dwIndex
0x180003481  call    cs:__imp_RegEnumKeyExW
0x180003487  test    eax, eax
0x180003489  jz      short loc_18000343C
0x18000348b  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180003490  test    rcx, rcx
0x180003493  jz      short loc_1800034A0
0x180003495  call    cs:__imp_RegCloseKey
0x18000349b  mov     [rsp+2A0h+hKey], r14
0x1800034a0  mov     rdx, rsi; unsigned __int16 *
0x1800034a3  mov     rcx, rdi; this
0x1800034a6  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800034ab  mov     ebx, eax
0x1800034ad  mov     rcx, [rsp+2A0h+hKey]
0x1800034b2  jmp     short $+2
0x1800034b4  test    rcx, rcx
0x1800034b7  jz      short loc_1800034BF
0x1800034b9  call    cs:__imp_RegCloseKey
0x1800034bf  mov     eax, ebx
0x1800034c1  mov     rcx, [rbp+1A0h+var_20]
0x1800034c8  xor     rcx, rsp; StackCookie
0x1800034cb  call    __security_check_cookie
0x1800034d0  lea     r11, [rsp+2A0h+var_10]
0x1800034d8  mov     rbx, [r11+30h]
0x1800034dc  mov     rsi, [r11+38h]
0x1800034e0  mov     rsp, r11
0x1800034e3  pop     r14
0x1800034e5  pop     rdi
0x1800034e6  pop     rbp
0x1800034e7  retn
```
