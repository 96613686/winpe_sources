# ServiceBase::_CheckServiceShutdownAlready(void)

- ea: `0x18005fcb4`
- end: `0x18005fd75`
- name: `?_CheckServiceShutdownAlready@ServiceBase@@AEAAJXZ`
- size: `193`
- prototype: `__int64 __fastcall(ServiceBase *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18005f9f8`

## callees

- `0x18005fcb4`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005fd00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005fd00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005fd27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005fd53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005fd62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005fd27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005fd53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005fd62`

## pseudocode

```c
__int64 __fastcall ServiceBase::_CheckServiceShutdownAlready(ServiceBase *this)
{
  const WCHAR *v1; // rax
  LSTATUS v2; // eax
  signed int v3; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = (HKEY)this;
  v1 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *))(qword_18010C3C0 + 88))(&qword_18010C3C0);
  if ( !v1 )
  {
    (*(void (__fastcall **)(__int64 *))(qword_18010C3C0 + 64))(&qword_18010C3C0);
    return 0;
  }
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_CURRENT_USER, v1, 0, 0x20019u, &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 == -2147024894 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  if ( v3 >= 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 2147943515LL;
  }
  else
  {
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v3;
  }
}

```

## disassembly

```asm
0x18005fcb4  mov     [rsp+hKey], rcx
0x18005fcb9  push    rbx
0x18005fcba  sub     rsp, 30h
0x18005fcbe  mov     rax, cs:qword_18010C3C0
0x18005fcc5  lea     rcx, qword_18010C3C0
0x18005fccc  mov     rax, [rax+58h]
0x18005fcd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fcd5  test    rax, rax
0x18005fcd8  jz      short loc_18005FD35
0x18005fcda  lea     rcx, [rsp+38h+hKey]
0x18005fcdf  mov     [rsp+38h+hKey], 0
0x18005fce8  mov     [rsp+38h+phkResult], rcx; phkResult
0x18005fced  mov     r9d, 20019h; samDesired
0x18005fcf3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18005fcfa  xor     r8d, r8d; ulOptions
0x18005fcfd  mov     rdx, rax; lpSubKey
0x18005fd00  call    cs:__imp_RegOpenKeyExW
0x18005fd06  mov     ebx, eax
0x18005fd08  test    eax, eax
0x18005fd0a  jle     short loc_18005FD15
0x18005fd0c  movzx   ebx, ax
0x18005fd0f  or      ebx, 80070000h
0x18005fd15  mov     rcx, [rsp+38h+hKey]; hKey
0x18005fd1a  cmp     ebx, 80070002h
0x18005fd20  jnz     short loc_18005FD6F
0x18005fd22  test    rcx, rcx
0x18005fd25  jz      short loc_18005FD2D
0x18005fd27  call    cs:__imp_RegCloseKey
0x18005fd2d  xor     eax, eax
0x18005fd2f  add     rsp, 30h
0x18005fd33  pop     rbx
0x18005fd34  retn
0x18005fd35  mov     rax, cs:qword_18010C3C0
0x18005fd3c  lea     rcx, qword_18010C3C0
0x18005fd43  mov     rax, [rax+40h]
0x18005fd47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd4c  jmp     short loc_18005FD2D
0x18005fd4e  test    rcx, rcx
0x18005fd51  jz      short loc_18005FD59
0x18005fd53  call    cs:__imp_RegCloseKey
0x18005fd59  mov     eax, ebx
0x18005fd5b  jmp     short loc_18005FD2F
0x18005fd5d  test    rcx, rcx
0x18005fd60  jz      short loc_18005FD68
0x18005fd62  call    cs:__imp_RegCloseKey
0x18005fd68  mov     eax, 8007045Bh
0x18005fd6d  jmp     short loc_18005FD2F
0x18005fd6f  test    ebx, ebx
0x18005fd71  jns     short loc_18005FD5D
0x18005fd73  jmp     short loc_18005FD4E
```
