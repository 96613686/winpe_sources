# PgmGetUserInfo

- ea: `0x140038704`
- end: `0x1400387cd`
- name: `PgmGetUserInfo`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001a50`

## callees

- `0x140038704`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14003875b`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14003875b`
- `ntoskrnl!SeQueryInformationToken` at `0x140038744`
- `ntoskrnl!SeQueryInformationToken` at `0x140038744`
- `ntoskrnl!SeAccessCheck` at `0x1400387aa`
- `ntoskrnl!SeAccessCheck` at `0x1400387aa`

## pseudocode

```c
__int64 __fastcall PgmGetUserInfo(__int64 a1, __int64 a2, PVOID *a3, BOOLEAN *a4)
{
  struct _SECURITY_SUBJECT_CONTEXT *v5; // rbx
  PACCESS_TOKEN ClientToken; // rcx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  int AccessStatus; // [rsp+60h] [rbp+8h] BYREF
  int v10; // [rsp+64h] [rbp+Ch]
  DWORD GrantedAccess; // [rsp+68h] [rbp+10h] BYREF

  v10 = HIDWORD(a1);
  AccessStatus = 0;
  GrantedAccess = 0;
  v5 = *(struct _SECURITY_SUBJECT_CONTEXT **)(*(_QWORD *)(a2 + 8) + 8LL);
  ClientToken = v5[1].ClientToken;
  if ( !ClientToken )
  {
    ClientToken = v5[1].PrimaryToken;
    if ( !ClientToken )
      return 3221225473LL;
  }
  AccessStatus = SeQueryInformationToken(ClientToken, TokenUser, a3);
  if ( AccessStatus < 0 )
    return 3221225473LL;
  *a4 = 0;
  GenericMapping = IoGetFileObjectGenericMapping();
  *a4 = SeAccessCheck(PgmSecurityDescriptor, v5 + 1, 0, 3u, 0, 0, GenericMapping, 1, &GrantedAccess, &AccessStatus);
  return 0;
}

```

## disassembly

```asm
0x140038704  mov     rax, rsp
0x140038707  mov     [rax+18h], rbx
0x14003870b  mov     [rax+8], rcx
0x14003870f  push    rdi
0x140038710  sub     rsp, 50h
0x140038714  mov     dword ptr [rax+8], 0
0x14003871b  mov     rdi, r9
0x14003871e  mov     dword ptr [rax+10h], 0
0x140038725  mov     rax, [rdx+8]
0x140038729  mov     rbx, [rax+8]
0x14003872d  mov     rcx, [rbx+20h]
0x140038731  test    rcx, rcx
0x140038734  jnz     short loc_14003873F
0x140038736  mov     rcx, [rbx+30h]; Token
0x14003873a  test    rcx, rcx
0x14003873d  jz      short loc_1400387BC
0x14003873f  mov     edx, 1; TokenInformationClass
0x140038744  call    cs:__imp_SeQueryInformationToken
0x14003874b  nop     dword ptr [rax+rax+00h]
0x140038750  mov     [rsp+58h+arg_0], eax
0x140038754  test    eax, eax
0x140038756  js      short loc_1400387BC
0x140038758  mov     byte ptr [rdi], 0
0x14003875b  call    cs:__imp_IoGetFileObjectGenericMapping
0x140038762  nop     dword ptr [rax+rax+00h]
0x140038767  lea     rcx, [rsp+58h+arg_0]
0x14003876c  mov     r9d, 3; DesiredAccess
0x140038772  mov     [rsp+58h+AccessStatus], rcx; AccessStatus
0x140038777  lea     rdx, [rbx+20h]; SubjectSecurityContext
0x14003877b  lea     rcx, [rsp+58h+arg_8]
0x140038780  xor     r8d, r8d; SubjectContextLocked
0x140038783  mov     [rsp+58h+GrantedAccess], rcx; GrantedAccess
0x140038788  mov     rcx, cs:PgmSecurityDescriptor; SecurityDescriptor
0x14003878f  mov     [rsp+58h+AccessMode], 1; AccessMode
0x140038794  mov     [rsp+58h+GenericMapping], rax; GenericMapping
0x140038799  mov     [rsp+58h+Privileges], 0; Privileges
0x1400387a2  mov     [rsp+58h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x1400387aa  call    cs:__imp_SeAccessCheck
0x1400387b1  nop     dword ptr [rax+rax+00h]
0x1400387b6  mov     [rdi], al
0x1400387b8  xor     eax, eax
0x1400387ba  jmp     short loc_1400387C1
0x1400387bc  mov     eax, 0C0000001h
0x1400387c1  mov     rbx, [rsp+58h+arg_10]
0x1400387c6  add     rsp, 50h
0x1400387ca  pop     rdi
0x1400387cb  retn
```
