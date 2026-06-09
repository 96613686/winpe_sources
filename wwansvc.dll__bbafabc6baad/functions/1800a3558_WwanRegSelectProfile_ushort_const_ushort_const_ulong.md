# WwanRegSelectProfile(ushort const *,ushort const *,ulong *)

- ea: `0x1800a3558`
- end: `0x1800a36ee`
- name: `?WwanRegSelectProfile@@YAKPEBG0PEAK@Z`
- size: `406`
- prototype: `unsigned int __fastcall(LPCWSTR lpSubKey, LPCWSTR, LPBYTE lpData)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800a4af8`

## callees

- `0x180012300`
- `0x180016c50`
- `0x180074758`
- `0x180074cec`
- `0x1800a3558`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3609`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a367c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a36b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3609`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a367c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a36b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a35bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a35fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a35bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a35fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a3637`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a36ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a3637`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a36ab`

## string_xrefs

- `0x1800a35ce`: `RegOpenKeyEx failed, errCode (0x%8x)`

## pseudocode

```c
__int64 __fastcall WwanRegSelectProfile(LPCWSTR lpSubKey, LPCWSTR a2, LPBYTE lpData)
{
  unsigned int v6; // ebx
  unsigned int v7; // eax
  DWORD Type; // [rsp+30h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+38h] BYREF

  WwanLog::Enter("WwanRegSelectProfile");
  Type = 0;
  cbData = 0;
  hKey = 0;
  phkResult = 0;
  v6 = RegOpenKeyExW(qword_180152870, lpSubKey, 0, 0x20019u, &hKey);
  if ( v6 || (v6 = RegOpenKeyExW(hKey, a2, 0, 0x20019u, &phkResult), RegCloseKey(hKey), v6) )
  {
    WwanLog::Error("WwanRegSelectProfile", 0, L"RegOpenKeyEx failed, errCode (0x%8x)", v6);
  }
  else
  {
    v7 = RegQueryValueExW(phkResult, L"dwFlags", 0, &Type, 0, &cbData);
    v6 = v7;
    if ( v7 )
    {
      WwanLog::Error("WwanRegSelectProfile", 0, L"RegQueryValueEx failed, errCode (0x%8x)", v7);
    }
    else
    {
      if ( Type == 4 )
      {
        cbData = 4;
        RegQueryValueExW(phkResult, L"dwFlags", 0, &Type, lpData, &cbData);
        RegCloseKey(phkResult);
        WwanLog::Verbose("WwanRegSelectProfile", 0, L"errCode (0x%8x)", 0);
        v6 = 0;
        goto LABEL_10;
      }
      WwanLog::Error("WwanRegSelectProfile", 0, L"data type mismatch, errCode (0x%8x)", 0);
      v6 = 13;
    }
    RegCloseKey(phkResult);
  }
LABEL_10:
  WwanLog::Exit("WwanRegSelectProfile");
  return v6;
}

```

## disassembly

```asm
0x1800a3558  mov     [rsp-18h+arg_0], rbx
0x1800a355d  mov     [rsp-18h+arg_8], rsi
0x1800a3562  push    rbp
0x1800a3563  push    rdi
0x1800a3564  push    r14
0x1800a3566  mov     rbp, rsp
0x1800a3569  sub     rsp, 50h
0x1800a356d  mov     rbx, rcx
0x1800a3570  lea     r14, aWwanregselectp_0; "WwanRegSelectProfile"
0x1800a3577  mov     rcx, r14; char *
0x1800a357a  mov     rsi, r8
0x1800a357d  mov     rdi, rdx
0x1800a3580  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800a3585  mov     rcx, cs:qword_180152870; hKey
0x1800a358c  lea     rax, [rbp+hKey]
0x1800a3590  mov     r9d, 20019h; samDesired
0x1800a3596  mov     [rsp+50h+phkResult], rax; phkResult
0x1800a359b  xor     r8d, r8d; ulOptions
0x1800a359e  mov     [rbp+Type], 0
0x1800a35a5  mov     rdx, rbx; lpSubKey
0x1800a35a8  mov     [rbp+cbData], 0
0x1800a35af  mov     [rbp+hKey], 0
0x1800a35b7  mov     [rbp+var_18], 0
0x1800a35bf  call    cs:__imp_RegOpenKeyExW
0x1800a35c5  mov     ebx, eax
0x1800a35c7  test    eax, eax
0x1800a35c9  jz      short loc_1800A35E4
0x1800a35cb  mov     r9d, ebx
0x1800a35ce  lea     r8, aRegopenkeyexFa_1; "RegOpenKeyEx failed, errCode (0x%8x)"
0x1800a35d5  xor     edx, edx; struct _GUID *
0x1800a35d7  mov     rcx, r14; char *
0x1800a35da  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a35df  jmp     loc_1800A36D1
0x1800a35e4  mov     rcx, [rbp+hKey]; hKey
0x1800a35e8  lea     rax, [rbp+var_18]
0x1800a35ec  mov     r9d, 20019h; samDesired
0x1800a35f2  mov     [rsp+50h+phkResult], rax; phkResult
0x1800a35f7  xor     r8d, r8d; ulOptions
0x1800a35fa  mov     rdx, rdi; lpSubKey
0x1800a35fd  call    cs:__imp_RegOpenKeyExW
0x1800a3603  mov     rcx, [rbp+hKey]; hKey
0x1800a3607  mov     ebx, eax
0x1800a3609  call    cs:__imp_RegCloseKey
0x1800a360f  test    ebx, ebx
0x1800a3611  jnz     short loc_1800A35CB
0x1800a3613  mov     rcx, [rbp+var_18]; hKey
0x1800a3617  lea     rax, [rbp+cbData]
0x1800a361b  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800a3620  lea     r9, [rbp+Type]; lpType
0x1800a3624  xor     r8d, r8d; lpReserved
0x1800a3627  mov     [rsp+50h+phkResult], 0; lpData
0x1800a3630  lea     rdx, aDwflags; "dwFlags"
0x1800a3637  call    cs:__imp_RegQueryValueExW
0x1800a363d  mov     ebx, eax
0x1800a363f  test    eax, eax
0x1800a3641  jz      short loc_1800A3659
0x1800a3643  mov     r9d, eax
0x1800a3646  lea     r8, aRegqueryvaluee_1; "RegQueryValueEx failed, errCode (0x%8x)"
0x1800a364d  xor     edx, edx; struct _GUID *
0x1800a364f  mov     rcx, r14; char *
0x1800a3652  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a3657  jmp     short loc_1800A3678
0x1800a3659  cmp     [rbp+Type], 4
0x1800a365d  jz      short loc_1800A3684
0x1800a365f  xor     r9d, r9d
0x1800a3662  lea     r8, aDataTypeMismat_0; "data type mismatch, errCode (0x%8x)"
0x1800a3669  xor     edx, edx; struct _GUID *
0x1800a366b  mov     rcx, r14; char *
0x1800a366e  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a3673  mov     ebx, 0Dh
0x1800a3678  mov     rcx, [rbp+var_18]; hKey
0x1800a367c  call    cs:__imp_RegCloseKey
0x1800a3682  jmp     short loc_1800A36D1
0x1800a3684  mov     rcx, [rbp+var_18]; hKey
0x1800a3688  lea     rax, [rbp+cbData]
0x1800a368c  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800a3691  lea     r9, [rbp+Type]; lpType
0x1800a3695  xor     r8d, r8d; lpReserved
0x1800a3698  mov     [rsp+50h+phkResult], rsi; lpData
0x1800a369d  lea     rdx, aDwflags; "dwFlags"
0x1800a36a4  mov     [rbp+cbData], 4
0x1800a36ab  call    cs:__imp_RegQueryValueExW
0x1800a36b1  mov     rcx, [rbp+var_18]; hKey
0x1800a36b5  call    cs:__imp_RegCloseKey
0x1800a36bb  xor     r9d, r9d
0x1800a36be  lea     r8, aErrcode0x8x; "errCode (0x%8x)"
0x1800a36c5  xor     edx, edx; struct _GUID *
0x1800a36c7  mov     rcx, r14; char *
0x1800a36ca  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800a36cf  xor     ebx, ebx
0x1800a36d1  mov     rcx, r14; char *
0x1800a36d4  call    ?Exit@WwanLog@@SAXPEBD@Z; WwanLog::Exit(char const *)
0x1800a36d9  mov     rsi, [rsp+50h+arg_8]
0x1800a36de  mov     eax, ebx
0x1800a36e0  mov     rbx, [rsp+50h+arg_0]
0x1800a36e5  add     rsp, 50h
0x1800a36e9  pop     r14
0x1800a36eb  pop     rdi
0x1800a36ec  pop     rbp
0x1800a36ed  retn
```
