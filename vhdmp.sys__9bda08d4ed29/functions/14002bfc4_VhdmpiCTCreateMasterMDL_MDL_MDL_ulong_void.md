# VhdmpiCTCreateMasterMDL(_MDL *,_MDL * *,ulong *,void * *)

- ea: `0x14002bfc4`
- end: `0x14002c1d5`
- name: `?VhdmpiCTCreateMasterMDL@@YAJPEAU_MDL@@PEAPEAU1@PEAKPEAPEAX@Z`
- size: `529`
- prototype: `__int64 __fastcall(struct _MDL *, struct _MDL **, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14002cac4`

## callees

- `0x140023980`
- `0x14002bfc4`
- `0x14002c1dc`
- `0x140036284`
- `0x14005de00`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002c10c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002c10c`
- `ntoskrnl!IoAllocateMdl` at `0x14002c058`
- `ntoskrnl!IoAllocateMdl` at `0x14002c058`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002c091`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002c091`

## string_xrefs

- `0x14002c199`: `VhdmpiCTCreateMasterMDL: ERROR!   Status=0x%x`
- `0x14002c1b0`: `VhdmpiCTCreateMasterMDL`

## pseudocode

```c
__int64 __fastcall VhdmpiCTCreateMasterMDL(struct _MDL *a1, struct _MDL **a2, unsigned int *a3, void **a4)
{
  struct _MDL *v7; // rsi
  ULONG v8; // r15d
  PVOID v9; // r14
  ULONG v10; // edx
  struct _MDL *v11; // rax
  ULONG ByteCount; // ecx
  PMDL Mdl; // rax
  int v14; // ebx
  ULONG v15; // r14d
  struct _MDL *i; // r12
  unsigned int v17; // eax
  unsigned int v18; // ebx
  unsigned int v19; // edx

  v7 = 0;
  v8 = 0;
  v9 = 0;
  if ( a1 && a2 && a3 && a1->Next )
  {
    v10 = 0;
    *a2 = 0;
    *a3 = 0;
    *a4 = 0;
    v11 = a1;
    while ( 1 )
    {
      ByteCount = v11->ByteCount;
      v11 = v11->Next;
      if ( v11 )
      {
        if ( (ByteCount & 0xFFF) != 0 )
          break;
      }
      v10 += ByteCount;
      if ( !v11 )
      {
        Mdl = IoAllocateMdl((char *)a1->StartVa + a1->ByteOffset, v10, 0, 0, 0);
        v7 = Mdl;
        if ( !Mdl )
          goto LABEL_10;
        v8 = a1->ByteCount;
        Mdl->ByteCount = v8;
        MmProbeAndLockPages(Mdl, 0, IoModifyAccess);
        v15 = a1->ByteCount >> 12;
        for ( i = a1->Next; i; i = i->Next )
        {
          v17 = (i->ByteCount >> 12) + 1;
          if ( (i->ByteCount & 0xFFF) == 0 )
            v17 = i->ByteCount >> 12;
          v18 = v17;
          memmove(&v7[1].Next + v15, &i[1], 8LL * v17);
          v7->ByteCount += i->ByteCount;
          v15 += v18;
        }
        v9 = MmMapLockedPagesSpecifyCache(v7, 0, MmCached, 0, 0, 0x40000010u);
        if ( v9 )
        {
          v14 = 0;
          *a2 = v7;
          *a3 = v8;
          *a4 = v9;
          v7 = 0;
        }
        else
        {
LABEL_10:
          v14 = -1073741670;
        }
        goto LABEL_19;
      }
    }
  }
  v14 = -1073741811;
LABEL_19:
  if ( v7 )
    VhdmpiCTDeleteMasterMDL(v7, v8, v9);
  if ( v14 < 0 && (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
    TraceEvents("VhdmpiCTCreateMasterMDL", 0x405u, 2u, v19, "VhdmpiCTCreateMasterMDL: ERROR!   Status=0x%x", v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14002bfc4  mov     [rsp+arg_10], rbx
0x14002bfc9  mov     [rsp+arg_18], r9
0x14002bfce  mov     [rsp+arg_8], rdx
0x14002bfd3  push    rsi
0x14002bfd4  push    r12
0x14002bfd6  push    r13
0x14002bfd8  push    r14
0x14002bfda  push    r15
0x14002bfdc  sub     rsp, 40h
0x14002bfe0  mov     r13, r8
0x14002bfe3  mov     rax, rdx
0x14002bfe6  mov     rbx, rcx
0x14002bfe9  xor     esi, esi
0x14002bfeb  xor     r15d, r15d
0x14002bfee  xor     r14d, r14d
0x14002bff1  mov     [rsp+68h+var_30], r14
0x14002bff6  test    rcx, rcx
0x14002bff9  jz      loc_14002C154
0x14002bfff  test    rax, rax
0x14002c002  jz      loc_14002C154
0x14002c008  test    r8, r8
0x14002c00b  jz      loc_14002C154
0x14002c011  cmp     [rcx], rsi
0x14002c014  jz      loc_14002C154
0x14002c01a  xor     edx, edx
0x14002c01c  mov     [rax], rdx
0x14002c01f  mov     [r8], edx
0x14002c022  mov     [r9], rdx
0x14002c025  mov     rax, rcx
0x14002c028  mov     ecx, [rax+28h]
0x14002c02b  mov     rax, [rax]
0x14002c02e  test    rax, rax
0x14002c031  jz      short loc_14002C03F
0x14002c033  test    ecx, 0FFFh
0x14002c039  jnz     loc_14002C154
0x14002c03f  add     edx, ecx; Length
0x14002c041  test    rax, rax
0x14002c044  jnz     short loc_14002C028
0x14002c046  mov     ecx, [rbx+2Ch]
0x14002c049  add     rcx, [rbx+20h]; VirtualAddress
0x14002c04d  mov     [rsp+68h+Irp], rsi; Irp
0x14002c052  xor     r9d, r9d; ChargeQuota
0x14002c055  xor     r8d, r8d; SecondaryBuffer
0x14002c058  call    cs:__imp_IoAllocateMdl
0x14002c05f  nop     dword ptr [rax+rax+00h]
0x14002c064  mov     rsi, rax
0x14002c067  mov     [rsp+68h+var_38], rax
0x14002c06c  test    rax, rax
0x14002c06f  jnz     short loc_14002C07B
0x14002c071  mov     ebx, 0C000009Ah
0x14002c076  jmp     loc_14002C159
0x14002c07b  mov     r15d, [rbx+28h]
0x14002c07f  mov     [rsp+68h+arg_0], r15d
0x14002c084  mov     [rax+28h], r15d
0x14002c088  xor     edx, edx; AccessMode
0x14002c08a  lea     r8d, [rdx+2]; Operation
0x14002c08e  mov     rcx, rsi; MemoryDescriptorList
0x14002c091  call    cs:__imp_MmProbeAndLockPages
0x14002c098  nop     dword ptr [rax+rax+00h]
0x14002c09d  nop
0x14002c09e  mov     r14d, [rbx+28h]
0x14002c0a2  shr     r14d, 0Ch
0x14002c0a6  mov     r12, [rbx]
0x14002c0a9  jmp     short loc_14002C0ED
0x14002c0ab  mov     eax, [r12+28h]
0x14002c0b0  mov     ecx, eax
0x14002c0b2  shr     ecx, 0Ch
0x14002c0b5  test    eax, 0FFFh
0x14002c0ba  lea     eax, [rcx+1]
0x14002c0bd  cmovz   eax, ecx
0x14002c0c0  mov     ebx, eax
0x14002c0c2  mov     r8d, eax
0x14002c0c5  shl     r8, 3; Size
0x14002c0c9  lea     rdx, [r12+30h]; Src
0x14002c0ce  mov     eax, r14d
0x14002c0d1  add     rax, 6
0x14002c0d5  lea     rcx, [rsi+rax*8]; void *
0x14002c0d9  call    memmove
0x14002c0de  mov     eax, [r12+28h]
0x14002c0e3  add     [rsi+28h], eax
0x14002c0e6  add     r14d, ebx
0x14002c0e9  mov     r12, [r12]
0x14002c0ed  test    r12, r12
0x14002c0f0  jnz     short loc_14002C0AB
0x14002c0f2  mov     [rsp+68h+Priority], 40000010h; Priority
0x14002c0fa  mov     dword ptr [rsp+68h+Irp], r12d; BugCheckOnFailure
0x14002c0ff  xor     r9d, r9d; RequestedAddress
0x14002c102  xor     edx, edx; AccessMode
0x14002c104  lea     r8d, [r12+1]; CacheType
0x14002c109  mov     rcx, rsi; MemoryDescriptorList
0x14002c10c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002c113  nop     dword ptr [rax+rax+00h]
0x14002c118  mov     r14, rax
0x14002c11b  test    rax, rax
0x14002c11e  jz      loc_14002C071
0x14002c124  xor     ebx, ebx
0x14002c126  mov     rax, [rsp+68h+arg_8]
0x14002c12b  mov     [rax], rsi
0x14002c12e  mov     [r13+0], r15d
0x14002c132  mov     rax, [rsp+68h+arg_18]
0x14002c13a  mov     [rax], r14
0x14002c13d  xor     esi, esi
0x14002c13f  jmp     short loc_14002C159
0x14002c141  mov     ebx, eax
0x14002c143  mov     rsi, [rsp+68h+var_38]
0x14002c148  mov     r15d, [rsp+68h+arg_0]
0x14002c14d  mov     r14, [rsp+68h+var_30]
0x14002c152  jmp     short loc_14002C159
0x14002c154  mov     ebx, 0C000000Dh
0x14002c159  test    rsi, rsi
0x14002c15c  jz      short loc_14002C16C
0x14002c15e  mov     r8, r14; void *
0x14002c161  mov     edx, r15d; unsigned int
0x14002c164  mov     rcx, rsi; Mdl
0x14002c167  call    ?VhdmpiCTDeleteMasterMDL@@YAXPEAU_MDL@@KPEAX@Z; VhdmpiCTDeleteMasterMDL(_MDL *,ulong,void *)
0x14002c16c  test    ebx, ebx
0x14002c16e  jns     short loc_14002C1BC
0x14002c170  mov     eax, cs:dword_1400876D0
0x14002c176  cmp     eax, 2
0x14002c179  jbe     short loc_14002C1BC
0x14002c17b  mov     edx, 1000h
0x14002c180  lea     rcx, dword_1400876D0
0x14002c187  call    _tlgKeywordOn
0x14002c18c  test    al, al
0x14002c18e  jz      short loc_14002C1BC
0x14002c190  mov     ecx, 405h
0x14002c195  mov     [rsp+68h+Priority], ebx; char
0x14002c199  lea     rax, aVhdmpictcreate_0; "VhdmpiCTCreateMasterMDL: ERROR!   Statu"...
0x14002c1a0  mov     [rsp+68h+Irp], rax; char *
0x14002c1a5  mov     r9d, edx; int
0x14002c1a8  mov     r8d, 2; int
0x14002c1ae  mov     edx, ecx; int
0x14002c1b0  lea     rcx, aVhdmpictcreate; "VhdmpiCTCreateMasterMDL"
0x14002c1b7  call    TraceEvents
0x14002c1bc  mov     eax, ebx
0x14002c1be  mov     rbx, [rsp+68h+arg_10]
0x14002c1c6  add     rsp, 40h
0x14002c1ca  pop     r15
0x14002c1cc  pop     r14
0x14002c1ce  pop     r13
0x14002c1d0  pop     r12
0x14002c1d2  pop     rsi
0x14002c1d3  retn
```
