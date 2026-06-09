# UnloadSslRegOptions(void)

- ea: `0x180054a8c`
- end: `0x180054b8b`
- name: `?UnloadSslRegOptions@@YAXXZ`
- size: `255`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180054884`

## callees

- `0x180054a8c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054b52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054b6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054b52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054b6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054ade`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054ade`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054af5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054af5`
- `ntdll!RtlDeregisterWait` at `0x180054ac8`
- `ntdll!RtlDeregisterWait` at `0x180054b18`
- `ntdll!RtlDeregisterWait` at `0x180054ac8`
- `ntdll!RtlDeregisterWait` at `0x180054b18`
- `bcrypt!BCryptUnregisterConfigChangeNotify` at `0x180054b35`
- `bcrypt!BCryptUnregisterConfigChangeNotify` at `0x180054b35`

## pseudocode

```c
void UnloadSslRegOptions(void)
{
  __int64 v0; // rdi
  __int64 v1; // rbx
  HKEY v2; // rcx
  void *v3; // rcx
  _QWORD v4[5]; // [rsp+20h] [rbp-28h]

  v0 = 0;
  v4[0] = &g_BaseSslRegOptions;
  v4[1] = &g_FipsRegOptions;
  v4[2] = &g_UserMappingRegOptions;
  do
  {
    v1 = v4[v0];
    if ( *(_QWORD *)v1 )
    {
      RtlDeregisterWait(*(HANDLE *)v1);
      *(_QWORD *)v1 = 0;
    }
    v2 = *(HKEY *)(v1 + 16);
    if ( v2 )
    {
      RegCloseKey(v2);
      *(_QWORD *)(v1 + 16) = 0;
    }
    v3 = *(void **)(v1 + 8);
    if ( v3 )
    {
      CloseHandle(v3);
      *(_QWORD *)(v1 + 8) = 0;
    }
    ++v0;
  }
  while ( v0 != 3 );
  if ( g_hBcryptWait )
  {
    RtlDeregisterWait(g_hBcryptWait);
    g_hBcryptWait = 0;
  }
  if ( g_hBcryptEvent )
  {
    BCryptUnregisterConfigChangeNotify(g_hBcryptEvent);
    g_hBcryptEvent = 0;
  }
  if ( g_pszDomainList )
  {
    LocalFree(g_pszDomainList);
    g_pszDomainList = 0;
  }
  if ( g_pszOcspReadDirectory )
  {
    LocalFree(g_pszOcspReadDirectory);
    g_pszOcspReadDirectory = 0;
  }
}

```

## disassembly

```asm
0x180054a8c  mov     r11, rsp
0x180054a8f  mov     [r11+8], rbx
0x180054a93  push    rdi
0x180054a94  sub     rsp, 40h
0x180054a98  lea     rax, ?g_BaseSslRegOptions@@3USSL_REG_OPTIONS@@A; SSL_REG_OPTIONS g_BaseSslRegOptions
0x180054a9f  xor     edi, edi
0x180054aa1  mov     [r11-28h], rax
0x180054aa5  lea     rax, ?g_FipsRegOptions@@3USSL_REG_OPTIONS@@A; SSL_REG_OPTIONS g_FipsRegOptions
0x180054aac  mov     [r11-20h], rax
0x180054ab0  lea     rax, ?g_UserMappingRegOptions@@3USSL_REG_OPTIONS@@A; SSL_REG_OPTIONS g_UserMappingRegOptions
0x180054ab7  mov     [r11-18h], rax
0x180054abb  mov     rbx, [rsp+rdi*8+48h+var_28]
0x180054ac0  mov     rcx, [rbx]; hWaitHandle
0x180054ac3  test    rcx, rcx
0x180054ac6  jz      short loc_180054AD5
0x180054ac8  call    cs:__imp_RtlDeregisterWait
0x180054ace  mov     qword ptr [rbx], 0
0x180054ad5  mov     rcx, [rbx+10h]; hKey
0x180054ad9  test    rcx, rcx
0x180054adc  jz      short loc_180054AEC
0x180054ade  call    cs:__imp_RegCloseKey
0x180054ae4  mov     qword ptr [rbx+10h], 0
0x180054aec  mov     rcx, [rbx+8]; hObject
0x180054af0  test    rcx, rcx
0x180054af3  jz      short loc_180054B03
0x180054af5  call    cs:__imp_CloseHandle
0x180054afb  mov     qword ptr [rbx+8], 0
0x180054b03  inc     rdi
0x180054b06  cmp     rdi, 3
0x180054b0a  jnz     short loc_180054ABB
0x180054b0c  mov     rcx, cs:?g_hBcryptWait@@3PEAXEA; hWaitHandle
0x180054b13  test    rcx, rcx
0x180054b16  jz      short loc_180054B29
0x180054b18  call    cs:__imp_RtlDeregisterWait
0x180054b1e  mov     cs:?g_hBcryptWait@@3PEAXEA, 0; void * g_hBcryptWait
0x180054b29  mov     rcx, cs:?g_hBcryptEvent@@3PEAXEA; hEvent
0x180054b30  test    rcx, rcx
0x180054b33  jz      short loc_180054B46
0x180054b35  call    cs:__imp_BCryptUnregisterConfigChangeNotify
0x180054b3b  mov     cs:?g_hBcryptEvent@@3PEAXEA, 0; void * g_hBcryptEvent
0x180054b46  mov     rcx, cs:?g_pszDomainList@@3PEAGEA; hMem
0x180054b4d  test    rcx, rcx
0x180054b50  jz      short loc_180054B63
0x180054b52  call    cs:__imp_LocalFree
0x180054b58  mov     cs:?g_pszDomainList@@3PEAGEA, 0; ushort * g_pszDomainList
0x180054b63  mov     rcx, cs:?g_pszOcspReadDirectory@@3PEAGEA; hMem
0x180054b6a  test    rcx, rcx
0x180054b6d  jz      short loc_180054B80
0x180054b6f  call    cs:__imp_LocalFree
0x180054b75  mov     cs:?g_pszOcspReadDirectory@@3PEAGEA, 0; ushort * g_pszOcspReadDirectory
0x180054b80  mov     rbx, [rsp+48h+arg_0]
0x180054b85  add     rsp, 40h
0x180054b89  pop     rdi
0x180054b8a  retn
```
