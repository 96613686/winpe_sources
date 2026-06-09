# RPC_SERVER::FindOrCreateInterfaceInternal(_RPC_SERVER_INTERFACE *,uint,uint,uint,long (*)(void *,void *),void *,long *,int *,RPCP_INTERFACE_GROUP *)

- ea: `0x18000ecac`
- end: `0x18000f07e`
- name: `?FindOrCreateInterfaceInternal@RPC_SERVER@@AEAAPEAVRPC_INTERFACE@@PEAU_RPC_SERVER_INTERFACE@@IIIP6AJPEAX1@Z1PEAJPEAHPEAVRPCP_INTERFACE_GROUP@@@Z`
- size: `978`
- prototype: `struct RPC_INTERFACE *__fastcall(RPC_SERVER *__hidden this, struct _RPC_SERVER_INTERFACE *, unsigned int, unsigned int, unsigned int, int (*)(void *, void *), void *, int *, int *, struct RPCP_INTERFACE_GROUP *)`
- caller_count: `2`
- callee_count: `16`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d31c`
- `0x1800900a0`

## callees

- `0x18000ecac`
- `0x18000f084`
- `0x18000f110`
- `0x18000fd70`
- `0x18000fe44`
- `0x18000ff20`
- `0x180023020`
- `0x180072f50`
- `0x1800995e8`
- `0x1800a5e7c`
- `0x1800a8098`
- `0x1800adb74`
- `0x1800adc00`
- `0x1800b7800`
- `0x1800ce5d0`
- `0x1800d7010`

## import_xrefs

- `ntdll!_wcsicmp` at `0x18000ef67`
- `ntdll!_wcsicmp` at `0x18000ef67`
- `ntdll!DbgPrint` at `0x18000ef18`
- `ntdll!DbgPrint` at `0x18000ef2b`
- `ntdll!DbgPrint` at `0x18000ef46`
- `ntdll!DbgPrint` at `0x18000ef86`
- `ntdll!DbgPrint` at `0x18000efaf`
- `ntdll!DbgPrint` at `0x18000efcf`
- `ntdll!DbgPrint` at `0x18000f00c`
- `ntdll!DbgPrint` at `0x18000f01f`
- `ntdll!DbgPrint` at `0x18000f03a`
- `ntdll!DbgPrint` at `0x18000f04d`
- `ntdll!DbgPrint` at `0x18000f06d`
- `ntdll!DbgPrint` at `0x18000ef18`
- `ntdll!DbgPrint` at `0x18000ef2b`
- `ntdll!DbgPrint` at `0x18000ef46`
- `ntdll!DbgPrint` at `0x18000ef86`
- `ntdll!DbgPrint` at `0x18000efaf`
- `ntdll!DbgPrint` at `0x18000efcf`
- `ntdll!DbgPrint` at `0x18000f00c`
- `ntdll!DbgPrint` at `0x18000f01f`
- `ntdll!DbgPrint` at `0x18000f03a`
- `ntdll!DbgPrint` at `0x18000f04d`
- `ntdll!DbgPrint` at `0x18000f06d`
- `ntdll!WinSqmIncrementDWORD` at `0x18000edc1`
- `ntdll!WinSqmIncrementDWORD` at `0x18000edc1`

## string_xrefs

- `0x18000efc8`: `RPC: To determine the symbolic stack, do an "ln" on the above addresses in the context of the faulting process.\n\n`
- `0x18000f066`: `RPC: To determine the symbolic stack, do an "ln" on the above addresses in the context of the faulting process.\n\n`
- `0x18000ef0a`: `Possible security threat: Server that is remotely accessible is registering an insecure interface`
- `0x18000effe`: `Possible security threat: Server registers an interface compiled without /robust option`

## pseudocode

```c
struct RPC_INTERFACE *__fastcall RPC_SERVER::FindOrCreateInterfaceInternal(
        RPC_SERVER *this,
        struct _RPC_SERVER_INTERFACE *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        int (*a6)(void *, void *),
        void *a7,
        int *a8,
        int *a9,
        struct RPCP_INTERFACE_GROUP *a10)
{
  unsigned int v14; // ebp
  struct RPC_INTERFACE *Interface; // rbx
  RPC_INTERFACE *v16; // rax
  RPC_INTERFACE *v17; // rax
  unsigned int v18; // edx
  unsigned int v19; // edx
  int FirewallExtensionIfNecessary; // eax
  int v21; // eax
  int v23; // eax
  unsigned int *v24; // rdx
  const wchar_t **v25; // rax
  const wchar_t **v26; // rdi
  unsigned int v27; // [rsp+50h] [rbp-58h] BYREF
  unsigned int *v28; // [rsp+58h] [rbp-50h] BYREF

  v14 = 0;
  Interface = RPC_SERVER::FindInterface(this, a2);
  if ( Interface )
  {
    v21 = 1;
LABEL_10:
    *a9 = v21;
    *a8 = 0;
    if ( (unsigned int)CheckForRobust(a2) )
      WinSqmIncrementDWORD(0, 1201, 1);
    if ( !gfRPCVerifierEnabled || *((_DWORD *)pRpcVerifierSettings + 33) || *a9 )
      return Interface;
    if ( (unsigned int)RPC_INTERFACE::IsSecure(Interface) )
    {
      if ( (a3 & 2) == 0 )
      {
LABEL_40:
        if ( (unsigned int)CheckForRobust((struct _RPC_SERVER_INTERFACE *)((char *)Interface + 80)) )
        {
          DbgPrint(
            "%s : type (0x%x)",
            "Possible security threat: Server registers an interface compiled without /robust option",
            112);
          DbgPrint("RPC: Insecure interface UUID: ");
          DbgPrintUUID((struct _GUID *)((char *)Interface + 84));
          DbgPrint("\n");
          DbgPrint("RPC: Offending Stack:\n");
          PrintCurrentStackTrace(2u, 4u);
          DbgPrint(
            "RPC: To determine the symbolic stack, do an \"ln\" on the above addresses in the context of the faulting process.\n\n");
        }
      }
    }
    else if ( (a3 & 2) == 0 )
    {
      if ( !(unsigned int)IsInterfaceExempt((struct _GUID *)((char *)Interface + 84), 1u) )
      {
        gfUnsecureInterfaceRegistered = 1;
        if ( gfRemoteProtseqRegistered )
        {
          DbgPrint(
            "%s : type (0x%x)",
            "Possible security threat: Server that is remotely accessible is registering an insecure interface",
            16);
          DbgPrint("RPC: Insecure interface UUID: ");
          DbgPrintUUID((struct _GUID *)((char *)Interface + 84));
          DbgPrint("\n");
          v27 = 0;
          while ( 1 )
          {
            v25 = (const wchar_t **)SIMPLE_DICT::Next((RPC_SERVER *)((char *)this + 72), &v27);
            v26 = v25;
            if ( !v25 )
              break;
            if ( _wcsicmp(v25[5], L"ncalrpc") )
              DbgPrint("RPC: Listening on protseq: %S endpoint: %S\n", v26[5], v26[4]);
          }
          DbgPrint("RPC: Offending Stack:\n");
          PrintCurrentStackTrace(2u, 4u);
          DbgPrint(
            "RPC: To determine the symbolic stack, do an \"ln\" on the above addresses in the context of the faulting process.\n\n");
        }
      }
      goto LABEL_40;
    }
    return Interface;
  }
  v16 = (RPC_INTERFACE *)AllocWrapper(0x240u);
  if ( !v16 )
    goto LABEL_20;
  v17 = RPC_INTERFACE::RPC_INTERFACE(v16, a2, this, a3, a4, a5, a6, a7, a8, a10);
  Interface = v17;
  if ( !v17 )
    goto LABEL_20;
  if ( !*a8 )
  {
    if ( SIMPLE_DICT::Insert((RPC_SERVER *)((char *)this + 288), v17) != -1 )
    {
      if ( (NtCurrentPeb()->ProcessParameters->Flags & 0x80000000) != 0 )
      {
        gFwExtensionState = 2;
        goto LABEL_9;
      }
      FirewallExtensionIfNecessary = LoadFirewallExtensionIfNecessary();
      *a8 = FirewallExtensionIfNecessary;
      if ( FirewallExtensionIfNecessary != 14 )
      {
        if ( FirewallExtensionIfNecessary )
        {
LABEL_9:
          v21 = 0;
          goto LABEL_10;
        }
        v27 = 0;
        v28 = 0;
        v23 = (*(__int64 (__fastcall **)(struct _RPC_SERVER_INTERFACE *, unsigned int *, unsigned int **))qword_1800FF548)(
                a2,
                &v27,
                &v28);
        *a8 = v23;
        if ( !v23 )
        {
          if ( v27 )
            *((_DWORD *)Interface + 14) |= 4u;
          v24 = v28;
          if ( v28 && *v28 )
          {
            do
            {
              RPC_INTERFACE::EpAdd(Interface, (struct _FwEp *)&v24[6 * v14 + 2]);
              v24 = v28;
              ++v14;
            }
            while ( v14 < *v28 );
          }
          goto LABEL_9;
        }
      }
      RPC_SERVER::RemoveInterface(this, Interface);
      goto LABEL_16;
    }
    RPC_INTERFACE::`scalar deleting destructor'(Interface, v19);
LABEL_20:
    *a8 = 14;
    return 0;
  }
LABEL_16:
  RPC_INTERFACE::`scalar deleting destructor'(Interface, v18);
  return 0;
}

```

## disassembly

```asm
0x18000ecac  push    rbx
0x18000ecae  push    rbp
0x18000ecaf  push    rsi
0x18000ecb0  push    rdi
0x18000ecb1  push    r12
0x18000ecb3  push    r13
0x18000ecb5  push    r14
0x18000ecb7  push    r15
0x18000ecb9  sub     rsp, 68h
0x18000ecbd  mov     esi, r9d
0x18000ecc0  mov     r13d, r8d
0x18000ecc3  mov     r12, rdx
0x18000ecc6  mov     r14, rcx
0x18000ecc9  call    ?FindInterface@RPC_SERVER@@QEAAPEAVRPC_INTERFACE@@PEAU_RPC_SERVER_INTERFACE@@@Z; RPC_SERVER::FindInterface(_RPC_SERVER_INTERFACE *)
0x18000ecce  mov     rdi, [rsp+0A8h+arg_38]
0x18000ecd6  xor     ebp, ebp
0x18000ecd8  mov     rbx, rax
0x18000ecdb  test    rax, rax
0x18000ecde  jnz     loc_18000EE30
0x18000ece4  mov     ecx, 240h; dwBytes
0x18000ece9  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18000ecee  test    rax, rax
0x18000ecf1  jz      loc_18000EE44
0x18000ecf7  mov     rcx, [rsp+0A8h+arg_48]
0x18000ecff  mov     r9d, r13d; unsigned int
0x18000ed02  mov     [rsp+0A8h+var_60], rcx; struct RPCP_INTERFACE_GROUP *
0x18000ed07  mov     r8, r14; struct RPC_SERVER *
0x18000ed0a  mov     rcx, [rsp+0A8h+arg_30]
0x18000ed12  mov     rdx, r12; struct _RPC_SERVER_INTERFACE *
0x18000ed15  mov     [rsp+0A8h+var_68], rdi; int *
0x18000ed1a  mov     [rsp+0A8h+var_70], rcx; void *
0x18000ed1f  mov     rcx, [rsp+0A8h+arg_28]
0x18000ed27  mov     [rsp+0A8h+var_78], rcx; int (*)(void *, void *)
0x18000ed2c  mov     ecx, [rsp+0A8h+arg_20]
0x18000ed33  mov     [rsp+0A8h+var_80], ecx; unsigned int
0x18000ed37  mov     rcx, rax; this
0x18000ed3a  mov     [rsp+0A8h+var_88], esi; unsigned int
0x18000ed3e  call    ??0RPC_INTERFACE@@QEAA@PEAU_RPC_SERVER_INTERFACE@@PEAVRPC_SERVER@@IIIP6AJPEAX2@Z2PEAJPEAVRPCP_INTERFACE_GROUP@@@Z; RPC_INTERFACE::RPC_INTERFACE(_RPC_SERVER_INTERFACE *,RPC_SERVER *,uint,uint,uint,long (*)(void *,void *),void *,long *,RPCP_INTERFACE_GROUP *)
0x18000ed43  mov     rbx, rax
0x18000ed46  test    rax, rax
0x18000ed49  jz      loc_18000EE44
0x18000ed4f  cmp     [rdi], ebp
0x18000ed51  jnz     loc_18000EE24
0x18000ed57  lea     rcx, [r14+120h]; this
0x18000ed5e  mov     rdx, rax; void *
0x18000ed61  call    ?Insert@SIMPLE_DICT@@QEAAIPEAX@Z; SIMPLE_DICT::Insert(void *)
0x18000ed66  cmp     eax, 0FFFFFFFFh
0x18000ed69  jz      loc_18000EE3C
0x18000ed6f  mov     rax, gs:60h
0x18000ed78  lea     esi, [rbp+1]
0x18000ed7b  mov     rcx, [rax+20h]
0x18000ed7f  cmp     [rcx+8], ebp
0x18000ed82  jl      loc_18000EE4C
0x18000ed88  call    ?LoadFirewallExtensionIfNecessary@@YAJXZ; LoadFirewallExtensionIfNecessary(void)
0x18000ed8d  mov     [rdi], eax
0x18000ed8f  cmp     eax, 0Eh
0x18000ed92  jz      loc_18000EE19
0x18000ed98  test    eax, eax
0x18000ed9a  jz      short loc_18000EDEE
0x18000ed9c  mov     eax, ebp
0x18000ed9e  mov     r15, [rsp+0A8h+arg_40]
0x18000eda6  mov     rcx, r12; struct _RPC_SERVER_INTERFACE *
0x18000eda9  mov     [r15], eax
0x18000edac  mov     [rdi], ebp
0x18000edae  call    ?CheckForRobust@@YAJPEAU_RPC_SERVER_INTERFACE@@@Z; CheckForRobust(_RPC_SERVER_INTERFACE *)
0x18000edb3  test    eax, eax
0x18000edb5  jz      short loc_18000EDCD
0x18000edb7  mov     r8d, esi
0x18000edba  mov     edx, 4B1h
0x18000edbf  xor     ecx, ecx
0x18000edc1  call    cs:__imp_WinSqmIncrementDWORD
0x18000edc8  nop     dword ptr [rax+rax+00h]
0x18000edcd  cmp     cs:?gfRPCVerifierEnabled@@3HA, ebp; int gfRPCVerifierEnabled
0x18000edd3  jnz     loc_18000EEA8
0x18000edd9  mov     rax, rbx
0x18000eddc  add     rsp, 68h
0x18000ede0  pop     r15
0x18000ede2  pop     r14
0x18000ede4  pop     r13
0x18000ede6  pop     r12
0x18000ede8  pop     rdi
0x18000ede9  pop     rsi
0x18000edea  pop     rbp
0x18000edeb  pop     rbx
0x18000edec  retn
0x18000edee  mov     rax, cs:qword_1800FF548
0x18000edf5  lea     r8, [rsp+0A8h+var_50]
0x18000edfa  mov     [rsp+0A8h+var_58], ebp
0x18000edfe  lea     rdx, [rsp+0A8h+var_58]
0x18000ee03  mov     [rsp+0A8h+var_50], rbp
0x18000ee08  mov     rcx, r12
0x18000ee0b  mov     rax, [rax]
0x18000ee0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee13  mov     [rdi], eax
0x18000ee15  test    eax, eax
0x18000ee17  jz      short loc_18000EE5B
0x18000ee19  mov     rdx, rbx; struct RPC_INTERFACE *
0x18000ee1c  mov     rcx, r14; this
0x18000ee1f  call    ?RemoveInterface@RPC_SERVER@@QEAAHPEAVRPC_INTERFACE@@@Z; RPC_SERVER::RemoveInterface(RPC_INTERFACE *)
0x18000ee24  mov     rcx, rbx; this
0x18000ee27  call    ??_GRPC_INTERFACE@@QEAAPEAXI@Z; RPC_INTERFACE::`scalar deleting destructor'(uint)
0x18000ee2c  xor     eax, eax
0x18000ee2e  jmp     short loc_18000EDDC
0x18000ee30  mov     esi, 1
0x18000ee35  mov     eax, esi
0x18000ee37  jmp     loc_18000ED9E
0x18000ee3c  mov     rcx, rbx; this
0x18000ee3f  call    ??_GRPC_INTERFACE@@QEAAPEAXI@Z; RPC_INTERFACE::`scalar deleting destructor'(uint)
0x18000ee44  mov     dword ptr [rdi], 0Eh
0x18000ee4a  jmp     short loc_18000EE2C
0x18000ee4c  mov     cs:?gFwExtensionState@@3W4FwExtensionState@@A, 2; FwExtensionState gFwExtensionState
0x18000ee56  jmp     loc_18000ED9C
0x18000ee5b  cmp     [rsp+0A8h+var_58], ebp
0x18000ee5f  jz      short loc_18000EE6A
0x18000ee61  mov     eax, [rbx+38h]
0x18000ee64  or      eax, 4
0x18000ee67  mov     [rbx+38h], eax
0x18000ee6a  mov     rdx, [rsp+0A8h+var_50]
0x18000ee6f  test    rdx, rdx
0x18000ee72  jz      loc_18000ED9C
0x18000ee78  cmp     [rdx], ebp
0x18000ee7a  jbe     loc_18000ED9C
0x18000ee80  mov     eax, ebp
0x18000ee82  lea     rcx, [rax+rax*2]
0x18000ee86  lea     rdx, [rdx+rcx*8]
0x18000ee8a  mov     rcx, rbx; this
0x18000ee8d  add     rdx, 8; struct _FwEp *
0x18000ee91  call    ?EpAdd@RPC_INTERFACE@@QEAAXPEAU_FwEp@@@Z; RPC_INTERFACE::EpAdd(_FwEp *)
0x18000ee96  mov     rdx, [rsp+0A8h+var_50]
0x18000ee9b  add     ebp, esi
0x18000ee9d  cmp     ebp, [rdx]
0x18000ee9f  jb      short loc_18000EE80
0x18000eea1  xor     ebp, ebp
0x18000eea3  jmp     loc_18000ED9C
0x18000eea8  mov     rax, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x18000eeaf  cmp     [rax+84h], ebp
0x18000eeb5  jnz     loc_18000EDD9
0x18000eebb  cmp     [r15], ebp
0x18000eebe  jnz     loc_18000EDD9
0x18000eec4  mov     rcx, rbx; this
0x18000eec7  lea     rbp, [rbx+54h]
0x18000eecb  call    ?IsSecure@RPC_INTERFACE@@QEAAHXZ; RPC_INTERFACE::IsSecure(void)
0x18000eed0  test    eax, eax
0x18000eed2  jnz     loc_18000EFDD
0x18000eed8  test    r13b, 2
0x18000eedc  jnz     loc_18000EDD9
0x18000eee2  mov     edx, esi; unsigned int
0x18000eee4  mov     rcx, rbp; struct _GUID *
0x18000eee7  call    ?IsInterfaceExempt@@YAHPEAU_GUID@@K@Z; IsInterfaceExempt(_GUID *,ulong)
0x18000eeec  test    eax, eax
0x18000eeee  jnz     loc_18000EFE7
0x18000eef4  cmp     cs:?gfRemoteProtseqRegistered@@3HA, eax; int gfRemoteProtseqRegistered
0x18000eefa  mov     cs:?gfUnsecureInterfaceRegistered@@3HA, esi; int gfUnsecureInterfaceRegistered
0x18000ef00  jz      loc_18000EFE7
0x18000ef06  lea     r8d, [rax+10h]
0x18000ef0a  lea     rdx, aPossibleSecuri_3; "Possible security threat: Server that i"...
0x18000ef11  lea     rcx, Format; "%s : type (0x%x)"
0x18000ef18  call    cs:__imp_DbgPrint
0x18000ef1f  nop     dword ptr [rax+rax+00h]
0x18000ef24  lea     rcx, aRpcInsecureInt; "RPC: Insecure interface UUID: "
0x18000ef2b  call    cs:__imp_DbgPrint
0x18000ef32  nop     dword ptr [rax+rax+00h]
0x18000ef37  mov     rcx, rbp; struct _GUID *
0x18000ef3a  call    ?DbgPrintUUID@@YAXPEAU_GUID@@@Z; DbgPrintUUID(_GUID *)
0x18000ef3f  lea     rcx, asc_1800E9378; "\n"
0x18000ef46  call    cs:__imp_DbgPrint
0x18000ef4d  nop     dword ptr [rax+rax+00h]
0x18000ef52  mov     [rsp+0A8h+var_58], 0
0x18000ef5a  jmp     short loc_18000EF92
0x18000ef5c  mov     rcx, [rdi+28h]; String1
0x18000ef60  lea     rdx, aNcalrpc; "ncalrpc"
0x18000ef67  call    cs:__imp__wcsicmp
0x18000ef6e  nop     dword ptr [rax+rax+00h]
0x18000ef73  test    eax, eax
0x18000ef75  jz      short loc_18000EF92
0x18000ef77  mov     r8, [rdi+20h]
0x18000ef7b  lea     rcx, aRpcListeningOn; "RPC: Listening on protseq: %S endpoint:"...
0x18000ef82  mov     rdx, [rdi+28h]
0x18000ef86  call    cs:__imp_DbgPrint
0x18000ef8d  nop     dword ptr [rax+rax+00h]
0x18000ef92  lea     rdx, [rsp+0A8h+var_58]; unsigned int *
0x18000ef97  lea     rcx, [r14+48h]; this
0x18000ef9b  call    ?Next@SIMPLE_DICT@@QEAAPEAXAEAI@Z; SIMPLE_DICT::Next(uint &)
0x18000efa0  mov     rdi, rax
0x18000efa3  test    rax, rax
0x18000efa6  jnz     short loc_18000EF5C
0x18000efa8  lea     rcx, aRpcOffendingSt; "RPC: Offending Stack:\n"
0x18000efaf  call    cs:__imp_DbgPrint
0x18000efb6  nop     dword ptr [rax+rax+00h]
0x18000efbb  mov     edx, 4; FramesToCapture
0x18000efc0  lea     ecx, [rdx-2]; FramesToSkip
0x18000efc3  call    ?PrintCurrentStackTrace@@YAXII@Z; PrintCurrentStackTrace(uint,uint)
0x18000efc8  lea     rcx, aRpcToDetermine_0; "RPC: To determine the symbolic stack, d"...
0x18000efcf  call    cs:__imp_DbgPrint
0x18000efd6  nop     dword ptr [rax+rax+00h]
0x18000efdb  jmp     short loc_18000EFE7
0x18000efdd  test    r13b, 2
0x18000efe1  jnz     loc_18000EDD9
0x18000efe7  lea     rcx, [rbx+50h]; struct _RPC_SERVER_INTERFACE *
0x18000efeb  call    ?CheckForRobust@@YAJPEAU_RPC_SERVER_INTERFACE@@@Z; CheckForRobust(_RPC_SERVER_INTERFACE *)
0x18000eff0  test    eax, eax
0x18000eff2  jz      loc_18000EDD9
0x18000eff8  mov     r8d, 70h ; 'p'
0x18000effe  lea     rdx, aPossibleSecuri_5; "Possible security threat: Server regist"...
0x18000f005  lea     rcx, Format; "%s : type (0x%x)"
0x18000f00c  call    cs:__imp_DbgPrint
0x18000f013  nop     dword ptr [rax+rax+00h]
0x18000f018  lea     rcx, aRpcInsecureInt; "RPC: Insecure interface UUID: "
0x18000f01f  call    cs:__imp_DbgPrint
0x18000f026  nop     dword ptr [rax+rax+00h]
0x18000f02b  mov     rcx, rbp; struct _GUID *
0x18000f02e  call    ?DbgPrintUUID@@YAXPEAU_GUID@@@Z; DbgPrintUUID(_GUID *)
0x18000f033  lea     rcx, asc_1800E9378; "\n"
0x18000f03a  call    cs:__imp_DbgPrint
0x18000f041  nop     dword ptr [rax+rax+00h]
0x18000f046  lea     rcx, aRpcOffendingSt; "RPC: Offending Stack:\n"
0x18000f04d  call    cs:__imp_DbgPrint
0x18000f054  nop     dword ptr [rax+rax+00h]
0x18000f059  mov     edx, 4; FramesToCapture
0x18000f05e  lea     ecx, [rdx-2]; FramesToSkip
0x18000f061  call    ?PrintCurrentStackTrace@@YAXII@Z; PrintCurrentStackTrace(uint,uint)
0x18000f066  lea     rcx, aRpcToDetermine_0; "RPC: To determine the symbolic stack, d"...
0x18000f06d  call    cs:__imp_DbgPrint
0x18000f074  nop     dword ptr [rax+rax+00h]
0x18000f079  jmp     loc_18000EDD9
```
