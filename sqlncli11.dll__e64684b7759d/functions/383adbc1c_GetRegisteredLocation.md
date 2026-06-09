# GetRegisteredLocation

- ea: `0x383adbc1c`
- end: `0x383adbd4f`
- name: `GetRegisteredLocation`
- size: `307`
- prototype: `__int64 __fastcall(LPSTR lpDst)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x383adbd94`
- `0x383adbe80`

## callees

- `0x3838434c0`
- `0x383adbc1c`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsA` at `0x383adbccb`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x383adbccb`
- `ADVAPI32!RegOpenKeyExA` at `0x383adbc66`
- `ADVAPI32!RegOpenKeyExA` at `0x383adbc66`
- `ADVAPI32!RegQueryValueExA` at `0x383adbca8`
- `ADVAPI32!RegQueryValueExA` at `0x383adbca8`
- `ADVAPI32!RegCloseKey` at `0x383adbd1e`
- `ADVAPI32!RegCloseKey` at `0x383adbd1e`

## string_xrefs

- `0x383adbc48`: `CLSID\{ADB880A6-D8FF-11CF-9377-00AA003B7A11}\InprocServer32`

## pseudocode

```c
__int64 __fastcall GetRegisteredLocation(LPSTR lpDst)
{
  unsigned int v2; // ebx
  __int64 v3; // rsi
  int v4; // ecx
  signed __int64 v5; // rdx
  CHAR v6; // al
  DWORD Type; // [rsp+30h] [rbp-138h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-134h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-130h] BYREF
  BYTE Data[272]; // [rsp+40h] [rbp-128h] BYREF

  v2 = 0;
  if ( RegOpenKeyExA(
         HKEY_CLASSES_ROOT,
         "CLSID\\{ADB880A6-D8FF-11CF-9377-00AA003B7A11}\\InprocServer32",
         0,
         0x20019u,
         &hKey) )
  {
    return 0;
  }
  v3 = 260;
  Type = 1;
  cbData = 260;
  if ( !RegQueryValueExA(hKey, 0, 0, &Type, Data, &cbData) )
  {
    Data[259] = 0;
    if ( Type == 2 )
    {
      LOBYTE(v2) = ExpandEnvironmentStringsA((LPCSTR)Data, lpDst, 0x104u) - 1 <= 0x103;
    }
    else
    {
      v4 = 0;
      v5 = Data - (BYTE *)lpDst;
      do
      {
        if ( v3 == -2147483386 )
          break;
        v6 = lpDst[v5];
        if ( !v6 )
          break;
        *lpDst++ = v6;
        --v3;
      }
      while ( v3 );
      if ( !v3 )
      {
        --lpDst;
        v4 = -2147024774;
      }
      *lpDst = 0;
      LOBYTE(v2) = v4 >= 0;
    }
  }
  RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x383adbc1c  mov     [rsp+arg_8], rbx
0x383adbc21  mov     [rsp+arg_10], rsi
0x383adbc26  push    rdi
0x383adbc27  sub     rsp, 160h
0x383adbc2e  mov     rax, cs:__security_cookie
0x383adbc35  xor     rax, rsp
0x383adbc38  mov     [rsp+168h+var_18], rax
0x383adbc40  lea     rax, [rsp+168h+hKey]
0x383adbc45  mov     rdi, rcx
0x383adbc48  lea     rdx, aClsidAdb880a6D; "CLSID\\{ADB880A6-D8FF-11CF-9377-00AA003"...
0x383adbc4f  mov     r9d, 20019h; samDesired
0x383adbc55  xor     r8d, r8d; ulOptions
0x383adbc58  mov     rcx, 0FFFFFFFF80000000h; hKey
0x383adbc5f  mov     [rsp+168h+phkResult], rax; phkResult
0x383adbc64  xor     ebx, ebx
0x383adbc66  call    cs:__imp_RegOpenKeyExA
0x383adbc6c  cmp     eax, ebx
0x383adbc6e  jnz     loc_383ADBD28
0x383adbc74  mov     rcx, [rsp+168h+hKey]; hKey
0x383adbc79  lea     rax, [rsp+168h+cbData]
0x383adbc7e  lea     r9, [rsp+168h+Type]; lpType
0x383adbc83  mov     [rsp+168h+lpcbData], rax; lpcbData
0x383adbc88  lea     rax, [rsp+168h+Data]
0x383adbc8d  mov     esi, 104h
0x383adbc92  xor     r8d, r8d; lpReserved
0x383adbc95  xor     edx, edx; lpValueName
0x383adbc97  mov     [rsp+168h+Type], 1
0x383adbc9f  mov     [rsp+168h+phkResult], rax; lpData
0x383adbca4  mov     [rsp+168h+cbData], esi
0x383adbca8  call    cs:__imp_RegQueryValueExA
0x383adbcae  cmp     eax, ebx
0x383adbcb0  jnz     short loc_383ADBD19
0x383adbcb2  cmp     [rsp+168h+Type], 2
0x383adbcb7  mov     [rsp+168h+var_25], bl
0x383adbcbe  jnz     short loc_383ADBCDD
0x383adbcc0  lea     rcx, [rsp+168h+Data]; lpSrc
0x383adbcc5  mov     r8d, esi; nSize
0x383adbcc8  mov     rdx, rdi; lpDst
0x383adbccb  call    cs:__imp_ExpandEnvironmentStringsA
0x383adbcd1  dec     eax
0x383adbcd3  cmp     eax, 103h
0x383adbcd8  setbe   bl
0x383adbcdb  jmp     short loc_383ADBD19
0x383adbcdd  lea     rdx, [rsp+168h+Data]
0x383adbce2  mov     ecx, ebx
0x383adbce4  sub     rdx, rdi
0x383adbce7  lea     rax, [rsi+7FFFFEFAh]
0x383adbcee  cmp     rax, rbx
0x383adbcf1  jz      short loc_383ADBD05
0x383adbcf3  mov     al, [rdx+rdi]
0x383adbcf6  cmp     al, bl
0x383adbcf8  jz      short loc_383ADBD05
0x383adbcfa  mov     [rdi], al
0x383adbcfc  inc     rdi
0x383adbcff  sub     rsi, 1
0x383adbd03  jnz     short loc_383ADBCE7
0x383adbd05  cmp     rsi, rbx
0x383adbd08  jnz     short loc_383ADBD12
0x383adbd0a  dec     rdi
0x383adbd0d  mov     ecx, 8007007Ah
0x383adbd12  cmp     ecx, ebx
0x383adbd14  mov     [rdi], bl
0x383adbd16  setnl   bl
0x383adbd19  mov     rcx, [rsp+168h+hKey]; hKey
0x383adbd1e  call    cs:__imp_RegCloseKey
0x383adbd24  mov     eax, ebx
0x383adbd26  jmp     short loc_383ADBD2A
0x383adbd28  xor     eax, eax
0x383adbd2a  mov     rcx, [rsp+168h+var_18]
0x383adbd32  xor     rcx, rsp; StackCookie
0x383adbd35  call    __security_check_cookie
0x383adbd3a  lea     r11, [rsp+168h+var_8]
0x383adbd42  mov     rbx, [r11+18h]
0x383adbd46  mov     rsi, [r11+20h]
0x383adbd4a  mov     rsp, r11
0x383adbd4d  pop     rdi
0x383adbd4e  retn
```
