# BCACHE::Allocate(unsigned __int64)

- ea: `0x1800206a0`
- end: `0x1800209e0`
- name: `?Allocate@BCACHE@@QEAAPEAX_K@Z`
- size: `832`
- prototype: `struct _SLIST_ENTRY *__fastcall(BCACHE *this, unsigned __int64)`
- caller_count: `42`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001dd40`
- `0x18001ebf0`
- `0x18001edd0`
- `0x18001f070`
- `0x18001f970`
- `0x180021fc0`
- `0x1800266f0`
- `0x1800354f4`
- `0x180047a30`
- `0x1800578fc`
- `0x1800592a8`
- `0x18005b1f0`
- `0x18005b55c`
- `0x18005e400`
- `0x180069618`
- `0x180070eb0`
- `0x1800716d8`
- `0x180075290`
- `0x180079cb4`
- `0x18007b320`
- `0x18007dc10`
- `0x18007f1f0`
- `0x18007f490`
- `0x18007f7f0`
- `0x18008cc70`
- `0x18008d670`
- `0x18008d880`
- `0x180091ae0`
- `0x1800960fc`
- `0x180096730`
- `0x18009e258`
- `0x18009e2fc`
- `0x1800a0330`
- `0x1800a05d0`
- `0x1800a7e24`
- `0x1800a86c0`
- `0x1800b8608`
- `0x1800b9370`
- `0x1800ba210`
- `0x1800ba708`
- `0x1800ccdc0`
- `0x1800cdaa0`

## callees

- `0x18001ed04`
- `0x1800206a0`
- `0x180021ce0`
- `0x180021e18`
- `0x180021e70`
- `0x1800ca140`

## import_xrefs

- `ntdll!RtlGetCurrentProcessorNumber` at `0x180020799`
- `ntdll!RtlGetCurrentProcessorNumber` at `0x180020799`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800207c2`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800207c2`

## pseudocode

```c
struct _SLIST_ENTRY *__fastcall BCACHE::Allocate(BCACHE *this, unsigned __int64 a2)
{
  unsigned __int64 v2; // rdi
  unsigned int i; // ebx
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  struct BCACHE *v7; // r14
  ULONG CurrentProcessorNumber; // eax
  union _SLIST_HEADER *v9; // rcx
  PSLIST_ENTRY v10; // rax
  int v11; // r8d
  PSLIST_ENTRY v12; // r14
  unsigned int j; // ecx
  SIZE_T v14; // rsi
  _DWORD *v15; // rax
  int v16; // r8d
  _DWORD *v17; // rdi
  unsigned int k; // ecx
  int v19; // [rsp+30h] [rbp-71h]
  int v20; // [rsp+38h] [rbp-69h]
  char v21; // [rsp+48h] [rbp-59h] BYREF
  char v22; // [rsp+50h] [rbp-51h] BYREF
  SIZE_T v23; // [rsp+58h] [rbp-49h] BYREF
  __int64 v24; // [rsp+60h] [rbp-41h] BYREF
  _QWORD v25[2]; // [rsp+68h] [rbp-39h] BYREF
  _BYTE v26[16]; // [rsp+78h] [rbp-29h] BYREF
  char *v27; // [rsp+88h] [rbp-19h]
  __int64 v28; // [rsp+90h] [rbp-11h]
  char *v29; // [rsp+98h] [rbp-9h]
  __int64 v30; // [rsp+A0h] [rbp-1h]
  SIZE_T *v31; // [rsp+A8h] [rbp+7h]
  __int64 v32; // [rsp+B0h] [rbp+Fh]
  __int64 *v33; // [rsp+B8h] [rbp+17h]
  __int64 v34; // [rsp+C0h] [rbp+1Fh]
  SIZE_T *v35; // [rsp+C8h] [rbp+27h]
  __int64 v36; // [rsp+D0h] [rbp+2Fh]

  v2 = ((_DWORD)a2 + 31) & 0xFFFFFFF0;
  if ( v2 < a2 )
    return 0;
  if ( (_DWORD)gBCacheMode != 1 )
  {
    for ( i = 0; i < 5; ++i )
    {
      if ( (unsigned int)dword_1800E2804[2 * i] >= v2 )
      {
        v7 = gBufferCache;
        CurrentProcessorNumber = RtlGetCurrentProcessorNumber();
        if ( *(_QWORD *)v7
          && (v9 = (union _SLIST_HEADER *)(*(_QWORD *)v7
                                         + 16 * ((int)i + 8LL * (CurrentProcessorNumber % *((_DWORD *)v7 + 2))))) != 0
          && (v10 = InterlockedPopEntrySList(v9), (v12 = v10) != 0) )
        {
          LODWORD(v10->Next) = i + 1;
          if ( dword_1800F9624 )
          {
            for ( j = 0; j < 4; ++j )
            {
              if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[j] == 98 )
                return v12 + 2;
            }
            if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
            {
              v25[0] = v2;
              v27 = &v21;
              v24 = 0;
              v29 = &v22;
              v23 = (SIZE_T)v10;
              v31 = &v23;
              v22 = 66;
              v33 = &v24;
              v35 = v25;
              v21 = 98;
              v28 = 1;
              v30 = 1;
              v32 = 8;
              v34 = 8;
              v36 = 8;
              McGenEventWrite_EtwEventWriteTransfer(
                (unsigned int)&RpcEtwGuid_Context,
                (unsigned int)RPCLogEvent,
                v11,
                6,
                (__int64)v26);
            }
          }
          return v12 + 2;
        }
        else
        {
          v14 = (unsigned int)dword_1800E2804[2 * i] + 32LL;
          v15 = AllocWrapper(v14);
          v17 = v15;
          if ( v15 )
          {
            *v15 = i + 1;
            if ( dword_1800F9624 )
            {
              for ( k = 0; k < 4; ++k )
              {
                if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[k] == 98 )
                  return (struct _SLIST_ENTRY *)(v17 + 8);
              }
              if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
              {
                v23 = v14;
                v27 = &v22;
                v24 = 0;
                v29 = &v21;
                v25[0] = v15;
                v31 = v25;
                v21 = 66;
                v33 = &v24;
                v35 = &v23;
                v22 = 98;
                v28 = 1;
                v30 = 1;
                v32 = 8;
                v34 = 8;
                v36 = 8;
                McGenEventWrite_EtwEventWriteTransfer(
                  (unsigned int)&RpcEtwGuid_Context,
                  (unsigned int)RPCLogEvent,
                  v16,
                  6,
                  (__int64)v26);
              }
            }
            return (struct _SLIST_ENTRY *)(v17 + 8);
          }
          else
          {
            LogEvent(0x62u, 0x58u, 0, 0, v14, v19, v20);
            return 0;
          }
        }
      }
    }
  }
  if ( v2 + 32 >= v2 )
  {
    if ( (_DWORD)gBCacheMode == 1 || !gBufferCache2 )
      v4 = AllocWrapper(v2 + 32);
    else
      v4 = BCache2::Alloc((BCache2 *)(unsigned int)gBCacheMode, v2 + 32);
    v5 = v4;
    if ( v4 )
    {
      *(_DWORD *)v4 = -1;
      v4[2] = v2 + 32;
      LogEvent(0x62u, 0x42u, v4, 0, v2, v19, v20);
      return (struct _SLIST_ENTRY *)(v5 + 4);
    }
    LogEvent(0x62u, 0x58u, 0, 0, v2, v19, v20);
  }
  return 0;
}

```

## disassembly

```asm
0x1800206a0  mov     r11, rsp
0x1800206a3  push    rbp
0x1800206a4  push    rdi
0x1800206a5  lea     rbp, [r11-5Fh]
0x1800206a9  sub     rsp, 0E8h
0x1800206b0  mov     rax, cs:__security_cookie
0x1800206b7  xor     rax, rsp
0x1800206ba  mov     [rbp+57h+var_20], rax
0x1800206be  lea     edi, [rdx+1Fh]
0x1800206c1  mov     eax, 0FFFFFFF0h
0x1800206c6  and     rdi, rax
0x1800206c9  cmp     rdi, rdx
0x1800206cc  jb      loc_1800209AD
0x1800206d2  mov     ecx, cs:?gBCacheMode@@3W4BCacheMode@@A; this
0x1800206d8  mov     [r11+8], rbx
0x1800206dc  mov     [r11+18h], rsi
0x1800206e0  mov     [r11-18h], r15
0x1800206e4  cmp     ecx, 1
0x1800206e7  jz      short loc_180020710
0x1800206e9  xor     ebx, ebx
0x1800206eb  lea     r15, __ImageBase
0x1800206f2  cmp     ebx, 5
0x1800206f5  jnb     short loc_180020710
0x1800206f7  movsxd  rsi, ebx
0x1800206fa  mov     eax, ds:rva dword_1800E2804[r15+rsi*8]
0x180020702  cmp     rax, rdi
0x180020705  jnb     short loc_18002070B
0x180020707  inc     ebx
0x180020709  jmp     short loc_1800206F2
0x18002070b  cmp     ebx, 0FFFFFFFFh
0x18002070e  jnz     short loc_18002078A
0x180020710  lea     rsi, [rdi+20h]
0x180020714  cmp     rsi, rdi
0x180020717  jb      loc_1800209D9
0x18002071d  cmp     ecx, 1
0x180020720  jnz     loc_180020814
0x180020726  mov     rcx, rsi; dwBytes
0x180020729  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18002072e  xor     r9d, r9d; void *
0x180020731  mov     [rsp+20h], rdi; unsigned __int64
0x180020736  mov     rbx, rax
0x180020739  mov     cl, 62h ; 'b'; unsigned __int8
0x18002073b  test    rax, rax
0x18002073e  jz      loc_1800209CF
0x180020744  mov     r8, rax; void *
0x180020747  mov     dword ptr [rax], 0FFFFFFFFh
0x18002074d  mov     dl, 42h ; 'B'; unsigned __int8
0x18002074f  mov     [rax+10h], rsi
0x180020753  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x180020758  lea     rax, [rbx+20h]
0x18002075c  mov     rsi, [rsp+0F0h+arg_10]
0x180020764  mov     rbx, [rsp+0F0h+arg_0]
0x18002076c  mov     r15, [rsp+0E0h]
0x180020774  mov     rcx, [rbp+57h+var_20]
0x180020778  xor     rcx, rsp; StackCookie
0x18002077b  call    __security_check_cookie
0x180020780  add     rsp, 0E8h
0x180020787  pop     rdi
0x180020788  pop     rbp
0x180020789  retn
0x18002078a  mov     [rsp+0F0h+arg_18], r14
0x180020792  mov     r14, cs:?gBufferCache@@3PEAVBCACHE@@EA; BCACHE * gBufferCache
0x180020799  call    cs:__imp_RtlGetCurrentProcessorNumber
0x18002079f  mov     r8, [r14]
0x1800207a2  test    r8, r8
0x1800207a5  jz      loc_1800208BE
0x1800207ab  xor     edx, edx
0x1800207ad  div     dword ptr [r14+8]
0x1800207b1  lea     rcx, [rsi+rdx*8]
0x1800207b5  shl     rcx, 4
0x1800207b9  add     rcx, r8; ListHead
0x1800207bc  jz      loc_1800208BE
0x1800207c2  call    cs:__imp_InterlockedPopEntrySList
0x1800207c8  mov     r14, rax
0x1800207cb  test    rax, rax
0x1800207ce  jz      loc_1800208BE
0x1800207d4  inc     ebx
0x1800207d6  mov     [rax], ebx
0x1800207d8  cmp     cs:dword_1800F9624, 0
0x1800207df  jz      short loc_180020803
0x1800207e1  xor     ecx, ecx
0x1800207e3  cmp     ecx, 4
0x1800207e6  jnb     short loc_1800207FA
0x1800207e8  movsxd  rax, ecx
0x1800207eb  cmp     byte ptr [rax+r15+0E1808h], 62h ; 'b'
0x1800207f4  jz      short loc_180020803
0x1800207f6  inc     ecx
0x1800207f8  jmp     short loc_1800207E3
0x1800207fa  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180020801  jnz     short loc_18002082F
0x180020803  lea     rax, [r14+20h]
0x180020807  mov     r14, [rsp+0F0h+arg_18]
0x18002080f  jmp     loc_18002075C
0x180020814  cmp     cs:?gBufferCache2@@3PEAVBCache2@@EA, 0; BCache2 * gBufferCache2
0x18002081c  jz      loc_180020726
0x180020822  mov     rdx, rsi; unsigned __int64
0x180020825  call    ?Alloc@BCache2@@QEAAPEAX_K@Z; BCache2::Alloc(unsigned __int64)
0x18002082a  jmp     loc_18002072E
0x18002082f  lea     rax, [rbp+57h+var_B0]
0x180020833  mov     [rbp+57h+var_90], rdi
0x180020837  mov     [rbp+57h+var_70], rax
0x18002083b  lea     rdx, RPCLogEvent
0x180020842  lea     rax, [rbp+57h+var_A8]
0x180020846  mov     [rbp+57h+var_98], 0
0x18002084e  mov     [rbp+57h+var_60], rax
0x180020852  lea     rcx, RpcEtwGuid_Context
0x180020859  lea     rax, [rbp+57h+var_A0]
0x18002085d  mov     [rbp+57h+var_A0], r14
0x180020861  mov     [rbp+57h+var_50], rax
0x180020865  mov     r9d, 6
0x18002086b  lea     rax, [rbp+57h+var_98]
0x18002086f  mov     [rbp+57h+var_A8], 42h ; 'B'
0x180020873  mov     [rbp+57h+var_40], rax
0x180020877  lea     rax, [rbp+57h+var_90]
0x18002087b  mov     [rbp+57h+var_30], rax
0x18002087f  lea     rax, [rbp+57h+var_80]
0x180020883  mov     [rsp+20h], rax
0x180020888  mov     [rbp+57h+var_B0], 62h ; 'b'
0x18002088c  mov     [rbp+57h+var_68], 1
0x180020894  mov     [rbp+57h+var_58], 1
0x18002089c  mov     [rbp+57h+var_48], 8
0x1800208a4  mov     [rbp+57h+var_38], 8
0x1800208ac  mov     [rbp+57h+var_28], 8
0x1800208b4  call    McGenEventWrite_EtwEventWriteTransfer
0x1800208b9  jmp     loc_180020803
0x1800208be  mov     esi, ds:rva dword_1800E2804[r15+rsi*8]
0x1800208c6  add     rsi, 20h ; ' '
0x1800208ca  mov     rcx, rsi; dwBytes
0x1800208cd  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800208d2  mov     rdi, rax
0x1800208d5  test    rax, rax
0x1800208d8  jz      loc_1800209B4
0x1800208de  inc     ebx
0x1800208e0  mov     [rax], ebx
0x1800208e2  cmp     cs:dword_1800F9624, 0
0x1800208e9  jz      short loc_18002090D
0x1800208eb  xor     ecx, ecx
0x1800208ed  cmp     ecx, 4
0x1800208f0  jnb     short loc_180020904
0x1800208f2  movsxd  rax, ecx
0x1800208f5  cmp     byte ptr [rax+r15+0E1808h], 62h ; 'b'
0x1800208fe  jz      short loc_18002090D
0x180020900  inc     ecx
0x180020902  jmp     short loc_1800208ED
0x180020904  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18002090b  jnz     short loc_18002091E
0x18002090d  mov     r14, [rsp+0F0h+arg_18]
0x180020915  lea     rax, [rdi+20h]
0x180020919  jmp     loc_18002075C
0x18002091e  lea     rax, [rbp+57h+var_A8]
0x180020922  mov     [rbp+57h+var_A0], rsi
0x180020926  mov     [rbp+57h+var_70], rax
0x18002092a  lea     rdx, RPCLogEvent
0x180020931  lea     rax, [rbp+57h+var_B0]
0x180020935  mov     [rbp+57h+var_98], 0
0x18002093d  mov     [rbp+57h+var_60], rax
0x180020941  lea     rcx, RpcEtwGuid_Context
0x180020948  lea     rax, [rbp+57h+var_90]
0x18002094c  mov     [rbp+57h+var_90], rdi
0x180020950  mov     [rbp+57h+var_50], rax
0x180020954  mov     r9d, 6
0x18002095a  lea     rax, [rbp+57h+var_98]
0x18002095e  mov     [rbp+57h+var_B0], 42h ; 'B'
0x180020962  mov     [rbp+57h+var_40], rax
0x180020966  lea     rax, [rbp+57h+var_A0]
0x18002096a  mov     [rbp+57h+var_30], rax
0x18002096e  lea     rax, [rbp+57h+var_80]
0x180020972  mov     [rsp+20h], rax
0x180020977  mov     [rbp+57h+var_A8], 62h ; 'b'
0x18002097b  mov     [rbp+57h+var_68], 1
0x180020983  mov     [rbp+57h+var_58], 1
0x18002098b  mov     [rbp+57h+var_48], 8
0x180020993  mov     [rbp+57h+var_38], 8
0x18002099b  mov     [rbp+57h+var_28], 8
0x1800209a3  call    McGenEventWrite_EtwEventWriteTransfer
0x1800209a8  jmp     loc_18002090D
0x1800209ad  xor     eax, eax
0x1800209af  jmp     loc_180020774
0x1800209b4  xor     r9d, r9d; void *
0x1800209b7  mov     [rsp+20h], rsi; unsigned __int64
0x1800209bc  xor     r8d, r8d; void *
0x1800209bf  mov     dl, 58h ; 'X'; unsigned __int8
0x1800209c1  mov     cl, 62h ; 'b'; unsigned __int8
0x1800209c3  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x1800209c8  xor     eax, eax
0x1800209ca  jmp     loc_180020807
0x1800209cf  xor     r8d, r8d; void *
0x1800209d2  mov     dl, 58h ; 'X'; unsigned __int8
0x1800209d4  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x1800209d9  xor     eax, eax
0x1800209db  jmp     loc_18002075C
```
