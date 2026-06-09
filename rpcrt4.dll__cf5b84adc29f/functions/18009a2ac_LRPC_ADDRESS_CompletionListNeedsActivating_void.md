# LRPC_ADDRESS::CompletionListNeedsActivating(void)

- ea: `0x18009a2ac`
- end: `0x18009a4f5`
- name: `?CompletionListNeedsActivating@LRPC_ADDRESS@@QEAAXXZ`
- size: `585`
- prototype: `void __fastcall(LRPC_ADDRESS *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180023b80`

## callees

- `0x1800162a8`
- `0x180023020`
- `0x180023a40`
- `0x180030cb8`
- `0x18009a2ac`
- `0x18009a4fc`

## import_xrefs

- `ntdll!TpAlpcRegisterCompletionList` at `0x18009a3ec`
- `ntdll!TpAlpcRegisterCompletionList` at `0x18009a3ec`
- `ntdll!AlpcRegisterCompletionList` at `0x18009a3cb`
- `ntdll!AlpcRegisterCompletionList` at `0x18009a3cb`
- `ntdll!RtlDeleteResource` at `0x18009a4a3`
- `ntdll!RtlDeleteResource` at `0x18009a4a3`
- `ntdll!RtlInitializeResource` at `0x18009a2fe`
- `ntdll!RtlInitializeResource` at `0x18009a2fe`
- `ntdll!RtlAcquireResourceExclusive` at `0x18009a33f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18009a33f`
- `ntdll!RtlReleaseResource` at `0x18009a438`
- `ntdll!RtlReleaseResource` at `0x18009a438`
- `ntdll!WinSqmIncrementDWORD` at `0x18009a4dd`
- `ntdll!WinSqmIncrementDWORD` at `0x18009a4dd`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18009a408`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18009a408`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18009a398`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18009a398`

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
                WinSqmIncrementDWORD(0, 1191, 1);
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
0x18009a2ac  mov     [rsp+arg_18], rbx
0x18009a2b1  mov     [rsp+arg_0], rcx
0x18009a2b6  push    rsi
0x18009a2b7  push    r14
0x18009a2b9  push    r15
0x18009a2bb  sub     rsp, 40h
0x18009a2bf  mov     rbx, rcx
0x18009a2c2  mov     eax, [rcx+124h]
0x18009a2c8  test    eax, eax
0x18009a2ca  jnz     loc_18009A444
0x18009a2d0  lea     rsi, [rcx+158h]
0x18009a2d7  mov     [rsp+58h+arg_10], rsi
0x18009a2dc  cmp     qword ptr [rsi], 0
0x18009a2e0  jnz     short loc_18009A33A
0x18009a2e2  lea     ecx, [rax+60h]; dwBytes
0x18009a2e5  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18009a2ea  mov     r14, rax
0x18009a2ed  mov     [rsp+58h+arg_8], rax
0x18009a2f2  test    rax, rax
0x18009a2f5  jz      loc_18009A444
0x18009a2fb  mov     rcx, rax; Resource
0x18009a2fe  call    cs:__imp_RtlInitializeResource
0x18009a305  nop     dword ptr [rax+rax+00h]
0x18009a30a  xor     eax, eax
0x18009a30c  mov     [rsp+58h+var_28], eax
0x18009a310  jmp     short loc_18009A325
0x18009a312  mov     [rsp+58h+var_28], eax
0x18009a316  mov     rbx, [rsp+58h+arg_0]
0x18009a31b  mov     r14, [rsp+58h+arg_8]
0x18009a320  mov     rsi, [rsp+58h+arg_10]
0x18009a325  test    eax, eax
0x18009a327  jnz     loc_18009A454
0x18009a32d  xor     eax, eax
0x18009a32f  lock cmpxchg [rsi], r14
0x18009a334  jnz     loc_18009A4A0
0x18009a33a  xor     edx, edx; Wait
0x18009a33c  mov     rcx, [rsi]; Resource
0x18009a33f  call    cs:__imp_RtlAcquireResourceExclusive
0x18009a346  nop     dword ptr [rax+rax+00h]
0x18009a34b  test    al, al
0x18009a34d  jz      loc_18009A444
0x18009a353  mov     eax, [rbx+124h]
0x18009a359  test    eax, eax
0x18009a35b  jnz     loc_18009A435
0x18009a361  mov     dword ptr [rbx+124h], 1
0x18009a36b  lock inc cs:?EnableLrpcCompletionListCheckupCount@@3KA; ulong EnableLrpcCompletionListCheckupCount
0x18009a372  mov     edx, 0FA0h; unsigned int
0x18009a377  xor     ecx, ecx; int
0x18009a379  call    ?GarbageCollectionNeeded@@YAHHK@Z; GarbageCollectionNeeded(int,ulong)
0x18009a37e  test    eax, eax
0x18009a380  jz      loc_18009A4BC
0x18009a386  mov     edx, [rbx+130h]; dwSize
0x18009a38c  xor     ecx, ecx; lpAddress
0x18009a38e  lea     r9d, [rcx+4]; flProtect
0x18009a392  mov     r8d, 3000h; flAllocationType
0x18009a398  call    cs:__imp_VirtualAlloc
0x18009a39f  nop     dword ptr [rax+rax+00h]
0x18009a3a4  mov     r14, rax
0x18009a3a7  test    rax, rax
0x18009a3aa  jz      short loc_18009A41F
0x18009a3ac  mov     [rsp+58h+var_38], 0AA000000h
0x18009a3b4  mov     r9d, 2
0x18009a3ba  mov     r8d, [rbx+130h]
0x18009a3c1  mov     rdx, rax
0x18009a3c4  mov     rcx, [rbx+0D0h]
0x18009a3cb  call    cs:__imp_AlpcRegisterCompletionList
0x18009a3d2  nop     dword ptr [rax+rax+00h]
0x18009a3d7  mov     r15d, eax
0x18009a3da  test    eax, eax
0x18009a3dc  js      short loc_18009A3F8
0x18009a3de  mov     rcx, [rbx+110h]
0x18009a3e5  mov     byte ptr [rcx+8], 1
0x18009a3e9  mov     rcx, [rcx]
0x18009a3ec  call    cs:__imp_TpAlpcRegisterCompletionList
0x18009a3f3  nop     dword ptr [rax+rax+00h]
0x18009a3f8  test    r15d, r15d
0x18009a3fb  jns     short loc_18009A45E
0x18009a3fd  xor     edx, edx; dwSize
0x18009a3ff  mov     r8d, 8000h; dwFreeType
0x18009a405  mov     rcx, r14; lpAddress
0x18009a408  call    cs:__imp_VirtualFree
0x18009a40f  nop     dword ptr [rax+rax+00h]
0x18009a414  mov     qword ptr [rbx+128h], 0
0x18009a41f  mov     dword ptr [rbx+124h], 0
0x18009a429  lock dec cs:?EnableLrpcCompletionListCheckupCount@@3KA; ulong EnableLrpcCompletionListCheckupCount
0x18009a430  call    ?DecrementPeriodicGarbageCollectItems@@YAXXZ; DecrementPeriodicGarbageCollectItems(void)
0x18009a435  mov     rcx, [rsi]; Resource
0x18009a438  call    cs:__imp_RtlReleaseResource
0x18009a43f  nop     dword ptr [rax+rax+00h]
0x18009a444  mov     rbx, [rsp+58h+arg_18]
0x18009a449  add     rsp, 40h
0x18009a44d  pop     r15
0x18009a44f  pop     r14
0x18009a451  pop     rsi
0x18009a452  retn
0x18009a454  mov     rcx, r14; lpMem
0x18009a457  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18009a45c  jmp     short loc_18009A444
0x18009a45e  mov     eax, [rbx+120h]
0x18009a464  test    al, 4
0x18009a466  jnz     short loc_18009A470
0x18009a468  mov     rcx, rbx; this
0x18009a46b  call    ?AddAddressToLrpcAddressList@LRPC_ADDRESS@@AEAAXXZ; LRPC_ADDRESS::AddAddressToLrpcAddressList(void)
0x18009a470  mov     [rbx+128h], r14
0x18009a477  lock or [rsp+58h+var_58], 0
0x18009a47c  mov     dword ptr [rbx+124h], 2
0x18009a486  cmp     cs:?LrpcCompletionListEnabled@@3KA, 0; ulong LrpcCompletionListEnabled
0x18009a48d  jz      short loc_18009A4D2
0x18009a48f  mov     eax, [rbx+120h]
0x18009a495  or      eax, 4
0x18009a498  mov     [rbx+120h], eax
0x18009a49e  jmp     short loc_18009A435
0x18009a4a0  mov     rcx, r14; Resource
0x18009a4a3  call    cs:__imp_RtlDeleteResource
0x18009a4aa  nop     dword ptr [rax+rax+00h]
0x18009a4af  mov     rcx, r14; lpMem
0x18009a4b2  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18009a4b7  jmp     loc_18009A33A
0x18009a4bc  lock dec cs:?EnableLrpcCompletionListCheckupCount@@3KA; ulong EnableLrpcCompletionListCheckupCount
0x18009a4c3  mov     dword ptr [rbx+124h], 0
0x18009a4cd  jmp     loc_18009A435
0x18009a4d2  mov     edx, 4A7h
0x18009a4d7  xor     ecx, ecx
0x18009a4d9  lea     r8d, [rcx+1]
0x18009a4dd  call    cs:__imp_WinSqmIncrementDWORD
0x18009a4e4  nop     dword ptr [rax+rax+00h]
0x18009a4e9  mov     cs:?LrpcCompletionListEnabled@@3KA, 1; ulong LrpcCompletionListEnabled
0x18009a4f3  jmp     short loc_18009A48F
```
