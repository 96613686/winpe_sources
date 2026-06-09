# _CreateRestrictedTokenFromSpecifiedToken(ulong,void *,void * *)

- ea: `0x1800d8f90`
- end: `0x1800d90fa`
- name: `?_CreateRestrictedTokenFromSpecifiedToken@@YAJKPEAXPEAPEAX@Z`
- size: `362`
- prototype: `__int64 __fastcall(DWORD nSubAuthority0, HANDLE ExistingTokenHandle, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003cf38`
- `0x18003d124`

## callees

- `0x180006800`
- `0x18003d244`
- `0x1800d8c14`
- `0x1800d8f90`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d90c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d90c1`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1800d907c`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1800d907c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d9010`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d9010`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d90d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d90d2`

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
0x1800d8f90  mov     [rsp+arg_0], rbx
0x1800d8f95  mov     [rsp+arg_8], rbp
0x1800d8f9a  push    rsi
0x1800d8f9b  push    rdi
0x1800d8f9c  push    r12
0x1800d8f9e  push    r14
0x1800d8fa0  push    r15
0x1800d8fa2  sub     rsp, 60h
0x1800d8fa6  xorps   xmm0, xmm0
0x1800d8fa9  mov     qword ptr [r8], 0
0x1800d8fb0  movups  xmmword ptr [rsp+88h+SidsToDisable.Sid], xmm0
0x1800d8fb5  mov     r14, r8
0x1800d8fb8  mov     r12, rdx
0x1800d8fbb  mov     ebp, ecx
0x1800d8fbd  xor     edi, edi
0x1800d8fbf  movsxd  rsi, edi
0x1800d8fc2  mov     edx, 1; unsigned int
0x1800d8fc7  cmp     rsi, 1
0x1800d8fcb  jnb     short loc_1800D9036
0x1800d8fcd  mov     rax, rsi
0x1800d8fd0  mov     dword ptr [rsp+88h+cbSid], 44h ; 'D'
0x1800d8fdb  shl     rax, 4
0x1800d8fdf  lea     r15, [rsp+88h+SidsToDisable]
0x1800d8fe4  add     r15, rax
0x1800d8fe7  lea     r8d, [rdx+43h]; unsigned __int64
0x1800d8feb  mov     r9, r15; void **
0x1800d8fee  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800d8ff3  mov     ebx, eax
0x1800d8ff5  test    eax, eax
0x1800d8ff7  js      short loc_1800D902B
0x1800d8ff9  mov     r8, [r15]; pSid
0x1800d8ffc  lea     rcx, dword_18010F464
0x1800d9003  mov     ecx, [rcx+rsi*4]; WellKnownSidType
0x1800d9006  lea     r9, [rsp+88h+cbSid]; cbSid
0x1800d900e  xor     edx, edx; DomainSid
0x1800d9010  call    cs:__imp_CreateWellKnownSid
0x1800d9017  nop     dword ptr [rax+rax+00h]
0x1800d901c  test    eax, eax
0x1800d901e  jz      short loc_1800D9024
0x1800d9020  inc     edi
0x1800d9022  jmp     short loc_1800D8FBF
0x1800d9024  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d9029  mov     ebx, eax
0x1800d902b  inc     edi
0x1800d902d  test    ebx, ebx
0x1800d902f  jns     short loc_1800D8FBF
0x1800d9031  jmp     loc_1800D90CD
0x1800d9036  lea     rax, [rsp+88h+cbSid]
0x1800d903e  mov     [rsp+88h+cbSid], 0
0x1800d904a  mov     [rsp+88h+NewTokenHandle], rax; NewTokenHandle
0x1800d904f  lea     r9, [rsp+88h+SidsToDisable]; SidsToDisable
0x1800d9054  mov     [rsp+88h+SidsToRestrict], 0; SidsToRestrict
0x1800d905d  mov     r8d, edx; DisableSidCount
0x1800d9060  mov     [rsp+88h+RestrictedSidCount], 0; RestrictedSidCount
0x1800d9068  mov     rcx, r12; ExistingTokenHandle
0x1800d906b  mov     [rsp+88h+PrivilegesToDelete], 0; PrivilegesToDelete
0x1800d9074  mov     [rsp+88h+DeletePrivilegeCount], 0; DeletePrivilegeCount
0x1800d907c  call    cs:__imp_CreateRestrictedToken
0x1800d9083  nop     dword ptr [rax+rax+00h]
0x1800d9088  test    eax, eax
0x1800d908a  jnz     short loc_1800D9097
0x1800d908c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d9091  mov     ebx, eax
0x1800d9093  test    eax, eax
0x1800d9095  js      short loc_1800D90CD
0x1800d9097  mov     rdx, [rsp+88h+cbSid]; TokenHandle
0x1800d909f  mov     ecx, ebp; nSubAuthority0
0x1800d90a1  call    ?AdjustTokenIntegrity@@YAJKPEAX@Z; AdjustTokenIntegrity(ulong,void *)
0x1800d90a6  mov     ebx, eax
0x1800d90a8  test    eax, eax
0x1800d90aa  js      short loc_1800D90B9
0x1800d90ac  mov     rax, [rsp+88h+cbSid]
0x1800d90b4  mov     [r14], rax
0x1800d90b7  jmp     short loc_1800D90CD
0x1800d90b9  mov     rcx, [rsp+88h+cbSid]; hObject
0x1800d90c1  call    cs:__imp_CloseHandle
0x1800d90c8  nop     dword ptr [rax+rax+00h]
0x1800d90cd  mov     rcx, [rsp+88h+SidsToDisable.Sid]; pv
0x1800d90d2  call    cs:__imp_CoTaskMemFree
0x1800d90d9  nop     dword ptr [rax+rax+00h]
0x1800d90de  lea     r11, [rsp+88h+var_28]
0x1800d90e3  mov     eax, ebx
0x1800d90e5  mov     rbx, [r11+30h]
0x1800d90e9  mov     rbp, [r11+38h]
0x1800d90ed  mov     rsp, r11
0x1800d90f0  pop     r15
0x1800d90f2  pop     r14
0x1800d90f4  pop     r12
0x1800d90f6  pop     rdi
0x1800d90f7  pop     rsi
0x1800d90f8  retn
```
