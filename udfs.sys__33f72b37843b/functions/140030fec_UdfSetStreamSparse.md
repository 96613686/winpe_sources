# UdfSetStreamSparse

- ea: `0x140030fec`
- end: `0x140031078`
- name: `UdfSetStreamSparse`
- size: `140`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14003e368`

## callees

- `0x140030d3c`
- `0x140030fec`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140031018`
- `ntoskrnl!ExAcquireFastMutex` at `0x140031018`
- `ntoskrnl!ExReleaseFastMutex` at `0x14003102c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14003102c`
- `ntoskrnl!CcFlushCache` at `0x14003104d`
- `ntoskrnl!CcFlushCache` at `0x14003104d`

## pseudocode

```c
__int64 __fastcall UdfSetStreamSparse(__int64 a1, __int64 a2)
{
  bool v2; // zf
  __int64 result; // rax
  struct _FAST_MUTEX *v6; // rcx
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+20h] [rbp-18h] BYREF

  v2 = (*(_DWORD *)(a2 + 212) & 0x2000) == 0;
  IoStatus = 0;
  if ( !v2 )
    return 0;
  ExAcquireFastMutex(*(PFAST_MUTEX *)(a2 + 48));
  v6 = *(struct _FAST_MUTEX **)(a2 + 48);
  *(_BYTE *)(a2 + 6) |= 4u;
  ExReleaseFastMutex(v6);
  CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(a2 + 424) + 8LL), 0, 0, &IoStatus);
  result = (unsigned int)IoStatus.Status;
  if ( IoStatus.Status >= 0 )
    return UdfCreateSparseReservationBitmap(a1, a2);
  return result;
}

```

## disassembly

```asm
0x140030fec  mov     [rsp+arg_0], rbx
0x140030ff1  push    rdi
0x140030ff2  sub     rsp, 30h
0x140030ff6  test    dword ptr [rdx+0D4h], 2000h
0x140031000  xorps   xmm0, xmm0
0x140031003  movups  xmmword ptr [rsp+38h+IoStatus], xmm0
0x140031008  mov     rbx, rdx
0x14003100b  mov     rdi, rcx
0x14003100e  jz      short loc_140031014
0x140031010  xor     eax, eax
0x140031012  jmp     short loc_14003106C
0x140031014  mov     rcx, [rdx+30h]; FastMutex
0x140031018  call    cs:__imp_ExAcquireFastMutex
0x14003101f  nop     dword ptr [rax+rax+00h]
0x140031024  mov     rcx, [rbx+30h]; FastMutex
0x140031028  or      byte ptr [rbx+6], 4
0x14003102c  call    cs:__imp_ExReleaseFastMutex
0x140031033  nop     dword ptr [rax+rax+00h]
0x140031038  mov     rcx, [rbx+1A8h]
0x14003103f  lea     r9, [rsp+38h+IoStatus]; IoStatus
0x140031044  add     rcx, 8; SectionObjectPointer
0x140031048  xor     r8d, r8d; Length
0x14003104b  xor     edx, edx; FileOffset
0x14003104d  call    cs:__imp_CcFlushCache
0x140031054  nop     dword ptr [rax+rax+00h]
0x140031059  mov     eax, dword ptr [rsp+38h+IoStatus]
0x14003105d  test    eax, eax
0x14003105f  js      short loc_14003106C
0x140031061  mov     rdx, rbx
0x140031064  mov     rcx, rdi
0x140031067  call    UdfCreateSparseReservationBitmap
0x14003106c  mov     rbx, [rsp+38h+arg_0]
0x140031071  add     rsp, 30h
0x140031075  pop     rdi
0x140031076  retn
```
