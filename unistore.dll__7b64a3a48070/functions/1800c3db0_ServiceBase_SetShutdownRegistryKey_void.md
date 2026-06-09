# ServiceBase::_SetShutdownRegistryKey(void)

- ea: `0x1800c3db0`
- end: `0x1800c3e74`
- name: `?_SetShutdownRegistryKey@ServiceBase@@AEAAJXZ`
- size: `196`
- prototype: `__int64 __fastcall(ServiceBase *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18004403c`

## callees

- `0x18001a6c4`
- `0x1800c3db0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3e52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3e61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3e52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3e61`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c3e2f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c3e2f`

## pseudocode

```c
__int64 __fastcall ServiceBase::_SetShutdownRegistryKey(ServiceBase *this)
{
  const WCHAR *v2; // rdi
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  signed int v5; // ebx
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  v2 = (const WCHAR *)(*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 88LL))(this);
  if ( !v2 )
  {
    (*(void (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 64LL))(this);
    return 0;
  }
  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  Key = RegCreateKeyExW(HKEY_CURRENT_USER, v2, 0, 0, 1u, 0x20019u, 0, phkResult, 0);
  v5 = Key;
  if ( Key > 0 )
    v5 = (unsigned __int16)Key | 0x80070000;
  if ( v5 >= 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800c3db0  mov     [rsp+arg_8], rbx
0x1800c3db5  push    rdi
0x1800c3db6  sub     rsp, 50h
0x1800c3dba  mov     rax, [rcx]
0x1800c3dbd  mov     rbx, rcx
0x1800c3dc0  mov     rax, [rax+58h]
0x1800c3dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3dc9  mov     rdi, rax
0x1800c3dcc  test    rax, rax
0x1800c3dcf  jnz     short loc_1800C3DE5
0x1800c3dd1  mov     rax, [rbx]
0x1800c3dd4  mov     rcx, rbx
0x1800c3dd7  mov     rax, [rax+40h]
0x1800c3ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3de0  jmp     loc_1800C3E67
0x1800c3de5  lea     rcx, [rsp+58h+hKey]
0x1800c3dea  mov     [rsp+58h+hKey], 0
0x1800c3df3  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x1800c3df8  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800c3e01  xor     r9d, r9d; lpClass
0x1800c3e04  mov     [rsp+58h+phkResult], rax; phkResult
0x1800c3e09  xor     r8d, r8d; Reserved
0x1800c3e0c  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800c3e15  mov     rdx, rdi; lpSubKey
0x1800c3e18  mov     [rsp+58h+samDesired], 20019h; samDesired
0x1800c3e20  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800c3e27  mov     [rsp+58h+dwOptions], 1; dwOptions
0x1800c3e2f  call    cs:__imp_RegCreateKeyExW
0x1800c3e35  mov     ebx, eax
0x1800c3e37  test    eax, eax
0x1800c3e39  jle     short loc_1800C3E44
0x1800c3e3b  movzx   ebx, ax
0x1800c3e3e  or      ebx, 80070000h
0x1800c3e44  mov     rcx, [rsp+58h+hKey]; hKey
0x1800c3e49  test    ebx, ebx
0x1800c3e4b  jns     short loc_1800C3E5C
0x1800c3e4d  test    rcx, rcx
0x1800c3e50  jz      short loc_1800C3E58
0x1800c3e52  call    cs:__imp_RegCloseKey
0x1800c3e58  mov     eax, ebx
0x1800c3e5a  jmp     short loc_1800C3E69
0x1800c3e5c  test    rcx, rcx
0x1800c3e5f  jz      short loc_1800C3E67
0x1800c3e61  call    cs:__imp_RegCloseKey
0x1800c3e67  xor     eax, eax
0x1800c3e69  mov     rbx, [rsp+58h+arg_8]
0x1800c3e6e  add     rsp, 50h
0x1800c3e72  pop     rdi
0x1800c3e73  retn
```
