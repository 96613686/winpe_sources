# NfsMemMgrStructureFreeByHandle

- ea: `0x140012a60`
- end: `0x140012acd`
- name: `NfsMemMgrStructureFreeByHandle`
- size: `109`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400083b8`
- `0x14000b140`
- `0x140010080`
- `0x1400103d0`
- `0x1400105d0`
- `0x14001143c`

## callees

- `0x1400122e0`
- `0x140012a60`
- `0x140012ad4`

## pseudocode

```c
__int64 __fastcall NfsMemMgrStructureFreeByHandle(__int64 a1, _WORD *a2)
{
  unsigned int v4; // edx
  unsigned int v5; // edi
  unsigned int v6; // eax

  v4 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
  if ( NfsRefHistoryTracingpGlobal )
    NfsReferenceHistoryCaptureRecord((_DWORD *)a1, v4, 0);
  v5 = NfsMemMgrStructureFreeInternal(a1, a2);
  v6 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 4), 0, 0);
  if ( NfsRefHistoryTracingpGlobal )
    NfsReferenceHistoryCaptureRecord((_DWORD *)a1, v6, 1u);
  _InterlockedDecrement((volatile signed __int32 *)(a1 + 4));
  return v5;
}

```

## disassembly

```asm
0x140012a60  mov     [rsp+arg_0], rbx
0x140012a65  push    rdi
0x140012a66  sub     rsp, 20h
0x140012a6a  mov     rdi, rdx
0x140012a6d  mov     rbx, rcx
0x140012a70  mov     edx, 1
0x140012a75  lock xadd [rcx+4], edx
0x140012a7a  inc     edx
0x140012a7c  cmp     cs:NfsRefHistoryTracingpGlobal, 0
0x140012a84  jz      short loc_140012A8E
0x140012a86  xor     r8d, r8d
0x140012a89  call    NfsReferenceHistoryCaptureRecord
0x140012a8e  mov     rdx, rdi
0x140012a91  mov     rcx, rbx
0x140012a94  call    NfsMemMgrStructureFreeInternal
0x140012a99  xor     ecx, ecx
0x140012a9b  mov     edi, eax
0x140012a9d  xor     eax, eax
0x140012a9f  lock cmpxchg [rbx+4], ecx
0x140012aa4  cmp     cs:NfsRefHistoryTracingpGlobal, rcx
0x140012aab  jz      short loc_140012ABB
0x140012aad  lea     r8d, [rcx+1]
0x140012ab1  mov     edx, eax
0x140012ab3  mov     rcx, rbx
0x140012ab6  call    NfsReferenceHistoryCaptureRecord
0x140012abb  lock dec dword ptr [rbx+4]
0x140012abf  mov     eax, edi
0x140012ac1  mov     rbx, [rsp+28h+arg_0]
0x140012ac6  add     rsp, 20h
0x140012aca  pop     rdi
0x140012acb  retn
```
