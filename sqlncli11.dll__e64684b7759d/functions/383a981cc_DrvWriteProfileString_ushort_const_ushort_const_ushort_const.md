# DrvWriteProfileString(ushort const *,ushort const *,ushort const *)

- ea: `0x383a981cc`
- end: `0x383a982dc`
- name: `?DrvWriteProfileString@@YAHPEBG00@Z`
- size: `272`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, BYTE *lpData, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x38395d490`

## callees

- `0x383a981cc`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x383a98219`
- `ADVAPI32!RegOpenKeyExW` at `0x383a98219`
- `ADVAPI32!RegSetValueExW` at `0x383a982b2`
- `ADVAPI32!RegSetValueExW` at `0x383a982b2`
- `ADVAPI32!RegDeleteValueW` at `0x383a9827c`
- `ADVAPI32!RegDeleteValueW` at `0x383a9827c`
- `ADVAPI32!RegCreateKeyExW` at `0x383a98261`
- `ADVAPI32!RegCreateKeyExW` at `0x383a98261`
- `ADVAPI32!RegDeleteKeyW` at `0x383a981f6`
- `ADVAPI32!RegDeleteKeyW` at `0x383a981f6`
- `ADVAPI32!RegCloseKey` at `0x383a982bf`
- `ADVAPI32!RegCloseKey` at `0x383a982bf`

## pseudocode

```c
__int64 __fastcall DrvWriteProfileString(LPCWSTR lpValueName, BYTE *lpData, const unsigned __int16 *a3)
{
  unsigned int v3; // ebx
  LSTATUS v7; // eax
  __int64 v8; // rax
  LSTATUS v9; // edi
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  v3 = 0;
  if ( !lpValueName )
  {
    RegDeleteKeyW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MSSQLServer\\Client\\ConnectTo");
    return 1;
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MSSQLServer\\Client\\ConnectTo", 0, 0x2001Fu, &hKey) )
    goto LABEL_8;
  if ( !lpData )
    return 1;
  if ( RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\MSSQLServer\\Client\\ConnectTo",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &hKey,
         &dwDisposition) )
  {
    return 0;
  }
LABEL_8:
  if ( lpData )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&lpData[2 * v8] );
    v7 = RegSetValueExW(hKey, lpValueName, 0, 1u, lpData, 2 * v8 + 2);
  }
  else
  {
    v7 = RegDeleteValueW(hKey, lpValueName);
  }
  v9 = v7;
  RegCloseKey(hKey);
  LOBYTE(v3) = v9 == 0;
  return v3;
}

```

## disassembly

```asm
0x383a981cc  mov     [rsp+arg_8], rbx
0x383a981d1  mov     [rsp+arg_18], rbp
0x383a981d6  push    rdi
0x383a981d7  sub     rsp, 50h
0x383a981db  xor     ebx, ebx
0x383a981dd  mov     rdi, rdx
0x383a981e0  mov     rbp, rcx
0x383a981e3  test    rcx, rcx
0x383a981e6  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\MSSQLServer\\Clien"...
0x383a981ed  mov     rcx, 0FFFFFFFF80000002h; hKey
0x383a981f4  jnz     short loc_383A98206
0x383a981f6  call    cs:__imp_RegDeleteKeyW
0x383a981fc  mov     eax, 1
0x383a98201  jmp     loc_383A982CC
0x383a98206  lea     rax, [rsp+58h+hKey]
0x383a9820b  mov     r9d, 2001Fh; samDesired
0x383a98211  xor     r8d, r8d; ulOptions
0x383a98214  mov     [rsp+58h+phkResult], rax; phkResult
0x383a98219  call    cs:__imp_RegOpenKeyExW
0x383a9821f  test    eax, eax
0x383a98221  jz      short loc_383A9826F
0x383a98223  test    rdi, rdi
0x383a98226  jz      short loc_383A981FC
0x383a98228  lea     rax, [rsp+58h+dwDisposition]
0x383a9822d  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\MSSQLServer\\Clien"...
0x383a98234  xor     r9d, r9d; lpClass
0x383a98237  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x383a9823c  lea     rax, [rsp+58h+hKey]
0x383a98241  xor     r8d, r8d; Reserved
0x383a98244  mov     [rsp+58h+var_20], rax; phkResult
0x383a98249  mov     [rsp+58h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x383a9824e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x383a98255  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x383a9825d  mov     dword ptr [rsp+58h+phkResult], ebx; dwOptions
0x383a98261  call    cs:__imp_RegCreateKeyExW
0x383a98267  test    eax, eax
0x383a98269  jz      short loc_383A9826F
0x383a9826b  xor     eax, eax
0x383a9826d  jmp     short loc_383A982CC
0x383a9826f  test    rdi, rdi
0x383a98272  jnz     short loc_383A98284
0x383a98274  mov     rcx, [rsp+58h+hKey]; hKey
0x383a98279  mov     rdx, rbp; lpValueName
0x383a9827c  call    cs:__imp_RegDeleteValueW
0x383a98282  jmp     short loc_383A982B8
0x383a98284  or      rax, 0FFFFFFFFFFFFFFFFh
0x383a98288  inc     rax
0x383a9828b  cmp     [rdi+rax*2], bx
0x383a9828f  jnz     short loc_383A98288
0x383a98291  mov     rcx, [rsp+58h+hKey]; hKey
0x383a98296  lea     eax, ds:2[rax*2]
0x383a9829d  mov     r9d, 1; dwType
0x383a982a3  mov     [rsp+58h+samDesired], eax; cbData
0x383a982a7  xor     r8d, r8d; Reserved
0x383a982aa  mov     rdx, rbp; lpValueName
0x383a982ad  mov     [rsp+58h+phkResult], rdi; lpData
0x383a982b2  call    cs:__imp_RegSetValueExW
0x383a982b8  mov     rcx, [rsp+58h+hKey]; hKey
0x383a982bd  mov     edi, eax
0x383a982bf  call    cs:__imp_RegCloseKey
0x383a982c5  test    edi, edi
0x383a982c7  setz    bl
0x383a982ca  mov     eax, ebx
0x383a982cc  mov     rbx, [rsp+58h+arg_8]
0x383a982d1  mov     rbp, [rsp+58h+arg_18]
0x383a982d6  add     rsp, 50h
0x383a982da  pop     rdi
0x383a982db  retn
```
