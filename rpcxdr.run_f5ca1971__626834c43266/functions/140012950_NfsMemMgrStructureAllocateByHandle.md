# NfsMemMgrStructureAllocateByHandle

- ea: `0x140012950`
- end: `0x1400129bd`
- name: `NfsMemMgrStructureAllocateByHandle`
- size: `109`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140007b48`
- `0x14000bb64`
- `0x14000fce4`
- `0x1400102b4`
- `0x1400104e0`
- `0x140011350`

## callees

- `0x1400122e0`
- `0x140012950`
- `0x140012e58`

## pseudocode

```c
__int64 __fastcall NfsMemMgrStructureAllocateByHandle(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rdx
  unsigned int Internal; // edi
  unsigned int v7; // eax

  v5 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
  if ( NfsRefHistoryTracingpGlobal )
    NfsReferenceHistoryCaptureRecord((_DWORD *)a1, v5, 0);
  Internal = NfsMemMgrpStructureAllocateInternal(a1, v5, a3);
  v7 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 4), 0, 0);
  if ( NfsRefHistoryTracingpGlobal )
    NfsReferenceHistoryCaptureRecord((_DWORD *)a1, v7, 1u);
  _InterlockedDecrement((volatile signed __int32 *)(a1 + 4));
  return Internal;
}

```

## disassembly

```asm
0x140012950  mov     [rsp+arg_0], rbx
0x140012955  push    rdi
0x140012956  sub     rsp, 20h
0x14001295a  mov     rdi, r8
0x14001295d  mov     rbx, rcx
0x140012960  mov     edx, 1
0x140012965  lock xadd [rcx+4], edx
0x14001296a  inc     edx
0x14001296c  cmp     cs:NfsRefHistoryTracingpGlobal, 0
0x140012974  jz      short loc_14001297E
0x140012976  xor     r8d, r8d
0x140012979  call    NfsReferenceHistoryCaptureRecord
0x14001297e  mov     r8, rdi
0x140012981  mov     rcx, rbx
0x140012984  call    NfsMemMgrpStructureAllocateInternal
0x140012989  xor     ecx, ecx
0x14001298b  mov     edi, eax
0x14001298d  xor     eax, eax
0x14001298f  lock cmpxchg [rbx+4], ecx
0x140012994  cmp     cs:NfsRefHistoryTracingpGlobal, rcx
0x14001299b  jz      short loc_1400129AB
0x14001299d  lea     r8d, [rcx+1]
0x1400129a1  mov     edx, eax
0x1400129a3  mov     rcx, rbx
0x1400129a6  call    NfsReferenceHistoryCaptureRecord
0x1400129ab  lock dec dword ptr [rbx+4]
0x1400129af  mov     eax, edi
0x1400129b1  mov     rbx, [rsp+28h+arg_0]
0x1400129b6  add     rsp, 20h
0x1400129ba  pop     rdi
0x1400129bb  retn
```
