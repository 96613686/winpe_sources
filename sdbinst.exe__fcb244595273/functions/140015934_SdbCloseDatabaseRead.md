# SdbCloseDatabaseRead

- ea: `0x140015934`
- end: `0x140015a12`
- name: `SdbCloseDatabaseRead`
- size: `222`
- prototype: `BOOLEAN __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140008500`
- `0x140015b08`
- `0x140018e34`
- `0x140019018`

## callees

- `0x14000f980`
- `0x14000ffe0`
- `0x140015934`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140015967`
- `ntdll!RtlFreeHeap` at `0x140015988`
- `ntdll!RtlFreeHeap` at `0x1400159d7`
- `ntdll!RtlFreeHeap` at `0x140015967`
- `ntdll!RtlFreeHeap` at `0x140015988`
- `ntdll!RtlFreeHeap` at `0x1400159d7`
- `ntdll!RtlFreeHeap` at `0x140015a0b`

## pseudocode

```c
BOOLEAN __fastcall SdbCloseDatabaseRead(_QWORD *a1)
{
  __int64 v1; // rax
  void *v3; // r8
  void *v4; // r8
  void *v5; // rcx
  void *v6; // r8

  v1 = a1[330];
  if ( v1 && *(_DWORD *)(v1 + 16) == 1 )
  {
    v3 = *(void **)(v1 + 8);
    if ( v3 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
    v4 = (void *)a1[330];
    if ( v4 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    v5 = (void *)a1[331];
    a1[330] = 0;
    if ( v5 )
    {
      AslHashFree(v5);
      a1[331] = 0;
    }
  }
  if ( (a1[3] & 9) == 9 )
  {
    v6 = (void *)a1[1];
    if ( v6 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      a1[1] = 0;
      *((_DWORD *)a1 + 5) = 0;
    }
  }
  AslFileMappingDelete((_BYTE *)*a1);
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x140015934  push    rbx
0x140015936  sub     rsp, 20h
0x14001593a  mov     rax, [rcx+0A50h]
0x140015941  mov     rbx, rcx
0x140015944  test    rax, rax
0x140015947  jz      short loc_1400159B5
0x140015949  cmp     dword ptr [rax+10h], 1
0x14001594d  jnz     short loc_1400159B5
0x14001594f  mov     r8, [rax+8]; P
0x140015953  test    r8, r8
0x140015956  jz      short loc_14001596D
0x140015958  mov     rcx, gs:60h
0x140015961  xor     edx, edx; Flags
0x140015963  mov     rcx, [rcx+30h]; HeapHandle
0x140015967  call    cs:__imp_RtlFreeHeap
0x14001596d  mov     r8, [rbx+0A50h]; P
0x140015974  test    r8, r8
0x140015977  jz      short loc_14001598E
0x140015979  mov     rcx, gs:60h
0x140015982  xor     edx, edx; Flags
0x140015984  mov     rcx, [rcx+30h]; HeapHandle
0x140015988  call    cs:__imp_RtlFreeHeap
0x14001598e  mov     rcx, [rbx+0A58h]; P
0x140015995  mov     qword ptr [rbx+0A50h], 0
0x1400159a0  test    rcx, rcx
0x1400159a3  jz      short loc_1400159B5
0x1400159a5  call    AslHashFree
0x1400159aa  mov     qword ptr [rbx+0A58h], 0
0x1400159b5  mov     eax, [rbx+18h]
0x1400159b8  and     eax, 9
0x1400159bb  cmp     al, 9
0x1400159bd  jnz     short loc_1400159EC
0x1400159bf  mov     r8, [rbx+8]; P
0x1400159c3  test    r8, r8
0x1400159c6  jz      short loc_1400159EC
0x1400159c8  mov     rcx, gs:60h
0x1400159d1  xor     edx, edx; Flags
0x1400159d3  mov     rcx, [rcx+30h]; HeapHandle
0x1400159d7  call    cs:__imp_RtlFreeHeap
0x1400159dd  mov     qword ptr [rbx+8], 0
0x1400159e5  mov     dword ptr [rbx+14h], 0
0x1400159ec  mov     rcx, [rbx]; P
0x1400159ef  call    AslFileMappingDelete
0x1400159f4  mov     rcx, gs:60h
0x1400159fd  mov     r8, rbx
0x140015a00  xor     edx, edx
0x140015a02  mov     rcx, [rcx+30h]
0x140015a06  add     rsp, 20h
0x140015a0a  pop     rbx
0x140015a0b  jmp     cs:__imp_RtlFreeHeap
```
