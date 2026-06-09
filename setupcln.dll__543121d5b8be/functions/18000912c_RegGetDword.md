# RegGetDword

- ea: `0x18000912c`
- end: `0x18000920c`
- name: `RegGetDword`
- size: `224`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, const WCHAR *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005080`
- `0x1800056c0`

## callees

- `0x18000912c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000916b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800091f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000916b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800091f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000918f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000918f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800091eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800091eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800091c6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800091c6`

## pseudocode

```c
__int64 __fastcall RegGetDword(HKEY a1, const WCHAR *a2, const WCHAR *a3)
{
  DWORD v5; // ecx
  LSTATUS v7; // eax
  LSTATUS v8; // edi
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  unsigned int Data; // [rsp+50h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  Data = 0;
  cbData = 4;
  Type = 0;
  if ( !a1 )
  {
    v5 = 87;
LABEL_3:
    SetLastError(v5);
    return 0;
  }
  if ( a2 )
  {
    v7 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
    if ( v7 || (a1 = hKey) == 0 )
    {
      v5 = v7;
      goto LABEL_3;
    }
  }
  else
  {
    hKey = a1;
  }
  v8 = RegQueryValueExW(a1, a3, 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v8 )
    goto LABEL_12;
  if ( cbData != 4 )
  {
    v8 = 13;
LABEL_12:
    Data = 0;
  }
  if ( a2 )
    RegCloseKey(hKey);
  SetLastError(v8);
  return Data;
}

```

## disassembly

```asm
0x18000912c  mov     [rsp-8+arg_8], rbx
0x180009131  mov     [rsp-8+arg_10], rdi
0x180009136  push    rbp
0x180009137  mov     rbp, rsp
0x18000913a  sub     rsp, 40h
0x18000913e  mov     [rbp+hKey], 0
0x180009146  mov     rdi, r8
0x180009149  mov     [rbp+Data], 0
0x180009150  mov     rbx, rdx
0x180009153  mov     [rbp+cbData], 4
0x18000915a  mov     [rbp+Type], 0
0x180009161  test    rcx, rcx
0x180009164  jnz     short loc_180009178
0x180009166  mov     ecx, 57h ; 'W'; dwErrCode
0x18000916b  call    cs:__imp_SetLastError
0x180009171  xor     eax, eax
0x180009173  jmp     loc_1800091FC
0x180009178  test    rbx, rbx
0x18000917b  jz      short loc_1800091A6
0x18000917d  lea     rax, [rbp+hKey]
0x180009181  mov     r9d, 20019h; samDesired
0x180009187  xor     r8d, r8d; ulOptions
0x18000918a  mov     [rsp+40h+phkResult], rax; phkResult
0x18000918f  call    cs:__imp_RegOpenKeyExW
0x180009195  test    eax, eax
0x180009197  jnz     short loc_1800091A2
0x180009199  mov     rcx, [rbp+hKey]
0x18000919d  test    rcx, rcx
0x1800091a0  jnz     short loc_1800091AA
0x1800091a2  mov     ecx, eax; hKey
0x1800091a4  jmp     short loc_18000916B
0x1800091a6  mov     [rbp+hKey], rcx
0x1800091aa  lea     rax, [rbp+cbData]
0x1800091ae  xor     r8d, r8d; lpReserved
0x1800091b1  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800091b6  lea     r9, [rbp+Type]; lpType
0x1800091ba  lea     rax, [rbp+Data]
0x1800091be  mov     rdx, rdi; lpValueName
0x1800091c1  mov     [rsp+40h+phkResult], rax; lpData
0x1800091c6  call    cs:__imp_RegQueryValueExW
0x1800091cc  mov     edi, eax
0x1800091ce  test    eax, eax
0x1800091d0  jnz     short loc_1800091DB
0x1800091d2  cmp     [rbp+cbData], 4
0x1800091d6  jz      short loc_1800091E2
0x1800091d8  lea     edi, [rax+0Dh]
0x1800091db  mov     [rbp+Data], 0
0x1800091e2  test    rbx, rbx
0x1800091e5  jz      short loc_1800091F1
0x1800091e7  mov     rcx, [rbp+hKey]; hKey
0x1800091eb  call    cs:__imp_RegCloseKey
0x1800091f1  mov     ecx, edi; dwErrCode
0x1800091f3  call    cs:__imp_SetLastError
0x1800091f9  mov     eax, [rbp+Data]
0x1800091fc  mov     rbx, [rsp+40h+arg_8]
0x180009201  mov     rdi, [rsp+40h+arg_10]
0x180009206  add     rsp, 40h
0x18000920a  pop     rbp
0x18000920b  retn
```
