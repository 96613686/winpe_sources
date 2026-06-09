# NetpCreateSecurityDescriptor

- ea: `0x18002ffa0`
- end: `0x1800302db`
- name: `NetpCreateSecurityDescriptor`
- size: `827`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800302e4`

## callees

- `0x18002ffa0`
- `0x1800305fc`
- `0x18003061c`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800301d3`
- `ntdll!RtlCopySid` at `0x1800301d3`
- `ntdll!RtlLengthSid` at `0x18002ffe6`
- `ntdll!RtlLengthSid` at `0x18003013a`
- `ntdll!RtlLengthSid` at `0x1800301be`
- `ntdll!RtlLengthSid` at `0x18002ffe6`
- `ntdll!RtlLengthSid` at `0x18003013a`
- `ntdll!RtlLengthSid` at `0x1800301be`
- `ntdll!RtlCreateAcl` at `0x180030074`
- `ntdll!RtlCreateAcl` at `0x1800300ad`
- `ntdll!RtlCreateAcl` at `0x180030074`
- `ntdll!RtlCreateAcl` at `0x1800300ad`
- `ntdll!RtlAddAce` at `0x18003020a`
- `ntdll!RtlAddAce` at `0x18003020a`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180030235`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180030235`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180030253`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180030253`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180030271`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180030271`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180030292`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180030292`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1800302b3`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1800302b3`

## pseudocode

```c
__int64 __fastcall NetpCreateSecurityDescriptor(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, struct _ACL **a5)
{
  ULONG v5; // r13d
  __int64 v6; // rdi
  ULONG v7; // r14d
  unsigned int v8; // esi
  unsigned int i; // eax
  ULONG v11; // eax
  ULONG v12; // eax
  unsigned int v14; // eax
  __int64 v15; // rcx
  struct _ACL *v16; // rax
  struct _ACL *v17; // rbp
  NTSTATUS SecurityDescriptor; // ebx
  char *v19; // rsi
  struct _ACL *v20; // r15
  struct _ACL *v21; // rdi
  unsigned int j; // r13d
  __int64 v23; // r14
  ULONG AceListLength; // r8d
  void *v25; // rdi
  ULONG v26; // eax
  NTSTATUS v27; // eax
  struct _ACL *v28; // [rsp+30h] [rbp-48h]
  struct _ACL *Acl; // [rsp+90h] [rbp+18h]
  ULONG v31; // [rsp+98h] [rbp+20h]

  v5 = 0;
  v6 = 8;
  v7 = 8;
  v8 = 0;
  for ( i = a2; v8 < i; i = a2 )
  {
    v11 = RtlLengthSid(**(PSID **)(a1 + 16LL * v8 + 8));
    if ( !*(_BYTE *)(a1 + 16LL * v8) || *(_BYTE *)(a1 + 16LL * v8) == 1 )
    {
      v12 = v11 + 8;
      v6 = v12 + (unsigned int)v6;
    }
    else
    {
      if ( *(_BYTE *)(a1 + 16LL * v8) != 2 )
        return 3221225485LL;
      v12 = v11 + 8;
      v7 += v12;
    }
    ++v8;
    if ( v5 > v12 )
      v12 = v5;
    v5 = v12;
  }
  v14 = v6 + 40;
  if ( (_DWORD)v6 == 8 )
    v14 = 40;
  v15 = v14 + v7;
  if ( v7 == 8 )
    v15 = v14;
  v16 = (struct _ACL *)NetpMemoryAllocate(v15);
  v17 = v16;
  if ( !v16 )
    return (unsigned int)-1073741801;
  v19 = 0;
  v20 = v16 + 5;
  if ( (_DWORD)v6 == 8 )
  {
    v21 = v16 + 5;
    SecurityDescriptor = -1073741811;
    v20 = 0;
  }
  else
  {
    SecurityDescriptor = RtlCreateAcl(v16 + 5, v6, 2u);
    if ( SecurityDescriptor < 0 )
      goto LABEL_28;
    v21 = (struct _ACL *)((char *)v20 + v6);
  }
  v28 = 0;
  if ( v7 == 8 )
  {
    v21 = 0;
  }
  else
  {
    SecurityDescriptor = RtlCreateAcl(v21, v7, 2u);
    if ( SecurityDescriptor < 0 )
      goto LABEL_28;
    v28 = v21;
  }
  v19 = (char *)NetpMemoryAllocate(v5);
  if ( !v19 )
  {
    SecurityDescriptor = -1073741801;
    goto LABEL_28;
  }
  for ( j = 0; j < a2; ++j )
  {
    v23 = 16LL * j;
    Acl = 0;
    AceListLength = RtlLengthSid(**(PSID **)(v23 + a1 + 8));
    switch ( *(_BYTE *)(v23 + a1) )
    {
      case 0:
        v25 = **(void ***)(v23 + a1 + 8);
        *v19 = 0;
        goto LABEL_39;
      case 1:
        v25 = **(void ***)(v23 + a1 + 8);
        *v19 = 1;
LABEL_39:
        Acl = v20;
        goto LABEL_40;
      case 2:
        Acl = v21;
        v25 = **(void ***)(v23 + a1 + 8);
        *v19 = 2;
LABEL_40:
        v19[1] = *(_BYTE *)(v23 + a1 + 1) | *(_BYTE *)(v23 + a1 + 2);
        *((_DWORD *)v19 + 1) = *(_DWORD *)(v23 + a1 + 4);
        v31 = AceListLength + 8;
        *((_WORD *)v19 + 1) = AceListLength + 8;
        v26 = RtlLengthSid(v25);
        v27 = RtlCopySid(v26, v19 + 8, v25);
        AceListLength = v31;
        SecurityDescriptor = v27;
        break;
    }
    if ( SecurityDescriptor < 0 )
      goto LABEL_28;
    SecurityDescriptor = RtlAddAce(Acl, 2u, 0xFFFFFFFF, v19, AceListLength);
    if ( SecurityDescriptor < 0 )
      goto LABEL_28;
    v21 = v28;
  }
  SecurityDescriptor = RtlCreateSecurityDescriptor(v17, 1u);
  if ( SecurityDescriptor < 0
    || (SecurityDescriptor = RtlSetOwnerSecurityDescriptor(v17, 0, 0), SecurityDescriptor < 0)
    || (SecurityDescriptor = RtlSetGroupSecurityDescriptor(v17, 0, 0), SecurityDescriptor < 0)
    || (SecurityDescriptor = RtlSetDaclSecurityDescriptor(v17, 1u, v20, 0), SecurityDescriptor < 0)
    || (SecurityDescriptor = RtlSetSaclSecurityDescriptor(v17, 0, v21, 0), SecurityDescriptor < 0) )
  {
LABEL_28:
    NetpMemoryFree(v17);
    if ( v19 )
      goto LABEL_29;
    return (unsigned int)SecurityDescriptor;
  }
  SecurityDescriptor = 0;
  *a5 = v17;
LABEL_29:
  NetpMemoryFree(v19);
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x18002ffa0  mov     rax, rsp
0x18002ffa3  mov     [rax+8], rbx
0x18002ffa7  mov     [rax+20h], r9
0x18002ffab  mov     [rax+18h], r8
0x18002ffaf  mov     [rax+10h], edx
0x18002ffb2  push    rbp
0x18002ffb3  push    rsi
0x18002ffb4  push    rdi
0x18002ffb5  push    r12
0x18002ffb7  push    r13
0x18002ffb9  push    r14
0x18002ffbb  push    r15
0x18002ffbd  sub     rsp, 40h
0x18002ffc1  mov     ebp, 8
0x18002ffc6  xor     r13d, r13d
0x18002ffc9  mov     edi, ebp
0x18002ffcb  mov     r14d, ebp
0x18002ffce  xor     esi, esi
0x18002ffd0  mov     eax, edx
0x18002ffd2  mov     r12, rcx
0x18002ffd5  cmp     esi, eax
0x18002ffd7  jnb     short loc_180030032
0x18002ffd9  mov     ebx, esi
0x18002ffdb  add     rbx, rbx
0x18002ffde  mov     rcx, [r12+rbx*8+8]
0x18002ffe3  mov     rcx, [rcx]; Sid
0x18002ffe6  call    cs:__imp_RtlLengthSid
0x18002ffed  nop     dword ptr [rax+rax+00h]
0x18002fff2  movzx   edx, byte ptr [r12+rbx*8]
0x18002fff7  test    edx, edx
0x18002fff9  jz      short loc_18003000F
0x18002fffb  sub     edx, 1
0x18002fffe  jz      short loc_18003000F
0x180030000  cmp     edx, 1
0x180030003  jnz     short loc_180030028
0x180030005  lea     ecx, [rax+8]
0x180030008  mov     eax, ecx
0x18003000a  add     r14d, ecx
0x18003000d  jmp     short loc_180030013
0x18003000f  add     eax, ebp
0x180030011  add     edi, eax
0x180030013  inc     esi
0x180030015  cmp     r13d, eax
0x180030018  cmova   eax, r13d
0x18003001c  mov     r13d, eax
0x18003001f  mov     eax, [rsp+78h+arg_8]
0x180030026  jmp     short loc_18002FFD5
0x180030028  mov     eax, 0C000000Dh
0x18003002d  jmp     loc_1800300F5
0x180030032  mov     ecx, 28h ; '('
0x180030037  lea     eax, [rdi+28h]
0x18003003a  cmp     edi, ebp
0x18003003c  cmovz   eax, ecx
0x18003003f  cmp     r14d, ebp
0x180030042  lea     ecx, [rax+r14]
0x180030046  cmovz   ecx, eax
0x180030049  call    NetpMemoryAllocate
0x18003004e  mov     rbp, rax
0x180030051  test    rax, rax
0x180030054  jnz     short loc_180030060
0x180030056  mov     ebx, 0C0000017h
0x18003005b  jmp     loc_1800300F3
0x180030060  xor     esi, esi
0x180030062  lea     r15, [rax+28h]
0x180030066  cmp     edi, 8
0x180030069  jz      short loc_18003008B
0x18003006b  lea     r8d, [rsi+2]; AclRevision
0x18003006f  mov     edx, edi; AclSize
0x180030071  mov     rcx, r15; Acl
0x180030074  call    cs:__imp_RtlCreateAcl
0x18003007b  nop     dword ptr [rax+rax+00h]
0x180030080  mov     ebx, eax
0x180030082  test    eax, eax
0x180030084  js      short loc_1800300DE
0x180030086  add     rdi, r15
0x180030089  jmp     short loc_180030096
0x18003008b  mov     rdi, r15
0x18003008e  mov     ebx, 0C000000Dh
0x180030093  xor     r15d, r15d
0x180030096  mov     [rsp+78h+var_48], rsi
0x18003009b  cmp     r14d, 8
0x18003009f  jz      short loc_1800300C6
0x1800300a1  mov     r8d, 2; AclRevision
0x1800300a7  mov     edx, r14d; AclSize
0x1800300aa  mov     rcx, rdi; Acl
0x1800300ad  call    cs:__imp_RtlCreateAcl
0x1800300b4  nop     dword ptr [rax+rax+00h]
0x1800300b9  mov     ebx, eax
0x1800300bb  test    eax, eax
0x1800300bd  js      short loc_1800300DE
0x1800300bf  mov     [rsp+78h+var_48], rdi
0x1800300c4  jmp     short loc_1800300C9
0x1800300c6  mov     rdi, rsi
0x1800300c9  mov     ecx, r13d
0x1800300cc  call    NetpMemoryAllocate
0x1800300d1  mov     rsi, rax
0x1800300d4  test    rax, rax
0x1800300d7  jnz     short loc_18003010E
0x1800300d9  mov     ebx, 0C0000017h
0x1800300de  mov     rcx, rbp
0x1800300e1  call    NetpMemoryFree
0x1800300e6  test    rsi, rsi
0x1800300e9  jz      short loc_1800300F3
0x1800300eb  mov     rcx, rsi
0x1800300ee  call    NetpMemoryFree
0x1800300f3  mov     eax, ebx
0x1800300f5  mov     rbx, [rsp+78h+arg_0]
0x1800300fd  add     rsp, 40h
0x180030101  pop     r15
0x180030103  pop     r14
0x180030105  pop     r13
0x180030107  pop     r12
0x180030109  pop     rdi
0x18003010a  pop     rsi
0x18003010b  pop     rbp
0x18003010c  retn
0x18003010e  xor     r13d, r13d
0x180030111  cmp     r13d, [rsp+78h+arg_8]
0x180030119  jnb     loc_18003022D
0x18003011f  mov     r14d, r13d
0x180030122  shl     r14, 4
0x180030126  mov     [rsp+78h+Acl], 0
0x180030132  mov     rcx, [r14+r12+8]
0x180030137  mov     rcx, [rcx]; Sid
0x18003013a  call    cs:__imp_RtlLengthSid
0x180030141  nop     dword ptr [rax+rax+00h]
0x180030146  movzx   edx, byte ptr [r14+r12]
0x18003014b  mov     r8d, eax
0x18003014e  test    edx, edx
0x180030150  jz      short loc_180030182
0x180030152  sub     edx, 1
0x180030155  jz      short loc_180030175
0x180030157  cmp     edx, 1
0x18003015a  jnz     loc_1800301E9
0x180030160  mov     rax, [r14+r12+8]
0x180030165  mov     [rsp+78h+Acl], rdi
0x18003016d  mov     rdi, [rax]
0x180030170  mov     byte ptr [rsi], 2
0x180030173  jmp     short loc_180030195
0x180030175  mov     rax, [r14+r12+8]
0x18003017a  mov     rdi, [rax]
0x18003017d  mov     byte ptr [rsi], 1
0x180030180  jmp     short loc_18003018D
0x180030182  mov     rax, [r14+r12+8]
0x180030187  mov     rdi, [rax]
0x18003018a  mov     byte ptr [rsi], 0
0x18003018d  mov     [rsp+78h+Acl], r15
0x180030195  mov     al, [r14+r12+2]
0x18003019a  add     r8d, 8
0x18003019e  or      al, [r14+r12+1]
0x1800301a3  mov     rcx, rdi; Sid
0x1800301a6  mov     [rsi+1], al
0x1800301a9  mov     eax, [r14+r12+4]
0x1800301ae  mov     [rsi+4], eax
0x1800301b1  mov     [rsp+78h+arg_18], r8d
0x1800301b9  mov     [rsi+2], r8w
0x1800301be  call    cs:__imp_RtlLengthSid
0x1800301c5  nop     dword ptr [rax+rax+00h]
0x1800301ca  mov     r8, rdi; SourceSid
0x1800301cd  lea     rdx, [rsi+8]; DestinationSid
0x1800301d1  mov     ecx, eax; DestinationSidLength
0x1800301d3  call    cs:__imp_RtlCopySid
0x1800301da  nop     dword ptr [rax+rax+00h]
0x1800301df  mov     r8d, [rsp+78h+arg_18]
0x1800301e7  mov     ebx, eax
0x1800301e9  test    ebx, ebx
0x1800301eb  js      loc_1800300DE
0x1800301f1  mov     rcx, [rsp+78h+Acl]; Acl
0x1800301f9  mov     r9, rsi; AceList
0x1800301fc  mov     [rsp+78h+AceListLength], r8d; AceListLength
0x180030201  mov     edx, 2; AceRevision
0x180030206  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x18003020a  call    cs:__imp_RtlAddAce
0x180030211  nop     dword ptr [rax+rax+00h]
0x180030216  mov     ebx, eax
0x180030218  test    eax, eax
0x18003021a  js      loc_1800300DE
0x180030220  mov     rdi, [rsp+78h+var_48]
0x180030225  inc     r13d
0x180030228  jmp     loc_180030111
0x18003022d  mov     edx, 1; Revision
0x180030232  mov     rcx, rbp; SecurityDescriptor
0x180030235  call    cs:__imp_RtlCreateSecurityDescriptor
0x18003023c  nop     dword ptr [rax+rax+00h]
0x180030241  mov     ebx, eax
0x180030243  test    eax, eax
0x180030245  js      loc_1800300DE
0x18003024b  xor     r8d, r8d; OwnerDefaulted
0x18003024e  xor     edx, edx; Owner
0x180030250  mov     rcx, rbp; SecurityDescriptor
0x180030253  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18003025a  nop     dword ptr [rax+rax+00h]
0x18003025f  mov     ebx, eax
0x180030261  test    eax, eax
0x180030263  js      loc_1800300DE
0x180030269  xor     r8d, r8d; GroupDefaulted
0x18003026c  xor     edx, edx; Group
0x18003026e  mov     rcx, rbp; SecurityDescriptor
0x180030271  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x180030278  nop     dword ptr [rax+rax+00h]
0x18003027d  mov     ebx, eax
0x18003027f  test    eax, eax
0x180030281  js      loc_1800300DE
0x180030287  xor     r9d, r9d; DaclDefaulted
0x18003028a  mov     r8, r15; Dacl
0x18003028d  mov     dl, 1; DaclPresent
0x18003028f  mov     rcx, rbp; SecurityDescriptor
0x180030292  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180030299  nop     dword ptr [rax+rax+00h]
0x18003029e  mov     ebx, eax
0x1800302a0  test    eax, eax
0x1800302a2  js      loc_1800300DE
0x1800302a8  xor     r9d, r9d; SaclDefaulted
0x1800302ab  mov     r8, rdi; Sacl
0x1800302ae  xor     edx, edx; SaclPresent
0x1800302b0  mov     rcx, rbp; SecurityDescriptor
0x1800302b3  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x1800302ba  nop     dword ptr [rax+rax+00h]
0x1800302bf  mov     ebx, eax
0x1800302c1  test    eax, eax
0x1800302c3  js      loc_1800300DE
0x1800302c9  xor     ebx, ebx
0x1800302cb  mov     rax, [rsp+78h+arg_20]
0x1800302d3  mov     [rax], rbp
0x1800302d6  jmp     loc_1800300EB
```
