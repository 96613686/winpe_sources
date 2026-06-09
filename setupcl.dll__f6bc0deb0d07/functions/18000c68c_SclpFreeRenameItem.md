# SclpFreeRenameItem

- ea: `0x18000c68c`
- end: `0x18000c703`
- name: `SclpFreeRenameItem`
- size: `119`
- prototype: `BOOLEAN __fastcall(_QWORD *P)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000c70c`
- `0x18000d124`

## callees

- `0x18000c68c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000c6b1`
- `ntdll!RtlFreeHeap` at `0x18000c6d7`
- `ntdll!RtlFreeHeap` at `0x18000c6f7`
- `ntdll!RtlFreeHeap` at `0x18000c6b1`
- `ntdll!RtlFreeHeap` at `0x18000c6d7`
- `ntdll!RtlFreeHeap` at `0x18000c6f7`

## pseudocode

```c
BOOLEAN __fastcall SclpFreeRenameItem(_QWORD *P)
{
  void *v1; // r8
  void *v3; // r8
  BOOLEAN result; // al

  if ( P )
  {
    v1 = (void *)P[2];
    if ( v1 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
      P[2] = 0;
    }
    v3 = (void *)P[3];
    if ( v3 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
      P[3] = 0;
    }
    return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  return result;
}

```

## disassembly

```asm
0x18000c68c  test    rcx, rcx
0x18000c68f  jz      short locret_18000C702
0x18000c691  push    rbx
0x18000c692  sub     rsp, 20h
0x18000c696  mov     r8, [rcx+10h]; P
0x18000c69a  mov     rbx, rcx
0x18000c69d  test    r8, r8
0x18000c6a0  jz      short loc_18000C6BF
0x18000c6a2  mov     rcx, gs:60h
0x18000c6ab  xor     edx, edx; Flags
0x18000c6ad  mov     rcx, [rcx+30h]; HeapHandle
0x18000c6b1  call    cs:__imp_RtlFreeHeap
0x18000c6b7  mov     qword ptr [rbx+10h], 0
0x18000c6bf  mov     r8, [rbx+18h]; P
0x18000c6c3  test    r8, r8
0x18000c6c6  jz      short loc_18000C6E5
0x18000c6c8  mov     rcx, gs:60h
0x18000c6d1  xor     edx, edx; Flags
0x18000c6d3  mov     rcx, [rcx+30h]; HeapHandle
0x18000c6d7  call    cs:__imp_RtlFreeHeap
0x18000c6dd  mov     qword ptr [rbx+18h], 0
0x18000c6e5  mov     rcx, gs:60h
0x18000c6ee  mov     r8, rbx; P
0x18000c6f1  xor     edx, edx; Flags
0x18000c6f3  mov     rcx, [rcx+30h]; HeapHandle
0x18000c6f7  call    cs:__imp_RtlFreeHeap
0x18000c6fd  add     rsp, 20h
0x18000c701  pop     rbx
0x18000c702  retn
```
