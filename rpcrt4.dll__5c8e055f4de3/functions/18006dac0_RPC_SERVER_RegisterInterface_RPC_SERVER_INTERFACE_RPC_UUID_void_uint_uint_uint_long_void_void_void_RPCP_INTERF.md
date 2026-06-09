# RPC_SERVER::RegisterInterface(_RPC_SERVER_INTERFACE *,RPC_UUID *,void *,uint,uint,uint,long (*)(void *,void *),void *,RPCP_INTERFACE_GROUP *)

- ea: `0x18006dac0`
- end: `0x18006dce8`
- name: `?RegisterInterface@RPC_SERVER@@QEAAJPEAU_RPC_SERVER_INTERFACE@@PEAVRPC_UUID@@PEAXIIIP6AJ22@Z2PEAVRPCP_INTERFACE_GROUP@@@Z`
- size: `552`
- prototype: `__int64 __fastcall(RPC_SERVER *__hidden this, struct _RPC_SERVER_INTERFACE *, struct _GUID *, void *, unsigned int, unsigned int, unsigned int, int (*)(void *, void *), PSECURITY_DESCRIPTOR pSecurityDescriptor, struct RPCP_INTERFACE_GROUP *)`
- caller_count: `5`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006cddc`
- `0x18006da20`
- `0x18006e1e0`
- `0x18006e270`
- `0x18006e310`

## callees

- `0x180048bc8`
- `0x18004e484`
- `0x18004f690`
- `0x18006dac0`
- `0x180070400`
- `0x18008e148`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18006dc56`
- `ntdll!RtlLeaveCriticalSection` at `0x18006dc56`
- `ntdll!RtlEnterCriticalSection` at `0x18006dbc8`
- `ntdll!RtlEnterCriticalSection` at `0x18006dbc8`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18006db6b`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18006db6b`

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
0x18006dac0  mov     [rsp-8+arg_18], rbx
0x18006dac5  push    rbp
0x18006dac6  push    rsi
0x18006dac7  push    rdi
0x18006dac8  push    r12
0x18006daca  push    r13
0x18006dacc  push    r14
0x18006dace  push    r15
0x18006dad0  lea     rbp, [rsp-7]
0x18006dad5  sub     rsp, 90h
0x18006dadc  mov     rax, cs:__security_cookie
0x18006dae3  xor     rax, rsp
0x18006dae6  mov     [rbp+37h+var_40], rax
0x18006daea  mov     eax, [rbp+37h+arg_30]
0x18006daed  mov     r13, rdx
0x18006daf0  mov     esi, [rbp+37h+arg_28]
0x18006daf3  lea     rdx, [rbp+37h+var_50]
0x18006daf7  mov     ebx, [rbp+37h+arg_20]
0x18006dafa  test    r8, r8
0x18006dafd  mov     rdi, [rbp+37h+pSecurityDescriptor]
0x18006db04  mov     r15, r9
0x18006db07  mov     r12, [rbp+37h+arg_38]
0x18006db0b  mov     r14, rcx
0x18006db0e  mov     [rbp+37h+var_64], eax
0x18006db11  lea     rcx, [r13+4]; struct _GUID *
0x18006db15  mov     rax, [rbp+37h+arg_48]
0x18006db1c  xorps   xmm0, xmm0
0x18006db1f  mov     [rbp+37h+var_58], r8
0x18006db23  cmovnz  rdx, r8; struct _GUID *
0x18006db27  mov     r9d, esi; unsigned int
0x18006db2a  mov     [rbp+37h+var_70], esi
0x18006db2d  mov     r8d, ebx; unsigned int
0x18006db30  mov     [rbp+37h+var_60], rax
0x18006db34  mov     [rbp+37h+var_6C], 0
0x18006db3b  mov     [rbp+37h+var_68], 0
0x18006db42  movups  [rbp+37h+var_50], xmm0
0x18006db46  mov     [rsp+0C0h+Src], rdi; Src
0x18006db4b  call    ?LogEtwDebugRpcInterfaceRegistrationEvent@@YAXPEAU_GUID@@0IIPEAX@Z; LogEtwDebugRpcInterfaceRegistrationEvent(_GUID *,_GUID *,uint,uint,void *)
0x18006db50  test    r12, r12
0x18006db53  jz      short loc_18006DB5D
0x18006db55  test    bl, 8
0x18006db58  jz      short loc_18006DB5D
0x18006db5a  and     ebx, 0FFFFFFF7h
0x18006db5d  bt      ebx, 8
0x18006db61  jb      short loc_18006DB7F
0x18006db63  test    rdi, rdi
0x18006db66  jz      short loc_18006DB75
0x18006db68  mov     rcx, rdi; pSecurityDescriptor
0x18006db6b  call    cs:__imp_IsValidSecurityDescriptor
0x18006db71  test    eax, eax
0x18006db73  jz      short loc_18006DB7F
0x18006db75  test    r12, r12
0x18006db78  jnz     short loc_18006DBAB
0x18006db7a  test    bl, 0C0h
0x18006db7d  jz      short loc_18006DBB6
0x18006db7f  mov     eax, 57h ; 'W'
0x18006db84  mov     rcx, [rbp+37h+var_40]
0x18006db88  xor     rcx, rsp; StackCookie
0x18006db8b  call    __security_check_cookie
0x18006db90  mov     rbx, [rsp+0C0h+arg_18]
0x18006db98  add     rsp, 90h
0x18006db9f  pop     r15
0x18006dba1  pop     r14
0x18006dba3  pop     r13
0x18006dba5  pop     r12
0x18006dba7  pop     rdi
0x18006dba8  pop     rsi
0x18006dba9  pop     rbp
0x18006dbaa  retn
0x18006dbab  mov     eax, ebx
0x18006dbad  and     eax, 0C0h
0x18006dbb2  cmp     al, 0C0h
0x18006dbb4  jz      short loc_18006DB7F
0x18006dbb6  test    r15, r15
0x18006dbb9  jnz     short loc_18006DBC5
0x18006dbbb  mov     r15, [r13+48h]
0x18006dbbf  cmp     r15d, 0FFFFFFFFh
0x18006dbc3  jz      short loc_18006DB7F
0x18006dbc5  mov     rcx, r14; CriticalSection
0x18006dbc8  call    cs:__imp_RtlEnterCriticalSection
0x18006dbce  mov     rax, [rbp+37h+var_60]
0x18006dbd2  mov     r9d, esi; unsigned int
0x18006dbd5  mov     [rsp+0C0h+var_78], rax; struct RPCP_INTERFACE_GROUP *
0x18006dbda  mov     r8d, ebx; unsigned int
0x18006dbdd  lea     rax, [rbp+37h+var_68]
0x18006dbe1  mov     rdx, r13; struct _RPC_SERVER_INTERFACE *
0x18006dbe4  mov     [rsp+0C0h+var_80], rax; int *
0x18006dbe9  mov     rcx, r14; this
0x18006dbec  lea     rax, [rbp+37h+var_6C]
0x18006dbf0  mov     [rsp+0C0h+var_88], rax; int *
0x18006dbf5  mov     eax, [rbp+37h+var_64]
0x18006dbf8  mov     [rsp+0C0h+var_90], rdi; void *
0x18006dbfd  mov     [rsp+0C0h+var_98], r12; int (*)(void *, void *)
0x18006dc02  mov     dword ptr [rsp+0C0h+Src], eax; unsigned int
0x18006dc06  call    ?FindOrCreateInterfaceInternal@RPC_SERVER@@AEAAPEAVRPC_INTERFACE@@PEAU_RPC_SERVER_INTERFACE@@IIIP6AJPEAX1@Z1PEAJPEAHPEAVRPCP_INTERFACE_GROUP@@@Z; RPC_SERVER::FindOrCreateInterfaceInternal(_RPC_SERVER_INTERFACE *,uint,uint,uint,long (*)(void *,void *),void *,long *,int *,RPCP_INTERFACE_GROUP *)
0x18006dc0b  mov     rsi, rax
0x18006dc0e  test    rax, rax
0x18006dc11  jnz     short loc_18006DC18
0x18006dc13  mov     edi, [rbp+37h+var_6C]
0x18006dc16  jmp     short loc_18006DC53
0x18006dc18  cmp     [rbp+37h+var_68], 0
0x18006dc1c  jz      short loc_18006DC63
0x18006dc1e  mov     rax, [rbp+37h+var_60]
0x18006dc22  mov     r8d, ebx; unsigned int
0x18006dc25  mov     [rsp+0C0h+var_88], rax; struct RPCP_INTERFACE_GROUP *
0x18006dc2a  mov     rdx, r13; struct _RPC_SERVER_INTERFACE *
0x18006dc2d  mov     eax, [rbp+37h+var_64]
0x18006dc30  mov     rcx, rsi; this
0x18006dc33  mov     [rsp+0C0h+var_90], rdi; void *
0x18006dc38  mov     [rsp+0C0h+var_98], r12; int (*)(void *, void *)
0x18006dc3d  mov     r12d, [rbp+37h+var_70]
0x18006dc41  mov     r9d, r12d; unsigned int
0x18006dc44  mov     dword ptr [rsp+0C0h+Src], eax; unsigned int
0x18006dc48  call    ?UpdateRpcInterfaceInformation@RPC_INTERFACE@@QEAAJPEAU_RPC_SERVER_INTERFACE@@IIIP6AJPEAX1@Z1PEAVRPCP_INTERFACE_GROUP@@@Z; RPC_INTERFACE::UpdateRpcInterfaceInformation(_RPC_SERVER_INTERFACE *,uint,uint,uint,long (*)(void *,void *),void *,RPCP_INTERFACE_GROUP *)
0x18006dc4d  mov     edi, eax
0x18006dc4f  test    eax, eax
0x18006dc51  jz      short loc_18006DC67
0x18006dc53  mov     rcx, r14; CriticalSection
0x18006dc56  call    cs:__imp_RtlLeaveCriticalSection
0x18006dc5c  mov     eax, edi
0x18006dc5e  jmp     loc_18006DB84
0x18006dc63  mov     r12d, [rbp+37h+var_70]
0x18006dc67  mov     rdx, [rbp+37h+var_58]; struct RPC_UUID *
0x18006dc6b  mov     r8, r15; void *
0x18006dc6e  mov     rcx, rsi; this
0x18006dc71  call    ?RegisterTypeManager@RPC_INTERFACE@@QEAAJPEAVRPC_UUID@@PEAX@Z; RPC_INTERFACE::RegisterTypeManager(RPC_UUID *,void *)
0x18006dc76  mov     edi, eax
0x18006dc78  test    bl, 1
0x18006dc7b  jz      short loc_18006DCC4
0x18006dc7d  lea     rdx, [rbp+37h+var_70]; unsigned int *
0x18006dc81  mov     [rbp+37h+var_70], 0
0x18006dc88  lea     rcx, [r14+48h]; this
0x18006dc8c  call    ?Next@SIMPLE_DICT@@QEAAPEAXAEAI@Z; SIMPLE_DICT::Next(uint &)
0x18006dc91  jmp     short loc_18006DCBC
0x18006dc93  mov     rcx, [r9]
0x18006dc96  mov     r8d, r12d
0x18006dc99  mov     edx, [r14+30h]
0x18006dc9d  mov     rax, [rcx+58h]
0x18006dca1  mov     rcx, r9
0x18006dca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dca9  mov     edi, eax
0x18006dcab  test    eax, eax
0x18006dcad  jnz     short loc_18006DCC4
0x18006dcaf  lea     rdx, [rbp+37h+var_70]; unsigned int *
0x18006dcb3  lea     rcx, [r14+48h]; this
0x18006dcb7  call    ?Next@SIMPLE_DICT@@QEAAPEAXAEAI@Z; SIMPLE_DICT::Next(uint &)
0x18006dcbc  mov     r9, rax
0x18006dcbf  test    rax, rax
0x18006dcc2  jnz     short loc_18006DC93
0x18006dcc4  mov     ecx, [rsi+8]
0x18006dcc7  test    cl, 2
0x18006dcca  jnz     short loc_18006DC53
0x18006dccc  mov     rcx, gs:30h
0x18006dcd5  mov     rdx, [rcx+1720h]
0x18006dcdc  mov     [rsi+228h], rdx
0x18006dce3  jmp     loc_18006DC53
```
