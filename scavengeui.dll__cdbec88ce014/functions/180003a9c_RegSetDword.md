# RegSetDword

- ea: `0x180003a9c`
- end: `0x180003b7f`
- name: `RegSetDword`
- size: `227`
- prototype: `_BOOL8 __fastcall(HKEY, const WCHAR *, const WCHAR *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002360`

## callees

- `0x180003a9c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180003b58`
- `KERNEL32!SetLastError` at `0x180003b6c`
- `KERNEL32!SetLastError` at `0x180003b58`
- `KERNEL32!SetLastError` at `0x180003b6c`
- `ADVAPI32!RegCloseKey` at `0x180003b2b`
- `ADVAPI32!RegCloseKey` at `0x180003b2b`
- `ADVAPI32!RegCreateKeyExW` at `0x180003af1`
- `ADVAPI32!RegCreateKeyExW` at `0x180003af1`
- `ADVAPI32!RegSetValueExW` at `0x180003b1e`
- `ADVAPI32!RegSetValueExW` at `0x180003b4e`
- `ADVAPI32!RegSetValueExW` at `0x180003b1e`
- `ADVAPI32!RegSetValueExW` at `0x180003b4e`

## pseudocode

```c
_BOOL8 __fastcall RegSetDword(HKEY a1, const WCHAR *a2, const WCHAR *a3, int a4)
{
  LSTATUS v5; // ebx
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF
  DWORD v8; // [rsp+70h] [rbp+8h] BYREF
  int Data; // [rsp+88h] [rbp+20h] BYREF

  Data = a4;
  if ( a1 )
  {
    if ( a2 )
    {
      hKey = 0;
      v8 = 0;
      v5 = RegCreateKeyExW(a1, a2, 0, (LPWSTR)&Class, 0, 0x20006u, 0, &hKey, &v8);
      if ( !v5 )
      {
        v5 = RegSetValueExW(hKey, a3, 0, 4u, (const BYTE *)&Data, 4u);
        RegCloseKey(hKey);
      }
    }
    else
    {
      v5 = RegSetValueExW(a1, a3, 0, 4u, (const BYTE *)&Data, 4u);
    }
    SetLastError(v5);
    return v5 == 0;
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
0x180003a9c  mov     r11, rsp
0x180003a9f  mov     [r11+10h], rbx
0x180003aa3  mov     [r11+20h], r9d
0x180003aa7  push    rdi
0x180003aa8  sub     rsp, 60h
0x180003aac  mov     rdi, r8
0x180003aaf  test    rcx, rcx
0x180003ab2  jz      loc_180003B67
0x180003ab8  xor     r8d, r8d; Reserved
0x180003abb  test    rdx, rdx
0x180003abe  jz      short loc_180003B33
0x180003ac0  lea     rax, [r11+8]
0x180003ac4  mov     [r11-18h], r8
0x180003ac8  mov     [r11-28h], rax
0x180003acc  lea     r9, Class; lpClass
0x180003ad3  lea     rax, [r11-18h]
0x180003ad7  mov     [rsp+68h+arg_0], r8d
0x180003adc  mov     [r11-30h], rax
0x180003ae0  mov     [r11-38h], r8
0x180003ae4  mov     [rsp+68h+samDesired], 20006h; samDesired
0x180003aec  mov     [rsp+68h+dwOptions], r8d; dwOptions
0x180003af1  call    cs:__imp_RegCreateKeyExW
0x180003af7  mov     ebx, eax
0x180003af9  test    eax, eax
0x180003afb  jnz     short loc_180003B56
0x180003afd  mov     rcx, [rsp+68h+hKey]; hKey
0x180003b02  lea     r9d, [rax+4]; dwType
0x180003b06  lea     rax, [rsp+68h+Data]
0x180003b0e  mov     [rsp+68h+samDesired], r9d; cbData
0x180003b13  xor     r8d, r8d; Reserved
0x180003b16  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180003b1b  mov     rdx, rdi; lpValueName
0x180003b1e  call    cs:__imp_RegSetValueExW
0x180003b24  mov     rcx, [rsp+68h+hKey]; hKey
0x180003b29  mov     ebx, eax
0x180003b2b  call    cs:__imp_RegCloseKey
0x180003b31  jmp     short loc_180003B56
0x180003b33  mov     r9d, 4; dwType
0x180003b39  lea     rax, [rsp+68h+Data]
0x180003b41  mov     [rsp+68h+samDesired], r9d; cbData
0x180003b46  mov     rdx, rdi; lpValueName
0x180003b49  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180003b4e  call    cs:__imp_RegSetValueExW
0x180003b54  mov     ebx, eax
0x180003b56  mov     ecx, ebx; dwErrCode
0x180003b58  call    cs:__imp_SetLastError
0x180003b5e  xor     eax, eax
0x180003b60  test    ebx, ebx
0x180003b62  setz    al
0x180003b65  jmp     short loc_180003B74
0x180003b67  mov     ecx, 57h ; 'W'; dwErrCode
0x180003b6c  call    cs:__imp_SetLastError
0x180003b72  xor     eax, eax
0x180003b74  mov     rbx, [rsp+68h+arg_8]
0x180003b79  add     rsp, 60h
0x180003b7d  pop     rdi
0x180003b7e  retn
```
