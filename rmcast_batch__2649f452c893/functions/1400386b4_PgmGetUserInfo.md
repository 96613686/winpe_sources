# PgmGetUserInfo

- ea: `0x1400386b4`
- end: `0x14003877d`
- name: `PgmGetUserInfo`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001a50`

## callees

- `0x1400386b4`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14003870b`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14003870b`
- `ntoskrnl!SeQueryInformationToken` at `0x1400386f4`
- `ntoskrnl!SeQueryInformationToken` at `0x1400386f4`
- `ntoskrnl!SeAccessCheck` at `0x14003875a`
- `ntoskrnl!SeAccessCheck` at `0x14003875a`

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
0x1400386b4  mov     rax, rsp
0x1400386b7  mov     [rax+18h], rbx
0x1400386bb  mov     [rax+8], rcx
0x1400386bf  push    rdi
0x1400386c0  sub     rsp, 50h
0x1400386c4  mov     dword ptr [rax+8], 0
0x1400386cb  mov     rdi, r9
0x1400386ce  mov     dword ptr [rax+10h], 0
0x1400386d5  mov     rax, [rdx+8]
0x1400386d9  mov     rbx, [rax+8]
0x1400386dd  mov     rcx, [rbx+20h]
0x1400386e1  test    rcx, rcx
0x1400386e4  jnz     short loc_1400386EF
0x1400386e6  mov     rcx, [rbx+30h]; Token
0x1400386ea  test    rcx, rcx
0x1400386ed  jz      short loc_14003876C
0x1400386ef  mov     edx, 1; TokenInformationClass
0x1400386f4  call    cs:__imp_SeQueryInformationToken
0x1400386fb  nop     dword ptr [rax+rax+00h]
0x140038700  mov     [rsp+58h+arg_0], eax
0x140038704  test    eax, eax
0x140038706  js      short loc_14003876C
0x140038708  mov     byte ptr [rdi], 0
0x14003870b  call    cs:__imp_IoGetFileObjectGenericMapping
0x140038712  nop     dword ptr [rax+rax+00h]
0x140038717  lea     rcx, [rsp+58h+arg_0]
0x14003871c  mov     r9d, 3; DesiredAccess
0x140038722  mov     [rsp+58h+AccessStatus], rcx; AccessStatus
0x140038727  lea     rdx, [rbx+20h]; SubjectSecurityContext
0x14003872b  lea     rcx, [rsp+58h+arg_8]
0x140038730  xor     r8d, r8d; SubjectContextLocked
0x140038733  mov     [rsp+58h+GrantedAccess], rcx; GrantedAccess
0x140038738  mov     rcx, cs:PgmSecurityDescriptor; SecurityDescriptor
0x14003873f  mov     [rsp+58h+AccessMode], 1; AccessMode
0x140038744  mov     [rsp+58h+GenericMapping], rax; GenericMapping
0x140038749  mov     [rsp+58h+Privileges], 0; Privileges
0x140038752  mov     [rsp+58h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14003875a  call    cs:__imp_SeAccessCheck
0x140038761  nop     dword ptr [rax+rax+00h]
0x140038766  mov     [rdi], al
0x140038768  xor     eax, eax
0x14003876a  jmp     short loc_140038771
0x14003876c  mov     eax, 0C0000001h
0x140038771  mov     rbx, [rsp+58h+arg_10]
0x140038776  add     rsp, 50h
0x14003877a  pop     rdi
0x14003877b  retn
```
