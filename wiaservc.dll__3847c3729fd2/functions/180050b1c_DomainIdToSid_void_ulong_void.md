# DomainIdToSid(void *,ulong,void * *)

- ea: `0x180050b1c`
- end: `0x180050bc1`
- name: `?DomainIdToSid@@YAKPEAXKPEAPEAX@Z`
- size: `165`
- prototype: `unsigned int __fastcall(void *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005096c`

## callees

- `0x180050b1c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180050b91`
- `KERNEL32!LocalFree` at `0x180050b91`
- `KERNEL32!LocalAlloc` at `0x180050b5f`
- `KERNEL32!LocalAlloc` at `0x180050b5f`
- `KERNEL32!GetLastError` at `0x180050b42`
- `KERNEL32!GetLastError` at `0x180050b86`
- `KERNEL32!GetLastError` at `0x180050b42`
- `KERNEL32!GetLastError` at `0x180050b86`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180050b7c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180050b7c`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180050b50`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180050b50`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180050bab`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180050bab`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180050b37`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180050b9e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180050b37`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180050b9e`

## pseudocode

```c
DWORD __fastcall DomainIdToSid(void *a1, DWORD a2, void **a3)
{
  PSID v3; // rbx
  PUCHAR SidSubAuthorityCount; // rax
  DWORD v8; // esi
  DWORD SidLengthRequired; // ebp
  HLOCAL v10; // rax
  DWORD LastError; // ebx
  PUCHAR v12; // rax

  v3 = psidBuiltinDomain;
  SidSubAuthorityCount = GetSidSubAuthorityCount(psidBuiltinDomain);
  if ( !SidSubAuthorityCount )
    return GetLastError();
  v8 = *SidSubAuthorityCount;
  SidLengthRequired = GetSidLengthRequired(v8 + 1);
  v10 = LocalAlloc(0x40u, SidLengthRequired);
  *a3 = v10;
  if ( !v10 )
    return 8;
  if ( CopySid(SidLengthRequired, v10, v3) )
  {
    v12 = GetSidSubAuthorityCount(*a3);
    ++*v12;
    *GetSidSubAuthority(*a3, v8) = a2;
    return 0;
  }
  else
  {
    LastError = GetLastError();
    LocalFree(*a3);
    return LastError;
  }
}

```

## disassembly

```asm
0x180050b1c  push    rbx
0x180050b1e  push    rbp
0x180050b1f  push    rsi
0x180050b20  push    rdi
0x180050b21  push    r14
0x180050b23  sub     rsp, 20h
0x180050b27  mov     rbx, cs:?psidBuiltinDomain@@3PEAXEA; void * psidBuiltinDomain
0x180050b2e  mov     rdi, r8
0x180050b31  mov     rcx, rbx; pSid
0x180050b34  mov     r14d, edx
0x180050b37  call    cs:__imp_GetSidSubAuthorityCount
0x180050b3d  test    rax, rax
0x180050b40  jnz     short loc_180050B4A
0x180050b42  call    cs:__imp_GetLastError
0x180050b48  jmp     short loc_180050BB6
0x180050b4a  movzx   esi, byte ptr [rax]
0x180050b4d  lea     ecx, [rsi+1]; nSubAuthorityCount
0x180050b50  call    cs:__imp_GetSidLengthRequired
0x180050b56  mov     edx, eax; uBytes
0x180050b58  mov     ecx, 40h ; '@'; uFlags
0x180050b5d  mov     ebp, eax
0x180050b5f  call    cs:__imp_LocalAlloc
0x180050b65  mov     [rdi], rax
0x180050b68  test    rax, rax
0x180050b6b  jnz     short loc_180050B74
0x180050b6d  mov     eax, 8
0x180050b72  jmp     short loc_180050BB6
0x180050b74  mov     r8, rbx; pSourceSid
0x180050b77  mov     rdx, rax; pDestinationSid
0x180050b7a  mov     ecx, ebp; nDestinationSidLength
0x180050b7c  call    cs:__imp_CopySid
0x180050b82  test    eax, eax
0x180050b84  jnz     short loc_180050B9B
0x180050b86  call    cs:__imp_GetLastError
0x180050b8c  mov     rcx, [rdi]; hMem
0x180050b8f  mov     ebx, eax
0x180050b91  call    cs:__imp_LocalFree
0x180050b97  mov     eax, ebx
0x180050b99  jmp     short loc_180050BB6
0x180050b9b  mov     rcx, [rdi]; pSid
0x180050b9e  call    cs:__imp_GetSidSubAuthorityCount
0x180050ba4  mov     edx, esi; nSubAuthority
0x180050ba6  inc     byte ptr [rax]
0x180050ba8  mov     rcx, [rdi]; pSid
0x180050bab  call    cs:__imp_GetSidSubAuthority
0x180050bb1  mov     [rax], r14d
0x180050bb4  xor     eax, eax
0x180050bb6  add     rsp, 20h
0x180050bba  pop     r14
0x180050bbc  pop     rdi
0x180050bbd  pop     rsi
0x180050bbe  pop     rbp
0x180050bbf  pop     rbx
0x180050bc0  retn
```
