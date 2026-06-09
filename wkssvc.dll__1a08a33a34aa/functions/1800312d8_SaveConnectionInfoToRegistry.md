# SaveConnectionInfoToRegistry

- ea: `0x1800312d8`
- end: `0x18003149f`
- name: `SaveConnectionInfoToRegistry`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800315f8`

## callees

- `0x18003097c`
- `0x1800312d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031339`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031382`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800313bd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800313f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031429`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003145a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031339`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031382`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800313bd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800313f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031429`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003145a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031487`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031487`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180031471`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180031471`

## string_xrefs

- `0x18003136e`: `RemotePath`
- `0x1800313d6`: `SecurityDescriptor`

## pseudocode

```c
__int64 __fastcall SaveConnectionInfoToRegistry(HKEY a1, __int64 a2)
{
  const WCHAR *v3; // rdx
  unsigned int v4; // ebx
  const BYTE *lpData; // rcx
  __int64 v6; // rax

  v3 = *(const WCHAR **)a2;
  if ( !v3 )
    v3 = *(const WCHAR **)(a2 + 8);
  v4 = FindCreateOrDeleteConnectionKey(a1, v3);
  if ( !v4 )
  {
    v4 = RegSetValueExW(0, L"ProviderName", 0, 1u, L"Microsoft Windows Network", 0x34u);
    if ( !v4 )
    {
      lpData = *(const BYTE **)(a2 + 8);
      v6 = -1;
      do
        ++v6;
      while ( *(_WORD *)&lpData[2 * v6] );
      v4 = RegSetValueExW(0, L"RemotePath", 0, 1u, lpData, 2 * v6 + 2);
      if ( !v4 )
      {
        v4 = RegSetValueExW(0, L"UseOptions", 0, 3u, *(const BYTE **)(a2 + 24), *(_DWORD *)(a2 + 32));
        if ( !v4 )
        {
          v4 = RegSetValueExW(0, L"SecurityDescriptor", 0, 3u, *(const BYTE **)(a2 + 40), *(_DWORD *)(a2 + 48));
          if ( !v4 )
          {
            v4 = RegSetValueExW(0, L"ProviderFlags", 0, 4u, (const BYTE *)(a2 + 16), 4u);
            if ( !v4 )
            {
              v4 = RegSetValueExW(0, L"CredentialType", 0, 4u, (const BYTE *)(a2 + 20), 4u);
              if ( !v4 )
                RegFlushKey(0);
            }
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800312d8  push    rbx
0x1800312da  push    rbp
0x1800312db  push    rsi
0x1800312dc  push    rdi
0x1800312dd  sub     rsp, 38h
0x1800312e1  xor     esi, esi
0x1800312e3  mov     rdi, rdx
0x1800312e6  mov     rdx, [rdx]
0x1800312e9  mov     [rsp+58h+hKey], rsi
0x1800312ee  test    rdx, rdx
0x1800312f1  jnz     short loc_1800312F7
0x1800312f3  mov     rdx, [rdi+8]; SourceString
0x1800312f7  mov     ebp, 1
0x1800312fc  lea     r9, [rsp+58h+hKey]
0x180031301  mov     r8d, ebp
0x180031304  call    FindCreateOrDeleteConnectionKey
0x180031309  mov     ebx, eax
0x18003130b  test    eax, eax
0x18003130d  jnz     loc_18003147D
0x180031313  mov     rcx, [rsp+58h+hKey]; hKey
0x180031318  lea     rax, Data; "Microsoft Windows Network"
0x18003131f  mov     [rsp+58h+cbData], 34h ; '4'; cbData
0x180031327  lea     rdx, aProvidername; "ProviderName"
0x18003132e  mov     r9d, ebp; dwType
0x180031331  mov     [rsp+58h+lpData], rax; lpData
0x180031336  xor     r8d, r8d; Reserved
0x180031339  call    cs:__imp_RegSetValueExW
0x180031340  nop     dword ptr [rax+rax+00h]
0x180031345  mov     ebx, eax
0x180031347  test    eax, eax
0x180031349  jnz     loc_18003147D
0x18003134f  mov     rcx, [rdi+8]
0x180031353  or      rax, 0FFFFFFFFFFFFFFFFh
0x180031357  inc     rax
0x18003135a  cmp     [rcx+rax*2], si
0x18003135e  jnz     short loc_180031357
0x180031360  lea     eax, ds:2[rax*2]
0x180031367  mov     r9d, ebp; dwType
0x18003136a  mov     [rsp+58h+cbData], eax; cbData
0x18003136e  lea     rdx, aRemotepath; "RemotePath"
0x180031375  mov     [rsp+58h+lpData], rcx; lpData
0x18003137a  xor     r8d, r8d; Reserved
0x18003137d  mov     rcx, [rsp+58h+hKey]; hKey
0x180031382  call    cs:__imp_RegSetValueExW
0x180031389  nop     dword ptr [rax+rax+00h]
0x18003138e  mov     ebx, eax
0x180031390  test    eax, eax
0x180031392  jnz     loc_18003147D
0x180031398  mov     eax, [rdi+20h]
0x18003139b  lea     ebp, [rbx+3]
0x18003139e  mov     rcx, [rsp+58h+hKey]; hKey
0x1800313a3  lea     rdx, aUseoptions; "UseOptions"
0x1800313aa  mov     [rsp+58h+cbData], eax; cbData
0x1800313ae  mov     r9d, ebp; dwType
0x1800313b1  mov     rax, [rdi+18h]
0x1800313b5  xor     r8d, r8d; Reserved
0x1800313b8  mov     [rsp+58h+lpData], rax; lpData
0x1800313bd  call    cs:__imp_RegSetValueExW
0x1800313c4  nop     dword ptr [rax+rax+00h]
0x1800313c9  mov     ebx, eax
0x1800313cb  test    eax, eax
0x1800313cd  jnz     loc_18003147D
0x1800313d3  mov     eax, [rdi+30h]
0x1800313d6  lea     rdx, aSecuritydescri; "SecurityDescriptor"
0x1800313dd  mov     rcx, [rsp+58h+hKey]; hKey
0x1800313e2  mov     r9d, ebp; dwType
0x1800313e5  mov     [rsp+58h+cbData], eax; cbData
0x1800313e9  xor     r8d, r8d; Reserved
0x1800313ec  mov     rax, [rdi+28h]
0x1800313f0  mov     [rsp+58h+lpData], rax; lpData
0x1800313f5  call    cs:__imp_RegSetValueExW
0x1800313fc  nop     dword ptr [rax+rax+00h]
0x180031401  mov     ebx, eax
0x180031403  test    eax, eax
0x180031405  jnz     short loc_18003147D
0x180031407  mov     rcx, [rsp+58h+hKey]; hKey
0x18003140c  lea     ebp, [rbx+4]
0x18003140f  lea     rax, [rdi+10h]
0x180031413  mov     [rsp+58h+cbData], ebp; cbData
0x180031417  mov     r9d, ebp; dwType
0x18003141a  mov     [rsp+58h+lpData], rax; lpData
0x18003141f  xor     r8d, r8d; Reserved
0x180031422  lea     rdx, aProviderflags; "ProviderFlags"
0x180031429  call    cs:__imp_RegSetValueExW
0x180031430  nop     dword ptr [rax+rax+00h]
0x180031435  mov     ebx, eax
0x180031437  test    eax, eax
0x180031439  jnz     short loc_18003147D
0x18003143b  mov     rcx, [rsp+58h+hKey]; hKey
0x180031440  lea     rax, [rdi+14h]
0x180031444  mov     [rsp+58h+cbData], ebp; cbData
0x180031448  lea     rdx, aCredentialtype; "CredentialType"
0x18003144f  mov     r9d, ebp; dwType
0x180031452  mov     [rsp+58h+lpData], rax; lpData
0x180031457  xor     r8d, r8d; Reserved
0x18003145a  call    cs:__imp_RegSetValueExW
0x180031461  nop     dword ptr [rax+rax+00h]
0x180031466  mov     ebx, eax
0x180031468  test    eax, eax
0x18003146a  jnz     short loc_18003147D
0x18003146c  mov     rcx, [rsp+58h+hKey]; hKey
0x180031471  call    cs:__imp_RegFlushKey
0x180031478  nop     dword ptr [rax+rax+00h]
0x18003147d  mov     rcx, [rsp+58h+hKey]; hKey
0x180031482  test    rcx, rcx
0x180031485  jz      short loc_180031493
0x180031487  call    cs:__imp_RegCloseKey
0x18003148e  nop     dword ptr [rax+rax+00h]
0x180031493  mov     eax, ebx
0x180031495  add     rsp, 38h
0x180031499  pop     rdi
0x18003149a  pop     rsi
0x18003149b  pop     rbp
0x18003149c  pop     rbx
0x18003149d  retn
```
