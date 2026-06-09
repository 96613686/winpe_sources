# Smb2QueryMaximalAccess

- ea: `0x140085670`
- end: `0x140085801`
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
- `0x140085670`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14009a8ab`
- `ntoskrnl!ExAllocatePool2` at `0x14009a8ab`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14008578e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14008578e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400857b9`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400857b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400857f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400857f0`
- `ntoskrnl!NtQuerySecurityObject` at `0x1400856f5`
- `ntoskrnl!NtQuerySecurityObject` at `0x14009a8df`
- `ntoskrnl!NtQuerySecurityObject` at `0x1400856f5`
- `ntoskrnl!NtQuerySecurityObject` at `0x14009a8df`
- `srvnet!SrvLibRetrieveMaximalAccessRightsForUser` at `0x140085737`
- `srvnet!SrvLibRetrieveMaximalAccessRightsForUser` at `0x140085737`

## pseudocode

```c
__int64 __fastcall Smb2QueryMaximalAccess(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 FileHandle; // rax
  HANDLE *v9; // rsi
  NTSTATUS MaximalAccessRightsForUser; // ebx
  int v11; // edi
  _BYTE *Pool2; // rbp
  ULONG v14; // eax
  _BYTE *v15; // rax
  int LengthNeeded; // [rsp+20h] [rbp-248h]
  ULONG Length; // [rsp+30h] [rbp-238h] BYREF
  _BYTE SecurityDescriptor[512]; // [rsp+38h] [rbp-230h] BYREF

  Length = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  FileHandle = Smb2GetFileHandle(a1, v6, v7);
  v9 = (HANDLE *)FileHandle;
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
      v11 = 0;
      Pool2 = SecurityDescriptor;
LABEL_4:
      Smb2DereferenceHandle(v9);
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
      if ( v11 == 3 )
      {
        ExFreeToLookasideListEx(&Srv2PagedBlockTypeBuffer8K, Pool2);
      }
      else if ( v11 == 1 )
      {
        ExFreePoolWithTag(Pool2, 0);
      }
      return (unsigned int)MaximalAccessRightsForUser;
    }
    v14 = Length;
    if ( Length <= 0x2000 )
    {
      v15 = ExAllocateFromLookasideListEx(&Srv2PagedBlockTypeBuffer8K);
      Pool2 = v15;
      if ( v15 )
      {
        memset(v15, 0, 0x2000u);
        v11 = 3;
LABEL_18:
        MaximalAccessRightsForUser = NtQuerySecurityObject(v9[11], 0x7Fu, Pool2, Length, &Length);
        goto LABEL_4;
      }
      v14 = Length;
    }
    Pool2 = (_BYTE *)ExAllocatePool2(256, v14, 1647465292);
    if ( !Pool2 )
    {
      MaximalAccessRightsForUser = -1073741670;
      Smb2DereferenceHandle(v9);
      return (unsigned int)MaximalAccessRightsForUser;
    }
    v11 = 1;
    goto LABEL_18;
  }
  return 3221225768LL;
}

```

## disassembly

```asm
0x140085670  push    rbx
0x140085672  push    rsi
0x140085673  push    r14
0x140085675  push    r15
0x140085677  sub     rsp, 248h
0x14008567e  mov     rax, cs:__security_cookie
0x140085685  xor     rax, rsp
0x140085688  mov     [rsp+268h+var_30], rax
0x140085690  mov     r15, r8
0x140085693  mov     [rsp+268h+Length], 0
0x14008569b  mov     r14, rdx
0x14008569e  mov     rbx, rcx
0x1400856a1  xor     edx, edx; Val
0x1400856a3  lea     rcx, [rsp+268h+SecurityDescriptor]; void *
0x1400856a8  mov     r8d, 200h; Size
0x1400856ae  call    memset
0x1400856b3  mov     rcx, rbx
0x1400856b6  call    Smb2GetFileHandle
0x1400856bb  mov     rsi, rax
0x1400856be  test    rax, rax
0x1400856c1  jz      loc_14008579C
0x1400856c7  mov     rcx, [rsi+58h]; Handle
0x1400856cb  lea     rax, [rsp+268h+Length]
0x1400856d0  mov     [rsp+268h+arg_18], rbp
0x1400856d8  lea     r8, [rsp+268h+SecurityDescriptor]; SecurityDescriptor
0x1400856dd  mov     r9d, 200h; Length
0x1400856e3  mov     qword ptr [rsp+268h+LengthNeeded], rax; LengthNeeded
0x1400856e8  mov     edx, 7Fh; SecurityInformation
0x1400856ed  mov     [rsp+268h+var_28], rdi
0x1400856f5  call    cs:__imp_NtQuerySecurityObject
0x1400856fc  nop     dword ptr [rax+rax+00h]
0x140085701  mov     ebx, eax
0x140085703  cmp     eax, 0C0000023h
0x140085708  jz      loc_1400857A3
0x14008570e  xor     edi, edi
0x140085710  lea     rbp, [rsp+268h+SecurityDescriptor]
0x140085715  mov     rcx, rsi; P
0x140085718  call    Smb2DereferenceHandle
0x14008571d  test    ebx, ebx
0x14008571f  js      short loc_140085745
0x140085721  lea     rcx, [r14+20h]
0x140085725  mov     byte ptr [rsp+268h+LengthNeeded], 1
0x14008572a  mov     r9, r15
0x14008572d  lea     r8, Smb2FileAccessMapping
0x140085734  mov     rdx, rbp
0x140085737  call    cs:__imp_SrvLibRetrieveMaximalAccessRightsForUser
0x14008573e  nop     dword ptr [rax+rax+00h]
0x140085743  mov     ebx, eax
0x140085745  cmp     edi, 3
0x140085748  jz      short loc_140085784
0x14008574a  cmp     edi, 1
0x14008574d  jz      loc_1400857EB
0x140085753  mov     rdi, [rsp+268h+var_28]
0x14008575b  mov     eax, ebx
0x14008575d  mov     rbp, [rsp+268h+arg_18]
0x140085765  mov     rcx, [rsp+268h+var_30]
0x14008576d  xor     rcx, rsp; StackCookie
0x140085770  call    __security_check_cookie
0x140085775  add     rsp, 248h
0x14008577c  pop     r15
0x14008577e  pop     r14
0x140085780  pop     rsi
0x140085781  pop     rbx
0x140085782  retn
0x140085784  mov     rdx, rbp; Entry
0x140085787  lea     rcx, Srv2PagedBlockTypeBuffer8K; Lookaside
0x14008578e  call    cs:__imp_ExFreeToLookasideListEx
0x140085795  nop     dword ptr [rax+rax+00h]
0x14008579a  jmp     short loc_140085753
0x14008579c  mov     eax, 0C0000128h
0x1400857a1  jmp     short loc_140085765
0x1400857a3  mov     eax, [rsp+268h+Length]
0x1400857a7  cmp     eax, 2000h
0x1400857ac  ja      loc_14009A89E
0x1400857b2  lea     rcx, Srv2PagedBlockTypeBuffer8K; Lookaside
0x1400857b9  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400857c0  nop     dword ptr [rax+rax+00h]
0x1400857c5  mov     rbp, rax
0x1400857c8  test    rax, rax
0x1400857cb  jz      loc_14009A89A
0x1400857d1  xor     edx, edx; Val
0x1400857d3  mov     r8d, 2000h; Size
0x1400857d9  mov     rcx, rax; void *
0x1400857dc  call    memset
0x1400857e1  mov     edi, 3
0x1400857e6  jmp     loc_14009A8C4
0x1400857eb  xor     edx, edx; Tag
0x1400857ed  mov     rcx, rbp; P
0x1400857f0  call    cs:__imp_ExFreePoolWithTag
0x1400857f7  nop     dword ptr [rax+rax+00h]
0x1400857fc  jmp     loc_140085753
0x14009a89a  mov     eax, [rsp+268h+Length]
0x14009a89e  mov     edx, eax
0x14009a8a0  mov     ecx, 100h
0x14009a8a5  mov     r8d, 6232534Ch
0x14009a8ab  call    cs:__imp_ExAllocatePool2
0x14009a8b2  nop     dword ptr [rax+rax+00h]
0x14009a8b7  mov     rbp, rax
0x14009a8ba  test    rax, rax
0x14009a8bd  jz      short loc_14009A8F2
0x14009a8bf  mov     edi, 1
0x14009a8c4  mov     r9d, [rsp+268h+Length]; Length
0x14009a8c9  lea     rax, [rsp+268h+Length]
0x14009a8ce  mov     rcx, [rsi+58h]; Handle
0x14009a8d2  mov     r8, rbp; SecurityDescriptor
0x14009a8d5  mov     edx, 7Fh; SecurityInformation
0x14009a8da  mov     qword ptr [rsp+268h+LengthNeeded], rax; LengthNeeded
0x14009a8df  call    cs:__imp_NtQuerySecurityObject
0x14009a8e6  nop     dword ptr [rax+rax+00h]
0x14009a8eb  mov     ebx, eax
0x14009a8ed  jmp     loc_140085715
0x14009a8f2  mov     rcx, rsi; P
0x14009a8f5  mov     ebx, 0C000009Ah
0x14009a8fa  call    Smb2DereferenceHandle
0x14009a8ff  nop
0x14009a900  jmp     loc_140085753
```
