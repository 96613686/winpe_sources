# RegDeleteKeyRecursive(HKEY__ *,wchar_t const *,void *)

- ea: `0x1800be098`
- end: `0x1800be1ab`
- name: `?RegDeleteKeyRecursive@@YAJPEAUHKEY__@@PEB_WPEAX@Z`
- size: `275`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180055b58`
- `0x1800be098`
- `0x1800bf644`

## callees

- `0x180006600`
- `0x18009aee0`
- `0x1800be098`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be14c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be14c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800be17e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800be17e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800be123`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800be123`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x1800be176`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x1800be176`

## pseudocode

```c
__int64 __fastcall RegDeleteKeyRecursive(HKEY a1, const wchar_t *a2, void *a3)
{
  unsigned int v6; // ebx
  HKEY hKey; // [rsp+40h] [rbp-248h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-240h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-238h] BYREF

  hKey = 0;
  v6 = OpenRegKey(a1, a2, 0x2001Fu, &hKey, a3);
  if ( !v6 )
  {
    do
    {
      cchName = 260;
      v6 = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0);
      if ( v6 )
        break;
      v6 = RegDeleteKeyRecursive(hKey, Name, a3);
    }
    while ( !v6 );
    RegCloseKey(hKey);
  }
  if ( v6 == 259 )
  {
    if ( a3 == (void *)-1LL )
      return (unsigned int)RegDeleteKeyExW(a1, a2, 0, 0);
    else
      return (unsigned int)RegDeleteKeyTransactedW(a1, a2, 0, 0, a3, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x1800be098  mov     [rsp+arg_18], rbx
0x1800be09d  push    rbp
0x1800be09e  push    rsi
0x1800be09f  push    rdi
0x1800be0a0  sub     rsp, 270h
0x1800be0a7  mov     rax, cs:__security_cookie
0x1800be0ae  xor     rax, rsp
0x1800be0b1  mov     [rsp+288h+var_28], rax
0x1800be0b9  mov     rdi, r8
0x1800be0bc  mov     [rsp+288h+lpReserved], r8; void *
0x1800be0c1  mov     r8d, 2001Fh; unsigned int
0x1800be0c7  mov     [rsp+288h+hKey], 0
0x1800be0d0  lea     r9, [rsp+288h+hKey]; HKEY *
0x1800be0d5  mov     rbp, rdx
0x1800be0d8  mov     rsi, rcx
0x1800be0db  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x1800be0e0  mov     ebx, eax
0x1800be0e2  test    eax, eax
0x1800be0e4  jnz     short loc_1800BE152
0x1800be0e6  mov     rcx, [rsp+288h+hKey]; hKey
0x1800be0eb  lea     r9, [rsp+288h+cchName]; lpcchName
0x1800be0f0  mov     [rsp+288h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800be0f9  lea     r8, [rsp+288h+Name]; lpName
0x1800be0fe  mov     [rsp+288h+lpcchClass], 0; lpcchClass
0x1800be107  xor     edx, edx; dwIndex
0x1800be109  mov     [rsp+288h+lpClass], 0; lpClass
0x1800be112  mov     [rsp+288h+lpReserved], 0; lpReserved
0x1800be11b  mov     [rsp+288h+cchName], 104h
0x1800be123  call    cs:__imp_RegEnumKeyExW
0x1800be129  mov     ebx, eax
0x1800be12b  test    eax, eax
0x1800be12d  jnz     short loc_1800BE147
0x1800be12f  mov     rcx, [rsp+288h+hKey]; HKEY
0x1800be134  lea     rdx, [rsp+288h+Name]; wchar_t *
0x1800be139  mov     r8, rdi; void *
0x1800be13c  call    ?RegDeleteKeyRecursive@@YAJPEAUHKEY__@@PEB_WPEAX@Z; RegDeleteKeyRecursive(HKEY__ *,wchar_t const *,void *)
0x1800be141  mov     ebx, eax
0x1800be143  test    eax, eax
0x1800be145  jz      short loc_1800BE0E6
0x1800be147  mov     rcx, [rsp+288h+hKey]; hKey
0x1800be14c  call    cs:__imp_RegCloseKey
0x1800be152  cmp     ebx, 103h
0x1800be158  jnz     short loc_1800BE186
0x1800be15a  xor     r9d, r9d; Reserved
0x1800be15d  xor     r8d, r8d; samDesired
0x1800be160  mov     rdx, rbp; lpSubKey
0x1800be163  mov     rcx, rsi; hKey
0x1800be166  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800be16a  jz      short loc_1800BE17E
0x1800be16c  mov     [rsp+288h+lpClass], r8; pExtendedParameter
0x1800be171  mov     [rsp+288h+lpReserved], rdi; hTransaction
0x1800be176  call    cs:__imp_RegDeleteKeyTransactedW
0x1800be17c  jmp     short loc_1800BE184
0x1800be17e  call    cs:__imp_RegDeleteKeyExW
0x1800be184  mov     ebx, eax
0x1800be186  mov     eax, ebx
0x1800be188  mov     rcx, [rsp+288h+var_28]
0x1800be190  xor     rcx, rsp; StackCookie
0x1800be193  call    __security_check_cookie
0x1800be198  mov     rbx, [rsp+288h+arg_18]
0x1800be1a0  add     rsp, 270h
0x1800be1a7  pop     rdi
0x1800be1a8  pop     rsi
0x1800be1a9  pop     rbp
0x1800be1aa  retn
```
