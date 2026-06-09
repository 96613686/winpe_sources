# SetEUDCRegEntry

- ea: `0x180022828`
- end: `0x1800229a0`
- name: `SetEUDCRegEntry`
- size: `376`
- prototype: `__int64 __fastcall(LPCSTR lpValueName, BYTE *lpData)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180022de8`

## callees

- `0x18001f470`
- `0x180022828`
- `0x18002a590`

## import_xrefs

- `KERNEL32!RegQueryValueExA` at `0x180022913`
- `KERNEL32!RegQueryValueExA` at `0x180022913`
- `KERNEL32!RegCloseKey` at `0x180022926`
- `KERNEL32!RegCloseKey` at `0x180022996`
- `KERNEL32!RegCloseKey` at `0x180022926`
- `KERNEL32!RegCloseKey` at `0x180022996`
- `KERNEL32!RegSetValueExA` at `0x180022985`
- `KERNEL32!RegSetValueExA` at `0x180022985`
- `KERNEL32!RegCreateKeyExA` at `0x1800228de`
- `KERNEL32!RegCreateKeyExA` at `0x1800228de`

## pseudocode

```c
_BOOL8 __fastcall SetEUDCRegEntry(LPCSTR lpValueName, BYTE *lpData, int a3, int a4)
{
  DWORD v8; // eax
  __int64 v9; // rax
  BOOL v10; // ebx
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type[3]; // [rsp+64h] [rbp-9Ch] BYREF
  char pszDest[256]; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[272]; // [rsp+170h] [rbp+70h] BYREF

  hKey = 0;
  dwDisposition = 0;
  Type[0] = 0;
  cbData = 0;
  if ( StringCchPrintfA(pszDest, 0x100u, "EUDC\\%lu", a3) < 0
    || RegCreateKeyExA(HKEY_CURRENT_USER, pszDest, 0, (LPSTR)&Class, 0, 0x2001Fu, 0, &hKey, &dwDisposition) )
  {
    return 0;
  }
  cbData = 260;
  if ( !RegQueryValueExA(hKey, lpValueName, 0, Type, Data, &cbData) && !a4 )
  {
    RegCloseKey(hKey);
    return 0;
  }
  if ( lpData )
  {
    v9 = -1;
    do
      ++v9;
    while ( lpData[v9] );
    v8 = v9 + 1;
  }
  else
  {
    v8 = 0;
  }
  v10 = RegSetValueExA(hKey, lpValueName, 0, 1u, lpData, v8) == 0;
  RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x180022828  mov     [rsp-8+arg_18], rbx
0x18002282d  push    rbp
0x18002282e  push    rsi
0x18002282f  push    rdi
0x180022830  lea     rbp, [rsp-190h]
0x180022838  sub     rsp, 290h
0x18002283f  mov     rax, cs:__security_cookie
0x180022846  xor     rax, rsp
0x180022849  mov     [rbp+1A0h+var_20], rax
0x180022850  mov     edi, r9d
0x180022853  mov     [rsp+2A0h+hKey], 0
0x18002285c  mov     r9d, r8d
0x18002285f  mov     [rsp+2A0h+dwDisposition], 0
0x180022867  mov     rbx, rdx
0x18002286a  mov     [rsp+2A0h+Type], 0
0x180022872  mov     rsi, rcx
0x180022875  mov     [rsp+2A0h+cbData], 0
0x18002287d  lea     r8, pszFormat; "EUDC\\%lu"
0x180022884  mov     edx, 100h; cchDest
0x180022889  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x18002288e  call    StringCchPrintfA
0x180022893  test    eax, eax
0x180022895  js      loc_18002292C
0x18002289b  lea     rax, [rsp+2A0h+dwDisposition]
0x1800228a0  xor     r8d, r8d; Reserved
0x1800228a3  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x1800228a8  lea     r9, Class; lpClass
0x1800228af  lea     rax, [rsp+2A0h+hKey]
0x1800228b4  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800228bb  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800228c0  lea     rdx, [rsp+2A0h+pszDest]; lpSubKey
0x1800228c5  mov     [rsp+2A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800228ce  mov     [rsp+2A0h+samDesired], 2001Fh; samDesired
0x1800228d6  mov     [rsp+2A0h+dwOptions], 0; dwOptions
0x1800228de  call    cs:__imp_RegCreateKeyExA
0x1800228e4  test    eax, eax
0x1800228e6  jnz     short loc_18002292C
0x1800228e8  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800228ed  lea     rax, [rsp+2A0h+cbData]
0x1800228f2  mov     qword ptr [rsp+2A0h+samDesired], rax; lpcbData
0x1800228f7  lea     r9, [rsp+2A0h+Type]; lpType
0x1800228fc  lea     rax, [rbp+1A0h+Data]
0x180022900  mov     [rsp+2A0h+cbData], 104h
0x180022908  xor     r8d, r8d; lpReserved
0x18002290b  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x180022910  mov     rdx, rsi; lpValueName
0x180022913  call    cs:__imp_RegQueryValueExA
0x180022919  test    eax, eax
0x18002291b  jnz     short loc_180022950
0x18002291d  test    edi, edi
0x18002291f  jnz     short loc_180022950
0x180022921  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180022926  call    cs:__imp_RegCloseKey
0x18002292c  xor     eax, eax
0x18002292e  mov     rcx, [rbp+1A0h+var_20]
0x180022935  xor     rcx, rsp; StackCookie
0x180022938  call    __security_check_cookie
0x18002293d  mov     rbx, [rsp+2A0h+arg_18]
0x180022945  add     rsp, 290h
0x18002294c  pop     rdi
0x18002294d  pop     rsi
0x18002294e  pop     rbp
0x18002294f  retn
0x180022950  test    rbx, rbx
0x180022953  jnz     short loc_180022959
0x180022955  xor     eax, eax
0x180022957  jmp     short loc_180022969
0x180022959  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002295d  inc     rax
0x180022960  cmp     byte ptr [rbx+rax], 0
0x180022964  jnz     short loc_18002295D
0x180022966  inc     rax
0x180022969  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18002296e  xor     r8d, r8d; Reserved
0x180022971  mov     [rsp+2A0h+samDesired], eax; cbData
0x180022975  mov     rdx, rsi; lpValueName
0x180022978  mov     qword ptr [rsp+2A0h+dwOptions], rbx; lpData
0x18002297d  mov     ebx, 1
0x180022982  mov     r9d, ebx; dwType
0x180022985  call    cs:__imp_RegSetValueExA
0x18002298b  test    eax, eax
0x18002298d  jz      short loc_180022991
0x18002298f  xor     ebx, ebx
0x180022991  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180022996  call    cs:__imp_RegCloseKey
0x18002299c  mov     eax, ebx
0x18002299e  jmp     short loc_18002292E
```
