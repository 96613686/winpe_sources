# LB_RESOURCE_ID_CONFIG_ENTRY::WaitAndComplete(ulong,int)

- ea: `0x1800237c8`
- end: `0x180023a65`
- name: `?WaitAndComplete@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAJKH@Z`
- size: `669`
- prototype: `__int64 __fastcall(LB_RESOURCE_ID_CONFIG_ENTRY *__hidden this, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180023688`

## callees

- `0x18001f984`
- `0x18001f9c0`
- `0x180021238`
- `0x180021ed8`
- `0x1800237c8`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002385b`
- `ntdll!RtlLeaveCriticalSection` at `0x18002388a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800238fd`
- `ntdll!RtlLeaveCriticalSection` at `0x180023a27`
- `ntdll!RtlLeaveCriticalSection` at `0x180023a49`
- `ntdll!RtlLeaveCriticalSection` at `0x18002385b`
- `ntdll!RtlLeaveCriticalSection` at `0x18002388a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800238fd`
- `ntdll!RtlLeaveCriticalSection` at `0x180023a27`
- `ntdll!RtlLeaveCriticalSection` at `0x180023a49`
- `ntdll!RtlEnterCriticalSection` at `0x1800237fa`
- `ntdll!RtlEnterCriticalSection` at `0x1800237fa`
- `KERNEL32!WaitForMultipleObjects` at `0x18002393d`
- `KERNEL32!WaitForMultipleObjects` at `0x18002393d`
- `KERNEL32!WaitForSingleObject` at `0x1800239c0`
- `KERNEL32!WaitForSingleObject` at `0x1800239c0`
- `RPCRT4!I_RpcFree` at `0x180023893`
- `RPCRT4!I_RpcFree` at `0x180023a30`
- `RPCRT4!I_RpcFree` at `0x180023a3b`
- `RPCRT4!I_RpcFree` at `0x180023893`
- `RPCRT4!I_RpcFree` at `0x180023a30`
- `RPCRT4!I_RpcFree` at `0x180023a3b`
- `RPCRT4!I_RpcAllocate` at `0x18002384a`
- `RPCRT4!I_RpcAllocate` at `0x180023877`
- `RPCRT4!I_RpcAllocate` at `0x18002384a`
- `RPCRT4!I_RpcAllocate` at `0x180023877`
- `RPCRT4!RpcBindingFree` at `0x1800239f2`
- `RPCRT4!RpcBindingFree` at `0x1800239f2`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800239b0`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800239b0`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800239cc`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800239cc`

## pseudocode

```c
__int64 __fastcall LB_RESOURCE_ID_CONFIG_ENTRY::WaitAndComplete(LB_RESOURCE_ID_CONFIG_ENTRY *this, int a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  DWORD v5; // esi
  LB_RPCHTTP_SERVER *v6; // rbx
  LB_RPCHTTP_SERVER *v7; // r9
  LB_RPCHTTP_SERVER *v8; // rax
  DWORD v9; // ecx
  unsigned int v10; // eax
  void *v11; // r12
  unsigned int v13; // eax
  HANDLE *v14; // rax
  LB_RPCHTTP_SERVER *v15; // rdi
  __int64 v16; // r15
  int v17; // r13d
  HANDLE *v18; // rbp
  LB_RPCHTTP_SERVER *v19; // r13
  DWORD v20; // ebp
  int v21; // r14d
  DWORD v22; // ebx
  unsigned int v23; // edi
  DWORD v24; // eax
  DWORD v25; // eax
  DWORD v26; // r15d
  unsigned int v27; // r14d
  __int64 i; // r15
  __int64 v29; // rdi
  HANDLE *lpHandles; // [rsp+20h] [rbp-58h]
  struct _RTL_CRITICAL_SECTION *CriticalSection; // [rsp+98h] [rbp+20h]

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  CriticalSection = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  v5 = 0;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 48));
  v6 = (LB_RESOURCE_ID_CONFIG_ENTRY *)((char *)this + 24);
  v7 = *(LB_RPCHTTP_SERVER **)v6;
  if ( *(LB_RPCHTTP_SERVER **)v6 == v6 )
    goto LABEL_42;
  do
  {
    v8 = v7;
    v7 = *(LB_RPCHTTP_SERVER **)v7;
    v9 = v5 + 1;
    if ( *((_DWORD *)v8 + 48) != 1 )
      v9 = v5;
    v5 = v9;
  }
  while ( v7 != v6 );
  if ( !v9 )
  {
LABEL_42:
    RtlLeaveCriticalSection(v3);
    return 1722;
  }
  else
  {
    v10 = 8 * v9;
    if ( !is_mul_ok(v9, 8u) )
      v10 = -1;
    v11 = I_RpcAllocate(v10);
    if ( !v11 )
    {
      RtlLeaveCriticalSection(v3);
      return 14;
    }
    v13 = 8 * v5;
    if ( !is_mul_ok(v5, 8u) )
      v13 = -1;
    v14 = (HANDLE *)I_RpcAllocate(v13);
    lpHandles = v14;
    if ( !v14 )
    {
      RtlLeaveCriticalSection(v3);
      I_RpcFree(v11);
      return 14;
    }
    v15 = *(LB_RPCHTTP_SERVER **)v6;
    v16 = 0;
    v17 = 87;
    if ( *(LB_RPCHTTP_SERVER **)v6 != v6 )
    {
      v18 = v14;
      do
      {
        v19 = v15;
        v15 = *(LB_RPCHTTP_SERVER **)v15;
        if ( *((_DWORD *)v19 + 48) == 1 )
        {
          LB_RPCHTTP_SERVER::AddReference(v19);
          *((_QWORD *)v11 + v16) = v19;
          v18[v16] = (HANDLE)*((_QWORD *)v19 + 16);
          v16 = (unsigned int)(v16 + 1);
        }
      }
      while ( v15 != v6 );
      v3 = CriticalSection;
      v17 = 87;
    }
    if ( a3 )
      RtlLeaveCriticalSection(v3);
    v20 = v5 - 1;
    v21 = 0;
    v22 = v5;
    v23 = a2 + ((MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24);
    do
    {
      v24 = CalculateRemainingTimeout(v23);
      v25 = WaitForMultipleObjects(v5, lpHandles, 0, v24);
      v26 = v25;
      if ( v25 <= v20 )
      {
        --v22;
        v17 = LB_RPCHTTP_SERVER::CompleteCall(*((LB_RPCHTTP_SERVER **)v11 + v25));
        if ( !v17 )
          ++v21;
      }
    }
    while ( v22 && v26 <= v20 );
    if ( v21 )
    {
      v27 = 0;
    }
    else
    {
      v27 = 258;
      if ( !v22 )
        v27 = v17;
    }
    for ( i = 0; (unsigned int)i < v5; i = (unsigned int)(i + 1) )
    {
      v29 = *((_QWORD *)v11 + i);
      if ( *(_DWORD *)(v29 + 192) == 1 && (*(_DWORD *)(v29 + 196))-- == 1 )
      {
        RpcAsyncCancelCall((PRPC_ASYNC_STATE)(v29 + 80), 1);
        WaitForSingleObject(*(HANDLE *)(v29 + 128), 0xFFFFFFFF);
        RpcAsyncCompleteCall((PRPC_ASYNC_STATE)(v29 + 80), 0);
        LB_RPCHTTP_SERVER::RemoveReference((LB_RPCHTTP_SERVER *)v29);
        *(_DWORD *)(v29 + 192) = 2;
        *(_DWORD *)(v29 + 200) = 0;
        RpcBindingFree((RPC_BINDING_HANDLE *)(v29 + 72));
      }
      LB_RPCHTTP_SERVER::RemoveReference((LB_RPCHTTP_SERVER *)v29);
    }
    *((_DWORD *)this + 33) = 1;
    if ( !a3 )
      RtlLeaveCriticalSection(CriticalSection);
    I_RpcFree(v11);
    I_RpcFree(lpHandles);
    return v27;
  }
}

```

## disassembly

```asm
0x1800237c8  mov     [rsp+arg_10], r8d
0x1800237cd  mov     [rsp+arg_8], edx
0x1800237d1  mov     [rsp+arg_0], rcx
0x1800237d6  push    rbx
0x1800237d7  push    rbp
0x1800237d8  push    rsi
0x1800237d9  push    rdi
0x1800237da  push    r12
0x1800237dc  push    r13
0x1800237de  push    r14
0x1800237e0  push    r15
0x1800237e2  sub     rsp, 38h
0x1800237e6  lea     rbp, [rcx+30h]
0x1800237ea  mov     rbx, rcx
0x1800237ed  mov     rcx, rbp; CriticalSection
0x1800237f0  mov     [rsp+78h+CriticalSection], rbp
0x1800237f8  xor     esi, esi
0x1800237fa  call    cs:__imp_RtlEnterCriticalSection
0x180023800  add     rbx, 18h
0x180023804  mov     r9, [rbx]
0x180023807  cmp     r9, rbx
0x18002380a  jz      loc_180023A46
0x180023810  lea     rax, [r9]
0x180023813  mov     r9, [r9]
0x180023816  cmp     dword ptr [rax+0C0h], 1
0x18002381d  lea     ecx, [rsi+1]
0x180023820  cmovnz  ecx, esi
0x180023823  mov     esi, ecx
0x180023825  cmp     r9, rbx
0x180023828  jnz     short loc_180023810
0x18002382a  test    ecx, ecx
0x18002382c  jz      loc_180023A46
0x180023832  mov     r14d, 8
0x180023838  mov     edi, esi
0x18002383a  mov     eax, r14d
0x18002383d  mul     rsi
0x180023840  lea     r15, [r14-9]
0x180023844  cmovb   rax, r15
0x180023848  mov     ecx, eax; Size
0x18002384a  call    cs:__imp_I_RpcAllocate
0x180023850  mov     r12, rax
0x180023853  test    rax, rax
0x180023856  jnz     short loc_18002386B
0x180023858  mov     rcx, rbp; CriticalSection
0x18002385b  call    cs:__imp_RtlLeaveCriticalSection
0x180023861  mov     eax, 0Eh
0x180023866  jmp     loc_180023A54
0x18002386b  mov     rax, r14
0x18002386e  mul     rdi
0x180023871  cmovb   rax, r15
0x180023875  mov     ecx, eax; Size
0x180023877  call    cs:__imp_I_RpcAllocate
0x18002387d  mov     [rsp+78h+lpHandles], rax
0x180023882  test    rax, rax
0x180023885  jnz     short loc_18002389B
0x180023887  mov     rcx, rbp; CriticalSection
0x18002388a  call    cs:__imp_RtlLeaveCriticalSection
0x180023890  mov     rcx, r12; Object
0x180023893  call    cs:__imp_I_RpcFree
0x180023899  jmp     short loc_180023861
0x18002389b  mov     rdi, [rbx]
0x18002389e  xor     r15d, r15d
0x1800238a1  mov     r13d, 57h ; 'W'
0x1800238a7  cmp     rdi, rbx
0x1800238aa  jz      short loc_1800238F0
0x1800238ac  mov     rbp, rax
0x1800238af  mov     r13, rdi
0x1800238b2  mov     r14, rdi
0x1800238b5  mov     rdi, [rdi]
0x1800238b8  cmp     dword ptr [r13+0C0h], 1
0x1800238c0  jnz     short loc_1800238DD
0x1800238c2  mov     rcx, r13; this
0x1800238c5  call    ?AddReference@LB_RPCHTTP_SERVER@@QEAAXXZ; LB_RPCHTTP_SERVER::AddReference(void)
0x1800238ca  mov     [r12+r15*8], r13
0x1800238ce  mov     rax, [r13+80h]
0x1800238d5  mov     [rbp+r15*8+0], rax
0x1800238da  inc     r15d
0x1800238dd  cmp     rdi, rbx
0x1800238e0  jnz     short loc_1800238AF
0x1800238e2  mov     rbp, [rsp+78h+CriticalSection]
0x1800238ea  mov     r13d, 57h ; 'W'
0x1800238f0  cmp     [rsp+78h+arg_10], 0
0x1800238f8  jz      short loc_180023903
0x1800238fa  mov     rcx, rbp; CriticalSection
0x1800238fd  call    cs:__imp_RtlLeaveCriticalSection
0x180023903  mov     eax, 7FFE0320h
0x180023908  lea     ebp, [rsi-1]
0x18002390b  xor     r14d, r14d
0x18002390e  mov     ebx, esi
0x180023910  mov     rax, [rax]
0x180023913  mov     edi, ds:7FFE0004h
0x18002391a  imul    rdi, rax
0x18002391e  shr     rdi, 18h
0x180023922  add     edi, [rsp+78h+arg_8]
0x180023929  mov     ecx, edi; unsigned int
0x18002392b  call    ?CalculateRemainingTimeout@@YAKK@Z; CalculateRemainingTimeout(ulong)
0x180023930  mov     rdx, [rsp+78h+lpHandles]; lpHandles
0x180023935  mov     r9d, eax; dwMilliseconds
0x180023938  mov     ecx, esi; nCount
0x18002393a  xor     r8d, r8d; bWaitAll
0x18002393d  call    cs:__imp_WaitForMultipleObjects
0x180023943  mov     r15d, eax
0x180023946  cmp     eax, ebp
0x180023948  ja      short loc_18002395F
0x18002394a  mov     rcx, [r12+r15*8]; this
0x18002394e  dec     ebx
0x180023950  call    ?CompleteCall@LB_RPCHTTP_SERVER@@AEAAJXZ; LB_RPCHTTP_SERVER::CompleteCall(void)
0x180023955  mov     r13d, eax
0x180023958  test    eax, eax
0x18002395a  jnz     short loc_18002395F
0x18002395c  inc     r14d
0x18002395f  test    ebx, ebx
0x180023961  jz      short loc_180023968
0x180023963  cmp     r15d, ebp
0x180023966  jbe     short loc_180023929
0x180023968  test    r14d, r14d
0x18002396b  jnz     short loc_18002397B
0x18002396d  test    ebx, ebx
0x18002396f  mov     r14d, 102h
0x180023975  cmovz   r14d, r13d
0x180023979  jmp     short loc_18002397E
0x18002397b  xor     r14d, r14d
0x18002397e  mov     rbp, [rsp+78h+CriticalSection]
0x180023986  xor     r15d, r15d
0x180023989  test    esi, esi
0x18002398b  jz      short loc_180023A08
0x18002398d  mov     rdi, [r12+r15*8]
0x180023991  cmp     dword ptr [rdi+0C0h], 1
0x180023998  jnz     short loc_1800239F8
0x18002399a  or      r13d, 0FFFFFFFFh
0x18002399e  add     [rdi+0C4h], r13d
0x1800239a5  jnz     short loc_1800239F8
0x1800239a7  mov     edx, 1; fAbort
0x1800239ac  lea     rcx, [rdi+50h]; pAsync
0x1800239b0  call    cs:__imp_RpcAsyncCancelCall
0x1800239b6  mov     rcx, [rdi+80h]; hHandle
0x1800239bd  mov     edx, r13d; dwMilliseconds
0x1800239c0  call    cs:__imp_WaitForSingleObject
0x1800239c6  xor     edx, edx; Reply
0x1800239c8  lea     rcx, [rdi+50h]; pAsync
0x1800239cc  call    cs:__imp_RpcAsyncCompleteCall
0x1800239d2  mov     rcx, rdi; this
0x1800239d5  call    ?RemoveReference@LB_RPCHTTP_SERVER@@QEAAXXZ; LB_RPCHTTP_SERVER::RemoveReference(void)
0x1800239da  lea     rcx, [rdi+48h]; Binding
0x1800239de  mov     dword ptr [rdi+0C0h], 2
0x1800239e8  mov     dword ptr [rdi+0C8h], 0
0x1800239f2  call    cs:__imp_RpcBindingFree
0x1800239f8  mov     rcx, rdi; this
0x1800239fb  call    ?RemoveReference@LB_RPCHTTP_SERVER@@QEAAXXZ; LB_RPCHTTP_SERVER::RemoveReference(void)
0x180023a00  inc     r15d
0x180023a03  cmp     r15d, esi
0x180023a06  jb      short loc_18002398D
0x180023a08  cmp     [rsp+78h+arg_10], 0
0x180023a10  mov     rax, [rsp+78h+arg_0]
0x180023a18  mov     dword ptr [rax+84h], 1
0x180023a22  jnz     short loc_180023A2D
0x180023a24  mov     rcx, rbp; CriticalSection
0x180023a27  call    cs:__imp_RtlLeaveCriticalSection
0x180023a2d  mov     rcx, r12; Object
0x180023a30  call    cs:__imp_I_RpcFree
0x180023a36  mov     rcx, [rsp+78h+lpHandles]; Object
0x180023a3b  call    cs:__imp_I_RpcFree
0x180023a41  mov     eax, r14d
0x180023a44  jmp     short loc_180023A54
0x180023a46  mov     rcx, rbp; CriticalSection
0x180023a49  call    cs:__imp_RtlLeaveCriticalSection
0x180023a4f  mov     eax, 6BAh
0x180023a54  add     rsp, 38h
0x180023a58  pop     r15
0x180023a5a  pop     r14
0x180023a5c  pop     r13
0x180023a5e  pop     r12
0x180023a60  pop     rdi
0x180023a61  pop     rsi
0x180023a62  pop     rbp
0x180023a63  pop     rbx
0x180023a64  retn
```
