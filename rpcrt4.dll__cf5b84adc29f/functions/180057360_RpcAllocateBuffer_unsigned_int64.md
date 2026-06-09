# RpcAllocateBuffer(unsigned __int64)

- ea: `0x180057360`
- end: `0x1800576ad`
- name: `?RpcAllocateBuffer@@YAPEAX_K@Z`
- size: `845`
- prototype: `struct _SLIST_ENTRY *__fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001fdb4`
- `0x180022e80`
- `0x180022fb8`
- `0x180023020`
- `0x180057360`
- `0x1800ceda0`

## import_xrefs

- `ntdll!RtlGetCurrentProcessorNumber` at `0x180057461`
- `ntdll!RtlGetCurrentProcessorNumber` at `0x180057461`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180057490`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180057490`

## pseudocode

```c
struct _SLIST_ENTRY *__fastcall RpcAllocateBuffer(unsigned __int64 a1)
{
  unsigned __int64 v1; // rdi
  __int64 v2; // r14
  unsigned int i; // ebx
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  struct BCACHE *v7; // r15
  ULONG CurrentProcessorNumber; // eax
  union _SLIST_HEADER *v9; // rcx
  PSLIST_ENTRY v10; // rax
  int v11; // r8d
  PSLIST_ENTRY v12; // r15
  unsigned int j; // ecx
  SIZE_T v14; // rsi
  _DWORD *v15; // rax
  int v16; // r8d
  _DWORD *v17; // rdi
  unsigned int k; // ecx
  int v19; // [rsp+30h] [rbp-81h]
  int v20; // [rsp+38h] [rbp-79h]
  char v21; // [rsp+48h] [rbp-69h] BYREF
  char v22; // [rsp+50h] [rbp-61h] BYREF
  SIZE_T v23; // [rsp+58h] [rbp-59h] BYREF
  __int64 v24; // [rsp+60h] [rbp-51h] BYREF
  _QWORD v25[2]; // [rsp+68h] [rbp-49h] BYREF
  _BYTE v26[16]; // [rsp+78h] [rbp-39h] BYREF
  char *v27; // [rsp+88h] [rbp-29h]
  __int64 v28; // [rsp+90h] [rbp-21h]
  char *v29; // [rsp+98h] [rbp-19h]
  __int64 v30; // [rsp+A0h] [rbp-11h]
  SIZE_T *v31; // [rsp+A8h] [rbp-9h]
  __int64 v32; // [rsp+B0h] [rbp-1h]
  __int64 *v33; // [rsp+B8h] [rbp+7h]
  __int64 v34; // [rsp+C0h] [rbp+Fh]
  SIZE_T *v35; // [rsp+C8h] [rbp+17h]
  __int64 v36; // [rsp+D0h] [rbp+1Fh]

  v1 = ((_DWORD)a1 + 31) & 0xFFFFFFF0;
  v2 = 0;
  if ( v1 < a1 )
    return 0;
  if ( (_DWORD)gBCacheMode != 1 )
  {
    for ( i = 0; i < 5; ++i )
    {
      if ( (unsigned int)dword_1800E743C[2 * i] >= v1 )
      {
        v7 = gBufferCache;
        CurrentProcessorNumber = RtlGetCurrentProcessorNumber();
        if ( *(_QWORD *)v7
          && (v9 = (union _SLIST_HEADER *)(*(_QWORD *)v7
                                         + 16 * ((int)i + 8LL * (CurrentProcessorNumber % *((_DWORD *)v7 + 2))))) != 0
          && (v10 = InterlockedPopEntrySList(v9), (v12 = v10) != 0) )
        {
          LODWORD(v10->Next) = i + 1;
          if ( dword_1800FE624 )
          {
            for ( j = 0; j < 4; ++j )
            {
              if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[j] == 98 )
                return v12 + 2;
            }
            if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
            {
              v25[0] = v1;
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
          v14 = (unsigned int)dword_1800E743C[2 * i] + 32LL;
          v15 = AllocWrapper(v14);
          v17 = v15;
          if ( v15 )
          {
            *v15 = i + 1;
            if ( dword_1800FE624 )
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
  if ( v1 + 32 >= v1 )
  {
    if ( (_DWORD)gBCacheMode == 1 || !gBufferCache2 )
      v4 = AllocWrapper(v1 + 32);
    else
      v4 = BCache2::Alloc((BCache2 *)(unsigned int)gBCacheMode, v1 + 32);
    v5 = v4;
    if ( v4 )
    {
      *(_DWORD *)v4 = -1;
      v4[2] = v1 + 32;
      LogEvent(0x62u, 0x42u, v4, 0, v1, v19, v20);
      return (struct _SLIST_ENTRY *)(v5 + 4);
    }
    else
    {
      LogEvent(0x62u, 0x58u, 0, 0, v1, v19, v20);
    }
  }
  return (struct _SLIST_ENTRY *)v2;
}

```

## disassembly

```asm
0x180057360  mov     r11, rsp
0x180057363  push    rbp
0x180057364  push    rdi
0x180057365  push    r14
0x180057367  lea     rbp, [r11-5Fh]
0x18005736b  sub     rsp, 0F0h
0x180057372  mov     rax, cs:__security_cookie
0x180057379  xor     rax, rsp
0x18005737c  mov     [rbp+57h+var_30], rax
0x180057380  lea     edi, [rcx+1Fh]
0x180057383  mov     eax, 0FFFFFFF0h
0x180057388  and     rdi, rax
0x18005738b  xor     r14d, r14d
0x18005738e  cmp     rdi, rcx
0x180057391  jb      loc_18005767A
0x180057397  mov     ecx, cs:?gBCacheMode@@3W4BCacheMode@@A; this
0x18005739d  mov     [r11+10h], rbx
0x1800573a1  mov     [r11+18h], rsi
0x1800573a5  mov     [r11-20h], r12
0x1800573a9  cmp     ecx, 1
0x1800573ac  jz      short loc_1800573D6
0x1800573ae  mov     ebx, r14d
0x1800573b1  lea     r12, __ImageBase
0x1800573b8  cmp     ebx, 5
0x1800573bb  jnb     short loc_1800573D6
0x1800573bd  movsxd  rsi, ebx
0x1800573c0  mov     eax, ds:rva dword_1800E743C[r12+rsi*8]
0x1800573c8  cmp     rax, rdi
0x1800573cb  jnb     short loc_1800573D1
0x1800573cd  inc     ebx
0x1800573cf  jmp     short loc_1800573B8
0x1800573d1  cmp     ebx, 0FFFFFFFFh
0x1800573d4  jnz     short loc_180057452
0x1800573d6  lea     rsi, [rdi+20h]
0x1800573da  cmp     rsi, rdi
0x1800573dd  jb      short loc_18005741E
0x1800573df  cmp     ecx, 1
0x1800573e2  jnz     loc_1800574E9
0x1800573e8  mov     rcx, rsi; dwBytes
0x1800573eb  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800573f0  xor     r9d, r9d; void *
0x1800573f3  mov     [rsp+20h], rdi; unsigned __int64
0x1800573f8  mov     rbx, rax
0x1800573fb  mov     cl, 62h ; 'b'; unsigned __int8
0x1800573fd  test    rax, rax
0x180057400  jz      loc_18005769E
0x180057406  mov     r8, rax; void *
0x180057409  mov     dword ptr [rax], 0FFFFFFFFh
0x18005740f  mov     dl, 42h ; 'B'; unsigned __int8
0x180057411  mov     [rax+10h], rsi
0x180057415  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x18005741a  lea     r14, [rbx+20h]
0x18005741e  mov     rax, r14
0x180057421  mov     rsi, [rsp+100h+arg_10]
0x180057429  mov     rbx, [rsp+100h+arg_8]
0x180057431  mov     r12, [rsp+0E8h]
0x180057439  mov     rcx, [rbp+57h+var_30]
0x18005743d  xor     rcx, rsp; StackCookie
0x180057440  call    __security_check_cookie
0x180057445  add     rsp, 0F0h
0x18005744c  pop     r14
0x18005744e  pop     rdi
0x18005744f  pop     rbp
0x180057450  retn
0x180057452  mov     [rsp+100h+var_20], r15
0x18005745a  mov     r15, cs:?gBufferCache@@3PEAVBCACHE@@EA; BCACHE * gBufferCache
0x180057461  call    cs:__imp_RtlGetCurrentProcessorNumber
0x180057468  nop     dword ptr [rax+rax+00h]
0x18005746d  mov     r8, [r15]
0x180057470  test    r8, r8
0x180057473  jz      loc_18005758E
0x180057479  xor     edx, edx
0x18005747b  div     dword ptr [r15+8]
0x18005747f  lea     rcx, [rsi+rdx*8]
0x180057483  shl     rcx, 4
0x180057487  add     rcx, r8; ListHead
0x18005748a  jz      loc_18005758E
0x180057490  call    cs:__imp_InterlockedPopEntrySList
0x180057497  nop     dword ptr [rax+rax+00h]
0x18005749c  mov     r15, rax
0x18005749f  test    rax, rax
0x1800574a2  jz      loc_18005758E
0x1800574a8  inc     ebx
0x1800574aa  mov     [rax], ebx
0x1800574ac  cmp     cs:dword_1800FE624, r14d
0x1800574b3  jz      short loc_1800574D8
0x1800574b5  mov     ecx, r14d
0x1800574b8  cmp     ecx, 4
0x1800574bb  jnb     short loc_1800574CF
0x1800574bd  movsxd  rax, ecx
0x1800574c0  cmp     byte ptr [rax+r12+0E66D8h], 62h ; 'b'
0x1800574c9  jz      short loc_1800574D8
0x1800574cb  inc     ecx
0x1800574cd  jmp     short loc_1800574B8
0x1800574cf  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x1800574d6  jnz     short loc_180057503
0x1800574d8  lea     rax, [r15+20h]
0x1800574dc  mov     r15, [rsp+100h+var_20]
0x1800574e4  jmp     loc_180057421
0x1800574e9  cmp     cs:?gBufferCache2@@3PEAVBCache2@@EA, r14; BCache2 * gBufferCache2
0x1800574f0  jz      loc_1800573E8
0x1800574f6  mov     rdx, rsi; unsigned __int64
0x1800574f9  call    ?Alloc@BCache2@@QEAAPEAX_K@Z; BCache2::Alloc(unsigned __int64)
0x1800574fe  jmp     loc_1800573F0
0x180057503  lea     rax, [rbp+57h+var_C0]
0x180057507  mov     [rbp+57h+var_A0], rdi
0x18005750b  mov     [rbp+57h+var_80], rax
0x18005750f  lea     rdx, RPCLogEvent
0x180057516  lea     rax, [rbp+57h+var_B8]
0x18005751a  mov     [rbp+57h+var_A8], r14
0x18005751e  mov     [rbp+57h+var_70], rax
0x180057522  lea     rcx, RpcEtwGuid_Context
0x180057529  lea     rax, [rbp+57h+var_B0]
0x18005752d  mov     [rbp+57h+var_B0], r15
0x180057531  mov     [rbp+57h+var_60], rax
0x180057535  mov     r9d, 6
0x18005753b  lea     rax, [rbp+57h+var_A8]
0x18005753f  mov     [rbp+57h+var_B8], 42h ; 'B'
0x180057543  mov     [rbp+57h+var_50], rax
0x180057547  lea     rax, [rbp+57h+var_A0]
0x18005754b  mov     [rbp+57h+var_40], rax
0x18005754f  lea     rax, [rbp+57h+var_90]
0x180057553  mov     [rsp+20h], rax
0x180057558  mov     [rbp+57h+var_C0], 62h ; 'b'
0x18005755c  mov     [rbp+57h+var_78], 1
0x180057564  mov     [rbp+57h+var_68], 1
0x18005756c  mov     [rbp+57h+var_58], 8
0x180057574  mov     [rbp+57h+var_48], 8
0x18005757c  mov     [rbp+57h+var_38], 8
0x180057584  call    McGenEventWrite_EtwEventWriteTransfer
0x180057589  jmp     loc_1800574D8
0x18005758e  mov     esi, ds:rva dword_1800E743C[r12+rsi*8]
0x180057596  add     rsi, 20h ; ' '
0x18005759a  mov     rcx, rsi; dwBytes
0x18005759d  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800575a2  mov     rdi, rax
0x1800575a5  test    rax, rax
0x1800575a8  jz      loc_180057682
0x1800575ae  inc     ebx
0x1800575b0  mov     [rax], ebx
0x1800575b2  cmp     cs:dword_1800FE624, r14d
0x1800575b9  jz      short loc_1800575DE
0x1800575bb  mov     ecx, r14d
0x1800575be  cmp     ecx, 4
0x1800575c1  jnb     short loc_1800575D5
0x1800575c3  movsxd  rax, ecx
0x1800575c6  cmp     byte ptr [rax+r12+0E66D8h], 62h ; 'b'
0x1800575cf  jz      short loc_1800575DE
0x1800575d1  inc     ecx
0x1800575d3  jmp     short loc_1800575BE
0x1800575d5  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x1800575dc  jnz     short loc_1800575EF
0x1800575de  mov     r15, [rsp+100h+var_20]
0x1800575e6  lea     rax, [rdi+20h]
0x1800575ea  jmp     loc_180057421
0x1800575ef  lea     rax, [rbp+57h+var_B8]
0x1800575f3  mov     [rbp+57h+var_B0], rsi
0x1800575f7  mov     [rbp+57h+var_80], rax
0x1800575fb  lea     rdx, RPCLogEvent
0x180057602  lea     rax, [rbp+57h+var_C0]
0x180057606  mov     [rbp+57h+var_A8], r14
0x18005760a  mov     [rbp+57h+var_70], rax
0x18005760e  lea     rcx, RpcEtwGuid_Context
0x180057615  lea     rax, [rbp+57h+var_A0]
0x180057619  mov     [rbp+57h+var_A0], rdi
0x18005761d  mov     [rbp+57h+var_60], rax
0x180057621  mov     r9d, 6
0x180057627  lea     rax, [rbp+57h+var_A8]
0x18005762b  mov     [rbp+57h+var_C0], 42h ; 'B'
0x18005762f  mov     [rbp+57h+var_50], rax
0x180057633  lea     rax, [rbp+57h+var_B0]
0x180057637  mov     [rbp+57h+var_40], rax
0x18005763b  lea     rax, [rbp+57h+var_90]
0x18005763f  mov     [rsp+20h], rax
0x180057644  mov     [rbp+57h+var_B8], 62h ; 'b'
0x180057648  mov     [rbp+57h+var_78], 1
0x180057650  mov     [rbp+57h+var_68], 1
0x180057658  mov     [rbp+57h+var_58], 8
0x180057660  mov     [rbp+57h+var_48], 8
0x180057668  mov     [rbp+57h+var_38], 8
0x180057670  call    McGenEventWrite_EtwEventWriteTransfer
0x180057675  jmp     loc_1800575DE
0x18005767a  mov     rax, r14
0x18005767d  jmp     loc_180057439
0x180057682  xor     r9d, r9d; void *
0x180057685  mov     [rsp+20h], rsi; unsigned __int64
0x18005768a  xor     r8d, r8d; void *
0x18005768d  mov     dl, 58h ; 'X'; unsigned __int8
0x18005768f  mov     cl, 62h ; 'b'; unsigned __int8
0x180057691  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x180057696  mov     rax, r14
0x180057699  jmp     loc_1800574DC
0x18005769e  xor     r8d, r8d; void *
0x1800576a1  mov     dl, 58h ; 'X'; unsigned __int8
0x1800576a3  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x1800576a8  jmp     loc_18005741E
```
