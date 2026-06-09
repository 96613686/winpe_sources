# __std_tzdb_get_leap_seconds

- ea: `0x18007de48`
- end: `0x18007df8e`
- name: `__std_tzdb_get_leap_seconds`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800632b8`

## callees

- `0x18007de48`
- `0x180095ea4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007df76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007df76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007df6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007df6a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007de8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007de8c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007deca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007df43`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007deca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007df43`

## pseudocode

```c
BYTE *__fastcall _std_tzdb_get_leap_seconds(unsigned __int64 a1, unsigned __int64 *a2)
{
  LSTATUS v5; // edi
  unsigned __int64 v6; // rcx
  BYTE *lpData; // rsi
  unsigned __int64 v8; // rax
  BYTE *v9; // [rsp+30h] [rbp-28h]
  DWORD cbData; // [rsp+68h] [rbp+10h] BYREF
  LSTATUS v12; // [rsp+70h] [rbp+18h]
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  *a2 = 0;
  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\LeapSecondInformation",
         0,
         0x20019u,
         &hKey) )
  {
    return 0;
  }
  cbData = 0;
  v5 = RegQueryValueExW(hKey, L"LeapSeconds", 0, 0, 0, &cbData);
  v12 = v5;
  v6 = cbData / 0xC;
  *a2 = v6;
  lpData = 0;
  if ( (!v5 || v5 == 234) && v6 > a1 )
  {
    v8 = 12 * v6;
    if ( !is_mul_ok(v6, 0xCu) )
      v8 = -1;
    try
    {
      lpData = (BYTE *)operator new[](v8);
      v9 = lpData;
      v5 = RegQueryValueExW(hKey, L"LeapSeconds", 0, 0, lpData, &cbData);
      v12 = v5;
      if ( v5 )
        *a2 = 0;
    }
    catch ( ... )
    {
      v5 = v12;
      lpData = v9;
    }
  }
  RegCloseKey(hKey);
  if ( v5 )
    SetLastError(v5);
  return lpData;
}

```

## disassembly

```asm
0x18007de48  mov     r11, rsp
0x18007de4b  mov     [r11+8], rsi
0x18007de4f  push    rdi
0x18007de50  push    r14
0x18007de52  push    r15
0x18007de54  sub     rsp, 40h
0x18007de58  mov     r14, rdx
0x18007de5b  mov     r15, rcx
0x18007de5e  mov     qword ptr [rdx], 0
0x18007de65  mov     qword ptr [r11+20h], 0
0x18007de6d  lea     rax, [r11+20h]
0x18007de71  mov     [r11-38h], rax
0x18007de75  mov     r9d, 20019h; samDesired
0x18007de7b  xor     r8d, r8d; ulOptions
0x18007de7e  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Lea"...
0x18007de85  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007de8c  call    cs:__imp_RegOpenKeyExW
0x18007de92  test    eax, eax
0x18007de94  jz      short loc_18007DE9D
0x18007de96  xor     eax, eax
0x18007de98  jmp     loc_18007DF7F
0x18007de9d  mov     [rsp+58h+cbData], 0
0x18007dea5  lea     rax, [rsp+58h+cbData]
0x18007deaa  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18007deaf  mov     [rsp+58h+lpData], 0; lpData
0x18007deb8  xor     r9d, r9d; lpType
0x18007debb  xor     r8d, r8d; lpReserved
0x18007debe  lea     rdx, ValueName; "LeapSeconds"
0x18007dec5  mov     rcx, [rsp+58h+hKey]; hKey
0x18007deca  call    cs:__imp_RegQueryValueExW
0x18007ded0  mov     edi, eax
0x18007ded2  mov     [rsp+58h+arg_10], eax
0x18007ded6  mov     eax, 0AAAAAAABh
0x18007dedb  mul     [rsp+58h+cbData]
0x18007dedf  shr     edx, 3
0x18007dee2  mov     ecx, edx
0x18007dee4  mov     [r14], rcx
0x18007dee7  xor     esi, esi
0x18007dee9  mov     [rsp+58h+var_28], rsi
0x18007deee  test    edi, edi
0x18007def0  jz      short loc_18007DEFA
0x18007def2  cmp     edi, 0EAh
0x18007def8  jnz     short loc_18007DF65
0x18007defa  cmp     rcx, r15
0x18007defd  jbe     short loc_18007DF65
0x18007deff  mov     eax, 0Ch
0x18007df04  mul     rcx
0x18007df07  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18007df0e  cmovb   rax, rcx
0x18007df12  mov     rcx, rax; unsigned __int64
0x18007df15  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007df1a  mov     rsi, rax
0x18007df1d  mov     [rsp+58h+var_28], rax
0x18007df22  lea     rax, [rsp+58h+cbData]
0x18007df27  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18007df2c  mov     [rsp+58h+lpData], rsi; lpData
0x18007df31  xor     r9d, r9d; lpType
0x18007df34  xor     r8d, r8d; lpReserved
0x18007df37  lea     rdx, ValueName; "LeapSeconds"
0x18007df3e  mov     rcx, [rsp+58h+hKey]; hKey
0x18007df43  call    cs:__imp_RegQueryValueExW
0x18007df49  mov     edi, eax
0x18007df4b  mov     [rsp+58h+arg_10], eax
0x18007df4f  test    eax, eax
0x18007df51  jz      short loc_18007DF5A
0x18007df53  mov     qword ptr [r14], 0
0x18007df5a  jmp     short loc_18007DF65
0x18007df5c  mov     edi, [rsp+58h+arg_10]
0x18007df60  mov     rsi, [rsp+58h+var_28]
0x18007df65  mov     rcx, [rsp+58h+hKey]; hKey
0x18007df6a  call    cs:__imp_RegCloseKey
0x18007df70  test    edi, edi
0x18007df72  jz      short loc_18007DF7C
0x18007df74  mov     ecx, edi; dwErrCode
0x18007df76  call    cs:__imp_SetLastError
0x18007df7c  mov     rax, rsi
0x18007df7f  mov     rsi, [rsp+58h+arg_0]
0x18007df84  add     rsp, 40h
0x18007df88  pop     r15
0x18007df8a  pop     r14
0x18007df8c  pop     rdi
0x18007df8d  retn
```
