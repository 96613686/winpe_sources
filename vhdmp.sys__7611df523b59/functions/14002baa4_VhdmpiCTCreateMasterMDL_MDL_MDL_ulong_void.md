# VhdmpiCTCreateMasterMDL(_MDL *,_MDL * *,ulong *,void * *)

- ea: `0x14002baa4`
- end: `0x14002bcb5`
- name: `?VhdmpiCTCreateMasterMDL@@YAJPEAU_MDL@@PEAPEAU1@PEAKPEAPEAX@Z`
- size: `529`
- prototype: `__int64 __fastcall(struct _MDL *, struct _MDL **, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14002c5a4`

## callees

- `0x140023560`
- `0x14002baa4`
- `0x14002bcbc`
- `0x140035e94`
- `0x14005da00`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002bbec`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002bbec`
- `ntoskrnl!IoAllocateMdl` at `0x14002bb38`
- `ntoskrnl!IoAllocateMdl` at `0x14002bb38`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002bb71`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002bb71`

## string_xrefs

- `0x14002bc79`: `VhdmpiCTCreateMasterMDL: ERROR!   Status=0x%x`
- `0x14002bc90`: `VhdmpiCTCreateMasterMDL`

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
  int v19; // edx

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
  if ( v14 < 0 && (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
    TraceEvents((int)"VhdmpiCTCreateMasterMDL", 1029, 2, v19, "VhdmpiCTCreateMasterMDL: ERROR!   Status=0x%x", v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14002baa4  mov     [rsp+arg_10], rbx
0x14002baa9  mov     [rsp+arg_18], r9
0x14002baae  mov     [rsp+arg_8], rdx
0x14002bab3  push    rsi
0x14002bab4  push    r12
0x14002bab6  push    r13
0x14002bab8  push    r14
0x14002baba  push    r15
0x14002babc  sub     rsp, 40h
0x14002bac0  mov     r13, r8
0x14002bac3  mov     rax, rdx
0x14002bac6  mov     rbx, rcx
0x14002bac9  xor     esi, esi
0x14002bacb  xor     r15d, r15d
0x14002bace  xor     r14d, r14d
0x14002bad1  mov     [rsp+68h+var_30], r14
0x14002bad6  test    rcx, rcx
0x14002bad9  jz      loc_14002BC34
0x14002badf  test    rax, rax
0x14002bae2  jz      loc_14002BC34
0x14002bae8  test    r8, r8
0x14002baeb  jz      loc_14002BC34
0x14002baf1  cmp     [rcx], rsi
0x14002baf4  jz      loc_14002BC34
0x14002bafa  xor     edx, edx
0x14002bafc  mov     [rax], rdx
0x14002baff  mov     [r8], edx
0x14002bb02  mov     [r9], rdx
0x14002bb05  mov     rax, rcx
0x14002bb08  mov     ecx, [rax+28h]
0x14002bb0b  mov     rax, [rax]
0x14002bb0e  test    rax, rax
0x14002bb11  jz      short loc_14002BB1F
0x14002bb13  test    ecx, 0FFFh
0x14002bb19  jnz     loc_14002BC34
0x14002bb1f  add     edx, ecx; Length
0x14002bb21  test    rax, rax
0x14002bb24  jnz     short loc_14002BB08
0x14002bb26  mov     ecx, [rbx+2Ch]
0x14002bb29  add     rcx, [rbx+20h]; VirtualAddress
0x14002bb2d  mov     [rsp+68h+Irp], rsi; Irp
0x14002bb32  xor     r9d, r9d; ChargeQuota
0x14002bb35  xor     r8d, r8d; SecondaryBuffer
0x14002bb38  call    cs:__imp_IoAllocateMdl
0x14002bb3f  nop     dword ptr [rax+rax+00h]
0x14002bb44  mov     rsi, rax
0x14002bb47  mov     [rsp+68h+var_38], rax
0x14002bb4c  test    rax, rax
0x14002bb4f  jnz     short loc_14002BB5B
0x14002bb51  mov     ebx, 0C000009Ah
0x14002bb56  jmp     loc_14002BC39
0x14002bb5b  mov     r15d, [rbx+28h]
0x14002bb5f  mov     [rsp+68h+arg_0], r15d
0x14002bb64  mov     [rax+28h], r15d
0x14002bb68  xor     edx, edx; AccessMode
0x14002bb6a  lea     r8d, [rdx+2]; Operation
0x14002bb6e  mov     rcx, rsi; MemoryDescriptorList
0x14002bb71  call    cs:__imp_MmProbeAndLockPages
0x14002bb78  nop     dword ptr [rax+rax+00h]
0x14002bb7d  nop
0x14002bb7e  mov     r14d, [rbx+28h]
0x14002bb82  shr     r14d, 0Ch
0x14002bb86  mov     r12, [rbx]
0x14002bb89  jmp     short loc_14002BBCD
0x14002bb8b  mov     eax, [r12+28h]
0x14002bb90  mov     ecx, eax
0x14002bb92  shr     ecx, 0Ch
0x14002bb95  test    eax, 0FFFh
0x14002bb9a  lea     eax, [rcx+1]
0x14002bb9d  cmovz   eax, ecx
0x14002bba0  mov     ebx, eax
0x14002bba2  mov     r8d, eax
0x14002bba5  shl     r8, 3; Size
0x14002bba9  lea     rdx, [r12+30h]; Src
0x14002bbae  mov     eax, r14d
0x14002bbb1  add     rax, 6
0x14002bbb5  lea     rcx, [rsi+rax*8]; void *
0x14002bbb9  call    memmove
0x14002bbbe  mov     eax, [r12+28h]
0x14002bbc3  add     [rsi+28h], eax
0x14002bbc6  add     r14d, ebx
0x14002bbc9  mov     r12, [r12]
0x14002bbcd  test    r12, r12
0x14002bbd0  jnz     short loc_14002BB8B
0x14002bbd2  mov     [rsp+68h+Priority], 40000010h; Priority
0x14002bbda  mov     dword ptr [rsp+68h+Irp], r12d; BugCheckOnFailure
0x14002bbdf  xor     r9d, r9d; RequestedAddress
0x14002bbe2  xor     edx, edx; AccessMode
0x14002bbe4  lea     r8d, [r12+1]; CacheType
0x14002bbe9  mov     rcx, rsi; MemoryDescriptorList
0x14002bbec  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002bbf3  nop     dword ptr [rax+rax+00h]
0x14002bbf8  mov     r14, rax
0x14002bbfb  test    rax, rax
0x14002bbfe  jz      loc_14002BB51
0x14002bc04  xor     ebx, ebx
0x14002bc06  mov     rax, [rsp+68h+arg_8]
0x14002bc0b  mov     [rax], rsi
0x14002bc0e  mov     [r13+0], r15d
0x14002bc12  mov     rax, [rsp+68h+arg_18]
0x14002bc1a  mov     [rax], r14
0x14002bc1d  xor     esi, esi
0x14002bc1f  jmp     short loc_14002BC39
0x14002bc21  mov     ebx, eax
0x14002bc23  mov     rsi, [rsp+68h+var_38]
0x14002bc28  mov     r15d, [rsp+68h+arg_0]
0x14002bc2d  mov     r14, [rsp+68h+var_30]
0x14002bc32  jmp     short loc_14002BC39
0x14002bc34  mov     ebx, 0C000000Dh
0x14002bc39  test    rsi, rsi
0x14002bc3c  jz      short loc_14002BC4C
0x14002bc3e  mov     r8, r14; void *
0x14002bc41  mov     edx, r15d; unsigned int
0x14002bc44  mov     rcx, rsi; Mdl
0x14002bc47  call    ?VhdmpiCTDeleteMasterMDL@@YAXPEAU_MDL@@KPEAX@Z; VhdmpiCTDeleteMasterMDL(_MDL *,ulong,void *)
0x14002bc4c  test    ebx, ebx
0x14002bc4e  jns     short loc_14002BC9C
0x14002bc50  mov     eax, cs:dword_140087708
0x14002bc56  cmp     eax, 2
0x14002bc59  jbe     short loc_14002BC9C
0x14002bc5b  mov     edx, 1000h
0x14002bc60  lea     rcx, dword_140087708
0x14002bc67  call    _tlgKeywordOn
0x14002bc6c  test    al, al
0x14002bc6e  jz      short loc_14002BC9C
0x14002bc70  mov     ecx, 405h
0x14002bc75  mov     [rsp+68h+Priority], ebx; char
0x14002bc79  lea     rax, aVhdmpictcreate_0; "VhdmpiCTCreateMasterMDL: ERROR!   Statu"...
0x14002bc80  mov     [rsp+68h+Irp], rax; char *
0x14002bc85  mov     r9d, edx; int
0x14002bc88  mov     r8d, 2; int
0x14002bc8e  mov     edx, ecx; int
0x14002bc90  lea     rcx, aVhdmpictcreate; "VhdmpiCTCreateMasterMDL"
0x14002bc97  call    TraceEvents
0x14002bc9c  mov     eax, ebx
0x14002bc9e  mov     rbx, [rsp+68h+arg_10]
0x14002bca6  add     rsp, 40h
0x14002bcaa  pop     r15
0x14002bcac  pop     r14
0x14002bcae  pop     r13
0x14002bcb0  pop     r12
0x14002bcb2  pop     rsi
0x14002bcb3  retn
```
