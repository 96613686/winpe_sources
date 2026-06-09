# NetpCreateSecurityDescriptor

- ea: `0x180007f60`
- end: `0x18000826d`
- name: `NetpCreateSecurityDescriptor`
- size: `781`
- prototype: `__int64 __fastcall(__int64, unsigned int, void *, void *, struct _ACL **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800079c4`
- `0x180008bfc`

## callees

- `0x180007604`
- `0x180007710`
- `0x180007f60`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180008189`
- `ntdll!RtlCopySid` at `0x180008189`
- `ntdll!RtlLengthSid` at `0x180007fa6`
- `ntdll!RtlLengthSid` at `0x1800080e4`
- `ntdll!RtlLengthSid` at `0x18000817a`
- `ntdll!RtlLengthSid` at `0x180007fa6`
- `ntdll!RtlLengthSid` at `0x1800080e4`
- `ntdll!RtlLengthSid` at `0x18000817a`
- `ntdll!RtlCreateAcl` at `0x18000802f`
- `ntdll!RtlCreateAcl` at `0x180008062`
- `ntdll!RtlCreateAcl` at `0x18000802f`
- `ntdll!RtlCreateAcl` at `0x180008062`
- `ntdll!RtlAddAce` at `0x1800081b4`
- `ntdll!RtlAddAce` at `0x1800081b4`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800081d9`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800081d9`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800081f7`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800081f7`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180008215`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180008215`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180008230`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180008230`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18000824b`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18000824b`

## pseudocode

```c
__int64 __fastcall NetpCreateSecurityDescriptor(__int64 a1, unsigned int a2, void *a3, void *a4, struct _ACL **a5)
{
  ULONG v5; // r12d
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
  _DWORD *v19; // rsi
  struct _ACL *v20; // r15
  struct _ACL *v21; // rdi
  unsigned int j; // r12d
  ULONG AceListLength; // r8d
  int v24; // edx
  char v25; // cl
  void *v26; // rdi
  char v27; // al
  ULONG v28; // eax
  NTSTATUS v29; // eax
  ULONG v30; // [rsp+30h] [rbp-58h]
  struct _ACL *Acl; // [rsp+38h] [rbp-50h]
  struct _ACL *v32; // [rsp+40h] [rbp-48h]

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
  v32 = 0;
  if ( v7 == 8 )
  {
    v21 = 0;
  }
  else
  {
    SecurityDescriptor = RtlCreateAcl(v21, v7, 2u);
    if ( SecurityDescriptor < 0 )
      goto LABEL_28;
    v32 = v21;
  }
  v19 = (_DWORD *)NetpMemoryAllocate(v5);
  if ( !v19 )
  {
    SecurityDescriptor = -1073741801;
    goto LABEL_28;
  }
  for ( j = 0; j < a2; ++j )
  {
    Acl = 0;
    AceListLength = RtlLengthSid(**(PSID **)(a1 + 16LL * j + 8));
    switch ( *(_BYTE *)(a1 + 16LL * j) )
    {
      case 0:
        v24 = *(_DWORD *)(a1 + 16LL * j + 4);
        v25 = *(_BYTE *)(a1 + 16LL * j + 1);
        v26 = **(void ***)(a1 + 16LL * j + 8);
        v27 = *(_BYTE *)(a1 + 16LL * j + 2);
        *(_BYTE *)v19 = 0;
        goto LABEL_39;
      case 1:
        v24 = *(_DWORD *)(a1 + 16LL * j + 4);
        v25 = *(_BYTE *)(a1 + 16LL * j + 1);
        v26 = **(void ***)(a1 + 16LL * j + 8);
        v27 = *(_BYTE *)(a1 + 16LL * j + 2);
        *(_BYTE *)v19 = 1;
LABEL_39:
        Acl = v20;
        goto LABEL_40;
      case 2:
        v24 = *(_DWORD *)(a1 + 16LL * j + 4);
        v25 = *(_BYTE *)(a1 + 16LL * j + 1);
        Acl = v21;
        v26 = **(void ***)(a1 + 16LL * j + 8);
        v27 = *(_BYTE *)(a1 + 16LL * j + 2);
        *(_BYTE *)v19 = 2;
LABEL_40:
        v19[1] = v24;
        *((_BYTE *)v19 + 1) = v27 | v25;
        v30 = AceListLength + 8;
        *((_WORD *)v19 + 1) = AceListLength + 8;
        v28 = RtlLengthSid(v26);
        v29 = RtlCopySid(v28, v19 + 2, v26);
        AceListLength = v30;
        SecurityDescriptor = v29;
        break;
    }
    if ( SecurityDescriptor < 0 )
      goto LABEL_28;
    SecurityDescriptor = RtlAddAce(Acl, 2u, 0xFFFFFFFF, v19, AceListLength);
    if ( SecurityDescriptor < 0 )
      goto LABEL_28;
    v21 = v32;
  }
  SecurityDescriptor = RtlCreateSecurityDescriptor(v17, 1u);
  if ( SecurityDescriptor < 0
    || (SecurityDescriptor = RtlSetOwnerSecurityDescriptor(v17, a3, 0), SecurityDescriptor < 0)
    || (SecurityDescriptor = RtlSetGroupSecurityDescriptor(v17, a4, 0), SecurityDescriptor < 0)
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
0x180007f60  mov     rax, rsp
0x180007f63  mov     [rax+8], rbx
0x180007f67  mov     [rax+20h], r9
0x180007f6b  mov     [rax+18h], r8
0x180007f6f  mov     [rax+10h], edx
0x180007f72  push    rbp
0x180007f73  push    rsi
0x180007f74  push    rdi
0x180007f75  push    r12
0x180007f77  push    r13
0x180007f79  push    r14
0x180007f7b  push    r15
0x180007f7d  sub     rsp, 50h
0x180007f81  mov     ebp, 8
0x180007f86  xor     r12d, r12d
0x180007f89  mov     edi, ebp
0x180007f8b  mov     r14d, ebp
0x180007f8e  xor     esi, esi
0x180007f90  mov     eax, edx
0x180007f92  mov     r13, rcx
0x180007f95  cmp     esi, eax
0x180007f97  jnb     short loc_180007FED
0x180007f99  mov     ebx, esi
0x180007f9b  add     rbx, rbx
0x180007f9e  mov     rcx, [r13+rbx*8+8]
0x180007fa3  mov     rcx, [rcx]; Sid
0x180007fa6  call    cs:__imp_RtlLengthSid
0x180007fac  movzx   edx, byte ptr [r13+rbx*8+0]
0x180007fb2  test    edx, edx
0x180007fb4  jz      short loc_180007FCA
0x180007fb6  sub     edx, 1
0x180007fb9  jz      short loc_180007FCA
0x180007fbb  cmp     edx, 1
0x180007fbe  jnz     short loc_180007FE3
0x180007fc0  lea     ecx, [rax+8]
0x180007fc3  mov     eax, ecx
0x180007fc5  add     r14d, ecx
0x180007fc8  jmp     short loc_180007FCE
0x180007fca  add     eax, ebp
0x180007fcc  add     edi, eax
0x180007fce  inc     esi
0x180007fd0  cmp     r12d, eax
0x180007fd3  cmova   eax, r12d
0x180007fd7  mov     r12d, eax
0x180007fda  mov     eax, [rsp+88h+arg_8]
0x180007fe1  jmp     short loc_180007F95
0x180007fe3  mov     eax, 0C000000Dh
0x180007fe8  jmp     loc_1800080A4
0x180007fed  mov     ecx, 28h ; '('
0x180007ff2  lea     eax, [rdi+28h]
0x180007ff5  cmp     edi, ebp
0x180007ff7  cmovz   eax, ecx
0x180007ffa  cmp     r14d, ebp
0x180007ffd  lea     ecx, [rax+r14]
0x180008001  cmovz   ecx, eax
0x180008004  call    NetpMemoryAllocate
0x180008009  mov     rbp, rax
0x18000800c  test    rax, rax
0x18000800f  jnz     short loc_18000801B
0x180008011  mov     ebx, 0C0000017h
0x180008016  jmp     loc_1800080A2
0x18000801b  xor     esi, esi
0x18000801d  lea     r15, [rax+28h]
0x180008021  cmp     edi, 8
0x180008024  jz      short loc_180008040
0x180008026  lea     r8d, [rsi+2]; AclRevision
0x18000802a  mov     edx, edi; AclSize
0x18000802c  mov     rcx, r15; Acl
0x18000802f  call    cs:__imp_RtlCreateAcl
0x180008035  mov     ebx, eax
0x180008037  test    eax, eax
0x180008039  js      short loc_18000808D
0x18000803b  add     rdi, r15
0x18000803e  jmp     short loc_18000804B
0x180008040  mov     rdi, r15
0x180008043  mov     ebx, 0C000000Dh
0x180008048  xor     r15d, r15d
0x18000804b  mov     [rsp+88h+var_48], rsi
0x180008050  cmp     r14d, 8
0x180008054  jz      short loc_180008075
0x180008056  mov     r8d, 2; AclRevision
0x18000805c  mov     edx, r14d; AclSize
0x18000805f  mov     rcx, rdi; Acl
0x180008062  call    cs:__imp_RtlCreateAcl
0x180008068  mov     ebx, eax
0x18000806a  test    eax, eax
0x18000806c  js      short loc_18000808D
0x18000806e  mov     [rsp+88h+var_48], rdi
0x180008073  jmp     short loc_180008078
0x180008075  mov     rdi, rsi
0x180008078  mov     ecx, r12d
0x18000807b  call    NetpMemoryAllocate
0x180008080  mov     rsi, rax
0x180008083  test    rax, rax
0x180008086  jnz     short loc_1800080BC
0x180008088  mov     ebx, 0C0000017h
0x18000808d  mov     rcx, rbp
0x180008090  call    NetpMemoryFree
0x180008095  test    rsi, rsi
0x180008098  jz      short loc_1800080A2
0x18000809a  mov     rcx, rsi
0x18000809d  call    NetpMemoryFree
0x1800080a2  mov     eax, ebx
0x1800080a4  mov     rbx, [rsp+88h+arg_0]
0x1800080ac  add     rsp, 50h
0x1800080b0  pop     r15
0x1800080b2  pop     r14
0x1800080b4  pop     r13
0x1800080b6  pop     r12
0x1800080b8  pop     rdi
0x1800080b9  pop     rsi
0x1800080ba  pop     rbp
0x1800080bb  retn
0x1800080bc  xor     r12d, r12d
0x1800080bf  cmp     r12d, [rsp+88h+arg_8]
0x1800080c7  jnb     loc_1800081D1
0x1800080cd  mov     r14d, r12d
0x1800080d0  add     r14, r14
0x1800080d3  mov     [rsp+88h+Acl], 0
0x1800080dc  mov     rcx, [r13+r14*8+8]
0x1800080e1  mov     rcx, [rcx]; Sid
0x1800080e4  call    cs:__imp_RtlLengthSid
0x1800080ea  movzx   edx, byte ptr [r13+r14*8+0]
0x1800080f0  mov     r8d, eax
0x1800080f3  test    edx, edx
0x1800080f5  jz      short loc_180008142
0x1800080f7  sub     edx, 1
0x1800080fa  jz      short loc_180008126
0x1800080fc  cmp     edx, 1
0x1800080ff  jnz     loc_180008196
0x180008105  mov     rax, [r13+r14*8+8]
0x18000810a  mov     edx, [r13+r14*8+4]
0x18000810f  mov     cl, [r13+r14*8+1]
0x180008114  mov     [rsp+88h+Acl], rdi
0x180008119  mov     rdi, [rax]
0x18000811c  mov     al, [r13+r14*8+2]
0x180008121  mov     byte ptr [rsi], 2
0x180008124  jmp     short loc_180008161
0x180008126  mov     rax, [r13+r14*8+8]
0x18000812b  mov     edx, [r13+r14*8+4]
0x180008130  mov     cl, [r13+r14*8+1]
0x180008135  mov     rdi, [rax]
0x180008138  mov     al, [r13+r14*8+2]
0x18000813d  mov     byte ptr [rsi], 1
0x180008140  jmp     short loc_18000815C
0x180008142  mov     rax, [r13+r14*8+8]
0x180008147  mov     edx, [r13+r14*8+4]
0x18000814c  mov     cl, [r13+r14*8+1]
0x180008151  mov     rdi, [rax]
0x180008154  mov     al, [r13+r14*8+2]
0x180008159  mov     byte ptr [rsi], 0
0x18000815c  mov     [rsp+88h+Acl], r15
0x180008161  or      cl, al
0x180008163  mov     [rsi+4], edx
0x180008166  add     r8d, 8
0x18000816a  mov     [rsi+1], cl
0x18000816d  mov     rcx, rdi; Sid
0x180008170  mov     [rsp+88h+var_58], r8d
0x180008175  mov     [rsi+2], r8w
0x18000817a  call    cs:__imp_RtlLengthSid
0x180008180  mov     r8, rdi; SourceSid
0x180008183  lea     rdx, [rsi+8]; DestinationSid
0x180008187  mov     ecx, eax; DestinationSidLength
0x180008189  call    cs:__imp_RtlCopySid
0x18000818f  mov     r8d, [rsp+88h+var_58]
0x180008194  mov     ebx, eax
0x180008196  test    ebx, ebx
0x180008198  js      loc_18000808D
0x18000819e  mov     rcx, [rsp+88h+Acl]; Acl
0x1800081a3  mov     r9, rsi; AceList
0x1800081a6  mov     [rsp+88h+AceListLength], r8d; AceListLength
0x1800081ab  mov     edx, 2; AceRevision
0x1800081b0  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x1800081b4  call    cs:__imp_RtlAddAce
0x1800081ba  mov     ebx, eax
0x1800081bc  test    eax, eax
0x1800081be  js      loc_18000808D
0x1800081c4  mov     rdi, [rsp+88h+var_48]
0x1800081c9  inc     r12d
0x1800081cc  jmp     loc_1800080BF
0x1800081d1  mov     edx, 1; Revision
0x1800081d6  mov     rcx, rbp; SecurityDescriptor
0x1800081d9  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800081df  mov     ebx, eax
0x1800081e1  test    eax, eax
0x1800081e3  js      loc_18000808D
0x1800081e9  mov     rdx, [rsp+88h+Owner]; Owner
0x1800081f1  xor     r8d, r8d; OwnerDefaulted
0x1800081f4  mov     rcx, rbp; SecurityDescriptor
0x1800081f7  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1800081fd  mov     ebx, eax
0x1800081ff  test    eax, eax
0x180008201  js      loc_18000808D
0x180008207  mov     rdx, [rsp+88h+Group]; Group
0x18000820f  xor     r8d, r8d; GroupDefaulted
0x180008212  mov     rcx, rbp; SecurityDescriptor
0x180008215  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x18000821b  mov     ebx, eax
0x18000821d  test    eax, eax
0x18000821f  js      loc_18000808D
0x180008225  xor     r9d, r9d; DaclDefaulted
0x180008228  mov     r8, r15; Dacl
0x18000822b  mov     dl, 1; DaclPresent
0x18000822d  mov     rcx, rbp; SecurityDescriptor
0x180008230  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180008236  mov     ebx, eax
0x180008238  test    eax, eax
0x18000823a  js      loc_18000808D
0x180008240  xor     r9d, r9d; SaclDefaulted
0x180008243  mov     r8, rdi; Sacl
0x180008246  xor     edx, edx; SaclPresent
0x180008248  mov     rcx, rbp; SecurityDescriptor
0x18000824b  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x180008251  mov     ebx, eax
0x180008253  test    eax, eax
0x180008255  js      loc_18000808D
0x18000825b  xor     ebx, ebx
0x18000825d  mov     rax, [rsp+88h+arg_20]
0x180008265  mov     [rax], rbp
0x180008268  jmp     loc_18000809A
```
