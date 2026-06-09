# RpcGetSecurityProviderInfo(ulong,ushort * *,ulong *)

- ea: `0x1800461fc`
- end: `0x180046403`
- name: `?RpcGetSecurityProviderInfo@@YAJKPEAPEAGPEAK@Z`
- size: `519`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180045d90`
- `0x1800b2000`

## callees

- `0x18002d420`
- `0x1800461fc`
- `0x1800b2b1c`
- `0x1800ca140`

## import_xrefs

- `ntdll!_itoa_s` at `0x18004626d`
- `ntdll!_itoa_s` at `0x18004626d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180046294`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180046294`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046382`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800463be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800463f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046382`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800463be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800463f6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180046375`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180046375`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180046302`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180046302`

## string_xrefs

- `0x180046286`: `Software\Microsoft\Rpc\SecurityService`

## pseudocode

```c
__int64 __fastcall RpcGetSecurityProviderInfo(int a1, unsigned __int16 **a2, unsigned int *a3)
{
  __int64 i; // rcx
  unsigned int ValueW; // ebx
  const unsigned __int16 *v7; // rcx
  unsigned __int16 *v8; // rax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cValues; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcbData; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cbMaxValueLen; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchClass; // [rsp+7Ch] [rbp-84h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+80h] [rbp-80h] BYREF
  char Buffer[16]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Value[12]; // [rsp+98h] [rbp-68h] BYREF
  CHAR Class[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 pvData[136]; // [rsp+F0h] [rbp-10h] BYREF

  cSubKeys = 0;
  cValues = 0;
  cbMaxValueLen = 0;
  pcbData = 129;
  cchClass = 64;
  ftLastWriteTime = 0;
  hKey = 0;
  _itoa_s(a1, Buffer, 0xCu, 10);
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Rpc\\SecurityService", 0, 0x20019u, &hKey) )
    return 1747;
  if ( RegQueryInfoKeyA(
         hKey,
         Class,
         &cchClass,
         0,
         &cSubKeys,
         &cSubKeys,
         &cSubKeys,
         &cValues,
         &cSubKeys,
         &cbMaxValueLen,
         &cSubKeys,
         &ftLastWriteTime)
    || cValues < 2 )
  {
    RegCloseKey(hKey);
    return 1747;
  }
  if ( cValues <= 0xFFFF )
  {
    *a3 = cValues - 2;
    for ( i = 0; i != 12; ++i )
      Value[i] = Buffer[i];
    Value[11] = 0;
    ValueW = RegGetValueW(hKey, 0, Value, 2u, 0, pvData, &pcbData);
    RegCloseKey(hKey);
    v7 = pvData;
    if ( ValueW )
    {
      ValueW = GetDefaultSecurityDll(pvData, pcbData);
      if ( ValueW )
        return 1747;
      v7 = DefaultSecurityDLL;
    }
    v8 = DuplicateString(v7);
    *a2 = v8;
    if ( !v8 )
      return 14;
    return ValueW;
  }
  RegCloseKey(hKey);
  return 14;
}

```

## disassembly

```asm
0x1800461fc  push    rbp
0x1800461fe  push    rbx
0x1800461ff  push    rdi
0x180046200  lea     rbp, [rsp-110h]
0x180046208  sub     rsp, 210h
0x18004620f  mov     rax, cs:__security_cookie
0x180046216  xor     rax, rsp
0x180046219  mov     [rbp+120h+var_20], rax
0x180046220  mov     r9d, 0Ah; Radix
0x180046226  mov     [rsp+220h+cSubKeys], 0
0x18004622e  mov     rbx, r8
0x180046231  mov     [rsp+220h+cValues], 0
0x180046239  mov     rdi, rdx
0x18004623c  mov     [rsp+220h+cbMaxValueLen], 0
0x180046244  lea     rdx, [rbp+120h+Buffer]; Buffer
0x180046248  mov     [rsp+220h+pcbData], 81h
0x180046250  lea     r8d, [r9+2]; BufferCount
0x180046254  mov     [rsp+220h+cchClass], 40h ; '@'
0x18004625c  mov     qword ptr [rbp+120h+ftLastWriteTime.dwLowDateTime], 0
0x180046264  mov     [rsp+220h+hKey], 0
0x18004626d  call    cs:__imp__itoa_s
0x180046273  lea     rax, [rsp+220h+hKey]
0x180046278  mov     r9d, 20019h; samDesired
0x18004627e  xor     r8d, r8d; ulOptions
0x180046281  mov     [rsp+220h+phkResult], rax; phkResult
0x180046286  lea     rdx, SubKey; "Software\\Microsoft\\Rpc\\SecurityServi"...
0x18004628d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180046294  call    cs:__imp_RegOpenKeyExA
0x18004629a  test    eax, eax
0x18004629c  jnz     loc_1800463FC
0x1800462a2  mov     rcx, [rsp+220h+hKey]; hKey
0x1800462a7  lea     rax, [rbp+120h+ftLastWriteTime]
0x1800462ab  mov     [rsp+220h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800462b0  lea     r8, [rsp+220h+cchClass]; lpcchClass
0x1800462b5  lea     rax, [rsp+220h+cSubKeys]
0x1800462ba  xor     r9d, r9d; lpReserved
0x1800462bd  mov     [rsp+220h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x1800462c2  lea     rdx, [rbp+120h+Class]; lpClass
0x1800462c6  lea     rax, [rsp+220h+cbMaxValueLen]
0x1800462cb  mov     [rsp+220h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800462d0  lea     rax, [rsp+220h+cSubKeys]
0x1800462d5  mov     [rsp+220h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800462da  lea     rax, [rsp+220h+cValues]
0x1800462df  mov     [rsp+220h+lpcValues], rax; lpcValues
0x1800462e4  lea     rax, [rsp+220h+cSubKeys]
0x1800462e9  mov     [rsp+220h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x1800462ee  lea     rax, [rsp+220h+cSubKeys]
0x1800462f3  mov     [rsp+220h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800462f8  lea     rax, [rsp+220h+cSubKeys]
0x1800462fd  mov     [rsp+220h+phkResult], rax; lpcSubKeys
0x180046302  call    cs:__imp_RegQueryInfoKeyA
0x180046308  test    eax, eax
0x18004630a  jnz     loc_1800463F1
0x180046310  mov     eax, [rsp+220h+cValues]
0x180046314  mov     r9d, 2; dwFlags
0x18004631a  cmp     eax, r9d
0x18004631d  jb      loc_1800463F1
0x180046323  cmp     eax, 0FFFFh
0x180046328  ja      loc_1800463B9
0x18004632e  add     eax, 0FFFFFFFEh
0x180046331  mov     [rbx], eax
0x180046333  xor     ecx, ecx
0x180046335  movsx   eax, [rbp+rcx+120h+Buffer]
0x18004633a  mov     [rbp+rcx*2+120h+Value], ax
0x18004633f  inc     rcx
0x180046342  cmp     rcx, 0Ch
0x180046346  jnz     short loc_180046335
0x180046348  mov     rcx, [rsp+220h+hKey]; hkey
0x18004634d  lea     r8, [rbp+120h+Value]; lpValue
0x180046351  xor     eax, eax
0x180046353  xor     edx, edx; lpSubKey
0x180046355  mov     [rbp+120h+var_172], ax
0x180046359  lea     rax, [rsp+220h+pcbData]
0x18004635e  mov     [rsp+220h+lpcbMaxClassLen], rax; pcbData
0x180046363  lea     rax, [rbp+120h+pvData]
0x180046367  mov     [rsp+220h+lpcbMaxSubKeyLen], rax; pvData
0x18004636c  mov     [rsp+220h+phkResult], 0; pdwType
0x180046375  call    cs:__imp_RegGetValueW
0x18004637b  mov     rcx, [rsp+220h+hKey]; hKey
0x180046380  mov     ebx, eax
0x180046382  call    cs:__imp_RegCloseKey
0x180046388  lea     rcx, [rbp+120h+pvData]; Src
0x18004638c  test    ebx, ebx
0x18004638e  jnz     short loc_1800463CB
0x180046390  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x180046395  mov     [rdi], rax
0x180046398  test    rax, rax
0x18004639b  jz      short loc_1800463EA
0x18004639d  mov     eax, ebx
0x18004639f  mov     rcx, [rbp+120h+var_20]
0x1800463a6  xor     rcx, rsp; StackCookie
0x1800463a9  call    __security_check_cookie
0x1800463ae  add     rsp, 210h
0x1800463b5  pop     rdi
0x1800463b6  pop     rbx
0x1800463b7  pop     rbp
0x1800463b8  retn
0x1800463b9  mov     rcx, [rsp+220h+hKey]; hKey
0x1800463be  call    cs:__imp_RegCloseKey
0x1800463c4  mov     eax, 0Eh
0x1800463c9  jmp     short loc_18004639F
0x1800463cb  mov     edx, [rsp+220h+pcbData]; unsigned int
0x1800463cf  call    ?GetDefaultSecurityDll@@YAJPEAGK@Z; GetDefaultSecurityDll(ushort *,ulong)
0x1800463d4  mov     ebx, eax
0x1800463d6  test    eax, eax
0x1800463d8  jnz     short loc_1800463E3
0x1800463da  mov     rcx, cs:?DefaultSecurityDLL@@3PEAGEA; ushort * DefaultSecurityDLL
0x1800463e1  jmp     short loc_180046390
0x1800463e3  mov     ebx, 6D3h
0x1800463e8  jmp     short loc_18004639D
0x1800463ea  mov     ebx, 0Eh
0x1800463ef  jmp     short loc_18004639D
0x1800463f1  mov     rcx, [rsp+220h+hKey]; hKey
0x1800463f6  call    cs:__imp_RegCloseKey
0x1800463fc  mov     eax, 6D3h
0x180046401  jmp     short loc_18004639F
```
