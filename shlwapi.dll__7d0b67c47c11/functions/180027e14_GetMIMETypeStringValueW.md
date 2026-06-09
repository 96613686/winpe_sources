# GetMIMETypeStringValueW

- ea: `0x180027e14`
- end: `0x180027edb`
- name: `GetMIMETypeStringValueW`
- size: `199`
- prototype: `__int64 __fastcall(LPCWSTR pszSubKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180027ef0`

## callees

- `0x180012550`
- `0x180027e14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027eb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027eb0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027e62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027e62`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x180027ea3`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x180027ea3`

## string_xrefs

- `0x180027e7b`: `Extension`

## pseudocode

```c
_BOOL8 __fastcall GetMIMETypeStringValueW(LPCWSTR pszSubKey, __int64 a2, void *a3, int a4)
{
  LSTATUS ValueW; // ebx
  HKEY hkey; // [rsp+40h] [rbp-38h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-30h] BYREF

  hkey = 0;
  ValueW = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"MIME\\Database\\Content Type", 0, 1u, &hkey);
  if ( !ValueW )
  {
    pcbData = 2 * a4;
    ValueW = SHRegGetValueW(hkey, pszSubKey, L"Extension", 268435458, 0, a3, &pcbData);
    RegCloseKey(hkey);
  }
  return ValueW == 0;
}

```

## disassembly

```asm
0x180027e14  mov     r11, rsp
0x180027e17  mov     [r11+10h], rbx
0x180027e1b  push    rsi
0x180027e1c  push    rdi
0x180027e1d  push    r14
0x180027e1f  sub     rsp, 60h
0x180027e23  mov     rax, cs:__security_cookie
0x180027e2a  xor     rax, rsp
0x180027e2d  mov     [rsp+78h+var_28], rax
0x180027e32  mov     r14d, r9d
0x180027e35  mov     qword ptr [r11-38h], 0
0x180027e3d  mov     rsi, r8
0x180027e40  lea     rax, [r11-38h]
0x180027e44  mov     rdi, rcx
0x180027e47  mov     [r11-58h], rax
0x180027e4b  mov     r9d, 1; samDesired
0x180027e51  lea     rdx, aMimeDatabaseCo; "MIME\\Database\\Content Type"
0x180027e58  xor     r8d, r8d; ulOptions
0x180027e5b  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180027e62  call    cs:__imp_RegOpenKeyExW
0x180027e68  mov     ebx, eax
0x180027e6a  test    eax, eax
0x180027e6c  jnz     short loc_180027EB6
0x180027e6e  mov     rcx, [rsp+78h+hkey]; hkey
0x180027e73  lea     eax, [r14+r14]
0x180027e77  mov     [rsp+78h+var_30], eax
0x180027e7b  lea     r8, aExtension; "Extension"
0x180027e82  lea     rax, [rsp+78h+var_30]
0x180027e87  mov     r9d, 10000002h; srrfFlags
0x180027e8d  mov     [rsp+78h+pcbData], rax; pcbData
0x180027e92  mov     rdx, rdi; pszSubKey
0x180027e95  mov     [rsp+78h+pvData], rsi; pvData
0x180027e9a  mov     [rsp+78h+pdwType], 0; pdwType
0x180027ea3  call    cs:__imp_SHRegGetValueW
0x180027ea9  mov     rcx, [rsp+78h+hkey]; hKey
0x180027eae  mov     ebx, eax
0x180027eb0  call    cs:__imp_RegCloseKey
0x180027eb6  xor     eax, eax
0x180027eb8  test    ebx, ebx
0x180027eba  setz    al
0x180027ebd  mov     rcx, [rsp+78h+var_28]
0x180027ec2  xor     rcx, rsp; StackCookie
0x180027ec5  call    __security_check_cookie
0x180027eca  mov     rbx, [rsp+78h+arg_8]
0x180027ed2  add     rsp, 60h
0x180027ed6  pop     r14
0x180027ed8  pop     rdi
0x180027ed9  pop     rsi
0x180027eda  retn
```
