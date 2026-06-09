# ScCreateTemporaryImageRecord(ushort const *,ulong,unsigned __int64)

- ea: `0x14002d988`
- end: `0x14002dacb`
- name: `?ScCreateTemporaryImageRecord@@YAPEAU_IMAGE_RECORD@@PEBGK_K@Z`
- size: `323`
- prototype: `struct _IMAGE_RECORD *__fastcall(const unsigned __int16 *, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x14003c510`

## callees

- `0x14000cee0`
- `0x14001f99c`
- `0x14002d988`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14002da49`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14002da49`
- `ntdll!RtlAcquireResourceExclusive` at `0x14002da7e`
- `ntdll!RtlAcquireResourceExclusive` at `0x14002da7e`
- `ntdll!RtlReleaseResource` at `0x14002dab5`
- `ntdll!RtlReleaseResource` at `0x14002dab5`
- `ntdll!RtlFreeHeap` at `0x14002da6a`
- `ntdll!RtlFreeHeap` at `0x14002da6a`
- `ntdll!RtlAllocateHeap` at `0x14002d9cb`
- `ntdll!RtlAllocateHeap` at `0x14002d9cb`

## pseudocode

```c
struct _IMAGE_RECORD *__fastcall ScCreateTemporaryImageRecord(const unsigned __int16 *a1, int a2, __int64 a3)
{
  __int64 v3; // rax
  unsigned int v7; // esi
  unsigned __int16 *Heap; // rax
  unsigned __int16 *v9; // rbx
  __int64 v10; // r10
  HANDLE EventW; // rax
  __int64 v12; // rax

  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  v7 = 2 * v3 + 138;
  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v7);
  v9 = Heap;
  if ( Heap )
  {
    StringCbCopyW(Heap + 68, v7 - 136, a1);
    *((_QWORD *)v9 + 3) = v10;
    *((_DWORD *)v9 + 27) = a2;
    *((_DWORD *)v9 + 26) = 3;
    *((_QWORD *)v9 + 15) = a3;
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)v9 + 14) = EventW;
    if ( EventW )
    {
      RtlAcquireResourceExclusive(&ScServiceRecordLock, 1u);
      *((_QWORD *)v9 + 2) = qword_1400BC300;
      *((_QWORD *)v9 + 1) = &ImageDatabase;
      qword_1400BC300 = (struct _IMAGE_RECORD *)v9;
      v12 = *((_QWORD *)v9 + 2);
      if ( v12 )
        *(_QWORD *)(v12 + 8) = v9;
      RtlReleaseResource(&ScServiceRecordLock);
    }
    else
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
      return 0;
    }
  }
  else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
         && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->StubInfo, 17, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids);
  }
  return (struct _IMAGE_RECORD *)v9;
}

```

## disassembly

```asm
0x14002d988  push    rbx
0x14002d98a  push    rbp
0x14002d98b  push    rsi
0x14002d98c  push    rdi
0x14002d98d  push    r14
0x14002d98f  push    r15
0x14002d991  sub     rsp, 28h
0x14002d995  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002d999  mov     rbp, r8
0x14002d99c  xor     r15d, r15d
0x14002d99f  mov     r14d, edx
0x14002d9a2  mov     rdi, rcx
0x14002d9a5  inc     rax
0x14002d9a8  cmp     [rcx+rax*2], r15w
0x14002d9ad  jnz     short loc_14002D9A5
0x14002d9af  mov     rcx, gs:60h
0x14002d9b8  lea     esi, ds:8Ah[rax*2]
0x14002d9bf  mov     r8d, esi; Size
0x14002d9c2  mov     edx, 8; Flags
0x14002d9c7  mov     rcx, [rcx+30h]; HeapHandle
0x14002d9cb  call    cs:__imp_RtlAllocateHeap
0x14002d9d1  mov     rbx, rax
0x14002d9d4  test    rax, rax
0x14002d9d7  jnz     short loc_14002DA12
0x14002d9d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d9e0  lea     rax, WPP_GLOBAL_Control
0x14002d9e7  cmp     rcx, rax
0x14002d9ea  jz      loc_14002DABB
0x14002d9f0  test    byte ptr [rcx+1Ch], 4
0x14002d9f4  jz      loc_14002DABB
0x14002d9fa  mov     rcx, [rcx+10h]
0x14002d9fe  lea     edx, [rbx+11h]
0x14002da01  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14002da08  call    WPP_SF_
0x14002da0d  jmp     loc_14002DABB
0x14002da12  lea     r10, [rax+88h]
0x14002da19  mov     r8, rdi; unsigned __int16 *
0x14002da1c  mov     rcx, r10; unsigned __int16 *
0x14002da1f  lea     edx, [rsi-88h]; unsigned __int64
0x14002da25  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14002da2a  xor     r9d, r9d; lpName
0x14002da2d  mov     [rbx+18h], r10
0x14002da31  xor     r8d, r8d; bInitialState
0x14002da34  mov     [rbx+6Ch], r14d
0x14002da38  xor     ecx, ecx; lpEventAttributes
0x14002da3a  mov     dword ptr [rbx+68h], 3
0x14002da41  mov     [rbx+78h], rbp
0x14002da45  lea     edx, [r9+1]; bManualReset
0x14002da49  call    cs:__imp_CreateEventW
0x14002da4f  mov     [rbx+70h], rax
0x14002da53  test    rax, rax
0x14002da56  jnz     short loc_14002DA75
0x14002da58  mov     rcx, gs:60h
0x14002da61  mov     r8, rbx; P
0x14002da64  xor     edx, edx; Flags
0x14002da66  mov     rcx, [rcx+30h]; HeapHandle
0x14002da6a  call    cs:__imp_RtlFreeHeap
0x14002da70  mov     rbx, r15
0x14002da73  jmp     short loc_14002DABB
0x14002da75  mov     dl, 1; Wait
0x14002da77  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x14002da7e  call    cs:__imp_RtlAcquireResourceExclusive
0x14002da84  mov     rax, cs:qword_1400BC300
0x14002da8b  mov     [rbx+10h], rax
0x14002da8f  lea     rax, ?ImageDatabase@@3U_IMAGE_RECORD@@A; _IMAGE_RECORD ImageDatabase
0x14002da96  mov     [rbx+8], rax
0x14002da9a  mov     cs:qword_1400BC300, rbx
0x14002daa1  mov     rax, [rbx+10h]
0x14002daa5  test    rax, rax
0x14002daa8  jz      short loc_14002DAAE
0x14002daaa  mov     [rax+8], rbx
0x14002daae  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x14002dab5  call    cs:__imp_RtlReleaseResource
0x14002dabb  mov     rax, rbx
0x14002dabe  add     rsp, 28h
0x14002dac2  pop     r15
0x14002dac4  pop     r14
0x14002dac6  pop     rdi
0x14002dac7  pop     rsi
0x14002dac8  pop     rbp
0x14002dac9  pop     rbx
0x14002daca  retn
```
