# LRPC_SASSOCIATION::GetClientName(LRPC_SCALL *,ulong *,ushort * *)

- ea: `0x180087000`
- end: `0x18008732b`
- name: `?GetClientName@LRPC_SASSOCIATION@@QEAAJPEAVLRPC_SCALL@@PEAKPEAPEAG@Z`
- size: `811`
- prototype: `__int64 __fastcall(LRPC_SASSOCIATION *__hidden this, struct LRPC_SCALL *, unsigned int *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180079310`
- `0x180086f80`

## callees

- `0x18000fd70`
- `0x180016100`
- `0x180023020`
- `0x180023a40`
- `0x1800295d8`
- `0x180030cb8`
- `0x180087000`
- `0x180087334`
- `0x180087400`
- `0x1800ab038`
- `0x1800cec91`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800870f1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800871c1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800872b6`
- `ntdll!RtlLeaveCriticalSection` at `0x1800872f4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800870f1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800871c1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800872b6`
- `ntdll!RtlLeaveCriticalSection` at `0x1800872f4`
- `ntdll!RtlEnterCriticalSection` at `0x1800870d8`
- `ntdll!RtlEnterCriticalSection` at `0x180087124`
- `ntdll!RtlEnterCriticalSection` at `0x1800870d8`
- `ntdll!RtlEnterCriticalSection` at `0x180087124`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18008717f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18008717f`

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
  PSID pSid2; // [rsp+78h] [rbp+10h] BYREF
  unsigned int *v24; // [rsp+80h] [rbp+18h]

  v24 = a3;
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
        LRPC_SCONTEXT::`scalar deleting destructor'(v4);
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
        v6 = v24;
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
      LRPC_SCONTEXT::`scalar deleting destructor'(v4);
    }
    LODWORD(v11) = 14;
  }
  RtlLeaveCriticalSection(v20);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180087000  mov     [rsp+arg_0], rbx
0x180087005  mov     [rsp+arg_10], r8
0x18008700a  push    rbp
0x18008700b  push    rsi
0x18008700c  push    rdi
0x18008700d  push    r12
0x18008700f  push    r13
0x180087011  push    r14
0x180087013  push    r15
0x180087015  sub     rsp, 30h
0x180087019  mov     rbx, [rdx+218h]
0x180087020  xor     r12d, r12d
0x180087023  mov     [rsp+68h+pSid2], r12
0x180087028  mov     r15, r9
0x18008702b  mov     r14, r8
0x18008702e  mov     r13, rdx
0x180087031  mov     rsi, rcx
0x180087034  mov     ebp, r12d
0x180087037  test    rbx, rbx
0x18008703a  jz      loc_18008711D
0x180087040  mov     eax, 7FFE0320h
0x180087045  mov     rax, [rax]
0x180087048  mov     ecx, ds:7FFE0004h
0x18008704f  imul    rcx, rax
0x180087053  shr     rcx, 18h
0x180087057  mov     [rbx+2Ch], ecx
0x18008705a  mov     r8, r15; unsigned __int16 **
0x18008705d  mov     rdx, r14; unsigned int *
0x180087060  mov     rcx, rbx; this
0x180087063  call    ?GetUserNameW@LRPC_SCONTEXT@@QEAAJPEAKPEAPEAG@Z; LRPC_SCONTEXT::GetUserNameW(ulong *,ushort * *)
0x180087068  mov     edi, eax
0x18008706a  test    ebp, ebp
0x18008706c  jz      loc_1800870FD
0x180087072  test    eax, eax
0x180087074  jnz     short loc_1800870D1
0x180087076  test    r14, r14
0x180087079  jnz     short loc_1800870D1
0x18008707b  mov     rax, [r13+1B0h]
0x180087082  test    rax, rax
0x180087085  jnz     loc_1800872A6
0x18008708b  mov     rcx, [r15]
0x18008708e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180087092  inc     rax
0x180087095  cmp     [rcx+rax*2], r12w
0x18008709a  jnz     short loc_180087092
0x18008709c  lea     eax, ds:2[rax*2]
0x1800870a3  mov     ecx, eax; dwBytes
0x1800870a5  mov     r14d, eax
0x1800870a8  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800870ad  mov     rbp, rax
0x1800870b0  test    rax, rax
0x1800870b3  jz      loc_1800872EA
0x1800870b9  mov     rdx, [r15]; Src
0x1800870bc  mov     r8d, r14d; Size
0x1800870bf  mov     rcx, rax; void *
0x1800870c2  call    memcpy_0
0x1800870c7  mov     [r13+1B0h], rbp
0x1800870ce  mov     [r15], rbp
0x1800870d1  add     rsi, 70h ; 'p'
0x1800870d5  mov     rcx, rsi; CriticalSection
0x1800870d8  call    cs:__imp_RtlEnterCriticalSection
0x1800870df  nop     dword ptr [rax+rax+00h]
0x1800870e4  sub     dword ptr [rbx+10h], 1
0x1800870e8  mov     rcx, rsi; CriticalSection
0x1800870eb  jz      loc_1800872F4
0x1800870f1  call    cs:__imp_RtlLeaveCriticalSection
0x1800870f8  nop     dword ptr [rax+rax+00h]
0x1800870fd  test    edi, edi
0x1800870ff  jnz     loc_18008730D
0x180087105  mov     rbx, [rsp+68h+arg_0]
0x18008710a  mov     eax, edi
0x18008710c  add     rsp, 30h
0x180087110  pop     r15
0x180087112  pop     r14
0x180087114  pop     r13
0x180087116  pop     r12
0x180087118  pop     rdi
0x180087119  pop     rsi
0x18008711a  pop     rbp
0x18008711b  retn
0x18008711d  lea     r12, [rcx+70h]
0x180087121  mov     rcx, r12; CriticalSection
0x180087124  call    cs:__imp_RtlEnterCriticalSection
0x18008712b  nop     dword ptr [rax+rax+00h]
0x180087130  mov     rbx, [r13+218h]
0x180087137  test    rbx, rbx
0x18008713a  jnz     loc_180087287
0x180087140  lea     rdx, [rsp+68h+pSid2]; void **
0x180087145  mov     rcx, r13; this
0x180087148  call    ?GetClientSid@LRPC_SCALL@@QEAAJPEAPEAX@Z; LRPC_SCALL::GetClientSid(void * *)
0x18008714d  mov     edi, eax
0x18008714f  test    eax, eax
0x180087151  jnz     loc_1800872B3
0x180087157  lea     r14, [rsi+98h]
0x18008715e  mov     ebp, 1
0x180087163  cmp     edi, [r14+8]
0x180087167  jnb     short loc_1800871D5
0x180087169  mov     rax, [r14]
0x18008716c  mov     rbx, [rax+rdi*8]
0x180087170  inc     edi
0x180087172  test    rbx, rbx
0x180087175  jz      short loc_18008715E
0x180087177  mov     rdx, [rsp+68h+pSid2]; pSid2
0x18008717c  mov     rcx, [rbx]; pSid1
0x18008717f  call    cs:__imp_EqualSid
0x180087186  nop     dword ptr [rax+rax+00h]
0x18008718b  test    eax, eax
0x18008718d  jz      short loc_18008715E
0x18008718f  mov     rcx, [rsp+68h+pSid2]; lpMem
0x180087194  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180087199  mov     eax, 7FFE0320h
0x18008719e  mov     rax, [rax]
0x1800871a1  mov     ecx, ds:7FFE0004h
0x1800871a8  imul    rcx, rax
0x1800871ac  shr     rcx, 18h
0x1800871b0  mov     [rbx+2Ch], ecx
0x1800871b3  add     [rbx+10h], ebp
0x1800871b6  mov     r14, [rsp+68h+arg_10]
0x1800871be  mov     rcx, r12; CriticalSection
0x1800871c1  call    cs:__imp_RtlLeaveCriticalSection
0x1800871c8  nop     dword ptr [rax+rax+00h]
0x1800871cd  xor     r12d, r12d
0x1800871d0  jmp     loc_18008705A
0x1800871d5  mov     ecx, 30h ; '0'; dwBytes
0x1800871da  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800871df  xor     edi, edi
0x1800871e1  mov     rbx, rax
0x1800871e4  test    rax, rax
0x1800871e7  jz      loc_1800872AE
0x1800871ed  mov     [rax+8], rdi
0x1800871f1  mov     rdx, rbx; void *
0x1800871f4  mov     rax, [rsp+68h+pSid2]
0x1800871f9  mov     rcx, r14; this
0x1800871fc  mov     [rbx], rax
0x1800871ff  mov     [rbx+10h], ebp
0x180087202  mov     [rbx+28h], edi
0x180087205  mov     [rbx+18h], rsi
0x180087209  mov     [rbx+20h], rdi
0x18008720d  call    ?Insert@SIMPLE_DICT@@QEAAIPEAX@Z; SIMPLE_DICT::Insert(void *)
0x180087212  cmp     eax, 0FFFFFFFFh
0x180087215  jz      loc_1800872C7
0x18008721b  cmp     dword ptr [rsi+0A4h], 7D0h
0x180087225  ja      loc_1800872D1
0x18008722b  mov     eax, [rbx+28h]
0x18008722e  or      eax, 8
0x180087231  mov     [rbx+28h], eax
0x180087234  mov     eax, 7FFE0320h
0x180087239  mov     rax, [rax]
0x18008723c  mov     ecx, ds:7FFE0004h
0x180087243  imul    rcx, rax
0x180087247  shr     rcx, 18h
0x18008724b  mov     [rbx+2Ch], ecx
0x18008724e  mov     eax, [rsi+1B0h]
0x180087254  test    bpl, al
0x180087257  jnz     loc_1800871B3
0x18008725d  lock add cs:?EnableIdleLrpcSContextsCleanupCount@@3KA, ebp; ulong EnableIdleLrpcSContextsCleanupCount
0x180087264  mov     edx, 1D4C0h; unsigned int
0x180087269  xor     ecx, ecx; int
0x18008726b  call    ?GarbageCollectionNeeded@@YAHHK@Z; GarbageCollectionNeeded(int,ulong)
0x180087270  test    eax, eax
0x180087272  jz      short loc_1800872DE
0x180087274  mov     eax, [rsi+1B0h]
0x18008727a  or      eax, ebp
0x18008727c  mov     [rsi+1B0h], eax
0x180087282  jmp     loc_1800871B3
0x180087287  mov     eax, 7FFE0320h
0x18008728c  mov     rax, [rax]
0x18008728f  mov     ecx, ds:7FFE0004h
0x180087296  imul    rcx, rax
0x18008729a  shr     rcx, 18h
0x18008729e  mov     [rbx+2Ch], ecx
0x1800872a1  jmp     loc_1800871BE
0x1800872a6  mov     [r15], rax
0x1800872a9  jmp     loc_1800870D1
0x1800872ae  mov     edi, 0Eh
0x1800872b3  mov     rcx, r12; CriticalSection
0x1800872b6  call    cs:__imp_RtlLeaveCriticalSection
0x1800872bd  nop     dword ptr [rax+rax+00h]
0x1800872c2  jmp     loc_180087105
0x1800872c7  mov     rcx, rbx; this
0x1800872ca  call    ??_GLRPC_SCONTEXT@@QEAAPEAXI@Z; LRPC_SCONTEXT::`scalar deleting destructor'(uint)
0x1800872cf  jmp     short loc_1800872AE
0x1800872d1  mov     rcx, rsi; this
0x1800872d4  call    ?AgeOldestCachedSContext@LRPC_SASSOCIATION@@AEAAXXZ; LRPC_SASSOCIATION::AgeOldestCachedSContext(void)
0x1800872d9  jmp     loc_18008722B
0x1800872de  lock dec cs:?EnableIdleLrpcSContextsCleanupCount@@3KA; ulong EnableIdleLrpcSContextsCleanupCount
0x1800872e5  jmp     loc_1800871B3
0x1800872ea  mov     edi, 0Eh
0x1800872ef  jmp     loc_1800870D1
0x1800872f4  call    cs:__imp_RtlLeaveCriticalSection
0x1800872fb  nop     dword ptr [rax+rax+00h]
0x180087300  mov     rcx, rbx; this
0x180087303  call    ??_GLRPC_SCONTEXT@@QEAAPEAXI@Z; LRPC_SCONTEXT::`scalar deleting destructor'(uint)
0x180087308  jmp     loc_1800870FD
0x18008730d  xor     r9d, r9d; int
0x180087310  mov     [rsp+68h+var_48], r12; struct tagParam *
0x180087315  mov     r8d, 49Ch; unsigned __int16
0x18008731b  mov     edx, edi; int
0x18008731d  lea     ecx, [r9+2]; unsigned int
0x180087321  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180087326  jmp     loc_180087105
```
