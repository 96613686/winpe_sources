# RPC_INTERFACE::UpdateRpcInterfaceInformation(_RPC_SERVER_INTERFACE *,uint,uint,uint,long (*)(void *,void *),void *,RPCP_INTERFACE_GROUP *)

- ea: `0x18004f690`
- end: `0x18004f930`
- name: `?UpdateRpcInterfaceInformation@RPC_INTERFACE@@QEAAJPEAU_RPC_SERVER_INTERFACE@@IIIP6AJPEAX1@Z1PEAVRPCP_INTERFACE_GROUP@@@Z`
- size: `672`
- prototype: `__int64 __fastcall(RPC_INTERFACE *this, struct _RPC_SERVER_INTERFACE *, int, int, unsigned int, int (*)(void *, void *), PSECURITY_DESCRIPTOR CreatorDescriptor, struct RPCP_INTERFACE_GROUP *)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004e894`
- `0x18006dac0`

## callees

- `0x180021e70`
- `0x180022870`
- `0x18002b7c0`
- `0x18004f690`
- `0x18004f938`
- `0x1800ca025`
- `0x1800ca031`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18004f8d5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18004f8e4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18004f8d5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18004f8e4`

## pseudocode

```c
__int64 __fastcall RPC_INTERFACE::UpdateRpcInterfaceInformation(
        RPC_INTERFACE *this,
        struct _RPC_SERVER_INTERFACE *a2,
        int a3,
        int a4,
        unsigned int a5,
        int (*a6)(void *, void *),
        PSECURITY_DESCRIPTOR CreatorDescriptor,
        struct RPCP_INTERFACE_GROUP *a8)
{
  size_t Length; // r15
  void *v9; // rsi
  unsigned int v14; // eax
  unsigned int v15; // edi
  _DWORD *InterpreterInfo; // rcx
  int v17; // eax
  void *v18; // rcx
  void *v19; // rax
  __int64 i; // r10
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rcx
  __int64 v24; // r9
  void *v25; // rcx
  unsigned int v26; // eax
  bool v27; // cf
  __int64 v28; // rcx
  REFERENCED_OBJECT *v29; // rcx
  DWORD SecurityDescriptorLength; // edi
  void *lpMem; // [rsp+58h] [rbp+10h] BYREF

  Length = a2->Length;
  v9 = 0;
  lpMem = 0;
  if ( (((_DWORD)Length - 64) & 0xFFFFFFDF) != 0 )
    return 1717;
  if ( CreatorDescriptor )
  {
    v14 = RpcpNormalizeSecurityDescriptor(CreatorDescriptor, 0, &lpMem);
    v9 = lpMem;
    v15 = v14;
    if ( v14 )
      goto LABEL_21;
  }
  if ( *((_DWORD *)this + 50) )
  {
    if ( *((_DWORD *)this + 2) == a3 && *((int (**)(void *, void *))this + 9) == a6 )
    {
      if ( v9 )
      {
LABEL_32:
        if ( !*((_QWORD *)this + 70) )
          goto LABEL_35;
        SecurityDescriptorLength = GetSecurityDescriptorLength(v9);
        if ( SecurityDescriptorLength != GetSecurityDescriptorLength(*((PSECURITY_DESCRIPTOR *)this + 70))
          || memcmp_0(v9, *((const void **)this + 70), SecurityDescriptorLength) )
        {
          goto LABEL_35;
        }
LABEL_15:
        v26 = a5;
        v27 = a5 < 0x7FFFFFFF;
        *((_DWORD *)this + 51) = a4;
        if ( !v27 )
          v26 = 0x7FFFFFFF;
        ++*((_DWORD *)this + 91);
        v28 = *((_QWORD *)this + 71);
        v15 = 0;
        *((_DWORD *)this + 82) = v26;
        if ( v28 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 32LL))(v28);
        v29 = a8;
        *((_QWORD *)this + 71) = a8;
        if ( v29 )
          REFERENCED_OBJECT::AddReference(v29);
        goto LABEL_21;
      }
      if ( !*((_QWORD *)this + 70) )
        goto LABEL_15;
    }
    if ( !v9 )
    {
LABEL_35:
      v15 = 87;
      goto LABEL_21;
    }
    goto LABEL_32;
  }
  if ( (a2->Flags & 0x2000000) == 0 )
  {
    *((_DWORD *)this + 48) = 0;
LABEL_11:
    memcpy_0((char *)this + 80, a2, Length);
    *((_DWORD *)this + 2) = 0;
    v25 = (void *)*((_QWORD *)this + 70);
    *((_DWORD *)this + 2) |= a3;
    *((_QWORD *)this + 9) = a6;
    if ( v25 )
    {
      FreeWrapper(v25);
      *((_QWORD *)this + 70) = 0;
    }
    if ( v9 )
    {
      *((_QWORD *)this + 70) = v9;
      v9 = 0;
    }
    goto LABEL_15;
  }
  InterpreterInfo = a2->InterpreterInfo;
  *((_DWORD *)this + 48) = InterpreterInfo[12];
  *((_QWORD *)this + 22) = *((_QWORD *)InterpreterInfo + 7);
  v17 = InterpreterInfo[12];
  v18 = (void *)*((_QWORD *)this + 23);
  *((_DWORD *)this + 49) = v17 - 1;
  if ( v18 )
    FreeWrapper(v18);
  v19 = AllocWrapper(saturated_mul(*((unsigned int *)this + 48), 0x14u));
  *((_QWORD *)this + 23) = v19;
  if ( v19 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 48); *(_DWORD *)(v23 + 4 * v22 + 16) = *(_DWORD *)(v21 + 8 * v24 + 16) )
    {
      v21 = *((_QWORD *)this + 22);
      v22 = 5 * i;
      v23 = *((_QWORD *)this + 23);
      v24 = 10 * i;
      i = (unsigned int)(i + 1);
      *(_OWORD *)(v23 + 4 * v22) = *(_OWORD *)(v21 + 8 * v24);
    }
    goto LABEL_11;
  }
  *((_DWORD *)this + 48) = 0;
  v15 = 14;
LABEL_21:
  if ( v9 )
    FreeWrapper(v9);
  return v15;
}

```

## disassembly

```asm
0x18004f690  mov     r11, rsp
0x18004f693  mov     [r11+8], rbx
0x18004f697  mov     [r11+18h], rbp
0x18004f69b  push    rsi
0x18004f69c  push    rdi
0x18004f69d  push    r12
0x18004f69f  push    r14
0x18004f6a1  push    r15
0x18004f6a3  sub     rsp, 20h
0x18004f6a7  mov     r15d, [rdx]
0x18004f6aa  xor     esi, esi
0x18004f6ac  mov     r12d, r9d
0x18004f6af  mov     [r11+10h], rsi
0x18004f6b3  mov     ebp, r8d
0x18004f6b6  mov     r14, rdx
0x18004f6b9  mov     rbx, rcx
0x18004f6bc  lea     eax, [r15-40h]
0x18004f6c0  test    eax, 0FFFFFFDFh
0x18004f6c5  jnz     loc_18004F898
0x18004f6cb  mov     rcx, [rsp+48h+CreatorDescriptor]; CreatorDescriptor
0x18004f6d3  test    rcx, rcx
0x18004f6d6  jz      short loc_18004F6F2
0x18004f6d8  lea     r8, [r11+10h]; void **
0x18004f6dc  xor     edx, edx; AutoInheritFlags
0x18004f6de  call    ?RpcpNormalizeSecurityDescriptor@@YAJPEAXKPEAPEAX@Z; RpcpNormalizeSecurityDescriptor(void *,ulong,void * *)
0x18004f6e3  mov     rsi, [rsp+48h+lpMem]
0x18004f6e8  mov     edi, eax
0x18004f6ea  test    eax, eax
0x18004f6ec  jnz     loc_18004F84F
0x18004f6f2  cmp     dword ptr [rbx+0C8h], 0
0x18004f6f9  jnz     loc_18004F89F
0x18004f6ff  test    dword ptr [r14+58h], 2000000h
0x18004f707  jz      loc_18004F871
0x18004f70d  mov     rcx, [r14+50h]
0x18004f711  mov     eax, [rcx+30h]
0x18004f714  mov     [rbx+0C0h], eax
0x18004f71a  mov     rax, [rcx+38h]
0x18004f71e  mov     [rbx+0B0h], rax
0x18004f725  mov     eax, [rcx+30h]
0x18004f728  mov     rcx, [rbx+0B8h]; lpMem
0x18004f72f  dec     eax
0x18004f731  mov     [rbx+0C4h], eax
0x18004f737  test    rcx, rcx
0x18004f73a  jz      short loc_18004F741
0x18004f73c  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18004f741  mov     ecx, [rbx+0C0h]
0x18004f747  mov     eax, 14h
0x18004f74c  mul     rcx
0x18004f74f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004f756  cmovb   rax, rcx
0x18004f75a  mov     rcx, rax; dwBytes
0x18004f75d  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18004f762  mov     [rbx+0B8h], rax
0x18004f769  test    rax, rax
0x18004f76c  jz      loc_18004F887
0x18004f772  xor     r10d, r10d
0x18004f775  cmp     [rbx+0C0h], r10d
0x18004f77c  jbe     short loc_18004F7B7
0x18004f77e  mov     rdx, [rbx+0B0h]
0x18004f785  lea     r8, [r10+r10*4]
0x18004f789  mov     rcx, [rbx+0B8h]
0x18004f790  lea     r9, [r10+r10*4]
0x18004f794  add     r9, r9
0x18004f797  inc     r10d
0x18004f79a  movups  xmm0, xmmword ptr [rdx+r9*8]
0x18004f79f  movups  xmmword ptr [rcx+r8*4], xmm0
0x18004f7a4  mov     eax, [rdx+r9*8+10h]
0x18004f7a9  mov     [rcx+r8*4+10h], eax
0x18004f7ae  cmp     r10d, [rbx+0C0h]
0x18004f7b5  jb      short loc_18004F77E
0x18004f7b7  mov     r8, r15; Size
0x18004f7ba  lea     rcx, [rbx+50h]; void *
0x18004f7be  mov     rdx, r14; Src
0x18004f7c1  call    memcpy_0
0x18004f7c6  mov     dword ptr [rbx+8], 0
0x18004f7cd  mov     eax, [rbx+8]
0x18004f7d0  mov     rcx, [rbx+230h]; lpMem
0x18004f7d7  or      eax, ebp
0x18004f7d9  mov     [rbx+8], eax
0x18004f7dc  mov     rax, [rsp+48h+arg_28]
0x18004f7e1  mov     [rbx+48h], rax
0x18004f7e5  test    rcx, rcx
0x18004f7e8  jz      short loc_18004F7FA
0x18004f7ea  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18004f7ef  mov     qword ptr [rbx+230h], 0
0x18004f7fa  test    rsi, rsi
0x18004f7fd  jz      short loc_18004F808
0x18004f7ff  mov     [rbx+230h], rsi
0x18004f806  xor     esi, esi
0x18004f808  mov     eax, [rsp+48h+arg_20]
0x18004f80c  mov     ecx, 7FFFFFFFh
0x18004f811  cmp     eax, ecx
0x18004f813  mov     [rbx+0CCh], r12d
0x18004f81a  cmovnb  eax, ecx
0x18004f81d  inc     dword ptr [rbx+16Ch]
0x18004f823  mov     rcx, [rbx+238h]
0x18004f82a  xor     edi, edi
0x18004f82c  mov     [rbx+148h], eax
0x18004f832  test    rcx, rcx
0x18004f835  jnz     loc_18004F912
0x18004f83b  mov     rcx, [rsp+48h+arg_38]; this
0x18004f843  mov     [rbx+238h], rcx
0x18004f84a  test    rcx, rcx
0x18004f84d  jnz     short loc_18004F880
0x18004f84f  test    rsi, rsi
0x18004f852  jnz     loc_18004F923
0x18004f858  mov     rbx, [rsp+48h+arg_0]
0x18004f85d  mov     eax, edi
0x18004f85f  mov     rbp, [rsp+48h+arg_10]
0x18004f864  add     rsp, 20h
0x18004f868  pop     r15
0x18004f86a  pop     r14
0x18004f86c  pop     r12
0x18004f86e  pop     rdi
0x18004f86f  pop     rsi
0x18004f870  retn
0x18004f871  mov     dword ptr [rbx+0C0h], 0
0x18004f87b  jmp     loc_18004F7B7
0x18004f880  call    ?AddReference@REFERENCED_OBJECT@@QEAAHXZ; REFERENCED_OBJECT::AddReference(void)
0x18004f885  jmp     short loc_18004F84F
0x18004f887  mov     dword ptr [rbx+0C0h], 0
0x18004f891  mov     edi, 0Eh
0x18004f896  jmp     short loc_18004F84F
0x18004f898  mov     edi, 6B5h
0x18004f89d  jmp     short loc_18004F858
0x18004f89f  mov     eax, [rbx+8]
0x18004f8a2  cmp     eax, ebp
0x18004f8a4  jnz     short loc_18004F8C3
0x18004f8a6  mov     rax, [rsp+48h+arg_28]
0x18004f8ab  cmp     [rbx+48h], rax
0x18004f8af  jnz     short loc_18004F8C3
0x18004f8b1  test    rsi, rsi
0x18004f8b4  jnz     short loc_18004F8C8
0x18004f8b6  cmp     [rbx+230h], rsi
0x18004f8bd  jz      loc_18004F808
0x18004f8c3  test    rsi, rsi
0x18004f8c6  jz      short loc_18004F908
0x18004f8c8  cmp     qword ptr [rbx+230h], 0
0x18004f8d0  jz      short loc_18004F908
0x18004f8d2  mov     rcx, rsi; pSecurityDescriptor
0x18004f8d5  call    cs:__imp_GetSecurityDescriptorLength
0x18004f8db  mov     rcx, [rbx+230h]; pSecurityDescriptor
0x18004f8e2  mov     edi, eax
0x18004f8e4  call    cs:__imp_GetSecurityDescriptorLength
0x18004f8ea  cmp     edi, eax
0x18004f8ec  jnz     short loc_18004F908
0x18004f8ee  mov     rdx, [rbx+230h]; Buf2
0x18004f8f5  mov     r8d, edi; Size
0x18004f8f8  mov     rcx, rsi; Buf1
0x18004f8fb  call    memcmp_0
0x18004f900  test    eax, eax
0x18004f902  jz      loc_18004F808
0x18004f908  mov     edi, 57h ; 'W'
0x18004f90d  jmp     loc_18004F84F
0x18004f912  mov     rax, [rcx]
0x18004f915  mov     rax, [rax+20h]
0x18004f919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f91e  jmp     loc_18004F83B
0x18004f923  mov     rcx, rsi; lpMem
0x18004f926  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18004f92b  jmp     loc_18004F858
```
