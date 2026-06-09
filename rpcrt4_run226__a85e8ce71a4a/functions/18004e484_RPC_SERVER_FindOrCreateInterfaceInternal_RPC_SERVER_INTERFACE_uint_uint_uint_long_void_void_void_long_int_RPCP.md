# RPC_SERVER::FindOrCreateInterfaceInternal(_RPC_SERVER_INTERFACE *,uint,uint,uint,long (*)(void *,void *),void *,long *,int *,RPCP_INTERFACE_GROUP *)

- ea: `0x18004e484`
- end: `0x18004e803`
- name: `?FindOrCreateInterfaceInternal@RPC_SERVER@@AEAAPEAVRPC_INTERFACE@@PEAU_RPC_SERVER_INTERFACE@@IIIP6AJPEAX1@Z1PEAJPEAHPEAVRPCP_INTERFACE_GROUP@@@Z`
- size: `895`
- prototype: `struct RPC_INTERFACE *__fastcall(RPC_SERVER *__hidden this, struct _RPC_SERVER_INTERFACE *, unsigned int, unsigned int, unsigned int, int (*)(void *, void *), void *, int *, int *, struct RPCP_INTERFACE_GROUP *)`
- caller_count: `2`
- callee_count: `16`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006c894`
- `0x18006dac0`

## callees

- `0x180021e70`
- `0x18004e484`
- `0x18004e80c`
- `0x18004e894`
- `0x18004f480`
- `0x18004f554`
- `0x18004f624`
- `0x180070400`
- `0x180095f98`
- `0x1800a28a8`
- `0x1800a49c0`
- `0x1800aa1d0`
- `0x1800aa250`
- `0x1800b3890`
- `0x1800c99a0`
- `0x1800d2010`

## import_xrefs

- `ntdll!_wcsicmp` at `0x18004e722`
- `ntdll!_wcsicmp` at `0x18004e722`
- `ntdll!DbgPrint` at `0x18004e6e5`
- `ntdll!DbgPrint` at `0x18004e6f2`
- `ntdll!DbgPrint` at `0x18004e707`
- `ntdll!DbgPrint` at `0x18004e73b`
- `ntdll!DbgPrint` at `0x18004e75e`
- `ntdll!DbgPrint` at `0x18004e778`
- `ntdll!DbgPrint` at `0x18004e7af`
- `ntdll!DbgPrint` at `0x18004e7bc`
- `ntdll!DbgPrint` at `0x18004e7d1`
- `ntdll!DbgPrint` at `0x18004e7de`
- `ntdll!DbgPrint` at `0x18004e7f8`
- `ntdll!DbgPrint` at `0x18004e6e5`
- `ntdll!DbgPrint` at `0x18004e6f2`
- `ntdll!DbgPrint` at `0x18004e707`
- `ntdll!DbgPrint` at `0x18004e73b`
- `ntdll!DbgPrint` at `0x18004e75e`
- `ntdll!DbgPrint` at `0x18004e778`
- `ntdll!DbgPrint` at `0x18004e7af`
- `ntdll!DbgPrint` at `0x18004e7bc`
- `ntdll!DbgPrint` at `0x18004e7d1`
- `ntdll!DbgPrint` at `0x18004e7de`
- `ntdll!DbgPrint` at `0x18004e7f8`
- `ntdll!WinSqmIncrementDWORD` at `0x18004e595`
- `ntdll!WinSqmIncrementDWORD` at `0x18004e595`

## string_xrefs

- `0x18004e771`: `RPC: To determine the symbolic stack, do an "ln" on the above addresses in the context of the faulting process.\n\n`
- `0x18004e7f1`: `RPC: To determine the symbolic stack, do an "ln" on the above addresses in the context of the faulting process.\n\n`
- `0x18004e6d7`: `Possible security threat: Server that is remotely accessible is registering an insecure interface`
- `0x18004e7a1`: `Possible security threat: Server registers an interface compiled without /robust option`

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
      WinSqmIncrementDWORD(0, 1201);
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
        v23 = (*(__int64 (__fastcall **)(struct _RPC_SERVER_INTERFACE *, unsigned int *, unsigned int **))qword_1800FA548)(
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
0x18004e484  push    rbx
0x18004e486  push    rbp
0x18004e487  push    rsi
0x18004e488  push    rdi
0x18004e489  push    r12
0x18004e48b  push    r13
0x18004e48d  push    r14
0x18004e48f  push    r15
0x18004e491  sub     rsp, 68h
0x18004e495  mov     esi, r9d
0x18004e498  mov     r13d, r8d
0x18004e49b  mov     r12, rdx
0x18004e49e  mov     r14, rcx
0x18004e4a1  call    ?FindInterface@RPC_SERVER@@QEAAPEAVRPC_INTERFACE@@PEAU_RPC_SERVER_INTERFACE@@@Z; RPC_SERVER::FindInterface(_RPC_SERVER_INTERFACE *)
0x18004e4a6  mov     rdi, [rsp+0A8h+arg_38]
0x18004e4ae  xor     ebp, ebp
0x18004e4b0  mov     rbx, rax
0x18004e4b3  test    rax, rax
0x18004e4b6  jnz     loc_18004E5FD
0x18004e4bc  mov     ecx, 240h; dwBytes
0x18004e4c1  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18004e4c6  test    rax, rax
0x18004e4c9  jz      loc_18004E611
0x18004e4cf  mov     rcx, [rsp+0A8h+arg_48]
0x18004e4d7  mov     r9d, r13d; unsigned int
0x18004e4da  mov     [rsp+0A8h+var_60], rcx; struct RPCP_INTERFACE_GROUP *
0x18004e4df  mov     r8, r14; struct RPC_SERVER *
0x18004e4e2  mov     rcx, [rsp+0A8h+arg_30]
0x18004e4ea  mov     rdx, r12; struct _RPC_SERVER_INTERFACE *
0x18004e4ed  mov     [rsp+0A8h+var_68], rdi; int *
0x18004e4f2  mov     [rsp+0A8h+var_70], rcx; void *
0x18004e4f7  mov     rcx, [rsp+0A8h+arg_28]
0x18004e4ff  mov     [rsp+0A8h+var_78], rcx; int (*)(void *, void *)
0x18004e504  mov     ecx, [rsp+0A8h+arg_20]
0x18004e50b  mov     [rsp+0A8h+var_80], ecx; unsigned int
0x18004e50f  mov     rcx, rax; this
0x18004e512  mov     [rsp+0A8h+var_88], esi; unsigned int
0x18004e516  call    ??0RPC_INTERFACE@@QEAA@PEAU_RPC_SERVER_INTERFACE@@PEAVRPC_SERVER@@IIIP6AJPEAX2@Z2PEAJPEAVRPCP_INTERFACE_GROUP@@@Z; RPC_INTERFACE::RPC_INTERFACE(_RPC_SERVER_INTERFACE *,RPC_SERVER *,uint,uint,uint,long (*)(void *,void *),void *,long *,RPCP_INTERFACE_GROUP *)
0x18004e51b  mov     rbx, rax
0x18004e51e  test    rax, rax
0x18004e521  jz      loc_18004E611
0x18004e527  cmp     [rdi], ebp
0x18004e529  jnz     loc_18004E5F1
0x18004e52f  lea     rcx, [r14+120h]; this
0x18004e536  mov     rdx, rax; void *
0x18004e539  call    ?Insert@SIMPLE_DICT@@QEAAIPEAX@Z; SIMPLE_DICT::Insert(void *)
0x18004e53e  cmp     eax, 0FFFFFFFFh
0x18004e541  jz      loc_18004E609
0x18004e547  mov     rax, gs:60h
0x18004e550  lea     esi, [rbp+1]
0x18004e553  mov     rcx, [rax+20h]
0x18004e557  cmp     [rcx+8], ebp
0x18004e55a  jl      loc_18004E619
0x18004e560  call    ?LoadFirewallExtensionIfNecessary@@YAJXZ; LoadFirewallExtensionIfNecessary(void)
0x18004e565  mov     [rdi], eax
0x18004e567  cmp     eax, 0Eh
0x18004e56a  jz      short loc_18004E5E6
0x18004e56c  test    eax, eax
0x18004e56e  jz      short loc_18004E5BB
0x18004e570  mov     eax, ebp
0x18004e572  mov     r15, [rsp+0A8h+arg_40]
0x18004e57a  mov     rcx, r12; struct _RPC_SERVER_INTERFACE *
0x18004e57d  mov     [r15], eax
0x18004e580  mov     [rdi], ebp
0x18004e582  call    ?CheckForRobust@@YAJPEAU_RPC_SERVER_INTERFACE@@@Z; CheckForRobust(_RPC_SERVER_INTERFACE *)
0x18004e587  test    eax, eax
0x18004e589  jz      short loc_18004E59B
0x18004e58b  mov     r8d, esi
0x18004e58e  mov     edx, 4B1h
0x18004e593  xor     ecx, ecx
0x18004e595  call    cs:__imp_WinSqmIncrementDWORD
0x18004e59b  cmp     cs:?gfRPCVerifierEnabled@@3HA, ebp; int gfRPCVerifierEnabled
0x18004e5a1  jnz     loc_18004E675
0x18004e5a7  mov     rax, rbx
0x18004e5aa  add     rsp, 68h
0x18004e5ae  pop     r15
0x18004e5b0  pop     r14
0x18004e5b2  pop     r13
0x18004e5b4  pop     r12
0x18004e5b6  pop     rdi
0x18004e5b7  pop     rsi
0x18004e5b8  pop     rbp
0x18004e5b9  pop     rbx
0x18004e5ba  retn
0x18004e5bb  mov     rax, cs:qword_1800FA548
0x18004e5c2  lea     r8, [rsp+0A8h+var_50]
0x18004e5c7  mov     [rsp+0A8h+var_58], ebp
0x18004e5cb  lea     rdx, [rsp+0A8h+var_58]
0x18004e5d0  mov     [rsp+0A8h+var_50], rbp
0x18004e5d5  mov     rcx, r12
0x18004e5d8  mov     rax, [rax]
0x18004e5db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5e0  mov     [rdi], eax
0x18004e5e2  test    eax, eax
0x18004e5e4  jz      short loc_18004E628
0x18004e5e6  mov     rdx, rbx; struct RPC_INTERFACE *
0x18004e5e9  mov     rcx, r14; this
0x18004e5ec  call    ?RemoveInterface@RPC_SERVER@@QEAAHPEAVRPC_INTERFACE@@@Z; RPC_SERVER::RemoveInterface(RPC_INTERFACE *)
0x18004e5f1  mov     rcx, rbx; this
0x18004e5f4  call    ??_GRPC_INTERFACE@@QEAAPEAXI@Z; RPC_INTERFACE::`scalar deleting destructor'(uint)
0x18004e5f9  xor     eax, eax
0x18004e5fb  jmp     short loc_18004E5AA
0x18004e5fd  mov     esi, 1
0x18004e602  mov     eax, esi
0x18004e604  jmp     loc_18004E572
0x18004e609  mov     rcx, rbx; this
0x18004e60c  call    ??_GRPC_INTERFACE@@QEAAPEAXI@Z; RPC_INTERFACE::`scalar deleting destructor'(uint)
0x18004e611  mov     dword ptr [rdi], 0Eh
0x18004e617  jmp     short loc_18004E5F9
0x18004e619  mov     cs:?gFwExtensionState@@3W4FwExtensionState@@A, 2; FwExtensionState gFwExtensionState
0x18004e623  jmp     loc_18004E570
0x18004e628  cmp     [rsp+0A8h+var_58], ebp
0x18004e62c  jz      short loc_18004E637
0x18004e62e  mov     eax, [rbx+38h]
0x18004e631  or      eax, 4
0x18004e634  mov     [rbx+38h], eax
0x18004e637  mov     rdx, [rsp+0A8h+var_50]
0x18004e63c  test    rdx, rdx
0x18004e63f  jz      loc_18004E570
0x18004e645  cmp     [rdx], ebp
0x18004e647  jbe     loc_18004E570
0x18004e64d  mov     eax, ebp
0x18004e64f  lea     rcx, [rax+rax*2]
0x18004e653  lea     rdx, [rdx+rcx*8]
0x18004e657  mov     rcx, rbx; this
0x18004e65a  add     rdx, 8; struct _FwEp *
0x18004e65e  call    ?EpAdd@RPC_INTERFACE@@QEAAXPEAU_FwEp@@@Z; RPC_INTERFACE::EpAdd(_FwEp *)
0x18004e663  mov     rdx, [rsp+0A8h+var_50]
0x18004e668  add     ebp, esi
0x18004e66a  cmp     ebp, [rdx]
0x18004e66c  jb      short loc_18004E64D
0x18004e66e  xor     ebp, ebp
0x18004e670  jmp     loc_18004E570
0x18004e675  mov     rax, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x18004e67c  cmp     [rax+84h], ebp
0x18004e682  jnz     loc_18004E5A7
0x18004e688  cmp     [r15], ebp
0x18004e68b  jnz     loc_18004E5A7
0x18004e691  mov     rcx, rbx; this
0x18004e694  lea     rbp, [rbx+54h]
0x18004e698  call    ?IsSecure@RPC_INTERFACE@@QEAAHXZ; RPC_INTERFACE::IsSecure(void)
0x18004e69d  test    eax, eax
0x18004e69f  jnz     loc_18004E780
0x18004e6a5  test    r13b, 2
0x18004e6a9  jnz     loc_18004E5A7
0x18004e6af  mov     edx, esi; unsigned int
0x18004e6b1  mov     rcx, rbp; struct _GUID *
0x18004e6b4  call    ?IsInterfaceExempt@@YAHPEAU_GUID@@K@Z; IsInterfaceExempt(_GUID *,ulong)
0x18004e6b9  test    eax, eax
0x18004e6bb  jnz     loc_18004E78A
0x18004e6c1  cmp     cs:?gfRemoteProtseqRegistered@@3HA, eax; int gfRemoteProtseqRegistered
0x18004e6c7  mov     cs:?gfUnsecureInterfaceRegistered@@3HA, esi; int gfUnsecureInterfaceRegistered
0x18004e6cd  jz      loc_18004E78A
0x18004e6d3  lea     r8d, [rax+10h]
0x18004e6d7  lea     rdx, aPossibleSecuri_3; "Possible security threat: Server that i"...
0x18004e6de  lea     rcx, aSType0xX; "%s : type (0x%x)"
0x18004e6e5  call    cs:__imp_DbgPrint
0x18004e6eb  lea     rcx, aRpcInsecureInt; "RPC: Insecure interface UUID: "
0x18004e6f2  call    cs:__imp_DbgPrint
0x18004e6f8  mov     rcx, rbp; struct _GUID *
0x18004e6fb  call    ?DbgPrintUUID@@YAXPEAU_GUID@@@Z; DbgPrintUUID(_GUID *)
0x18004e700  lea     rcx, asc_1800E4358; "\n"
0x18004e707  call    cs:__imp_DbgPrint
0x18004e70d  mov     [rsp+0A8h+var_58], 0
0x18004e715  jmp     short loc_18004E741
0x18004e717  mov     rcx, [rdi+28h]; String1
0x18004e71b  lea     rdx, aNcalrpc; "ncalrpc"
0x18004e722  call    cs:__imp__wcsicmp
0x18004e728  test    eax, eax
0x18004e72a  jz      short loc_18004E741
0x18004e72c  mov     r8, [rdi+20h]
0x18004e730  lea     rcx, aRpcListeningOn; "RPC: Listening on protseq: %S endpoint:"...
0x18004e737  mov     rdx, [rdi+28h]
0x18004e73b  call    cs:__imp_DbgPrint
0x18004e741  lea     rdx, [rsp+0A8h+var_58]; unsigned int *
0x18004e746  lea     rcx, [r14+48h]; this
0x18004e74a  call    ?Next@SIMPLE_DICT@@QEAAPEAXAEAI@Z; SIMPLE_DICT::Next(uint &)
0x18004e74f  mov     rdi, rax
0x18004e752  test    rax, rax
0x18004e755  jnz     short loc_18004E717
0x18004e757  lea     rcx, aRpcOffendingSt; "RPC: Offending Stack:\n"
0x18004e75e  call    cs:__imp_DbgPrint
0x18004e764  mov     edx, 4; FramesToCapture
0x18004e769  lea     ecx, [rdx-2]; FramesToSkip
0x18004e76c  call    ?PrintCurrentStackTrace@@YAXII@Z; PrintCurrentStackTrace(uint,uint)
0x18004e771  lea     rcx, aRpcToDetermine_0; "RPC: To determine the symbolic stack, d"...
0x18004e778  call    cs:__imp_DbgPrint
0x18004e77e  jmp     short loc_18004E78A
0x18004e780  test    r13b, 2
0x18004e784  jnz     loc_18004E5A7
0x18004e78a  lea     rcx, [rbx+50h]; struct _RPC_SERVER_INTERFACE *
0x18004e78e  call    ?CheckForRobust@@YAJPEAU_RPC_SERVER_INTERFACE@@@Z; CheckForRobust(_RPC_SERVER_INTERFACE *)
0x18004e793  test    eax, eax
0x18004e795  jz      loc_18004E5A7
0x18004e79b  mov     r8d, 70h ; 'p'
0x18004e7a1  lea     rdx, aPossibleSecuri_5; "Possible security threat: Server regist"...
0x18004e7a8  lea     rcx, aSType0xX; "%s : type (0x%x)"
0x18004e7af  call    cs:__imp_DbgPrint
0x18004e7b5  lea     rcx, aRpcInsecureInt; "RPC: Insecure interface UUID: "
0x18004e7bc  call    cs:__imp_DbgPrint
0x18004e7c2  mov     rcx, rbp; struct _GUID *
0x18004e7c5  call    ?DbgPrintUUID@@YAXPEAU_GUID@@@Z; DbgPrintUUID(_GUID *)
0x18004e7ca  lea     rcx, asc_1800E4358; "\n"
0x18004e7d1  call    cs:__imp_DbgPrint
0x18004e7d7  lea     rcx, aRpcOffendingSt; "RPC: Offending Stack:\n"
0x18004e7de  call    cs:__imp_DbgPrint
0x18004e7e4  mov     edx, 4; FramesToCapture
0x18004e7e9  lea     ecx, [rdx-2]; FramesToSkip
0x18004e7ec  call    ?PrintCurrentStackTrace@@YAXII@Z; PrintCurrentStackTrace(uint,uint)
0x18004e7f1  lea     rcx, aRpcToDetermine_0; "RPC: To determine the symbolic stack, d"...
0x18004e7f8  call    cs:__imp_DbgPrint
0x18004e7fe  jmp     loc_18004E5A7
```
