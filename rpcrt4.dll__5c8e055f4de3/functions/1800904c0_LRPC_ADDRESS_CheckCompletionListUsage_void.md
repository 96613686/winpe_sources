# LRPC_ADDRESS::CheckCompletionListUsage(void)

- ea: `0x1800904c0`
- end: `0x1800905c0`
- name: `?CheckCompletionListUsage@LRPC_ADDRESS@@UEAAXXZ`
- size: `256`
- prototype: `void __fastcall(LRPC_ADDRESS *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180025c00`
- `0x18004ca30`
- `0x1800904c0`
- `0x1800905c8`

## import_xrefs

- `ntdll!TpAlpcUnregisterCompletionList` at `0x180090568`
- `ntdll!TpAlpcUnregisterCompletionList` at `0x180090568`
- `ntdll!AlpcRundownCompletionList` at `0x18009051b`
- `ntdll!AlpcRundownCompletionList` at `0x18009051b`
- `ntdll!AlpcUnregisterCompletionList` at `0x180090575`
- `ntdll!AlpcUnregisterCompletionList` at `0x180090575`
- `ntdll!AlpcGetOutstandingCompletionListMessageCount` at `0x180090551`
- `ntdll!AlpcGetOutstandingCompletionListMessageCount` at `0x180090551`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800904ed`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800904ed`
- `ntdll!RtlReleaseResource` at `0x1800905b9`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180090592`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180090592`

## pseudocode

```c
void __fastcall LRPC_ADDRESS::CheckCompletionListUsage(LRPC_ADDRESS *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  signed __int32 v4[10]; // [rsp+0h] [rbp-28h] BYREF

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
      _InterlockedOr(v4, 0);
      if ( *((_DWORD *)this + 84) || (unsigned int)AlpcGetOutstandingCompletionListMessageCount(*((_QWORD *)this + 37)) )
        goto LABEL_12;
      v3 = *((_QWORD *)this + 34);
      *(_BYTE *)(v3 + 8) = 0;
      TpAlpcUnregisterCompletionList(*(_QWORD *)v3);
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
    RpcpReportFatalError(21, this);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x1800904c0  push    rbx
0x1800904c2  sub     rsp, 20h
0x1800904c6  mov     eax, [rcx+124h]
0x1800904cc  mov     rbx, rcx
0x1800904cf  cmp     eax, 2
0x1800904d2  jz      short loc_1800904DA
0x1800904d4  add     rsp, 20h
0x1800904d8  pop     rbx
0x1800904d9  retn
0x1800904da  call    ?GetCallBatchesPerUnitOfTime@LRPC_ADDRESS@@QEAAKXZ; LRPC_ADDRESS::GetCallBatchesPerUnitOfTime(void)
0x1800904df  cmp     eax, 2
0x1800904e2  jnb     short loc_1800904D4
0x1800904e4  mov     rcx, [rcx+158h]; Resource
0x1800904eb  mov     dl, 1; Wait
0x1800904ed  call    cs:__imp_RtlAcquireResourceExclusive
0x1800904f3  test    al, al
0x1800904f5  jnz     short loc_180090505
0x1800904f7  mov     rdx, rbx
0x1800904fa  mov     ecx, 15h
0x1800904ff  call    RpcpReportFatalError
0x180090504  int     3; Trap to Debugger
0x180090505  mov     eax, [rbx+124h]
0x18009050b  cmp     eax, 2
0x18009050e  jnz     loc_1800905AD
0x180090514  mov     rcx, [rbx+0D0h]
0x18009051b  call    cs:__imp_AlpcRundownCompletionList
0x180090521  test    eax, eax
0x180090523  js      short loc_1800904F7
0x180090525  mov     dword ptr [rbx+124h], 3
0x18009052f  lock dec cs:?EnableLrpcCompletionListCheckupCount@@3KA; ulong EnableLrpcCompletionListCheckupCount
0x180090536  call    ?DecrementPeriodicGarbageCollectItems@@YAXXZ; DecrementPeriodicGarbageCollectItems(void)
0x18009053b  lock or [rsp+28h+var_28], 0
0x180090540  mov     eax, [rbx+150h]
0x180090546  test    eax, eax
0x180090548  jnz     short loc_1800905AD
0x18009054a  mov     rcx, [rbx+128h]
0x180090551  call    cs:__imp_AlpcGetOutstandingCompletionListMessageCount
0x180090557  test    eax, eax
0x180090559  jnz     short loc_1800905AD
0x18009055b  mov     rcx, [rbx+110h]
0x180090562  mov     [rcx+8], al
0x180090565  mov     rcx, [rcx]
0x180090568  call    cs:__imp_TpAlpcUnregisterCompletionList
0x18009056e  mov     rcx, [rbx+0D0h]
0x180090575  call    cs:__imp_AlpcUnregisterCompletionList
0x18009057b  test    eax, eax
0x18009057d  js      loc_1800904F7
0x180090583  mov     rcx, [rbx+128h]; lpAddress
0x18009058a  xor     edx, edx; dwSize
0x18009058c  mov     r8d, 8000h; dwFreeType
0x180090592  call    cs:__imp_VirtualFree
0x180090598  mov     qword ptr [rbx+128h], 0
0x1800905a3  mov     dword ptr [rbx+124h], 0
0x1800905ad  mov     rcx, [rbx+158h]
0x1800905b4  add     rsp, 20h
0x1800905b8  pop     rbx
0x1800905b9  jmp     cs:__imp_RtlReleaseResource
```
