# NtDigestInitReadRegistry

- ea: `0x1800265e4`
- end: `0x180026692`
- name: `NtDigestInitReadRegistry`
- size: `174`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026ad0`
- `0x180031510`

## callees

- `0x1800185b8`
- `0x1800265e4`
- `0x180026698`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180026644`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180026644`

## string_xrefs

- `0x180026625`: `System\CurrentControlSet\Control\SecurityProviders\WDigest`

## pseudocode

```c
__int64 NtDigestInitReadRegistry()
{
  unsigned int v0; // eax
  DWORD v2; // [rsp+60h] [rbp+8h] BYREF

  v2 = 0;
  if ( g_hkBase )
    return 1;
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\SecurityProviders\\WDigest",
         0,
         (LPWSTR)&Class,
         0,
         0x20019u,
         0,
         &g_hkBase,
         &v2);
  if ( !v0 )
  {
    NtDigestReadRegistry();
    return 1;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids, v0);
  return 0;
}

```

## disassembly

```asm
0x1800265e4  mov     r11, rsp
0x1800265e7  sub     rsp, 58h
0x1800265eb  cmp     cs:?g_hkBase@@3PEAUHKEY__@@EA, 0; HKEY__ * g_hkBase
0x1800265f3  mov     [rsp+58h+arg_0], 0
0x1800265fb  jnz     loc_180026688
0x180026601  lea     rax, [r11+8]
0x180026605  xor     r8d, r8d; Reserved
0x180026608  mov     [r11-18h], rax
0x18002660c  lea     r9, Class; lpClass
0x180026613  lea     rax, ?g_hkBase@@3PEAUHKEY__@@EA; HKEY__ * g_hkBase
0x18002661a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026621  mov     [r11-20h], rax
0x180026625  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Sec"...
0x18002662c  mov     qword ptr [r11-28h], 0
0x180026634  mov     [rsp+58h+samDesired], 20019h; samDesired
0x18002663c  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180026644  call    cs:__imp_RegCreateKeyExW
0x18002664a  test    eax, eax
0x18002664c  jz      short loc_180026683
0x18002664e  mov     rcx, cs:WPP_GLOBAL_Control
0x180026655  lea     rdx, WPP_GLOBAL_Control
0x18002665c  cmp     rcx, rdx
0x18002665f  jz      short loc_18002667F
0x180026661  test    byte ptr [rcx+1Ch], 2
0x180026665  jz      short loc_18002667F
0x180026667  mov     rcx, [rcx+10h]
0x18002666b  lea     r8, WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids
0x180026672  mov     edx, 35h ; '5'
0x180026677  mov     r9d, eax
0x18002667a  call    WPP_SF_d
0x18002667f  xor     eax, eax
0x180026681  jmp     short loc_18002668D
0x180026683  call    NtDigestReadRegistry
0x180026688  mov     eax, 1
0x18002668d  add     rsp, 58h
0x180026691  retn
```
