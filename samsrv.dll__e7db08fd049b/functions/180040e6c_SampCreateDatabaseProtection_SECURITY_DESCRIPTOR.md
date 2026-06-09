# SampCreateDatabaseProtection(_SECURITY_DESCRIPTOR *)

- ea: `0x180040e6c`
- end: `0x180040f6a`
- name: `?SampCreateDatabaseProtection@@YAJPEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `254`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003f850`

## callees

- `0x180040e6c`

## import_xrefs

- `ntdll!RtlGetAce` at `0x180040f35`
- `ntdll!RtlGetAce` at `0x180040f35`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180040f59`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180040f59`
- `ntdll!RtlAddAccessAllowedAce` at `0x180040eff`
- `ntdll!RtlAddAccessAllowedAce` at `0x180040f1a`
- `ntdll!RtlAddAccessAllowedAce` at `0x180040eff`
- `ntdll!RtlAddAccessAllowedAce` at `0x180040f1a`
- `ntdll!RtlCreateAcl` at `0x180040ee4`
- `ntdll!RtlCreateAcl` at `0x180040ee4`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180040e88`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180040e88`
- `ntdll!RtlAllocateHeap` at `0x180040ec1`
- `ntdll!RtlAllocateHeap` at `0x180040ec1`
- `ntdll!RtlLengthSid` at `0x180040e95`
- `ntdll!RtlLengthSid` at `0x180040ea4`
- `ntdll!RtlLengthSid` at `0x180040e95`
- `ntdll!RtlLengthSid` at `0x180040ea4`

## pseudocode

```c
__int64 __fastcall SampCreateDatabaseProtection(PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  ULONG v2; // ebx
  ULONG v3; // edi
  struct _ACL *Heap; // rax
  struct _ACL *v5; // rbx
  WORD i; // di
  PVOID Ace; // [rsp+58h] [rbp+10h] BYREF

  Ace = 0;
  RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  v2 = RtlLengthSid(Group);
  v3 = v2 + RtlLengthSid(qword_1800EF788) + 40;
  Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  v5 = Heap;
  if ( !Heap )
    return 3221225495LL;
  RtlCreateAcl(Heap, v3, 2u);
  RtlAddAccessAllowedAce(v5, 2u, 0x10000000u, qword_1800EF788);
  RtlAddAccessAllowedAce(v5, 2u, 0x60000u, Group);
  for ( i = 0; i < v5->AceCount; *((_BYTE *)Ace + 1) |= 2u )
    RtlGetAce(v5, i++, &Ace);
  RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v5, 0);
  return 0;
}

```

## disassembly

```asm
0x180040e6c  push    rbx
0x180040e6e  push    rbp
0x180040e6f  push    rsi
0x180040e70  push    rdi
0x180040e71  sub     rsp, 28h
0x180040e75  mov     ebp, 1
0x180040e7a  mov     [rsp+48h+Ace], 0
0x180040e83  mov     edx, ebp; Revision
0x180040e85  mov     rsi, rcx
0x180040e88  call    cs:__imp_RtlCreateSecurityDescriptor
0x180040e8e  mov     rcx, cs:Group; Sid
0x180040e95  call    cs:__imp_RtlLengthSid
0x180040e9b  mov     rcx, cs:qword_1800EF788; Sid
0x180040ea2  mov     ebx, eax
0x180040ea4  call    cs:__imp_RtlLengthSid
0x180040eaa  mov     rcx, gs:60h
0x180040eb3  xor     edx, edx; Flags
0x180040eb5  lea     edi, [rax+28h]
0x180040eb8  mov     rcx, [rcx+30h]; HeapHandle
0x180040ebc  add     edi, ebx
0x180040ebe  mov     r8d, edi; Size
0x180040ec1  call    cs:__imp_RtlAllocateHeap
0x180040ec7  mov     rbx, rax
0x180040eca  test    rax, rax
0x180040ecd  jnz     short loc_180040ED9
0x180040ecf  mov     eax, 0C0000017h
0x180040ed4  jmp     loc_180040F61
0x180040ed9  mov     r8d, 2; AclRevision
0x180040edf  mov     edx, edi; AclSize
0x180040ee1  mov     rcx, rbx; Acl
0x180040ee4  call    cs:__imp_RtlCreateAcl
0x180040eea  mov     r9, cs:qword_1800EF788; Sid
0x180040ef1  mov     edx, 2; Revision
0x180040ef6  mov     r8d, 10000000h; AccessMask
0x180040efc  mov     rcx, rbx; Acl
0x180040eff  call    cs:__imp_RtlAddAccessAllowedAce
0x180040f05  mov     r9, cs:Group; Sid
0x180040f0c  mov     edx, 2; Revision
0x180040f11  mov     r8d, 60000h; AccessMask
0x180040f17  mov     rcx, rbx; Acl
0x180040f1a  call    cs:__imp_RtlAddAccessAllowedAce
0x180040f20  xor     eax, eax
0x180040f22  xor     edi, edi
0x180040f24  cmp     ax, [rbx+4]
0x180040f28  jnb     short loc_180040F4D
0x180040f2a  movzx   edx, di; AceIndex
0x180040f2d  lea     r8, [rsp+48h+Ace]; Ace
0x180040f32  mov     rcx, rbx; Acl
0x180040f35  call    cs:__imp_RtlGetAce
0x180040f3b  mov     rax, [rsp+48h+Ace]
0x180040f40  add     di, bp
0x180040f43  or      byte ptr [rax+1], 2
0x180040f47  cmp     di, [rbx+4]
0x180040f4b  jb      short loc_180040F2A
0x180040f4d  xor     r9d, r9d; DaclDefaulted
0x180040f50  mov     r8, rbx; Dacl
0x180040f53  mov     dl, bpl; DaclPresent
0x180040f56  mov     rcx, rsi; SecurityDescriptor
0x180040f59  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180040f5f  xor     eax, eax
0x180040f61  add     rsp, 28h
0x180040f65  pop     rdi
0x180040f66  pop     rsi
0x180040f67  pop     rbp
0x180040f68  pop     rbx
0x180040f69  retn
```
