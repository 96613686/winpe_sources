# W32TimeVerifyUnjoinConfig

- ea: `0x18004b4b0`
- end: `0x18004b60c`
- name: `W32TimeVerifyUnjoinConfig`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18004ade0`

## callees

- `0x18003d270`
- `0x1800498b8`
- `0x180049bf4`
- `0x18004ac98`
- `0x18004b4b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004b598`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004b598`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b520`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b520`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b5df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b5df`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b56f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b56f`

## string_xrefs

- `0x18004b4f9`: `System\CurrentControlSet\Services\W32Time\Parameters`

## pseudocode

```c
LSTATUS W32TimeVerifyUnjoinConfig()
{
  BOOL v0; // ebx
  int Role; // eax
  int v2; // r8d
  LSTATUS result; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pdwType; // [rsp+44h] [rbp-BCh] BYREF
  int v6; // [rsp+48h] [rbp-B8h] BYREF
  int v7; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pvData[518]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v10; // [rsp+266h] [rbp+166h]

  pcbData = 0;
  pdwType = 0;
  hkey = 0;
  v7 = 0;
  v6 = 0;
  v0 = 1;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\W32Time\\Parameters", 0, 3u, &hkey) )
  {
    pcbData = 520;
    if ( !RegGetValueW(hkey, 0, L"Type", 0xFFFFu, &pdwType, pvData, &pcbData) && pdwType == 1 )
    {
      v10 = 0;
      v0 = _o__wcsicmp(pvData, L"NoSync") != 0;
    }
  }
  WriteSyncFromFlagsSpecial(v0);
  Role = GetRole((enum RoleType *)&v7, &v6);
  v2 = v6;
  if ( Role < 0 )
    v2 = 0;
  result = CreateRoleSpecificRegValues(3, 0, v2);
  if ( hkey )
    return RegCloseKey(hkey);
  return result;
}

```

## disassembly

```asm
0x18004b4b0  mov     [rsp-8+arg_0], rbx
0x18004b4b5  push    rbp
0x18004b4b6  lea     rbp, [rsp-180h]
0x18004b4be  sub     rsp, 280h
0x18004b4c5  mov     rax, cs:__security_cookie
0x18004b4cc  xor     rax, rsp
0x18004b4cf  mov     [rbp+180h+var_10], rax
0x18004b4d6  lea     rax, [rsp+280h+hkey]
0x18004b4db  mov     [rsp+280h+var_240], 0
0x18004b4e3  mov     r9d, 3; samDesired
0x18004b4e9  mov     [rsp+280h+phkResult], rax; phkResult
0x18004b4ee  xor     r8d, r8d; ulOptions
0x18004b4f1  mov     [rsp+280h+pdwType], 0
0x18004b4f9  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\W3"...
0x18004b500  mov     [rsp+280h+hkey], 0
0x18004b509  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004b510  mov     [rsp+280h+var_234], 0
0x18004b518  mov     [rsp+280h+var_238], 0
0x18004b520  call    cs:__imp_RegOpenKeyExW
0x18004b527  nop     dword ptr [rax+rax+00h]
0x18004b52c  mov     ebx, 1
0x18004b531  test    eax, eax
0x18004b533  jnz     short loc_18004B5AA
0x18004b535  mov     rcx, [rsp+280h+hkey]; hkey
0x18004b53a  lea     rax, [rsp+280h+var_240]
0x18004b53f  mov     [rsp+280h+pcbData], rax; pcbData
0x18004b544  lea     r8, aType; "Type"
0x18004b54b  lea     rax, [rsp+280h+var_220]
0x18004b550  mov     [rsp+280h+var_240], 208h
0x18004b558  mov     [rsp+280h+pvData], rax; pvData
0x18004b55d  mov     r9d, 0FFFFh; dwFlags
0x18004b563  lea     rax, [rsp+280h+pdwType]
0x18004b568  xor     edx, edx; lpSubKey
0x18004b56a  mov     [rsp+280h+phkResult], rax; pdwType
0x18004b56f  call    cs:__imp_RegGetValueW
0x18004b576  nop     dword ptr [rax+rax+00h]
0x18004b57b  test    eax, eax
0x18004b57d  jnz     short loc_18004B5AA
0x18004b57f  cmp     [rsp+280h+pdwType], ebx
0x18004b583  jnz     short loc_18004B5AA
0x18004b585  lea     rdx, aNosync; "NoSync"
0x18004b58c  mov     [rbp+180h+var_1A], ax
0x18004b593  lea     rcx, [rsp+280h+var_220]
0x18004b598  call    cs:__imp__o__wcsicmp
0x18004b59f  nop     dword ptr [rax+rax+00h]
0x18004b5a4  test    eax, eax
0x18004b5a6  jnz     short loc_18004B5AA
0x18004b5a8  xor     ebx, ebx
0x18004b5aa  mov     ecx, ebx; unsigned int
0x18004b5ac  call    ?WriteSyncFromFlagsSpecial@@YAJK@Z; WriteSyncFromFlagsSpecial(ulong)
0x18004b5b1  lea     rdx, [rsp+280h+var_238]; int *
0x18004b5b6  lea     rcx, [rsp+280h+var_234]; enum RoleType *
0x18004b5bb  call    ?GetRole@@YAJPEAW4RoleType@@PEAH@Z; GetRole(RoleType *,int *)
0x18004b5c0  mov     r8d, [rsp+280h+var_238]
0x18004b5c5  xor     edx, edx
0x18004b5c7  test    eax, eax
0x18004b5c9  cmovs   r8d, edx
0x18004b5cd  lea     ecx, [rdx+3]
0x18004b5d0  call    ?CreateRoleSpecificRegValues@@YAJW4RoleType@@HH@Z; CreateRoleSpecificRegValues(RoleType,int,int)
0x18004b5d5  mov     rcx, [rsp+280h+hkey]; hKey
0x18004b5da  test    rcx, rcx
0x18004b5dd  jz      short loc_18004B5EB
0x18004b5df  call    cs:__imp_RegCloseKey
0x18004b5e6  nop     dword ptr [rax+rax+00h]
0x18004b5eb  mov     rcx, [rbp+180h+var_10]
0x18004b5f2  xor     rcx, rsp; StackCookie
0x18004b5f5  call    __security_check_cookie
0x18004b5fa  mov     rbx, [rsp+280h+arg_0]
0x18004b602  add     rsp, 280h
0x18004b609  pop     rbp
0x18004b60a  retn
```
