# VsmmAllocateMemoryBlockReadWriteBuffers

- ea: `0x14007972c`
- end: `0x140079984`
- name: `VsmmAllocateMemoryBlockReadWriteBuffers`
- size: `600`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140035708`

## callees

- `0x140021aec`
- `0x14002f724`
- `0x14007972c`
- `0x14007998c`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140079770`
- `ntoskrnl!PsGetCurrentProcess` at `0x140079770`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140079964`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140079964`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140079753`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140079753`

## string_xrefs

- `0x1400797a3`: `VsmmAllocateMemoryBlockReadWriteBuffers`
- `0x1400797d2`: `VsmmAllocateMemoryBlockReadWriteBuffers`
- `0x14007983f`: `VsmmAllocateMemoryBlockReadWriteBuffers`
- `0x1400798f1`: `VsmmAllocateMemoryBlockReadWriteBuffers`
- `0x140079926`: `VsmmAllocateMemoryBlockReadWriteBuffers`
- `0x140079946`: `VsmmAllocateMemoryBlockReadWriteBuffers`

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
        613,
        3221225485LL);
      goto LABEL_28;
    }
    if ( !(_DWORD)v5 || !a3 || (unsigned int)v5 > 0x40 || a3 > 0x100 )
    {
      v10 = -1073741811;
      VidTraceErrorStatusInternal0(
        "VsmmAllocateMemoryBlockReadWriteBuffers",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
        622,
        3221225485LL);
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
        646,
        3221225485LL);
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
        700,
        3221225506LL);
LABEL_28:
      VsmmpFreeMemoryBlockReadWriteBuffers(a1);
      goto LABEL_29;
    }
    v17 = 684;
LABEL_27:
    VidTraceErrorStatusInternal0(
      "VsmmAllocateMemoryBlockReadWriteBuffers",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
      v17,
      (unsigned int)v10);
    goto LABEL_28;
  }
  v10 = -1073740528;
  VidTraceErrorStatusInternal0(
    "VsmmAllocateMemoryBlockReadWriteBuffers",
    "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
    605,
    3221226768LL);
LABEL_29:
  KeReleaseGuardedMutex(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14007972c  push    rbx
0x14007972e  push    rbp
0x14007972f  push    rsi
0x140079730  push    rdi
0x140079731  push    r12
0x140079733  push    r13
0x140079735  push    r14
0x140079737  push    r15
0x140079739  sub     rsp, 28h
0x14007973d  lea     r13, [rcx+2678h]
0x140079744  mov     r14d, edx
0x140079747  mov     rdi, rcx
0x14007974a  mov     esi, r9d
0x14007974d  mov     rcx, r13; Mutex
0x140079750  mov     ebp, r8d
0x140079753  call    cs:__imp_KeAcquireGuardedMutex
0x14007975a  nop     dword ptr [rax+rax+00h]
0x14007975f  test    byte ptr [rdi+28h], 1
0x140079763  jz      loc_140079934
0x140079769  mov     rbx, [rdi+2800h]
0x140079770  call    cs:__imp_PsGetCurrentProcess
0x140079777  nop     dword ptr [rax+rax+00h]
0x14007977c  cmp     rbx, rax
0x14007977f  jnz     loc_140079934
0x140079785  cmp     byte ptr [rdi+2670h], 0
0x14007978c  jz      short loc_1400797B4
0x14007978e  mov     ebx, 0C0000510h
0x140079793  mov     r9d, ebx
0x140079796  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14007979d  mov     r8d, 25Dh
0x1400797a3  lea     rcx, aVsmmallocateme; "VsmmAllocateMemoryBlockReadWriteBuffers"
0x1400797aa  call    VidTraceErrorStatusInternal0
0x1400797af  jmp     loc_140079961
0x1400797b4  test    esi, 0FFFFFFFCh
0x1400797ba  jz      short loc_1400797E3
0x1400797bc  mov     r9d, 0C000000Dh
0x1400797c2  mov     ebx, r9d
0x1400797c5  mov     r8d, 265h
0x1400797cb  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x1400797d2  lea     rcx, aVsmmallocateme; "VsmmAllocateMemoryBlockReadWriteBuffers"
0x1400797d9  call    VidTraceErrorStatusInternal0
0x1400797de  jmp     loc_140079959
0x1400797e3  test    r14d, r14d
0x1400797e6  jz      loc_140079910
0x1400797ec  test    ebp, ebp
0x1400797ee  jz      loc_140079910
0x1400797f4  cmp     r14d, 40h ; '@'
0x1400797f8  ja      loc_140079910
0x1400797fe  cmp     ebp, 100h
0x140079804  ja      loc_140079910
0x14007980a  shl     ebp, 0Ch
0x14007980d  mov     cl, sil
0x140079810  mov     r15d, ebp
0x140079813  imul    r15d, r14d
0x140079817  and     cl, 2
0x14007981a  lea     eax, [r15+r15]
0x14007981e  cmovz   eax, r15d
0x140079822  cmp     eax, 1000000h
0x140079827  jbe     short loc_140079850
0x140079829  mov     r9d, 0C000000Dh
0x14007982f  mov     ebx, r9d
0x140079832  mov     r8d, 286h
0x140079838  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14007983f  lea     rcx, aVsmmallocateme; "VsmmAllocateMemoryBlockReadWriteBuffers"
0x140079846  call    VidTraceErrorStatusInternal0
0x14007984b  jmp     loc_140079959
0x140079850  movzx   esi, sil
0x140079854  and     esi, 1
0x140079857  mov     r12d, ebp
0x14007985a  inc     esi
0x14007985c  test    cl, cl
0x14007985e  jz      short loc_140079899
0x140079860  lea     rcx, [rdi+26B0h]
0x140079867  mov     r8, r14
0x14007986a  mov     edx, r12d
0x14007986d  call    VidManagedBufferListInitialize
0x140079872  mov     ebx, eax
0x140079874  test    eax, eax
0x140079876  jns     short loc_140079883
0x140079878  mov     r8d, 299h
0x14007987e  jmp     loc_14007993F
0x140079883  mov     rax, [rdi+5F8h]
0x14007988a  or      esi, 4
0x14007988d  mov     ebp, r15d
0x140079890  mov     [rax+198h], rbp
0x140079897  jmp     short loc_14007989C
0x140079899  mov     ebp, r15d
0x14007989c  lea     rcx, [rdi+2750h]
0x1400798a3  mov     r8, r14
0x1400798a6  mov     rdx, r12
0x1400798a9  call    VidManagedBufferListInitialize
0x1400798ae  mov     ebx, eax
0x1400798b0  test    eax, eax
0x1400798b2  jns     short loc_1400798BF
0x1400798b4  mov     r8d, 2ACh
0x1400798ba  jmp     loc_14007993F
0x1400798bf  mov     rax, [rdi+5F8h]
0x1400798c6  mov     [rax+1D0h], rbp
0x1400798cd  mov     eax, 1
0x1400798d2  xchg    eax, [rdi+2108h]
0x1400798d8  test    eax, eax
0x1400798da  jz      short loc_1400798FF
0x1400798dc  mov     ebx, 0C0000022h
0x1400798e1  mov     r9d, ebx
0x1400798e4  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x1400798eb  mov     r8d, 2BCh
0x1400798f1  lea     rcx, aVsmmallocateme; "VsmmAllocateMemoryBlockReadWriteBuffers"
0x1400798f8  call    VidTraceErrorStatusInternal0
0x1400798fd  jmp     short loc_140079959
0x1400798ff  mov     [rdi+27F0h], esi
0x140079905  xor     ebx, ebx
0x140079907  mov     byte ptr [rdi+2670h], 1
0x14007990e  jmp     short loc_140079961
0x140079910  mov     r9d, 0C000000Dh
0x140079916  mov     ebx, r9d
0x140079919  mov     r8d, 26Eh
0x14007991f  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x140079926  lea     rcx, aVsmmallocateme; "VsmmAllocateMemoryBlockReadWriteBuffers"
0x14007992d  call    VidTraceErrorStatusInternal0
0x140079932  jmp     short loc_140079959
0x140079934  mov     ebx, 0C0000022h
0x140079939  mov     r8d, 254h
0x14007993f  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x140079946  lea     rcx, aVsmmallocateme; "VsmmAllocateMemoryBlockReadWriteBuffers"
0x14007994d  mov     r9d, ebx
0x140079950  call    VidTraceErrorStatusInternal0
0x140079955  test    ebx, ebx
0x140079957  jns     short loc_140079961
0x140079959  mov     rcx, rdi
0x14007995c  call    VsmmpFreeMemoryBlockReadWriteBuffers
0x140079961  mov     rcx, r13; Mutex
0x140079964  call    cs:__imp_KeReleaseGuardedMutex
0x14007996b  nop     dword ptr [rax+rax+00h]
0x140079970  mov     eax, ebx
0x140079972  add     rsp, 28h
0x140079976  pop     r15
0x140079978  pop     r14
0x14007997a  pop     r13
0x14007997c  pop     r12
0x14007997e  pop     rdi
0x14007997f  pop     rsi
0x140079980  pop     rbp
0x140079981  pop     rbx
0x140079982  retn
```
