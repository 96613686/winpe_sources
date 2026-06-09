# EnsureUserTileRegKey(ushort const *)

- ea: `0x1800708a0`
- end: `0x1800709aa`
- name: `?EnsureUserTileRegKey@@YAJPEBG@Z`
- size: `266`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180060d60`

## callees

- `0x1800708a0`
- `0x180070c20`
- `0x180073cec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070991`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070991`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007097f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007097f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070975`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070975`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180070958`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180070958`

## pseudocode

```c
__int64 __fastcall EnsureUserTileRegKey(const unsigned __int16 *a1)
{
  const unsigned __int16 *v1; // rcx
  int UserTileRegPath; // ebx
  LSTATUS v3; // eax
  WCHAR *v4; // rcx
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+50h] [rbp+17h] BYREF
  _OWORD v7[2]; // [rsp+68h] [rbp+2Fh] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp+4Fh]
  DWORD dwDisposition; // [rsp+A8h] [rbp+6Fh] BYREF
  LPCWSTR lpSubKey; // [rsp+B0h] [rbp+77h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+7Fh] BYREF

  lpSubKey = 0;
  UserTileRegPath = GetUserTileRegPath(a1, (LPWSTR *)&lpSubKey);
  if ( UserTileRegPath >= 0 )
  {
    memset(v7, 0, sizeof(v7));
    hMem = 0;
    UserTileRegPath = GetCustomSecurityDescriptor(v1, v7);
    if ( UserTileRegPath >= 0 )
    {
      SecurityAttributes.lpSecurityDescriptor = v7;
      *(_QWORD *)&SecurityAttributes.nLength = 24;
      *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
      dwDisposition = 0;
      hKey = 0;
      v3 = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             lpSubKey,
             0,
             (LPWSTR)&Class,
             0,
             0x2011Fu,
             &SecurityAttributes,
             &hKey,
             &dwDisposition);
      UserTileRegPath = v3;
      if ( v3 > 0 )
        UserTileRegPath = (unsigned __int16)v3 | 0x80070000;
      if ( UserTileRegPath >= 0 )
        RegCloseKey(hKey);
      LocalFree(hMem);
    }
  }
  v4 = (WCHAR *)lpSubKey;
  lpSubKey = 0;
  CoTaskMemFree(v4);
  return (unsigned int)UserTileRegPath;
}

```

## disassembly

```asm
0x1800708a0  mov     [rsp-8+arg_0], rbx
0x1800708a5  push    rbp
0x1800708a6  lea     rbp, [rsp-57h]
0x1800708ab  sub     rsp, 90h
0x1800708b2  lea     rdx, [rbp+57h+lpSubKey]; ppwsz
0x1800708b6  mov     [rbp+57h+lpSubKey], 0
0x1800708be  call    ?GetUserTileRegPath@@YAJPEBGPEAPEAG@Z; GetUserTileRegPath(ushort const *,ushort * *)
0x1800708c3  mov     ebx, eax
0x1800708c5  test    eax, eax
0x1800708c7  js      loc_180070985
0x1800708cd  xorps   xmm0, xmm0
0x1800708d0  lea     rdx, [rbp+57h+var_28]; void *
0x1800708d4  xor     eax, eax
0x1800708d6  movups  [rbp+57h+var_28], xmm0
0x1800708da  mov     [rbp+57h+hMem], rax
0x1800708de  movups  [rbp+57h+var_18], xmm0
0x1800708e2  call    ?GetCustomSecurityDescriptor@@YAJPEBGPEAX@Z; GetCustomSecurityDescriptor(ushort const *,void *)
0x1800708e7  mov     ebx, eax
0x1800708e9  test    eax, eax
0x1800708eb  js      loc_180070985
0x1800708f1  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800708f5  lea     rax, [rbp+57h+var_28]
0x1800708f9  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800708fd  lea     r9, Class; lpClass
0x180070904  lea     rax, [rbp+57h+dwDisposition]
0x180070908  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x180070910  mov     [rsp+90h+lpdwDisposition], rax; lpdwDisposition
0x180070915  xor     r8d, r8d; Reserved
0x180070918  lea     rax, [rbp+57h+hKey]
0x18007091c  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x180070924  mov     [rsp+90h+phkResult], rax; phkResult
0x180070929  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180070930  lea     rax, [rbp+57h+SecurityAttributes]
0x180070934  mov     [rbp+57h+dwDisposition], 0
0x18007093b  mov     [rsp+90h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180070940  mov     [rsp+90h+samDesired], 2011Fh; samDesired
0x180070948  mov     [rsp+90h+dwOptions], 0; dwOptions
0x180070950  mov     [rbp+57h+hKey], 0
0x180070958  call    cs:__imp_RegCreateKeyExW
0x18007095e  mov     ebx, eax
0x180070960  test    eax, eax
0x180070962  jle     short loc_18007096D
0x180070964  movzx   ebx, ax
0x180070967  or      ebx, 80070000h
0x18007096d  test    ebx, ebx
0x18007096f  js      short loc_18007097B
0x180070971  mov     rcx, [rbp+57h+hKey]; hKey
0x180070975  call    cs:__imp_RegCloseKey
0x18007097b  mov     rcx, [rbp+57h+hMem]; hMem
0x18007097f  call    cs:__imp_LocalFree
0x180070985  mov     rcx, [rbp+57h+lpSubKey]; pv
0x180070989  mov     [rbp+57h+lpSubKey], 0
0x180070991  call    cs:__imp_CoTaskMemFree
0x180070997  mov     eax, ebx
0x180070999  mov     rbx, [rsp+90h+arg_0]
0x1800709a1  add     rsp, 90h
0x1800709a8  pop     rbp
0x1800709a9  retn
```
