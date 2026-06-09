# ReadWABCustomColumnProps(AddressBook *)

- ea: `0x18001cdf4`
- end: `0x18001cf7d`
- name: `?ReadWABCustomColumnProps@@YAXPEAVAddressBook@@@Z`
- size: `393`
- prototype: `void __fastcall(struct AddressBook *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180060850`
- `0x180075194`

## callees

- `0x1800045e4`
- `0x18001cdf4`
- `0x18006314c`
- `0x180091ef0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18001ce78`
- `ADVAPI32!RegOpenKeyExW` at `0x18001ce78`
- `ADVAPI32!RegCloseKey` at `0x18001cf5c`
- `ADVAPI32!RegCloseKey` at `0x18001cf5c`
- `ADVAPI32!RegQueryValueExW` at `0x18001cf0b`
- `ADVAPI32!RegQueryValueExW` at `0x18001cf0b`

## pseudocode

```c
void __fastcall ReadWABCustomColumnProps(struct AddressBook *a1)
{
  __int64 v1; // rcx
  int i; // ebx
  unsigned __int16 *v3; // rdi
  unsigned int *v4; // rsi
  const WCHAR *v5; // rdx
  unsigned int v6; // r8d
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v11[264]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  if ( !a1 || (v1 = *((_QWORD *)a1 + 132)) == 0 )
    v1 = -2147483647;
  PR_WAB_CUSTOMPROP2 = 0;
  LOWORD(szCustomProp1) = 0;
  szCustomProp2 = 0;
  PR_WAB_CUSTOMPROP1 = 0;
  if ( !RegOpenKeyExW((HKEY)v1, L"Software\\Microsoft\\WAB\\WAB4", 0, 0x20019u, &hKey) )
  {
    for ( i = 0; i < 2; ++i )
    {
      cbData = 4;
      v3 = (unsigned __int16 *)&szCustomProp1;
      Type = 0;
      if ( i )
        v3 = &szCustomProp2;
      *(_DWORD *)Data = 0;
      v4 = &PR_WAB_CUSTOMPROP1;
      if ( i )
        v4 = &PR_WAB_CUSTOMPROP2;
      v5 = L"PropTag1";
      v11[0] = 0;
      if ( i )
        v5 = L"PropTag2";
      if ( !RegQueryValueExW(hKey, v5, 0, &Type, Data, &cbData) && *(_DWORD *)Data && *(_WORD *)Data == 31 )
      {
        if ( (unsigned int)ColSel_PropTagToString(*(unsigned int *)Data, v11, v6) )
        {
          StringCchCopyW(v3, 0x104u, v11);
          *v4 = *(_DWORD *)Data;
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18001cdf4  push    rbp
0x18001cdf6  push    rbx
0x18001cdf7  push    rsi
0x18001cdf8  push    rdi
0x18001cdf9  lea     rbp, [rsp-178h]
0x18001ce01  sub     rsp, 278h
0x18001ce08  mov     rax, cs:__security_cookie
0x18001ce0f  xor     rax, rsp
0x18001ce12  mov     [rbp+190h+var_30], rax
0x18001ce19  mov     [rsp+290h+hKey], 0
0x18001ce22  test    rcx, rcx
0x18001ce25  jz      short loc_18001CE33
0x18001ce27  mov     rcx, [rcx+420h]
0x18001ce2e  test    rcx, rcx
0x18001ce31  jnz     short loc_18001CE3A
0x18001ce33  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001ce3a  xor     eax, eax
0x18001ce3c  mov     cs:?PR_WAB_CUSTOMPROP2@@3KA, 0; ulong PR_WAB_CUSTOMPROP2
0x18001ce46  mov     cs:?szCustomProp1@@3PAGA, ax; ushort near * szCustomProp1
0x18001ce4d  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\WAB\\WAB4"
0x18001ce54  mov     cs:?szCustomProp2@@3PAGA, ax; ushort near * szCustomProp2
0x18001ce5b  mov     r9d, 20019h; samDesired
0x18001ce61  lea     rax, [rsp+290h+hKey]
0x18001ce66  mov     cs:?PR_WAB_CUSTOMPROP1@@3KA, 0; ulong PR_WAB_CUSTOMPROP1
0x18001ce70  xor     r8d, r8d; ulOptions
0x18001ce73  mov     [rsp+290h+phkResult], rax; phkResult
0x18001ce78  call    cs:__imp_RegOpenKeyExW
0x18001ce7e  test    eax, eax
0x18001ce80  jnz     loc_18001CF52
0x18001ce86  xor     ebx, ebx
0x18001ce88  cmp     ebx, 2
0x18001ce8b  jge     loc_18001CF52
0x18001ce91  mov     rcx, [rsp+290h+hKey]; hKey
0x18001ce96  lea     rax, ?szCustomProp2@@3PAGA; ushort near * szCustomProp2
0x18001ce9d  test    ebx, ebx
0x18001ce9f  mov     [rsp+290h+cbData], 4
0x18001cea7  lea     rdi, ?szCustomProp1@@3PAGA; ushort near * szCustomProp1
0x18001ceae  mov     [rsp+290h+Type], 0
0x18001ceb6  cmovnz  rdi, rax
0x18001ceba  mov     dword ptr [rsp+290h+Data], 0
0x18001cec2  lea     rax, ?PR_WAB_CUSTOMPROP2@@3KA; ulong PR_WAB_CUSTOMPROP2
0x18001cec9  lea     rsi, ?PR_WAB_CUSTOMPROP1@@3KA; ulong PR_WAB_CUSTOMPROP1
0x18001ced0  cmovnz  rsi, rax
0x18001ced4  lea     rdx, aProptag1; "PropTag1"
0x18001cedb  xor     eax, eax
0x18001cedd  lea     r9, [rsp+290h+Type]; lpType
0x18001cee2  mov     [rsp+290h+var_240], ax
0x18001cee7  test    ebx, ebx
0x18001cee9  lea     rax, aProptag2; "PropTag2"
0x18001cef0  cmovnz  rdx, rax; lpValueName
0x18001cef4  lea     rax, [rsp+290h+cbData]
0x18001cef9  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18001cefe  xor     r8d, r8d; lpReserved
0x18001cf01  lea     rax, [rsp+290h+Data]
0x18001cf06  mov     [rsp+290h+phkResult], rax; lpData
0x18001cf0b  call    cs:__imp_RegQueryValueExW
0x18001cf11  test    eax, eax
0x18001cf13  jnz     short loc_18001CF4B
0x18001cf15  mov     ecx, dword ptr [rsp+290h+Data]; unsigned int
0x18001cf19  test    ecx, ecx
0x18001cf1b  jz      short loc_18001CF4B
0x18001cf1d  cmp     cx, 1Fh
0x18001cf21  jnz     short loc_18001CF4B
0x18001cf23  lea     rdx, [rsp+290h+var_240]; unsigned __int16 *
0x18001cf28  call    ?ColSel_PropTagToString@@YAHKPEAGK@Z; ColSel_PropTagToString(ulong,ushort *,ulong)
0x18001cf2d  test    eax, eax
0x18001cf2f  jz      short loc_18001CF4B
0x18001cf31  lea     r8, [rsp+290h+var_240]; unsigned __int16 *
0x18001cf36  mov     edx, 104h; unsigned __int64
0x18001cf3b  mov     rcx, rdi; unsigned __int16 *
0x18001cf3e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001cf43  mov     r11d, dword ptr [rsp+290h+Data]
0x18001cf48  mov     [rsi], r11d
0x18001cf4b  inc     ebx
0x18001cf4d  jmp     loc_18001CE88
0x18001cf52  mov     rcx, [rsp+290h+hKey]; hKey
0x18001cf57  test    rcx, rcx
0x18001cf5a  jz      short loc_18001CF62
0x18001cf5c  call    cs:__imp_RegCloseKey
0x18001cf62  mov     rcx, [rbp+190h+var_30]
0x18001cf69  xor     rcx, rsp; StackCookie
0x18001cf6c  call    __security_check_cookie
0x18001cf71  add     rsp, 278h
0x18001cf78  pop     rdi
0x18001cf79  pop     rsi
0x18001cf7a  pop     rbx
0x18001cf7b  pop     rbp
0x18001cf7c  retn
```
