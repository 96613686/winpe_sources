# LRPC_SASSOCIATION::GetClientName(LRPC_SCALL *,ulong *,ushort * *)

- ea: `0x180085070`
- end: `0x18008536c`
- name: `?GetClientName@LRPC_SASSOCIATION@@QEAAJPEAVLRPC_SCALL@@PEAKPEAPEAG@Z`
- size: `764`
- prototype: `__int64 __fastcall(LRPC_SASSOCIATION *__hidden this, struct LRPC_SCALL *, unsigned int *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007a220`
- `0x180084ff0`

## callees

- `0x180021e70`
- `0x180022870`
- `0x1800283bc`
- `0x18002f928`
- `0x18004c8b0`
- `0x18004f480`
- `0x180085070`
- `0x180085374`
- `0x180085440`
- `0x1800a7758`
- `0x1800ca031`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180085157`
- `ntdll!RtlLeaveCriticalSection` at `0x180085214`
- `ntdll!RtlLeaveCriticalSection` at `0x180085303`
- `ntdll!RtlLeaveCriticalSection` at `0x18008533b`
- `ntdll!RtlLeaveCriticalSection` at `0x180085157`
- `ntdll!RtlLeaveCriticalSection` at `0x180085214`
- `ntdll!RtlLeaveCriticalSection` at `0x180085303`
- `ntdll!RtlLeaveCriticalSection` at `0x18008533b`
- `ntdll!RtlEnterCriticalSection` at `0x180085144`
- `ntdll!RtlEnterCriticalSection` at `0x180085183`
- `ntdll!RtlEnterCriticalSection` at `0x180085144`
- `ntdll!RtlEnterCriticalSection` at `0x180085183`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800851d8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800851d8`

## pseudocode

```c
__int64 __fastcall LRPC_SASSOCIATION::GetClientName(
        LRPC_SASSOCIATION *this,
        struct LRPC_SCALL *a2,
        unsigned int *a3,
        unsigned __int16 **a4)
{
  LRPC_SCONTEXT *v4; // rbx
  unsigned int *v6; // r14
  int v9; // ebp
  int UserNameW; // eax
  __int64 v11; // rdi
  unsigned __int16 *v12; // rax
  __int64 v13; // rax
  SIZE_T v14; // r14
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rbp
  struct _RTL_CRITICAL_SECTION *v17; // rsi
  struct _RTL_CRITICAL_SECTION *v20; // r12
  unsigned int ClientSid; // eax
  LRPC_SCONTEXT *v22; // rax
  unsigned int v23; // edx
  unsigned int v24; // edx
  PSID pSid2; // [rsp+78h] [rbp+10h] BYREF
  unsigned int *v26; // [rsp+80h] [rbp+18h]

  v26 = a3;
  v4 = (LRPC_SCONTEXT *)*((_QWORD *)a2 + 67);
  pSid2 = 0;
  v6 = a3;
  v9 = 0;
  if ( v4 )
  {
    *((_DWORD *)v4 + 11) = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
LABEL_3:
    UserNameW = LRPC_SCONTEXT::GetUserNameW(v4, v6, a4);
    LODWORD(v11) = UserNameW;
    if ( v9 )
    {
      if ( !UserNameW && !v6 )
      {
        v12 = (unsigned __int16 *)*((_QWORD *)a2 + 54);
        if ( v12 )
        {
          *a4 = v12;
        }
        else
        {
          v13 = -1;
          do
            ++v13;
          while ( (*a4)[v13] );
          v14 = (unsigned int)(2 * v13 + 2);
          v15 = (unsigned __int16 *)AllocWrapper(v14);
          v16 = v15;
          if ( v15 )
          {
            memcpy_0(v15, *a4, (unsigned int)v14);
            *((_QWORD *)a2 + 54) = v16;
            *a4 = v16;
          }
          else
          {
            LODWORD(v11) = 14;
          }
        }
      }
      v17 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 112);
      RtlEnterCriticalSection(v17);
      if ( (*((_DWORD *)v4 + 4))-- == 1 )
      {
        RtlLeaveCriticalSection(v17);
        LRPC_SCONTEXT::`scalar deleting destructor'(v4, v24);
      }
      else
      {
        RtlLeaveCriticalSection(v17);
      }
    }
    if ( (_DWORD)v11 )
      RpcpErrorAddRecord(2u, v11, 0x49Cu, 0, 0);
    return (unsigned int)v11;
  }
  v20 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 112);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 112));
  v4 = (LRPC_SCONTEXT *)*((_QWORD *)a2 + 67);
  if ( v4 )
  {
    *((_DWORD *)v4 + 11) = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
LABEL_23:
    RtlLeaveCriticalSection(v20);
    goto LABEL_3;
  }
  ClientSid = LRPC_SCALL::GetClientSid(a2, &pSid2);
  v11 = ClientSid;
  if ( !ClientSid )
  {
    while ( 1 )
    {
      v9 = 1;
      if ( (unsigned int)v11 >= *((_DWORD *)this + 40) )
        break;
      v4 = *(LRPC_SCONTEXT **)(*((_QWORD *)this + 19) + 8 * v11);
      v11 = (unsigned int)(v11 + 1);
      if ( v4 && EqualSid(*(PSID *)v4, pSid2) )
      {
        FreeWrapper(pSid2);
        *((_DWORD *)v4 + 11) = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
LABEL_22:
        ++*((_DWORD *)v4 + 4);
        v6 = v26;
        goto LABEL_23;
      }
    }
    v22 = (LRPC_SCONTEXT *)AllocWrapper(0x30u);
    v4 = v22;
    if ( v22 )
    {
      *((_QWORD *)v22 + 1) = 0;
      *(_QWORD *)v22 = pSid2;
      *((_DWORD *)v22 + 4) = 1;
      *((_DWORD *)v22 + 10) = 0;
      *((_QWORD *)v22 + 3) = this;
      *((_QWORD *)v22 + 4) = 0;
      if ( SIMPLE_DICT::Insert((LRPC_SASSOCIATION *)((char *)this + 152), v22) != -1 )
      {
        if ( *((_DWORD *)this + 41) > 0x7D0u )
          LRPC_SASSOCIATION::AgeOldestCachedSContext(this);
        *((_DWORD *)v4 + 10) |= 8u;
        *((_DWORD *)v4 + 11) = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
        if ( (*((_DWORD *)this + 108) & 1) == 0 )
        {
          _InterlockedAdd((volatile signed __int32 *)&EnableIdleLrpcSContextsCleanupCount, 1u);
          if ( (unsigned int)GarbageCollectionNeeded(0, 0x1D4C0u) )
            *((_DWORD *)this + 108) |= 1u;
          else
            _InterlockedDecrement((volatile signed __int32 *)&EnableIdleLrpcSContextsCleanupCount);
        }
        goto LABEL_22;
      }
      LRPC_SCONTEXT::`scalar deleting destructor'(v4, v23);
    }
    LODWORD(v11) = 14;
  }
  RtlLeaveCriticalSection(v20);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180085070  mov     [rsp+arg_0], rbx
0x180085075  mov     [rsp+arg_10], r8
0x18008507a  push    rbp
0x18008507b  push    rsi
0x18008507c  push    rdi
0x18008507d  push    r12
0x18008507f  push    r13
0x180085081  push    r14
0x180085083  push    r15
0x180085085  sub     rsp, 30h
0x180085089  mov     rbx, [rdx+218h]
0x180085090  xor     r12d, r12d
0x180085093  mov     [rsp+68h+pSid2], r12
0x180085098  mov     r15, r9
0x18008509b  mov     r14, r8
0x18008509e  mov     r13, rdx
0x1800850a1  mov     rsi, rcx
0x1800850a4  mov     ebp, r12d
0x1800850a7  test    rbx, rbx
0x1800850aa  jz      loc_18008517C
0x1800850b0  mov     eax, 7FFE0320h
0x1800850b5  mov     rax, [rax]
0x1800850b8  mov     ecx, ds:7FFE0004h
0x1800850bf  imul    rcx, rax
0x1800850c3  shr     rcx, 18h
0x1800850c7  mov     [rbx+2Ch], ecx
0x1800850ca  mov     r8, r15; unsigned __int16 **
0x1800850cd  mov     rdx, r14; unsigned int *
0x1800850d0  mov     rcx, rbx; this
0x1800850d3  call    ?GetUserNameW@LRPC_SCONTEXT@@QEAAJPEAKPEAPEAG@Z; LRPC_SCONTEXT::GetUserNameW(ulong *,ushort * *)
0x1800850d8  mov     edi, eax
0x1800850da  test    ebp, ebp
0x1800850dc  jz      short loc_18008515D
0x1800850de  test    eax, eax
0x1800850e0  jnz     short loc_18008513D
0x1800850e2  test    r14, r14
0x1800850e5  jnz     short loc_18008513D
0x1800850e7  mov     rax, [r13+1B0h]
0x1800850ee  test    rax, rax
0x1800850f1  jnz     loc_1800852F3
0x1800850f7  mov     rcx, [r15]
0x1800850fa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800850fe  inc     rax
0x180085101  cmp     [rcx+rax*2], r12w
0x180085106  jnz     short loc_1800850FE
0x180085108  lea     eax, ds:2[rax*2]
0x18008510f  mov     ecx, eax; dwBytes
0x180085111  mov     r14d, eax
0x180085114  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180085119  mov     rbp, rax
0x18008511c  test    rax, rax
0x18008511f  jz      loc_180085331
0x180085125  mov     rdx, [r15]; Src
0x180085128  mov     r8d, r14d; Size
0x18008512b  mov     rcx, rax; void *
0x18008512e  call    memcpy_0
0x180085133  mov     [r13+1B0h], rbp
0x18008513a  mov     [r15], rbp
0x18008513d  add     rsi, 70h ; 'p'
0x180085141  mov     rcx, rsi; CriticalSection
0x180085144  call    cs:__imp_RtlEnterCriticalSection
0x18008514a  sub     dword ptr [rbx+10h], 1
0x18008514e  mov     rcx, rsi; CriticalSection
0x180085151  jz      loc_18008533B
0x180085157  call    cs:__imp_RtlLeaveCriticalSection
0x18008515d  test    edi, edi
0x18008515f  jnz     loc_18008534E
0x180085165  mov     rbx, [rsp+68h+arg_0]
0x18008516a  mov     eax, edi
0x18008516c  add     rsp, 30h
0x180085170  pop     r15
0x180085172  pop     r14
0x180085174  pop     r13
0x180085176  pop     r12
0x180085178  pop     rdi
0x180085179  pop     rsi
0x18008517a  pop     rbp
0x18008517b  retn
0x18008517c  lea     r12, [rcx+70h]
0x180085180  mov     rcx, r12; CriticalSection
0x180085183  call    cs:__imp_RtlEnterCriticalSection
0x180085189  mov     rbx, [r13+218h]
0x180085190  test    rbx, rbx
0x180085193  jnz     loc_1800852D4
0x180085199  lea     rdx, [rsp+68h+pSid2]; void **
0x18008519e  mov     rcx, r13; this
0x1800851a1  call    ?GetClientSid@LRPC_SCALL@@QEAAJPEAPEAX@Z; LRPC_SCALL::GetClientSid(void * *)
0x1800851a6  mov     edi, eax
0x1800851a8  test    eax, eax
0x1800851aa  jnz     loc_180085300
0x1800851b0  lea     r14, [rsi+98h]
0x1800851b7  mov     ebp, 1
0x1800851bc  cmp     edi, [r14+8]
0x1800851c0  jnb     short loc_180085222
0x1800851c2  mov     rax, [r14]
0x1800851c5  mov     rbx, [rax+rdi*8]
0x1800851c9  inc     edi
0x1800851cb  test    rbx, rbx
0x1800851ce  jz      short loc_1800851B7
0x1800851d0  mov     rdx, [rsp+68h+pSid2]; pSid2
0x1800851d5  mov     rcx, [rbx]; pSid1
0x1800851d8  call    cs:__imp_EqualSid
0x1800851de  test    eax, eax
0x1800851e0  jz      short loc_1800851B7
0x1800851e2  mov     rcx, [rsp+68h+pSid2]; lpMem
0x1800851e7  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800851ec  mov     eax, 7FFE0320h
0x1800851f1  mov     rax, [rax]
0x1800851f4  mov     ecx, ds:7FFE0004h
0x1800851fb  imul    rcx, rax
0x1800851ff  shr     rcx, 18h
0x180085203  mov     [rbx+2Ch], ecx
0x180085206  add     [rbx+10h], ebp
0x180085209  mov     r14, [rsp+68h+arg_10]
0x180085211  mov     rcx, r12; CriticalSection
0x180085214  call    cs:__imp_RtlLeaveCriticalSection
0x18008521a  xor     r12d, r12d
0x18008521d  jmp     loc_1800850CA
0x180085222  mov     ecx, 30h ; '0'; dwBytes
0x180085227  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18008522c  xor     edi, edi
0x18008522e  mov     rbx, rax
0x180085231  test    rax, rax
0x180085234  jz      loc_1800852FB
0x18008523a  mov     [rax+8], rdi
0x18008523e  mov     rdx, rbx; void *
0x180085241  mov     rax, [rsp+68h+pSid2]
0x180085246  mov     rcx, r14; this
0x180085249  mov     [rbx], rax
0x18008524c  mov     [rbx+10h], ebp
0x18008524f  mov     [rbx+28h], edi
0x180085252  mov     [rbx+18h], rsi
0x180085256  mov     [rbx+20h], rdi
0x18008525a  call    ?Insert@SIMPLE_DICT@@QEAAIPEAX@Z; SIMPLE_DICT::Insert(void *)
0x18008525f  cmp     eax, 0FFFFFFFFh
0x180085262  jz      loc_18008530E
0x180085268  cmp     dword ptr [rsi+0A4h], 7D0h
0x180085272  ja      loc_180085318
0x180085278  mov     eax, [rbx+28h]
0x18008527b  or      eax, 8
0x18008527e  mov     [rbx+28h], eax
0x180085281  mov     eax, 7FFE0320h
0x180085286  mov     rax, [rax]
0x180085289  mov     ecx, ds:7FFE0004h
0x180085290  imul    rcx, rax
0x180085294  shr     rcx, 18h
0x180085298  mov     [rbx+2Ch], ecx
0x18008529b  mov     eax, [rsi+1B0h]
0x1800852a1  test    bpl, al
0x1800852a4  jnz     loc_180085206
0x1800852aa  lock add cs:?EnableIdleLrpcSContextsCleanupCount@@3KA, ebp; ulong EnableIdleLrpcSContextsCleanupCount
0x1800852b1  mov     edx, 1D4C0h; unsigned int
0x1800852b6  xor     ecx, ecx; int
0x1800852b8  call    ?GarbageCollectionNeeded@@YAHHK@Z; GarbageCollectionNeeded(int,ulong)
0x1800852bd  test    eax, eax
0x1800852bf  jz      short loc_180085325
0x1800852c1  mov     eax, [rsi+1B0h]
0x1800852c7  or      eax, ebp
0x1800852c9  mov     [rsi+1B0h], eax
0x1800852cf  jmp     loc_180085206
0x1800852d4  mov     eax, 7FFE0320h
0x1800852d9  mov     rax, [rax]
0x1800852dc  mov     ecx, ds:7FFE0004h
0x1800852e3  imul    rcx, rax
0x1800852e7  shr     rcx, 18h
0x1800852eb  mov     [rbx+2Ch], ecx
0x1800852ee  jmp     loc_180085211
0x1800852f3  mov     [r15], rax
0x1800852f6  jmp     loc_18008513D
0x1800852fb  mov     edi, 0Eh
0x180085300  mov     rcx, r12; CriticalSection
0x180085303  call    cs:__imp_RtlLeaveCriticalSection
0x180085309  jmp     loc_180085165
0x18008530e  mov     rcx, rbx; this
0x180085311  call    ??_GLRPC_SCONTEXT@@QEAAPEAXI@Z; LRPC_SCONTEXT::`scalar deleting destructor'(uint)
0x180085316  jmp     short loc_1800852FB
0x180085318  mov     rcx, rsi; this
0x18008531b  call    ?AgeOldestCachedSContext@LRPC_SASSOCIATION@@AEAAXXZ; LRPC_SASSOCIATION::AgeOldestCachedSContext(void)
0x180085320  jmp     loc_180085278
0x180085325  lock dec cs:?EnableIdleLrpcSContextsCleanupCount@@3KA; ulong EnableIdleLrpcSContextsCleanupCount
0x18008532c  jmp     loc_180085206
0x180085331  mov     edi, 0Eh
0x180085336  jmp     loc_18008513D
0x18008533b  call    cs:__imp_RtlLeaveCriticalSection
0x180085341  mov     rcx, rbx; this
0x180085344  call    ??_GLRPC_SCONTEXT@@QEAAPEAXI@Z; LRPC_SCONTEXT::`scalar deleting destructor'(uint)
0x180085349  jmp     loc_18008515D
0x18008534e  xor     r9d, r9d; int
0x180085351  mov     [rsp+68h+var_48], r12; struct tagParam *
0x180085356  mov     r8d, 49Ch; unsigned __int16
0x18008535c  mov     edx, edi; int
0x18008535e  lea     ecx, [r9+2]; unsigned int
0x180085362  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180085367  jmp     loc_180085165
```
