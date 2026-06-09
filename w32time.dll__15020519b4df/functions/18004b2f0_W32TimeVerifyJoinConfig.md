# W32TimeVerifyJoinConfig

- ea: `0x18004b2f0`
- end: `0x18004b49d`
- name: `W32TimeVerifyJoinConfig`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18004ade0`

## callees

- `0x18003d270`
- `0x1800498b8`
- `0x180049bf4`
- `0x18004a3cc`
- `0x18004ac98`
- `0x18004b2f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004b3da`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004b3fa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004b416`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004b3da`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004b3fa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004b416`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b362`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b362`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b470`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b470`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b3b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b3b0`

## string_xrefs

- `0x18004b347`: `System\CurrentControlSet\Services\W32Time\Parameters`

## pseudocode

```c
LSTATUS W32TimeVerifyJoinConfig()
{
  int v0; // ebx
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
  v0 = 3;
  pdwType = 0;
  hkey = 0;
  v7 = 0;
  v6 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\W32Time\\Parameters", 0, 3u, &hkey) )
    goto LABEL_9;
  pcbData = 520;
  if ( RegGetValueW(hkey, 0, L"Type", 0xFFFFu, &pdwType, pvData, &pcbData) || pdwType != 1 )
    goto LABEL_9;
  v10 = 0;
  if ( !(unsigned int)_o__wcsicmp(pvData, L"NoSync") )
  {
    v0 = 0;
    goto LABEL_10;
  }
  if ( !(unsigned int)_o__wcsicmp(pvData, L"NT5DS") )
  {
LABEL_9:
    v0 = 2;
  }
  else if ( (unsigned int)_o__wcsicmp(pvData, L"AllSync") )
  {
    v0 = ((unsigned int)HasNewPeerlist() != 0) + 2;
  }
LABEL_10:
  WriteSyncFromFlagsSpecial(v0);
  Role = GetRole((enum RoleType *)&v7, &v6);
  v2 = v6;
  if ( Role < 0 )
    v2 = 0;
  result = CreateRoleSpecificRegValues(2, 0, v2);
  if ( hkey )
    return RegCloseKey(hkey);
  return result;
}

```

## disassembly

```asm
0x18004b2f0  mov     [rsp-8+arg_0], rbx
0x18004b2f5  push    rbp
0x18004b2f6  lea     rbp, [rsp-180h]
0x18004b2fe  sub     rsp, 280h
0x18004b305  mov     rax, cs:__security_cookie
0x18004b30c  xor     rax, rsp
0x18004b30f  mov     [rbp+180h+var_10], rax
0x18004b316  lea     rax, [rsp+280h+hkey]
0x18004b31b  mov     [rsp+280h+var_240], 0
0x18004b323  mov     ebx, 3
0x18004b328  mov     [rsp+280h+pdwType], 0
0x18004b330  mov     r9d, ebx; samDesired
0x18004b333  mov     [rsp+280h+hkey], 0
0x18004b33c  xor     r8d, r8d; ulOptions
0x18004b33f  mov     [rsp+280h+var_234], 0
0x18004b347  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\W3"...
0x18004b34e  mov     [rsp+280h+var_238], 0
0x18004b356  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004b35d  mov     [rsp+280h+phkResult], rax; phkResult
0x18004b362  call    cs:__imp_RegOpenKeyExW
0x18004b369  nop     dword ptr [rax+rax+00h]
0x18004b36e  test    eax, eax
0x18004b370  jnz     loc_18004B436
0x18004b376  mov     rcx, [rsp+280h+hkey]; hkey
0x18004b37b  lea     rax, [rsp+280h+var_240]
0x18004b380  mov     [rsp+280h+pcbData], rax; pcbData
0x18004b385  lea     r8, aType; "Type"
0x18004b38c  lea     rax, [rsp+280h+var_220]
0x18004b391  mov     [rsp+280h+var_240], 208h
0x18004b399  mov     [rsp+280h+pvData], rax; pvData
0x18004b39e  mov     r9d, 0FFFFh; dwFlags
0x18004b3a4  lea     rax, [rsp+280h+pdwType]
0x18004b3a9  xor     edx, edx; lpSubKey
0x18004b3ab  mov     [rsp+280h+phkResult], rax; pdwType
0x18004b3b0  call    cs:__imp_RegGetValueW
0x18004b3b7  nop     dword ptr [rax+rax+00h]
0x18004b3bc  test    eax, eax
0x18004b3be  jnz     short loc_18004B436
0x18004b3c0  cmp     [rsp+280h+pdwType], 1
0x18004b3c5  jnz     short loc_18004B436
0x18004b3c7  lea     rdx, aNosync; "NoSync"
0x18004b3ce  mov     [rbp+180h+var_1A], ax
0x18004b3d5  lea     rcx, [rsp+280h+var_220]
0x18004b3da  call    cs:__imp__o__wcsicmp
0x18004b3e1  nop     dword ptr [rax+rax+00h]
0x18004b3e6  test    eax, eax
0x18004b3e8  jnz     short loc_18004B3EE
0x18004b3ea  xor     ebx, ebx
0x18004b3ec  jmp     short loc_18004B43B
0x18004b3ee  lea     rdx, aNt5ds; "NT5DS"
0x18004b3f5  lea     rcx, [rsp+280h+var_220]
0x18004b3fa  call    cs:__imp__o__wcsicmp
0x18004b401  nop     dword ptr [rax+rax+00h]
0x18004b406  test    eax, eax
0x18004b408  jz      short loc_18004B436
0x18004b40a  lea     rdx, aAllsync; "AllSync"
0x18004b411  lea     rcx, [rsp+280h+var_220]
0x18004b416  call    cs:__imp__o__wcsicmp
0x18004b41d  nop     dword ptr [rax+rax+00h]
0x18004b422  test    eax, eax
0x18004b424  jz      short loc_18004B43B
0x18004b426  call    ?HasNewPeerlist@@YAHXZ; HasNewPeerlist(void)
0x18004b42b  neg     eax
0x18004b42d  sbb     ebx, ebx
0x18004b42f  neg     ebx
0x18004b431  add     ebx, 2
0x18004b434  jmp     short loc_18004B43B
0x18004b436  mov     ebx, 2
0x18004b43b  mov     ecx, ebx; unsigned int
0x18004b43d  call    ?WriteSyncFromFlagsSpecial@@YAJK@Z; WriteSyncFromFlagsSpecial(ulong)
0x18004b442  lea     rdx, [rsp+280h+var_238]; int *
0x18004b447  lea     rcx, [rsp+280h+var_234]; enum RoleType *
0x18004b44c  call    ?GetRole@@YAJPEAW4RoleType@@PEAH@Z; GetRole(RoleType *,int *)
0x18004b451  mov     r8d, [rsp+280h+var_238]
0x18004b456  xor     edx, edx
0x18004b458  test    eax, eax
0x18004b45a  cmovs   r8d, edx
0x18004b45e  lea     ecx, [rdx+2]
0x18004b461  call    ?CreateRoleSpecificRegValues@@YAJW4RoleType@@HH@Z; CreateRoleSpecificRegValues(RoleType,int,int)
0x18004b466  mov     rcx, [rsp+280h+hkey]; hKey
0x18004b46b  test    rcx, rcx
0x18004b46e  jz      short loc_18004B47C
0x18004b470  call    cs:__imp_RegCloseKey
0x18004b477  nop     dword ptr [rax+rax+00h]
0x18004b47c  mov     rcx, [rbp+180h+var_10]
0x18004b483  xor     rcx, rsp; StackCookie
0x18004b486  call    __security_check_cookie
0x18004b48b  mov     rbx, [rsp+280h+arg_0]
0x18004b493  add     rsp, 280h
0x18004b49a  pop     rbp
0x18004b49b  retn
```
