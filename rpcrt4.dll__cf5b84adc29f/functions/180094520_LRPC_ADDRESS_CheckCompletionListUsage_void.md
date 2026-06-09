# LRPC_ADDRESS::CheckCompletionListUsage(void)

- ea: `0x180094520`
- end: `0x18009464a`
- name: `?CheckCompletionListUsage@LRPC_ADDRESS@@UEAAXXZ`
- size: `298`
- prototype: `void __fastcall(LRPC_ADDRESS *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800162a8`
- `0x180026df0`
- `0x180094520`
- `0x180094650`

## import_xrefs

- `ntdll!TpAlpcUnregisterCompletionList` at `0x1800945db`
- `ntdll!TpAlpcUnregisterCompletionList` at `0x1800945db`
- `ntdll!AlpcRundownCompletionList` at `0x180094582`
- `ntdll!AlpcRundownCompletionList` at `0x180094582`
- `ntdll!AlpcUnregisterCompletionList` at `0x1800945ee`
- `ntdll!AlpcUnregisterCompletionList` at `0x1800945ee`
- `ntdll!AlpcGetOutstandingCompletionListMessageCount` at `0x1800945be`
- `ntdll!AlpcGetOutstandingCompletionListMessageCount` at `0x1800945be`
- `ntdll!RtlAcquireResourceExclusive` at `0x18009454e`
- `ntdll!RtlAcquireResourceExclusive` at `0x18009454e`
- `ntdll!RtlReleaseResource` at `0x18009463e`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180094611`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180094611`

## pseudocode

```c
void __fastcall LRPC_ADDRESS::CheckCompletionListUsage(LRPC_ADDRESS *this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rcx
  signed __int32 v6[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( *((_DWORD *)this + 73) == 2 && LRPC_ADDRESS::GetCallBatchesPerUnitOfTime(this) < 2 )
  {
    if ( !RtlAcquireResourceExclusive(*(PRTL_RESOURCE *)(v2 + 344), 1u) )
      goto LABEL_5;
    if ( *((_DWORD *)this + 73) != 2 )
      goto LABEL_12;
    if ( (int)AlpcRundownCompletionList(*((_QWORD *)this + 26)) >= 0 )
    {
      *((_DWORD *)this + 73) = 3;
      _InterlockedDecrement((volatile signed __int32 *)&EnableLrpcCompletionListCheckupCount);
      DecrementPeriodicGarbageCollectItems();
      _InterlockedOr(v6, 0);
      if ( *((_DWORD *)this + 84) || (unsigned int)AlpcGetOutstandingCompletionListMessageCount(*((_QWORD *)this + 37)) )
        goto LABEL_12;
      v5 = *((_QWORD *)this + 34);
      *(_BYTE *)(v5 + 8) = 0;
      TpAlpcUnregisterCompletionList(*(_QWORD *)v5);
      if ( (int)AlpcUnregisterCompletionList(*((_QWORD *)this + 26)) >= 0 )
      {
        VirtualFree(*((LPVOID *)this + 37), 0, 0x8000u);
        *((_QWORD *)this + 37) = 0;
        *((_DWORD *)this + 73) = 0;
LABEL_12:
        RtlReleaseResource(*((PRTL_RESOURCE *)this + 43));
        return;
      }
    }
LABEL_5:
    RpcpReportFatalError(21, this, v3, v4);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x180094520  push    rbx
0x180094522  sub     rsp, 20h
0x180094526  mov     eax, [rcx+124h]
0x18009452c  mov     rbx, rcx
0x18009452f  cmp     eax, 2
0x180094532  jz      short loc_18009453B
0x180094534  add     rsp, 20h
0x180094538  pop     rbx
0x180094539  retn
0x18009453b  call    ?GetCallBatchesPerUnitOfTime@LRPC_ADDRESS@@QEAAKXZ; LRPC_ADDRESS::GetCallBatchesPerUnitOfTime(void)
0x180094540  cmp     eax, 2
0x180094543  jnb     short loc_180094534
0x180094545  mov     rcx, [rcx+158h]; Resource
0x18009454c  mov     dl, 1; Wait
0x18009454e  call    cs:__imp_RtlAcquireResourceExclusive
0x180094555  nop     dword ptr [rax+rax+00h]
0x18009455a  test    al, al
0x18009455c  jnz     short loc_18009456C
0x18009455e  mov     rdx, rbx
0x180094561  mov     ecx, 15h
0x180094566  call    RpcpReportFatalError
0x18009456b  int     3; Trap to Debugger
0x18009456c  mov     eax, [rbx+124h]
0x180094572  cmp     eax, 2
0x180094575  jnz     loc_180094632
0x18009457b  mov     rcx, [rbx+0D0h]
0x180094582  call    cs:__imp_AlpcRundownCompletionList
0x180094589  nop     dword ptr [rax+rax+00h]
0x18009458e  test    eax, eax
0x180094590  js      short loc_18009455E
0x180094592  mov     dword ptr [rbx+124h], 3
0x18009459c  lock dec cs:?EnableLrpcCompletionListCheckupCount@@3KA; ulong EnableLrpcCompletionListCheckupCount
0x1800945a3  call    ?DecrementPeriodicGarbageCollectItems@@YAXXZ; DecrementPeriodicGarbageCollectItems(void)
0x1800945a8  lock or [rsp+28h+var_28], 0
0x1800945ad  mov     eax, [rbx+150h]
0x1800945b3  test    eax, eax
0x1800945b5  jnz     short loc_180094632
0x1800945b7  mov     rcx, [rbx+128h]
0x1800945be  call    cs:__imp_AlpcGetOutstandingCompletionListMessageCount
0x1800945c5  nop     dword ptr [rax+rax+00h]
0x1800945ca  test    eax, eax
0x1800945cc  jnz     short loc_180094632
0x1800945ce  mov     rcx, [rbx+110h]
0x1800945d5  mov     [rcx+8], al
0x1800945d8  mov     rcx, [rcx]
0x1800945db  call    cs:__imp_TpAlpcUnregisterCompletionList
0x1800945e2  nop     dword ptr [rax+rax+00h]
0x1800945e7  mov     rcx, [rbx+0D0h]
0x1800945ee  call    cs:__imp_AlpcUnregisterCompletionList
0x1800945f5  nop     dword ptr [rax+rax+00h]
0x1800945fa  test    eax, eax
0x1800945fc  js      loc_18009455E
0x180094602  mov     rcx, [rbx+128h]; lpAddress
0x180094609  xor     edx, edx; dwSize
0x18009460b  mov     r8d, 8000h; dwFreeType
0x180094611  call    cs:__imp_VirtualFree
0x180094618  nop     dword ptr [rax+rax+00h]
0x18009461d  mov     qword ptr [rbx+128h], 0
0x180094628  mov     dword ptr [rbx+124h], 0
0x180094632  mov     rcx, [rbx+158h]
0x180094639  add     rsp, 20h
0x18009463d  pop     rbx
0x18009463e  jmp     cs:__imp_RtlReleaseResource
```
