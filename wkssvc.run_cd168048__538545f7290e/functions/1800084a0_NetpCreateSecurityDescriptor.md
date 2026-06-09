# NetpCreateSecurityDescriptor

- ea: `0x1800084a0`
- end: `0x1800087f6`
- name: `NetpCreateSecurityDescriptor`
- size: `854`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007ecc`
- `0x1800092cc`

## callees

- `0x180007cb0`
- `0x180007cd4`
- `0x1800084a0`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800086e8`
- `ntdll!RtlCopySid` at `0x1800086e8`
- `ntdll!RtlLengthSid` at `0x1800084e6`
- `ntdll!RtlLengthSid` at `0x180008637`
- `ntdll!RtlLengthSid` at `0x1800086d3`
- `ntdll!RtlLengthSid` at `0x1800084e6`
- `ntdll!RtlLengthSid` at `0x180008637`
- `ntdll!RtlLengthSid` at `0x1800086d3`
- `ntdll!RtlCreateAcl` at `0x180008575`
- `ntdll!RtlCreateAcl` at `0x1800085ae`
- `ntdll!RtlCreateAcl` at `0x180008575`
- `ntdll!RtlCreateAcl` at `0x1800085ae`
- `ntdll!RtlAddAce` at `0x180008719`
- `ntdll!RtlAddAce` at `0x180008719`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180008744`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180008744`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180008768`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180008768`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18000878c`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18000878c`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800087ad`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800087ad`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1800087ce`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1800087ce`

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
0x1800084a0  mov     rax, rsp
0x1800084a3  mov     [rax+8], rbx
0x1800084a7  mov     [rax+20h], r9
0x1800084ab  mov     [rax+18h], r8
0x1800084af  mov     [rax+10h], edx
0x1800084b2  push    rbp
0x1800084b3  push    rsi
0x1800084b4  push    rdi
0x1800084b5  push    r12
0x1800084b7  push    r13
0x1800084b9  push    r14
0x1800084bb  push    r15
0x1800084bd  sub     rsp, 50h
0x1800084c1  mov     ebp, 8
0x1800084c6  xor     r12d, r12d
0x1800084c9  mov     edi, ebp
0x1800084cb  mov     r14d, ebp
0x1800084ce  xor     esi, esi
0x1800084d0  mov     eax, edx
0x1800084d2  mov     r13, rcx
0x1800084d5  cmp     esi, eax
0x1800084d7  jnb     short loc_180008533
0x1800084d9  mov     ebx, esi
0x1800084db  add     rbx, rbx
0x1800084de  mov     rcx, [r13+rbx*8+8]
0x1800084e3  mov     rcx, [rcx]; Sid
0x1800084e6  call    cs:__imp_RtlLengthSid
0x1800084ed  nop     dword ptr [rax+rax+00h]
0x1800084f2  movzx   edx, byte ptr [r13+rbx*8+0]
0x1800084f8  test    edx, edx
0x1800084fa  jz      short loc_180008510
0x1800084fc  sub     edx, 1
0x1800084ff  jz      short loc_180008510
0x180008501  cmp     edx, 1
0x180008504  jnz     short loc_180008529
0x180008506  lea     ecx, [rax+8]
0x180008509  mov     eax, ecx
0x18000850b  add     r14d, ecx
0x18000850e  jmp     short loc_180008514
0x180008510  add     eax, ebp
0x180008512  add     edi, eax
0x180008514  inc     esi
0x180008516  cmp     r12d, eax
0x180008519  cmova   eax, r12d
0x18000851d  mov     r12d, eax
0x180008520  mov     eax, [rsp+88h+arg_8]
0x180008527  jmp     short loc_1800084D5
0x180008529  mov     eax, 0C000000Dh
0x18000852e  jmp     loc_1800085F6
0x180008533  mov     ecx, 28h ; '('
0x180008538  lea     eax, [rdi+28h]
0x18000853b  cmp     edi, ebp
0x18000853d  cmovz   eax, ecx
0x180008540  cmp     r14d, ebp
0x180008543  lea     ecx, [rax+r14]
0x180008547  cmovz   ecx, eax
0x18000854a  call    NetpMemoryAllocate
0x18000854f  mov     rbp, rax
0x180008552  test    rax, rax
0x180008555  jnz     short loc_180008561
0x180008557  mov     ebx, 0C0000017h
0x18000855c  jmp     loc_1800085F4
0x180008561  xor     esi, esi
0x180008563  lea     r15, [rax+28h]
0x180008567  cmp     edi, 8
0x18000856a  jz      short loc_18000858C
0x18000856c  lea     r8d, [rsi+2]; AclRevision
0x180008570  mov     edx, edi; AclSize
0x180008572  mov     rcx, r15; Acl
0x180008575  call    cs:__imp_RtlCreateAcl
0x18000857c  nop     dword ptr [rax+rax+00h]
0x180008581  mov     ebx, eax
0x180008583  test    eax, eax
0x180008585  js      short loc_1800085DF
0x180008587  add     rdi, r15
0x18000858a  jmp     short loc_180008597
0x18000858c  mov     rdi, r15
0x18000858f  mov     ebx, 0C000000Dh
0x180008594  xor     r15d, r15d
0x180008597  mov     [rsp+88h+var_48], rsi
0x18000859c  cmp     r14d, 8
0x1800085a0  jz      short loc_1800085C7
0x1800085a2  mov     r8d, 2; AclRevision
0x1800085a8  mov     edx, r14d; AclSize
0x1800085ab  mov     rcx, rdi; Acl
0x1800085ae  call    cs:__imp_RtlCreateAcl
0x1800085b5  nop     dword ptr [rax+rax+00h]
0x1800085ba  mov     ebx, eax
0x1800085bc  test    eax, eax
0x1800085be  js      short loc_1800085DF
0x1800085c0  mov     [rsp+88h+var_48], rdi
0x1800085c5  jmp     short loc_1800085CA
0x1800085c7  mov     rdi, rsi
0x1800085ca  mov     ecx, r12d
0x1800085cd  call    NetpMemoryAllocate
0x1800085d2  mov     rsi, rax
0x1800085d5  test    rax, rax
0x1800085d8  jnz     short loc_18000860F
0x1800085da  mov     ebx, 0C0000017h
0x1800085df  mov     rcx, rbp
0x1800085e2  call    NetpMemoryFree
0x1800085e7  test    rsi, rsi
0x1800085ea  jz      short loc_1800085F4
0x1800085ec  mov     rcx, rsi
0x1800085ef  call    NetpMemoryFree
0x1800085f4  mov     eax, ebx
0x1800085f6  mov     rbx, [rsp+88h+arg_0]
0x1800085fe  add     rsp, 50h
0x180008602  pop     r15
0x180008604  pop     r14
0x180008606  pop     r13
0x180008608  pop     r12
0x18000860a  pop     rdi
0x18000860b  pop     rsi
0x18000860c  pop     rbp
0x18000860d  retn
0x18000860f  xor     r12d, r12d
0x180008612  cmp     r12d, [rsp+88h+arg_8]
0x18000861a  jnb     loc_18000873C
0x180008620  mov     r14d, r12d
0x180008623  add     r14, r14
0x180008626  mov     [rsp+88h+Acl], 0
0x18000862f  mov     rcx, [r13+r14*8+8]
0x180008634  mov     rcx, [rcx]; Sid
0x180008637  call    cs:__imp_RtlLengthSid
0x18000863e  nop     dword ptr [rax+rax+00h]
0x180008643  movzx   edx, byte ptr [r13+r14*8+0]
0x180008649  mov     r8d, eax
0x18000864c  test    edx, edx
0x18000864e  jz      short loc_18000869B
0x180008650  sub     edx, 1
0x180008653  jz      short loc_18000867F
0x180008655  cmp     edx, 1
0x180008658  jnz     loc_1800086FB
0x18000865e  mov     rax, [r13+r14*8+8]
0x180008663  mov     edx, [r13+r14*8+4]
0x180008668  mov     cl, [r13+r14*8+1]
0x18000866d  mov     [rsp+88h+Acl], rdi
0x180008672  mov     rdi, [rax]
0x180008675  mov     al, [r13+r14*8+2]
0x18000867a  mov     byte ptr [rsi], 2
0x18000867d  jmp     short loc_1800086BA
0x18000867f  mov     rax, [r13+r14*8+8]
0x180008684  mov     edx, [r13+r14*8+4]
0x180008689  mov     cl, [r13+r14*8+1]
0x18000868e  mov     rdi, [rax]
0x180008691  mov     al, [r13+r14*8+2]
0x180008696  mov     byte ptr [rsi], 1
0x180008699  jmp     short loc_1800086B5
0x18000869b  mov     rax, [r13+r14*8+8]
0x1800086a0  mov     edx, [r13+r14*8+4]
0x1800086a5  mov     cl, [r13+r14*8+1]
0x1800086aa  mov     rdi, [rax]
0x1800086ad  mov     al, [r13+r14*8+2]
0x1800086b2  mov     byte ptr [rsi], 0
0x1800086b5  mov     [rsp+88h+Acl], r15
0x1800086ba  or      cl, al
0x1800086bc  mov     [rsi+4], edx
0x1800086bf  add     r8d, 8
0x1800086c3  mov     [rsi+1], cl
0x1800086c6  mov     rcx, rdi; Sid
0x1800086c9  mov     [rsp+88h+var_58], r8d
0x1800086ce  mov     [rsi+2], r8w
0x1800086d3  call    cs:__imp_RtlLengthSid
0x1800086da  nop     dword ptr [rax+rax+00h]
0x1800086df  mov     r8, rdi; SourceSid
0x1800086e2  lea     rdx, [rsi+8]; DestinationSid
0x1800086e6  mov     ecx, eax; DestinationSidLength
0x1800086e8  call    cs:__imp_RtlCopySid
0x1800086ef  nop     dword ptr [rax+rax+00h]
0x1800086f4  mov     r8d, [rsp+88h+var_58]
0x1800086f9  mov     ebx, eax
0x1800086fb  test    ebx, ebx
0x1800086fd  js      loc_1800085DF
0x180008703  mov     rcx, [rsp+88h+Acl]; Acl
0x180008708  mov     r9, rsi; AceList
0x18000870b  mov     [rsp+88h+AceListLength], r8d; AceListLength
0x180008710  mov     edx, 2; AceRevision
0x180008715  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x180008719  call    cs:__imp_RtlAddAce
0x180008720  nop     dword ptr [rax+rax+00h]
0x180008725  mov     ebx, eax
0x180008727  test    eax, eax
0x180008729  js      loc_1800085DF
0x18000872f  mov     rdi, [rsp+88h+var_48]
0x180008734  inc     r12d
0x180008737  jmp     loc_180008612
0x18000873c  mov     edx, 1; Revision
0x180008741  mov     rcx, rbp; SecurityDescriptor
0x180008744  call    cs:__imp_RtlCreateSecurityDescriptor
0x18000874b  nop     dword ptr [rax+rax+00h]
0x180008750  mov     ebx, eax
0x180008752  test    eax, eax
0x180008754  js      loc_1800085DF
0x18000875a  mov     rdx, [rsp+88h+Owner]; Owner
0x180008762  xor     r8d, r8d; OwnerDefaulted
0x180008765  mov     rcx, rbp; SecurityDescriptor
0x180008768  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18000876f  nop     dword ptr [rax+rax+00h]
0x180008774  mov     ebx, eax
0x180008776  test    eax, eax
0x180008778  js      loc_1800085DF
0x18000877e  mov     rdx, [rsp+88h+Group]; Group
0x180008786  xor     r8d, r8d; GroupDefaulted
0x180008789  mov     rcx, rbp; SecurityDescriptor
0x18000878c  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x180008793  nop     dword ptr [rax+rax+00h]
0x180008798  mov     ebx, eax
0x18000879a  test    eax, eax
0x18000879c  js      loc_1800085DF
0x1800087a2  xor     r9d, r9d; DaclDefaulted
0x1800087a5  mov     r8, r15; Dacl
0x1800087a8  mov     dl, 1; DaclPresent
0x1800087aa  mov     rcx, rbp; SecurityDescriptor
0x1800087ad  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1800087b4  nop     dword ptr [rax+rax+00h]
0x1800087b9  mov     ebx, eax
0x1800087bb  test    eax, eax
0x1800087bd  js      loc_1800085DF
0x1800087c3  xor     r9d, r9d; SaclDefaulted
0x1800087c6  mov     r8, rdi; Sacl
0x1800087c9  xor     edx, edx; SaclPresent
0x1800087cb  mov     rcx, rbp; SecurityDescriptor
0x1800087ce  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x1800087d5  nop     dword ptr [rax+rax+00h]
0x1800087da  mov     ebx, eax
0x1800087dc  test    eax, eax
0x1800087de  js      loc_1800085DF
0x1800087e4  xor     ebx, ebx
0x1800087e6  mov     rax, [rsp+88h+arg_20]
0x1800087ee  mov     [rax], rbp
0x1800087f1  jmp     loc_1800085EC
```
