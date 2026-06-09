# OncRpcBufMgrpAllocateDescriptorFromLLForUserSuppliedBuffer

- ea: `0x140001804`
- end: `0x140001917`
- name: `OncRpcBufMgrpAllocateDescriptorFromLLForUserSuppliedBuffer`
- size: `275`
- prototype: `_DWORD *__fastcall(__int64, char *, ULONG, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140001100`

## callees

- `0x140001804`
- `0x140002060`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400018f8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400018f8`
- `ntoskrnl!IoFreeMdl` at `0x1400018e0`
- `ntoskrnl!IoFreeMdl` at `0x1400018e0`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140001863`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140001863`
- `ntoskrnl!IoAllocateMdl` at `0x140001831`
- `ntoskrnl!IoAllocateMdl` at `0x140001831`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001847`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001847`

## pseudocode

```c
_DWORD *__fastcall OncRpcBufMgrpAllocateDescriptorFromLLForUserSuppliedBuffer(
        __int64 a1,
        char *a2,
        ULONG a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v6; // rsi
  struct _MDL *Mdl; // rdi
  _DWORD *v11; // rax
  _DWORD *v12; // rbx

  v6 = a3;
  Mdl = IoAllocateMdl(a2, a3, 0, 0, 0);
  v11 = ExAllocateFromNPagedLookasideList(&stru_14001A600);
  v12 = v11;
  if ( Mdl )
  {
    if ( v11 )
    {
      MmBuildMdlForNonPagedPool(Mdl);
      ++qword_14001A6A0;
      ++dword_14001A6F0;
      ++dword_14001A6F8;
      OncRpcBufpDescriptorInit(v12, a1, a4);
      v12[20] |= 0x12u;
      *((_QWORD *)v12 + 8) = &a2[v6];
      *((_QWORD *)v12 + 5) = a5;
      *((_QWORD *)v12 + 6) = a6;
      *((_QWORD *)v12 + 11) = Mdl;
      *((_QWORD *)v12 + 7) = a2;
      v12[18] = v6;
      v12[19] = v6;
      *((_QWORD *)v12 + 12) = 0;
      return v12;
    }
  }
  else if ( v11 )
  {
    ExFreeToNPagedLookasideList(&stru_14001A600, v11);
    return 0;
  }
  ++qword_14001A6A8;
  if ( Mdl )
    IoFreeMdl(Mdl);
  return v12;
}

```

## disassembly

```asm
0x140001804  push    rbx
0x140001806  push    rbp
0x140001807  push    rsi
0x140001808  push    rdi
0x140001809  push    r14
0x14000180b  push    r15
0x14000180d  sub     rsp, 38h
0x140001811  mov     esi, r8d
0x140001814  mov     rbp, rdx
0x140001817  mov     r14, r9
0x14000181a  mov     [rsp+68h+Irp], 0; Irp
0x140001823  mov     r15, rcx
0x140001826  mov     edx, esi; Length
0x140001828  mov     rcx, rbp; VirtualAddress
0x14000182b  xor     r9d, r9d; ChargeQuota
0x14000182e  xor     r8d, r8d; SecondaryBuffer
0x140001831  call    cs:__imp_IoAllocateMdl
0x140001838  nop     dword ptr [rax+rax+00h]
0x14000183d  lea     rcx, stru_14001A600; Lookaside
0x140001844  mov     rdi, rax
0x140001847  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000184e  nop     dword ptr [rax+rax+00h]
0x140001853  mov     rbx, rax
0x140001856  test    rdi, rdi
0x140001859  jz      short loc_1400018CC
0x14000185b  test    rax, rax
0x14000185e  jz      short loc_1400018D1
0x140001860  mov     rcx, rdi; MemoryDescriptorList
0x140001863  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14000186a  nop     dword ptr [rax+rax+00h]
0x14000186f  inc     cs:qword_14001A6A0
0x140001876  mov     r8, r14
0x140001879  inc     cs:dword_14001A6F0
0x14000187f  mov     rdx, r15
0x140001882  inc     cs:dword_14001A6F8
0x140001888  mov     rcx, rbx
0x14000188b  call    OncRpcBufpDescriptorInit
0x140001890  or      dword ptr [rbx+50h], 12h
0x140001894  lea     rax, [rsi+rbp]
0x140001898  mov     [rbx+40h], rax
0x14000189c  mov     rax, [rsp+68h+arg_20]
0x1400018a4  mov     [rbx+28h], rax
0x1400018a8  mov     rax, [rsp+68h+arg_28]
0x1400018b0  mov     [rbx+30h], rax
0x1400018b4  mov     [rbx+58h], rdi
0x1400018b8  mov     [rbx+38h], rbp
0x1400018bc  mov     [rbx+48h], esi
0x1400018bf  mov     [rbx+4Ch], esi
0x1400018c2  mov     qword ptr [rbx+60h], 0
0x1400018ca  jmp     short loc_140001906
0x1400018cc  test    rbx, rbx
0x1400018cf  jnz     short loc_1400018EE
0x1400018d1  inc     cs:qword_14001A6A8
0x1400018d8  test    rdi, rdi
0x1400018db  jz      short loc_140001906
0x1400018dd  mov     rcx, rdi; Mdl
0x1400018e0  call    cs:__imp_IoFreeMdl
0x1400018e7  nop     dword ptr [rax+rax+00h]
0x1400018ec  jmp     short loc_140001906
0x1400018ee  mov     rdx, rbx; Entry
0x1400018f1  lea     rcx, stru_14001A600; Lookaside
0x1400018f8  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400018ff  nop     dword ptr [rax+rax+00h]
0x140001904  xor     ebx, ebx
0x140001906  mov     rax, rbx
0x140001909  add     rsp, 38h
0x14000190d  pop     r15
0x14000190f  pop     r14
0x140001911  pop     rdi
0x140001912  pop     rsi
0x140001913  pop     rbp
0x140001914  pop     rbx
0x140001915  retn
```
