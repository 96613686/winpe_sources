# ScReadServiceAliasFromRegistry(HKEY__ *,ushort *,ushort * *)

- ea: `0x18000c870`
- end: `0x18000c9f0`
- name: `?ScReadServiceAliasFromRegistry@@YAKPEAUHKEY__@@PEAGPEAPEAG@Z`
- size: `384`
- prototype: `unsigned int __fastcall(HKEY, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000a87c`
- `0x18003a5a8`

## callees

- `0x18000c870`
- `0x18004f902`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c8cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c8cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c904`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c954`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c904`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c954`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c9ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c9ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c91c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c978`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c91c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c978`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c9c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c9c6`

## pseudocode

```c
__int64 __fastcall ScReadServiceAliasFromRegistry(HKEY a1, unsigned __int16 *a2, BYTE **a3)
{
  BYTE *v4; // rbx
  unsigned int v5; // edi
  BYTE *v6; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[528]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  cbData = 520;
  Type = 0;
  v4 = Data;
  v5 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  if ( !v5 )
  {
    v5 = RegQueryValueExW(hKey, L"Alias", 0, &Type, Data, &cbData);
    if ( v5 == 234 )
    {
      v4 = (BYTE *)LocalAlloc(0x40u, cbData);
      if ( !v4 )
      {
LABEL_4:
        v5 = 8;
        goto LABEL_13;
      }
      v5 = RegQueryValueExW(hKey, L"Alias", 0, &Type, v4, &cbData);
    }
    if ( v5 || Type != 1 )
    {
      v5 = 13;
    }
    else
    {
      if ( v4 == Data )
      {
        v6 = (BYTE *)LocalAlloc(0x40u, cbData);
        v4 = v6;
        if ( !v6 )
          goto LABEL_4;
        memcpy_0(v6, Data, cbData);
      }
      *a3 = v4;
      v4 = 0;
    }
  }
LABEL_13:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 && v4 != Data )
    LocalFree(v4);
  return v5;
}

```

## disassembly

```asm
0x18000c870  mov     [rsp-8+arg_18], rbx
0x18000c875  push    rbp
0x18000c876  push    rsi
0x18000c877  push    rdi
0x18000c878  lea     rbp, [rsp-160h]
0x18000c880  sub     rsp, 260h
0x18000c887  mov     rax, cs:__security_cookie
0x18000c88e  xor     rax, rsp
0x18000c891  mov     [rbp+170h+var_20], rax
0x18000c898  mov     rsi, r8
0x18000c89b  mov     [rsp+270h+hKey], 0
0x18000c8a4  lea     rax, [rsp+270h+hKey]
0x18000c8a9  mov     [rsp+270h+cbData], 208h
0x18000c8b1  xor     r8d, r8d; ulOptions
0x18000c8b4  mov     [rsp+270h+phkResult], rax; phkResult
0x18000c8b9  mov     r9d, 20019h; samDesired
0x18000c8bf  mov     [rsp+270h+Type], 0
0x18000c8c7  lea     rbx, [rsp+270h+Data]
0x18000c8cc  call    cs:__imp_RegOpenKeyExW
0x18000c8d2  mov     edi, eax
0x18000c8d4  test    eax, eax
0x18000c8d6  jnz     loc_18000C9A4
0x18000c8dc  mov     rcx, [rsp+270h+hKey]; hKey
0x18000c8e1  lea     rax, [rsp+270h+cbData]
0x18000c8e6  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000c8eb  lea     r9, [rsp+270h+Type]; lpType
0x18000c8f0  lea     rax, [rsp+270h+Data]
0x18000c8f5  xor     r8d, r8d; lpReserved
0x18000c8f8  lea     rdx, ValueName; "Alias"
0x18000c8ff  mov     [rsp+270h+phkResult], rax; lpData
0x18000c904  call    cs:__imp_RegQueryValueExW
0x18000c90a  mov     edi, eax
0x18000c90c  cmp     eax, 0EAh
0x18000c911  jnz     short loc_18000C95C
0x18000c913  mov     edx, [rsp+270h+cbData]; uBytes
0x18000c917  mov     ecx, 40h ; '@'; uFlags
0x18000c91c  call    cs:__imp_LocalAlloc
0x18000c922  mov     rbx, rax
0x18000c925  test    rax, rax
0x18000c928  jnz     short loc_18000C931
0x18000c92a  mov     edi, 8
0x18000c92f  jmp     short loc_18000C9A4
0x18000c931  mov     rcx, [rsp+270h+hKey]; hKey
0x18000c936  lea     rax, [rsp+270h+cbData]
0x18000c93b  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000c940  lea     r9, [rsp+270h+Type]; lpType
0x18000c945  xor     r8d, r8d; lpReserved
0x18000c948  mov     [rsp+270h+phkResult], rbx; lpData
0x18000c94d  lea     rdx, ValueName; "Alias"
0x18000c954  call    cs:__imp_RegQueryValueExW
0x18000c95a  mov     edi, eax
0x18000c95c  test    edi, edi
0x18000c95e  jnz     short loc_18000C99F
0x18000c960  cmp     [rsp+270h+Type], 1
0x18000c965  jnz     short loc_18000C99F
0x18000c967  lea     rax, [rsp+270h+Data]
0x18000c96c  cmp     rbx, rax
0x18000c96f  jnz     short loc_18000C998
0x18000c971  mov     edx, [rsp+270h+cbData]; uBytes
0x18000c975  lea     ecx, [rdi+40h]; uFlags
0x18000c978  call    cs:__imp_LocalAlloc
0x18000c97e  mov     rbx, rax
0x18000c981  test    rax, rax
0x18000c984  jz      short loc_18000C92A
0x18000c986  mov     r8d, [rsp+270h+cbData]; Size
0x18000c98b  lea     rdx, [rsp+270h+Data]; Src
0x18000c990  mov     rcx, rax; void *
0x18000c993  call    memcpy_0
0x18000c998  mov     [rsi], rbx
0x18000c99b  xor     ebx, ebx
0x18000c99d  jmp     short loc_18000C9A4
0x18000c99f  mov     edi, 0Dh
0x18000c9a4  mov     rcx, [rsp+270h+hKey]; hKey
0x18000c9a9  test    rcx, rcx
0x18000c9ac  jz      short loc_18000C9B4
0x18000c9ae  call    cs:__imp_RegCloseKey
0x18000c9b4  test    rbx, rbx
0x18000c9b7  jz      short loc_18000C9CC
0x18000c9b9  lea     rax, [rsp+270h+Data]
0x18000c9be  cmp     rbx, rax
0x18000c9c1  jz      short loc_18000C9CC
0x18000c9c3  mov     rcx, rbx; hMem
0x18000c9c6  call    cs:__imp_LocalFree
0x18000c9cc  mov     eax, edi
0x18000c9ce  mov     rcx, [rbp+170h+var_20]
0x18000c9d5  xor     rcx, rsp; StackCookie
0x18000c9d8  call    __security_check_cookie
0x18000c9dd  mov     rbx, [rsp+270h+arg_18]
0x18000c9e5  add     rsp, 260h
0x18000c9ec  pop     rdi
0x18000c9ed  pop     rsi
0x18000c9ee  pop     rbp
0x18000c9ef  retn
```
