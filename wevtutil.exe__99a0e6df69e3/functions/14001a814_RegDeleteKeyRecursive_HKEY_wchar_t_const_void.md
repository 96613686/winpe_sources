# RegDeleteKeyRecursive(HKEY__ *,wchar_t const *,void *)

- ea: `0x14001a814`
- end: `0x14001a94f`
- name: `?RegDeleteKeyRecursive@@YAJPEAUHKEY__@@PEB_WPEAX@Z`
- size: `315`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, void *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140009b58`
- `0x140014988`
- `0x14001a814`
- `0x14001d828`
- `0x14001e0c0`
- `0x14001eb9c`

## callees

- `0x14001a814`
- `0x140021b00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001a87e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001a87e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a8f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a8f0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14001a922`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14001a922`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14001a8c7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14001a8c7`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x14001a91a`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x14001a91a`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x14001a86e`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x14001a86e`

## pseudocode

```c
__int64 __fastcall RegDeleteKeyRecursive(HKEY a1, const wchar_t *a2, void *hTransaction)
{
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  HKEY hKey; // [rsp+40h] [rbp-248h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-240h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-238h] BYREF

  hKey = 0;
  if ( hTransaction == (void *)-1LL )
    v6 = RegOpenKeyExW(a1, a2, 0, 0x2001Fu, &hKey);
  else
    v6 = RegOpenKeyTransactedW(a1, a2, 0, 0x2001Fu, &hKey, hTransaction, 0);
  v7 = v6;
  if ( !v6 )
  {
    do
    {
      cchName = 260;
      v7 = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0);
      if ( v7 )
        break;
      v7 = RegDeleteKeyRecursive(hKey, Name, hTransaction);
    }
    while ( !v7 );
    RegCloseKey(hKey);
  }
  if ( v7 == 259 )
  {
    if ( hTransaction == (void *)-1LL )
      return (unsigned int)RegDeleteKeyExW(a1, a2, 0, 0);
    else
      return (unsigned int)RegDeleteKeyTransactedW(a1, a2, 0, 0, hTransaction, 0);
  }
  return v7;
}

```

## disassembly

```asm
0x14001a814  mov     [rsp+arg_18], rbx
0x14001a819  push    rbp
0x14001a81a  push    rsi
0x14001a81b  push    rdi
0x14001a81c  sub     rsp, 270h
0x14001a823  mov     rax, cs:__security_cookie
0x14001a82a  xor     rax, rsp
0x14001a82d  mov     [rsp+288h+var_28], rax
0x14001a835  mov     [rsp+288h+hKey], 0
0x14001a83e  mov     rdi, r8
0x14001a841  lea     rax, [rsp+288h+hKey]
0x14001a846  mov     rbp, rdx
0x14001a849  mov     rsi, rcx
0x14001a84c  mov     r9d, 2001Fh; samDesired
0x14001a852  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14001a856  jz      short loc_14001A876
0x14001a858  mov     [rsp+288h+pExtendedParemeter], 0; pExtendedParemeter
0x14001a861  mov     [rsp+288h+hTransaction], r8; hTransaction
0x14001a866  xor     r8d, r8d; ulOptions
0x14001a869  mov     [rsp+288h+phkResult], rax; phkResult
0x14001a86e  call    cs:__imp_RegOpenKeyTransactedW
0x14001a874  jmp     short loc_14001A884
0x14001a876  xor     r8d, r8d; ulOptions
0x14001a879  mov     [rsp+288h+phkResult], rax; phkResult
0x14001a87e  call    cs:__imp_RegOpenKeyExW
0x14001a884  mov     ebx, eax
0x14001a886  test    eax, eax
0x14001a888  jnz     short loc_14001A8F6
0x14001a88a  mov     rcx, [rsp+288h+hKey]; hKey
0x14001a88f  lea     r9, [rsp+288h+cchName]; lpcchName
0x14001a894  mov     [rsp+288h+lpftLastWriteTime], 0; lpftLastWriteTime
0x14001a89d  lea     r8, [rsp+288h+Name]; lpName
0x14001a8a2  mov     [rsp+288h+pExtendedParemeter], 0; lpcchClass
0x14001a8ab  xor     edx, edx; dwIndex
0x14001a8ad  mov     [rsp+288h+hTransaction], 0; lpClass
0x14001a8b6  mov     [rsp+288h+phkResult], 0; lpReserved
0x14001a8bf  mov     [rsp+288h+cchName], 104h
0x14001a8c7  call    cs:__imp_RegEnumKeyExW
0x14001a8cd  mov     ebx, eax
0x14001a8cf  test    eax, eax
0x14001a8d1  jnz     short loc_14001A8EB
0x14001a8d3  mov     rcx, [rsp+288h+hKey]; HKEY
0x14001a8d8  lea     rdx, [rsp+288h+Name]; wchar_t *
0x14001a8dd  mov     r8, rdi; void *
0x14001a8e0  call    ?RegDeleteKeyRecursive@@YAJPEAUHKEY__@@PEB_WPEAX@Z; RegDeleteKeyRecursive(HKEY__ *,wchar_t const *,void *)
0x14001a8e5  mov     ebx, eax
0x14001a8e7  test    eax, eax
0x14001a8e9  jz      short loc_14001A88A
0x14001a8eb  mov     rcx, [rsp+288h+hKey]; hKey
0x14001a8f0  call    cs:__imp_RegCloseKey
0x14001a8f6  cmp     ebx, 103h
0x14001a8fc  jnz     short loc_14001A92A
0x14001a8fe  xor     r9d, r9d; Reserved
0x14001a901  xor     r8d, r8d; samDesired
0x14001a904  mov     rdx, rbp; lpSubKey
0x14001a907  mov     rcx, rsi; hKey
0x14001a90a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14001a90e  jz      short loc_14001A922
0x14001a910  mov     [rsp+288h+hTransaction], r8; pExtendedParameter
0x14001a915  mov     [rsp+288h+phkResult], rdi; hTransaction
0x14001a91a  call    cs:__imp_RegDeleteKeyTransactedW
0x14001a920  jmp     short loc_14001A928
0x14001a922  call    cs:__imp_RegDeleteKeyExW
0x14001a928  mov     ebx, eax
0x14001a92a  mov     eax, ebx
0x14001a92c  mov     rcx, [rsp+288h+var_28]
0x14001a934  xor     rcx, rsp; StackCookie
0x14001a937  call    __security_check_cookie
0x14001a93c  mov     rbx, [rsp+288h+arg_18]
0x14001a944  add     rsp, 270h
0x14001a94b  pop     rdi
0x14001a94c  pop     rsi
0x14001a94d  pop     rbp
0x14001a94e  retn
```
