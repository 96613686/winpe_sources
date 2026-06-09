# PolicyTransforms::ProcessDisableWUfBSafeguards(tagEnterprisePolicyValue_V1 *)

- ea: `0x180017460`
- end: `0x1800175c5`
- name: `?ProcessDisableWUfBSafeguards@PolicyTransforms@@SAJPEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `357`
- prototype: `__int64 __fastcall(struct tagEnterprisePolicyValue_V1 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180017460`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800174f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800174f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001759c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001759c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017525`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017525`
- `OLEAUT32!__imp_VariantClear` at `0x180017569`
- `OLEAUT32!__imp_VariantClear` at `0x180017569`

## string_xrefs

- `0x18001751e`: `DataRequireGatedScanForFeatureUpdates`

## pseudocode

```c
__int64 __fastcall PolicyTransforms::ProcessDisableWUfBSafeguards(struct tagEnterprisePolicyValue_V1 *a1)
{
  unsigned int v1; // ebx
  unsigned int v3; // eax
  LSTATUS v4; // eax
  int v5; // eax
  DWORD cbData; // [rsp+30h] [rbp-20h] BYREF
  DWORD Type; // [rsp+34h] [rbp-1Ch] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF

  v1 = 0;
  hKey = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  Type = 0;
  if ( !a1 )
  {
    v1 = -2147467261;
    goto LABEL_19;
  }
  v3 = *((_DWORD *)a1 + 6);
  if ( v3 >= 2 )
  {
    v1 = -2147024809;
    goto LABEL_19;
  }
  if ( *((_DWORD *)a1 + 2) == 1 || *((_DWORD *)a1 + 2) == 2 )
  {
    *((_DWORD *)a1 + 6) = v3 == 0;
  }
  else
  {
    v4 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\502505fe-762c-4e80-911e-0c3fa4c63fb0",
           0,
           1u,
           &hKey);
    if ( v4
      || (cbData = 4,
          (v4 = RegQueryValueExW(hKey, L"DataRequireGatedScanForFeatureUpdates", 0, &Type, Data, &cbData)) != 0) )
    {
      v1 = (unsigned __int16)v4 | 0x80070000;
      if ( v4 <= 0 )
        v1 = v4;
      goto LABEL_16;
    }
    if ( Type != 4 )
    {
      v1 = -2147024883;
LABEL_16:
      *(_QWORD *)((char *)a1 + 4) = 0;
      VariantClear((VARIANTARG *)((char *)a1 + 16));
      goto LABEL_19;
    }
    v5 = *(_DWORD *)Data;
    if ( *(_DWORD *)Data >= 2u )
    {
      v1 = -2147024809;
      goto LABEL_16;
    }
    *((_DWORD *)a1 + 1) = 1;
    *((_DWORD *)a1 + 2) = 3;
    *((_WORD *)a1 + 8) = 3;
    *((_DWORD *)a1 + 6) = v5;
  }
LABEL_19:
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x180017460  mov     [rsp-8+arg_8], rbx
0x180017465  mov     [rsp-8+arg_10], rsi
0x18001746a  mov     [rsp-8+arg_18], rdi
0x18001746f  push    rbp
0x180017470  mov     rbp, rsp
0x180017473  sub     rsp, 50h
0x180017477  mov     rax, cs:__security_cookie
0x18001747e  xor     rax, rsp
0x180017481  mov     [rbp+var_8], rax
0x180017485  xor     ebx, ebx
0x180017487  mov     rdi, rcx
0x18001748a  mov     [rbp+hKey], rbx
0x18001748e  mov     dword ptr [rbp+Data], ebx
0x180017491  mov     [rbp+cbData], ebx
0x180017494  mov     [rbp+Type], ebx
0x180017497  test    rcx, rcx
0x18001749a  jnz     short loc_1800174A6
0x18001749c  mov     ebx, 80004003h
0x1800174a1  jmp     loc_180017593
0x1800174a6  mov     eax, [rcx+18h]
0x1800174a9  test    eax, eax
0x1800174ab  jz      short loc_1800174BC
0x1800174ad  cmp     eax, 1
0x1800174b0  jz      short loc_1800174BC
0x1800174b2  mov     ebx, 80070057h
0x1800174b7  jmp     loc_180017593
0x1800174bc  cmp     dword ptr [rcx+8], 1
0x1800174c0  jz      loc_180017589
0x1800174c6  cmp     dword ptr [rcx+8], 2
0x1800174ca  jz      loc_180017589
0x1800174d0  lea     rax, [rbp+hKey]
0x1800174d4  mov     r9d, 1; samDesired
0x1800174da  xor     r8d, r8d; ulOptions
0x1800174dd  mov     [rsp+50h+phkResult], rax; phkResult
0x1800174e2  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800174e9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800174f0  call    cs:__imp_RegOpenKeyExW
0x1800174f6  test    eax, eax
0x1800174f8  jnz     short loc_18001752F
0x1800174fa  mov     rcx, [rbp+hKey]; hKey
0x1800174fe  lea     rax, [rbp+cbData]
0x180017502  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180017507  lea     r9, [rbp+Type]; lpType
0x18001750b  lea     rax, [rbp+Data]
0x18001750f  mov     [rbp+cbData], 4
0x180017516  xor     r8d, r8d; lpReserved
0x180017519  mov     [rsp+50h+phkResult], rax; lpData
0x18001751e  lea     rdx, ValueName; "DataRequireGatedScanForFeatureUpdates"
0x180017525  call    cs:__imp_RegQueryValueExW
0x18001752b  test    eax, eax
0x18001752d  jz      short loc_180017543
0x18001752f  movzx   ebx, ax
0x180017532  or      ebx, 80070000h
0x180017538  test    eax, eax
0x18001753a  cmovle  ebx, eax
0x18001753d  test    ebx, ebx
0x18001753f  js      short loc_18001755D
0x180017541  jmp     short loc_180017593
0x180017543  cmp     [rbp+Type], 4
0x180017547  jz      short loc_180017550
0x180017549  mov     ebx, 8007000Dh
0x18001754e  jmp     short loc_18001755D
0x180017550  mov     eax, dword ptr [rbp+Data]
0x180017553  cmp     eax, 2
0x180017556  jb      short loc_180017571
0x180017558  mov     ebx, 80070057h
0x18001755d  lea     rcx, [rdi+10h]; pvarg
0x180017561  mov     qword ptr [rdi+4], 0
0x180017569  call    cs:__imp_VariantClear
0x18001756f  jmp     short loc_180017593
0x180017571  mov     ecx, 3
0x180017576  mov     dword ptr [rdi+4], 1
0x18001757d  mov     [rdi+8], ecx
0x180017580  mov     [rdi+10h], cx
0x180017584  mov     [rdi+18h], eax
0x180017587  jmp     short loc_180017593
0x180017589  xor     ecx, ecx
0x18001758b  test    eax, eax
0x18001758d  setz    cl
0x180017590  mov     [rdi+18h], ecx
0x180017593  mov     rcx, [rbp+hKey]; hKey
0x180017597  test    rcx, rcx
0x18001759a  jz      short loc_1800175A2
0x18001759c  call    cs:__imp_RegCloseKey
0x1800175a2  mov     eax, ebx
0x1800175a4  mov     rcx, [rbp+var_8]
0x1800175a8  xor     rcx, rsp; StackCookie
0x1800175ab  call    __security_check_cookie
0x1800175b0  mov     rbx, [rsp+50h+arg_8]
0x1800175b5  mov     rsi, [rsp+50h+arg_10]
0x1800175ba  mov     rdi, [rsp+50h+arg_18]
0x1800175bf  add     rsp, 50h
0x1800175c3  pop     rbp
0x1800175c4  retn
```
