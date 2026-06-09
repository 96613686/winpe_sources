# VsmmMemPartpSetup

- ea: `0x1400a9dbc`
- end: `0x1400aa1b3`
- name: `VsmmMemPartpSetup`
- size: `1015`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400a8228`
- `0x1400a84f4`
- `0x1400a86dc`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x1400a6f00`
- `0x1400a9ad8`
- `0x1400a9dbc`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400a9e38`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400a9e38`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a9f3f`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a9f3f`
- `ntoskrnl!PsPartitionType` at `0x1400a9e12`
- `ntoskrnl!PsPartitionType` at `0x1400a9f14`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400aa0fe`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400aa0fe`

## pseudocode

```c
__int64 __fastcall VsmmMemPartpSetup(__int64 a1, char a2)
{
  void **Handle; // rdi
  void *v4; // rcx
  NTSTATUS IdFromHandle; // ebx
  __int16 *v7; // rdx
  PVOID *p_Object; // rax
  int v10; // [rsp+40h] [rbp-C0h] BYREF
  NTSTATUS v11; // [rsp+44h] [rbp-BCh] BYREF
  PVOID Object; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+70h] [rbp-90h]
  char v15[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v16[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v17[16]; // [rsp+B0h] [rbp-50h] BYREF
  PVOID *v18; // [rsp+C0h] [rbp-40h]
  __int64 v19; // [rsp+C8h] [rbp-38h]
  NTSTATUS *v20; // [rsp+D0h] [rbp-30h]
  __int64 v21; // [rsp+D8h] [rbp-28h]
  PVOID *v22; // [rsp+E0h] [rbp-20h]
  __int64 v23; // [rsp+E8h] [rbp-18h]
  struct _ACL Dacl; // [rsp+F0h] [rbp-10h] BYREF

  Handle = (void **)(a1 + 80);
  v14 = 0;
  v4 = *(void **)(a1 + 80);
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( v4 )
  {
    Object = 0;
    IdFromHandle = ObReferenceObjectByHandle(v4, 0x1F0003u, PsPartitionType, 0, &Object, 0);
    *(_QWORD *)(a1 + 88) = Object;
    if ( IdFromHandle < 0 )
    {
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v16, "VsmmMemPartpSetup");
        tlgCreate1Sz_char(v17, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
        v10 = 3089;
        v18 = (PVOID *)&v10;
        v7 = word_14004BFD2;
        v20 = &v11;
        LODWORD(Object) = *(_DWORD *)(a1 + 28);
        p_Object = &Object;
LABEL_6:
        v23 = 4;
        v21 = 4;
        v19 = 4;
LABEL_7:
        v22 = p_Object;
        v11 = IdFromHandle;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v7, 0, 0, 7, v15);
        return (unsigned int)IdFromHandle;
      }
      return (unsigned int)IdFromHandle;
    }
  }
  else
  {
    IdFromHandle = ObOpenObjectByPointer(*(PVOID *)(a1 + 88), 0x200u, 0, 0x1F0003u, PsPartitionType, 0, Handle);
    if ( IdFromHandle < 0 )
    {
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v16, "VsmmMemPartpSetup");
        tlgCreate1Sz_char(v17, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
        LODWORD(Object) = 3109;
        v18 = &Object;
        v7 = (__int16 *)qword_14004C028;
        v20 = &v11;
        v10 = *(_DWORD *)(a1 + 28);
        p_Object = (PVOID *)&v10;
        goto LABEL_6;
      }
      return (unsigned int)IdFromHandle;
    }
  }
  IdFromHandle = VsmmMemPartGetIdFromHandle(*Handle, a1 + 24);
  if ( IdFromHandle >= 0 )
  {
    if ( a2 )
    {
      IdFromHandle = VsmmMemPartpCreateSecurityDescriptor(SecurityDescriptor, &Dacl);
      if ( IdFromHandle < 0 )
      {
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v16, "VsmmMemPartpSetup");
          tlgCreate1Sz_char(v17, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
          LODWORD(Object) = 3146;
          v18 = &Object;
          v7 = (__int16 *)&dword_14004C0D4;
          v20 = &v11;
          v10 = *(_DWORD *)(a1 + 28);
          p_Object = (PVOID *)&v10;
          goto LABEL_6;
        }
        return (unsigned int)IdFromHandle;
      }
      IdFromHandle = ObSetSecurityObjectByPointer(*(_QWORD *)(a1 + 88), 4, SecurityDescriptor);
      if ( IdFromHandle < 0 )
      {
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v16, "VsmmMemPartpSetup");
          tlgCreate1Sz_char(v17, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
          LODWORD(Object) = 3160;
          v18 = &Object;
          v7 = (__int16 *)&dword_14004BF7C;
          v19 = 4;
          v20 = &v11;
          v10 = *(_DWORD *)(a1 + 28);
          p_Object = (PVOID *)&v10;
          v21 = 4;
          v23 = 4;
          goto LABEL_7;
        }
        return (unsigned int)IdFromHandle;
      }
    }
    return 0;
  }
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v16, "VsmmMemPartpSetup");
    tlgCreate1Sz_char(v17, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
    LODWORD(Object) = 3123;
    v18 = &Object;
    v7 = &word_14004C07E;
    v20 = &v11;
    v10 = *(_DWORD *)(a1 + 28);
    p_Object = (PVOID *)&v10;
    goto LABEL_6;
  }
  return (unsigned int)IdFromHandle;
}

```

## disassembly

```asm
0x1400a9dbc  push    rbp
0x1400a9dbe  push    rbx
0x1400a9dbf  push    rsi
0x1400a9dc0  push    rdi
0x1400a9dc1  push    r14
0x1400a9dc3  push    r15
0x1400a9dc5  lea     rbp, [rsp-0F8h]
0x1400a9dcd  sub     rsp, 1F8h
0x1400a9dd4  mov     rax, cs:__security_cookie
0x1400a9ddb  xor     rax, rsp
0x1400a9dde  mov     [rbp+120h+var_40], rax
0x1400a9de5  xor     eax, eax
0x1400a9de7  lea     rdi, [rcx+50h]
0x1400a9deb  xorps   xmm0, xmm0
0x1400a9dee  mov     [rsp+220h+var_1B0], rax
0x1400a9df3  mov     rsi, rcx
0x1400a9df6  xor     r15d, r15d
0x1400a9df9  mov     rcx, [rdi]; Handle
0x1400a9dfc  mov     r14b, dl
0x1400a9dff  movups  [rsp+220h+SecurityDescriptor], xmm0
0x1400a9e04  movups  [rsp+220h+var_1C0], xmm0
0x1400a9e09  test    rcx, rcx
0x1400a9e0c  jz      loc_1400A9F14
0x1400a9e12  mov     r8, cs:__imp_PsPartitionType
0x1400a9e19  lea     rax, [rsp+220h+var_1D8]
0x1400a9e1e  mov     [rsp+220h+HandleInformation], r15; HandleInformation
0x1400a9e23  xor     r9d, r9d; AccessMode
0x1400a9e26  mov     edx, 1F0003h; DesiredAccess
0x1400a9e2b  mov     [rsp+220h+var_1D8], r15
0x1400a9e30  mov     [rsp+220h+Object], rax; Object
0x1400a9e35  mov     r8, [r8]; ObjectType
0x1400a9e38  call    cs:__imp_ObReferenceObjectByHandle
0x1400a9e3f  nop     dword ptr [rax+rax+00h]
0x1400a9e44  mov     ebx, eax
0x1400a9e46  mov     rax, [rsp+220h+var_1D8]
0x1400a9e4b  mov     [rsi+58h], rax
0x1400a9e4f  test    ebx, ebx
0x1400a9e51  jns     loc_1400A9FCB
0x1400a9e57  mov     eax, cs:dword_140065110
0x1400a9e5d  cmp     eax, 2
0x1400a9e60  jbe     loc_1400AA191
0x1400a9e66  mov     edx, 100h
0x1400a9e6b  lea     rcx, dword_140065110
0x1400a9e72  call    _tlgKeywordOn
0x1400a9e77  test    al, al
0x1400a9e79  jz      loc_1400AA191
0x1400a9e7f  lea     rdx, aVsmmmempartpse; "VsmmMemPartpSetup"
0x1400a9e86  lea     rcx, [rbp+120h+var_180]
0x1400a9e8a  call    _tlgCreate1Sz_char
0x1400a9e8f  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a9e96  lea     rcx, [rbp+120h+var_170]
0x1400a9e9a  call    _tlgCreate1Sz_char
0x1400a9e9f  lea     rax, [rsp+220h+var_1E0]
0x1400a9ea4  mov     [rsp+220h+var_1E0], 0C11h
0x1400a9eac  mov     [rbp+120h+var_160], rax
0x1400a9eb0  lea     rdx, word_14004BFD2
0x1400a9eb7  lea     rax, [rsp+220h+var_1DC]
0x1400a9ebc  mov     [rbp+120h+var_150], rax
0x1400a9ec0  mov     eax, [rsi+1Ch]
0x1400a9ec3  mov     dword ptr [rsp+220h+var_1D8], eax
0x1400a9ec7  lea     rax, [rsp+220h+var_1D8]
0x1400a9ecc  mov     [rbp+120h+var_138], 4
0x1400a9ed4  mov     [rbp+120h+var_148], 4
0x1400a9edc  mov     [rbp+120h+var_158], 4
0x1400a9ee4  mov     [rbp+120h+var_140], rax
0x1400a9ee8  lea     rcx, dword_140065110
0x1400a9eef  lea     rax, [rbp+120h+var_1A0]
0x1400a9ef3  mov     [rsp+220h+var_1DC], ebx
0x1400a9ef7  mov     [rsp+220h+HandleInformation], rax
0x1400a9efc  xor     r9d, r9d
0x1400a9eff  xor     r8d, r8d
0x1400a9f02  mov     dword ptr [rsp+220h+Object], 7
0x1400a9f0a  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400a9f0f  jmp     loc_1400AA191
0x1400a9f14  mov     rax, cs:__imp_PsPartitionType
0x1400a9f1b  mov     r9d, 1F0003h; DesiredAccess
0x1400a9f21  mov     [rsp+220h+Handle], rdi; Handle
0x1400a9f26  xor     r8d, r8d; PassedAccessState
0x1400a9f29  mov     byte ptr [rsp+220h+HandleInformation], r15b; AccessMode
0x1400a9f2e  mov     edx, 200h; HandleAttributes
0x1400a9f33  mov     rcx, [rax]
0x1400a9f36  mov     [rsp+220h+Object], rcx; ObjectType
0x1400a9f3b  mov     rcx, [rsi+58h]; Object
0x1400a9f3f  call    cs:__imp_ObOpenObjectByPointer
0x1400a9f46  nop     dword ptr [rax+rax+00h]
0x1400a9f4b  mov     ebx, eax
0x1400a9f4d  test    eax, eax
0x1400a9f4f  jns     short loc_1400A9FCB
0x1400a9f51  mov     ecx, cs:dword_140065110
0x1400a9f57  cmp     ecx, 2
0x1400a9f5a  jbe     loc_1400AA191
0x1400a9f60  mov     edx, 100h
0x1400a9f65  lea     rcx, dword_140065110
0x1400a9f6c  call    _tlgKeywordOn
0x1400a9f71  test    al, al
0x1400a9f73  jz      loc_1400AA191
0x1400a9f79  lea     rdx, aVsmmmempartpse; "VsmmMemPartpSetup"
0x1400a9f80  lea     rcx, [rbp+120h+var_180]
0x1400a9f84  call    _tlgCreate1Sz_char
0x1400a9f89  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a9f90  lea     rcx, [rbp+120h+var_170]
0x1400a9f94  call    _tlgCreate1Sz_char
0x1400a9f99  lea     rax, [rsp+220h+var_1D8]
0x1400a9f9e  mov     dword ptr [rsp+220h+var_1D8], 0C25h
0x1400a9fa6  mov     [rbp+120h+var_160], rax
0x1400a9faa  lea     rdx, qword_14004C028
0x1400a9fb1  lea     rax, [rsp+220h+var_1DC]
0x1400a9fb6  mov     [rbp+120h+var_150], rax
0x1400a9fba  mov     eax, [rsi+1Ch]
0x1400a9fbd  mov     [rsp+220h+var_1E0], eax
0x1400a9fc1  lea     rax, [rsp+220h+var_1E0]
0x1400a9fc6  jmp     loc_1400A9ECC
0x1400a9fcb  mov     rcx, [rdi]
0x1400a9fce  lea     rdx, [rsi+18h]
0x1400a9fd2  call    VsmmMemPartGetIdFromHandle
0x1400a9fd7  mov     ebx, eax
0x1400a9fd9  test    eax, eax
0x1400a9fdb  jns     short loc_1400AA057
0x1400a9fdd  mov     eax, cs:dword_140065110
0x1400a9fe3  cmp     eax, 2
0x1400a9fe6  jbe     loc_1400AA191
0x1400a9fec  mov     edx, 100h
0x1400a9ff1  lea     rcx, dword_140065110
0x1400a9ff8  call    _tlgKeywordOn
0x1400a9ffd  test    al, al
0x1400a9fff  jz      loc_1400AA191
0x1400aa005  lea     rdx, aVsmmmempartpse; "VsmmMemPartpSetup"
0x1400aa00c  lea     rcx, [rbp+120h+var_180]
0x1400aa010  call    _tlgCreate1Sz_char
0x1400aa015  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400aa01c  lea     rcx, [rbp+120h+var_170]
0x1400aa020  call    _tlgCreate1Sz_char
0x1400aa025  lea     rax, [rsp+220h+var_1D8]
0x1400aa02a  mov     dword ptr [rsp+220h+var_1D8], 0C33h
0x1400aa032  mov     [rbp+120h+var_160], rax
0x1400aa036  lea     rdx, word_14004C07E
0x1400aa03d  lea     rax, [rsp+220h+var_1DC]
0x1400aa042  mov     [rbp+120h+var_150], rax
0x1400aa046  mov     eax, [rsi+1Ch]
0x1400aa049  mov     [rsp+220h+var_1E0], eax
0x1400aa04d  lea     rax, [rsp+220h+var_1E0]
0x1400aa052  jmp     loc_1400A9ECC
0x1400aa057  test    r14b, r14b
0x1400aa05a  jz      loc_1400AA18E
0x1400aa060  lea     rdx, [rbp+120h+Dacl]; Dacl
0x1400aa064  lea     rcx, [rsp+220h+SecurityDescriptor]; SecurityDescriptor
0x1400aa069  call    VsmmMemPartpCreateSecurityDescriptor
0x1400aa06e  mov     ebx, eax
0x1400aa070  test    eax, eax
0x1400aa072  jns     short loc_1400AA0EE
0x1400aa074  mov     eax, cs:dword_140065110
0x1400aa07a  cmp     eax, 2
0x1400aa07d  jbe     loc_1400AA191
0x1400aa083  mov     edx, 100h
0x1400aa088  lea     rcx, dword_140065110
0x1400aa08f  call    _tlgKeywordOn
0x1400aa094  test    al, al
0x1400aa096  jz      loc_1400AA191
0x1400aa09c  lea     rdx, aVsmmmempartpse; "VsmmMemPartpSetup"
0x1400aa0a3  lea     rcx, [rbp+120h+var_180]
0x1400aa0a7  call    _tlgCreate1Sz_char
0x1400aa0ac  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400aa0b3  lea     rcx, [rbp+120h+var_170]
0x1400aa0b7  call    _tlgCreate1Sz_char
0x1400aa0bc  lea     rax, [rsp+220h+var_1D8]
0x1400aa0c1  mov     dword ptr [rsp+220h+var_1D8], 0C4Ah
0x1400aa0c9  mov     [rbp+120h+var_160], rax
0x1400aa0cd  lea     rdx, dword_14004C0D4
0x1400aa0d4  lea     rax, [rsp+220h+var_1DC]
0x1400aa0d9  mov     [rbp+120h+var_150], rax
0x1400aa0dd  mov     eax, [rsi+1Ch]
0x1400aa0e0  mov     [rsp+220h+var_1E0], eax
0x1400aa0e4  lea     rax, [rsp+220h+var_1E0]
0x1400aa0e9  jmp     loc_1400A9ECC
0x1400aa0ee  mov     rcx, [rsi+58h]
0x1400aa0f2  lea     r8, [rsp+220h+SecurityDescriptor]
0x1400aa0f7  mov     edi, 4
0x1400aa0fc  mov     edx, edi
0x1400aa0fe  call    cs:__imp_ObSetSecurityObjectByPointer
0x1400aa105  nop     dword ptr [rax+rax+00h]
0x1400aa10a  mov     ebx, eax
0x1400aa10c  test    eax, eax
0x1400aa10e  jns     short loc_1400AA18E
0x1400aa110  mov     eax, cs:dword_140065110
0x1400aa116  cmp     eax, 2
0x1400aa119  jbe     short loc_1400AA191
0x1400aa11b  mov     edx, 100h
0x1400aa120  lea     rcx, dword_140065110
0x1400aa127  call    _tlgKeywordOn
0x1400aa12c  test    al, al
0x1400aa12e  jz      short loc_1400AA191
0x1400aa130  lea     rdx, aVsmmmempartpse; "VsmmMemPartpSetup"
0x1400aa137  lea     rcx, [rbp+120h+var_180]
0x1400aa13b  call    _tlgCreate1Sz_char
0x1400aa140  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400aa147  lea     rcx, [rbp+120h+var_170]
0x1400aa14b  call    _tlgCreate1Sz_char
0x1400aa150  lea     rax, [rsp+220h+var_1D8]
0x1400aa155  mov     dword ptr [rsp+220h+var_1D8], 0C58h
0x1400aa15d  mov     [rbp+120h+var_160], rax
0x1400aa161  lea     rdx, dword_14004BF7C
0x1400aa168  lea     rax, [rsp+220h+var_1DC]
0x1400aa16d  mov     [rbp+120h+var_158], rdi
0x1400aa171  mov     [rbp+120h+var_150], rax
0x1400aa175  mov     eax, [rsi+1Ch]
0x1400aa178  mov     [rsp+220h+var_1E0], eax
0x1400aa17c  lea     rax, [rsp+220h+var_1E0]
0x1400aa181  mov     [rbp+120h+var_148], rdi
0x1400aa185  mov     [rbp+120h+var_138], rdi
0x1400aa189  jmp     loc_1400A9EE4
0x1400aa18e  mov     ebx, r15d
0x1400aa191  mov     eax, ebx
0x1400aa193  mov     rcx, [rbp+120h+var_40]
0x1400aa19a  xor     rcx, rsp; StackCookie
0x1400aa19d  call    __security_check_cookie
0x1400aa1a2  add     rsp, 1F8h
0x1400aa1a9  pop     r15
0x1400aa1ab  pop     r14
0x1400aa1ad  pop     rdi
0x1400aa1ae  pop     rsi
0x1400aa1af  pop     rbx
0x1400aa1b0  pop     rbp
0x1400aa1b1  retn
```
