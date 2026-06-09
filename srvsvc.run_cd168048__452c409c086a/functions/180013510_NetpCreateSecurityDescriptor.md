# NetpCreateSecurityDescriptor

- ea: `0x180013510`
- end: `0x18001381d`
- name: `NetpCreateSecurityDescriptor`
- size: `781`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001d9ac`

## callees

- `0x180013510`
- `0x1800427d8`
- `0x1800427f0`

## import_xrefs

- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800137e0`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800137e0`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800137a7`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800137a7`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180013789`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180013789`
- `ntdll!RtlCopySid` at `0x180013739`
- `ntdll!RtlCopySid` at `0x180013739`
- `ntdll!RtlLengthSid` at `0x180013556`
- `ntdll!RtlLengthSid` at `0x180013694`
- `ntdll!RtlLengthSid` at `0x18001372a`
- `ntdll!RtlLengthSid` at `0x180013556`
- `ntdll!RtlLengthSid` at `0x180013694`
- `ntdll!RtlLengthSid` at `0x18001372a`
- `ntdll!RtlCreateAcl` at `0x1800135df`
- `ntdll!RtlCreateAcl` at `0x180013612`
- `ntdll!RtlCreateAcl` at `0x1800135df`
- `ntdll!RtlCreateAcl` at `0x180013612`
- `ntdll!RtlAddAce` at `0x180013764`
- `ntdll!RtlAddAce` at `0x180013764`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1800137fb`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1800137fb`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x1800137c5`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x1800137c5`

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
0x180013510  mov     rax, rsp
0x180013513  mov     [rax+8], rbx
0x180013517  mov     [rax+20h], r9
0x18001351b  mov     [rax+18h], r8
0x18001351f  mov     [rax+10h], edx
0x180013522  push    rbp
0x180013523  push    rsi
0x180013524  push    rdi
0x180013525  push    r12
0x180013527  push    r13
0x180013529  push    r14
0x18001352b  push    r15
0x18001352d  sub     rsp, 50h
0x180013531  mov     ebp, 8
0x180013536  xor     r12d, r12d
0x180013539  mov     edi, ebp
0x18001353b  mov     r14d, ebp
0x18001353e  xor     esi, esi
0x180013540  mov     eax, edx
0x180013542  mov     r13, rcx
0x180013545  cmp     esi, eax
0x180013547  jnb     short loc_18001359D
0x180013549  mov     ebx, esi
0x18001354b  add     rbx, rbx
0x18001354e  mov     rcx, [r13+rbx*8+8]
0x180013553  mov     rcx, [rcx]; Sid
0x180013556  call    cs:__imp_RtlLengthSid
0x18001355c  movzx   edx, byte ptr [r13+rbx*8+0]
0x180013562  test    edx, edx
0x180013564  jz      short loc_18001357A
0x180013566  sub     edx, 1
0x180013569  jz      short loc_18001357A
0x18001356b  cmp     edx, 1
0x18001356e  jnz     short loc_180013593
0x180013570  lea     ecx, [rax+8]
0x180013573  mov     eax, ecx
0x180013575  add     r14d, ecx
0x180013578  jmp     short loc_18001357E
0x18001357a  add     eax, ebp
0x18001357c  add     edi, eax
0x18001357e  inc     esi
0x180013580  cmp     r12d, eax
0x180013583  cmova   eax, r12d
0x180013587  mov     r12d, eax
0x18001358a  mov     eax, [rsp+88h+arg_8]
0x180013591  jmp     short loc_180013545
0x180013593  mov     eax, 0C000000Dh
0x180013598  jmp     loc_180013654
0x18001359d  mov     ecx, 28h ; '('
0x1800135a2  lea     eax, [rdi+28h]
0x1800135a5  cmp     edi, ebp
0x1800135a7  cmovz   eax, ecx
0x1800135aa  cmp     r14d, ebp
0x1800135ad  lea     ecx, [rax+r14]
0x1800135b1  cmovz   ecx, eax
0x1800135b4  call    NetpMemoryAllocate
0x1800135b9  mov     rbp, rax
0x1800135bc  test    rax, rax
0x1800135bf  jnz     short loc_1800135CB
0x1800135c1  mov     ebx, 0C0000017h
0x1800135c6  jmp     loc_180013652
0x1800135cb  xor     esi, esi
0x1800135cd  lea     r15, [rax+28h]
0x1800135d1  cmp     edi, 8
0x1800135d4  jz      short loc_1800135F0
0x1800135d6  lea     r8d, [rsi+2]; AclRevision
0x1800135da  mov     edx, edi; AclSize
0x1800135dc  mov     rcx, r15; Acl
0x1800135df  call    cs:__imp_RtlCreateAcl
0x1800135e5  mov     ebx, eax
0x1800135e7  test    eax, eax
0x1800135e9  js      short loc_18001363D
0x1800135eb  add     rdi, r15
0x1800135ee  jmp     short loc_1800135FB
0x1800135f0  mov     rdi, r15
0x1800135f3  mov     ebx, 0C000000Dh
0x1800135f8  xor     r15d, r15d
0x1800135fb  mov     [rsp+88h+var_48], rsi
0x180013600  cmp     r14d, 8
0x180013604  jz      short loc_180013625
0x180013606  mov     r8d, 2; AclRevision
0x18001360c  mov     edx, r14d; AclSize
0x18001360f  mov     rcx, rdi; Acl
0x180013612  call    cs:__imp_RtlCreateAcl
0x180013618  mov     ebx, eax
0x18001361a  test    eax, eax
0x18001361c  js      short loc_18001363D
0x18001361e  mov     [rsp+88h+var_48], rdi
0x180013623  jmp     short loc_180013628
0x180013625  mov     rdi, rsi
0x180013628  mov     ecx, r12d
0x18001362b  call    NetpMemoryAllocate
0x180013630  mov     rsi, rax
0x180013633  test    rax, rax
0x180013636  jnz     short loc_18001366C
0x180013638  mov     ebx, 0C0000017h
0x18001363d  mov     rcx, rbp
0x180013640  call    NetpMemoryFree
0x180013645  test    rsi, rsi
0x180013648  jz      short loc_180013652
0x18001364a  mov     rcx, rsi
0x18001364d  call    NetpMemoryFree
0x180013652  mov     eax, ebx
0x180013654  mov     rbx, [rsp+88h+arg_0]
0x18001365c  add     rsp, 50h
0x180013660  pop     r15
0x180013662  pop     r14
0x180013664  pop     r13
0x180013666  pop     r12
0x180013668  pop     rdi
0x180013669  pop     rsi
0x18001366a  pop     rbp
0x18001366b  retn
0x18001366c  xor     r12d, r12d
0x18001366f  cmp     r12d, [rsp+88h+arg_8]
0x180013677  jnb     loc_180013781
0x18001367d  mov     r14d, r12d
0x180013680  add     r14, r14
0x180013683  mov     [rsp+88h+Acl], 0
0x18001368c  mov     rcx, [r13+r14*8+8]
0x180013691  mov     rcx, [rcx]; Sid
0x180013694  call    cs:__imp_RtlLengthSid
0x18001369a  movzx   edx, byte ptr [r13+r14*8+0]
0x1800136a0  mov     r8d, eax
0x1800136a3  test    edx, edx
0x1800136a5  jz      short loc_1800136F2
0x1800136a7  sub     edx, 1
0x1800136aa  jz      short loc_1800136D6
0x1800136ac  cmp     edx, 1
0x1800136af  jnz     loc_180013746
0x1800136b5  mov     rax, [r13+r14*8+8]
0x1800136ba  mov     edx, [r13+r14*8+4]
0x1800136bf  mov     cl, [r13+r14*8+1]
0x1800136c4  mov     [rsp+88h+Acl], rdi
0x1800136c9  mov     rdi, [rax]
0x1800136cc  mov     al, [r13+r14*8+2]
0x1800136d1  mov     byte ptr [rsi], 2
0x1800136d4  jmp     short loc_180013711
0x1800136d6  mov     rax, [r13+r14*8+8]
0x1800136db  mov     edx, [r13+r14*8+4]
0x1800136e0  mov     cl, [r13+r14*8+1]
0x1800136e5  mov     rdi, [rax]
0x1800136e8  mov     al, [r13+r14*8+2]
0x1800136ed  mov     byte ptr [rsi], 1
0x1800136f0  jmp     short loc_18001370C
0x1800136f2  mov     rax, [r13+r14*8+8]
0x1800136f7  mov     edx, [r13+r14*8+4]
0x1800136fc  mov     cl, [r13+r14*8+1]
0x180013701  mov     rdi, [rax]
0x180013704  mov     al, [r13+r14*8+2]
0x180013709  mov     byte ptr [rsi], 0
0x18001370c  mov     [rsp+88h+Acl], r15
0x180013711  or      cl, al
0x180013713  mov     [rsi+4], edx
0x180013716  add     r8d, 8
0x18001371a  mov     [rsi+1], cl
0x18001371d  mov     rcx, rdi; Sid
0x180013720  mov     [rsp+88h+var_58], r8d
0x180013725  mov     [rsi+2], r8w
0x18001372a  call    cs:__imp_RtlLengthSid
0x180013730  mov     r8, rdi; SourceSid
0x180013733  lea     rdx, [rsi+8]; DestinationSid
0x180013737  mov     ecx, eax; DestinationSidLength
0x180013739  call    cs:__imp_RtlCopySid
0x18001373f  mov     r8d, [rsp+88h+var_58]
0x180013744  mov     ebx, eax
0x180013746  test    ebx, ebx
0x180013748  js      loc_18001363D
0x18001374e  mov     rcx, [rsp+88h+Acl]; Acl
0x180013753  mov     r9, rsi; AceList
0x180013756  mov     [rsp+88h+AceListLength], r8d; AceListLength
0x18001375b  mov     edx, 2; AceRevision
0x180013760  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x180013764  call    cs:__imp_RtlAddAce
0x18001376a  mov     ebx, eax
0x18001376c  test    eax, eax
0x18001376e  js      loc_18001363D
0x180013774  mov     rdi, [rsp+88h+var_48]
0x180013779  inc     r12d
0x18001377c  jmp     loc_18001366F
0x180013781  mov     edx, 1; Revision
0x180013786  mov     rcx, rbp; SecurityDescriptor
0x180013789  call    cs:__imp_RtlCreateSecurityDescriptor
0x18001378f  mov     ebx, eax
0x180013791  test    eax, eax
0x180013793  js      loc_18001363D
0x180013799  mov     rdx, [rsp+88h+Owner]; Owner
0x1800137a1  xor     r8d, r8d; OwnerDefaulted
0x1800137a4  mov     rcx, rbp; SecurityDescriptor
0x1800137a7  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1800137ad  mov     ebx, eax
0x1800137af  test    eax, eax
0x1800137b1  js      loc_18001363D
0x1800137b7  mov     rdx, [rsp+88h+Group]; Group
0x1800137bf  xor     r8d, r8d; GroupDefaulted
0x1800137c2  mov     rcx, rbp; SecurityDescriptor
0x1800137c5  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x1800137cb  mov     ebx, eax
0x1800137cd  test    eax, eax
0x1800137cf  js      loc_18001363D
0x1800137d5  xor     r9d, r9d; DaclDefaulted
0x1800137d8  mov     r8, r15; Dacl
0x1800137db  mov     dl, 1; DaclPresent
0x1800137dd  mov     rcx, rbp; SecurityDescriptor
0x1800137e0  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1800137e6  mov     ebx, eax
0x1800137e8  test    eax, eax
0x1800137ea  js      loc_18001363D
0x1800137f0  xor     r9d, r9d; SaclDefaulted
0x1800137f3  mov     r8, rdi; Sacl
0x1800137f6  xor     edx, edx; SaclPresent
0x1800137f8  mov     rcx, rbp; SecurityDescriptor
0x1800137fb  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x180013801  mov     ebx, eax
0x180013803  test    eax, eax
0x180013805  js      loc_18001363D
0x18001380b  xor     ebx, ebx
0x18001380d  mov     rax, [rsp+88h+arg_20]
0x180013815  mov     [rax], rbp
0x180013818  jmp     loc_18001364A
```
