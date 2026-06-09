# ScCreateDispatchTableW(_SERVICE_TABLE_ENTRYW const *,_INTERNAL_DISPATCH_TABLE * *)

- ea: `0x18000a87c`
- end: `0x18000a9f1`
- name: `?ScCreateDispatchTableW@@YAKPEBU_SERVICE_TABLE_ENTRYW@@PEAPEAU_INTERNAL_DISPATCH_TABLE@@@Z`
- size: `373`
- prototype: `unsigned int __fastcall(const struct _SERVICE_TABLE_ENTRYW *, struct _INTERNAL_DISPATCH_TABLE **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000a780`

## callees

- `0x18000a87c`
- `0x18000c870`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000a91c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000a91c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a9db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a9db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a8c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a8c8`

## string_xrefs

- `0x18000a90e`: `System\CurrentControlSet\Services`

## pseudocode

```c
__int64 __fastcall ScCreateDispatchTableW(const struct _SERVICE_TABLE_ENTRYW *a1, struct _INTERNAL_DISPATCH_TABLE **a2)
{
  const struct _SERVICE_TABLE_ENTRYW *v2; // rsi
  int v3; // eax
  _DWORD *v5; // rax
  _DWORD *v6; // rdi
  HKEY v7; // rax
  LPWSTR lpServiceName; // rax
  __int64 v9; // rcx
  unsigned __int16 *v10; // rdx
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF
  _DWORD *v12; // [rsp+70h] [rbp+18h]

  v2 = a1;
  hKey = 0;
  v3 = 0;
  while ( a1->lpServiceName )
  {
    ++v3;
    ++a1;
  }
  if ( !v3 )
    return 87;
  v5 = LocalAlloc(0x40u, 96LL * (unsigned int)(v3 + 1) + 8);
  if ( !v5 )
    return 8;
  *v5 = 875651923;
  hMem = v5;
  v6 = v5 + 2;
  v12 = v5 + 2;
  RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services", 0, 0x20019u, &hKey);
  v7 = hKey;
  while ( v2->lpServiceName )
  {
    *v6 = 892429139;
    lpServiceName = v2->lpServiceName;
    v9 = -1;
    do
      ++v9;
    while ( lpServiceName[v9] );
    *((_QWORD *)v6 + 1) = lpServiceName;
    v10 = (unsigned __int16 *)*((_QWORD *)v6 + 1);
    *((_QWORD *)v6 + 2) = v10;
    *((_QWORD *)v6 + 4) = v2->lpServiceProc;
    *((_QWORD *)v6 + 5) = 0;
    *((_QWORD *)v6 + 6) = 0;
    v6[14] = 0;
    v7 = hKey;
    if ( hKey )
    {
      if ( v9 )
      {
        ScReadServiceAliasFromRegistry(hKey, v10, (unsigned __int16 **)v6 + 3);
        v7 = hKey;
      }
    }
    ++v2;
    v6 += 24;
    v12 = v6;
  }
  if ( v7 )
    RegCloseKey(v7);
  return 0;
}

```

## disassembly

```asm
0x18000a87c  mov     [rsp+arg_18], rbx
0x18000a881  mov     [rsp+hKey], rdx
0x18000a886  push    rsi
0x18000a887  push    rdi
0x18000a888  push    r14
0x18000a88a  sub     rsp, 40h
0x18000a88e  mov     rsi, rcx
0x18000a891  xor     ebx, ebx
0x18000a893  mov     [rsp+58h+hKey], rbx
0x18000a898  mov     eax, ebx
0x18000a89a  jmp     short loc_18000A8A2
0x18000a89c  inc     eax
0x18000a89e  lea     rcx, [rcx+10h]
0x18000a8a2  cmp     [rcx], rbx
0x18000a8a5  jnz     short loc_18000A89C
0x18000a8a7  test    eax, eax
0x18000a8a9  jnz     short loc_18000A8B5
0x18000a8ab  mov     eax, 57h ; 'W'
0x18000a8b0  jmp     loc_18000A9E3
0x18000a8b5  inc     eax
0x18000a8b7  lea     rdx, [rax+rax*2]
0x18000a8bb  shl     rdx, 5
0x18000a8bf  add     rdx, 8; uBytes
0x18000a8c3  mov     ecx, 40h ; '@'; uFlags
0x18000a8c8  call    cs:__imp_LocalAlloc
0x18000a8ce  test    rax, rax
0x18000a8d1  jnz     short loc_18000A8DD
0x18000a8d3  mov     eax, 8
0x18000a8d8  jmp     loc_18000A9E3
0x18000a8dd  mov     dword ptr [rax], 34316353h
0x18000a8e3  mov     cs:hMem, rax
0x18000a8ea  mov     [rsp+58h+arg_0], rsi
0x18000a8ef  lea     rdi, [rax+8]
0x18000a8f3  mov     [rsp+58h+arg_10], rdi
0x18000a8f8  mov     r14d, ebx
0x18000a8fb  lea     rax, [rsp+58h+hKey]
0x18000a900  mov     [rsp+58h+phkResult], rax; phkResult
0x18000a905  mov     r9d, 20019h; samDesired
0x18000a90b  xor     r8d, r8d; ulOptions
0x18000a90e  lea     rdx, SubKey; "System\\CurrentControlSet\\Services"
0x18000a915  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a91c  call    cs:__imp_RegOpenKeyExA
0x18000a922  mov     rax, [rsp+58h+hKey]
0x18000a927  cmp     [rsi], rbx
0x18000a92a  jz      loc_18000A9D3
0x18000a930  test    r14d, r14d
0x18000a933  jnz     loc_18000A9D3
0x18000a939  mov     dword ptr [rdi], 35316353h
0x18000a93f  mov     rax, [rsi]
0x18000a942  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000a946  inc     rcx
0x18000a949  cmp     [rax+rcx*2], bx
0x18000a94d  jnz     short loc_18000A946
0x18000a94f  mov     [rsp+58h+var_28], rcx
0x18000a954  mov     [rdi+8], rax
0x18000a958  jmp     short loc_18000A97C
0x18000a95a  xor     ecx, ecx
0x18000a95c  mov     [rsp+58h+var_28], rcx
0x18000a961  lea     rax, Options
0x18000a968  mov     rdi, [rsp+58h+arg_10]
0x18000a96d  mov     [rdi+8], rax
0x18000a971  xor     ebx, ebx
0x18000a973  lea     r14d, [rcx+1]
0x18000a977  mov     rsi, [rsp+58h+arg_0]
0x18000a97c  mov     rdx, [rdi+8]; unsigned __int16 *
0x18000a980  mov     [rdi+10h], rdx
0x18000a984  mov     rax, [rsi+8]
0x18000a988  mov     [rdi+20h], rax
0x18000a98c  mov     [rdi+28h], rbx
0x18000a990  mov     [rdi+30h], rbx
0x18000a994  mov     [rdi+38h], ebx
0x18000a997  mov     rax, [rsp+58h+hKey]
0x18000a99c  test    rax, rax
0x18000a99f  jz      short loc_18000A9BC
0x18000a9a1  test    r14d, r14d
0x18000a9a4  jnz     short loc_18000A9BC
0x18000a9a6  test    rcx, rcx
0x18000a9a9  jz      short loc_18000A9BC
0x18000a9ab  lea     r8, [rdi+18h]; unsigned __int16 **
0x18000a9af  mov     rcx, rax; HKEY
0x18000a9b2  call    ?ScReadServiceAliasFromRegistry@@YAKPEAUHKEY__@@PEAGPEAPEAG@Z; ScReadServiceAliasFromRegistry(HKEY__ *,ushort *,ushort * *)
0x18000a9b7  mov     rax, [rsp+58h+hKey]
0x18000a9bc  add     rsi, 10h
0x18000a9c0  mov     [rsp+58h+arg_0], rsi
0x18000a9c5  add     rdi, 60h ; '`'
0x18000a9c9  mov     [rsp+58h+arg_10], rdi
0x18000a9ce  jmp     loc_18000A927
0x18000a9d3  test    rax, rax
0x18000a9d6  jz      short loc_18000A9E1
0x18000a9d8  mov     rcx, rax; hKey
0x18000a9db  call    cs:__imp_RegCloseKey
0x18000a9e1  xor     eax, eax
0x18000a9e3  mov     rbx, [rsp+58h+arg_18]
0x18000a9e8  add     rsp, 40h
0x18000a9ec  pop     r14
0x18000a9ee  pop     rdi
0x18000a9ef  pop     rsi
0x18000a9f0  retn
```
