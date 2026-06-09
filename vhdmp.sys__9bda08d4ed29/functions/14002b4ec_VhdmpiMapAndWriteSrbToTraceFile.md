# VhdmpiMapAndWriteSrbToTraceFile

- ea: `0x14002b4ec`
- end: `0x14002b69c`
- name: `VhdmpiMapAndWriteSrbToTraceFile`
- size: `432`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140005c30`
- `0x1400068d0`
- `0x140018480`
- `0x14001c4a0`

## callees

- `0x140014b00`
- `0x140023980`
- `0x14002b4ec`
- `0x14002bab4`
- `0x140036284`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14002b68b`
- `ntoskrnl!IoFreeMdl` at `0x14002b68b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002b655`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002b655`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002b52c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002b52c`
- `ntoskrnl!IoAllocateMdl` at `0x14002b5fa`
- `ntoskrnl!IoAllocateMdl` at `0x14002b5fa`
- `ntoskrnl!IoBuildPartialMdl` at `0x14002b621`
- `ntoskrnl!IoBuildPartialMdl` at `0x14002b621`

## string_xrefs

- `0x14002b5a0`: `CT Tracing error: SrbExtension length is greater than MDL byte count`
- `0x14002b5b1`: `VhdmpiMapAndWriteSrbToTraceFile`

## pseudocode

```c
__int64 __fastcall VhdmpiMapAndWriteSrbToTraceFile(__int64 *a1, int a2, unsigned int a3)
{
  __int64 v6; // r9
  unsigned int v7; // edi
  int v8; // eax
  int v9; // ecx
  __int64 v10; // rax
  ULONG v11; // edx
  unsigned int v12; // edx
  unsigned __int8 v13; // r8
  struct _MDL *Mdl; // rax
  struct _MDL *v16; // rbx
  PVOID MappedSystemVa; // rax

  if ( *(_QWORD *)(*a1 + 2152) == -1
    || !(unsigned __int8)VhdmpiIsCTLogTrackingEnabled(*a1) && (*(_DWORD *)(v6 + 2144) & 0x80u) == 0 )
  {
    return 0;
  }
  if ( !KeGetCurrentIrql() )
  {
    if ( (a1[8] & 0x800) == 0 )
    {
      v8 = *((_DWORD *)a1 + 15);
      if ( v8 == 5 || v8 == 4 )
        return 0;
    }
    v9 = *((_DWORD *)a1 + 15);
    if ( (unsigned int)(v9 - 6) <= 1 )
      return 0;
    v10 = a1[9];
    v11 = *((_DWORD *)a1 + 13);
    if ( v11 > *(_DWORD *)(v10 + 40) && v9 != 8 )
    {
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
        TraceEvents(
          "VhdmpiMapAndWriteSrbToTraceFile",
          0x9BEu,
          v13,
          v12,
          "CT Tracing error: SrbExtension length is greater than MDL byte count");
      return 0;
    }
    if ( !v10 || v9 == 8 )
    {
      v16 = 0;
      MappedSystemVa = 0;
    }
    else
    {
      v7 = -1073741823;
      Mdl = IoAllocateMdl((PVOID)(*(_QWORD *)(v10 + 32) + *(unsigned int *)(v10 + 44)), v11, 0, 0, 0);
      v16 = Mdl;
      if ( !Mdl )
        return v7;
      IoBuildPartialMdl(
        (PMDL)a1[9],
        Mdl,
        (PVOID)(*(_QWORD *)(a1[9] + 32) + *(unsigned int *)(a1[9] + 44)),
        *((_DWORD *)a1 + 13));
      if ( (v16->MdlFlags & 5) != 0 )
        MappedSystemVa = v16->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(v16, 0, MmCached, 0, 0, 0x40000010u);
      if ( !MappedSystemVa )
      {
LABEL_27:
        IoFreeMdl(v16);
        return v7;
      }
    }
    v7 = VhdmpiWriteSrbToTraceFile(a1, MappedSystemVa, a2, a3);
    if ( !v16 )
      return v7;
    goto LABEL_27;
  }
  return (unsigned int)-1073741608;
}

```

## disassembly

```asm
0x14002b4ec  push    rbx
0x14002b4ee  push    rbp
0x14002b4ef  push    rsi
0x14002b4f0  push    rdi
0x14002b4f1  push    r14
0x14002b4f3  sub     rsp, 30h
0x14002b4f7  mov     r9, [rcx]
0x14002b4fa  mov     ebp, r8d
0x14002b4fd  mov     r14d, edx
0x14002b500  mov     rsi, rcx
0x14002b503  cmp     qword ptr [r9+868h], 0FFFFFFFFFFFFFFFFh
0x14002b50b  jz      loc_14002B5BD
0x14002b511  mov     rcx, r9
0x14002b514  call    VhdmpiIsCTLogTrackingEnabled
0x14002b519  test    al, al
0x14002b51b  jnz     short loc_14002B52C
0x14002b51d  mov     eax, [r9+860h]
0x14002b524  test    al, al
0x14002b526  jns     loc_14002B5BD
0x14002b52c  call    cs:__imp_KeGetCurrentIrql
0x14002b533  nop     dword ptr [rax+rax+00h]
0x14002b538  test    al, al
0x14002b53a  jz      short loc_14002B543
0x14002b53c  mov     edi, 0C00000D8h
0x14002b541  jmp     short loc_14002B5BF
0x14002b543  test    dword ptr [rsi+40h], 800h
0x14002b54a  jnz     short loc_14002B559
0x14002b54c  mov     eax, [rsi+3Ch]
0x14002b54f  cmp     eax, 5
0x14002b552  jz      short loc_14002B5BD
0x14002b554  cmp     eax, 4
0x14002b557  jz      short loc_14002B5BD
0x14002b559  mov     ecx, [rsi+3Ch]
0x14002b55c  lea     eax, [rcx-6]
0x14002b55f  cmp     eax, 1
0x14002b562  jbe     short loc_14002B5BD
0x14002b564  mov     rax, [rsi+48h]
0x14002b568  mov     edx, [rsi+34h]; Length
0x14002b56b  cmp     edx, [rax+28h]
0x14002b56e  jbe     short loc_14002B5CD
0x14002b570  cmp     ecx, 8
0x14002b573  jz      short loc_14002B5CD
0x14002b575  mov     eax, cs:dword_1400876D0
0x14002b57b  mov     r8d, 2
0x14002b581  cmp     eax, r8d
0x14002b584  jbe     short loc_14002B5BD
0x14002b586  mov     edx, 1000h
0x14002b58b  lea     rcx, dword_1400876D0
0x14002b592  call    _tlgKeywordOn
0x14002b597  test    al, al
0x14002b599  jz      short loc_14002B5BD
0x14002b59b  mov     ecx, 9BEh
0x14002b5a0  lea     rax, aCtTracingError; "CT Tracing error: SrbExtension length i"...
0x14002b5a7  mov     r9d, edx; int
0x14002b5aa  mov     [rsp+58h+Irp], rax; char *
0x14002b5af  mov     edx, ecx; int
0x14002b5b1  lea     rcx, aVhdmpimapandwr; "VhdmpiMapAndWriteSrbToTraceFile"
0x14002b5b8  call    TraceEvents
0x14002b5bd  xor     edi, edi
0x14002b5bf  mov     eax, edi
0x14002b5c1  add     rsp, 30h
0x14002b5c5  pop     r14
0x14002b5c7  pop     rdi
0x14002b5c8  pop     rsi
0x14002b5c9  pop     rbp
0x14002b5ca  pop     rbx
0x14002b5cb  retn
0x14002b5cd  test    rax, rax
0x14002b5d0  jz      loc_14002B668
0x14002b5d6  cmp     ecx, 8
0x14002b5d9  jz      loc_14002B668
0x14002b5df  mov     ecx, [rax+2Ch]
0x14002b5e2  xor     r9d, r9d; ChargeQuota
0x14002b5e5  add     rcx, [rax+20h]; VirtualAddress
0x14002b5e9  xor     r8d, r8d; SecondaryBuffer
0x14002b5ec  mov     edi, 0C0000001h
0x14002b5f1  mov     [rsp+58h+Irp], 0; Irp
0x14002b5fa  call    cs:__imp_IoAllocateMdl
0x14002b601  nop     dword ptr [rax+rax+00h]
0x14002b606  mov     rbx, rax
0x14002b609  test    rax, rax
0x14002b60c  jz      short loc_14002B5BF
0x14002b60e  mov     rcx, [rsi+48h]; SourceMdl
0x14002b612  mov     rdx, rax; TargetMdl
0x14002b615  mov     r9d, [rsi+34h]; Length
0x14002b619  mov     r8d, [rcx+2Ch]
0x14002b61d  add     r8, [rcx+20h]; VirtualAddress
0x14002b621  call    cs:__imp_IoBuildPartialMdl
0x14002b628  nop     dword ptr [rax+rax+00h]
0x14002b62d  test    byte ptr [rbx+0Ah], 5
0x14002b631  jz      short loc_14002B639
0x14002b633  mov     rax, [rbx+18h]
0x14002b637  jmp     short loc_14002B661
0x14002b639  xor     r9d, r9d; RequestedAddress
0x14002b63c  mov     [rsp+58h+Priority], 40000010h; Priority
0x14002b644  xor     edx, edx; AccessMode
0x14002b646  mov     dword ptr [rsp+58h+Irp], 0; BugCheckOnFailure
0x14002b64e  mov     rcx, rbx; MemoryDescriptorList
0x14002b651  lea     r8d, [r9+1]; CacheType
0x14002b655  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002b65c  nop     dword ptr [rax+rax+00h]
0x14002b661  test    rax, rax
0x14002b664  jz      short loc_14002B688
0x14002b666  jmp     short loc_14002B66C
0x14002b668  xor     ebx, ebx
0x14002b66a  xor     eax, eax
0x14002b66c  mov     r9d, ebp
0x14002b66f  mov     r8d, r14d
0x14002b672  mov     rdx, rax
0x14002b675  mov     rcx, rsi
0x14002b678  call    VhdmpiWriteSrbToTraceFile
0x14002b67d  mov     edi, eax
0x14002b67f  test    rbx, rbx
0x14002b682  jz      loc_14002B5BF
0x14002b688  mov     rcx, rbx; Mdl
0x14002b68b  call    cs:__imp_IoFreeMdl
0x14002b692  nop     dword ptr [rax+rax+00h]
0x14002b697  jmp     loc_14002B5BF
```
