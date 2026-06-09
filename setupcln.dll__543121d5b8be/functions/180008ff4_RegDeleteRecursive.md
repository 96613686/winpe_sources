# RegDeleteRecursive

- ea: `0x180008ff4`
- end: `0x1800090ac`
- name: `RegDeleteRecursive`
- size: `184`
- prototype: `_BOOL8 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800035b0`

## callees

- `0x180008ff4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009080`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009094`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009080`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009094`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000904c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000904c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009039`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009039`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180009076`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180009076`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009059`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009059`

## pseudocode

```c
_BOOL8 __fastcall RegDeleteRecursive(HKEY hKey, LPCWSTR lpSubKey)
{
  LSTATUS v4; // ebx
  LSTATUS v5; // eax
  HKEY hKeya; // [rsp+40h] [rbp+8h] BYREF

  hKeya = 0;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL && lpSubKey && *lpSubKey )
  {
    v4 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20F003Fu, &hKeya);
    if ( !v4 )
    {
      v4 = RegDeleteTreeW(hKeya, 0);
      v5 = RegCloseKey(hKeya);
      if ( !v4 )
      {
        if ( !v5 )
          v5 = RegDeleteKeyExW(hKey, lpSubKey, 0xF003Fu, 0);
        v4 = v5;
      }
    }
    SetLastError(v4);
    return v4 == 0;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x180008ff4  mov     r11, rsp
0x180008ff7  mov     [r11+10h], rbx
0x180008ffb  mov     [r11+18h], rsi
0x180008fff  push    rdi
0x180009000  sub     rsp, 30h
0x180009004  lea     rax, [rcx-1]
0x180009008  mov     qword ptr [r11+8], 0
0x180009010  mov     rdi, rdx
0x180009013  mov     rsi, rcx
0x180009016  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000901a  ja      short loc_18000908F
0x18000901c  test    rdx, rdx
0x18000901f  jz      short loc_18000908F
0x180009021  xor     eax, eax
0x180009023  cmp     ax, [rdx]
0x180009026  jz      short loc_18000908F
0x180009028  lea     rax, [r11+8]
0x18000902c  mov     r9d, 20F003Fh; samDesired
0x180009032  xor     r8d, r8d; ulOptions
0x180009035  mov     [r11-18h], rax
0x180009039  call    cs:__imp_RegOpenKeyExW
0x18000903f  mov     ebx, eax
0x180009041  test    eax, eax
0x180009043  jnz     short loc_18000907E
0x180009045  mov     rcx, [rsp+38h+hKey]; hKey
0x18000904a  xor     edx, edx; lpSubKey
0x18000904c  call    cs:__imp_RegDeleteTreeW
0x180009052  mov     rcx, [rsp+38h+hKey]; hKey
0x180009057  mov     ebx, eax
0x180009059  call    cs:__imp_RegCloseKey
0x18000905f  test    ebx, ebx
0x180009061  jnz     short loc_18000907E
0x180009063  test    eax, eax
0x180009065  jnz     short loc_18000907C
0x180009067  xor     r9d, r9d; Reserved
0x18000906a  mov     r8d, 0F003Fh; samDesired
0x180009070  mov     rdx, rdi; lpSubKey
0x180009073  mov     rcx, rsi; hKey
0x180009076  call    cs:__imp_RegDeleteKeyExW
0x18000907c  mov     ebx, eax
0x18000907e  mov     ecx, ebx; dwErrCode
0x180009080  call    cs:__imp_SetLastError
0x180009086  xor     eax, eax
0x180009088  test    ebx, ebx
0x18000908a  setz    al
0x18000908d  jmp     short loc_18000909C
0x18000908f  mov     ecx, 57h ; 'W'; dwErrCode
0x180009094  call    cs:__imp_SetLastError
0x18000909a  xor     eax, eax
0x18000909c  mov     rbx, [rsp+38h+arg_8]
0x1800090a1  mov     rsi, [rsp+38h+arg_10]
0x1800090a6  add     rsp, 30h
0x1800090aa  pop     rdi
0x1800090ab  retn
```
