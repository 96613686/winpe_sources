# LRPC_BASE_BINDING_HANDLE::NormalizeServerSid(int)

- ea: `0x180033100`
- end: `0x18003336a`
- name: `?NormalizeServerSid@LRPC_BASE_BINDING_HANDLE@@IEAAJH@Z`
- size: `618`
- prototype: `__int64 __fastcall(LRPC_BASE_BINDING_HANDLE *__hidden this, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180032074`
- `0x180068534`

## callees

- `0x180021e70`
- `0x1800283bc`
- `0x180033100`
- `0x18003408c`
- `0x1800637f0`
- `0x18009ee0c`
- `0x1800a291c`
- `0x1800a4c50`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800331d2`
- `ntdll!RtlLeaveCriticalSection` at `0x180033240`
- `ntdll!RtlLeaveCriticalSection` at `0x1800331d2`
- `ntdll!RtlLeaveCriticalSection` at `0x180033240`
- `ntdll!RtlEnterCriticalSection` at `0x18003311e`
- `ntdll!RtlEnterCriticalSection` at `0x180033338`
- `ntdll!RtlEnterCriticalSection` at `0x18003311e`
- `ntdll!RtlEnterCriticalSection` at `0x180033338`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003325d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003325d`

## pseudocode

```c
__int64 __fastcall LRPC_BASE_BINDING_HANDLE::NormalizeServerSid(LRPC_BASE_BINDING_HANDLE *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r15
  unsigned int v5; // edi
  NORMALIZATION_SID_IO *v6; // rbp
  struct CLIENT_AUTH_INFO *v7; // rax
  NORMALIZATION_SID_IO *v8; // rax
  NORMALIZATION_SID_IO *v9; // rcx
  LRPC_CLIENT_IO *v10; // rcx
  int v11; // r14d
  int v12; // edx
  unsigned __int16 v13; // r8
  int v15; // edx
  unsigned __int16 v16; // r8
  unsigned int v17; // eax
  __int64 v18; // rcx
  int v19; // [rsp+70h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 304);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 304));
  if ( (*((_DWORD *)this + 124) & 4) != 0 )
  {
    v15 = 1818;
    v16 = 910;
LABEL_24:
    v5 = v15;
    RpcpErrorAddRecord(2u, v15, v16, 0, 0);
    goto LABEL_16;
  }
  if ( RpcpIsWellKnownSid(*((PSID *)this + 50)) )
  {
    v15 = -1073606633;
    v16 = 913;
    goto LABEL_24;
  }
  v5 = 0;
  v19 = 0;
  v6 = (NORMALIZATION_SID_IO *)AllocWrapper(0xD8u);
  if ( v6 )
  {
    v7 = (struct CLIENT_AUTH_INFO *)(*(__int64 (__fastcall **)(LRPC_BASE_BINDING_HANDLE *))(*(_QWORD *)this + 208LL))(this);
    v8 = NORMALIZATION_SID_IO::NORMALIZATION_SID_IO(v6, v7, &v19);
    v5 = v19;
    v9 = v8;
  }
  else
  {
    v9 = 0;
  }
  *((_QWORD *)this + 65) = v9;
  if ( !v9 )
  {
    v5 = 14;
    goto LABEL_16;
  }
  if ( v5 )
  {
    v11 = 1;
    (*(void (__fastcall **)(NORMALIZATION_SID_IO *))(*(_QWORD *)v9 + 32LL))(v9);
    *((_QWORD *)this + 65) = 0;
    goto LABEL_14;
  }
  v10 = (NORMALIZATION_SID_IO *)((char *)v9 + 24);
  if ( a2 )
    LRPC_CLIENT_IO::FullReinitAsync(v10, (void (*)(void *))LrpcRetryEpResolve, this);
  else
    LRPC_CLIENT_IO::FullReinitSync(v10);
  _InterlockedOr((volatile signed __int32 *)(*((_QWORD *)this + 65) + 48LL), 2u);
  RtlLeaveCriticalSection(v2);
  v11 = 0;
  *(_DWORD *)(*((_QWORD *)this + 65) + 208LL) = 0;
  if ( !g_pMachineAccountSid )
  {
    v17 = LrpcPrepareMachineAccountSid(a2, (struct LRPC_CLIENT_IO *)(*((_QWORD *)this + 65) + 24LL), 0);
    v5 = v17;
    if ( v17 == -1073606632 )
      return v5;
    if ( v17 )
    {
      v13 = 911;
      v12 = v17;
      goto LABEL_13;
    }
  }
  if ( (*((_DWORD *)this + 124) & 4) != 0 )
  {
    v5 = 1818;
    RpcpErrorAddRecord(2u, 1818, 0x38Eu, 0, 0);
    goto LABEL_32;
  }
  if ( !g_pMachineAccountSid || !EqualSid(g_pMachineAccountSid, *((PSID *)this + 50)) )
  {
    v12 = -1073606633;
    v13 = 912;
    v5 = -1073606633;
LABEL_13:
    RpcpErrorAddRecord(2u, v12, v13, 0, 0);
LABEL_14:
    if ( v5 == -1073606632 )
    {
      if ( !v11 )
        return v5;
LABEL_16:
      RtlLeaveCriticalSection(v2);
      return v5;
    }
    if ( v11 )
      goto LABEL_16;
LABEL_32:
    RtlEnterCriticalSection(v2);
    v18 = *((_QWORD *)this + 65);
    if ( v18 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 32LL))(v18);
      *((_QWORD *)this + 65) = 0;
    }
    goto LABEL_16;
  }
  return 0;
}

```

## disassembly

```asm
0x180033100  push    rbp
0x180033102  push    rsi
0x180033103  push    rdi
0x180033104  push    r12
0x180033106  push    r14
0x180033108  push    r15
0x18003310a  sub     rsp, 38h
0x18003310e  lea     r15, [rcx+130h]
0x180033115  mov     rsi, rcx
0x180033118  mov     rcx, r15; CriticalSection
0x18003311b  mov     r12d, edx
0x18003311e  call    cs:__imp_RtlEnterCriticalSection
0x180033124  mov     eax, [rsi+1F0h]
0x18003312a  test    al, 4
0x18003312c  jnz     loc_18003327C
0x180033132  mov     rcx, [rsi+190h]; pSid1
0x180033139  call    ?RpcpIsWellKnownSid@@YAHPEAX@Z; RpcpIsWellKnownSid(void *)
0x18003313e  test    eax, eax
0x180033140  jnz     loc_180033289
0x180033146  xor     edi, edi
0x180033148  mov     ecx, 0D8h; dwBytes
0x18003314d  mov     [rsp+68h+arg_0], edi
0x180033151  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180033156  mov     rbp, rax
0x180033159  test    rax, rax
0x18003315c  jz      loc_18003326B
0x180033162  mov     rax, [rsi]
0x180033165  mov     rcx, rsi
0x180033168  mov     rax, [rax+0D0h]
0x18003316f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033174  lea     r8, [rsp+68h+arg_0]; int *
0x180033179  mov     rdx, rax; struct CLIENT_AUTH_INFO *
0x18003317c  mov     rcx, rbp; this
0x18003317f  call    ??0NORMALIZATION_SID_IO@@QEAA@PEAUCLIENT_AUTH_INFO@@PEAJ@Z; NORMALIZATION_SID_IO::NORMALIZATION_SID_IO(CLIENT_AUTH_INFO *,long *)
0x180033184  mov     edi, [rsp+68h+arg_0]
0x180033188  mov     rcx, rax
0x18003318b  mov     [rsi+208h], rcx
0x180033192  test    rcx, rcx
0x180033195  jz      loc_1800332AD
0x18003319b  test    edi, edi
0x18003319d  jnz     loc_1800332B4
0x1800331a3  add     rcx, 18h; this
0x1800331a7  test    r12d, r12d
0x1800331aa  jz      loc_180033272
0x1800331b0  mov     r8, rsi; void *
0x1800331b3  lea     rdx, ?LrpcRetryEpResolve@@YAXPEAX@Z; void (*)(void *)
0x1800331ba  call    ?FullReinitAsync@LRPC_CLIENT_IO@@QEAAXP6AXPEAX@Z0@Z; LRPC_CLIENT_IO::FullReinitAsync(void (*)(void *),void *)
0x1800331bf  mov     rax, [rsi+208h]
0x1800331c6  mov     ebp, 2
0x1800331cb  lock or [rax+30h], ebp
0x1800331cf  mov     rcx, r15; CriticalSection
0x1800331d2  call    cs:__imp_RtlLeaveCriticalSection
0x1800331d8  mov     rax, [rsi+208h]
0x1800331df  xor     r14d, r14d
0x1800331e2  mov     [rax+0D0h], r14d
0x1800331e9  cmp     cs:?g_pMachineAccountSid@@3PEAXEA, r14; void * g_pMachineAccountSid
0x1800331f0  jz      loc_1800332D6
0x1800331f6  mov     eax, [rsi+1F0h]
0x1800331fc  test    al, 4
0x1800331fe  jnz     loc_18003330E
0x180033204  mov     rcx, cs:?g_pMachineAccountSid@@3PEAXEA; pSid1
0x18003320b  test    rcx, rcx
0x18003320e  jnz     short loc_180033256
0x180033210  mov     edx, 0C0021017h; int
0x180033215  mov     r8d, 390h; unsigned __int16
0x18003321b  mov     edi, edx
0x18003321d  xor     r9d, r9d; int
0x180033220  mov     [rsp+68h+var_48], r14; struct tagParam *
0x180033225  mov     ecx, ebp; unsigned int
0x180033227  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18003322c  cmp     edi, 0C0021018h
0x180033232  jnz     loc_18003332C
0x180033238  test    r14d, r14d
0x18003323b  jz      short loc_180033246
0x18003323d  mov     rcx, r15; CriticalSection
0x180033240  call    cs:__imp_RtlLeaveCriticalSection
0x180033246  mov     eax, edi
0x180033248  add     rsp, 38h
0x18003324c  pop     r15
0x18003324e  pop     r14
0x180033250  pop     r12
0x180033252  pop     rdi
0x180033253  pop     rsi
0x180033254  pop     rbp
0x180033255  retn
0x180033256  mov     rdx, [rsi+190h]; pSid2
0x18003325d  call    cs:__imp_EqualSid
0x180033263  test    eax, eax
0x180033265  jz      short loc_180033210
0x180033267  xor     eax, eax
0x180033269  jmp     short loc_180033248
0x18003326b  xor     ecx, ecx
0x18003326d  jmp     loc_18003318B
0x180033272  call    ?FullReinitSync@LRPC_CLIENT_IO@@QEAAXXZ; LRPC_CLIENT_IO::FullReinitSync(void)
0x180033277  jmp     loc_1800331BF
0x18003327c  mov     edx, 71Ah
0x180033281  mov     r8d, 38Eh
0x180033287  jmp     short loc_180033294
0x180033289  mov     edx, 0C0021017h; int
0x18003328e  mov     r8d, 391h; unsigned __int16
0x180033294  xor     r9d, r9d; int
0x180033297  mov     [rsp+68h+var_48], 0; struct tagParam *
0x1800332a0  mov     edi, edx
0x1800332a2  lea     ecx, [r9+2]; unsigned int
0x1800332a6  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x1800332ab  jmp     short loc_18003323D
0x1800332ad  mov     edi, 0Eh
0x1800332b2  jmp     short loc_18003323D
0x1800332b4  mov     rax, [rcx]
0x1800332b7  mov     r14d, 1
0x1800332bd  mov     rax, [rax+20h]
0x1800332c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332c6  mov     qword ptr [rsi+208h], 0
0x1800332d1  jmp     loc_18003322C
0x1800332d6  mov     rdx, [rsi+208h]
0x1800332dd  xor     r8d, r8d; unsigned int
0x1800332e0  add     rdx, 18h; struct LRPC_CLIENT_IO *
0x1800332e4  mov     ecx, r12d; int
0x1800332e7  call    ?LrpcPrepareMachineAccountSid@@YAJHPEAVLRPC_CLIENT_IO@@K@Z; LrpcPrepareMachineAccountSid(int,LRPC_CLIENT_IO *,ulong)
0x1800332ec  mov     edi, eax
0x1800332ee  cmp     eax, 0C0021018h
0x1800332f3  jz      loc_180033246
0x1800332f9  test    eax, eax
0x1800332fb  jz      loc_1800331F6
0x180033301  mov     r8d, 38Fh
0x180033307  mov     edx, eax
0x180033309  jmp     loc_18003321D
0x18003330e  mov     edx, 71Ah; int
0x180033313  mov     [rsp+68h+var_48], r14; struct tagParam *
0x180033318  mov     r8d, 38Eh; unsigned __int16
0x18003331e  xor     r9d, r9d; int
0x180033321  mov     ecx, ebp; unsigned int
0x180033323  mov     edi, edx
0x180033325  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18003332a  jmp     short loc_180033335
0x18003332c  test    r14d, r14d
0x18003332f  jnz     loc_18003323D
0x180033335  mov     rcx, r15; CriticalSection
0x180033338  call    cs:__imp_RtlEnterCriticalSection
0x18003333e  mov     rcx, [rsi+208h]
0x180033345  test    rcx, rcx
0x180033348  jz      loc_18003323D
0x18003334e  mov     rax, [rcx]
0x180033351  mov     rax, [rax+20h]
0x180033355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003335a  mov     qword ptr [rsi+208h], 0
0x180033365  jmp     loc_18003323D
```
