# NetpCreateSecurityDescriptor

- ea: `0x18002def8`
- end: `0x18002e1e6`
- name: `NetpCreateSecurityDescriptor`
- size: `750`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, struct _ACL **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002e1ec`

## callees

- `0x18002def8`
- `0x18002e4bc`
- `0x18002e4d4`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18002e108`
- `ntdll!RtlCopySid` at `0x18002e108`
- `ntdll!RtlLengthSid` at `0x18002df3e`
- `ntdll!RtlLengthSid` at `0x18002e07f`
- `ntdll!RtlLengthSid` at `0x18002e0f9`
- `ntdll!RtlLengthSid` at `0x18002df3e`
- `ntdll!RtlLengthSid` at `0x18002e07f`
- `ntdll!RtlLengthSid` at `0x18002e0f9`
- `ntdll!RtlCreateAcl` at `0x18002dfc6`
- `ntdll!RtlCreateAcl` at `0x18002dff9`
- `ntdll!RtlCreateAcl` at `0x18002dfc6`
- `ntdll!RtlCreateAcl` at `0x18002dff9`
- `ntdll!RtlAddAce` at `0x18002e139`
- `ntdll!RtlAddAce` at `0x18002e139`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18002e15e`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18002e15e`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18002e176`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18002e176`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18002e18e`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18002e18e`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18002e1a9`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18002e1a9`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18002e1c4`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18002e1c4`

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
0x18002def8  mov     rax, rsp
0x18002defb  mov     [rax+8], rbx
0x18002deff  mov     [rax+20h], r9
0x18002df03  mov     [rax+18h], r8
0x18002df07  mov     [rax+10h], edx
0x18002df0a  push    rbp
0x18002df0b  push    rsi
0x18002df0c  push    rdi
0x18002df0d  push    r12
0x18002df0f  push    r13
0x18002df11  push    r14
0x18002df13  push    r15
0x18002df15  sub     rsp, 40h
0x18002df19  mov     ebp, 8
0x18002df1e  xor     r13d, r13d
0x18002df21  mov     edi, ebp
0x18002df23  mov     r14d, ebp
0x18002df26  xor     esi, esi
0x18002df28  mov     eax, edx
0x18002df2a  mov     r12, rcx
0x18002df2d  cmp     esi, eax
0x18002df2f  jnb     short loc_18002DF84
0x18002df31  mov     ebx, esi
0x18002df33  add     rbx, rbx
0x18002df36  mov     rcx, [r12+rbx*8+8]
0x18002df3b  mov     rcx, [rcx]; Sid
0x18002df3e  call    cs:__imp_RtlLengthSid
0x18002df44  movzx   edx, byte ptr [r12+rbx*8]
0x18002df49  test    edx, edx
0x18002df4b  jz      short loc_18002DF61
0x18002df4d  sub     edx, 1
0x18002df50  jz      short loc_18002DF61
0x18002df52  cmp     edx, 1
0x18002df55  jnz     short loc_18002DF7A
0x18002df57  lea     ecx, [rax+8]
0x18002df5a  mov     eax, ecx
0x18002df5c  add     r14d, ecx
0x18002df5f  jmp     short loc_18002DF65
0x18002df61  add     eax, ebp
0x18002df63  add     edi, eax
0x18002df65  inc     esi
0x18002df67  cmp     r13d, eax
0x18002df6a  cmova   eax, r13d
0x18002df6e  mov     r13d, eax
0x18002df71  mov     eax, [rsp+78h+arg_8]
0x18002df78  jmp     short loc_18002DF2D
0x18002df7a  mov     eax, 0C000000Dh
0x18002df7f  jmp     loc_18002E03B
0x18002df84  mov     ecx, 28h ; '('
0x18002df89  lea     eax, [rdi+28h]
0x18002df8c  cmp     edi, ebp
0x18002df8e  cmovz   eax, ecx
0x18002df91  cmp     r14d, ebp
0x18002df94  lea     ecx, [rax+r14]
0x18002df98  cmovz   ecx, eax
0x18002df9b  call    NetpMemoryAllocate
0x18002dfa0  mov     rbp, rax
0x18002dfa3  test    rax, rax
0x18002dfa6  jnz     short loc_18002DFB2
0x18002dfa8  mov     ebx, 0C0000017h
0x18002dfad  jmp     loc_18002E039
0x18002dfb2  xor     esi, esi
0x18002dfb4  lea     r15, [rax+28h]
0x18002dfb8  cmp     edi, 8
0x18002dfbb  jz      short loc_18002DFD7
0x18002dfbd  lea     r8d, [rsi+2]; AclRevision
0x18002dfc1  mov     edx, edi; AclSize
0x18002dfc3  mov     rcx, r15; Acl
0x18002dfc6  call    cs:__imp_RtlCreateAcl
0x18002dfcc  mov     ebx, eax
0x18002dfce  test    eax, eax
0x18002dfd0  js      short loc_18002E024
0x18002dfd2  add     rdi, r15
0x18002dfd5  jmp     short loc_18002DFE2
0x18002dfd7  mov     rdi, r15
0x18002dfda  mov     ebx, 0C000000Dh
0x18002dfdf  xor     r15d, r15d
0x18002dfe2  mov     [rsp+78h+var_48], rsi
0x18002dfe7  cmp     r14d, 8
0x18002dfeb  jz      short loc_18002E00C
0x18002dfed  mov     r8d, 2; AclRevision
0x18002dff3  mov     edx, r14d; AclSize
0x18002dff6  mov     rcx, rdi; Acl
0x18002dff9  call    cs:__imp_RtlCreateAcl
0x18002dfff  mov     ebx, eax
0x18002e001  test    eax, eax
0x18002e003  js      short loc_18002E024
0x18002e005  mov     [rsp+78h+var_48], rdi
0x18002e00a  jmp     short loc_18002E00F
0x18002e00c  mov     rdi, rsi
0x18002e00f  mov     ecx, r13d
0x18002e012  call    NetpMemoryAllocate
0x18002e017  mov     rsi, rax
0x18002e01a  test    rax, rax
0x18002e01d  jnz     short loc_18002E053
0x18002e01f  mov     ebx, 0C0000017h
0x18002e024  mov     rcx, rbp
0x18002e027  call    NetpMemoryFree
0x18002e02c  test    rsi, rsi
0x18002e02f  jz      short loc_18002E039
0x18002e031  mov     rcx, rsi
0x18002e034  call    NetpMemoryFree
0x18002e039  mov     eax, ebx
0x18002e03b  mov     rbx, [rsp+78h+arg_0]
0x18002e043  add     rsp, 40h
0x18002e047  pop     r15
0x18002e049  pop     r14
0x18002e04b  pop     r13
0x18002e04d  pop     r12
0x18002e04f  pop     rdi
0x18002e050  pop     rsi
0x18002e051  pop     rbp
0x18002e052  retn
0x18002e053  xor     r13d, r13d
0x18002e056  cmp     r13d, [rsp+78h+arg_8]
0x18002e05e  jnb     loc_18002E156
0x18002e064  mov     r14d, r13d
0x18002e067  shl     r14, 4
0x18002e06b  mov     [rsp+78h+Acl], 0
0x18002e077  mov     rcx, [r14+r12+8]
0x18002e07c  mov     rcx, [rcx]; Sid
0x18002e07f  call    cs:__imp_RtlLengthSid
0x18002e085  movzx   edx, byte ptr [r14+r12]
0x18002e08a  mov     r8d, eax
0x18002e08d  test    edx, edx
0x18002e08f  jz      short loc_18002E0BD
0x18002e091  sub     edx, 1
0x18002e094  jz      short loc_18002E0B0
0x18002e096  cmp     edx, 1
0x18002e099  jnz     short loc_18002E118
0x18002e09b  mov     rax, [r14+r12+8]
0x18002e0a0  mov     [rsp+78h+Acl], rdi
0x18002e0a8  mov     rdi, [rax]
0x18002e0ab  mov     byte ptr [rsi], 2
0x18002e0ae  jmp     short loc_18002E0D0
0x18002e0b0  mov     rax, [r14+r12+8]
0x18002e0b5  mov     rdi, [rax]
0x18002e0b8  mov     byte ptr [rsi], 1
0x18002e0bb  jmp     short loc_18002E0C8
0x18002e0bd  mov     rax, [r14+r12+8]
0x18002e0c2  mov     rdi, [rax]
0x18002e0c5  mov     byte ptr [rsi], 0
0x18002e0c8  mov     [rsp+78h+Acl], r15
0x18002e0d0  mov     al, [r14+r12+2]
0x18002e0d5  add     r8d, 8
0x18002e0d9  or      al, [r14+r12+1]
0x18002e0de  mov     rcx, rdi; Sid
0x18002e0e1  mov     [rsi+1], al
0x18002e0e4  mov     eax, [r14+r12+4]
0x18002e0e9  mov     [rsi+4], eax
0x18002e0ec  mov     [rsp+78h+arg_18], r8d
0x18002e0f4  mov     [rsi+2], r8w
0x18002e0f9  call    cs:__imp_RtlLengthSid
0x18002e0ff  mov     r8, rdi; SourceSid
0x18002e102  lea     rdx, [rsi+8]; DestinationSid
0x18002e106  mov     ecx, eax; DestinationSidLength
0x18002e108  call    cs:__imp_RtlCopySid
0x18002e10e  mov     r8d, [rsp+78h+arg_18]
0x18002e116  mov     ebx, eax
0x18002e118  test    ebx, ebx
0x18002e11a  js      loc_18002E024
0x18002e120  mov     rcx, [rsp+78h+Acl]; Acl
0x18002e128  mov     r9, rsi; AceList
0x18002e12b  mov     [rsp+78h+AceListLength], r8d; AceListLength
0x18002e130  mov     edx, 2; AceRevision
0x18002e135  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x18002e139  call    cs:__imp_RtlAddAce
0x18002e13f  mov     ebx, eax
0x18002e141  test    eax, eax
0x18002e143  js      loc_18002E024
0x18002e149  mov     rdi, [rsp+78h+var_48]
0x18002e14e  inc     r13d
0x18002e151  jmp     loc_18002E056
0x18002e156  mov     edx, 1; Revision
0x18002e15b  mov     rcx, rbp; SecurityDescriptor
0x18002e15e  call    cs:__imp_RtlCreateSecurityDescriptor
0x18002e164  mov     ebx, eax
0x18002e166  test    eax, eax
0x18002e168  js      loc_18002E024
0x18002e16e  xor     r8d, r8d; OwnerDefaulted
0x18002e171  xor     edx, edx; Owner
0x18002e173  mov     rcx, rbp; SecurityDescriptor
0x18002e176  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18002e17c  mov     ebx, eax
0x18002e17e  test    eax, eax
0x18002e180  js      loc_18002E024
0x18002e186  xor     r8d, r8d; GroupDefaulted
0x18002e189  xor     edx, edx; Group
0x18002e18b  mov     rcx, rbp; SecurityDescriptor
0x18002e18e  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x18002e194  mov     ebx, eax
0x18002e196  test    eax, eax
0x18002e198  js      loc_18002E024
0x18002e19e  xor     r9d, r9d; DaclDefaulted
0x18002e1a1  mov     r8, r15; Dacl
0x18002e1a4  mov     dl, 1; DaclPresent
0x18002e1a6  mov     rcx, rbp; SecurityDescriptor
0x18002e1a9  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18002e1af  mov     ebx, eax
0x18002e1b1  test    eax, eax
0x18002e1b3  js      loc_18002E024
0x18002e1b9  xor     r9d, r9d; SaclDefaulted
0x18002e1bc  mov     r8, rdi; Sacl
0x18002e1bf  xor     edx, edx; SaclPresent
0x18002e1c1  mov     rcx, rbp; SecurityDescriptor
0x18002e1c4  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x18002e1ca  mov     ebx, eax
0x18002e1cc  test    eax, eax
0x18002e1ce  js      loc_18002E024
0x18002e1d4  xor     ebx, ebx
0x18002e1d6  mov     rax, [rsp+78h+arg_20]
0x18002e1de  mov     [rax], rbp
0x18002e1e1  jmp     loc_18002E031
```
