# SaveConnectionInfoToRegistry

- ea: `0x18002e7a8`
- end: `0x18002e93e`
- name: `SaveConnectionInfoToRegistry`
- size: `406`
- prototype: `__int64 __fastcall(HKEY, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002ea70`

## callees

- `0x18002df2c`
- `0x18002e7a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e809`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e84c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e881`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e8b3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e8e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e90c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e809`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e84c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e881`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e8b3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e8e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e90c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e92d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e92d`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18002e91d`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18002e91d`

## string_xrefs

- `0x18002e838`: `RemotePath`
- `0x18002e894`: `SecurityDescriptor`

## pseudocode

```c
__int64 __fastcall SaveConnectionInfoToRegistry(HKEY a1, __int64 a2)
{
  wint_t *v3; // rdx
  unsigned int v4; // ebx
  const BYTE *lpData; // rcx
  __int64 v6; // rax
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  v3 = *(wint_t **)a2;
  hKey = 0;
  if ( !v3 )
    v3 = *(wint_t **)(a2 + 8);
  v4 = FindCreateOrDeleteConnectionKey(a1, v3, 1, &hKey);
  if ( !v4 )
  {
    v4 = RegSetValueExW(hKey, L"ProviderName", 0, 1u, L"Microsoft Windows Network", 0x34u);
    if ( !v4 )
    {
      lpData = *(const BYTE **)(a2 + 8);
      v6 = -1;
      do
        ++v6;
      while ( *(_WORD *)&lpData[2 * v6] );
      v4 = RegSetValueExW(hKey, L"RemotePath", 0, 1u, lpData, 2 * v6 + 2);
      if ( !v4 )
      {
        v4 = RegSetValueExW(hKey, L"UseOptions", 0, 3u, *(const BYTE **)(a2 + 24), *(_DWORD *)(a2 + 32));
        if ( !v4 )
        {
          v4 = RegSetValueExW(hKey, L"SecurityDescriptor", 0, 3u, *(const BYTE **)(a2 + 40), *(_DWORD *)(a2 + 48));
          if ( !v4 )
          {
            v4 = RegSetValueExW(hKey, L"ProviderFlags", 0, 4u, (const BYTE *)(a2 + 16), 4u);
            if ( !v4 )
            {
              v4 = RegSetValueExW(hKey, L"CredentialType", 0, 4u, (const BYTE *)(a2 + 20), 4u);
              if ( !v4 )
                RegFlushKey(hKey);
            }
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x18002e7a8  push    rbx
0x18002e7aa  push    rbp
0x18002e7ab  push    rsi
0x18002e7ac  push    rdi
0x18002e7ad  sub     rsp, 38h
0x18002e7b1  xor     esi, esi
0x18002e7b3  mov     rdi, rdx
0x18002e7b6  mov     rdx, [rdx]
0x18002e7b9  mov     [rsp+58h+hKey], rsi
0x18002e7be  test    rdx, rdx
0x18002e7c1  jnz     short loc_18002E7C7
0x18002e7c3  mov     rdx, [rdi+8]; SourceString
0x18002e7c7  mov     ebp, 1
0x18002e7cc  lea     r9, [rsp+58h+hKey]
0x18002e7d1  mov     r8d, ebp
0x18002e7d4  call    FindCreateOrDeleteConnectionKey
0x18002e7d9  mov     ebx, eax
0x18002e7db  test    eax, eax
0x18002e7dd  jnz     loc_18002E923
0x18002e7e3  mov     rcx, [rsp+58h+hKey]; hKey
0x18002e7e8  lea     rax, Data; "Microsoft Windows Network"
0x18002e7ef  mov     [rsp+58h+cbData], 34h ; '4'; cbData
0x18002e7f7  lea     rdx, aProvidername; "ProviderName"
0x18002e7fe  mov     r9d, ebp; dwType
0x18002e801  mov     [rsp+58h+lpData], rax; lpData
0x18002e806  xor     r8d, r8d; Reserved
0x18002e809  call    cs:__imp_RegSetValueExW
0x18002e80f  mov     ebx, eax
0x18002e811  test    eax, eax
0x18002e813  jnz     loc_18002E923
0x18002e819  mov     rcx, [rdi+8]
0x18002e81d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e821  inc     rax
0x18002e824  cmp     [rcx+rax*2], si
0x18002e828  jnz     short loc_18002E821
0x18002e82a  lea     eax, ds:2[rax*2]
0x18002e831  mov     r9d, ebp; dwType
0x18002e834  mov     [rsp+58h+cbData], eax; cbData
0x18002e838  lea     rdx, aRemotepath; "RemotePath"
0x18002e83f  mov     [rsp+58h+lpData], rcx; lpData
0x18002e844  xor     r8d, r8d; Reserved
0x18002e847  mov     rcx, [rsp+58h+hKey]; hKey
0x18002e84c  call    cs:__imp_RegSetValueExW
0x18002e852  mov     ebx, eax
0x18002e854  test    eax, eax
0x18002e856  jnz     loc_18002E923
0x18002e85c  mov     eax, [rdi+20h]
0x18002e85f  lea     ebp, [rbx+3]
0x18002e862  mov     rcx, [rsp+58h+hKey]; hKey
0x18002e867  lea     rdx, aUseoptions; "UseOptions"
0x18002e86e  mov     [rsp+58h+cbData], eax; cbData
0x18002e872  mov     r9d, ebp; dwType
0x18002e875  mov     rax, [rdi+18h]
0x18002e879  xor     r8d, r8d; Reserved
0x18002e87c  mov     [rsp+58h+lpData], rax; lpData
0x18002e881  call    cs:__imp_RegSetValueExW
0x18002e887  mov     ebx, eax
0x18002e889  test    eax, eax
0x18002e88b  jnz     loc_18002E923
0x18002e891  mov     eax, [rdi+30h]
0x18002e894  lea     rdx, aSecuritydescri; "SecurityDescriptor"
0x18002e89b  mov     rcx, [rsp+58h+hKey]; hKey
0x18002e8a0  mov     r9d, ebp; dwType
0x18002e8a3  mov     [rsp+58h+cbData], eax; cbData
0x18002e8a7  xor     r8d, r8d; Reserved
0x18002e8aa  mov     rax, [rdi+28h]
0x18002e8ae  mov     [rsp+58h+lpData], rax; lpData
0x18002e8b3  call    cs:__imp_RegSetValueExW
0x18002e8b9  mov     ebx, eax
0x18002e8bb  test    eax, eax
0x18002e8bd  jnz     short loc_18002E923
0x18002e8bf  mov     rcx, [rsp+58h+hKey]; hKey
0x18002e8c4  lea     ebp, [rbx+4]
0x18002e8c7  lea     rax, [rdi+10h]
0x18002e8cb  mov     [rsp+58h+cbData], ebp; cbData
0x18002e8cf  mov     r9d, ebp; dwType
0x18002e8d2  mov     [rsp+58h+lpData], rax; lpData
0x18002e8d7  xor     r8d, r8d; Reserved
0x18002e8da  lea     rdx, aProviderflags; "ProviderFlags"
0x18002e8e1  call    cs:__imp_RegSetValueExW
0x18002e8e7  mov     ebx, eax
0x18002e8e9  test    eax, eax
0x18002e8eb  jnz     short loc_18002E923
0x18002e8ed  mov     rcx, [rsp+58h+hKey]; hKey
0x18002e8f2  lea     rax, [rdi+14h]
0x18002e8f6  mov     [rsp+58h+cbData], ebp; cbData
0x18002e8fa  lea     rdx, aCredentialtype; "CredentialType"
0x18002e901  mov     r9d, ebp; dwType
0x18002e904  mov     [rsp+58h+lpData], rax; lpData
0x18002e909  xor     r8d, r8d; Reserved
0x18002e90c  call    cs:__imp_RegSetValueExW
0x18002e912  mov     ebx, eax
0x18002e914  test    eax, eax
0x18002e916  jnz     short loc_18002E923
0x18002e918  mov     rcx, [rsp+58h+hKey]; hKey
0x18002e91d  call    cs:__imp_RegFlushKey
0x18002e923  mov     rcx, [rsp+58h+hKey]; hKey
0x18002e928  test    rcx, rcx
0x18002e92b  jz      short loc_18002E933
0x18002e92d  call    cs:__imp_RegCloseKey
0x18002e933  mov     eax, ebx
0x18002e935  add     rsp, 38h
0x18002e939  pop     rdi
0x18002e93a  pop     rsi
0x18002e93b  pop     rbp
0x18002e93c  pop     rbx
0x18002e93d  retn
```
