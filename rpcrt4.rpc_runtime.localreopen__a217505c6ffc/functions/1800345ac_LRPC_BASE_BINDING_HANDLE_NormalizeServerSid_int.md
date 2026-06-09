# LRPC_BASE_BINDING_HANDLE::NormalizeServerSid(int)

- ea: `0x1800345ac`
- end: `0x180034838`
- name: `?NormalizeServerSid@LRPC_BASE_BINDING_HANDLE@@IEAAJH@Z`
- size: `652`
- prototype: `__int64 __fastcall(LRPC_BASE_BINDING_HANDLE *__hidden this, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800334e4`
- `0x180034840`

## callees

- `0x180023020`
- `0x1800295d8`
- `0x1800345ac`
- `0x180034c58`
- `0x180036048`
- `0x1800361a0`
- `0x1800a5ef4`
- `0x1800a8378`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180034684`
- `ntdll!RtlLeaveCriticalSection` at `0x1800346f8`
- `ntdll!RtlLeaveCriticalSection` at `0x180034684`
- `ntdll!RtlLeaveCriticalSection` at `0x1800346f8`
- `ntdll!RtlEnterCriticalSection` at `0x1800345ca`
- `ntdll!RtlEnterCriticalSection` at `0x180034800`
- `ntdll!RtlEnterCriticalSection` at `0x1800345ca`
- `ntdll!RtlEnterCriticalSection` at `0x180034800`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003471c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003471c`

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
0x1800345ac  push    rbp
0x1800345ae  push    rsi
0x1800345af  push    rdi
0x1800345b0  push    r12
0x1800345b2  push    r14
0x1800345b4  push    r15
0x1800345b6  sub     rsp, 38h
0x1800345ba  lea     r15, [rcx+130h]
0x1800345c1  mov     rsi, rcx
0x1800345c4  mov     rcx, r15; CriticalSection
0x1800345c7  mov     r12d, edx
0x1800345ca  call    cs:__imp_RtlEnterCriticalSection
0x1800345d1  nop     dword ptr [rax+rax+00h]
0x1800345d6  mov     eax, [rsi+1F0h]
0x1800345dc  test    al, 4
0x1800345de  jnz     loc_180034741
0x1800345e4  mov     rcx, [rsi+190h]; pSid1
0x1800345eb  call    ?RpcpIsWellKnownSid@@YAHPEAX@Z; RpcpIsWellKnownSid(void *)
0x1800345f0  test    eax, eax
0x1800345f2  jnz     loc_18003474E
0x1800345f8  xor     edi, edi
0x1800345fa  mov     ecx, 0D8h; dwBytes
0x1800345ff  mov     [rsp+68h+arg_0], edi
0x180034603  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180034608  mov     rbp, rax
0x18003460b  test    rax, rax
0x18003460e  jz      loc_180034730
0x180034614  mov     rax, [rsi]
0x180034617  mov     rcx, rsi
0x18003461a  mov     rax, [rax+0D0h]
0x180034621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034626  lea     r8, [rsp+68h+arg_0]; int *
0x18003462b  mov     rdx, rax; struct CLIENT_AUTH_INFO *
0x18003462e  mov     rcx, rbp; this
0x180034631  call    ??0NORMALIZATION_SID_IO@@QEAA@PEAUCLIENT_AUTH_INFO@@PEAJ@Z; NORMALIZATION_SID_IO::NORMALIZATION_SID_IO(CLIENT_AUTH_INFO *,long *)
0x180034636  mov     edi, [rsp+68h+arg_0]
0x18003463a  mov     rcx, rax
0x18003463d  mov     [rsi+208h], rcx
0x180034644  test    rcx, rcx
0x180034647  jz      loc_180034772
0x18003464d  test    edi, edi
0x18003464f  jnz     loc_18003477C
0x180034655  add     rcx, 18h; this
0x180034659  test    r12d, r12d
0x18003465c  jz      loc_180034737
0x180034662  mov     r8, rsi; void *
0x180034665  lea     rdx, ?LrpcRetryEpResolve@@YAXPEAX@Z; void (*)(void *)
0x18003466c  call    ?FullReinitAsync@LRPC_CLIENT_IO@@QEAAXP6AXPEAX@Z0@Z; LRPC_CLIENT_IO::FullReinitAsync(void (*)(void *),void *)
0x180034671  mov     rax, [rsi+208h]
0x180034678  mov     ebp, 2
0x18003467d  lock or [rax+30h], ebp
0x180034681  mov     rcx, r15; CriticalSection
0x180034684  call    cs:__imp_RtlLeaveCriticalSection
0x18003468b  nop     dword ptr [rax+rax+00h]
0x180034690  mov     rax, [rsi+208h]
0x180034697  xor     r14d, r14d
0x18003469a  mov     [rax+0D0h], r14d
0x1800346a1  cmp     cs:?g_pMachineAccountSid@@3PEAXEA, r14; void * g_pMachineAccountSid
0x1800346a8  jz      loc_18003479E
0x1800346ae  mov     eax, [rsi+1F0h]
0x1800346b4  test    al, 4
0x1800346b6  jnz     loc_1800347D6
0x1800346bc  mov     rcx, cs:?g_pMachineAccountSid@@3PEAXEA; pSid1
0x1800346c3  test    rcx, rcx
0x1800346c6  jnz     short loc_180034715
0x1800346c8  mov     edx, 0C0021017h; int
0x1800346cd  mov     r8d, 390h; unsigned __int16
0x1800346d3  mov     edi, edx
0x1800346d5  xor     r9d, r9d; int
0x1800346d8  mov     [rsp+68h+var_48], r14; struct tagParam *
0x1800346dd  mov     ecx, ebp; unsigned int
0x1800346df  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x1800346e4  cmp     edi, 0C0021018h
0x1800346ea  jnz     loc_1800347F4
0x1800346f0  test    r14d, r14d
0x1800346f3  jz      short loc_180034704
0x1800346f5  mov     rcx, r15; CriticalSection
0x1800346f8  call    cs:__imp_RtlLeaveCriticalSection
0x1800346ff  nop     dword ptr [rax+rax+00h]
0x180034704  mov     eax, edi
0x180034706  add     rsp, 38h
0x18003470a  pop     r15
0x18003470c  pop     r14
0x18003470e  pop     r12
0x180034710  pop     rdi
0x180034711  pop     rsi
0x180034712  pop     rbp
0x180034713  retn
0x180034715  mov     rdx, [rsi+190h]; pSid2
0x18003471c  call    cs:__imp_EqualSid
0x180034723  nop     dword ptr [rax+rax+00h]
0x180034728  test    eax, eax
0x18003472a  jz      short loc_1800346C8
0x18003472c  xor     eax, eax
0x18003472e  jmp     short loc_180034706
0x180034730  xor     ecx, ecx
0x180034732  jmp     loc_18003463D
0x180034737  call    ?FullReinitSync@LRPC_CLIENT_IO@@QEAAXXZ; LRPC_CLIENT_IO::FullReinitSync(void)
0x18003473c  jmp     loc_180034671
0x180034741  mov     edx, 71Ah
0x180034746  mov     r8d, 38Eh
0x18003474c  jmp     short loc_180034759
0x18003474e  mov     edx, 0C0021017h; int
0x180034753  mov     r8d, 391h; unsigned __int16
0x180034759  xor     r9d, r9d; int
0x18003475c  mov     [rsp+68h+var_48], 0; struct tagParam *
0x180034765  mov     edi, edx
0x180034767  lea     ecx, [r9+2]; unsigned int
0x18003476b  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180034770  jmp     short loc_1800346F5
0x180034772  mov     edi, 0Eh
0x180034777  jmp     loc_1800346F5
0x18003477c  mov     rax, [rcx]
0x18003477f  mov     r14d, 1
0x180034785  mov     rax, [rax+20h]
0x180034789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003478e  mov     qword ptr [rsi+208h], 0
0x180034799  jmp     loc_1800346E4
0x18003479e  mov     rdx, [rsi+208h]
0x1800347a5  xor     r8d, r8d; unsigned int
0x1800347a8  add     rdx, 18h; struct LRPC_CLIENT_IO *
0x1800347ac  mov     ecx, r12d; int
0x1800347af  call    ?LrpcPrepareMachineAccountSid@@YAJHPEAVLRPC_CLIENT_IO@@K@Z; LrpcPrepareMachineAccountSid(int,LRPC_CLIENT_IO *,ulong)
0x1800347b4  mov     edi, eax
0x1800347b6  cmp     eax, 0C0021018h
0x1800347bb  jz      loc_180034704
0x1800347c1  test    eax, eax
0x1800347c3  jz      loc_1800346AE
0x1800347c9  mov     r8d, 38Fh
0x1800347cf  mov     edx, eax
0x1800347d1  jmp     loc_1800346D5
0x1800347d6  mov     edx, 71Ah; int
0x1800347db  mov     [rsp+68h+var_48], r14; struct tagParam *
0x1800347e0  mov     r8d, 38Eh; unsigned __int16
0x1800347e6  xor     r9d, r9d; int
0x1800347e9  mov     ecx, ebp; unsigned int
0x1800347eb  mov     edi, edx
0x1800347ed  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x1800347f2  jmp     short loc_1800347FD
0x1800347f4  test    r14d, r14d
0x1800347f7  jnz     loc_1800346F5
0x1800347fd  mov     rcx, r15; CriticalSection
0x180034800  call    cs:__imp_RtlEnterCriticalSection
0x180034807  nop     dword ptr [rax+rax+00h]
0x18003480c  mov     rcx, [rsi+208h]
0x180034813  test    rcx, rcx
0x180034816  jz      loc_1800346F5
0x18003481c  mov     rax, [rcx]
0x18003481f  mov     rax, [rax+20h]
0x180034823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034828  mov     qword ptr [rsi+208h], 0
0x180034833  jmp     loc_1800346F5
```
