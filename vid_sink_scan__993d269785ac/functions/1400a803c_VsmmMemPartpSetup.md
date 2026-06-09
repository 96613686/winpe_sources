# VsmmMemPartpSetup

- ea: `0x1400a803c`
- end: `0x1400a8433`
- name: `VsmmMemPartpSetup`
- size: `1015`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400a64c0`
- `0x1400a678c`
- `0x1400a6974`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x1400a53a4`
- `0x1400a7d58`
- `0x1400a803c`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400a80b8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400a80b8`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a81bf`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a81bf`
- `ntoskrnl!PsPartitionType` at `0x1400a8092`
- `ntoskrnl!PsPartitionType` at `0x1400a8194`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400a837e`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400a837e`

## pseudocode

```c
__int64 __fastcall VsmmMemPartpSetup(__int64 a1, char a2)
{
  void **Handle; // rdi
  void *v4; // rcx
  int IdFromHandle; // ebx
  char *v7; // rdx
  PVOID *p_Object; // rax
  int v10; // [rsp+40h] [rbp-C0h] BYREF
  int v11; // [rsp+44h] [rbp-BCh] BYREF
  PVOID Object; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+70h] [rbp-90h]
  char v15[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v16[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v17[16]; // [rsp+B0h] [rbp-50h] BYREF
  PVOID *v18; // [rsp+C0h] [rbp-40h]
  __int64 v19; // [rsp+C8h] [rbp-38h]
  int *v20; // [rsp+D0h] [rbp-30h]
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
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v16, "VsmmMemPartpSetup");
        tlgCreate1Sz_char(v17, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
        v10 = 2982;
        v18 = (PVOID *)&v10;
        v7 = &byte_14004BC47;
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
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v7, 0, 0, 7, v15);
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
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v16, "VsmmMemPartpSetup");
        tlgCreate1Sz_char(v17, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
        LODWORD(Object) = 3002;
        v18 = &Object;
        v7 = byte_14004BBF1;
        v20 = &v11;
        v10 = *(_DWORD *)(a1 + 28);
        p_Object = (PVOID *)&v10;
        goto LABEL_6;
      }
      return (unsigned int)IdFromHandle;
    }
  }
  IdFromHandle = VsmmMemPartGetIdFromHandle((__int64)*Handle, (_DWORD *)(a1 + 24));
  if ( IdFromHandle >= 0 )
  {
    if ( a2 )
    {
      IdFromHandle = VsmmMemPartpCreateSecurityDescriptor(SecurityDescriptor, &Dacl);
      if ( IdFromHandle < 0 )
      {
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v16, "VsmmMemPartpSetup");
          tlgCreate1Sz_char(v17, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
          LODWORD(Object) = 3039;
          v18 = &Object;
          v7 = &byte_14004BAEF;
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
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v16, "VsmmMemPartpSetup");
          tlgCreate1Sz_char(v17, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
          LODWORD(Object) = 3053;
          v18 = &Object;
          v7 = byte_14004BB9B;
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
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v16, "VsmmMemPartpSetup");
    tlgCreate1Sz_char(v17, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
    LODWORD(Object) = 3016;
    v18 = &Object;
    v7 = byte_14004BB45;
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
0x1400a803c  push    rbp
0x1400a803e  push    rbx
0x1400a803f  push    rsi
0x1400a8040  push    rdi
0x1400a8041  push    r14
0x1400a8043  push    r15
0x1400a8045  lea     rbp, [rsp-0F8h]
0x1400a804d  sub     rsp, 1F8h
0x1400a8054  mov     rax, cs:__security_cookie
0x1400a805b  xor     rax, rsp
0x1400a805e  mov     [rbp+120h+var_40], rax
0x1400a8065  xor     eax, eax
0x1400a8067  lea     rdi, [rcx+50h]
0x1400a806b  xorps   xmm0, xmm0
0x1400a806e  mov     [rsp+220h+var_1B0], rax
0x1400a8073  mov     rsi, rcx
0x1400a8076  xor     r15d, r15d
0x1400a8079  mov     rcx, [rdi]; Handle
0x1400a807c  mov     r14b, dl
0x1400a807f  movups  [rsp+220h+SecurityDescriptor], xmm0
0x1400a8084  movups  [rsp+220h+var_1C0], xmm0
0x1400a8089  test    rcx, rcx
0x1400a808c  jz      loc_1400A8194
0x1400a8092  mov     r8, cs:__imp_PsPartitionType
0x1400a8099  lea     rax, [rsp+220h+var_1D8]
0x1400a809e  mov     [rsp+220h+HandleInformation], r15; HandleInformation
0x1400a80a3  xor     r9d, r9d; AccessMode
0x1400a80a6  mov     edx, 1F0003h; DesiredAccess
0x1400a80ab  mov     [rsp+220h+var_1D8], r15
0x1400a80b0  mov     [rsp+220h+Object], rax; Object
0x1400a80b5  mov     r8, [r8]; ObjectType
0x1400a80b8  call    cs:__imp_ObReferenceObjectByHandle
0x1400a80bf  nop     dword ptr [rax+rax+00h]
0x1400a80c4  mov     ebx, eax
0x1400a80c6  mov     rax, [rsp+220h+var_1D8]
0x1400a80cb  mov     [rsi+58h], rax
0x1400a80cf  test    ebx, ebx
0x1400a80d1  jns     loc_1400A824B
0x1400a80d7  mov     eax, cs:dword_140064110
0x1400a80dd  cmp     eax, 2
0x1400a80e0  jbe     loc_1400A8411
0x1400a80e6  mov     edx, 100h
0x1400a80eb  lea     rcx, dword_140064110
0x1400a80f2  call    _tlgKeywordOn
0x1400a80f7  test    al, al
0x1400a80f9  jz      loc_1400A8411
0x1400a80ff  lea     rdx, aVsmmmempartpse; "VsmmMemPartpSetup"
0x1400a8106  lea     rcx, [rbp+120h+var_180]
0x1400a810a  call    _tlgCreate1Sz_char
0x1400a810f  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a8116  lea     rcx, [rbp+120h+var_170]
0x1400a811a  call    _tlgCreate1Sz_char
0x1400a811f  lea     rax, [rsp+220h+var_1E0]
0x1400a8124  mov     [rsp+220h+var_1E0], 0BA6h
0x1400a812c  mov     [rbp+120h+var_160], rax
0x1400a8130  lea     rdx, byte_14004BC47
0x1400a8137  lea     rax, [rsp+220h+var_1DC]
0x1400a813c  mov     [rbp+120h+var_150], rax
0x1400a8140  mov     eax, [rsi+1Ch]
0x1400a8143  mov     dword ptr [rsp+220h+var_1D8], eax
0x1400a8147  lea     rax, [rsp+220h+var_1D8]
0x1400a814c  mov     [rbp+120h+var_138], 4
0x1400a8154  mov     [rbp+120h+var_148], 4
0x1400a815c  mov     [rbp+120h+var_158], 4
0x1400a8164  mov     [rbp+120h+var_140], rax
0x1400a8168  lea     rcx, dword_140064110
0x1400a816f  lea     rax, [rbp+120h+var_1A0]
0x1400a8173  mov     [rsp+220h+var_1DC], ebx
0x1400a8177  mov     [rsp+220h+HandleInformation], rax
0x1400a817c  xor     r9d, r9d
0x1400a817f  xor     r8d, r8d
0x1400a8182  mov     dword ptr [rsp+220h+Object], 7
0x1400a818a  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400a818f  jmp     loc_1400A8411
0x1400a8194  mov     rax, cs:__imp_PsPartitionType
0x1400a819b  mov     r9d, 1F0003h; DesiredAccess
0x1400a81a1  mov     [rsp+220h+Handle], rdi; Handle
0x1400a81a6  xor     r8d, r8d; PassedAccessState
0x1400a81a9  mov     byte ptr [rsp+220h+HandleInformation], r15b; AccessMode
0x1400a81ae  mov     edx, 200h; HandleAttributes
0x1400a81b3  mov     rcx, [rax]
0x1400a81b6  mov     [rsp+220h+Object], rcx; ObjectType
0x1400a81bb  mov     rcx, [rsi+58h]; Object
0x1400a81bf  call    cs:__imp_ObOpenObjectByPointer
0x1400a81c6  nop     dword ptr [rax+rax+00h]
0x1400a81cb  mov     ebx, eax
0x1400a81cd  test    eax, eax
0x1400a81cf  jns     short loc_1400A824B
0x1400a81d1  mov     ecx, cs:dword_140064110
0x1400a81d7  cmp     ecx, 2
0x1400a81da  jbe     loc_1400A8411
0x1400a81e0  mov     edx, 100h
0x1400a81e5  lea     rcx, dword_140064110
0x1400a81ec  call    _tlgKeywordOn
0x1400a81f1  test    al, al
0x1400a81f3  jz      loc_1400A8411
0x1400a81f9  lea     rdx, aVsmmmempartpse; "VsmmMemPartpSetup"
0x1400a8200  lea     rcx, [rbp+120h+var_180]
0x1400a8204  call    _tlgCreate1Sz_char
0x1400a8209  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a8210  lea     rcx, [rbp+120h+var_170]
0x1400a8214  call    _tlgCreate1Sz_char
0x1400a8219  lea     rax, [rsp+220h+var_1D8]
0x1400a821e  mov     dword ptr [rsp+220h+var_1D8], 0BBAh
0x1400a8226  mov     [rbp+120h+var_160], rax
0x1400a822a  lea     rdx, byte_14004BBF1
0x1400a8231  lea     rax, [rsp+220h+var_1DC]
0x1400a8236  mov     [rbp+120h+var_150], rax
0x1400a823a  mov     eax, [rsi+1Ch]
0x1400a823d  mov     [rsp+220h+var_1E0], eax
0x1400a8241  lea     rax, [rsp+220h+var_1E0]
0x1400a8246  jmp     loc_1400A814C
0x1400a824b  mov     rcx, [rdi]
0x1400a824e  lea     rdx, [rsi+18h]
0x1400a8252  call    VsmmMemPartGetIdFromHandle
0x1400a8257  mov     ebx, eax
0x1400a8259  test    eax, eax
0x1400a825b  jns     short loc_1400A82D7
0x1400a825d  mov     eax, cs:dword_140064110
0x1400a8263  cmp     eax, 2
0x1400a8266  jbe     loc_1400A8411
0x1400a826c  mov     edx, 100h
0x1400a8271  lea     rcx, dword_140064110
0x1400a8278  call    _tlgKeywordOn
0x1400a827d  test    al, al
0x1400a827f  jz      loc_1400A8411
0x1400a8285  lea     rdx, aVsmmmempartpse; "VsmmMemPartpSetup"
0x1400a828c  lea     rcx, [rbp+120h+var_180]
0x1400a8290  call    _tlgCreate1Sz_char
0x1400a8295  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a829c  lea     rcx, [rbp+120h+var_170]
0x1400a82a0  call    _tlgCreate1Sz_char
0x1400a82a5  lea     rax, [rsp+220h+var_1D8]
0x1400a82aa  mov     dword ptr [rsp+220h+var_1D8], 0BC8h
0x1400a82b2  mov     [rbp+120h+var_160], rax
0x1400a82b6  lea     rdx, byte_14004BB45
0x1400a82bd  lea     rax, [rsp+220h+var_1DC]
0x1400a82c2  mov     [rbp+120h+var_150], rax
0x1400a82c6  mov     eax, [rsi+1Ch]
0x1400a82c9  mov     [rsp+220h+var_1E0], eax
0x1400a82cd  lea     rax, [rsp+220h+var_1E0]
0x1400a82d2  jmp     loc_1400A814C
0x1400a82d7  test    r14b, r14b
0x1400a82da  jz      loc_1400A840E
0x1400a82e0  lea     rdx, [rbp+120h+Dacl]; Dacl
0x1400a82e4  lea     rcx, [rsp+220h+SecurityDescriptor]; SecurityDescriptor
0x1400a82e9  call    VsmmMemPartpCreateSecurityDescriptor
0x1400a82ee  mov     ebx, eax
0x1400a82f0  test    eax, eax
0x1400a82f2  jns     short loc_1400A836E
0x1400a82f4  mov     eax, cs:dword_140064110
0x1400a82fa  cmp     eax, 2
0x1400a82fd  jbe     loc_1400A8411
0x1400a8303  mov     edx, 100h
0x1400a8308  lea     rcx, dword_140064110
0x1400a830f  call    _tlgKeywordOn
0x1400a8314  test    al, al
0x1400a8316  jz      loc_1400A8411
0x1400a831c  lea     rdx, aVsmmmempartpse; "VsmmMemPartpSetup"
0x1400a8323  lea     rcx, [rbp+120h+var_180]
0x1400a8327  call    _tlgCreate1Sz_char
0x1400a832c  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a8333  lea     rcx, [rbp+120h+var_170]
0x1400a8337  call    _tlgCreate1Sz_char
0x1400a833c  lea     rax, [rsp+220h+var_1D8]
0x1400a8341  mov     dword ptr [rsp+220h+var_1D8], 0BDFh
0x1400a8349  mov     [rbp+120h+var_160], rax
0x1400a834d  lea     rdx, byte_14004BAEF
0x1400a8354  lea     rax, [rsp+220h+var_1DC]
0x1400a8359  mov     [rbp+120h+var_150], rax
0x1400a835d  mov     eax, [rsi+1Ch]
0x1400a8360  mov     [rsp+220h+var_1E0], eax
0x1400a8364  lea     rax, [rsp+220h+var_1E0]
0x1400a8369  jmp     loc_1400A814C
0x1400a836e  mov     rcx, [rsi+58h]
0x1400a8372  lea     r8, [rsp+220h+SecurityDescriptor]
0x1400a8377  mov     edi, 4
0x1400a837c  mov     edx, edi
0x1400a837e  call    cs:__imp_ObSetSecurityObjectByPointer
0x1400a8385  nop     dword ptr [rax+rax+00h]
0x1400a838a  mov     ebx, eax
0x1400a838c  test    eax, eax
0x1400a838e  jns     short loc_1400A840E
0x1400a8390  mov     eax, cs:dword_140064110
0x1400a8396  cmp     eax, 2
0x1400a8399  jbe     short loc_1400A8411
0x1400a839b  mov     edx, 100h
0x1400a83a0  lea     rcx, dword_140064110
0x1400a83a7  call    _tlgKeywordOn
0x1400a83ac  test    al, al
0x1400a83ae  jz      short loc_1400A8411
0x1400a83b0  lea     rdx, aVsmmmempartpse; "VsmmMemPartpSetup"
0x1400a83b7  lea     rcx, [rbp+120h+var_180]
0x1400a83bb  call    _tlgCreate1Sz_char
0x1400a83c0  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a83c7  lea     rcx, [rbp+120h+var_170]
0x1400a83cb  call    _tlgCreate1Sz_char
0x1400a83d0  lea     rax, [rsp+220h+var_1D8]
0x1400a83d5  mov     dword ptr [rsp+220h+var_1D8], 0BEDh
0x1400a83dd  mov     [rbp+120h+var_160], rax
0x1400a83e1  lea     rdx, byte_14004BB9B
0x1400a83e8  lea     rax, [rsp+220h+var_1DC]
0x1400a83ed  mov     [rbp+120h+var_158], rdi
0x1400a83f1  mov     [rbp+120h+var_150], rax
0x1400a83f5  mov     eax, [rsi+1Ch]
0x1400a83f8  mov     [rsp+220h+var_1E0], eax
0x1400a83fc  lea     rax, [rsp+220h+var_1E0]
0x1400a8401  mov     [rbp+120h+var_148], rdi
0x1400a8405  mov     [rbp+120h+var_138], rdi
0x1400a8409  jmp     loc_1400A8164
0x1400a840e  mov     ebx, r15d
0x1400a8411  mov     eax, ebx
0x1400a8413  mov     rcx, [rbp+120h+var_40]
0x1400a841a  xor     rcx, rsp; StackCookie
0x1400a841d  call    __security_check_cookie
0x1400a8422  add     rsp, 1F8h
0x1400a8429  pop     r15
0x1400a842b  pop     r14
0x1400a842d  pop     rdi
0x1400a842e  pop     rsi
0x1400a842f  pop     rbx
0x1400a8430  pop     rbp
0x1400a8431  retn
```
