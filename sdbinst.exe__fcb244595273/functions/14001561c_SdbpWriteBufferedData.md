# SdbpWriteBufferedData

- ea: `0x14001561c`
- end: `0x140015766`
- name: `SdbpWriteBufferedData`
- size: `330`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140014b64`
- `0x1400152d8`
- `0x140015838`
- `0x14001d808`

## callees

- `0x140002206`
- `0x14001008c`
- `0x14001561c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140015699`
- `ntdll!RtlAllocateHeap` at `0x140015699`
- `ntdll!RtlFreeHeap` at `0x1400156fc`
- `ntdll!RtlFreeHeap` at `0x1400156fc`

## string_xrefs

- `0x1400156b8`: `SdbpWriteBufferedData`
- `0x140015744`: `SdbpWriteBufferedData`

## pseudocode

```c
__int64 __fastcall SdbpWriteBufferedData(__int64 a1, unsigned int a2, const void *a3, unsigned int a4, int a5)
{
  size_t v6; // rbp
  __int64 v8; // r14
  unsigned int v9; // edi
  unsigned int v10; // esi
  PVOID Heap; // rax
  PVOID v12; // r15
  const void *v13; // rdx
  void *v14; // r8

  v6 = a4;
  v8 = a2;
  if ( !*(_DWORD *)(a1 + 16) )
  {
    AslLogCallPrintf(1, "SdbpWriteBufferedData", 245, "Invalid parameter");
    return 0;
  }
  v9 = a2 + a4;
  if ( a2 + a4 < a2 )
  {
    AslLogCallPrintf(1, "SdbpWriteBufferedData", 250, "Invalid total buffer size");
    return 0;
  }
  if ( v9 > *(_DWORD *)(a1 + 2656) )
  {
    v10 = v9 + 2048;
    if ( v9 + 2048 < v9 )
    {
      AslLogCallPrintf(1, "SdbpWriteBufferedData", 263, "Invalid new buffer size");
      return 0;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v10);
    v12 = Heap;
    if ( !Heap )
    {
      AslLogCallPrintf(1, "SdbpWriteBufferedData", 270, "Failed to allocate %d bytes", v9 + 2048);
      return 0;
    }
    v13 = *(const void **)(a1 + 8);
    if ( v13 )
    {
      memcpy_0(Heap, v13, *(unsigned int *)(a1 + 2656));
      v14 = *(void **)(a1 + 8);
      if ( v14 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
    }
    *(_QWORD *)(a1 + 8) = v12;
    *(_DWORD *)(a1 + 2656) = v10;
  }
  memcpy_0((void *)(*(_QWORD *)(a1 + 8) + v8), a3, v6);
  if ( !a5 && v9 > *(_DWORD *)(a1 + 20) )
    *(_DWORD *)(a1 + 20) = v9;
  return 1;
}

```

## disassembly

```asm
0x14001561c  push    rbx
0x14001561e  push    rbp
0x14001561f  push    rsi
0x140015620  push    rdi
0x140015621  push    r12
0x140015623  push    r14
0x140015625  push    r15
0x140015627  sub     rsp, 30h
0x14001562b  cmp     dword ptr [rcx+10h], 0
0x14001562f  mov     r12, r8
0x140015632  mov     ebp, r9d
0x140015635  mov     rbx, rcx
0x140015638  mov     r14d, edx
0x14001563b  jnz     short loc_14001564F
0x14001563d  lea     r9, aInvalidParamet_0; "Invalid parameter"
0x140015644  mov     r8d, 0F5h
0x14001564a  jmp     loc_140015744
0x14001564f  lea     edi, [r14+rbp]
0x140015653  cmp     edi, r14d
0x140015656  jb      loc_140015737
0x14001565c  cmp     edi, [rcx+0A60h]
0x140015662  jbe     loc_14001570C
0x140015668  lea     esi, [rdi+800h]
0x14001566e  cmp     esi, edi
0x140015670  jnb     short loc_140015684
0x140015672  lea     r9, aInvalidNewBuff; "Invalid new buffer size"
0x140015679  mov     r8d, 107h
0x14001567f  jmp     loc_140015744
0x140015684  mov     rcx, gs:60h
0x14001568d  mov     edx, 8; Flags
0x140015692  mov     r8d, esi; Size
0x140015695  mov     rcx, [rcx+30h]; HeapHandle
0x140015699  call    cs:__imp_RtlAllocateHeap
0x14001569f  mov     r15, rax
0x1400156a2  test    rax, rax
0x1400156a5  jnz     short loc_1400156CC
0x1400156a7  lea     r9, aFailedToAlloca_10; "Failed to allocate %d bytes"
0x1400156ae  mov     [rsp+68h+var_48], esi
0x1400156b2  mov     r8d, 10Eh
0x1400156b8  lea     rdx, aSdbpwritebuffe; "SdbpWriteBufferedData"
0x1400156bf  lea     ecx, [rax+1]
0x1400156c2  call    AslLogCallPrintf
0x1400156c7  jmp     loc_140015755
0x1400156cc  mov     rdx, [rbx+8]; Src
0x1400156d0  test    rdx, rdx
0x1400156d3  jz      short loc_140015702
0x1400156d5  mov     r8d, [rbx+0A60h]; Size
0x1400156dc  mov     rcx, r15; void *
0x1400156df  call    memcpy_0
0x1400156e4  mov     r8, [rbx+8]; P
0x1400156e8  test    r8, r8
0x1400156eb  jz      short loc_140015702
0x1400156ed  mov     rcx, gs:60h
0x1400156f6  xor     edx, edx; Flags
0x1400156f8  mov     rcx, [rcx+30h]; HeapHandle
0x1400156fc  call    cs:__imp_RtlFreeHeap
0x140015702  mov     [rbx+8], r15
0x140015706  mov     [rbx+0A60h], esi
0x14001570c  mov     rcx, r14
0x14001570f  mov     r8, rbp; Size
0x140015712  add     rcx, [rbx+8]; void *
0x140015716  mov     rdx, r12; Src
0x140015719  call    memcpy_0
0x14001571e  cmp     [rsp+68h+arg_20], 0
0x140015726  jnz     short loc_140015730
0x140015728  cmp     edi, [rbx+14h]
0x14001572b  jbe     short loc_140015730
0x14001572d  mov     [rbx+14h], edi
0x140015730  mov     eax, 1
0x140015735  jmp     short loc_140015757
0x140015737  lea     r9, aInvalidTotalBu; "Invalid total buffer size"
0x14001573e  mov     r8d, 0FAh
0x140015744  lea     rdx, aSdbpwritebuffe; "SdbpWriteBufferedData"
0x14001574b  mov     ecx, 1
0x140015750  call    AslLogCallPrintf
0x140015755  xor     eax, eax
0x140015757  add     rsp, 30h
0x14001575b  pop     r15
0x14001575d  pop     r14
0x14001575f  pop     r12
0x140015761  pop     rdi
0x140015762  pop     rsi
0x140015763  pop     rbp
0x140015764  pop     rbx
0x140015765  retn
```
