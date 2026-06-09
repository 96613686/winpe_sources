# VhdmpiInitializeNewBackingStore

- ea: `0x1400e538c`
- end: `0x1400e55e3`
- name: `VhdmpiInitializeNewBackingStore`
- size: `599`
- prototype: `__int64 __fastcall(struct _VHD_BACKING_STORE_HEADER *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x1400e55ec`

## callees

- `0x140014710`
- `0x140017450`
- `0x1400210e0`
- `0x140023980`
- `0x140026e20`
- `0x14002ef38`
- `0x140036284`
- `0x1400e538c`
- `0x1400e77ac`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400e54f6`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400e54f6`
- `ntoskrnl!KeInitializeMutex` at `0x1400e54ac`
- `ntoskrnl!KeInitializeMutex` at `0x1400e54ac`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400e5484`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400e5484`

## pseudocode

```c
__int64 __fastcall VhdmpiInitializeNewBackingStore(struct _VHD_BACKING_STORE_HEADER *a1, char a2)
{
  __int64 v2; // r8
  int v4; // ebp
  __int64 v5; // rdx
  int Irp; // edi
  unsigned __int8 v7; // r8
  unsigned int v8; // r9d
  unsigned __int8 v9; // r8
  unsigned int v10; // r9d
  unsigned int v12; // ecx
  __int64 v13; // rdx
  int v14; // edx
  __int64 v15; // rax

  v2 = *(_QWORD *)a1;
  v4 = 0;
  *((_DWORD *)a1 + 16) = *(_DWORD *)(*(_QWORD *)a1 + 20LL);
  *((_DWORD *)a1 + 17) = *(_DWORD *)(v2 + 24);
  *((_BYTE *)a1 + 973) = a2;
  Irp = RmwInitializePackage(a1);
  if ( Irp >= 0 )
  {
    Irp = VhdmpiFileWrapperAllocateIrp((char *)a1 + 72, v5, (char *)a1 + 1032);
    if ( Irp >= 0 )
    {
      ExInitializeResourceLite((PERESOURCE)((char *)a1 + 864));
      *((_BYTE *)a1 + 856) = 1;
      VhdmpiInitializePassiveLock((char *)a1 + 1120);
      KeInitializeMutex((PRKMUTEX)((char *)a1 + 976), 0);
      *((_DWORD *)a1 + 266) = *((_DWORD *)a1 + 48);
      v12 = *(_DWORD *)(*(_QWORD *)a1 + 44LL);
      if ( v12 )
      {
        ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)a1 + 1344), 0, 0, 0x200u, v12, 0x65444856u, 0);
        *((_BYTE *)a1 + 1472) = 1;
      }
      *((_DWORD *)a1 + 314) = 0;
      *((_QWORD *)a1 + 155) = VhdmpiVdlExpansionWorkerRoutine;
      *((_QWORD *)a1 + 156) = (char *)a1 + 1224;
      *((_QWORD *)a1 + 153) = 0;
      DvInitializeWorkQueue((char *)a1 + 1192);
      *((_QWORD *)a1 + 150) = 0;
      *((_QWORD *)a1 + 151) = 0;
      *((_QWORD *)a1 + 161) = VhdmpiBlockingOperationWorkerRoutine;
      *((_DWORD *)a1 + 326) = 0;
      *((_QWORD *)a1 + 162) = (char *)a1 + 1272;
      *((_QWORD *)a1 + 159) = 0;
      DvInitializeWorkQueue((char *)a1 + 1264);
      if ( byte_14008E338 )
        *((_BYTE *)a1 + 1804) = 1;
      *((_BYTE *)a1 + 1805) = 1;
      Irp = VhdmpiInitializeSrbPartHandling(a1, v13);
      if ( Irp >= 0 )
      {
        v14 = *((_DWORD *)a1 + 52) >> 12;
        *((_BYTE *)a1 + 1806) = BYTE1(*((_DWORD *)a1 + 52)) & 1;
        v15 = *(_QWORD *)a1;
        *((_DWORD *)a1 + 291) = 3;
        *((_BYTE *)a1 + 1808) = v14 & 1;
        if ( *(_BYTE *)(v15 + 52) || (Irp = VhdmpiGetLastWriteTime((char *)a1 + 72, (char *)a1 + 1856), Irp >= 0) )
        {
          Irp = 0;
          goto LABEL_7;
        }
      }
    }
    else
    {
      v4 = 1;
    }
  }
  if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
    TraceEvents(
      "VhdmpiInitializeNewBackingStore",
      0x26Bu,
      v7,
      v8,
      "VhdmpiInitializeNewBackingStore: Failed. Status=0x%08x, ErrorId=%d",
      Irp,
      v4);
LABEL_7:
  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
    TraceEvents(
      "VhdmpiInitializeNewBackingStore",
      0x271u,
      v9,
      v10,
      "VhdmpiInitializeNewBackingStore: leaving... (0x%08x)",
      Irp);
  return (unsigned int)Irp;
}

```

## disassembly

```asm
0x1400e538c  push    rbx
0x1400e538e  push    rbp
0x1400e538f  push    rsi
0x1400e5390  push    rdi
0x1400e5391  sub     rsp, 48h
0x1400e5395  mov     r8, [rcx]
0x1400e5398  mov     rbx, rcx
0x1400e539b  xor     ebp, ebp
0x1400e539d  mov     eax, [r8+14h]
0x1400e53a1  mov     [rcx+40h], eax
0x1400e53a4  mov     eax, [r8+18h]
0x1400e53a8  mov     [rcx+44h], eax
0x1400e53ab  mov     [rcx+3CDh], dl
0x1400e53b1  call    ?RmwInitializePackage@@YAJPEAU_VHD_BACKING_STORE_HEADER@@@Z; RmwInitializePackage(_VHD_BACKING_STORE_HEADER *)
0x1400e53b6  mov     edi, eax
0x1400e53b8  test    eax, eax
0x1400e53ba  js      short loc_1400E53DB
0x1400e53bc  lea     r8, [rbx+408h]
0x1400e53c3  lea     rcx, [rbx+48h]
0x1400e53c7  call    VhdmpiFileWrapperAllocateIrp
0x1400e53cc  mov     edi, eax
0x1400e53ce  test    eax, eax
0x1400e53d0  jns     loc_1400E547D
0x1400e53d6  mov     ebp, 1
0x1400e53db  mov     eax, cs:dword_1400876D0
0x1400e53e1  mov     r8d, 2
0x1400e53e7  cmp     eax, r8d
0x1400e53ea  jbe     short loc_1400E5428
0x1400e53ec  lea     r9d, [r8+0Eh]
0x1400e53f0  mov     edx, r9d
0x1400e53f3  lea     rcx, dword_1400876D0
0x1400e53fa  call    _tlgKeywordOn
0x1400e53ff  test    al, al
0x1400e5401  jz      short loc_1400E5428
0x1400e5403  mov     dword ptr [rsp+68h+Depth], ebp
0x1400e5407  lea     rax, aVhdmpiinitiali_13; "VhdmpiInitializeNewBackingStore: Failed"...
0x1400e540e  mov     [rsp+68h+Tag], edi; char
0x1400e5412  lea     rcx, aVhdmpiinitiali_4; "VhdmpiInitializeNewBackingStore"
0x1400e5419  mov     edx, 26Bh; int
0x1400e541e  mov     [rsp+68h+Size], rax; char *
0x1400e5423  call    TraceEvents
0x1400e5428  mov     eax, cs:dword_1400876D0
0x1400e542e  mov     r8d, 5
0x1400e5434  cmp     eax, r8d
0x1400e5437  jbe     short loc_1400E5471
0x1400e5439  lea     r9d, [r8+3]
0x1400e543d  mov     edx, r9d
0x1400e5440  lea     rcx, dword_1400876D0
0x1400e5447  call    _tlgKeywordOn
0x1400e544c  test    al, al
0x1400e544e  jz      short loc_1400E5471
0x1400e5450  lea     rax, aVhdmpiinitiali_0; "VhdmpiInitializeNewBackingStore: leavin"...
0x1400e5457  mov     [rsp+68h+Tag], edi; char
0x1400e545b  mov     edx, 271h; int
0x1400e5460  mov     [rsp+68h+Size], rax; char *
0x1400e5465  lea     rcx, aVhdmpiinitiali_4; "VhdmpiInitializeNewBackingStore"
0x1400e546c  call    TraceEvents
0x1400e5471  mov     eax, edi
0x1400e5473  add     rsp, 48h
0x1400e5477  pop     rdi
0x1400e5478  pop     rsi
0x1400e5479  pop     rbp
0x1400e547a  pop     rbx
0x1400e547b  retn
0x1400e547d  lea     rcx, [rbx+360h]; Resource
0x1400e5484  call    cs:__imp_ExInitializeResourceLite
0x1400e548b  nop     dword ptr [rax+rax+00h]
0x1400e5490  lea     rcx, [rbx+460h]
0x1400e5497  mov     byte ptr [rbx+358h], 1
0x1400e549e  call    VhdmpiInitializePassiveLock
0x1400e54a3  lea     rcx, [rbx+3D0h]; Mutex
0x1400e54aa  xor     edx, edx; Level
0x1400e54ac  call    cs:__imp_KeInitializeMutex
0x1400e54b3  nop     dword ptr [rax+rax+00h]
0x1400e54b8  mov     eax, [rbx+0C0h]
0x1400e54be  mov     [rbx+428h], eax
0x1400e54c4  mov     rax, [rbx]
0x1400e54c7  mov     ecx, [rax+2Ch]
0x1400e54ca  test    ecx, ecx
0x1400e54cc  jz      short loc_1400E5509
0x1400e54ce  mov     edx, ecx
0x1400e54d0  xor     eax, eax
0x1400e54d2  mov     [rsp+68h+Depth], ax; Depth
0x1400e54d7  lea     rcx, [rbx+540h]; Lookaside
0x1400e54de  mov     [rsp+68h+Tag], 65444856h; Tag
0x1400e54e6  mov     r9d, 200h; Flags
0x1400e54ec  mov     [rsp+68h+Size], rdx; Size
0x1400e54f1  xor     r8d, r8d; Free
0x1400e54f4  xor     edx, edx; Allocate
0x1400e54f6  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400e54fd  nop     dword ptr [rax+rax+00h]
0x1400e5502  mov     byte ptr [rbx+5C0h], 1
0x1400e5509  lea     rax, [rbx+4C8h]
0x1400e5510  lea     rcx, VhdmpiVdlExpansionWorkerRoutine
0x1400e5517  mov     [rax+20h], ebp
0x1400e551a  mov     [rax+10h], rcx
0x1400e551e  lea     rcx, [rbx+4A8h]
0x1400e5525  mov     [rax+18h], rax
0x1400e5529  mov     [rax], rbp
0x1400e552c  call    DvInitializeWorkQueue
0x1400e5531  mov     [rbx+4B0h], rbp
0x1400e5538  lea     rax, [rbx+4F8h]
0x1400e553f  mov     [rbx+4B8h], rbp
0x1400e5546  lea     rcx, VhdmpiBlockingOperationWorkerRoutine
0x1400e554d  mov     [rax+10h], rcx
0x1400e5551  lea     rcx, [rbx+4F0h]
0x1400e5558  mov     [rax+20h], ebp
0x1400e555b  mov     [rax+18h], rax
0x1400e555f  mov     [rax], rbp
0x1400e5562  call    DvInitializeWorkQueue
0x1400e5567  cmp     cs:byte_14008E338, bpl
0x1400e556e  jz      short loc_1400E5577
0x1400e5570  mov     byte ptr [rbx+70Ch], 1
0x1400e5577  mov     rcx, rbx; struct _VHD_BACKING_STORE_HEADER *
0x1400e557a  mov     byte ptr [rbx+70Dh], 1
0x1400e5581  call    VhdmpiInitializeSrbPartHandling
0x1400e5586  mov     edi, eax
0x1400e5588  test    eax, eax
0x1400e558a  js      loc_1400E53DB
0x1400e5590  mov     edx, [rbx+0D0h]
0x1400e5596  mov     eax, edx
0x1400e5598  shr     eax, 8
0x1400e559b  and     al, 1
0x1400e559d  shr     edx, 0Ch
0x1400e55a0  mov     [rbx+70Eh], al
0x1400e55a6  and     dl, 1
0x1400e55a9  mov     rax, [rbx]
0x1400e55ac  mov     dword ptr [rbx+48Ch], 3
0x1400e55b6  mov     [rbx+710h], dl
0x1400e55bc  cmp     [rax+34h], bpl
0x1400e55c0  jnz     short loc_1400E55DC
0x1400e55c2  lea     rdx, [rbx+740h]
0x1400e55c9  lea     rcx, [rbx+48h]
0x1400e55cd  call    VhdmpiGetLastWriteTime
0x1400e55d2  mov     edi, eax
0x1400e55d4  test    eax, eax
0x1400e55d6  js      loc_1400E53DB
0x1400e55dc  xor     edi, edi
0x1400e55de  jmp     loc_1400E5428
```
