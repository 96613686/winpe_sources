# CredIsProtectedW

- ea: `0x180015500`
- end: `0x1800155bc`
- name: `CredIsProtectedW`
- size: `188`
- prototype: `BOOL __stdcall(LPWSTR pszProtectedCredentials, CRED_PROTECTION_TYPE *pProtectionType)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180040b60`

## callees

- `0x180015500`
- `0x1800155d0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800155a1`
- `ntdll!RtlNtStatusToDosError` at `0x1800155a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800155a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800155a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001558f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001558f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18001556c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18001556c`

## pseudocode

```c
BOOL __stdcall CredIsProtectedW(LPWSTR pszProtectedCredentials, CRED_PROTECTION_TYPE *pProtectionType)
{
  BOOL v3; // eax
  HLOCAL v4; // rbx
  const void *v5; // rcx
  DWORD v7; // eax
  int v8; // [rsp+30h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp+18h] BYREF

  hMem = 0;
  v8 = 0;
  if ( pszProtectedCredentials && pProtectionType )
  {
    v3 = CredUnmarshalCredentialW(pszProtectedCredentials, (PCRED_MARSHAL_TYPE)&v8, &hMem);
    v4 = hMem;
    if ( !v3 || ((v8 - 3) & 0xFFFFFFFD) != 0 )
    {
      *pProtectionType = CredUnprotected;
    }
    else
    {
      if ( !hMem )
        return 1;
      v5 = (const void *)*((_QWORD *)hMem + 1);
      if ( v5 && *(_DWORD *)hMem > 8u )
        *pProtectionType = (RtlCompareMemory(v5, &qword_18007BA90, 8u) == 8) + 1;
    }
    if ( v4 )
      LocalFree(v4);
    return 1;
  }
  v7 = RtlNtStatusToDosError(-1073741811);
  SetLastError(v7);
  return 0;
}

```

## disassembly

```asm
0x180015500  mov     rax, rsp
0x180015503  mov     [rax+10h], rbx
0x180015507  push    rdi
0x180015508  sub     rsp, 20h
0x18001550c  mov     qword ptr [rax+18h], 0
0x180015514  mov     rdi, rdx
0x180015517  mov     dword ptr [rax+8], 0
0x18001551e  test    rcx, rcx
0x180015521  jz      short loc_18001559C
0x180015523  test    rdx, rdx
0x180015526  jz      short loc_18001559C
0x180015528  lea     r8, [rax+18h]; Credential
0x18001552c  lea     rdx, [rax+8]; CredType
0x180015530  call    CredUnmarshalCredentialW
0x180015535  mov     rbx, [rsp+28h+hMem]
0x18001553a  test    eax, eax
0x18001553c  jz      short loc_180015581
0x18001553e  mov     eax, [rsp+28h+arg_0]
0x180015542  add     eax, 0FFFFFFFDh
0x180015545  test    eax, 0FFFFFFFDh
0x18001554a  jnz     short loc_180015581
0x18001554c  test    rbx, rbx
0x18001554f  jz      short loc_180015595
0x180015551  mov     rcx, [rbx+8]; Source1
0x180015555  test    rcx, rcx
0x180015558  jz      short loc_180015587
0x18001555a  cmp     dword ptr [rbx], 8
0x18001555d  jbe     short loc_180015587
0x18001555f  mov     r8d, 8; Length
0x180015565  lea     rdx, qword_18007BA90; Source2
0x18001556c  call    cs:__imp_RtlCompareMemory
0x180015572  xor     ecx, ecx
0x180015574  cmp     rax, 8
0x180015578  setz    cl
0x18001557b  inc     ecx
0x18001557d  mov     [rdi], ecx
0x18001557f  jmp     short loc_180015587
0x180015581  mov     dword ptr [rdi], 0
0x180015587  test    rbx, rbx
0x18001558a  jz      short loc_180015595
0x18001558c  mov     rcx, rbx; hMem
0x18001558f  call    cs:__imp_LocalFree
0x180015595  mov     eax, 1
0x18001559a  jmp     short loc_1800155B1
0x18001559c  mov     ecx, 0C000000Dh; Status
0x1800155a1  call    cs:__imp_RtlNtStatusToDosError
0x1800155a7  mov     ecx, eax; dwErrCode
0x1800155a9  call    cs:__imp_SetLastError
0x1800155af  xor     eax, eax
0x1800155b1  mov     rbx, [rsp+28h+arg_8]
0x1800155b6  add     rsp, 20h
0x1800155ba  pop     rdi
0x1800155bb  retn
```
