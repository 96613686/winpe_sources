# KmclpDisableClosedChannel

- ea: `0x14000cbc8`
- end: `0x14000cda9`
- name: `KmclpDisableClosedChannel`
- size: `481`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x14000abe0`
- `0x14000afe8`
- `0x14000b3d8`
- `0x14000bb70`
- `0x14001c758`

## callees

- `0x140009604`
- `0x14000a8c8`
- `0x14000a940`
- `0x14000ab90`
- `0x14000cbc8`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14000cc4c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000cc4c`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ccca`
- `ntoskrnl!ObfDereferenceObject` at `0x14000cced`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ccca`
- `ntoskrnl!ObfDereferenceObject` at `0x14000cced`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000cc16`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000cc16`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cc65`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cc65`
- `ntoskrnl!IoFreeIrp` at `0x14000cc7d`
- `ntoskrnl!IoFreeIrp` at `0x14000cc7d`

## pseudocode

```c
__int64 __fastcall KmclpDisableClosedChannel(ULONG_PTR BugCheckParameter2)
{
  void *v2; // rdi
  IRP *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x79u,
      (__int64)WPP_fa014546bb113ca58de70d4b381949e7_Traceguids,
      BugCheckParameter2);
  }
  v2 = 0;
  ExAcquireFastMutex(&KmclPerformanceCounterLock);
  if ( *(_QWORD *)(BugCheckParameter2 + 2168) )
  {
    v2 = *(void **)(BugCheckParameter2 + 2168);
    *(_QWORD *)(BugCheckParameter2 + 2168) = 0;
    *(_WORD *)(BugCheckParameter2 + 2160) = 0;
  }
  ExReleaseFastMutex(&KmclPerformanceCounterLock);
  if ( v2 )
    ExFreePoolWithTag(v2, 0x636D6B56u);
  v3 = *(IRP **)(BugCheckParameter2 + 2784);
  if ( v3 )
  {
    IoFreeIrp(v3);
    *(_QWORD *)(BugCheckParameter2 + 2784) = 0;
  }
  if ( *(_BYTE *)(BugCheckParameter2 + 2897) )
    KmclpFreeAllBounceBlocks(BugCheckParameter2);
  VmbusDropInterface(BugCheckParameter2);
  VmbusDropArrivalRemovalInterface(BugCheckParameter2);
  if ( !*(_BYTE *)(BugCheckParameter2 + 1985) )
  {
    v4 = *(void **)(BugCheckParameter2 + 2720);
    if ( v4 )
    {
      ObfDereferenceObject(v4);
      *(_QWORD *)(BugCheckParameter2 + 2720) = 0;
    }
    v5 = *(void **)(BugCheckParameter2 + 2728);
    if ( v5 )
    {
      ObfDereferenceObject(v5);
      *(_QWORD *)(BugCheckParameter2 + 2728) = 0;
    }
  }
  *(_OWORD *)(BugCheckParameter2 + 2752) = 0;
  *(_OWORD *)(BugCheckParameter2 + 2736) = 0;
  *(_DWORD *)(BugCheckParameter2 + 2200) = 0;
  v6 = _InterlockedIncrement((volatile signed __int32 *)(BugCheckParameter2 + 3296)) % 24;
  v7 = v6 + 207;
  v6 *= 2;
  *(_QWORD *)(BugCheckParameter2 + 8 * v6 + 3304) = MEMORY[0xFFFFF78000000008];
  *(_BYTE *)(BugCheckParameter2 + 16 * v7) = *(_BYTE *)(BugCheckParameter2 + 2200);
  *(_BYTE *)(BugCheckParameter2 + 8 * v6 + 3313) = *(_BYTE *)(BugCheckParameter2 + 2204);
  result = *(unsigned int *)(BugCheckParameter2 + 2216);
  *(_WORD *)(BugCheckParameter2 + 8 * v6 + 3314) = result;
  *(_WORD *)(BugCheckParameter2 + 8 * v6 + 3316) = 4506;
  return result;
}

```

## disassembly

```asm
0x14000cbc8  mov     [rsp+arg_0], rbx
0x14000cbcd  push    rdi
0x14000cbce  sub     rsp, 20h
0x14000cbd2  mov     rbx, rcx
0x14000cbd5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cbdc  lea     rax, WPP_GLOBAL_Control
0x14000cbe3  cmp     rcx, rax
0x14000cbe6  jz      short loc_14000CC0D
0x14000cbe8  mov     eax, [rcx+2Ch]
0x14000cbeb  test    al, 1
0x14000cbed  jz      short loc_14000CC0D
0x14000cbef  cmp     byte ptr [rcx+29h], 4
0x14000cbf3  jb      short loc_14000CC0D
0x14000cbf5  mov     rcx, [rcx+18h]
0x14000cbf9  lea     r8, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids
0x14000cc00  mov     edx, 79h ; 'y'
0x14000cc05  mov     r9, rbx
0x14000cc08  call    WPP_SF_q
0x14000cc0d  lea     rcx, KmclPerformanceCounterLock; FastMutex
0x14000cc14  xor     edi, edi
0x14000cc16  call    cs:__imp_ExAcquireFastMutex
0x14000cc1d  nop     dword ptr [rax+rax+00h]
0x14000cc22  mov     rax, [rbx+878h]
0x14000cc29  test    rax, rax
0x14000cc2c  jz      short loc_14000CC45
0x14000cc2e  mov     rdi, rax
0x14000cc31  mov     qword ptr [rbx+878h], 0
0x14000cc3c  xor     eax, eax
0x14000cc3e  mov     [rbx+870h], ax
0x14000cc45  lea     rcx, KmclPerformanceCounterLock; FastMutex
0x14000cc4c  call    cs:__imp_ExReleaseFastMutex
0x14000cc53  nop     dword ptr [rax+rax+00h]
0x14000cc58  test    rdi, rdi
0x14000cc5b  jz      short loc_14000CC71
0x14000cc5d  mov     edx, 636D6B56h; Tag
0x14000cc62  mov     rcx, rdi; P
0x14000cc65  call    cs:__imp_ExFreePoolWithTag
0x14000cc6c  nop     dword ptr [rax+rax+00h]
0x14000cc71  mov     rcx, [rbx+0AE0h]; Irp
0x14000cc78  test    rcx, rcx
0x14000cc7b  jz      short loc_14000CC94
0x14000cc7d  call    cs:__imp_IoFreeIrp
0x14000cc84  nop     dword ptr [rax+rax+00h]
0x14000cc89  mov     qword ptr [rbx+0AE0h], 0
0x14000cc94  cmp     byte ptr [rbx+0B51h], 0
0x14000cc9b  jz      short loc_14000CCA5
0x14000cc9d  mov     rcx, rbx; BugCheckParameter2
0x14000cca0  call    KmclpFreeAllBounceBlocks
0x14000cca5  mov     rcx, rbx
0x14000cca8  call    VmbusDropInterface
0x14000ccad  mov     rcx, rbx
0x14000ccb0  call    VmbusDropArrivalRemovalInterface
0x14000ccb5  cmp     byte ptr [rbx+7C1h], 0
0x14000ccbc  jnz     short loc_14000CD04
0x14000ccbe  mov     rcx, [rbx+0AA0h]; Object
0x14000ccc5  test    rcx, rcx
0x14000ccc8  jz      short loc_14000CCE1
0x14000ccca  call    cs:__imp_ObfDereferenceObject
0x14000ccd1  nop     dword ptr [rax+rax+00h]
0x14000ccd6  mov     qword ptr [rbx+0AA0h], 0
0x14000cce1  mov     rcx, [rbx+0AA8h]; Object
0x14000cce8  test    rcx, rcx
0x14000cceb  jz      short loc_14000CD04
0x14000cced  call    cs:__imp_ObfDereferenceObject
0x14000ccf4  nop     dword ptr [rax+rax+00h]
0x14000ccf9  mov     qword ptr [rbx+0AA8h], 0
0x14000cd04  xorps   xmm0, xmm0
0x14000cd07  xorps   xmm1, xmm1
0x14000cd0a  movups  xmmword ptr [rbx+0AC0h], xmm0
0x14000cd11  mov     ecx, 1
0x14000cd16  movups  xmmword ptr [rbx+0AB0h], xmm1
0x14000cd1d  mov     dword ptr [rbx+898h], 0
0x14000cd27  lock xadd [rbx+0CE0h], ecx
0x14000cd2f  inc     ecx
0x14000cd31  mov     eax, 2AAAAAABh
0x14000cd36  imul    ecx
0x14000cd38  sar     edx, 2
0x14000cd3b  mov     eax, edx
0x14000cd3d  shr     eax, 1Fh
0x14000cd40  add     edx, eax
0x14000cd42  lea     eax, [rdx+rdx*2]
0x14000cd45  shl     eax, 3
0x14000cd48  sub     ecx, eax
0x14000cd4a  mov     rax, ds:0FFFFF78000000008h
0x14000cd54  movsxd  rcx, ecx
0x14000cd57  mov     rdx, rcx
0x14000cd5a  add     rcx, 0CFh
0x14000cd61  add     rdx, rdx
0x14000cd64  add     rcx, rcx
0x14000cd67  mov     [rbx+rdx*8+0CE8h], rax
0x14000cd6f  mov     al, [rbx+898h]
0x14000cd75  mov     [rbx+rcx*8], al
0x14000cd78  mov     al, [rbx+89Ch]
0x14000cd7e  mov     [rbx+rdx*8+0CF1h], al
0x14000cd85  mov     eax, [rbx+8A8h]
0x14000cd8b  mov     [rbx+rdx*8+0CF2h], ax
0x14000cd93  mov     word ptr [rbx+rdx*8+0CF4h], 119Ah
0x14000cd9d  mov     rbx, [rsp+28h+arg_0]
0x14000cda2  add     rsp, 20h
0x14000cda6  pop     rdi
0x14000cda7  retn
```
