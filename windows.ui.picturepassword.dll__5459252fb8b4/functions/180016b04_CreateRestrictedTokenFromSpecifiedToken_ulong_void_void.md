# _CreateRestrictedTokenFromSpecifiedToken(ulong,void *,void * *)

- ea: `0x180016b04`
- end: `0x180016c55`
- name: `?_CreateRestrictedTokenFromSpecifiedToken@@YAJKPEAXPEAPEAX@Z`
- size: `337`
- prototype: `__int64 __fastcall(void *nSubAuthority0, HANDLE ExistingTokenHandle, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180016a8c`

## callees

- `0x1800063c0`
- `0x1800092b8`
- `0x1800169ac`
- `0x180016b04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016c34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016c34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016c29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016c29`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180016b84`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180016b84`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x180016bea`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x180016bea`

## pseudocode

```c
__int64 __fastcall _CreateRestrictedTokenFromSpecifiedToken(
        void *nSubAuthority0,
        HANDLE ExistingTokenHandle,
        void **a3)
{
  DWORD v5; // ebp
  int v6; // edi
  int Error; // ebx
  struct _SID_AND_ATTRIBUTES SidsToDisable; // [rsp+50h] [rbp-38h] BYREF
  void *cbSid; // [rsp+A0h] [rbp+18h] BYREF

  *a3 = 0;
  SidsToDisable = 0;
  v5 = (unsigned int)nSubAuthority0;
  v6 = 0;
  while ( !v6 )
  {
    LODWORD(cbSid) = 68;
    Error = CTCoAllocPolicy::Alloc(nSubAuthority0, 1u, 0x44u, &SidsToDisable.Sid);
    if ( Error < 0 )
    {
LABEL_7:
      v6 = 1;
      if ( Error < 0 )
        goto LABEL_14;
    }
    else
    {
      if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, *(&SidsToDisable.Sid + 2 * v6), (DWORD *)&cbSid) )
      {
        Error = ResultFromKnownLastError();
        goto LABEL_7;
      }
      v6 = 1;
    }
  }
  cbSid = 0;
  if ( CreateRestrictedToken(ExistingTokenHandle, 1u, 1u, &SidsToDisable, 0, 0, 0, 0, &cbSid)
    || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    Error = AdjustTokenIntegrity(v5, cbSid);
    if ( Error < 0 )
      CloseHandle(cbSid);
    else
      *a3 = cbSid;
  }
LABEL_14:
  CoTaskMemFree(SidsToDisable.Sid);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180016b04  mov     [rsp+arg_0], rbx
0x180016b09  mov     [rsp+arg_8], rbp
0x180016b0e  push    rsi
0x180016b0f  push    rdi
0x180016b10  push    r12
0x180016b12  push    r14
0x180016b14  push    r15
0x180016b16  sub     rsp, 60h
0x180016b1a  xorps   xmm0, xmm0
0x180016b1d  mov     qword ptr [r8], 0
0x180016b24  movups  xmmword ptr [rsp+88h+SidsToDisable.Sid], xmm0
0x180016b29  mov     r14, r8
0x180016b2c  mov     r12, rdx
0x180016b2f  mov     ebp, ecx
0x180016b31  xor     edi, edi
0x180016b33  movsxd  rsi, edi
0x180016b36  mov     edx, 1; unsigned int
0x180016b3b  cmp     rsi, 1
0x180016b3f  jnb     short loc_180016BA4
0x180016b41  mov     rax, rsi
0x180016b44  mov     dword ptr [rsp+88h+cbSid], 44h ; 'D'
0x180016b4f  shl     rax, 4
0x180016b53  lea     r15, [rsp+88h+SidsToDisable]
0x180016b58  add     r15, rax
0x180016b5b  lea     r8d, [rdx+43h]; unsigned __int64
0x180016b5f  mov     r9, r15; void **
0x180016b62  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180016b67  mov     ebx, eax
0x180016b69  test    eax, eax
0x180016b6b  js      short loc_180016B99
0x180016b6d  mov     r8, [r15]; pSid
0x180016b70  lea     rcx, qword_1800237F0
0x180016b77  mov     ecx, [rcx+rsi*4]; WellKnownSidType
0x180016b7a  lea     r9, [rsp+88h+cbSid]; cbSid
0x180016b82  xor     edx, edx; DomainSid
0x180016b84  call    cs:__imp_CreateWellKnownSid
0x180016b8a  test    eax, eax
0x180016b8c  jz      short loc_180016B92
0x180016b8e  inc     edi
0x180016b90  jmp     short loc_180016B33
0x180016b92  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180016b97  mov     ebx, eax
0x180016b99  inc     edi
0x180016b9b  test    ebx, ebx
0x180016b9d  jns     short loc_180016B33
0x180016b9f  jmp     loc_180016C2F
0x180016ba4  lea     rax, [rsp+88h+cbSid]
0x180016bac  mov     [rsp+88h+cbSid], 0
0x180016bb8  mov     [rsp+88h+NewTokenHandle], rax; NewTokenHandle
0x180016bbd  lea     r9, [rsp+88h+SidsToDisable]; SidsToDisable
0x180016bc2  mov     [rsp+88h+SidsToRestrict], 0; SidsToRestrict
0x180016bcb  mov     r8d, edx; DisableSidCount
0x180016bce  mov     [rsp+88h+RestrictedSidCount], 0; RestrictedSidCount
0x180016bd6  mov     rcx, r12; ExistingTokenHandle
0x180016bd9  mov     [rsp+88h+PrivilegesToDelete], 0; PrivilegesToDelete
0x180016be2  mov     [rsp+88h+DeletePrivilegeCount], 0; DeletePrivilegeCount
0x180016bea  call    cs:__imp_CreateRestrictedToken
0x180016bf0  test    eax, eax
0x180016bf2  jnz     short loc_180016BFF
0x180016bf4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180016bf9  mov     ebx, eax
0x180016bfb  test    eax, eax
0x180016bfd  js      short loc_180016C2F
0x180016bff  mov     rdx, [rsp+88h+cbSid]; TokenHandle
0x180016c07  mov     ecx, ebp; nSubAuthority0
0x180016c09  call    ?AdjustTokenIntegrity@@YAJKPEAX@Z; AdjustTokenIntegrity(ulong,void *)
0x180016c0e  mov     ebx, eax
0x180016c10  test    eax, eax
0x180016c12  js      short loc_180016C21
0x180016c14  mov     rax, [rsp+88h+cbSid]
0x180016c1c  mov     [r14], rax
0x180016c1f  jmp     short loc_180016C2F
0x180016c21  mov     rcx, [rsp+88h+cbSid]; hObject
0x180016c29  call    cs:__imp_CloseHandle
0x180016c2f  mov     rcx, [rsp+88h+SidsToDisable.Sid]; pv
0x180016c34  call    cs:__imp_CoTaskMemFree
0x180016c3a  lea     r11, [rsp+88h+var_28]
0x180016c3f  mov     eax, ebx
0x180016c41  mov     rbx, [r11+30h]
0x180016c45  mov     rbp, [r11+38h]
0x180016c49  mov     rsp, r11
0x180016c4c  pop     r15
0x180016c4e  pop     r14
0x180016c50  pop     r12
0x180016c52  pop     rdi
0x180016c53  pop     rsi
0x180016c54  retn
```
