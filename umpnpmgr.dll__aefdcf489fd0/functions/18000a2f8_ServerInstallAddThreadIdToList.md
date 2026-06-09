# ServerInstallAddThreadIdToList

- ea: `0x18000a2f8`
- end: `0x18000a391`
- name: `ServerInstallAddThreadIdToList`
- size: `153`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180009d70`

## callees

- `0x18000a210`
- `0x18000a2f8`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000a319`
- `ntdll!RtlAllocateHeap` at `0x18000a319`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a379`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a379`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018ceb`

## pseudocode

```c
__int64 __fastcall ServerInstallAddThreadIdToList(int a1)
{
  _QWORD *Heap; // rax
  _QWORD *v3; // rbx
  unsigned int v4; // edi
  _QWORD *v5; // rax
  __int64 v6; // rcx

  Heap = RtlAllocateHeap(PnpHeapHandle, 8u, 0x20u);
  v3 = Heap;
  if ( Heap )
  {
    v4 = 1;
    *((_DWORD *)Heap + 4) = a1;
    *((_DWORD *)Heap + 5) = 0;
    Heap[3] = 0;
    pSetupBeginSynchronizedAccess(&qword_1800239B0);
    v5 = ServerInstallThreadIdList;
    v6 = *(_QWORD *)ServerInstallThreadIdList;
    if ( *(PVOID *)(*(_QWORD *)ServerInstallThreadIdList + 8LL) != ServerInstallThreadIdList )
      __fastfail(3u);
    *v3 = v6;
    v3[1] = v5;
    *(_QWORD *)(v6 + 8) = v3;
    *v5 = v3;
    ReleaseMutex(qword_1800239B8);
  }
  else
  {
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18000a2f8  mov     [rsp+arg_0], rbx
0x18000a2fd  mov     [rsp+arg_8], rsi
0x18000a302  push    rdi
0x18000a303  sub     rsp, 20h
0x18000a307  mov     esi, ecx
0x18000a309  mov     edx, 8; Flags
0x18000a30e  lea     r8d, [rdx+18h]; Size
0x18000a312  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x18000a319  call    cs:__imp_RtlAllocateHeap
0x18000a31f  mov     rbx, rax
0x18000a322  test    rax, rax
0x18000a325  jnz     short loc_18000A32B
0x18000a327  xor     edi, edi
0x18000a329  jmp     short loc_18000A37F
0x18000a32b  mov     edi, 1
0x18000a330  mov     [rax+10h], esi
0x18000a333  mov     dword ptr [rax+14h], 0
0x18000a33a  mov     qword ptr [rax+18h], 0
0x18000a342  lea     rcx, qword_1800239B0; lpHandles
0x18000a349  call    pSetupBeginSynchronizedAccess
0x18000a34e  nop
0x18000a34f  mov     rax, cs:ServerInstallThreadIdList
0x18000a356  mov     rcx, [rax]
0x18000a359  cmp     [rcx+8], rax
0x18000a35d  jz      short loc_18000A364
0x18000a35f  lea     ecx, [rdi+2]
0x18000a362  int     29h; Win8: RtlFailFast(ecx)
0x18000a364  mov     [rbx], rcx
0x18000a367  mov     [rbx+8], rax
0x18000a36b  mov     [rcx+8], rbx
0x18000a36f  mov     [rax], rbx
0x18000a372  mov     rcx, cs:qword_1800239B8; hMutex
0x18000a379  call    cs:__imp_ReleaseMutex
0x18000a37f  mov     eax, edi
0x18000a381  mov     rbx, [rsp+28h+arg_0]
0x18000a386  mov     rsi, [rsp+28h+arg_8]
0x18000a38b  add     rsp, 20h
0x18000a38f  pop     rdi
0x18000a390  retn
0x180018cd6  push    rbp
0x180018cd8  sub     rsp, 20h
0x180018cdc  mov     rbp, rdx
0x180018cdf  mov     rcx, cs:qword_1800239B8
0x180018ce6  add     rsp, 20h
0x180018cea  pop     rbp
0x180018ceb  jmp     cs:__imp_ReleaseMutex
```
