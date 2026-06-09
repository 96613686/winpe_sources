# RPC_SERVER::RegisterInterface(_RPC_SERVER_INTERFACE *,RPC_UUID *,void *,uint,uint,uint,long (*)(void *,void *),void *,RPCP_INTERFACE_GROUP *)

- ea: `0x1800900a0`
- end: `0x1800902db`
- name: `?RegisterInterface@RPC_SERVER@@QEAAJPEAU_RPC_SERVER_INTERFACE@@PEAVRPC_UUID@@PEAXIIIP6AJ22@Z2PEAVRPCP_INTERFACE_GROUP@@@Z`
- size: `571`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct _RPC_SERVER_INTERFACE *, struct _GUID *, void *DefaultManagerEpv, unsigned int, unsigned int, unsigned int, int (*)(void *, void *), PSECURITY_DESCRIPTOR pSecurityDescriptor, struct RPCP_INTERFACE_GROUP *)`
- caller_count: `5`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18008ef60`
- `0x18008eff0`
- `0x18008f090`
- `0x18008f2fc`
- `0x180090000`

## callees

- `0x18000ecac`
- `0x18000ff90`
- `0x18005b8e8`
- `0x180072f50`
- `0x1800900a0`
- `0x180091c50`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180090243`
- `ntdll!RtlLeaveCriticalSection` at `0x180090243`
- `ntdll!RtlEnterCriticalSection` at `0x1800901af`
- `ntdll!RtlEnterCriticalSection` at `0x1800901af`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18009014b`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18009014b`

## pseudocode

```c
__int64 __fastcall RPC_SERVER::RegisterInterface(
        struct _RTL_CRITICAL_SECTION *this,
        struct _RPC_SERVER_INTERFACE *a2,
        struct _GUID *a3,
        void *DefaultManagerEpv,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        int (*a8)(void *, void *),
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        struct RPCP_INTERFACE_GROUP *a10)
{
  struct _GUID *v11; // rdx
  unsigned int v12; // ebx
  struct RPC_INTERFACE *v16; // rsi
  unsigned int updated; // edi
  unsigned int v18; // r12d
  void *i; // rax
  unsigned int v20; // [rsp+50h] [rbp-39h] BYREF
  int v21; // [rsp+54h] [rbp-35h] BYREF
  int v22; // [rsp+58h] [rbp-31h] BYREF
  unsigned int v23; // [rsp+5Ch] [rbp-2Dh]
  struct RPCP_INTERFACE_GROUP *v24; // [rsp+60h] [rbp-29h]
  struct RPC_UUID *v25; // [rsp+68h] [rbp-21h]
  __int128 v26; // [rsp+70h] [rbp-19h] BYREF

  v11 = (struct _GUID *)&v26;
  v12 = a5;
  v23 = a7;
  v25 = (struct RPC_UUID *)a3;
  if ( a3 )
    v11 = a3;
  v20 = a6;
  v24 = a10;
  v21 = 0;
  v22 = 0;
  v26 = 0;
  LogEtwDebugRpcInterfaceRegistrationEvent(&a2->InterfaceId.SyntaxGUID, v11, a5, a6, pSecurityDescriptor);
  if ( a8 && (a5 & 8) != 0 )
    v12 = a5 & 0xFFFFFFF7;
  if ( (v12 & 0x100) != 0 || pSecurityDescriptor && !IsValidSecurityDescriptor(pSecurityDescriptor) )
    return 87;
  if ( a8 )
  {
    if ( (v12 & 0xC0) == 0xC0 )
      return 87;
  }
  else if ( (v12 & 0xC0) != 0 )
  {
    return 87;
  }
  if ( !DefaultManagerEpv )
  {
    DefaultManagerEpv = a2->DefaultManagerEpv;
    if ( (_DWORD)DefaultManagerEpv == -1 )
      return 87;
  }
  RtlEnterCriticalSection(this);
  v16 = RPC_SERVER::FindOrCreateInterfaceInternal(
          (RPC_SERVER *)this,
          a2,
          v12,
          a6,
          v23,
          a8,
          pSecurityDescriptor,
          &v21,
          &v22,
          v24);
  if ( v16 )
  {
    if ( v22 )
    {
      v18 = v20;
      updated = RPC_INTERFACE::UpdateRpcInterfaceInformation(v16, a2, v12, v20, v23, a8, pSecurityDescriptor, v24);
      if ( updated )
        goto LABEL_19;
    }
    else
    {
      v18 = v20;
    }
    updated = RPC_INTERFACE::RegisterTypeManager(v16, v25, DefaultManagerEpv);
    if ( (v12 & 1) != 0 )
    {
      v20 = 0;
      for ( i = SIMPLE_DICT::Next((SIMPLE_DICT *)&this[1].SpinCount, &v20);
            i;
            i = SIMPLE_DICT::Next((SIMPLE_DICT *)&this[1].SpinCount, &v20) )
      {
        updated = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)i + 88LL))(
                    i,
                    (unsigned int)this[1].LockCount,
                    v18);
        if ( updated )
          break;
      }
    }
    if ( (*((_DWORD *)v16 + 2) & 2) == 0 )
      *((_QWORD *)v16 + 69) = NtCurrentTeb()->SubProcessTag;
    goto LABEL_19;
  }
  updated = v21;
LABEL_19:
  RtlLeaveCriticalSection(this);
  return updated;
}

```

## disassembly

```asm
0x1800900a0  mov     [rsp-8+arg_18], rbx
0x1800900a5  push    rbp
0x1800900a6  push    rsi
0x1800900a7  push    rdi
0x1800900a8  push    r12
0x1800900aa  push    r13
0x1800900ac  push    r14
0x1800900ae  push    r15
0x1800900b0  lea     rbp, [rsp-7]
0x1800900b5  sub     rsp, 90h
0x1800900bc  mov     rax, cs:__security_cookie
0x1800900c3  xor     rax, rsp
0x1800900c6  mov     [rbp+37h+var_40], rax
0x1800900ca  mov     eax, [rbp+37h+arg_30]
0x1800900cd  mov     r13, rdx
0x1800900d0  mov     esi, [rbp+37h+arg_28]
0x1800900d3  lea     rdx, [rbp+37h+var_50]
0x1800900d7  mov     ebx, [rbp+37h+arg_20]
0x1800900da  test    r8, r8
0x1800900dd  mov     rdi, [rbp+37h+pSecurityDescriptor]
0x1800900e4  mov     r15, r9
0x1800900e7  mov     r12, [rbp+37h+arg_38]
0x1800900eb  mov     r14, rcx
0x1800900ee  mov     [rbp+37h+var_64], eax
0x1800900f1  lea     rcx, [r13+4]; struct _GUID *
0x1800900f5  mov     rax, [rbp+37h+arg_48]
0x1800900fc  xorps   xmm0, xmm0
0x1800900ff  mov     [rbp+37h+var_58], r8
0x180090103  cmovnz  rdx, r8; struct _GUID *
0x180090107  mov     r9d, esi; unsigned int
0x18009010a  mov     [rbp+37h+var_70], esi
0x18009010d  mov     r8d, ebx; unsigned int
0x180090110  mov     [rbp+37h+var_60], rax
0x180090114  mov     [rbp+37h+var_6C], 0
0x18009011b  mov     [rbp+37h+var_68], 0
0x180090122  movups  [rbp+37h+var_50], xmm0
0x180090126  mov     [rsp+0C0h+Src], rdi; Src
0x18009012b  call    ?LogEtwDebugRpcInterfaceRegistrationEvent@@YAXPEAU_GUID@@0IIPEAX@Z; LogEtwDebugRpcInterfaceRegistrationEvent(_GUID *,_GUID *,uint,uint,void *)
0x180090130  test    r12, r12
0x180090133  jz      short loc_18009013D
0x180090135  test    bl, 8
0x180090138  jz      short loc_18009013D
0x18009013a  and     ebx, 0FFFFFFF7h
0x18009013d  bt      ebx, 8
0x180090141  jb      short loc_180090165
0x180090143  test    rdi, rdi
0x180090146  jz      short loc_18009015B
0x180090148  mov     rcx, rdi; pSecurityDescriptor
0x18009014b  call    cs:__imp_IsValidSecurityDescriptor
0x180090152  nop     dword ptr [rax+rax+00h]
0x180090157  test    eax, eax
0x180090159  jz      short loc_180090165
0x18009015b  test    r12, r12
0x18009015e  jnz     short loc_180090192
0x180090160  test    bl, 0C0h
0x180090163  jz      short loc_18009019D
0x180090165  mov     eax, 57h ; 'W'
0x18009016a  mov     rcx, [rbp+37h+var_40]
0x18009016e  xor     rcx, rsp; StackCookie
0x180090171  call    __security_check_cookie
0x180090176  mov     rbx, [rsp+0C0h+arg_18]
0x18009017e  add     rsp, 90h
0x180090185  pop     r15
0x180090187  pop     r14
0x180090189  pop     r13
0x18009018b  pop     r12
0x18009018d  pop     rdi
0x18009018e  pop     rsi
0x18009018f  pop     rbp
0x180090190  retn
0x180090192  mov     eax, ebx
0x180090194  and     eax, 0C0h
0x180090199  cmp     al, 0C0h
0x18009019b  jz      short loc_180090165
0x18009019d  test    r15, r15
0x1800901a0  jnz     short loc_1800901AC
0x1800901a2  mov     r15, [r13+48h]
0x1800901a6  cmp     r15d, 0FFFFFFFFh
0x1800901aa  jz      short loc_180090165
0x1800901ac  mov     rcx, r14; CriticalSection
0x1800901af  call    cs:__imp_RtlEnterCriticalSection
0x1800901b6  nop     dword ptr [rax+rax+00h]
0x1800901bb  mov     rax, [rbp+37h+var_60]
0x1800901bf  mov     r9d, esi; unsigned int
0x1800901c2  mov     [rsp+0C0h+var_78], rax; struct RPCP_INTERFACE_GROUP *
0x1800901c7  mov     r8d, ebx; unsigned int
0x1800901ca  lea     rax, [rbp+37h+var_68]
0x1800901ce  mov     rdx, r13; struct _RPC_SERVER_INTERFACE *
0x1800901d1  mov     [rsp+0C0h+var_80], rax; int *
0x1800901d6  mov     rcx, r14; this
0x1800901d9  lea     rax, [rbp+37h+var_6C]
0x1800901dd  mov     [rsp+0C0h+var_88], rax; int *
0x1800901e2  mov     eax, [rbp+37h+var_64]
0x1800901e5  mov     [rsp+0C0h+var_90], rdi; void *
0x1800901ea  mov     [rsp+0C0h+var_98], r12; int (*)(void *, void *)
0x1800901ef  mov     dword ptr [rsp+0C0h+Src], eax; unsigned int
0x1800901f3  call    ?FindOrCreateInterfaceInternal@RPC_SERVER@@AEAAPEAVRPC_INTERFACE@@PEAU_RPC_SERVER_INTERFACE@@IIIP6AJPEAX1@Z1PEAJPEAHPEAVRPCP_INTERFACE_GROUP@@@Z; RPC_SERVER::FindOrCreateInterfaceInternal(_RPC_SERVER_INTERFACE *,uint,uint,uint,long (*)(void *,void *),void *,long *,int *,RPCP_INTERFACE_GROUP *)
0x1800901f8  mov     rsi, rax
0x1800901fb  test    rax, rax
0x1800901fe  jnz     short loc_180090205
0x180090200  mov     edi, [rbp+37h+var_6C]
0x180090203  jmp     short loc_180090240
0x180090205  cmp     [rbp+37h+var_68], 0
0x180090209  jz      short loc_180090256
0x18009020b  mov     rax, [rbp+37h+var_60]
0x18009020f  mov     r8d, ebx; unsigned int
0x180090212  mov     [rsp+0C0h+var_88], rax; struct RPCP_INTERFACE_GROUP *
0x180090217  mov     rdx, r13; struct _RPC_SERVER_INTERFACE *
0x18009021a  mov     eax, [rbp+37h+var_64]
0x18009021d  mov     rcx, rsi; this
0x180090220  mov     [rsp+0C0h+var_90], rdi; void *
0x180090225  mov     [rsp+0C0h+var_98], r12; int (*)(void *, void *)
0x18009022a  mov     r12d, [rbp+37h+var_70]
0x18009022e  mov     r9d, r12d; unsigned int
0x180090231  mov     dword ptr [rsp+0C0h+Src], eax; unsigned int
0x180090235  call    ?UpdateRpcInterfaceInformation@RPC_INTERFACE@@QEAAJPEAU_RPC_SERVER_INTERFACE@@IIIP6AJPEAX1@Z1PEAVRPCP_INTERFACE_GROUP@@@Z; RPC_INTERFACE::UpdateRpcInterfaceInformation(_RPC_SERVER_INTERFACE *,uint,uint,uint,long (*)(void *,void *),void *,RPCP_INTERFACE_GROUP *)
0x18009023a  mov     edi, eax
0x18009023c  test    eax, eax
0x18009023e  jz      short loc_18009025A
0x180090240  mov     rcx, r14; CriticalSection
0x180090243  call    cs:__imp_RtlLeaveCriticalSection
0x18009024a  nop     dword ptr [rax+rax+00h]
0x18009024f  mov     eax, edi
0x180090251  jmp     loc_18009016A
0x180090256  mov     r12d, [rbp+37h+var_70]
0x18009025a  mov     rdx, [rbp+37h+var_58]; struct RPC_UUID *
0x18009025e  mov     r8, r15; void *
0x180090261  mov     rcx, rsi; this
0x180090264  call    ?RegisterTypeManager@RPC_INTERFACE@@QEAAJPEAVRPC_UUID@@PEAX@Z; RPC_INTERFACE::RegisterTypeManager(RPC_UUID *,void *)
0x180090269  mov     edi, eax
0x18009026b  test    bl, 1
0x18009026e  jz      short loc_1800902B7
0x180090270  lea     rdx, [rbp+37h+var_70]; unsigned int *
0x180090274  mov     [rbp+37h+var_70], 0
0x18009027b  lea     rcx, [r14+48h]; this
0x18009027f  call    ?Next@SIMPLE_DICT@@QEAAPEAXAEAI@Z; SIMPLE_DICT::Next(uint &)
0x180090284  jmp     short loc_1800902AF
0x180090286  mov     rcx, [r9]
0x180090289  mov     r8d, r12d
0x18009028c  mov     edx, [r14+30h]
0x180090290  mov     rax, [rcx+58h]
0x180090294  mov     rcx, r9
0x180090297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009029c  mov     edi, eax
0x18009029e  test    eax, eax
0x1800902a0  jnz     short loc_1800902B7
0x1800902a2  lea     rdx, [rbp+37h+var_70]; unsigned int *
0x1800902a6  lea     rcx, [r14+48h]; this
0x1800902aa  call    ?Next@SIMPLE_DICT@@QEAAPEAXAEAI@Z; SIMPLE_DICT::Next(uint &)
0x1800902af  mov     r9, rax
0x1800902b2  test    rax, rax
0x1800902b5  jnz     short loc_180090286
0x1800902b7  mov     ecx, [rsi+8]
0x1800902ba  test    cl, 2
0x1800902bd  jnz     short loc_180090240
0x1800902bf  mov     rcx, gs:30h
0x1800902c8  mov     rdx, [rcx+1720h]
0x1800902cf  mov     [rsi+228h], rdx
0x1800902d6  jmp     loc_180090240
```
