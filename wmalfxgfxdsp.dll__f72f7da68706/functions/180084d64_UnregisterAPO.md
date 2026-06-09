# UnregisterAPO

- ea: `0x180084d64`
- end: `0x180084e3a`
- name: `UnregisterAPO`
- size: `214`
- prototype: `HRESULT __stdcall(const IID *const clsid)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180079690`
- `0x1800796c0`
- `0x1800796f0`
- `0x180079710`

## callees

- `0x180015190`
- `0x180084d64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084db0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084db0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084e11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084e11`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180084df1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180084df1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180084dd7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180084dd7`

## pseudocode

```c
HRESULT __stdcall UnregisterAPO(const IID *const clsid)
{
  LSTATUS v2; // eax
  HRESULT v3; // ebx
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+30h] [rbp-428h] BYREF
  OLECHAR sz[512]; // [rsp+40h] [rbp-418h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"AudioEngine\\AudioProcessingObjects", 0, 0x20006u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      return (unsigned __int16)v2 | 0x80070000;
  }
  else
  {
    if ( StringFromGUID2(clsid, sz, 512) && (v4 = RegDeleteKeyExW(hKey, sz, 0, 0), (v3 = v4) != 0) )
    {
      if ( v4 > 0 )
        v3 = (unsigned __int16)v4 | 0x80070000;
    }
    else
    {
      v3 = 0;
    }
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x180084d64  mov     [rsp+arg_8], rbx
0x180084d69  push    rdi
0x180084d6a  sub     rsp, 450h
0x180084d71  mov     rax, cs:__security_cookie
0x180084d78  xor     rax, rsp
0x180084d7b  mov     [rsp+458h+var_18], rax
0x180084d83  mov     rdi, rcx
0x180084d86  mov     [rsp+458h+hKey], 0
0x180084d8f  lea     rax, [rsp+458h+hKey]
0x180084d94  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180084d9b  mov     r9d, 20006h; samDesired
0x180084da1  mov     [rsp+458h+phkResult], rax; phkResult
0x180084da6  xor     r8d, r8d; ulOptions
0x180084da9  lea     rdx, SubKey; "AudioEngine\\AudioProcessingObjects"
0x180084db0  call    cs:__imp_RegOpenKeyExW
0x180084db6  mov     ebx, eax
0x180084db8  test    eax, eax
0x180084dba  jz      short loc_180084DC9
0x180084dbc  jle     short loc_180084E17
0x180084dbe  movzx   ebx, ax
0x180084dc1  or      ebx, 80070000h
0x180084dc7  jmp     short loc_180084E17
0x180084dc9  mov     r8d, 200h; cchMax
0x180084dcf  lea     rdx, [rsp+458h+sz]; lpsz
0x180084dd4  mov     rcx, rdi; rguid
0x180084dd7  call    cs:__imp_StringFromGUID2
0x180084ddd  test    eax, eax
0x180084ddf  jz      short loc_180084E0A
0x180084de1  mov     rcx, [rsp+458h+hKey]; hKey
0x180084de6  lea     rdx, [rsp+458h+sz]; lpSubKey
0x180084deb  xor     r9d, r9d; Reserved
0x180084dee  xor     r8d, r8d; samDesired
0x180084df1  call    cs:__imp_RegDeleteKeyExW
0x180084df7  mov     ebx, eax
0x180084df9  test    eax, eax
0x180084dfb  jz      short loc_180084E0A
0x180084dfd  jle     short loc_180084E0C
0x180084dff  movzx   ebx, ax
0x180084e02  or      ebx, 80070000h
0x180084e08  jmp     short loc_180084E0C
0x180084e0a  xor     ebx, ebx
0x180084e0c  mov     rcx, [rsp+458h+hKey]; hKey
0x180084e11  call    cs:__imp_RegCloseKey
0x180084e17  mov     eax, ebx
0x180084e19  mov     rcx, [rsp+458h+var_18]
0x180084e21  xor     rcx, rsp; StackCookie
0x180084e24  call    __security_check_cookie
0x180084e29  mov     rbx, [rsp+458h+arg_8]
0x180084e31  add     rsp, 450h
0x180084e38  pop     rdi
0x180084e39  retn
```
