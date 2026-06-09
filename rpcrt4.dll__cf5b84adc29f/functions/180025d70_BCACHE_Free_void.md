# BCACHE::Free(void *)

- ea: `0x180025d70`
- end: `0x18002606f`
- name: `?Free@BCACHE@@QEAAXPEAX@Z`
- size: `767`
- prototype: `void __fastcall(BCACHE *this, int *, int)`
- caller_count: `27`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001050`
- `0x180002bc8`
- `0x180014550`
- `0x180014e60`
- `0x180017580`
- `0x1800178a0`
- `0x180019e3c`
- `0x18001b4d0`
- `0x18001d170`
- `0x18001ee10`
- `0x180020140`
- `0x180023170`
- `0x180023b80`
- `0x1800263a0`
- `0x180026500`
- `0x180026800`
- `0x180026e80`
- `0x18002bf80`
- `0x180032b98`
- `0x180048580`
- `0x180048860`
- `0x180049310`
- `0x180073f80`
- `0x180082b50`
- `0x18008a470`
- `0x1800d2ad0`
- `0x1800d60c0`

## callees

- `0x180022fb8`
- `0x180023a40`
- `0x180025d70`
- `0x18008e4c0`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlGetCurrentProcessorNumber` at `0x180025dfd`
- `ntdll!RtlGetCurrentProcessorNumber` at `0x180025dfd`
- `ntdll!DbgPrint` at `0x18002602e`
- `ntdll!DbgPrint` at `0x18002604a`
- `ntdll!DbgPrint` at `0x18002602e`
- `ntdll!DbgPrint` at `0x18002604a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025f59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025f59`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180025e2e`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180025e2e`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180025e51`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180025e51`

## string_xrefs

- `0x180026027`: `RPC: BCache corruption detected at 0x%p\n`
- `0x180026043`: `RPC: BCache corruption detected at 0x%p\n`

## pseudocode

```c
void __fastcall BCACHE::Free(BCACHE *this, int *a2, int a3)
{
  __int64 v3; // rax
  struct _SLIST_ENTRY *v4; // rdi
  struct BCACHE *v5; // rsi
  int v6; // ebx
  __int64 v7; // r14
  unsigned int i; // eax
  ULONG CurrentProcessorNumber; // eax
  __int64 v10; // r8
  union _SLIST_HEADER *v11; // rbx
  unsigned int j; // ecx
  char v13; // [rsp+30h] [rbp-69h] BYREF
  char v14; // [rsp+38h] [rbp-61h] BYREF
  int *v15; // [rsp+40h] [rbp-59h] BYREF
  HANDLE v16; // [rsp+48h] [rbp-51h] BYREF
  _QWORD v17[2]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v18[16]; // [rsp+60h] [rbp-39h] BYREF
  char *v19; // [rsp+70h] [rbp-29h]
  __int64 v20; // [rsp+78h] [rbp-21h]
  char *v21; // [rsp+80h] [rbp-19h]
  __int64 v22; // [rsp+88h] [rbp-11h]
  int **v23; // [rsp+90h] [rbp-9h]
  __int64 v24; // [rsp+98h] [rbp-1h]
  HANDLE *v25; // [rsp+A0h] [rbp+7h]
  __int64 v26; // [rsp+A8h] [rbp+Fh]
  int **v27; // [rsp+B0h] [rbp+17h]
  __int64 v28; // [rsp+B8h] [rbp+1Fh]

  v3 = *(a2 - 8);
  v4 = (struct _SLIST_ENTRY *)(a2 - 8);
  v5 = gBufferCache;
  v6 = v3 - 1;
  v7 = v3 - 1;
  if ( dword_1800FE624 )
  {
    for ( i = 0; i < 4; ++i )
    {
      this = (BCACHE *)(int)i;
      if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 98 )
        goto LABEL_8;
    }
    if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
    {
      v17[0] = v7;
      v19 = &v13;
      v16 = 0;
      v21 = &v14;
      v15 = a2 - 8;
      v23 = &v15;
      v14 = 98;
      v25 = &v16;
      v27 = (int **)v17;
      v13 = 98;
      v20 = 1;
      v22 = 1;
      v24 = 8;
      v26 = 8;
      v28 = 8;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&RpcEtwGuid_Context,
        (unsigned int)RPCLogEvent,
        a3,
        6,
        (__int64)v18);
    }
  }
LABEL_8:
  if ( v6 < 0 )
  {
    if ( v6 != -2 )
    {
      DbgPrint("RPC: BCache corruption detected at 0x%p\n", v4);
      __debugbreak();
    }
    if ( (_DWORD)gBCacheMode == 1 || !gBufferCache2 )
      FreeWrapper(v4);
    else
      BCache2::Free(this, v4);
  }
  else
  {
    if ( v6 >= 5 )
    {
      DbgPrint("RPC: BCache corruption detected at 0x%p\n", v4);
      __debugbreak();
    }
    CurrentProcessorNumber = RtlGetCurrentProcessorNumber();
    v10 = *(_QWORD *)v5;
    if ( *(_QWORD *)v5
      && (v11 = (union _SLIST_HEADER *)(v10 + 16 * (v7 + 8LL * (CurrentProcessorNumber % *((_DWORD *)v5 + 2))))) != 0
      && (unsigned int)QueryDepthSList(v11) <= *((_DWORD *)&gCacheHints + 2 * v7) )
    {
      InterlockedPushEntrySList(v11, v4);
    }
    else
    {
      if ( dword_1800FE624 )
      {
        for ( j = 0; j < 4; ++j )
        {
          if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[j] == 72 )
            goto LABEL_22;
        }
        if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
        {
          v16 = hRpcHeap;
          v15 = 0;
          v19 = &v14;
          v17[0] = v4;
          v21 = &v13;
          v23 = (int **)v17;
          v25 = &v16;
          v27 = &v15;
          v13 = 68;
          v14 = 72;
          v20 = 1;
          v22 = 1;
          v24 = 8;
          v26 = 8;
          v28 = 8;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&RpcEtwGuid_Context,
            (unsigned int)RPCLogEvent,
            v10,
            6,
            (__int64)v18);
        }
      }
LABEL_22:
      if ( LsaFree )
        LsaFree(v4);
      else
        HeapFree(hRpcHeap, 0, v4);
    }
  }
}

```

## disassembly

```asm
0x180025d70  mov     [rsp-8+arg_0], rbx
0x180025d75  mov     [rsp-8+arg_10], rsi
0x180025d7a  push    rbp
0x180025d7b  push    rdi
0x180025d7c  push    r12
0x180025d7e  push    r14
0x180025d80  push    r15
0x180025d82  lea     rbp, [rsp-37h]
0x180025d87  sub     rsp, 0D0h
0x180025d8e  mov     rax, cs:__security_cookie
0x180025d95  xor     rax, rsp
0x180025d98  mov     [rbp+57h+var_30], rax
0x180025d9c  movsxd  rax, dword ptr [rdx-20h]
0x180025da0  lea     rdi, [rdx-20h]
0x180025da4  mov     rsi, cs:?gBufferCache@@3PEAVBCACHE@@EA; BCACHE * gBufferCache
0x180025dab  lea     r15, __ImageBase
0x180025db2  xor     r12d, r12d
0x180025db5  cmp     cs:dword_1800FE624, r12d
0x180025dbc  lea     ebx, [rax-1]
0x180025dbf  lea     r14, [rax-1]
0x180025dc3  jz      short loc_180025DEC
0x180025dc5  mov     eax, r12d
0x180025dc8  cmp     eax, 4
0x180025dcb  jnb     short loc_180025DDF
0x180025dcd  movsxd  rcx, eax
0x180025dd0  cmp     byte ptr [rcx+r15+0E66D8h], 62h ; 'b'
0x180025dd9  jz      short loc_180025DEC
0x180025ddb  inc     eax
0x180025ddd  jmp     short loc_180025DC8
0x180025ddf  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180025de6  jnz     loc_180025E86
0x180025dec  test    ebx, ebx
0x180025dee  js      loc_180025FFC
0x180025df4  cmp     ebx, 5
0x180025df7  jge     loc_180026024
0x180025dfd  call    cs:__imp_RtlGetCurrentProcessorNumber
0x180025e04  nop     dword ptr [rax+rax+00h]
0x180025e09  mov     r8, [rsi]
0x180025e0c  test    r8, r8
0x180025e0f  jz      loc_180025F11
0x180025e15  xor     edx, edx
0x180025e17  div     dword ptr [rsi+8]
0x180025e1a  lea     rbx, [r14+rdx*8]
0x180025e1e  shl     rbx, 4
0x180025e22  add     rbx, r8
0x180025e25  jz      loc_180025F11
0x180025e2b  mov     rcx, rbx; ListHead
0x180025e2e  call    cs:__imp_QueryDepthSList
0x180025e35  nop     dword ptr [rax+rax+00h]
0x180025e3a  movzx   eax, ax
0x180025e3d  cmp     eax, ds:rva ?gCacheHints@@3QBUBUFFER_CACHE_HINTS@@B[r15+r14*8]; BUFFER_CACHE_HINTS const near * const gCacheHints ...
0x180025e45  ja      loc_180025F11
0x180025e4b  mov     rdx, rdi; ListEntry
0x180025e4e  mov     rcx, rbx; ListHead
0x180025e51  call    cs:__imp_InterlockedPushEntrySList
0x180025e58  nop     dword ptr [rax+rax+00h]
0x180025e5d  mov     rcx, [rbp+57h+var_30]
0x180025e61  xor     rcx, rsp; StackCookie
0x180025e64  call    __security_check_cookie
0x180025e69  lea     r11, [rsp+0F0h+var_20]
0x180025e71  mov     rbx, [r11+30h]
0x180025e75  mov     rsi, [r11+40h]
0x180025e79  mov     rsp, r11
0x180025e7c  pop     r15
0x180025e7e  pop     r14
0x180025e80  pop     r12
0x180025e82  pop     rdi
0x180025e83  pop     rbp
0x180025e84  retn
0x180025e86  lea     rax, [rbp+57h+var_C0]
0x180025e8a  mov     [rbp+57h+var_A0], r14
0x180025e8e  mov     [rbp+57h+var_80], rax
0x180025e92  lea     rdx, RPCLogEvent
0x180025e99  lea     rax, [rbp+57h+var_B8]
0x180025e9d  mov     [rbp+57h+var_A8], r12
0x180025ea1  mov     [rbp+57h+var_70], rax
0x180025ea5  lea     rcx, RpcEtwGuid_Context
0x180025eac  lea     rax, [rbp+57h+var_B0]
0x180025eb0  mov     [rbp+57h+var_B0], rdi
0x180025eb4  mov     [rbp+57h+var_60], rax
0x180025eb8  mov     r9d, 6
0x180025ebe  lea     rax, [rbp+57h+var_A8]
0x180025ec2  mov     [rbp+57h+var_B8], 62h ; 'b'
0x180025ec6  mov     [rbp+57h+var_50], rax
0x180025eca  lea     rax, [rbp+57h+var_A0]
0x180025ece  mov     [rbp+57h+var_40], rax
0x180025ed2  lea     rax, [rbp+57h+var_90]
0x180025ed6  mov     [rsp+0F0h+var_D0], rax
0x180025edb  mov     [rbp+57h+var_C0], 62h ; 'b'
0x180025edf  mov     [rbp+57h+var_78], 1
0x180025ee7  mov     [rbp+57h+var_68], 1
0x180025eef  mov     [rbp+57h+var_58], 8
0x180025ef7  mov     [rbp+57h+var_48], 8
0x180025eff  mov     [rbp+57h+var_38], 8
0x180025f07  call    McGenEventWrite_EtwEventWriteTransfer
0x180025f0c  jmp     loc_180025DEC
0x180025f11  cmp     cs:dword_1800FE624, r12d
0x180025f18  jz      short loc_180025F3D
0x180025f1a  mov     ecx, r12d
0x180025f1d  cmp     ecx, 4
0x180025f20  jnb     short loc_180025F34
0x180025f22  movsxd  rax, ecx
0x180025f25  cmp     byte ptr [rax+r15+0E66D8h], 48h ; 'H'
0x180025f2e  jz      short loc_180025F3D
0x180025f30  inc     ecx
0x180025f32  jmp     short loc_180025F1D
0x180025f34  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180025f3b  jnz     short loc_180025F6A
0x180025f3d  mov     rax, cs:?LsaFree@@3P6AXPEAX@ZEA; void (*LsaFree)(void *)
0x180025f44  test    rax, rax
0x180025f47  jnz     loc_180026017
0x180025f4d  mov     rcx, cs:?hRpcHeap@@3PEAXEA; hHeap
0x180025f54  mov     r8, rdi; lpMem
0x180025f57  xor     edx, edx; dwFlags
0x180025f59  call    cs:__imp_HeapFree
0x180025f60  nop     dword ptr [rax+rax+00h]
0x180025f65  jmp     loc_180025E5D
0x180025f6a  mov     rax, cs:?hRpcHeap@@3PEAXEA; void * hRpcHeap
0x180025f71  lea     rdx, RPCLogEvent
0x180025f78  mov     [rbp+57h+var_A8], rax
0x180025f7c  lea     rcx, RpcEtwGuid_Context
0x180025f83  lea     rax, [rbp+57h+var_B8]
0x180025f87  mov     [rbp+57h+var_B0], r12
0x180025f8b  mov     [rbp+57h+var_80], rax
0x180025f8f  mov     r9d, 6
0x180025f95  lea     rax, [rbp+57h+var_C0]
0x180025f99  mov     [rbp+57h+var_A0], rdi
0x180025f9d  mov     [rbp+57h+var_70], rax
0x180025fa1  lea     rax, [rbp+57h+var_A0]
0x180025fa5  mov     [rbp+57h+var_60], rax
0x180025fa9  lea     rax, [rbp+57h+var_A8]
0x180025fad  mov     [rbp+57h+var_50], rax
0x180025fb1  lea     rax, [rbp+57h+var_B0]
0x180025fb5  mov     [rbp+57h+var_40], rax
0x180025fb9  lea     rax, [rbp+57h+var_90]
0x180025fbd  mov     [rsp+0F0h+var_D0], rax
0x180025fc2  mov     [rbp+57h+var_C0], 44h ; 'D'
0x180025fc6  mov     [rbp+57h+var_B8], 48h ; 'H'
0x180025fca  mov     [rbp+57h+var_78], 1
0x180025fd2  mov     [rbp+57h+var_68], 1
0x180025fda  mov     [rbp+57h+var_58], 8
0x180025fe2  mov     [rbp+57h+var_48], 8
0x180025fea  mov     [rbp+57h+var_38], 8
0x180025ff2  call    McGenEventWrite_EtwEventWriteTransfer
0x180025ff7  jmp     loc_180025F3D
0x180025ffc  cmp     ebx, 0FFFFFFFEh
0x180025fff  jnz     short loc_180026040
0x180026001  cmp     cs:?gBCacheMode@@3W4BCacheMode@@A, 1; BCacheMode gBCacheMode
0x180026008  jnz     short loc_180026059
0x18002600a  mov     rcx, rdi; lpMem
0x18002600d  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180026012  jmp     loc_180025E5D
0x180026017  mov     rcx, rdi
0x18002601a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002601f  jmp     loc_180025E5D
0x180026024  mov     rdx, rdi
0x180026027  lea     rcx, aRpcBcacheCorru; "RPC: BCache corruption detected at 0x%p"...
0x18002602e  call    cs:__imp_DbgPrint
0x180026035  nop     dword ptr [rax+rax+00h]
0x18002603a  int     3; Trap to Debugger
0x18002603b  jmp     loc_180025DFD
0x180026040  mov     rdx, rdi
0x180026043  lea     rcx, aRpcBcacheCorru; "RPC: BCache corruption detected at 0x%p"...
0x18002604a  call    cs:__imp_DbgPrint
0x180026051  nop     dword ptr [rax+rax+00h]
0x180026056  int     3; Trap to Debugger
0x180026057  jmp     short loc_180026001
0x180026059  cmp     cs:?gBufferCache2@@3PEAVBCache2@@EA, r12; BCache2 * gBufferCache2
0x180026060  jz      short loc_18002600A
0x180026062  mov     rdx, rdi; void *
0x180026065  call    ?Free@BCache2@@QEAAXPEAX@Z; BCache2::Free(void *)
0x18002606a  jmp     loc_180025E5D
```
