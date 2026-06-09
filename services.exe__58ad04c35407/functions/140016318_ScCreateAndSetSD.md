# ScCreateAndSetSD

- ea: `0x140016318`
- end: `0x14001665b`
- name: `ScCreateAndSetSD`
- size: `835`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001457c`
- `0x14001462c`
- `0x1400154dc`
- `0x14001562c`
- `0x140015ba4`
- `0x140016220`
- `0x140031df8`
- `0x14003ae4c`
- `0x14006e990`
- `0x140078efc`
- `0x140078fb4`
- `0x140079d10`
- `0x14007be28`

## callees

- `0x140016318`

## import_xrefs

- `ntdll!RtlCreateSecurityDescriptor` at `0x1400164ec`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1400164ec`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x140016506`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x140016506`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x140016520`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x140016520`
- `ntdll!RtlCreateAcl` at `0x1400163e3`
- `ntdll!RtlCreateAcl` at `0x1400165f5`
- `ntdll!RtlCreateAcl` at `0x1400163e3`
- `ntdll!RtlCreateAcl` at `0x1400165f5`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x14001653e`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x14001653e`
- `ntdll!RtlLengthSid` at `0x14001636e`
- `ntdll!RtlLengthSid` at `0x140016449`
- `ntdll!RtlLengthSid` at `0x140016494`
- `ntdll!RtlLengthSid` at `0x14001636e`
- `ntdll!RtlLengthSid` at `0x140016449`
- `ntdll!RtlLengthSid` at `0x140016494`
- `ntdll!RtlCopySid` at `0x1400164a3`
- `ntdll!RtlCopySid` at `0x1400164a3`
- `ntdll!RtlFreeHeap` at `0x14001657e`
- `ntdll!RtlFreeHeap` at `0x140016593`
- `ntdll!RtlFreeHeap` at `0x14001657e`
- `ntdll!RtlFreeHeap` at `0x140016593`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x140016559`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x140016559`
- `ntdll!RtlAddAce` at `0x1400164cc`
- `ntdll!RtlAddAce` at `0x1400164cc`
- `ntdll!RtlAllocateHeap` at `0x1400163b9`
- `ntdll!RtlAllocateHeap` at `0x140016412`
- `ntdll!RtlAllocateHeap` at `0x1400163b9`
- `ntdll!RtlAllocateHeap` at `0x140016412`

## pseudocode

```c
__int64 __fastcall ScCreateAndSetSD(__int64 a1, unsigned int a2, void *a3, void *a4, struct _ACL **a5)
{
  ULONG v5; // r13d
  __int64 v6; // rdi
  ULONG v8; // r14d
  unsigned int v9; // esi
  ULONG v10; // eax
  ULONG v11; // eax
  unsigned int v12; // ecx
  SIZE_T v13; // r8
  struct _ACL *Heap; // rax
  struct _ACL *v15; // rbp
  _WORD *v16; // rsi
  struct _ACL *v17; // r15
  NTSTATUS SecurityDescriptor; // ebx
  struct _ACL *v19; // rdi
  struct _ACL *v20; // r15
  unsigned int i; // r14d
  __int64 v22; // rbx
  ULONG v23; // eax
  int v24; // edx
  void *v25; // rdi
  ULONG v26; // eax
  int v28; // edx
  ULONG AceListLength; // [rsp+30h] [rbp-58h]
  PVOID HeapHandle; // [rsp+38h] [rbp-50h]
  struct _ACL *Acl; // [rsp+40h] [rbp-48h]
  struct _ACL *Dacl; // [rsp+48h] [rbp-40h]
  unsigned int v33; // [rsp+98h] [rbp+10h]

  v33 = a2;
  v5 = 0;
  v6 = 8;
  v8 = 8;
  v9 = 0;
  HeapHandle = NtCurrentPeb()->ProcessHeap;
  while ( v9 < a2 )
  {
    v10 = RtlLengthSid(**(PSID **)(a1 + 16LL * v9 + 8));
    if ( !*(_BYTE *)(a1 + 16LL * v9) || *(_BYTE *)(a1 + 16LL * v9) == 1 )
    {
      v11 = v10 + 8;
      v6 = v11 + (unsigned int)v6;
    }
    else
    {
      if ( *(_BYTE *)(a1 + 16LL * v9) != 2 )
        return 3221225485LL;
      v11 = v10 + 8;
      v8 += v11;
    }
    a2 = v33;
    ++v9;
    if ( v5 > v11 )
      v11 = v5;
    v5 = v11;
  }
  v12 = v6 + 40;
  if ( (_DWORD)v6 == 8 )
    v12 = 40;
  v13 = v12 + v8;
  if ( v8 == 8 )
    v13 = v12;
  Heap = (struct _ACL *)RtlAllocateHeap(HeapHandle, 0, v13);
  v15 = Heap;
  if ( !Heap )
    return (unsigned int)-1073741801;
  v16 = 0;
  v17 = Heap + 5;
  if ( (_DWORD)v6 == 8 )
  {
    Dacl = 0;
    v19 = Heap + 5;
  }
  else
  {
    SecurityDescriptor = RtlCreateAcl(Heap + 5, v6, 2u);
    if ( SecurityDescriptor < 0 )
      goto LABEL_32;
    Dacl = v17;
    v19 = (struct _ACL *)((char *)v17 + v6);
  }
  v20 = 0;
  if ( v8 != 8 )
  {
    SecurityDescriptor = RtlCreateAcl(v19, v8, 2u);
    if ( SecurityDescriptor < 0 )
      goto LABEL_32;
    v20 = v19;
  }
  v16 = RtlAllocateHeap(HeapHandle, 0, v5);
  if ( !v16 )
  {
    SecurityDescriptor = -1073741801;
    goto LABEL_32;
  }
  for ( i = 0; i < v33; ++i )
  {
    v22 = 16LL * i;
    v23 = RtlLengthSid(**(PSID **)(v22 + a1 + 8));
    v24 = *(unsigned __int8 *)(v22 + a1);
    if ( !*(_BYTE *)(v22 + a1) )
    {
      v25 = **(void ***)(v22 + a1 + 8);
      *(_BYTE *)v16 = v24;
LABEL_22:
      Acl = Dacl;
      v16[1] = v23 + 8;
      AceListLength = v23 + 8;
      goto LABEL_23;
    }
    v28 = v24 - 1;
    if ( !v28 )
    {
      v25 = **(void ***)(v22 + a1 + 8);
      *(_BYTE *)v16 = 1;
      goto LABEL_22;
    }
    if ( v28 != 1 )
    {
      SecurityDescriptor = -1073741823;
      goto LABEL_32;
    }
    Acl = v20;
    AceListLength = v23 + 8;
    v25 = **(void ***)(v22 + a1 + 8);
    *(_BYTE *)v16 = 2;
    v16[1] = v23 + 8;
LABEL_23:
    *((_BYTE *)v16 + 1) = *(_BYTE *)(v22 + a1 + 1) | *(_BYTE *)(v22 + a1 + 2);
    *((_DWORD *)v16 + 1) = *(_DWORD *)(v22 + a1 + 4);
    v26 = RtlLengthSid(v25);
    SecurityDescriptor = RtlCopySid(v26, v16 + 4, v25);
    if ( SecurityDescriptor < 0 )
      goto LABEL_32;
    SecurityDescriptor = RtlAddAce(Acl, 2u, 0xFFFFFFFF, v16, AceListLength);
    if ( SecurityDescriptor < 0 )
      goto LABEL_32;
  }
  SecurityDescriptor = RtlCreateSecurityDescriptor(v15, 1u);
  if ( SecurityDescriptor >= 0 )
  {
    SecurityDescriptor = RtlSetOwnerSecurityDescriptor(v15, a3, 0);
    if ( SecurityDescriptor >= 0 )
    {
      SecurityDescriptor = RtlSetGroupSecurityDescriptor(v15, a4, 0);
      if ( SecurityDescriptor >= 0 )
      {
        SecurityDescriptor = RtlSetDaclSecurityDescriptor(v15, Dacl != 0, Dacl, 0);
        if ( SecurityDescriptor >= 0 )
        {
          SecurityDescriptor = RtlSetSaclSecurityDescriptor(v15, v20 != 0, v20, 0);
          if ( SecurityDescriptor >= 0 )
          {
            SecurityDescriptor = 0;
            *a5 = v15;
            goto LABEL_33;
          }
        }
      }
    }
  }
LABEL_32:
  RtlFreeHeap(HeapHandle, 0, v15);
  if ( v16 )
LABEL_33:
    RtlFreeHeap(HeapHandle, 0, v16);
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x140016318  mov     rax, rsp
0x14001631b  mov     [rax+8], rbx
0x14001631f  mov     [rax+20h], r9
0x140016323  mov     [rax+18h], r8
0x140016327  mov     [rax+10h], edx
0x14001632a  push    rbp
0x14001632b  push    rsi
0x14001632c  push    rdi
0x14001632d  push    r12
0x14001632f  push    r13
0x140016331  push    r14
0x140016333  push    r15
0x140016335  sub     rsp, 50h
0x140016339  mov     rax, gs:60h
0x140016342  mov     ebp, 8
0x140016347  xor     r13d, r13d
0x14001634a  mov     edi, ebp
0x14001634c  mov     r12, rcx
0x14001634f  mov     r14d, ebp
0x140016352  xor     esi, esi
0x140016354  mov     r9, [rax+30h]
0x140016358  mov     [rsp+88h+HeapHandle], r9
0x14001635d  cmp     esi, edx
0x14001635f  jnb     short loc_14001639A
0x140016361  mov     ebx, esi
0x140016363  add     rbx, rbx
0x140016366  mov     rcx, [r12+rbx*8+8]
0x14001636b  mov     rcx, [rcx]; Sid
0x14001636e  call    cs:__imp_RtlLengthSid
0x140016374  movzx   edx, byte ptr [r12+rbx*8]
0x140016379  test    edx, edx
0x14001637b  jnz     loc_1400165B3
0x140016381  add     eax, ebp
0x140016383  add     edi, eax
0x140016385  mov     edx, [rsp+88h+arg_8]
0x14001638c  inc     esi
0x14001638e  cmp     r13d, eax
0x140016391  cmova   eax, r13d
0x140016395  mov     r13d, eax
0x140016398  jmp     short loc_14001635D
0x14001639a  cmp     edi, ebp
0x14001639c  lea     ecx, [rdi+28h]
0x14001639f  mov     eax, 28h ; '('
0x1400163a4  cmovz   ecx, eax
0x1400163a7  cmp     r14d, ebp
0x1400163aa  lea     r8d, [rcx+r14]
0x1400163ae  cmovz   r8d, ecx; Size
0x1400163b2  mov     rcx, [rsp+88h+HeapHandle]; HeapHandle
0x1400163b7  xor     edx, edx; Flags
0x1400163b9  call    cs:__imp_RtlAllocateHeap
0x1400163bf  mov     rbp, rax
0x1400163c2  test    rax, rax
0x1400163c5  jz      loc_1400165D5
0x1400163cb  xor     esi, esi
0x1400163cd  lea     r15, [rax+28h]
0x1400163d1  cmp     edi, 8
0x1400163d4  jz      loc_1400165DC
0x1400163da  lea     r8d, [rsi+2]; AclRevision
0x1400163de  mov     edx, edi; AclSize
0x1400163e0  mov     rcx, r15; Acl
0x1400163e3  call    cs:__imp_RtlCreateAcl
0x1400163e9  mov     ebx, eax
0x1400163eb  test    eax, eax
0x1400163ed  js      loc_140016574
0x1400163f3  mov     [rsp+88h+Dacl], r15
0x1400163f8  add     rdi, r15
0x1400163fb  xor     r15d, r15d
0x1400163fe  cmp     r14d, 8
0x140016402  jnz     loc_1400165E9
0x140016408  mov     rcx, [rsp+88h+HeapHandle]; HeapHandle
0x14001640d  xor     edx, edx; Flags
0x14001640f  mov     r8d, r13d; Size
0x140016412  call    cs:__imp_RtlAllocateHeap
0x140016418  mov     rsi, rax
0x14001641b  test    rax, rax
0x14001641e  jz      loc_14001660D
0x140016424  mov     r13, [rsp+88h+Dacl]
0x140016429  xor     r14d, r14d
0x14001642c  cmp     r14d, [rsp+88h+arg_8]
0x140016434  jnb     loc_1400164E4
0x14001643a  mov     ebx, r14d
0x14001643d  shl     rbx, 4
0x140016441  mov     rcx, [rbx+r12+8]
0x140016446  mov     rcx, [rcx]; Sid
0x140016449  call    cs:__imp_RtlLengthSid
0x14001644f  movzx   edx, byte ptr [rbx+r12]
0x140016454  mov     r8d, eax
0x140016457  test    edx, edx
0x140016459  jnz     loc_140016617
0x14001645f  mov     rax, [rbx+r12+8]
0x140016464  mov     rdi, [rax]
0x140016467  mov     [rsi], dl
0x140016469  add     r8d, 8
0x14001646d  mov     [rsp+88h+Acl], r13
0x140016472  mov     [rsi+2], r8w
0x140016477  mov     [rsp+88h+var_58], r8d
0x14001647c  mov     al, [rbx+r12+2]
0x140016481  mov     rcx, rdi; Sid
0x140016484  or      al, [rbx+r12+1]
0x140016489  mov     [rsi+1], al
0x14001648c  mov     eax, [rbx+r12+4]
0x140016491  mov     [rsi+4], eax
0x140016494  call    cs:__imp_RtlLengthSid
0x14001649a  mov     r8, rdi; SourceSid
0x14001649d  lea     rdx, [rsi+8]; DestinationSid
0x1400164a1  mov     ecx, eax; DestinationSidLength
0x1400164a3  call    cs:__imp_RtlCopySid
0x1400164a9  mov     ebx, eax
0x1400164ab  test    eax, eax
0x1400164ad  js      loc_140016574
0x1400164b3  mov     eax, [rsp+88h+var_58]
0x1400164b7  mov     r9, rsi; AceList
0x1400164ba  mov     rcx, [rsp+88h+Acl]; Acl
0x1400164bf  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x1400164c3  mov     edx, 2; AceRevision
0x1400164c8  mov     [rsp+88h+AceListLength], eax; AceListLength
0x1400164cc  call    cs:__imp_RtlAddAce
0x1400164d2  mov     ebx, eax
0x1400164d4  test    eax, eax
0x1400164d6  js      loc_140016574
0x1400164dc  inc     r14d
0x1400164df  jmp     loc_14001642C
0x1400164e4  mov     edx, 1; Revision
0x1400164e9  mov     rcx, rbp; SecurityDescriptor
0x1400164ec  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400164f2  mov     ebx, eax
0x1400164f4  test    eax, eax
0x1400164f6  js      short loc_140016574
0x1400164f8  mov     rdx, [rsp+88h+Owner]; Owner
0x140016500  xor     r8d, r8d; OwnerDefaulted
0x140016503  mov     rcx, rbp; SecurityDescriptor
0x140016506  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14001650c  mov     ebx, eax
0x14001650e  test    eax, eax
0x140016510  js      short loc_140016574
0x140016512  mov     rdx, [rsp+88h+Group]; Group
0x14001651a  xor     r8d, r8d; GroupDefaulted
0x14001651d  mov     rcx, rbp; SecurityDescriptor
0x140016520  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x140016526  mov     ebx, eax
0x140016528  test    eax, eax
0x14001652a  js      short loc_140016574
0x14001652c  mov     rax, r13
0x14001652f  mov     rcx, rbp; SecurityDescriptor
0x140016532  test    rax, rax
0x140016535  mov     r8, rax; Dacl
0x140016538  setnz   dl; DaclPresent
0x14001653b  xor     r9d, r9d; DaclDefaulted
0x14001653e  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140016544  mov     ebx, eax
0x140016546  test    eax, eax
0x140016548  js      short loc_140016574
0x14001654a  test    r15, r15
0x14001654d  mov     r8, r15; Sacl
0x140016550  mov     rcx, rbp; SecurityDescriptor
0x140016553  setnz   dl; SaclPresent
0x140016556  xor     r9d, r9d; SaclDefaulted
0x140016559  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x14001655f  mov     ebx, eax
0x140016561  test    eax, eax
0x140016563  js      short loc_140016574
0x140016565  xor     ebx, ebx
0x140016567  mov     rax, [rsp+88h+arg_20]
0x14001656f  mov     [rax], rbp
0x140016572  jmp     short loc_140016589
0x140016574  mov     rcx, [rsp+88h+HeapHandle]; HeapHandle
0x140016579  mov     r8, rbp; P
0x14001657c  xor     edx, edx; Flags
0x14001657e  call    cs:__imp_RtlFreeHeap
0x140016584  test    rsi, rsi
0x140016587  jz      short loc_140016599
0x140016589  mov     rcx, [rsp+88h+HeapHandle]; HeapHandle
0x14001658e  mov     r8, rsi; P
0x140016591  xor     edx, edx; Flags
0x140016593  call    cs:__imp_RtlFreeHeap
0x140016599  mov     eax, ebx
0x14001659b  mov     rbx, [rsp+88h+arg_0]
0x1400165a3  add     rsp, 50h
0x1400165a7  pop     r15
0x1400165a9  pop     r14
0x1400165ab  pop     r13
0x1400165ad  pop     r12
0x1400165af  pop     rdi
0x1400165b0  pop     rsi
0x1400165b1  pop     rbp
0x1400165b2  retn
0x1400165b3  sub     edx, 1
0x1400165b6  jz      loc_140016381
0x1400165bc  cmp     edx, 1
0x1400165bf  jz      short loc_1400165C8
0x1400165c1  mov     eax, 0C000000Dh
0x1400165c6  jmp     short loc_14001659B
0x1400165c8  lea     ecx, [rax+8]
0x1400165cb  mov     eax, ecx
0x1400165cd  add     r14d, ecx
0x1400165d0  jmp     loc_140016385
0x1400165d5  mov     ebx, 0C0000017h
0x1400165da  jmp     short loc_140016599
0x1400165dc  mov     [rsp+88h+Dacl], rsi
0x1400165e1  mov     rdi, r15
0x1400165e4  jmp     loc_1400163FB
0x1400165e9  mov     r8d, 2; AclRevision
0x1400165ef  mov     edx, r14d; AclSize
0x1400165f2  mov     rcx, rdi; Acl
0x1400165f5  call    cs:__imp_RtlCreateAcl
0x1400165fb  mov     ebx, eax
0x1400165fd  test    eax, eax
0x1400165ff  js      loc_140016574
0x140016605  mov     r15, rdi
0x140016608  jmp     loc_140016408
0x14001660d  mov     ebx, 0C0000017h
0x140016612  jmp     loc_140016574
0x140016617  sub     edx, 1
0x14001661a  jz      short loc_140016641
0x14001661c  cmp     edx, 1
0x14001661f  jnz     short loc_140016651
0x140016621  lea     ecx, [rax+8]
0x140016624  mov     [rsp+88h+Acl], r15
0x140016629  mov     rax, [rbx+r12+8]
0x14001662e  mov     [rsp+88h+var_58], ecx
0x140016632  mov     rdi, [rax]
0x140016635  mov     byte ptr [rsi], 2
0x140016638  mov     [rsi+2], cx
0x14001663c  jmp     loc_14001647C
0x140016641  mov     rax, [rbx+r12+8]
0x140016646  mov     rdi, [rax]
0x140016649  mov     byte ptr [rsi], 1
0x14001664c  jmp     loc_140016469
0x140016651  mov     ebx, 0C0000001h
0x140016656  jmp     loc_140016574
```
