# LB_ARBITRATOR::WaitForCallSignal(ulong)

- ea: `0x18002199c`
- end: `0x180021c01`
- name: `?WaitForCallSignal@LB_ARBITRATOR@@AEAAPEAVLBS_CALL@@K@Z`
- size: `613`
- prototype: `struct LBS_CALL *(LB_ARBITRATOR *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020c3c`

## callees

- `0x18001f9f4`
- `0x18002199c`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x180021a12`
- `KERNEL32!WaitForMultipleObjects` at `0x180021a12`
- `RPCRT4!I_RpcFree` at `0x180021abd`
- `RPCRT4!I_RpcFree` at `0x180021b93`
- `RPCRT4!I_RpcFree` at `0x180021abd`
- `RPCRT4!I_RpcFree` at `0x180021b93`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180021a5e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180021b11`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180021a5e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180021b11`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180021ad3`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180021ba9`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180021bc0`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180021ad3`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180021ba9`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180021bc0`

## pseudocode

```c
struct LBS_CALL *__fastcall LB_ARBITRATOR::WaitForCallSignal(LB_ARBITRATOR *this, DWORD a2)
{
  __int64 *v2; // rdi
  DWORD v5; // esi
  unsigned int i; // r8d
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // rdx
  DWORD v10; // eax
  __int64 v11; // rbx
  bool v12; // zf
  struct _RPC_ASYNC_STATE *v13; // rcx
  _DWORD *v14; // rdi
  unsigned int v15; // esi
  void **v16; // r14
  _QWORD *v17; // rbp
  void **v18; // rbp
  unsigned int v19; // edi
  void *v20; // rcx
  __int64 v21; // r8

  v2 = (__int64 *)((char *)this + 24);
  v5 = 0;
  for ( i = 0; i < *((_DWORD *)this + 12); ++i )
  {
    v7 = *v2;
    v8 = 184LL * i;
    if ( *(_DWORD *)(v8 + *v2 + 152) == 1 && !*(_DWORD *)(v8 + v7 + 160) )
    {
      v9 = v5++;
      *(_QWORD *)(*((_QWORD *)this + 4) + 8 * v9) = *(_QWORD *)(v8 + v7 + 56);
      *(_DWORD *)(*((_QWORD *)this + 5) + 4 * v9) = i;
    }
  }
  v10 = WaitForMultipleObjects(v5, *((const HANDLE **)this + 4), 0, a2);
  if ( v10 <= v5 - 1 )
  {
    _mm_lfence();
    v11 = *v2 + 184LL * *(unsigned int *)(*((_QWORD *)this + 5) + 4LL * v10);
    v12 = *(_DWORD *)(v11 + 148) == 1;
    v13 = (struct _RPC_ASYNC_STATE *)(v11 + 8);
    *(_DWORD *)(v11 + 152) = 2;
    if ( v12 )
    {
      v14 = (_DWORD *)(v11 + 144);
      v15 = RpcAsyncCompleteCall(v13, (void *)(v11 + 144));
      if ( v15 )
      {
LABEL_57:
        v21 = v15;
LABEL_58:
        LBS_CALL::ChangeCallState(v11, 6, v21);
        return (struct LBS_CALL *)v11;
      }
      v16 = (void **)(v11 + 128);
      v17 = (_QWORD *)(v11 + 136);
      if ( *v14 )
      {
        if ( *v14 == 1 )
        {
          if ( !*v16 )
            v15 = 1728;
          if ( !*v17 )
            v15 = 1728;
        }
        else
        {
          if ( *v14 != 2 )
          {
            v15 = 1728;
LABEL_20:
            if ( *v16 )
            {
              I_RpcFree(*v16);
              *v16 = 0;
            }
            if ( *v17 )
              RpcSsDestroyClientContext((void **)(v11 + 136));
            goto LABEL_57;
          }
          if ( *(_WORD *)(v11 + 120) )
            v15 = 1728;
          if ( *v16 )
            v15 = 1728;
          if ( *v17 )
            v15 = 1728;
        }
      }
      else
      {
        if ( *(_WORD *)(v11 + 120) )
          v15 = 1728;
        if ( *v16 )
          v15 = 1728;
        if ( !*v17 )
        {
          v15 = 1728;
          goto LABEL_20;
        }
      }
      if ( v15 )
        goto LABEL_20;
      return (struct LBS_CALL *)v11;
    }
    v15 = RpcAsyncCompleteCall(v13, 0);
    if ( v15 )
    {
      if ( *(_QWORD *)(v11 + 136) )
        RpcSsDestroyClientContext((void **)(v11 + 136));
      if ( *(_DWORD *)(v11 + 148) == 2 && v15 == 1168 )
        v15 = 1722;
      goto LABEL_57;
    }
    if ( *(_DWORD *)(v11 + 148) == 2 )
    {
      v18 = (void **)(v11 + 136);
      v19 = 1728;
      if ( !*(_QWORD *)(v11 + 128) )
        v15 = 1728;
      if ( *v18 )
      {
        v19 = v15;
        if ( !v15 )
          return (struct LBS_CALL *)v11;
      }
    }
    else
    {
      if ( *(_DWORD *)(v11 + 148) == 3 )
      {
        v18 = (void **)(v11 + 136);
        if ( !*(_QWORD *)(v11 + 136) )
          return (struct LBS_CALL *)v11;
      }
      else
      {
        if ( *(_DWORD *)(v11 + 148) != 4 )
          return (struct LBS_CALL *)v11;
        v18 = (void **)(v11 + 136);
        if ( *(_QWORD *)(v11 + 136) )
          return (struct LBS_CALL *)v11;
      }
      v19 = 1728;
    }
    v20 = *(void **)(v11 + 128);
    if ( v20 )
    {
      I_RpcFree(v20);
      *(_QWORD *)(v11 + 128) = 0;
    }
    if ( *v18 )
      RpcSsDestroyClientContext(v18);
    v21 = v19;
    goto LABEL_58;
  }
  return 0;
}

```

## disassembly

```asm
0x18002199c  push    rbx
0x18002199e  push    rbp
0x18002199f  push    rsi
0x1800219a0  push    rdi
0x1800219a1  push    r14
0x1800219a3  push    r15
0x1800219a5  sub     rsp, 28h
0x1800219a9  xor     r15d, r15d
0x1800219ac  lea     rdi, [rcx+18h]
0x1800219b0  mov     r10d, edx
0x1800219b3  mov     rbx, rcx
0x1800219b6  mov     esi, r15d
0x1800219b9  mov     r8d, r15d
0x1800219bc  cmp     [rcx+30h], r15d
0x1800219c0  jbe     short loc_180021A06
0x1800219c2  mov     r9, [rdi]
0x1800219c5  mov     eax, r8d
0x1800219c8  imul    rax, 0B8h
0x1800219cf  cmp     dword ptr [rax+r9+98h], 1
0x1800219d8  jnz     short loc_1800219FD
0x1800219da  cmp     [rax+r9+0A0h], r15d
0x1800219e2  jnz     short loc_1800219FD
0x1800219e4  mov     rax, [rax+r9+38h]
0x1800219e9  mov     rcx, [rbx+20h]
0x1800219ed  mov     edx, esi
0x1800219ef  inc     esi
0x1800219f1  mov     [rcx+rdx*8], rax
0x1800219f5  mov     rax, [rbx+28h]
0x1800219f9  mov     [rax+rdx*4], r8d
0x1800219fd  inc     r8d
0x180021a00  cmp     r8d, [rbx+30h]
0x180021a04  jb      short loc_1800219C2
0x180021a06  mov     rdx, [rbx+20h]; lpHandles
0x180021a0a  mov     r9d, r10d; dwMilliseconds
0x180021a0d  xor     r8d, r8d; bWaitAll
0x180021a10  mov     ecx, esi; nCount
0x180021a12  call    cs:__imp_WaitForMultipleObjects
0x180021a18  lea     ecx, [rsi-1]
0x180021a1b  cmp     eax, ecx
0x180021a1d  ja      loc_180021BF2
0x180021a23  lfence
0x180021a26  mov     ecx, eax
0x180021a28  mov     rax, [rbx+28h]
0x180021a2c  mov     ecx, [rax+rcx*4]
0x180021a2f  imul    rbx, rcx, 0B8h
0x180021a36  add     rbx, [rdi]
0x180021a39  cmp     dword ptr [rbx+94h], 1
0x180021a40  lea     rcx, [rbx+8]; pAsync
0x180021a44  mov     dword ptr [rbx+98h], 2
0x180021a4e  jnz     loc_180021B0F
0x180021a54  lea     rdi, [rbx+90h]
0x180021a5b  mov     rdx, rdi; Reply
0x180021a5e  call    cs:__imp_RpcAsyncCompleteCall
0x180021a64  mov     esi, eax
0x180021a66  test    eax, eax
0x180021a68  jnz     loc_180021BDD
0x180021a6e  mov     ecx, [rdi]
0x180021a70  lea     r14, [rbx+80h]
0x180021a77  lea     rbp, [rbx+88h]
0x180021a7e  test    ecx, ecx
0x180021a80  jz      short loc_180021AF2
0x180021a82  sub     ecx, 1
0x180021a85  jz      short loc_180021ADE
0x180021a87  cmp     ecx, 1
0x180021a8a  jz      short loc_180021A93
0x180021a8c  mov     esi, 6C0h
0x180021a91  jmp     short loc_180021AB5
0x180021a93  cmp     [rbx+78h], r15w
0x180021a98  mov     edi, 6C0h
0x180021a9d  cmovnz  esi, edi
0x180021aa0  cmp     [r14], r15
0x180021aa3  cmovnz  esi, edi
0x180021aa6  cmp     [rbp+0], r15
0x180021aaa  cmovnz  esi, edi
0x180021aad  test    esi, esi
0x180021aaf  jz      loc_180021BED
0x180021ab5  mov     rcx, [r14]; Object
0x180021ab8  test    rcx, rcx
0x180021abb  jz      short loc_180021AC6
0x180021abd  call    cs:__imp_I_RpcFree
0x180021ac3  mov     [r14], r15
0x180021ac6  cmp     [rbp+0], r15
0x180021aca  jz      loc_180021BDD
0x180021ad0  mov     rcx, rbp; ContextHandle
0x180021ad3  call    cs:__imp_RpcSsDestroyClientContext
0x180021ad9  jmp     loc_180021BDD
0x180021ade  cmp     [r14], r15
0x180021ae1  mov     edi, 6C0h
0x180021ae6  cmovz   esi, edi
0x180021ae9  cmp     [rbp+0], r15
0x180021aed  cmovz   esi, edi
0x180021af0  jmp     short loc_180021AAD
0x180021af2  cmp     [rbx+78h], r15w
0x180021af7  mov     edi, 6C0h
0x180021afc  cmovnz  esi, edi
0x180021aff  cmp     [r14], r15
0x180021b02  cmovnz  esi, edi
0x180021b05  cmp     [rbp+0], r15
0x180021b09  jnz     short loc_180021AAD
0x180021b0b  mov     esi, edi
0x180021b0d  jmp     short loc_180021AB5
0x180021b0f  xor     edx, edx; Reply
0x180021b11  call    cs:__imp_RpcAsyncCompleteCall
0x180021b17  mov     esi, eax
0x180021b19  test    eax, eax
0x180021b1b  jnz     loc_180021BB4
0x180021b21  mov     eax, [rbx+94h]
0x180021b27  sub     eax, 2
0x180021b2a  jz      short loc_180021B65
0x180021b2c  sub     eax, 1
0x180021b2f  jz      short loc_180021B52
0x180021b31  cmp     eax, 1
0x180021b34  jnz     loc_180021BED
0x180021b3a  lea     rbp, [rbx+88h]
0x180021b41  cmp     [rbp+0], r15
0x180021b45  jnz     loc_180021BED
0x180021b4b  mov     edi, 6C0h
0x180021b50  jmp     short loc_180021B87
0x180021b52  lea     rbp, [rbx+88h]
0x180021b59  cmp     [rbp+0], r15
0x180021b5d  jz      loc_180021BED
0x180021b63  jmp     short loc_180021B4B
0x180021b65  cmp     [rbx+80h], r15
0x180021b6c  lea     rbp, [rbx+88h]
0x180021b73  mov     edi, 6C0h
0x180021b78  cmovz   esi, edi
0x180021b7b  cmp     [rbp+0], r15
0x180021b7f  jz      short loc_180021B87
0x180021b81  mov     edi, esi
0x180021b83  test    esi, esi
0x180021b85  jz      short loc_180021BED
0x180021b87  mov     rcx, [rbx+80h]; Object
0x180021b8e  test    rcx, rcx
0x180021b91  jz      short loc_180021BA0
0x180021b93  call    cs:__imp_I_RpcFree
0x180021b99  mov     [rbx+80h], r15
0x180021ba0  cmp     [rbp+0], r15
0x180021ba4  jz      short loc_180021BAF
0x180021ba6  mov     rcx, rbp; ContextHandle
0x180021ba9  call    cs:__imp_RpcSsDestroyClientContext
0x180021baf  mov     r8d, edi
0x180021bb2  jmp     short loc_180021BE0
0x180021bb4  lea     rcx, [rbx+88h]; ContextHandle
0x180021bbb  cmp     [rcx], r15
0x180021bbe  jz      short loc_180021BC6
0x180021bc0  call    cs:__imp_RpcSsDestroyClientContext
0x180021bc6  cmp     dword ptr [rbx+94h], 2
0x180021bcd  jnz     short loc_180021BDD
0x180021bcf  cmp     esi, 490h
0x180021bd5  mov     eax, 6BAh
0x180021bda  cmovz   esi, eax
0x180021bdd  mov     r8d, esi
0x180021be0  mov     edx, 6
0x180021be5  mov     rcx, rbx
0x180021be8  call    ?ChangeCallState@LBS_CALL@@QEAAXW4_CallStates@@J@Z; LBS_CALL::ChangeCallState(_CallStates,long)
0x180021bed  mov     rax, rbx
0x180021bf0  jmp     short loc_180021BF4
0x180021bf2  xor     eax, eax
0x180021bf4  add     rsp, 28h
0x180021bf8  pop     r15
0x180021bfa  pop     r14
0x180021bfc  pop     rdi
0x180021bfd  pop     rsi
0x180021bfe  pop     rbp
0x180021bff  pop     rbx
0x180021c00  retn
```
