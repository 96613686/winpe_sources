# WimpFSFIntegrityBuildContext

- ea: `0x1400298c0`
- end: `0x140029a88`
- name: `WimpFSFIntegrityBuildContext`
- size: `456`
- prototype: `__int64 __usercall@<rax>(PVOID Object@<rcx>, __int64, __int64, char, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140028488`

## callees

- `0x1400119c0`
- `0x1400287cc`
- `0x1400298c0`

## import_xrefs

- `ntoskrnl!RtlInitializeBitMap` at `0x1400299d3`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400299d3`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400299b0`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400299b0`
- `ntoskrnl!RtlClearAllBits` at `0x1400299e2`
- `ntoskrnl!RtlClearAllBits` at `0x1400299e2`
- `ntoskrnl!ObfReferenceObject` at `0x140029a11`
- `ntoskrnl!ObfReferenceObject` at `0x140029a11`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002993c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002993c`

## pseudocode

```c
__int64 __fastcall WimpFSFIntegrityBuildContext(
        PVOID Object,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        char a7,
        _QWORD *a8)
{
  unsigned __int64 v9; // rsi
  unsigned __int64 v13; // rsi
  unsigned __int64 v14; // rax
  __int64 v15; // rax
  size_t v16; // rbx
  char *PoolWithTag; // rax
  char *v18; // rdi
  NTSTATUS v19; // ebx

  v9 = (a2 + 4095) & 0xFFFFFFFFFFFFF000uLL;
  if ( v9 < a2 )
    return (unsigned int)-1073741675;
  v13 = v9 >> 12;
  if ( v13 > 0xFFFFFFFF )
    return (unsigned int)-1073741675;
  v14 = (unsigned int)(v13 + 31);
  if ( (unsigned int)v14 < (unsigned int)v13 )
    return (unsigned int)-1073741675;
  v15 = (v14 >> 3) & 0x1FFFFFFC;
  v16 = v15 + 256;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, v15 + 256, 0x69637077u);
  v18 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, v16);
      goto LABEL_8;
    }
    return (unsigned int)-1073741801;
  }
  if ( !PoolWithTag )
    return (unsigned int)-1073741801;
LABEL_8:
  v19 = ExInitializeLookasideListEx(
          (PLOOKASIDE_LIST_EX)(v18 + 64),
          WimpFSFAllocateMultiHashContext,
          WimpFSFFreeMultiHashContext,
          PagedPool,
          0,
          (unsigned int)(g_WimIntegrityMultiHashObjectLength + 1352),
          0x69637077u,
          0);
  if ( v19 < 0 )
  {
    WimFSFDestroyIntegrity(v18);
  }
  else
  {
    RtlInitializeBitMap((PRTL_BITMAP)v18, (PULONG)v18 + 64, v13);
    RtlClearAllBits((PRTL_BITMAP)v18);
    *((_QWORD *)v18 + 4) = a5;
    *((_QWORD *)v18 + 5) = a6;
    *((_QWORD *)v18 + 2) = a3;
    *((_QWORD *)v18 + 3) = a4;
    ObfReferenceObject(Object);
    *((_QWORD *)v18 + 20) = Object;
    *((_QWORD *)v18 + 21) = a2;
    *((_QWORD *)v18 + 22) = 0;
    *((_DWORD *)v18 + 46) = a7 != 0 ? 2 : 0;
    *a8 = v18;
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1400298c0  push    rbx
0x1400298c2  push    rbp
0x1400298c3  push    rsi
0x1400298c4  push    rdi
0x1400298c5  push    r12
0x1400298c7  push    r13
0x1400298c9  push    r14
0x1400298cb  push    r15
0x1400298cd  sub     rsp, 48h
0x1400298d1  lea     rsi, [rdx+0FFFh]
0x1400298d8  mov     r12, r9
0x1400298db  and     rsi, 0FFFFFFFFFFFFF000h
0x1400298e2  mov     r13, r8
0x1400298e5  mov     r14, rdx
0x1400298e8  mov     r15, rcx
0x1400298eb  cmp     rsi, rdx
0x1400298ee  jb      loc_140029A6F
0x1400298f4  shr     rsi, 0Ch
0x1400298f8  mov     eax, 0FFFFFFFFh
0x1400298fd  cmp     rsi, rax
0x140029900  ja      loc_140029A6F
0x140029906  lea     eax, [rsi+1Fh]
0x140029909  cmp     eax, esi
0x14002990b  jb      loc_140029A6F
0x140029911  shr     rax, 3
0x140029915  and     eax, 1FFFFFFCh
0x14002991a  lea     rbx, [rax+100h]
0x140029921  cmp     rbx, 100h
0x140029928  jb      loc_140029A6F
0x14002992e  mov     r8d, 69637077h; Tag
0x140029934  mov     rdx, rbx; NumberOfBytes
0x140029937  mov     ecx, 600h; PoolType
0x14002993c  call    cs:__imp_ExAllocatePoolWithTag
0x140029943  nop     dword ptr [rax+rax+00h]
0x140029948  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14002994f  mov     rdi, rax
0x140029952  jnz     loc_140029A55
0x140029958  test    rax, rax
0x14002995b  jz      loc_140029A5E
0x140029961  mov     r8, rbx; Size
0x140029964  xor     edx, edx; Val
0x140029966  mov     rcx, rax; void *
0x140029969  call    memset
0x14002996e  mov     edx, cs:g_WimIntegrityMultiHashObjectLength
0x140029974  lea     rcx, [rdi+40h]; Lookaside
0x140029978  xor     r9d, r9d
0x14002997b  lea     r8, WimpFSFFreeMultiHashContext; Free
0x140029982  mov     [rsp+88h+Depth], r9w; Depth
0x140029988  add     edx, 548h
0x14002998e  mov     [rsp+88h+Tag], 69637077h; Tag
0x140029996  mov     rbp, rdi
0x140029999  mov     [rsp+88h+Size], rdx; Size
0x14002999e  lea     rdx, WimpFSFAllocateMultiHashContext; Allocate
0x1400299a5  mov     [rsp+88h+Flags], r9d; Flags
0x1400299aa  mov     r9d, 1; PoolType
0x1400299b0  call    cs:__imp_ExInitializeLookasideListEx
0x1400299b7  nop     dword ptr [rax+rax+00h]
0x1400299bc  mov     ebx, eax
0x1400299be  test    eax, eax
0x1400299c0  js      loc_140029A65
0x1400299c6  lea     rdx, [rdi+100h]; BitMapBuffer
0x1400299cd  mov     r8d, esi; SizeOfBitMap
0x1400299d0  mov     rcx, rdi; BitMapHeader
0x1400299d3  call    cs:__imp_RtlInitializeBitMap
0x1400299da  nop     dword ptr [rax+rax+00h]
0x1400299df  mov     rcx, rdi; BitMapHeader
0x1400299e2  call    cs:__imp_RtlClearAllBits
0x1400299e9  nop     dword ptr [rax+rax+00h]
0x1400299ee  mov     rcx, [rsp+88h+arg_20]
0x1400299f6  mov     [rdi+20h], rcx
0x1400299fa  mov     rcx, [rsp+88h+arg_28]
0x140029a02  mov     [rdi+28h], rcx
0x140029a06  mov     rcx, r15; Object
0x140029a09  mov     [rdi+10h], r13
0x140029a0d  mov     [rdi+18h], r12
0x140029a11  call    cs:__imp_ObfReferenceObject
0x140029a18  nop     dword ptr [rax+rax+00h]
0x140029a1d  neg     [rsp+88h+arg_30]
0x140029a24  mov     [rdi+0A0h], r15
0x140029a2b  sbb     eax, eax
0x140029a2d  mov     [rdi+0A8h], r14
0x140029a34  and     eax, 2
0x140029a37  mov     qword ptr [rdi+0B0h], 0
0x140029a42  mov     [rdi+0B8h], eax
0x140029a48  mov     rax, [rsp+88h+arg_38]
0x140029a50  mov     [rax], rdi
0x140029a53  jmp     short loc_140029A74
0x140029a55  test    rdi, rdi
0x140029a58  jnz     loc_14002996E
0x140029a5e  mov     ebx, 0C0000017h
0x140029a63  jmp     short loc_140029A74
0x140029a65  mov     rcx, rbp; P
0x140029a68  call    WimFSFDestroyIntegrity
0x140029a6d  jmp     short loc_140029A74
0x140029a6f  mov     ebx, 0C0000095h
0x140029a74  mov     eax, ebx
0x140029a76  add     rsp, 48h
0x140029a7a  pop     r15
0x140029a7c  pop     r14
0x140029a7e  pop     r13
0x140029a80  pop     r12
0x140029a82  pop     rdi
0x140029a83  pop     rsi
0x140029a84  pop     rbp
0x140029a85  pop     rbx
0x140029a86  retn
```
