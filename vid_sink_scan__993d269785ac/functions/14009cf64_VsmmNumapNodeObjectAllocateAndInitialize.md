# VsmmNumapNodeObjectAllocateAndInitialize

- ea: `0x14009cf64`
- end: `0x14009d0c5`
- name: `VsmmNumapNodeObjectAllocateAndInitialize`
- size: `353`
- prototype: `__int64 __fastcall(__int64, unsigned __int8)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14009d8a4`

## callees

- `0x1400211f0`
- `0x140038630`
- `0x140075f58`
- `0x14009c624`
- `0x14009cf64`
- `0x14009d0cc`
- `0x1400ed7c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14009d0a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009d0a9`
- `ntoskrnl!ExAllocatePool2` at `0x14009cfc8`
- `ntoskrnl!ExAllocatePool2` at `0x14009cfc8`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14009d055`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14009d055`

## pseudocode

```c
__int64 __fastcall VsmmNumapNodeObjectAllocateAndInitialize(__int64 a1, unsigned __int8 a2, __int64 a3)
{
  __int64 v3; // rsi
  int i; // edi
  int WorkspaceSize; // ebx
  __int64 Pool2; // rax
  __int64 v8; // rdi
  __int64 j; // rbx
  _BYTE v11[12]; // [rsp+8Ch] [rbp+14h] BYREF

  v3 = a2;
  *(_QWORD *)&v11[4] = 0;
  for ( i = 1; i < 3; ++i )
  {
    WorkspaceSize = VmCompressGetWorkspaceSize(i != 1, (ULONG *)&v11[4 * i], a3);
    if ( WorkspaceSize < 0 )
      return (unsigned int)WorkspaceSize;
  }
  Pool2 = ExAllocatePool2(64, 432, 1833788502);
  v8 = Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)Pool2 = 1634563406;
    *(_BYTE *)(Pool2 + 4) = v3;
    VidStatisticsDataInitialize((struct _KEVENT *)(Pool2 + 72));
    for ( j = 1; j != 3; ++j )
      ExInitializeLookasideListEx(
        (PLOOKASIDE_LIST_EX)(v8 + 224 + 96 * (j - 1)),
        0,
        0,
        PagedPool,
        0,
        *(unsigned int *)&v11[4 * j],
        0x6D4D6456u,
        0);
    WorkspaceSize = VidStatisticsDataSetup((PFAST_MUTEX)(v8 + 72), 13);
    if ( WorkspaceSize < 0 || (WorkspaceSize = VsmmNumapBackingSetup(v8), WorkspaceSize < 0) )
    {
      VsmmNumapNodeObjectTeardown(v8);
      ExFreePoolWithTag((PVOID)v8, 0x6D4D6456u);
    }
    else
    {
      WorkspaceSize = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 264) + 8 * v3) = v8;
    }
  }
  else
  {
    WorkspaceSize = -1073741670;
    VidTraceErrorInternal0("VsmmNumapNodeObjectAllocateAndInitialize", "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c", 2082);
  }
  return (unsigned int)WorkspaceSize;
}

```

## disassembly

```asm
0x14009cf64  mov     rax, rsp
0x14009cf67  push    rbx
0x14009cf68  push    rbp
0x14009cf69  push    rsi
0x14009cf6a  push    rdi
0x14009cf6b  push    r14
0x14009cf6d  push    r15
0x14009cf6f  sub     rsp, 48h
0x14009cf73  movzx   esi, dl
0x14009cf76  mov     r14, rcx
0x14009cf79  mov     qword ptr [rax+18h], 0
0x14009cf81  mov     edi, 1
0x14009cf86  cmp     edi, 3
0x14009cf89  jge     short loc_14009CFB8
0x14009cf8b  xor     ecx, ecx
0x14009cf8d  lea     eax, [rdi-1]
0x14009cf90  movsxd  rdx, eax
0x14009cf93  cmp     edi, 1
0x14009cf96  lea     rax, [rsp+78h+arg_C+4]
0x14009cf9e  setnz   cl
0x14009cfa1  lea     rdx, [rax+rdx*4]
0x14009cfa5  call    VmCompressGetWorkspaceSize
0x14009cfaa  mov     ebx, eax
0x14009cfac  test    eax, eax
0x14009cfae  js      loc_14009D0B5
0x14009cfb4  inc     edi
0x14009cfb6  jmp     short loc_14009CF86
0x14009cfb8  mov     edx, 1B0h
0x14009cfbd  mov     ecx, 40h ; '@'
0x14009cfc2  mov     r8d, 6D4D6456h
0x14009cfc8  call    cs:__imp_ExAllocatePool2
0x14009cfcf  nop     dword ptr [rax+rax+00h]
0x14009cfd4  mov     rdi, rax
0x14009cfd7  test    rax, rax
0x14009cfda  jnz     short loc_14009CFFF
0x14009cfdc  mov     ebx, 0C000009Ah
0x14009cfe1  mov     r8d, 822h
0x14009cfe7  lea     rdx, aOnecoreVmVidSy_58; "onecore\\vm\\vid\\sys\\vsmm\\vsmmnuma.c"
0x14009cfee  lea     rcx, aVsmmnumapnodeo_0; "VsmmNumapNodeObjectAllocateAndInitializ"...
0x14009cff5  call    VidTraceErrorInternal0
0x14009cffa  jmp     loc_14009D0B5
0x14009cfff  lea     rcx, [rax+48h]
0x14009d003  mov     dword ptr [rax], 616D754Eh
0x14009d009  mov     [rax+4], sil
0x14009d00d  call    VidStatisticsDataInitialize
0x14009d012  lea     r15, [rdi+0E0h]
0x14009d019  mov     ebx, 1
0x14009d01e  mov     edx, dword ptr [rsp+rbx*4+78h+arg_C]
0x14009d025  lea     rcx, [rbx-1]
0x14009d029  xor     eax, eax
0x14009d02b  lea     rcx, [rcx+rcx*2]
0x14009d02f  mov     [rsp+78h+Depth], ax; Depth
0x14009d034  xor     r8d, r8d; Free
0x14009d037  shl     rcx, 5
0x14009d03b  mov     [rsp+78h+Tag], 6D4D6456h; Tag
0x14009d043  add     rcx, r15; Lookaside
0x14009d046  mov     [rsp+78h+Size], rdx; Size
0x14009d04b  lea     r9d, [rax+1]; PoolType
0x14009d04f  xor     edx, edx; Allocate
0x14009d051  mov     [rsp+78h+Flags], eax; Flags
0x14009d055  call    cs:__imp_ExInitializeLookasideListEx
0x14009d05c  nop     dword ptr [rax+rax+00h]
0x14009d061  inc     rbx
0x14009d064  cmp     rbx, 3
0x14009d068  jnz     short loc_14009D01E
0x14009d06a  lea     edx, [rbx+0Ah]
0x14009d06d  lea     rcx, [rdi+48h]; FastMutex
0x14009d071  call    VidStatisticsDataSetup
0x14009d076  mov     ebx, eax
0x14009d078  test    eax, eax
0x14009d07a  js      short loc_14009D099
0x14009d07c  mov     rcx, rdi
0x14009d07f  call    VsmmNumapBackingSetup
0x14009d084  mov     ebx, eax
0x14009d086  test    eax, eax
0x14009d088  js      short loc_14009D099
0x14009d08a  mov     rax, [r14+108h]
0x14009d091  xor     ebx, ebx
0x14009d093  mov     [rax+rsi*8], rdi
0x14009d097  jmp     short loc_14009D0B5
0x14009d099  mov     rcx, rdi
0x14009d09c  call    VsmmNumapNodeObjectTeardown
0x14009d0a1  mov     edx, 6D4D6456h; Tag
0x14009d0a6  mov     rcx, rdi; P
0x14009d0a9  call    cs:__imp_ExFreePoolWithTag
0x14009d0b0  nop     dword ptr [rax+rax+00h]
0x14009d0b5  mov     eax, ebx
0x14009d0b7  add     rsp, 48h
0x14009d0bb  pop     r15
0x14009d0bd  pop     r14
0x14009d0bf  pop     rdi
0x14009d0c0  pop     rsi
0x14009d0c1  pop     rbp
0x14009d0c2  pop     rbx
0x14009d0c3  retn
```
