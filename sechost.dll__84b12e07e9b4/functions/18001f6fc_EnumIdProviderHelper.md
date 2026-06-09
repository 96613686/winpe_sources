# EnumIdProviderHelper

- ea: `0x18001f6fc`
- end: `0x18001f895`
- name: `EnumIdProviderHelper`
- size: `409`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f940`

## callees

- `0x18001f6fc`
- `0x18004fa50`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001f809`
- `ntdll!RtlInitUnicodeString` at `0x18001f809`
- `ntdll!RtlGUIDFromString` at `0x18001f817`
- `ntdll!RtlGUIDFromString` at `0x18001f817`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f793`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f793`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f85f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f85f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001f7e5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001f7e5`

## pseudocode

```c
__int64 __fastcall EnumIdProviderHelper(HKEY *a1, DWORD a2, WCHAR *a3, __int64 a4, _DWORD *a5, GUID *a6)
{
  int v9; // esi
  HKEY v10; // rcx
  unsigned int v11; // ebx
  LSTATUS v12; // eax
  DWORD cchName; // [rsp+40h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-30h] BYREF
  GUID Guid; // [rsp+60h] [rbp-20h] BYREF

  cchName = 0;
  Guid = 0;
  DestinationString = 0;
  if ( a1 && a3 && a5 )
  {
    *a5 = 0;
    v9 = 0;
    v10 = *a1;
    hKey = v10;
    if ( !v10 )
    {
      v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\IdentityStore\\Providers", 0, 0x20019u, &hKey);
      if ( v11 )
      {
        if ( v11 - 2 <= 1 )
          return 259;
        return v11;
      }
      v10 = hKey;
      v9 = 1;
    }
    cchName = 64;
    v12 = RegEnumKeyExW(v10, a2, a3, &cchName, 0, 0, 0, 0);
    v11 = v12;
    if ( v12 != 234 )
    {
      if ( v12 )
        goto LABEL_19;
      if ( cchName + 1 <= 0x40 )
      {
        RtlInitUnicodeString(&DestinationString, a3);
        if ( RtlGUIDFromString(&DestinationString, &Guid) >= 0 )
        {
          if ( v9 )
            *a1 = hKey;
          if ( a6 )
            *a6 = Guid;
          return 0;
        }
      }
    }
    v11 = 13;
    *a5 = 1;
LABEL_19:
    if ( v9 )
    {
      if ( *a5 )
        *a1 = hKey;
      else
        RegCloseKey(hKey);
    }
    return v11;
  }
  return 87;
}

```

## disassembly

```asm
0x18001f6fc  mov     [rsp-38h+arg_18], rbx
0x18001f701  push    rbp
0x18001f702  push    rsi
0x18001f703  push    rdi
0x18001f704  push    r12
0x18001f706  push    r13
0x18001f708  push    r14
0x18001f70a  push    r15
0x18001f70c  mov     rbp, rsp
0x18001f70f  sub     rsp, 80h
0x18001f716  mov     rax, cs:__security_cookie
0x18001f71d  xor     rax, rsp
0x18001f720  mov     [rbp+var_10], rax
0x18001f724  mov     rdi, [rbp+arg_20]
0x18001f728  xor     eax, eax
0x18001f72a  mov     r15, [rbp+arg_28]
0x18001f72e  xorps   xmm0, xmm0
0x18001f731  mov     [rbp+cchName], eax
0x18001f734  xorps   xmm1, xmm1
0x18001f737  mov     r12, r8
0x18001f73a  mov     r13d, edx
0x18001f73d  mov     r14, rcx
0x18001f740  movups  xmmword ptr [rbp+Guid.Data1], xmm0
0x18001f744  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x18001f748  test    rcx, rcx
0x18001f74b  jz      loc_18001F869
0x18001f751  test    r8, r8
0x18001f754  jz      loc_18001F869
0x18001f75a  test    rdi, rdi
0x18001f75d  jz      loc_18001F869
0x18001f763  mov     [rdi], eax
0x18001f765  mov     esi, eax
0x18001f767  mov     rcx, [rcx]
0x18001f76a  mov     [rbp+hKey], rcx
0x18001f76e  test    rcx, rcx
0x18001f771  jnz     short loc_18001F7C0
0x18001f773  lea     rax, [rbp+hKey]
0x18001f777  mov     r9d, 20019h; samDesired
0x18001f77d  xor     r8d, r8d; ulOptions
0x18001f780  mov     [rsp+80h+phkResult], rax; phkResult
0x18001f785  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\IdentityStore\\Pro"...
0x18001f78c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f793  call    cs:__imp_RegOpenKeyExW
0x18001f799  mov     ebx, eax
0x18001f79b  xor     eax, eax
0x18001f79d  test    ebx, ebx
0x18001f79f  jz      short loc_18001F7B7
0x18001f7a1  lea     ecx, [rbx-2]
0x18001f7a4  cmp     ecx, 1
0x18001f7a7  ja      loc_18001F865
0x18001f7ad  mov     ebx, 103h
0x18001f7b2  jmp     loc_18001F865
0x18001f7b7  mov     rcx, [rbp+hKey]; hKey
0x18001f7bb  mov     esi, 1
0x18001f7c0  mov     [rsp+80h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18001f7c5  lea     r9, [rbp+cchName]; lpcchName
0x18001f7c9  mov     [rsp+80h+lpcchClass], rax; lpcchClass
0x18001f7ce  mov     r8, r12; lpName
0x18001f7d1  mov     [rsp+80h+lpClass], rax; lpClass
0x18001f7d6  mov     edx, r13d; dwIndex
0x18001f7d9  mov     [rsp+80h+phkResult], rax; lpReserved
0x18001f7de  mov     [rbp+cchName], 40h ; '@'
0x18001f7e5  call    cs:__imp_RegEnumKeyExW
0x18001f7eb  mov     ebx, eax
0x18001f7ed  cmp     eax, 0EAh
0x18001f7f2  jz      short loc_18001F83E
0x18001f7f4  test    eax, eax
0x18001f7f6  jnz     short loc_18001F849
0x18001f7f8  mov     eax, [rbp+cchName]
0x18001f7fb  inc     eax
0x18001f7fd  cmp     eax, 40h ; '@'
0x18001f800  ja      short loc_18001F83E
0x18001f802  mov     rdx, r12; SourceString
0x18001f805  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001f809  call    cs:__imp_RtlInitUnicodeString
0x18001f80f  lea     rdx, [rbp+Guid]; Guid
0x18001f813  lea     rcx, [rbp+DestinationString]; GuidString
0x18001f817  call    cs:__imp_RtlGUIDFromString
0x18001f81d  test    eax, eax
0x18001f81f  js      short loc_18001F83E
0x18001f821  test    esi, esi
0x18001f823  jz      short loc_18001F82C
0x18001f825  mov     rax, [rbp+hKey]
0x18001f829  mov     [r14], rax
0x18001f82c  test    r15, r15
0x18001f82f  jz      short loc_18001F83A
0x18001f831  movups  xmm0, xmmword ptr [rbp+Guid.Data1]
0x18001f835  movdqu  xmmword ptr [r15], xmm0
0x18001f83a  xor     ebx, ebx
0x18001f83c  jmp     short loc_18001F865
0x18001f83e  mov     ebx, 0Dh
0x18001f843  mov     dword ptr [rdi], 1
0x18001f849  test    esi, esi
0x18001f84b  jz      short loc_18001F865
0x18001f84d  cmp     dword ptr [rdi], 0
0x18001f850  jz      short loc_18001F85B
0x18001f852  mov     rax, [rbp+hKey]
0x18001f856  mov     [r14], rax
0x18001f859  jmp     short loc_18001F865
0x18001f85b  mov     rcx, [rbp+hKey]; hKey
0x18001f85f  call    cs:__imp_RegCloseKey
0x18001f865  mov     eax, ebx
0x18001f867  jmp     short loc_18001F86E
0x18001f869  mov     eax, 57h ; 'W'
0x18001f86e  mov     rcx, [rbp+var_10]
0x18001f872  xor     rcx, rsp; StackCookie
0x18001f875  call    __security_check_cookie
0x18001f87a  mov     rbx, [rsp+80h+arg_18]
0x18001f882  add     rsp, 80h
0x18001f889  pop     r15
0x18001f88b  pop     r14
0x18001f88d  pop     r13
0x18001f88f  pop     r12
0x18001f891  pop     rdi
0x18001f892  pop     rsi
0x18001f893  pop     rbp
0x18001f894  retn
```
