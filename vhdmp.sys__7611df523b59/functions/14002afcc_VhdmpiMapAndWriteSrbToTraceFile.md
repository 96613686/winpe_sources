# VhdmpiMapAndWriteSrbToTraceFile

- ea: `0x14002afcc`
- end: `0x14002b17c`
- name: `VhdmpiMapAndWriteSrbToTraceFile`
- size: `432`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140005c30`
- `0x1400068d0`
- `0x140017fe0`
- `0x14001c080`

## callees

- `0x140014660`
- `0x140023560`
- `0x14002afcc`
- `0x14002b594`
- `0x140035e94`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14002b16b`
- `ntoskrnl!IoFreeMdl` at `0x14002b16b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002b135`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002b135`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002b00c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002b00c`
- `ntoskrnl!IoAllocateMdl` at `0x14002b0da`
- `ntoskrnl!IoAllocateMdl` at `0x14002b0da`
- `ntoskrnl!IoBuildPartialMdl` at `0x14002b101`
- `ntoskrnl!IoBuildPartialMdl` at `0x14002b101`

## string_xrefs

- `0x14002b091`: `VhdmpiMapAndWriteSrbToTraceFile`
- `0x14002b080`: `CT Tracing error: SrbExtension length is greater than MDL byte count`

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
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
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
0x14002afcc  push    rbx
0x14002afce  push    rbp
0x14002afcf  push    rsi
0x14002afd0  push    rdi
0x14002afd1  push    r14
0x14002afd3  sub     rsp, 30h
0x14002afd7  mov     r9, [rcx]
0x14002afda  mov     ebp, r8d
0x14002afdd  mov     r14d, edx
0x14002afe0  mov     rsi, rcx
0x14002afe3  cmp     qword ptr [r9+868h], 0FFFFFFFFFFFFFFFFh
0x14002afeb  jz      loc_14002B09D
0x14002aff1  mov     rcx, r9
0x14002aff4  call    VhdmpiIsCTLogTrackingEnabled
0x14002aff9  test    al, al
0x14002affb  jnz     short loc_14002B00C
0x14002affd  mov     eax, [r9+860h]
0x14002b004  test    al, al
0x14002b006  jns     loc_14002B09D
0x14002b00c  call    cs:__imp_KeGetCurrentIrql
0x14002b013  nop     dword ptr [rax+rax+00h]
0x14002b018  test    al, al
0x14002b01a  jz      short loc_14002B023
0x14002b01c  mov     edi, 0C00000D8h
0x14002b021  jmp     short loc_14002B09F
0x14002b023  test    dword ptr [rsi+40h], 800h
0x14002b02a  jnz     short loc_14002B039
0x14002b02c  mov     eax, [rsi+3Ch]
0x14002b02f  cmp     eax, 5
0x14002b032  jz      short loc_14002B09D
0x14002b034  cmp     eax, 4
0x14002b037  jz      short loc_14002B09D
0x14002b039  mov     ecx, [rsi+3Ch]
0x14002b03c  lea     eax, [rcx-6]
0x14002b03f  cmp     eax, 1
0x14002b042  jbe     short loc_14002B09D
0x14002b044  mov     rax, [rsi+48h]
0x14002b048  mov     edx, [rsi+34h]; Length
0x14002b04b  cmp     edx, [rax+28h]
0x14002b04e  jbe     short loc_14002B0AD
0x14002b050  cmp     ecx, 8
0x14002b053  jz      short loc_14002B0AD
0x14002b055  mov     eax, cs:dword_140087708
0x14002b05b  mov     r8d, 2
0x14002b061  cmp     eax, r8d
0x14002b064  jbe     short loc_14002B09D
0x14002b066  mov     edx, 1000h
0x14002b06b  lea     rcx, dword_140087708
0x14002b072  call    _tlgKeywordOn
0x14002b077  test    al, al
0x14002b079  jz      short loc_14002B09D
0x14002b07b  mov     ecx, 9BEh
0x14002b080  lea     rax, aCtTracingError; "CT Tracing error: SrbExtension length i"...
0x14002b087  mov     r9d, edx; int
0x14002b08a  mov     [rsp+58h+Irp], rax; char *
0x14002b08f  mov     edx, ecx; int
0x14002b091  lea     rcx, aVhdmpimapandwr; "VhdmpiMapAndWriteSrbToTraceFile"
0x14002b098  call    TraceEvents
0x14002b09d  xor     edi, edi
0x14002b09f  mov     eax, edi
0x14002b0a1  add     rsp, 30h
0x14002b0a5  pop     r14
0x14002b0a7  pop     rdi
0x14002b0a8  pop     rsi
0x14002b0a9  pop     rbp
0x14002b0aa  pop     rbx
0x14002b0ab  retn
0x14002b0ad  test    rax, rax
0x14002b0b0  jz      loc_14002B148
0x14002b0b6  cmp     ecx, 8
0x14002b0b9  jz      loc_14002B148
0x14002b0bf  mov     ecx, [rax+2Ch]
0x14002b0c2  xor     r9d, r9d; ChargeQuota
0x14002b0c5  add     rcx, [rax+20h]; VirtualAddress
0x14002b0c9  xor     r8d, r8d; SecondaryBuffer
0x14002b0cc  mov     edi, 0C0000001h
0x14002b0d1  mov     [rsp+58h+Irp], 0; Irp
0x14002b0da  call    cs:__imp_IoAllocateMdl
0x14002b0e1  nop     dword ptr [rax+rax+00h]
0x14002b0e6  mov     rbx, rax
0x14002b0e9  test    rax, rax
0x14002b0ec  jz      short loc_14002B09F
0x14002b0ee  mov     rcx, [rsi+48h]; SourceMdl
0x14002b0f2  mov     rdx, rax; TargetMdl
0x14002b0f5  mov     r9d, [rsi+34h]; Length
0x14002b0f9  mov     r8d, [rcx+2Ch]
0x14002b0fd  add     r8, [rcx+20h]; VirtualAddress
0x14002b101  call    cs:__imp_IoBuildPartialMdl
0x14002b108  nop     dword ptr [rax+rax+00h]
0x14002b10d  test    byte ptr [rbx+0Ah], 5
0x14002b111  jz      short loc_14002B119
0x14002b113  mov     rax, [rbx+18h]
0x14002b117  jmp     short loc_14002B141
0x14002b119  xor     r9d, r9d; RequestedAddress
0x14002b11c  mov     [rsp+58h+Priority], 40000010h; Priority
0x14002b124  xor     edx, edx; AccessMode
0x14002b126  mov     dword ptr [rsp+58h+Irp], 0; BugCheckOnFailure
0x14002b12e  mov     rcx, rbx; MemoryDescriptorList
0x14002b131  lea     r8d, [r9+1]; CacheType
0x14002b135  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002b13c  nop     dword ptr [rax+rax+00h]
0x14002b141  test    rax, rax
0x14002b144  jz      short loc_14002B168
0x14002b146  jmp     short loc_14002B14C
0x14002b148  xor     ebx, ebx
0x14002b14a  xor     eax, eax
0x14002b14c  mov     r9d, ebp
0x14002b14f  mov     r8d, r14d
0x14002b152  mov     rdx, rax
0x14002b155  mov     rcx, rsi
0x14002b158  call    VhdmpiWriteSrbToTraceFile
0x14002b15d  mov     edi, eax
0x14002b15f  test    rbx, rbx
0x14002b162  jz      loc_14002B09F
0x14002b168  mov     rcx, rbx; Mdl
0x14002b16b  call    cs:__imp_IoFreeMdl
0x14002b172  nop     dword ptr [rax+rax+00h]
0x14002b177  jmp     loc_14002B09F
```
