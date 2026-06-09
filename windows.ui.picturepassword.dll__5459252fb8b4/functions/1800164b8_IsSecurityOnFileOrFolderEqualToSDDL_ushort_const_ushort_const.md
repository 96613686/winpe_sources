# _IsSecurityOnFileOrFolderEqualToSDDL(ushort const *,ushort const *)

- ea: `0x1800164b8`
- end: `0x1800165c1`
- name: `?_IsSecurityOnFileOrFolderEqualToSDDL@@YA_NPEBG0@Z`
- size: `265`
- prototype: `bool __fastcall(LPCWSTR lpFileName, LPCWCH lpString2)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800165c8`

## callees

- `0x1800063c0`
- `0x1800092b8`
- `0x1800164b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800165aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800165aa`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180016570`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180016570`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800165a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800165a0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001658f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001658f`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800164eb`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180016544`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800164eb`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180016544`

## pseudocode

```c
bool __fastcall _IsSecurityOnFileOrFolderEqualToSDDL(LPCWSTR lpFileName, LPCWCH lpString2)
{
  bool v4; // di
  void *v5; // rcx
  LPWSTR StringSecurityDescriptor; // [rsp+30h] [rbp-10h] BYREF
  DWORD nLengthNeeded; // [rsp+70h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+78h] [rbp+38h] BYREF

  nLengthNeeded = 0;
  v4 = 0;
  if ( !GetFileSecurityW(lpFileName, 7u, 0, 0, &nLengthNeeded)
    && (unsigned int)ResultFromKnownLastError() == -2147024774 )
  {
    pSecurityDescriptor = 0;
    if ( CTCoAllocPolicy::Alloc(v5, 1u, nLengthNeeded, &pSecurityDescriptor) >= 0 )
    {
      if ( GetFileSecurityW(lpFileName, 7u, pSecurityDescriptor, nLengthNeeded, &nLengthNeeded) )
      {
        StringSecurityDescriptor = 0;
        if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
               pSecurityDescriptor,
               1u,
               7u,
               &StringSecurityDescriptor,
               0) )
        {
          v4 = CompareStringOrdinal(StringSecurityDescriptor, -1, lpString2, -1, 1) == 2;
          LocalFree(StringSecurityDescriptor);
        }
      }
      CoTaskMemFree(pSecurityDescriptor);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800164b8  mov     [rsp-18h+arg_0], rsi
0x1800164bd  push    rbp
0x1800164be  push    rdi
0x1800164bf  push    r14
0x1800164c1  mov     rbp, rsp
0x1800164c4  sub     rsp, 40h
0x1800164c8  xor     r9d, r9d; nLength
0x1800164cb  mov     [rbp+nLengthNeeded], 0
0x1800164d2  mov     r14, rdx
0x1800164d5  lea     rax, [rbp+nLengthNeeded]
0x1800164d9  xor     r8d, r8d; pSecurityDescriptor
0x1800164dc  mov     [rsp+40h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800164e1  mov     rsi, rcx
0x1800164e4  xor     dil, dil
0x1800164e7  lea     edx, [r9+7]; RequestedInformation
0x1800164eb  call    cs:__imp_GetFileSecurityW
0x1800164f1  test    eax, eax
0x1800164f3  jnz     loc_1800165B0
0x1800164f9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800164fe  cmp     eax, 8007007Ah
0x180016503  jnz     loc_1800165B0
0x180016509  mov     r8d, [rbp+nLengthNeeded]; unsigned __int64
0x18001650d  lea     r9, [rbp+pSecurityDescriptor]; void **
0x180016511  mov     edx, 1; unsigned int
0x180016516  mov     [rbp+pSecurityDescriptor], 0
0x18001651e  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180016523  test    eax, eax
0x180016525  js      loc_1800165B0
0x18001652b  mov     r9d, [rbp+nLengthNeeded]; nLength
0x18001652f  lea     rax, [rbp+nLengthNeeded]
0x180016533  mov     r8, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180016537  mov     edx, 7; RequestedInformation
0x18001653c  mov     rcx, rsi; lpFileName
0x18001653f  mov     [rsp+40h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180016544  call    cs:__imp_GetFileSecurityW
0x18001654a  test    eax, eax
0x18001654c  jz      short loc_1800165A6
0x18001654e  mov     rcx, [rbp+pSecurityDescriptor]; SecurityDescriptor
0x180016552  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x180016556  mov     edx, 1; RequestedStringSDRevision
0x18001655b  mov     [rbp+StringSecurityDescriptor], 0
0x180016563  mov     [rsp+40h+lpnLengthNeeded], 0; StringSecurityDescriptorLen
0x18001656c  lea     r8d, [rdx+6]; SecurityInformation
0x180016570  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180016576  test    eax, eax
0x180016578  jz      short loc_1800165A6
0x18001657a  mov     rcx, [rbp+StringSecurityDescriptor]; lpString1
0x18001657e  or      edx, 0FFFFFFFFh; cchCount1
0x180016581  mov     r9d, edx; cchCount2
0x180016584  mov     dword ptr [rsp+40h+lpnLengthNeeded], 1; bIgnoreCase
0x18001658c  mov     r8, r14; lpString2
0x18001658f  call    cs:__imp_CompareStringOrdinal
0x180016595  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x180016599  cmp     eax, 2
0x18001659c  setz    dil
0x1800165a0  call    cs:__imp_LocalFree
0x1800165a6  mov     rcx, [rbp+pSecurityDescriptor]; pv
0x1800165aa  call    cs:__imp_CoTaskMemFree
0x1800165b0  mov     rsi, [rsp+40h+arg_0]
0x1800165b5  mov     al, dil
0x1800165b8  add     rsp, 40h
0x1800165bc  pop     r14
0x1800165be  pop     rdi
0x1800165bf  pop     rbp
0x1800165c0  retn
```
