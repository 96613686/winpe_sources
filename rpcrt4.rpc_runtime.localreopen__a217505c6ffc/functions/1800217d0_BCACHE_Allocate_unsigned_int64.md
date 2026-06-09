# BCACHE::Allocate(unsigned __int64)

- ea: `0x1800217d0`
- end: `0x180021b1d`
- name: `?Allocate@BCACHE@@QEAAPEAX_K@Z`
- size: `845`
- prototype: `struct _SLIST_ENTRY *__fastcall(BCACHE *this, unsigned __int64)`
- caller_count: `42`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009884`
- `0x18001ee10`
- `0x18001fca0`
- `0x18001fe90`
- `0x180020140`
- `0x180020a60`
- `0x180023170`
- `0x180027870`
- `0x18005a5e0`
- `0x18005feb0`
- `0x1800618ac`
- `0x180063880`
- `0x18006aa1c`
- `0x18006baf0`
- `0x18006eaec`
- `0x18006fc20`
- `0x180070458`
- `0x180074de0`
- `0x180078dac`
- `0x18007b310`
- `0x18007d010`
- `0x18007f3c0`
- `0x180080a60`
- `0x180080d10`
- `0x180081080`
- `0x1800906d0`
- `0x180091110`
- `0x180091320`
- `0x180099b7c`
- `0x18009a250`
- `0x1800a1c34`
- `0x1800a1d08`
- `0x1800a39d0`
- `0x1800a3c70`
- `0x1800ab6fc`
- `0x1800abfe0`
- `0x1800bca58`
- `0x1800bd840`
- `0x1800be770`
- `0x1800beca8`
- `0x1800d1df0`
- `0x1800d2ad0`

## callees

- `0x18001fdb4`
- `0x1800217d0`
- `0x180022e80`
- `0x180022fb8`
- `0x180023020`
- `0x1800ceda0`

## import_xrefs

- `ntdll!RtlGetCurrentProcessorNumber` at `0x1800218ca`
- `ntdll!RtlGetCurrentProcessorNumber` at `0x1800218ca`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800218f9`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800218f9`

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
      if ( (unsigned int)dword_1800E743C[2 * i] >= v2 )
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
0x1800217d0  mov     r11, rsp
0x1800217d3  push    rbp
0x1800217d4  push    rdi
0x1800217d5  lea     rbp, [r11-5Fh]
0x1800217d9  sub     rsp, 0E8h
0x1800217e0  mov     rax, cs:__security_cookie
0x1800217e7  xor     rax, rsp
0x1800217ea  mov     [rbp+57h+var_20], rax
0x1800217ee  lea     edi, [rdx+1Fh]
0x1800217f1  mov     eax, 0FFFFFFF0h
0x1800217f6  and     rdi, rax
0x1800217f9  cmp     rdi, rdx
0x1800217fc  jb      loc_180021AEA
0x180021802  mov     ecx, cs:?gBCacheMode@@3W4BCacheMode@@A; this
0x180021808  mov     [r11+8], rbx
0x18002180c  mov     [r11+18h], rsi
0x180021810  mov     [r11-18h], r15
0x180021814  cmp     ecx, 1
0x180021817  jz      short loc_180021840
0x180021819  xor     ebx, ebx
0x18002181b  lea     r15, __ImageBase
0x180021822  cmp     ebx, 5
0x180021825  jnb     short loc_180021840
0x180021827  movsxd  rsi, ebx
0x18002182a  mov     eax, ds:rva dword_1800E743C[r15+rsi*8]
0x180021832  cmp     rax, rdi
0x180021835  jnb     short loc_18002183B
0x180021837  inc     ebx
0x180021839  jmp     short loc_180021822
0x18002183b  cmp     ebx, 0FFFFFFFFh
0x18002183e  jnz     short loc_1800218BB
0x180021840  lea     rsi, [rdi+20h]
0x180021844  cmp     rsi, rdi
0x180021847  jb      loc_180021B16
0x18002184d  cmp     ecx, 1
0x180021850  jnz     loc_180021951
0x180021856  mov     rcx, rsi; dwBytes
0x180021859  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18002185e  xor     r9d, r9d; void *
0x180021861  mov     [rsp+20h], rdi; unsigned __int64
0x180021866  mov     rbx, rax
0x180021869  mov     cl, 62h ; 'b'; unsigned __int8
0x18002186b  test    rax, rax
0x18002186e  jz      loc_180021B0C
0x180021874  mov     r8, rax; void *
0x180021877  mov     dword ptr [rax], 0FFFFFFFFh
0x18002187d  mov     dl, 42h ; 'B'; unsigned __int8
0x18002187f  mov     [rax+10h], rsi
0x180021883  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x180021888  lea     rax, [rbx+20h]
0x18002188c  mov     rsi, [rsp+0F0h+arg_10]
0x180021894  mov     rbx, [rsp+0F0h+arg_0]
0x18002189c  mov     r15, [rsp+0E0h]
0x1800218a4  mov     rcx, [rbp+57h+var_20]
0x1800218a8  xor     rcx, rsp; StackCookie
0x1800218ab  call    __security_check_cookie
0x1800218b0  add     rsp, 0E8h
0x1800218b7  pop     rdi
0x1800218b8  pop     rbp
0x1800218b9  retn
0x1800218bb  mov     [rsp+0F0h+arg_18], r14
0x1800218c3  mov     r14, cs:?gBufferCache@@3PEAVBCACHE@@EA; BCACHE * gBufferCache
0x1800218ca  call    cs:__imp_RtlGetCurrentProcessorNumber
0x1800218d1  nop     dword ptr [rax+rax+00h]
0x1800218d6  mov     r8, [r14]
0x1800218d9  test    r8, r8
0x1800218dc  jz      loc_1800219FB
0x1800218e2  xor     edx, edx
0x1800218e4  div     dword ptr [r14+8]
0x1800218e8  lea     rcx, [rsi+rdx*8]
0x1800218ec  shl     rcx, 4
0x1800218f0  add     rcx, r8; ListHead
0x1800218f3  jz      loc_1800219FB
0x1800218f9  call    cs:__imp_InterlockedPopEntrySList
0x180021900  nop     dword ptr [rax+rax+00h]
0x180021905  mov     r14, rax
0x180021908  test    rax, rax
0x18002190b  jz      loc_1800219FB
0x180021911  inc     ebx
0x180021913  mov     [rax], ebx
0x180021915  cmp     cs:dword_1800FE624, 0
0x18002191c  jz      short loc_180021940
0x18002191e  xor     ecx, ecx
0x180021920  cmp     ecx, 4
0x180021923  jnb     short loc_180021937
0x180021925  movsxd  rax, ecx
0x180021928  cmp     byte ptr [rax+r15+0E66D8h], 62h ; 'b'
0x180021931  jz      short loc_180021940
0x180021933  inc     ecx
0x180021935  jmp     short loc_180021920
0x180021937  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18002193e  jnz     short loc_18002196C
0x180021940  lea     rax, [r14+20h]
0x180021944  mov     r14, [rsp+0F0h+arg_18]
0x18002194c  jmp     loc_18002188C
0x180021951  cmp     cs:?gBufferCache2@@3PEAVBCache2@@EA, 0; BCache2 * gBufferCache2
0x180021959  jz      loc_180021856
0x18002195f  mov     rdx, rsi; unsigned __int64
0x180021962  call    ?Alloc@BCache2@@QEAAPEAX_K@Z; BCache2::Alloc(unsigned __int64)
0x180021967  jmp     loc_18002185E
0x18002196c  lea     rax, [rbp+57h+var_B0]
0x180021970  mov     [rbp+57h+var_90], rdi
0x180021974  mov     [rbp+57h+var_70], rax
0x180021978  lea     rdx, RPCLogEvent
0x18002197f  lea     rax, [rbp+57h+var_A8]
0x180021983  mov     [rbp+57h+var_98], 0
0x18002198b  mov     [rbp+57h+var_60], rax
0x18002198f  lea     rcx, RpcEtwGuid_Context
0x180021996  lea     rax, [rbp+57h+var_A0]
0x18002199a  mov     [rbp+57h+var_A0], r14
0x18002199e  mov     [rbp+57h+var_50], rax
0x1800219a2  mov     r9d, 6
0x1800219a8  lea     rax, [rbp+57h+var_98]
0x1800219ac  mov     [rbp+57h+var_A8], 42h ; 'B'
0x1800219b0  mov     [rbp+57h+var_40], rax
0x1800219b4  lea     rax, [rbp+57h+var_90]
0x1800219b8  mov     [rbp+57h+var_30], rax
0x1800219bc  lea     rax, [rbp+57h+var_80]
0x1800219c0  mov     [rsp+20h], rax
0x1800219c5  mov     [rbp+57h+var_B0], 62h ; 'b'
0x1800219c9  mov     [rbp+57h+var_68], 1
0x1800219d1  mov     [rbp+57h+var_58], 1
0x1800219d9  mov     [rbp+57h+var_48], 8
0x1800219e1  mov     [rbp+57h+var_38], 8
0x1800219e9  mov     [rbp+57h+var_28], 8
0x1800219f1  call    McGenEventWrite_EtwEventWriteTransfer
0x1800219f6  jmp     loc_180021940
0x1800219fb  mov     esi, ds:rva dword_1800E743C[r15+rsi*8]
0x180021a03  add     rsi, 20h ; ' '
0x180021a07  mov     rcx, rsi; dwBytes
0x180021a0a  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180021a0f  mov     rdi, rax
0x180021a12  test    rax, rax
0x180021a15  jz      loc_180021AF1
0x180021a1b  inc     ebx
0x180021a1d  mov     [rax], ebx
0x180021a1f  cmp     cs:dword_1800FE624, 0
0x180021a26  jz      short loc_180021A4A
0x180021a28  xor     ecx, ecx
0x180021a2a  cmp     ecx, 4
0x180021a2d  jnb     short loc_180021A41
0x180021a2f  movsxd  rax, ecx
0x180021a32  cmp     byte ptr [rax+r15+0E66D8h], 62h ; 'b'
0x180021a3b  jz      short loc_180021A4A
0x180021a3d  inc     ecx
0x180021a3f  jmp     short loc_180021A2A
0x180021a41  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180021a48  jnz     short loc_180021A5B
0x180021a4a  mov     r14, [rsp+0F0h+arg_18]
0x180021a52  lea     rax, [rdi+20h]
0x180021a56  jmp     loc_18002188C
0x180021a5b  lea     rax, [rbp+57h+var_A8]
0x180021a5f  mov     [rbp+57h+var_A0], rsi
0x180021a63  mov     [rbp+57h+var_70], rax
0x180021a67  lea     rdx, RPCLogEvent
0x180021a6e  lea     rax, [rbp+57h+var_B0]
0x180021a72  mov     [rbp+57h+var_98], 0
0x180021a7a  mov     [rbp+57h+var_60], rax
0x180021a7e  lea     rcx, RpcEtwGuid_Context
0x180021a85  lea     rax, [rbp+57h+var_90]
0x180021a89  mov     [rbp+57h+var_90], rdi
0x180021a8d  mov     [rbp+57h+var_50], rax
0x180021a91  mov     r9d, 6
0x180021a97  lea     rax, [rbp+57h+var_98]
0x180021a9b  mov     [rbp+57h+var_B0], 42h ; 'B'
0x180021a9f  mov     [rbp+57h+var_40], rax
0x180021aa3  lea     rax, [rbp+57h+var_A0]
0x180021aa7  mov     [rbp+57h+var_30], rax
0x180021aab  lea     rax, [rbp+57h+var_80]
0x180021aaf  mov     [rsp+20h], rax
0x180021ab4  mov     [rbp+57h+var_A8], 62h ; 'b'
0x180021ab8  mov     [rbp+57h+var_68], 1
0x180021ac0  mov     [rbp+57h+var_58], 1
0x180021ac8  mov     [rbp+57h+var_48], 8
0x180021ad0  mov     [rbp+57h+var_38], 8
0x180021ad8  mov     [rbp+57h+var_28], 8
0x180021ae0  call    McGenEventWrite_EtwEventWriteTransfer
0x180021ae5  jmp     loc_180021A4A
0x180021aea  xor     eax, eax
0x180021aec  jmp     loc_1800218A4
0x180021af1  xor     r9d, r9d; void *
0x180021af4  mov     [rsp+20h], rsi; unsigned __int64
0x180021af9  xor     r8d, r8d; void *
0x180021afc  mov     dl, 58h ; 'X'; unsigned __int8
0x180021afe  mov     cl, 62h ; 'b'; unsigned __int8
0x180021b00  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x180021b05  xor     eax, eax
0x180021b07  jmp     loc_180021944
0x180021b0c  xor     r8d, r8d; void *
0x180021b0f  mov     dl, 58h ; 'X'; unsigned __int8
0x180021b11  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x180021b16  xor     eax, eax
0x180021b18  jmp     loc_18002188C
```
