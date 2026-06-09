# ScCreateAndSetSD

- ea: `0x18004ac10`
- end: `0x18004af57`
- name: `ScCreateAndSetSD`
- size: `839`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004af60`

## callees

- `0x18004ac10`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18004ae64`
- `ntdll!RtlCopySid` at `0x18004ae64`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18004af35`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18004af35`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18004aedb`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18004aedb`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18004af16`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18004af16`
- `ntdll!RtlAddAce` at `0x18004ae93`
- `ntdll!RtlAddAce` at `0x18004ae93`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18004aef4`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18004aef4`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18004aebd`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18004aebd`
- `ntdll!RtlLengthSid` at `0x18004ac76`
- `ntdll!RtlLengthSid` at `0x18004adc9`
- `ntdll!RtlLengthSid` at `0x18004ae55`
- `ntdll!RtlLengthSid` at `0x18004ac76`
- `ntdll!RtlLengthSid` at `0x18004adc9`
- `ntdll!RtlLengthSid` at `0x18004ae55`
- `ntdll!RtlAllocateHeap` at `0x18004acd7`
- `ntdll!RtlAllocateHeap` at `0x18004ad50`
- `ntdll!RtlAllocateHeap` at `0x18004acd7`
- `ntdll!RtlAllocateHeap` at `0x18004ad50`
- `ntdll!RtlFreeHeap` at `0x18004ad70`
- `ntdll!RtlFreeHeap` at `0x18004ad88`
- `ntdll!RtlFreeHeap` at `0x18004ad70`
- `ntdll!RtlFreeHeap` at `0x18004ad88`
- `ntdll!RtlCreateAcl` at `0x18004ad03`
- `ntdll!RtlCreateAcl` at `0x18004ad34`
- `ntdll!RtlCreateAcl` at `0x18004ad03`
- `ntdll!RtlCreateAcl` at `0x18004ad34`

## pseudocode

```c
__int64 __fastcall ScCreateAndSetSD(__int64 a1, __int64 a2, __int64 a3, __int64 a4, struct _ACL **a5)
{
  ULONG v5; // r13d
  __int64 v7; // rdi
  ULONG v8; // r14d
  unsigned int v9; // esi
  ULONG v10; // eax
  ULONG v11; // eax
  unsigned int v13; // ecx
  SIZE_T v14; // r8
  struct _ACL *Heap; // rax
  struct _ACL *v16; // rbp
  NTSTATUS SecurityDescriptor; // ebx
  _WORD *v18; // rsi
  struct _ACL *v19; // r15
  struct _ACL *v20; // rdi
  struct _ACL *v21; // r15
  unsigned int i; // r14d
  __int64 v23; // rbx
  ULONG v24; // eax
  void *v25; // rdi
  ULONG v26; // eax
  struct _ACL *Dacl; // [rsp+30h] [rbp-48h]
  PSID Owner; // [rsp+38h] [rbp-40h]
  ULONG AceListLength; // [rsp+88h] [rbp+10h]
  struct _ACL *Acl; // [rsp+90h] [rbp+18h]
  PVOID HeapHandle; // [rsp+98h] [rbp+20h]

  Owner = LocalSystemSid;
  v5 = 0;
  v7 = 8;
  v8 = 8;
  v9 = 0;
  HeapHandle = NtCurrentPeb()->ProcessHeap;
  while ( v9 < 4 )
  {
    v10 = RtlLengthSid(**(PSID **)(a1 + 16LL * v9 + 8));
    if ( !*(_BYTE *)(a1 + 16LL * v9) || *(_BYTE *)(a1 + 16LL * v9) == 1 )
    {
      v11 = v10 + 8;
      v7 = v11 + (unsigned int)v7;
    }
    else
    {
      if ( *(_BYTE *)(a1 + 16LL * v9) != 2 )
        return 3221225485LL;
      v11 = v10 + 8;
      v8 += v11;
    }
    ++v9;
    if ( v5 > v11 )
      v11 = v5;
    v5 = v11;
  }
  v13 = v7 + 40;
  if ( (_DWORD)v7 == 8 )
    v13 = 40;
  v14 = v13 + v8;
  if ( v8 == 8 )
    v14 = v13;
  Heap = (struct _ACL *)RtlAllocateHeap(HeapHandle, 0, v14);
  v16 = Heap;
  if ( !Heap )
    return (unsigned int)-1073741801;
  v18 = 0;
  v19 = Heap + 5;
  if ( (_DWORD)v7 == 8 )
  {
    Dacl = 0;
    v20 = Heap + 5;
  }
  else
  {
    SecurityDescriptor = RtlCreateAcl(Heap + 5, v7, 2u);
    if ( SecurityDescriptor < 0 )
      goto LABEL_27;
    Dacl = v19;
    v20 = (struct _ACL *)((char *)v19 + v7);
  }
  v21 = 0;
  if ( v8 != 8 )
  {
    SecurityDescriptor = RtlCreateAcl(v20, v8, 2u);
    if ( SecurityDescriptor < 0 )
      goto LABEL_27;
    v21 = v20;
  }
  v18 = RtlAllocateHeap(HeapHandle, 0, v5);
  if ( !v18 )
  {
    SecurityDescriptor = -1073741801;
    goto LABEL_27;
  }
  for ( i = 0; i < 4; ++i )
  {
    v23 = 16LL * i;
    v24 = RtlLengthSid(**(PSID **)(v23 + a1 + 8));
    if ( !*(_BYTE *)(v23 + a1) )
    {
      v25 = **(void ***)(v23 + a1 + 8);
      *(_BYTE *)v18 = 0;
      goto LABEL_38;
    }
    if ( *(_BYTE *)(v23 + a1) == 1 )
    {
      v25 = **(void ***)(v23 + a1 + 8);
      *(_BYTE *)v18 = 1;
LABEL_38:
      Acl = Dacl;
      v18[1] = v24 + 8;
      AceListLength = v24 + 8;
      goto LABEL_39;
    }
    if ( *(_BYTE *)(v23 + a1) != 2 )
    {
      SecurityDescriptor = -1073741823;
      goto LABEL_27;
    }
    Acl = v21;
    AceListLength = v24 + 8;
    v25 = **(void ***)(v23 + a1 + 8);
    *(_BYTE *)v18 = 2;
    v18[1] = v24 + 8;
LABEL_39:
    *((_BYTE *)v18 + 1) = *(_BYTE *)(v23 + a1 + 1) | *(_BYTE *)(v23 + a1 + 2);
    *((_DWORD *)v18 + 1) = *(_DWORD *)(v23 + a1 + 4);
    v26 = RtlLengthSid(v25);
    SecurityDescriptor = RtlCopySid(v26, v18 + 4, v25);
    if ( SecurityDescriptor < 0 )
      goto LABEL_27;
    SecurityDescriptor = RtlAddAce(Acl, 2u, 0xFFFFFFFF, v18, AceListLength);
    if ( SecurityDescriptor < 0 )
      goto LABEL_27;
  }
  SecurityDescriptor = RtlCreateSecurityDescriptor(v16, 1u);
  if ( SecurityDescriptor < 0
    || (SecurityDescriptor = RtlSetOwnerSecurityDescriptor(v16, Owner, 0), SecurityDescriptor < 0)
    || (SecurityDescriptor = RtlSetGroupSecurityDescriptor(v16, Owner, 0), SecurityDescriptor < 0)
    || (SecurityDescriptor = RtlSetDaclSecurityDescriptor(v16, Dacl != 0, Dacl, 0), SecurityDescriptor < 0)
    || (SecurityDescriptor = RtlSetSaclSecurityDescriptor(v16, v21 != 0, v21, 0), SecurityDescriptor < 0) )
  {
LABEL_27:
    RtlFreeHeap(HeapHandle, 0, v16);
    if ( v18 )
      goto LABEL_28;
    return (unsigned int)SecurityDescriptor;
  }
  SecurityDescriptor = 0;
  *a5 = v16;
LABEL_28:
  RtlFreeHeap(HeapHandle, 0, v18);
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x18004ac10  mov     rax, rsp
0x18004ac13  mov     [rax+8], rbx
0x18004ac17  mov     [rax+20h], r9
0x18004ac1b  mov     [rax+18h], r8
0x18004ac1f  mov     [rax+10h], edx
0x18004ac22  push    rbp
0x18004ac23  push    rsi
0x18004ac24  push    rdi
0x18004ac25  push    r12
0x18004ac27  push    r13
0x18004ac29  push    r14
0x18004ac2b  push    r15
0x18004ac2d  sub     rsp, 40h
0x18004ac31  mov     rax, cs:LocalSystemSid
0x18004ac38  mov     ebp, 8
0x18004ac3d  mov     [rsp+78h+Owner], rax
0x18004ac42  xor     r13d, r13d
0x18004ac45  mov     rax, gs:60h
0x18004ac4e  mov     r12, rcx
0x18004ac51  mov     edi, ebp
0x18004ac53  mov     r14d, ebp
0x18004ac56  xor     esi, esi
0x18004ac58  mov     r9, [rax+30h]
0x18004ac5c  mov     [rsp+78h+HeapHandle], r9
0x18004ac64  cmp     esi, 4
0x18004ac67  jnb     short loc_18004ACB5
0x18004ac69  mov     ebx, esi
0x18004ac6b  add     rbx, rbx
0x18004ac6e  mov     rcx, [r12+rbx*8+8]
0x18004ac73  mov     rcx, [rcx]; Sid
0x18004ac76  call    cs:__imp_RtlLengthSid
0x18004ac7c  movzx   edx, byte ptr [r12+rbx*8]
0x18004ac81  test    edx, edx
0x18004ac83  jz      short loc_18004AC99
0x18004ac85  sub     edx, 1
0x18004ac88  jz      short loc_18004AC99
0x18004ac8a  cmp     edx, 1
0x18004ac8d  jnz     short loc_18004ACAB
0x18004ac8f  lea     ecx, [rax+8]
0x18004ac92  mov     eax, ecx
0x18004ac94  add     r14d, ecx
0x18004ac97  jmp     short loc_18004AC9D
0x18004ac99  add     eax, ebp
0x18004ac9b  add     edi, eax
0x18004ac9d  inc     esi
0x18004ac9f  cmp     r13d, eax
0x18004aca2  cmova   eax, r13d
0x18004aca6  mov     r13d, eax
0x18004aca9  jmp     short loc_18004AC64
0x18004acab  mov     eax, 0C000000Dh
0x18004acb0  jmp     loc_18004AD90
0x18004acb5  cmp     edi, ebp
0x18004acb7  lea     ecx, [rdi+28h]
0x18004acba  mov     eax, 28h ; '('
0x18004acbf  cmovz   ecx, eax
0x18004acc2  cmp     r14d, ebp
0x18004acc5  lea     r8d, [rcx+r14]
0x18004acc9  cmovz   r8d, ecx; Size
0x18004accd  mov     rcx, [rsp+78h+HeapHandle]; HeapHandle
0x18004acd5  xor     edx, edx; Flags
0x18004acd7  call    cs:__imp_RtlAllocateHeap
0x18004acdd  mov     rbp, rax
0x18004ace0  test    rax, rax
0x18004ace3  jnz     short loc_18004ACEF
0x18004ace5  mov     ebx, 0C0000017h
0x18004acea  jmp     loc_18004AD8E
0x18004acef  xor     esi, esi
0x18004acf1  lea     r15, [rax+28h]
0x18004acf5  cmp     edi, 8
0x18004acf8  jz      short loc_18004AD19
0x18004acfa  lea     r8d, [rsi+2]; AclRevision
0x18004acfe  mov     edx, edi; AclSize
0x18004ad00  mov     rcx, r15; Acl
0x18004ad03  call    cs:__imp_RtlCreateAcl
0x18004ad09  mov     ebx, eax
0x18004ad0b  test    eax, eax
0x18004ad0d  js      short loc_18004AD63
0x18004ad0f  mov     [rsp+78h+Dacl], r15
0x18004ad14  add     rdi, r15
0x18004ad17  jmp     short loc_18004AD21
0x18004ad19  mov     [rsp+78h+Dacl], rsi
0x18004ad1e  mov     rdi, r15
0x18004ad21  xor     r15d, r15d
0x18004ad24  cmp     r14d, 8
0x18004ad28  jz      short loc_18004AD43
0x18004ad2a  lea     r8d, [r15+2]; AclRevision
0x18004ad2e  mov     edx, r14d; AclSize
0x18004ad31  mov     rcx, rdi; Acl
0x18004ad34  call    cs:__imp_RtlCreateAcl
0x18004ad3a  mov     ebx, eax
0x18004ad3c  test    eax, eax
0x18004ad3e  js      short loc_18004AD63
0x18004ad40  mov     r15, rdi
0x18004ad43  mov     rcx, [rsp+78h+HeapHandle]; HeapHandle
0x18004ad4b  xor     edx, edx; Flags
0x18004ad4d  mov     r8d, r13d; Size
0x18004ad50  call    cs:__imp_RtlAllocateHeap
0x18004ad56  mov     rsi, rax
0x18004ad59  test    rax, rax
0x18004ad5c  jnz     short loc_18004ADA8
0x18004ad5e  mov     ebx, 0C0000017h
0x18004ad63  mov     rcx, [rsp+78h+HeapHandle]; HeapHandle
0x18004ad6b  mov     r8, rbp; P
0x18004ad6e  xor     edx, edx; Flags
0x18004ad70  call    cs:__imp_RtlFreeHeap
0x18004ad76  test    rsi, rsi
0x18004ad79  jz      short loc_18004AD8E
0x18004ad7b  mov     rcx, [rsp+78h+HeapHandle]; HeapHandle
0x18004ad83  mov     r8, rsi; P
0x18004ad86  xor     edx, edx; Flags
0x18004ad88  call    cs:__imp_RtlFreeHeap
0x18004ad8e  mov     eax, ebx
0x18004ad90  mov     rbx, [rsp+78h+arg_0]
0x18004ad98  add     rsp, 40h
0x18004ad9c  pop     r15
0x18004ad9e  pop     r14
0x18004ada0  pop     r13
0x18004ada2  pop     r12
0x18004ada4  pop     rdi
0x18004ada5  pop     rsi
0x18004ada6  pop     rbp
0x18004ada7  retn
0x18004ada8  mov     r13, [rsp+78h+Dacl]
0x18004adad  xor     r14d, r14d
0x18004adb0  cmp     r14d, 4
0x18004adb4  jnb     loc_18004AEB5
0x18004adba  mov     ebx, r14d
0x18004adbd  shl     rbx, 4
0x18004adc1  mov     rcx, [rbx+r12+8]
0x18004adc6  mov     rcx, [rcx]; Sid
0x18004adc9  call    cs:__imp_RtlLengthSid
0x18004adcf  movzx   edx, byte ptr [rbx+r12]
0x18004add4  mov     r8d, eax
0x18004add7  test    edx, edx
0x18004add9  jz      short loc_18004AE19
0x18004addb  sub     edx, 1
0x18004adde  jz      short loc_18004AE0C
0x18004ade0  cmp     edx, 1
0x18004ade3  jnz     loc_18004AEAB
0x18004ade9  lea     ecx, [rax+8]
0x18004adec  mov     [rsp+78h+Acl], r15
0x18004adf4  mov     rax, [rbx+r12+8]
0x18004adf9  mov     [rsp+78h+arg_8], ecx
0x18004ae00  mov     rdi, [rax]
0x18004ae03  mov     byte ptr [rsi], 2
0x18004ae06  mov     [rsi+2], cx
0x18004ae0a  jmp     short loc_18004AE3D
0x18004ae0c  mov     rax, [rbx+r12+8]
0x18004ae11  mov     rdi, [rax]
0x18004ae14  mov     byte ptr [rsi], 1
0x18004ae17  jmp     short loc_18004AE24
0x18004ae19  mov     rax, [rbx+r12+8]
0x18004ae1e  mov     rdi, [rax]
0x18004ae21  mov     byte ptr [rsi], 0
0x18004ae24  add     r8d, 8
0x18004ae28  mov     [rsp+78h+Acl], r13
0x18004ae30  mov     [rsi+2], r8w
0x18004ae35  mov     [rsp+78h+arg_8], r8d
0x18004ae3d  mov     al, [rbx+r12+2]
0x18004ae42  mov     rcx, rdi; Sid
0x18004ae45  or      al, [rbx+r12+1]
0x18004ae4a  mov     [rsi+1], al
0x18004ae4d  mov     eax, [rbx+r12+4]
0x18004ae52  mov     [rsi+4], eax
0x18004ae55  call    cs:__imp_RtlLengthSid
0x18004ae5b  mov     r8, rdi; SourceSid
0x18004ae5e  lea     rdx, [rsi+8]; DestinationSid
0x18004ae62  mov     ecx, eax; DestinationSidLength
0x18004ae64  call    cs:__imp_RtlCopySid
0x18004ae6a  mov     ebx, eax
0x18004ae6c  test    eax, eax
0x18004ae6e  js      loc_18004AD63
0x18004ae74  mov     eax, [rsp+78h+arg_8]
0x18004ae7b  mov     r9, rsi; AceList
0x18004ae7e  mov     rcx, [rsp+78h+Acl]; Acl
0x18004ae86  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x18004ae8a  mov     edx, 2; AceRevision
0x18004ae8f  mov     [rsp+78h+AceListLength], eax; AceListLength
0x18004ae93  call    cs:__imp_RtlAddAce
0x18004ae99  mov     ebx, eax
0x18004ae9b  test    eax, eax
0x18004ae9d  js      loc_18004AD63
0x18004aea3  inc     r14d
0x18004aea6  jmp     loc_18004ADB0
0x18004aeab  mov     ebx, 0C0000001h
0x18004aeb0  jmp     loc_18004AD63
0x18004aeb5  mov     edx, 1; Revision
0x18004aeba  mov     rcx, rbp; SecurityDescriptor
0x18004aebd  call    cs:__imp_RtlCreateSecurityDescriptor
0x18004aec3  mov     ebx, eax
0x18004aec5  test    eax, eax
0x18004aec7  js      loc_18004AD63
0x18004aecd  mov     rdi, [rsp+78h+Owner]
0x18004aed2  xor     r8d, r8d; OwnerDefaulted
0x18004aed5  mov     rdx, rdi; Owner
0x18004aed8  mov     rcx, rbp; SecurityDescriptor
0x18004aedb  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18004aee1  mov     ebx, eax
0x18004aee3  test    eax, eax
0x18004aee5  js      loc_18004AD63
0x18004aeeb  xor     r8d, r8d; GroupDefaulted
0x18004aeee  mov     rdx, rdi; Group
0x18004aef1  mov     rcx, rbp; SecurityDescriptor
0x18004aef4  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x18004aefa  mov     ebx, eax
0x18004aefc  test    eax, eax
0x18004aefe  js      loc_18004AD63
0x18004af04  mov     rax, r13
0x18004af07  mov     rcx, rbp; SecurityDescriptor
0x18004af0a  test    rax, rax
0x18004af0d  mov     r8, rax; Dacl
0x18004af10  setnz   dl; DaclPresent
0x18004af13  xor     r9d, r9d; DaclDefaulted
0x18004af16  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18004af1c  mov     ebx, eax
0x18004af1e  test    eax, eax
0x18004af20  js      loc_18004AD63
0x18004af26  test    r15, r15
0x18004af29  mov     r8, r15; Sacl
0x18004af2c  mov     rcx, rbp; SecurityDescriptor
0x18004af2f  setnz   dl; SaclPresent
0x18004af32  xor     r9d, r9d; SaclDefaulted
0x18004af35  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x18004af3b  mov     ebx, eax
0x18004af3d  test    eax, eax
0x18004af3f  js      loc_18004AD63
0x18004af45  xor     ebx, ebx
0x18004af47  mov     rax, [rsp+78h+arg_20]
0x18004af4f  mov     [rax], rbp
0x18004af52  jmp     loc_18004AD7B
```
