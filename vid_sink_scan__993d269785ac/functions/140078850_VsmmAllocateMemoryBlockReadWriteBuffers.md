# VsmmAllocateMemoryBlockReadWriteBuffers

- ea: `0x140078850`
- end: `0x140078aa8`
- name: `VsmmAllocateMemoryBlockReadWriteBuffers`
- size: `600`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140035698`

## callees

- `0x1400214dc`
- `0x14002f524`
- `0x140078850`
- `0x140078ab0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140078894`
- `ntoskrnl!PsGetCurrentProcess` at `0x140078894`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140078a88`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140078a88`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140078877`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140078877`

## string_xrefs

- `0x1400788c7`: `VsmmAllocateMemoryBlockReadWriteBuffers`
- `0x1400788f6`: `VsmmAllocateMemoryBlockReadWriteBuffers`
- `0x140078963`: `VsmmAllocateMemoryBlockReadWriteBuffers`
- `0x140078a15`: `VsmmAllocateMemoryBlockReadWriteBuffers`
- `0x140078a4a`: `VsmmAllocateMemoryBlockReadWriteBuffers`
- `0x140078a6a`: `VsmmAllocateMemoryBlockReadWriteBuffers`

## pseudocode

```c
__int64 __fastcall VsmmAllocateMemoryBlockReadWriteBuffers(__int64 a1, unsigned int a2, unsigned int a3, int a4)
{
  struct _FAST_MUTEX *v4; // r13
  __int64 v5; // r14
  __int64 v9; // rbx
  int v10; // ebx
  unsigned int v11; // ebp
  unsigned int v12; // r15d
  char v13; // cl
  unsigned int v14; // eax
  __int64 v15; // r12
  int v16; // esi
  __int64 v17; // r8
  __int64 v18; // rbp

  v4 = (struct _FAST_MUTEX *)(a1 + 9848);
  v5 = a2;
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a1 + 9848));
  if ( (*(_BYTE *)(a1 + 40) & 1) == 0 || (v9 = *(_QWORD *)(a1 + 10240), v9 != PsGetCurrentProcess()) )
  {
    v10 = -1073741790;
    v17 = 596;
    goto LABEL_27;
  }
  if ( !*(_BYTE *)(a1 + 9840) )
  {
    if ( (a4 & 0xFFFFFFFC) != 0 )
    {
      v10 = -1073741811;
      VidTraceErrorStatusInternal0(
        "VsmmAllocateMemoryBlockReadWriteBuffers",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
        613);
      goto LABEL_28;
    }
    if ( !(_DWORD)v5 || !a3 || (unsigned int)v5 > 0x40 || a3 > 0x100 )
    {
      v10 = -1073741811;
      VidTraceErrorStatusInternal0(
        "VsmmAllocateMemoryBlockReadWriteBuffers",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
        622);
      goto LABEL_28;
    }
    v11 = a3 << 12;
    v12 = v5 * v11;
    v13 = a4 & 2;
    v14 = 2 * v5 * v11;
    if ( (a4 & 2) == 0 )
      v14 = v5 * v11;
    if ( v14 > 0x1000000 )
    {
      v10 = -1073741811;
      VidTraceErrorStatusInternal0(
        "VsmmAllocateMemoryBlockReadWriteBuffers",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
        646);
      goto LABEL_28;
    }
    v15 = v11;
    v16 = (a4 & 1) + 1;
    if ( v13 )
    {
      v10 = VidManagedBufferListInitialize(a1 + 9904, v11, v5);
      if ( v10 < 0 )
      {
        v17 = 665;
        goto LABEL_27;
      }
      v16 |= 4u;
      v18 = v12;
      *(_QWORD *)(*(_QWORD *)(a1 + 1528) + 408LL) = v12;
    }
    else
    {
      v18 = v12;
    }
    v10 = VidManagedBufferListInitialize(a1 + 10064, v15, v5);
    if ( v10 >= 0 )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 1528) + 464LL) = v18;
      if ( !_InterlockedExchange((volatile __int32 *)(a1 + 8456), 1) )
      {
        *(_DWORD *)(a1 + 10224) = v16;
        v10 = 0;
        *(_BYTE *)(a1 + 9840) = 1;
        goto LABEL_29;
      }
      v10 = -1073741790;
      VidTraceErrorStatusInternal0(
        "VsmmAllocateMemoryBlockReadWriteBuffers",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
        700);
LABEL_28:
      VsmmpFreeMemoryBlockReadWriteBuffers(a1);
      goto LABEL_29;
    }
    v17 = 684;
LABEL_27:
    VidTraceErrorStatusInternal0(
      "VsmmAllocateMemoryBlockReadWriteBuffers",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
      v17);
    goto LABEL_28;
  }
  v10 = -1073740528;
  VidTraceErrorStatusInternal0(
    "VsmmAllocateMemoryBlockReadWriteBuffers",
    "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
    605);
LABEL_29:
  KeReleaseGuardedMutex(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140078850  push    rbx
0x140078852  push    rbp
0x140078853  push    rsi
0x140078854  push    rdi
0x140078855  push    r12
0x140078857  push    r13
0x140078859  push    r14
0x14007885b  push    r15
0x14007885d  sub     rsp, 28h
0x140078861  lea     r13, [rcx+2678h]
0x140078868  mov     r14d, edx
0x14007886b  mov     rdi, rcx
0x14007886e  mov     esi, r9d
0x140078871  mov     rcx, r13; Mutex
0x140078874  mov     ebp, r8d
0x140078877  call    cs:__imp_KeAcquireGuardedMutex
0x14007887e  nop     dword ptr [rax+rax+00h]
0x140078883  test    byte ptr [rdi+28h], 1
0x140078887  jz      loc_140078A58
0x14007888d  mov     rbx, [rdi+2800h]
0x140078894  call    cs:__imp_PsGetCurrentProcess
0x14007889b  nop     dword ptr [rax+rax+00h]
0x1400788a0  cmp     rbx, rax
0x1400788a3  jnz     loc_140078A58
0x1400788a9  cmp     byte ptr [rdi+2670h], 0
0x1400788b0  jz      short loc_1400788D8
0x1400788b2  mov     ebx, 0C0000510h
0x1400788b7  mov     r9d, ebx
0x1400788ba  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x1400788c1  mov     r8d, 25Dh
0x1400788c7  lea     rcx, aVsmmallocateme; "VsmmAllocateMemoryBlockReadWriteBuffers"
0x1400788ce  call    VidTraceErrorStatusInternal0
0x1400788d3  jmp     loc_140078A85
0x1400788d8  test    esi, 0FFFFFFFCh
0x1400788de  jz      short loc_140078907
0x1400788e0  mov     r9d, 0C000000Dh
0x1400788e6  mov     ebx, r9d
0x1400788e9  mov     r8d, 265h
0x1400788ef  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x1400788f6  lea     rcx, aVsmmallocateme; "VsmmAllocateMemoryBlockReadWriteBuffers"
0x1400788fd  call    VidTraceErrorStatusInternal0
0x140078902  jmp     loc_140078A7D
0x140078907  test    r14d, r14d
0x14007890a  jz      loc_140078A34
0x140078910  test    ebp, ebp
0x140078912  jz      loc_140078A34
0x140078918  cmp     r14d, 40h ; '@'
0x14007891c  ja      loc_140078A34
0x140078922  cmp     ebp, 100h
0x140078928  ja      loc_140078A34
0x14007892e  shl     ebp, 0Ch
0x140078931  mov     cl, sil
0x140078934  mov     r15d, ebp
0x140078937  imul    r15d, r14d
0x14007893b  and     cl, 2
0x14007893e  lea     eax, [r15+r15]
0x140078942  cmovz   eax, r15d
0x140078946  cmp     eax, 1000000h
0x14007894b  jbe     short loc_140078974
0x14007894d  mov     r9d, 0C000000Dh
0x140078953  mov     ebx, r9d
0x140078956  mov     r8d, 286h
0x14007895c  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x140078963  lea     rcx, aVsmmallocateme; "VsmmAllocateMemoryBlockReadWriteBuffers"
0x14007896a  call    VidTraceErrorStatusInternal0
0x14007896f  jmp     loc_140078A7D
0x140078974  movzx   esi, sil
0x140078978  and     esi, 1
0x14007897b  mov     r12d, ebp
0x14007897e  inc     esi
0x140078980  test    cl, cl
0x140078982  jz      short loc_1400789BD
0x140078984  lea     rcx, [rdi+26B0h]
0x14007898b  mov     r8, r14
0x14007898e  mov     edx, r12d
0x140078991  call    VidManagedBufferListInitialize
0x140078996  mov     ebx, eax
0x140078998  test    eax, eax
0x14007899a  jns     short loc_1400789A7
0x14007899c  mov     r8d, 299h
0x1400789a2  jmp     loc_140078A63
0x1400789a7  mov     rax, [rdi+5F8h]
0x1400789ae  or      esi, 4
0x1400789b1  mov     ebp, r15d
0x1400789b4  mov     [rax+198h], rbp
0x1400789bb  jmp     short loc_1400789C0
0x1400789bd  mov     ebp, r15d
0x1400789c0  lea     rcx, [rdi+2750h]
0x1400789c7  mov     r8, r14
0x1400789ca  mov     rdx, r12
0x1400789cd  call    VidManagedBufferListInitialize
0x1400789d2  mov     ebx, eax
0x1400789d4  test    eax, eax
0x1400789d6  jns     short loc_1400789E3
0x1400789d8  mov     r8d, 2ACh
0x1400789de  jmp     loc_140078A63
0x1400789e3  mov     rax, [rdi+5F8h]
0x1400789ea  mov     [rax+1D0h], rbp
0x1400789f1  mov     eax, 1
0x1400789f6  xchg    eax, [rdi+2108h]
0x1400789fc  test    eax, eax
0x1400789fe  jz      short loc_140078A23
0x140078a00  mov     ebx, 0C0000022h
0x140078a05  mov     r9d, ebx
0x140078a08  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x140078a0f  mov     r8d, 2BCh
0x140078a15  lea     rcx, aVsmmallocateme; "VsmmAllocateMemoryBlockReadWriteBuffers"
0x140078a1c  call    VidTraceErrorStatusInternal0
0x140078a21  jmp     short loc_140078A7D
0x140078a23  mov     [rdi+27F0h], esi
0x140078a29  xor     ebx, ebx
0x140078a2b  mov     byte ptr [rdi+2670h], 1
0x140078a32  jmp     short loc_140078A85
0x140078a34  mov     r9d, 0C000000Dh
0x140078a3a  mov     ebx, r9d
0x140078a3d  mov     r8d, 26Eh
0x140078a43  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x140078a4a  lea     rcx, aVsmmallocateme; "VsmmAllocateMemoryBlockReadWriteBuffers"
0x140078a51  call    VidTraceErrorStatusInternal0
0x140078a56  jmp     short loc_140078A7D
0x140078a58  mov     ebx, 0C0000022h
0x140078a5d  mov     r8d, 254h
0x140078a63  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x140078a6a  lea     rcx, aVsmmallocateme; "VsmmAllocateMemoryBlockReadWriteBuffers"
0x140078a71  mov     r9d, ebx
0x140078a74  call    VidTraceErrorStatusInternal0
0x140078a79  test    ebx, ebx
0x140078a7b  jns     short loc_140078A85
0x140078a7d  mov     rcx, rdi
0x140078a80  call    VsmmpFreeMemoryBlockReadWriteBuffers
0x140078a85  mov     rcx, r13; Mutex
0x140078a88  call    cs:__imp_KeReleaseGuardedMutex
0x140078a8f  nop     dword ptr [rax+rax+00h]
0x140078a94  mov     eax, ebx
0x140078a96  add     rsp, 28h
0x140078a9a  pop     r15
0x140078a9c  pop     r14
0x140078a9e  pop     r13
0x140078aa0  pop     r12
0x140078aa2  pop     rdi
0x140078aa3  pop     rsi
0x140078aa4  pop     rbp
0x140078aa5  pop     rbx
0x140078aa6  retn
```
