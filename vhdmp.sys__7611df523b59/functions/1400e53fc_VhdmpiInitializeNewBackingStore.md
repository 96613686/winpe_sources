# VhdmpiInitializeNewBackingStore

- ea: `0x1400e53fc`
- end: `0x1400e5653`
- name: `VhdmpiInitializeNewBackingStore`
- size: `599`
- prototype: `__int64 __fastcall(struct _VHD_BACKING_STORE_HEADER *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x1400e565c`

## callees

- `0x140014270`
- `0x140016fb0`
- `0x140020cc0`
- `0x140023560`
- `0x140026a00`
- `0x14002ea78`
- `0x140035e94`
- `0x1400e53fc`
- `0x1400e781c`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400e5566`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400e5566`
- `ntoskrnl!KeInitializeMutex` at `0x1400e551c`
- `ntoskrnl!KeInitializeMutex` at `0x1400e551c`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400e54f4`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400e54f4`

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
  if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
    TraceEvents(
      "VhdmpiInitializeNewBackingStore",
      0x26Bu,
      v7,
      v8,
      "VhdmpiInitializeNewBackingStore: Failed. Status=0x%08x, ErrorId=%d",
      Irp,
      v4);
LABEL_7:
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
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
0x1400e53fc  push    rbx
0x1400e53fe  push    rbp
0x1400e53ff  push    rsi
0x1400e5400  push    rdi
0x1400e5401  sub     rsp, 48h
0x1400e5405  mov     r8, [rcx]
0x1400e5408  mov     rbx, rcx
0x1400e540b  xor     ebp, ebp
0x1400e540d  mov     eax, [r8+14h]
0x1400e5411  mov     [rcx+40h], eax
0x1400e5414  mov     eax, [r8+18h]
0x1400e5418  mov     [rcx+44h], eax
0x1400e541b  mov     [rcx+3CDh], dl
0x1400e5421  call    ?RmwInitializePackage@@YAJPEAU_VHD_BACKING_STORE_HEADER@@@Z; RmwInitializePackage(_VHD_BACKING_STORE_HEADER *)
0x1400e5426  mov     edi, eax
0x1400e5428  test    eax, eax
0x1400e542a  js      short loc_1400E544B
0x1400e542c  lea     r8, [rbx+408h]
0x1400e5433  lea     rcx, [rbx+48h]
0x1400e5437  call    VhdmpiFileWrapperAllocateIrp
0x1400e543c  mov     edi, eax
0x1400e543e  test    eax, eax
0x1400e5440  jns     loc_1400E54ED
0x1400e5446  mov     ebp, 1
0x1400e544b  mov     eax, cs:dword_140087708
0x1400e5451  mov     r8d, 2
0x1400e5457  cmp     eax, r8d
0x1400e545a  jbe     short loc_1400E5498
0x1400e545c  lea     r9d, [r8+0Eh]
0x1400e5460  mov     edx, r9d
0x1400e5463  lea     rcx, dword_140087708
0x1400e546a  call    _tlgKeywordOn
0x1400e546f  test    al, al
0x1400e5471  jz      short loc_1400E5498
0x1400e5473  mov     dword ptr [rsp+68h+Depth], ebp
0x1400e5477  lea     rax, aVhdmpiinitiali_13; "VhdmpiInitializeNewBackingStore: Failed"...
0x1400e547e  mov     [rsp+68h+Tag], edi; char
0x1400e5482  lea     rcx, aVhdmpiinitiali_4; "VhdmpiInitializeNewBackingStore"
0x1400e5489  mov     edx, 26Bh; int
0x1400e548e  mov     [rsp+68h+Size], rax; char *
0x1400e5493  call    TraceEvents
0x1400e5498  mov     eax, cs:dword_140087708
0x1400e549e  mov     r8d, 5
0x1400e54a4  cmp     eax, r8d
0x1400e54a7  jbe     short loc_1400E54E1
0x1400e54a9  lea     r9d, [r8+3]
0x1400e54ad  mov     edx, r9d
0x1400e54b0  lea     rcx, dword_140087708
0x1400e54b7  call    _tlgKeywordOn
0x1400e54bc  test    al, al
0x1400e54be  jz      short loc_1400E54E1
0x1400e54c0  lea     rax, aVhdmpiinitiali_0; "VhdmpiInitializeNewBackingStore: leavin"...
0x1400e54c7  mov     [rsp+68h+Tag], edi; char
0x1400e54cb  mov     edx, 271h; int
0x1400e54d0  mov     [rsp+68h+Size], rax; char *
0x1400e54d5  lea     rcx, aVhdmpiinitiali_4; "VhdmpiInitializeNewBackingStore"
0x1400e54dc  call    TraceEvents
0x1400e54e1  mov     eax, edi
0x1400e54e3  add     rsp, 48h
0x1400e54e7  pop     rdi
0x1400e54e8  pop     rsi
0x1400e54e9  pop     rbp
0x1400e54ea  pop     rbx
0x1400e54eb  retn
0x1400e54ed  lea     rcx, [rbx+360h]; Resource
0x1400e54f4  call    cs:__imp_ExInitializeResourceLite
0x1400e54fb  nop     dword ptr [rax+rax+00h]
0x1400e5500  lea     rcx, [rbx+460h]
0x1400e5507  mov     byte ptr [rbx+358h], 1
0x1400e550e  call    VhdmpiInitializePassiveLock
0x1400e5513  lea     rcx, [rbx+3D0h]; Mutex
0x1400e551a  xor     edx, edx; Level
0x1400e551c  call    cs:__imp_KeInitializeMutex
0x1400e5523  nop     dword ptr [rax+rax+00h]
0x1400e5528  mov     eax, [rbx+0C0h]
0x1400e552e  mov     [rbx+428h], eax
0x1400e5534  mov     rax, [rbx]
0x1400e5537  mov     ecx, [rax+2Ch]
0x1400e553a  test    ecx, ecx
0x1400e553c  jz      short loc_1400E5579
0x1400e553e  mov     edx, ecx
0x1400e5540  xor     eax, eax
0x1400e5542  mov     [rsp+68h+Depth], ax; Depth
0x1400e5547  lea     rcx, [rbx+540h]; Lookaside
0x1400e554e  mov     [rsp+68h+Tag], 65444856h; Tag
0x1400e5556  mov     r9d, 200h; Flags
0x1400e555c  mov     [rsp+68h+Size], rdx; Size
0x1400e5561  xor     r8d, r8d; Free
0x1400e5564  xor     edx, edx; Allocate
0x1400e5566  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400e556d  nop     dword ptr [rax+rax+00h]
0x1400e5572  mov     byte ptr [rbx+5C0h], 1
0x1400e5579  lea     rax, [rbx+4C8h]
0x1400e5580  lea     rcx, VhdmpiVdlExpansionWorkerRoutine
0x1400e5587  mov     [rax+20h], ebp
0x1400e558a  mov     [rax+10h], rcx
0x1400e558e  lea     rcx, [rbx+4A8h]
0x1400e5595  mov     [rax+18h], rax
0x1400e5599  mov     [rax], rbp
0x1400e559c  call    DvInitializeWorkQueue
0x1400e55a1  mov     [rbx+4B0h], rbp
0x1400e55a8  lea     rax, [rbx+4F8h]
0x1400e55af  mov     [rbx+4B8h], rbp
0x1400e55b6  lea     rcx, VhdmpiBlockingOperationWorkerRoutine
0x1400e55bd  mov     [rax+10h], rcx
0x1400e55c1  lea     rcx, [rbx+4F0h]
0x1400e55c8  mov     [rax+20h], ebp
0x1400e55cb  mov     [rax+18h], rax
0x1400e55cf  mov     [rax], rbp
0x1400e55d2  call    DvInitializeWorkQueue
0x1400e55d7  cmp     cs:byte_14008E338, bpl
0x1400e55de  jz      short loc_1400E55E7
0x1400e55e0  mov     byte ptr [rbx+70Ch], 1
0x1400e55e7  mov     rcx, rbx; struct _VHD_BACKING_STORE_HEADER *
0x1400e55ea  mov     byte ptr [rbx+70Dh], 1
0x1400e55f1  call    VhdmpiInitializeSrbPartHandling
0x1400e55f6  mov     edi, eax
0x1400e55f8  test    eax, eax
0x1400e55fa  js      loc_1400E544B
0x1400e5600  mov     edx, [rbx+0D0h]
0x1400e5606  mov     eax, edx
0x1400e5608  shr     eax, 8
0x1400e560b  and     al, 1
0x1400e560d  shr     edx, 0Ch
0x1400e5610  mov     [rbx+70Eh], al
0x1400e5616  and     dl, 1
0x1400e5619  mov     rax, [rbx]
0x1400e561c  mov     dword ptr [rbx+48Ch], 3
0x1400e5626  mov     [rbx+710h], dl
0x1400e562c  cmp     [rax+34h], bpl
0x1400e5630  jnz     short loc_1400E564C
0x1400e5632  lea     rdx, [rbx+740h]
0x1400e5639  lea     rcx, [rbx+48h]
0x1400e563d  call    VhdmpiGetLastWriteTime
0x1400e5642  mov     edi, eax
0x1400e5644  test    eax, eax
0x1400e5646  js      loc_1400E544B
0x1400e564c  xor     edi, edi
0x1400e564e  jmp     loc_1400E5498
```
