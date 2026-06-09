# LRPC_ADDRESS::CompletionListNeedsActivating(void)

- ea: `0x180096930`
- end: `0x180096b42`
- name: `?CompletionListNeedsActivating@LRPC_ADDRESS@@QEAAXXZ`
- size: `530`
- prototype: `void __fastcall(LRPC_ADDRESS *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800229b0`

## callees

- `0x180021e70`
- `0x180022870`
- `0x18002f928`
- `0x18004ca30`
- `0x180096930`
- `0x180096b48`

## import_xrefs

- `ntdll!TpAlpcRegisterCompletionList` at `0x180096a58`
- `ntdll!TpAlpcRegisterCompletionList` at `0x180096a58`
- `ntdll!AlpcRegisterCompletionList` at `0x180096a3d`
- `ntdll!AlpcRegisterCompletionList` at `0x180096a3d`
- `ntdll!RtlDeleteResource` at `0x180096afc`
- `ntdll!RtlDeleteResource` at `0x180096afc`
- `ntdll!RtlInitializeResource` at `0x180096982`
- `ntdll!RtlInitializeResource` at `0x180096982`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800969bd`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800969bd`
- `ntdll!RtlReleaseResource` at `0x180096a98`
- `ntdll!RtlReleaseResource` at `0x180096a98`
- `ntdll!WinSqmIncrementDWORD` at `0x180096b30`
- `ntdll!WinSqmIncrementDWORD` at `0x180096b30`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180096a6e`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180096a6e`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180096a10`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180096a10`

## pseudocode

```c
void __fastcall LRPC_ADDRESS::CompletionListNeedsActivating(LRPC_ADDRESS *this)
{
  volatile signed __int64 *v2; // rsi
  struct _RTL_RESOURCE *v3; // rax
  struct _RTL_RESOURCE *v4; // r14
  LPVOID v5; // rax
  void *v6; // r14
  __int64 v7; // rcx
  signed __int32 v8[22]; // [rsp+0h] [rbp-58h] BYREF

  if ( !*((_DWORD *)this + 73) )
  {
    v2 = (volatile signed __int64 *)((char *)this + 344);
    if ( !*((_QWORD *)this + 43) )
    {
      v3 = (struct _RTL_RESOURCE *)AllocWrapper(0x60u);
      v4 = v3;
      if ( !v3 )
        return;
      RtlInitializeResource(v3);
      v8[12] = 0;
      if ( _InterlockedCompareExchange64(v2, (signed __int64)v4, 0) )
      {
        RtlDeleteResource(v4);
        FreeWrapper(v4);
      }
    }
    if ( RtlAcquireResourceExclusive(*(PRTL_RESOURCE *)v2, 0) )
    {
      if ( !*((_DWORD *)this + 73) )
      {
        *((_DWORD *)this + 73) = 1;
        _InterlockedIncrement((volatile signed __int32 *)&EnableLrpcCompletionListCheckupCount);
        if ( (unsigned int)GarbageCollectionNeeded(0, 0xFA0u) )
        {
          v5 = VirtualAlloc(0, *((unsigned int *)this + 76), 0x3000u, 4u);
          v6 = v5;
          if ( v5 )
          {
            if ( (int)AlpcRegisterCompletionList(
                        *((_QWORD *)this + 26),
                        v5,
                        *((unsigned int *)this + 76),
                        2,
                        -1442840576) >= 0 )
            {
              v7 = *((_QWORD *)this + 34);
              *(_BYTE *)(v7 + 8) = 1;
              TpAlpcRegisterCompletionList(*(_QWORD *)v7);
              if ( (*((_DWORD *)this + 72) & 4) == 0 )
                LRPC_ADDRESS::AddAddressToLrpcAddressList(this);
              *((_QWORD *)this + 37) = v6;
              _InterlockedOr(v8, 0);
              *((_DWORD *)this + 73) = 2;
              if ( !LrpcCompletionListEnabled )
              {
                WinSqmIncrementDWORD(0, 1191);
                LrpcCompletionListEnabled = 1;
              }
              *((_DWORD *)this + 72) |= 4u;
              goto LABEL_14;
            }
            VirtualFree(v6, 0, 0x8000u);
            *((_QWORD *)this + 37) = 0;
          }
          *((_DWORD *)this + 73) = 0;
          _InterlockedDecrement((volatile signed __int32 *)&EnableLrpcCompletionListCheckupCount);
          DecrementPeriodicGarbageCollectItems();
        }
        else
        {
          _InterlockedDecrement((volatile signed __int32 *)&EnableLrpcCompletionListCheckupCount);
          *((_DWORD *)this + 73) = 0;
        }
      }
LABEL_14:
      RtlReleaseResource(*(PRTL_RESOURCE *)v2);
    }
  }
}

```

## disassembly

```asm
0x180096930  mov     [rsp+arg_18], rbx
0x180096935  mov     [rsp+arg_0], rcx
0x18009693a  push    rsi
0x18009693b  push    r14
0x18009693d  push    r15
0x18009693f  sub     rsp, 40h
0x180096943  mov     rbx, rcx
0x180096946  mov     eax, [rcx+124h]
0x18009694c  test    eax, eax
0x18009694e  jnz     loc_180096A9E
0x180096954  lea     rsi, [rcx+158h]
0x18009695b  mov     [rsp+58h+arg_10], rsi
0x180096960  cmp     qword ptr [rsi], 0
0x180096964  jnz     short loc_1800969B8
0x180096966  lea     ecx, [rax+60h]; dwBytes
0x180096969  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18009696e  mov     r14, rax
0x180096971  mov     [rsp+58h+arg_8], rax
0x180096976  test    rax, rax
0x180096979  jz      loc_180096A9E
0x18009697f  mov     rcx, rax; Resource
0x180096982  call    cs:__imp_RtlInitializeResource
0x180096988  xor     eax, eax
0x18009698a  mov     [rsp+58h+var_28], eax
0x18009698e  jmp     short loc_1800969A3
0x180096990  mov     [rsp+58h+var_28], eax
0x180096994  mov     rbx, [rsp+58h+arg_0]
0x180096999  mov     r14, [rsp+58h+arg_8]
0x18009699e  mov     rsi, [rsp+58h+arg_10]
0x1800969a3  test    eax, eax
0x1800969a5  jnz     loc_180096AAD
0x1800969ab  xor     eax, eax
0x1800969ad  lock cmpxchg [rsi], r14
0x1800969b2  jnz     loc_180096AF9
0x1800969b8  xor     edx, edx; Wait
0x1800969ba  mov     rcx, [rsi]; Resource
0x1800969bd  call    cs:__imp_RtlAcquireResourceExclusive
0x1800969c3  test    al, al
0x1800969c5  jz      loc_180096A9E
0x1800969cb  mov     eax, [rbx+124h]
0x1800969d1  test    eax, eax
0x1800969d3  jnz     loc_180096A95
0x1800969d9  mov     dword ptr [rbx+124h], 1
0x1800969e3  lock inc cs:?EnableLrpcCompletionListCheckupCount@@3KA; ulong EnableLrpcCompletionListCheckupCount
0x1800969ea  mov     edx, 0FA0h; unsigned int
0x1800969ef  xor     ecx, ecx; int
0x1800969f1  call    ?GarbageCollectionNeeded@@YAHHK@Z; GarbageCollectionNeeded(int,ulong)
0x1800969f6  test    eax, eax
0x1800969f8  jz      loc_180096B0F
0x1800969fe  mov     edx, [rbx+130h]; dwSize
0x180096a04  xor     ecx, ecx; lpAddress
0x180096a06  lea     r9d, [rcx+4]; flProtect
0x180096a0a  mov     r8d, 3000h; flAllocationType
0x180096a10  call    cs:__imp_VirtualAlloc
0x180096a16  mov     r14, rax
0x180096a19  test    rax, rax
0x180096a1c  jz      short loc_180096A7F
0x180096a1e  mov     [rsp+58h+var_38], 0AA000000h
0x180096a26  mov     r9d, 2
0x180096a2c  mov     r8d, [rbx+130h]
0x180096a33  mov     rdx, rax
0x180096a36  mov     rcx, [rbx+0D0h]
0x180096a3d  call    cs:__imp_AlpcRegisterCompletionList
0x180096a43  mov     r15d, eax
0x180096a46  test    eax, eax
0x180096a48  js      short loc_180096A5E
0x180096a4a  mov     rcx, [rbx+110h]
0x180096a51  mov     byte ptr [rcx+8], 1
0x180096a55  mov     rcx, [rcx]
0x180096a58  call    cs:__imp_TpAlpcRegisterCompletionList
0x180096a5e  test    r15d, r15d
0x180096a61  jns     short loc_180096AB7
0x180096a63  xor     edx, edx; dwSize
0x180096a65  mov     r8d, 8000h; dwFreeType
0x180096a6b  mov     rcx, r14; lpAddress
0x180096a6e  call    cs:__imp_VirtualFree
0x180096a74  mov     qword ptr [rbx+128h], 0
0x180096a7f  mov     dword ptr [rbx+124h], 0
0x180096a89  lock dec cs:?EnableLrpcCompletionListCheckupCount@@3KA; ulong EnableLrpcCompletionListCheckupCount
0x180096a90  call    ?DecrementPeriodicGarbageCollectItems@@YAXXZ; DecrementPeriodicGarbageCollectItems(void)
0x180096a95  mov     rcx, [rsi]; Resource
0x180096a98  call    cs:__imp_RtlReleaseResource
0x180096a9e  mov     rbx, [rsp+58h+arg_18]
0x180096aa3  add     rsp, 40h
0x180096aa7  pop     r15
0x180096aa9  pop     r14
0x180096aab  pop     rsi
0x180096aac  retn
0x180096aad  mov     rcx, r14; lpMem
0x180096ab0  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180096ab5  jmp     short loc_180096A9E
0x180096ab7  mov     eax, [rbx+120h]
0x180096abd  test    al, 4
0x180096abf  jnz     short loc_180096AC9
0x180096ac1  mov     rcx, rbx; this
0x180096ac4  call    ?AddAddressToLrpcAddressList@LRPC_ADDRESS@@AEAAXXZ; LRPC_ADDRESS::AddAddressToLrpcAddressList(void)
0x180096ac9  mov     [rbx+128h], r14
0x180096ad0  lock or [rsp+58h+var_58], 0
0x180096ad5  mov     dword ptr [rbx+124h], 2
0x180096adf  cmp     cs:?LrpcCompletionListEnabled@@3KA, 0; ulong LrpcCompletionListEnabled
0x180096ae6  jz      short loc_180096B25
0x180096ae8  mov     eax, [rbx+120h]
0x180096aee  or      eax, 4
0x180096af1  mov     [rbx+120h], eax
0x180096af7  jmp     short loc_180096A95
0x180096af9  mov     rcx, r14; Resource
0x180096afc  call    cs:__imp_RtlDeleteResource
0x180096b02  mov     rcx, r14; lpMem
0x180096b05  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180096b0a  jmp     loc_1800969B8
0x180096b0f  lock dec cs:?EnableLrpcCompletionListCheckupCount@@3KA; ulong EnableLrpcCompletionListCheckupCount
0x180096b16  mov     dword ptr [rbx+124h], 0
0x180096b20  jmp     loc_180096A95
0x180096b25  mov     edx, 4A7h
0x180096b2a  xor     ecx, ecx
0x180096b2c  lea     r8d, [rcx+1]
0x180096b30  call    cs:__imp_WinSqmIncrementDWORD
0x180096b36  mov     cs:?LrpcCompletionListEnabled@@3KA, 1; ulong LrpcCompletionListEnabled
0x180096b40  jmp     short loc_180096AE8
```
