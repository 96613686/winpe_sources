# DestroyOldRegValues(void)

- ea: `0x180049b50`
- end: `0x180049bed`
- name: `?DestroyOldRegValues@@YAJXZ`
- size: `157`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18004a5e4`

## callees

- `0x180049b50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049b95`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049b95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049bc5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049bc5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180049baf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180049baf`

## pseudocode

```c
__int64 DestroyOldRegValues(void)
{
  __int64 i; // rbx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  for ( i = 0; i != 8; ++i )
  {
    hKey = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, off_18006E390[2 * i], 0, 2u, &hKey) >= 0 )
      RegDeleteValueW(hKey, off_18006E390[2 * i + 1]);
    if ( hKey )
      RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x180049b50  mov     [rsp+arg_8], rbx
0x180049b55  mov     [rsp+arg_10], rsi
0x180049b5a  push    rdi
0x180049b5b  sub     rsp, 30h
0x180049b5f  xor     ebx, ebx
0x180049b61  lea     rsi, off_18006E390; "System\\CurrentControlSet\\Services\\W3"...
0x180049b68  lea     rax, [rsp+38h+hKey]
0x180049b6d  mov     [rsp+38h+hKey], 0
0x180049b76  mov     rdi, rbx
0x180049b79  mov     [rsp+38h+phkResult], rax; phkResult
0x180049b7e  add     rdi, rdi
0x180049b81  mov     r9d, 2; samDesired
0x180049b87  xor     r8d, r8d; ulOptions
0x180049b8a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180049b91  mov     rdx, [rsi+rdi*8]; lpSubKey
0x180049b95  call    cs:__imp_RegOpenKeyExW
0x180049b9c  nop     dword ptr [rax+rax+00h]
0x180049ba1  test    eax, eax
0x180049ba3  js      short loc_180049BBB
0x180049ba5  mov     rdx, [rsi+rdi*8+8]; lpValueName
0x180049baa  mov     rcx, [rsp+38h+hKey]; hKey
0x180049baf  call    cs:__imp_RegDeleteValueW
0x180049bb6  nop     dword ptr [rax+rax+00h]
0x180049bbb  mov     rcx, [rsp+38h+hKey]; hKey
0x180049bc0  test    rcx, rcx
0x180049bc3  jz      short loc_180049BD1
0x180049bc5  call    cs:__imp_RegCloseKey
0x180049bcc  nop     dword ptr [rax+rax+00h]
0x180049bd1  inc     rbx
0x180049bd4  cmp     rbx, 8
0x180049bd8  jnz     short loc_180049B68
0x180049bda  mov     rbx, [rsp+38h+arg_8]
0x180049bdf  xor     eax, eax
0x180049be1  mov     rsi, [rsp+38h+arg_10]
0x180049be6  add     rsp, 30h
0x180049bea  pop     rdi
0x180049beb  retn
```
