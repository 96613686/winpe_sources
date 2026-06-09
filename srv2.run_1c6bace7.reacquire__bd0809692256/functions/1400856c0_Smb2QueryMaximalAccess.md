# Smb2QueryMaximalAccess

- ea: `0x1400856c0`
- end: `0x140085851`
- name: `Smb2QueryMaximalAccess`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f4d0`

## callees

- `0x140013810`
- `0x140014d60`
- `0x140038490`
- `0x140038980`
- `0x1400856c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14009a8fb`
- `ntoskrnl!ExAllocatePool2` at `0x14009a8fb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400857de`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400857de`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140085809`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140085809`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085840`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085840`
- `ntoskrnl!NtQuerySecurityObject` at `0x140085745`
- `ntoskrnl!NtQuerySecurityObject` at `0x14009a92f`
- `ntoskrnl!NtQuerySecurityObject` at `0x140085745`
- `ntoskrnl!NtQuerySecurityObject` at `0x14009a92f`
- `srvnet!SrvLibRetrieveMaximalAccessRightsForUser` at `0x140085787`
- `srvnet!SrvLibRetrieveMaximalAccessRightsForUser` at `0x140085787`

## pseudocode

```c
__int64 __fastcall Smb2QueryMaximalAccess(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 FileHandle; // rax
  HANDLE *v7; // rsi
  NTSTATUS MaximalAccessRightsForUser; // ebx
  int v9; // edi
  _BYTE *Pool2; // rbp
  ULONG v12; // eax
  _BYTE *v13; // rax
  int LengthNeeded; // [rsp+20h] [rbp-248h]
  ULONG Length; // [rsp+30h] [rbp-238h] BYREF
  _BYTE SecurityDescriptor[512]; // [rsp+38h] [rbp-230h] BYREF

  Length = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  FileHandle = Smb2GetFileHandle(a1);
  v7 = (HANDLE *)FileHandle;
  if ( FileHandle )
  {
    MaximalAccessRightsForUser = NtQuerySecurityObject(
                                   *(HANDLE *)(FileHandle + 88),
                                   0x7Fu,
                                   SecurityDescriptor,
                                   0x200u,
                                   &Length);
    if ( MaximalAccessRightsForUser != -1073741789 )
    {
      v9 = 0;
      Pool2 = SecurityDescriptor;
LABEL_4:
      Smb2DereferenceHandle(v7);
      if ( MaximalAccessRightsForUser >= 0 )
      {
        LOBYTE(LengthNeeded) = 1;
        MaximalAccessRightsForUser = SrvLibRetrieveMaximalAccessRightsForUser(
                                       a2 + 32,
                                       Pool2,
                                       &Smb2FileAccessMapping,
                                       a3,
                                       LengthNeeded);
      }
      if ( v9 == 3 )
      {
        ExFreeToLookasideListEx(&Srv2PagedBlockTypeBuffer8K, Pool2);
      }
      else if ( v9 == 1 )
      {
        ExFreePoolWithTag(Pool2, 0);
      }
      return (unsigned int)MaximalAccessRightsForUser;
    }
    v12 = Length;
    if ( Length <= 0x2000 )
    {
      v13 = ExAllocateFromLookasideListEx(&Srv2PagedBlockTypeBuffer8K);
      Pool2 = v13;
      if ( v13 )
      {
        memset(v13, 0, 0x2000u);
        v9 = 3;
LABEL_18:
        MaximalAccessRightsForUser = NtQuerySecurityObject(v7[11], 0x7Fu, Pool2, Length, &Length);
        goto LABEL_4;
      }
      v12 = Length;
    }
    Pool2 = (_BYTE *)ExAllocatePool2(256, v12, 1647465292);
    if ( !Pool2 )
    {
      MaximalAccessRightsForUser = -1073741670;
      Smb2DereferenceHandle(v7);
      return (unsigned int)MaximalAccessRightsForUser;
    }
    v9 = 1;
    goto LABEL_18;
  }
  return 3221225768LL;
}

```

## disassembly

```asm
0x1400856c0  push    rbx
0x1400856c2  push    rsi
0x1400856c3  push    r14
0x1400856c5  push    r15
0x1400856c7  sub     rsp, 248h
0x1400856ce  mov     rax, cs:__security_cookie
0x1400856d5  xor     rax, rsp
0x1400856d8  mov     [rsp+268h+var_30], rax
0x1400856e0  mov     r15, r8
0x1400856e3  mov     [rsp+268h+Length], 0
0x1400856eb  mov     r14, rdx
0x1400856ee  mov     rbx, rcx
0x1400856f1  xor     edx, edx; Val
0x1400856f3  lea     rcx, [rsp+268h+SecurityDescriptor]; void *
0x1400856f8  mov     r8d, 200h; Size
0x1400856fe  call    memset
0x140085703  mov     rcx, rbx
0x140085706  call    Smb2GetFileHandle
0x14008570b  mov     rsi, rax
0x14008570e  test    rax, rax
0x140085711  jz      loc_1400857EC
0x140085717  mov     rcx, [rsi+58h]; Handle
0x14008571b  lea     rax, [rsp+268h+Length]
0x140085720  mov     [rsp+268h+arg_18], rbp
0x140085728  lea     r8, [rsp+268h+SecurityDescriptor]; SecurityDescriptor
0x14008572d  mov     r9d, 200h; Length
0x140085733  mov     qword ptr [rsp+268h+LengthNeeded], rax; LengthNeeded
0x140085738  mov     edx, 7Fh; SecurityInformation
0x14008573d  mov     [rsp+268h+var_28], rdi
0x140085745  call    cs:__imp_NtQuerySecurityObject
0x14008574c  nop     dword ptr [rax+rax+00h]
0x140085751  mov     ebx, eax
0x140085753  cmp     eax, 0C0000023h
0x140085758  jz      loc_1400857F3
0x14008575e  xor     edi, edi
0x140085760  lea     rbp, [rsp+268h+SecurityDescriptor]
0x140085765  mov     rcx, rsi; P
0x140085768  call    Smb2DereferenceHandle
0x14008576d  test    ebx, ebx
0x14008576f  js      short loc_140085795
0x140085771  lea     rcx, [r14+20h]
0x140085775  mov     byte ptr [rsp+268h+LengthNeeded], 1
0x14008577a  mov     r9, r15
0x14008577d  lea     r8, Smb2FileAccessMapping
0x140085784  mov     rdx, rbp
0x140085787  call    cs:__imp_SrvLibRetrieveMaximalAccessRightsForUser
0x14008578e  nop     dword ptr [rax+rax+00h]
0x140085793  mov     ebx, eax
0x140085795  cmp     edi, 3
0x140085798  jz      short loc_1400857D4
0x14008579a  cmp     edi, 1
0x14008579d  jz      loc_14008583B
0x1400857a3  mov     rdi, [rsp+268h+var_28]
0x1400857ab  mov     eax, ebx
0x1400857ad  mov     rbp, [rsp+268h+arg_18]
0x1400857b5  mov     rcx, [rsp+268h+var_30]
0x1400857bd  xor     rcx, rsp; StackCookie
0x1400857c0  call    __security_check_cookie
0x1400857c5  add     rsp, 248h
0x1400857cc  pop     r15
0x1400857ce  pop     r14
0x1400857d0  pop     rsi
0x1400857d1  pop     rbx
0x1400857d2  retn
0x1400857d4  mov     rdx, rbp; Entry
0x1400857d7  lea     rcx, Srv2PagedBlockTypeBuffer8K; Lookaside
0x1400857de  call    cs:__imp_ExFreeToLookasideListEx
0x1400857e5  nop     dword ptr [rax+rax+00h]
0x1400857ea  jmp     short loc_1400857A3
0x1400857ec  mov     eax, 0C0000128h
0x1400857f1  jmp     short loc_1400857B5
0x1400857f3  mov     eax, [rsp+268h+Length]
0x1400857f7  cmp     eax, 2000h
0x1400857fc  ja      loc_14009A8EE
0x140085802  lea     rcx, Srv2PagedBlockTypeBuffer8K; Lookaside
0x140085809  call    cs:__imp_ExAllocateFromLookasideListEx
0x140085810  nop     dword ptr [rax+rax+00h]
0x140085815  mov     rbp, rax
0x140085818  test    rax, rax
0x14008581b  jz      loc_14009A8EA
0x140085821  xor     edx, edx; Val
0x140085823  mov     r8d, 2000h; Size
0x140085829  mov     rcx, rax; void *
0x14008582c  call    memset
0x140085831  mov     edi, 3
0x140085836  jmp     loc_14009A914
0x14008583b  xor     edx, edx; Tag
0x14008583d  mov     rcx, rbp; P
0x140085840  call    cs:__imp_ExFreePoolWithTag
0x140085847  nop     dword ptr [rax+rax+00h]
0x14008584c  jmp     loc_1400857A3
0x14009a8ea  mov     eax, [rsp+268h+Length]
0x14009a8ee  mov     edx, eax
0x14009a8f0  mov     ecx, 100h
0x14009a8f5  mov     r8d, 6232534Ch
0x14009a8fb  call    cs:__imp_ExAllocatePool2
0x14009a902  nop     dword ptr [rax+rax+00h]
0x14009a907  mov     rbp, rax
0x14009a90a  test    rax, rax
0x14009a90d  jz      short loc_14009A942
0x14009a90f  mov     edi, 1
0x14009a914  mov     r9d, [rsp+268h+Length]; Length
0x14009a919  lea     rax, [rsp+268h+Length]
0x14009a91e  mov     rcx, [rsi+58h]; Handle
0x14009a922  mov     r8, rbp; SecurityDescriptor
0x14009a925  mov     edx, 7Fh; SecurityInformation
0x14009a92a  mov     qword ptr [rsp+268h+LengthNeeded], rax; LengthNeeded
0x14009a92f  call    cs:__imp_NtQuerySecurityObject
0x14009a936  nop     dword ptr [rax+rax+00h]
0x14009a93b  mov     ebx, eax
0x14009a93d  jmp     loc_140085765
0x14009a942  mov     rcx, rsi; P
0x14009a945  mov     ebx, 0C000009Ah
0x14009a94a  call    Smb2DereferenceHandle
0x14009a94f  nop
0x14009a950  jmp     loc_1400857A3
```
