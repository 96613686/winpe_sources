# TmpProcessNotificationResponse

- ea: `0x14001a000`
- end: `0x14001a22d`
- name: `TmpProcessNotificationResponse`
- size: `557`
- prototype: `__int64 __usercall@<rax>(PVOID Object@<rcx>, __int64, __int64, __int64, __int64)`
- caller_count: `8`
- callee_count: `6`
- tags: ``

## callers

- `0x1400100d0`
- `0x140013270`
- `0x140013480`
- `0x140019da0`
- `0x140019e50`
- `0x140019f00`
- `0x140019f90`
- `0x14001c4a0`

## callees

- `0x1400024c2`
- `0x1400025c0`
- `0x14000c9ac`
- `0x14001a000`
- `0x14001b338`
- `0x1400209fc`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001a07d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a07d`
- `ntoskrnl!KeReleaseMutex` at `0x14001a196`
- `ntoskrnl!KeReleaseMutex` at `0x14001a1e6`
- `ntoskrnl!KeReleaseMutex` at `0x14001a1fc`
- `ntoskrnl!KeReleaseMutex` at `0x1400212c0`
- `ntoskrnl!KeReleaseMutex` at `0x1400212de`
- `ntoskrnl!KeReleaseMutex` at `0x14001a196`
- `ntoskrnl!KeReleaseMutex` at `0x14001a1e6`
- `ntoskrnl!KeReleaseMutex` at `0x14001a1fc`
- `ntoskrnl!KeReleaseMutex` at `0x1400212c0`
- `ntoskrnl!KeReleaseMutex` at `0x1400212de`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a20b`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a21a`
- `ntoskrnl!ObfDereferenceObject` at `0x1400212ed`
- `ntoskrnl!ObfDereferenceObject` at `0x140021300`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a20b`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a21a`
- `ntoskrnl!ObfDereferenceObject` at `0x1400212ed`
- `ntoskrnl!ObfDereferenceObject` at `0x140021300`
- `ntoskrnl!ObfReferenceObject` at `0x14001a046`
- `ntoskrnl!ObfReferenceObject` at `0x14001a055`
- `ntoskrnl!ObfReferenceObject` at `0x14001a046`
- `ntoskrnl!ObfReferenceObject` at `0x14001a055`

## pseudocode

```c
__int64 __fastcall TmpProcessNotificationResponse(
        char *Object,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v9; // rdi
  unsigned int v10; // esi
  struct _KMUTANT *v11; // rbx
  char v12; // r12
  __int64 v13; // rbx
  __int64 v14; // r15
  bool v15; // zf
  __int64 v17; // [rsp+0h] [rbp-88h] BYREF
  char v18; // [rsp+30h] [rbp-58h]
  int i; // [rsp+34h] [rbp-54h]
  __int64 v20; // [rsp+38h] [rbp-50h]
  __int64 v21; // [rsp+40h] [rbp-48h]
  __int64 *v22; // [rsp+48h] [rbp-40h]

  v22 = &v17;
  v9 = *((_QWORD *)Object + 20);
  v21 = v9;
  v10 = 0;
  v20 = *((_QWORD *)Object + 19);
  ObfReferenceObject((PVOID)v9);
  ObfReferenceObject(Object);
  TmpAcquireTransactionMutex(v9);
  v11 = (struct _KMUTANT *)(Object + 64);
  KeWaitForSingleObject(Object + 64, Executive, 0, 0, 0);
  v12 = 1;
  v18 = 1;
  if ( (*((_DWORD *)Object + 43) & 1) != 0 )
  {
    v10 = -1072103404;
  }
  else
  {
    v13 = 0;
    for ( i = 0; ; i = v13 )
    {
      v14 = 4 * v13;
      v15 = (_DWORD)v13 == a3;
      if ( (unsigned int)v13 >= a3 )
        break;
      if ( *(_DWORD *)(v9 + 192) == *(_DWORD *)(v14 + a6) && *((_DWORD *)Object + 42) == *(_DWORD *)(v14 + a4) )
      {
        v15 = (_DWORD)v13 == a3;
        break;
      }
      v13 = (unsigned int)(v13 + 1);
    }
    if ( v15 )
    {
      v10 = -1072103404;
    }
    else
    {
      if ( a2 && !*(_QWORD *)(v20 + 360) )
      {
        local_unwind_0(v22, &loc_14001A12F);
        return 3222863954LL;
      }
      TmpAdjustVirtualClock(*(_QWORD *)(v20 + 360), a2);
      *((_DWORD *)Object + 42) = *(_DWORD *)(v14 + a5);
      if ( *(_DWORD *)(v14 + a8) == 1 || *(_DWORD *)(v14 + a8) == 2 && (*((_DWORD *)Object + 44) & 4) == 0 )
        TmpFinalizeEnlistment(Object);
      KeReleaseMutex((PRKMUTEX)(Object + 64), 0);
      v12 = 0;
      v18 = 0;
      if ( *(_QWORD *)(a7 + 8 * v13) )
      {
        v15 = (*(_DWORD *)(v9 + 236))-- == 1;
        if ( v15 )
          v10 = (*(__int64 (__fastcall **)(__int64, _QWORD))(a7 + 8 * v13))(v9, 0);
      }
    }
    v11 = (struct _KMUTANT *)(Object + 64);
  }
  if ( v12 )
    KeReleaseMutex(v11, 0);
  KeReleaseMutex((PRKMUTEX)(*(_QWORD *)(v9 + 88) + 32LL), 0);
  ObfDereferenceObject((PVOID)v9);
  ObfDereferenceObject(Object);
  return v10;
}

```

## disassembly

```asm
0x14001a000  mov     rax, rsp
0x14001a003  mov     [rax+20h], r9
0x14001a007  mov     [rax+18h], r8d
0x14001a00b  mov     [rax+10h], rdx
0x14001a00f  mov     [rax+8], rcx
0x14001a013  push    rbx
0x14001a014  push    rsi
0x14001a015  push    rdi
0x14001a016  push    r12
0x14001a018  push    r13
0x14001a01a  push    r14
0x14001a01c  push    r15
0x14001a01e  sub     rsp, 50h
0x14001a022  mov     [rsp+88h+var_40], rsp
0x14001a027  mov     r14, rcx
0x14001a02a  mov     rdi, [rcx+0A0h]
0x14001a031  mov     [rax-48h], rdi
0x14001a035  xor     esi, esi
0x14001a037  mov     rax, [rcx+98h]
0x14001a03e  mov     [rsp+88h+var_50], rax
0x14001a043  mov     rcx, rdi; Object
0x14001a046  call    cs:__imp_ObfReferenceObject
0x14001a04d  nop     dword ptr [rax+rax+00h]
0x14001a052  mov     rcx, r14; Object
0x14001a055  call    cs:__imp_ObfReferenceObject
0x14001a05c  nop     dword ptr [rax+rax+00h]
0x14001a061  mov     rcx, rdi
0x14001a064  call    TmpAcquireTransactionMutex
0x14001a069  lea     rbx, [r14+40h]
0x14001a06d  mov     [rsp+88h+Timeout], rsi; Timeout
0x14001a072  xor     r9d, r9d; Alertable
0x14001a075  xor     r8d, r8d; WaitMode
0x14001a078  xor     edx, edx; WaitReason
0x14001a07a  mov     rcx, rbx; Object
0x14001a07d  call    cs:__imp_KeWaitForSingleObject
0x14001a084  nop     dword ptr [rax+rax+00h]
0x14001a089  lea     r12d, [rsi+1]
0x14001a08d  mov     [rsp+88h+var_58], r12b
0x14001a092  mov     eax, [r14+0ACh]
0x14001a099  test    r12b, al
0x14001a09c  jz      short loc_14001A0A8
0x14001a09e  mov     esi, 0C0190014h
0x14001a0a3  jmp     loc_14001A1DC
0x14001a0a8  xor     ebx, ebx
0x14001a0aa  mov     [rsp+88h+var_54], ebx
0x14001a0ae  mov     rcx, [rsp+88h+arg_28]
0x14001a0b6  mov     edx, [rsp+88h+arg_10]
0x14001a0bd  mov     r8, [rsp+88h+arg_18]
0x14001a0c5  lea     r15, ds:0[rbx*4]
0x14001a0cd  cmp     ebx, edx
0x14001a0cf  jnb     short loc_14001A0F5
0x14001a0d1  mov     eax, [r15+rcx]
0x14001a0d5  cmp     [rdi+0C0h], eax
0x14001a0db  jnz     short loc_14001A0EA
0x14001a0dd  mov     eax, [r15+r8]
0x14001a0e1  cmp     [r14+0A8h], eax
0x14001a0e8  jz      short loc_14001A0F3
0x14001a0ea  add     ebx, r12d
0x14001a0ed  mov     [rsp+88h+var_54], ebx
0x14001a0f1  jmp     short loc_14001A0C5
0x14001a0f3  cmp     ebx, edx
0x14001a0f5  jnz     short loc_14001A101
0x14001a0f7  mov     esi, 0C0190014h
0x14001a0fc  jmp     loc_14001A1D8
0x14001a101  mov     rax, [rsp+88h+arg_8]
0x14001a109  mov     rcx, [rsp+88h+var_50]
0x14001a10e  test    rax, rax
0x14001a111  jz      short loc_14001A145
0x14001a113  cmp     qword ptr [rcx+168h], 0
0x14001a11b  jnz     short loc_14001A145
0x14001a11d  lea     rdx, loc_14001A12F
0x14001a124  mov     rcx, [rsp+88h+var_40]
0x14001a129  call    _local_unwind_0
0x14001a12e  nop
0x14001a12f  mov     eax, 0C0190052h
0x14001a134  add     rsp, 50h
0x14001a138  pop     r15
0x14001a13a  pop     r14
0x14001a13c  pop     r13
0x14001a13e  pop     r12
0x14001a140  pop     rdi
0x14001a141  pop     rsi
0x14001a142  pop     rbx
0x14001a143  retn
0x14001a145  mov     rdx, rax
0x14001a148  mov     rcx, [rcx+168h]
0x14001a14f  call    TmpAdjustVirtualClock
0x14001a154  mov     rax, [rsp+88h+arg_20]
0x14001a15c  mov     ecx, [r15+rax]
0x14001a160  mov     [r14+0A8h], ecx
0x14001a167  mov     rcx, [rsp+88h+arg_38]
0x14001a16f  mov     edx, [r15+rcx]
0x14001a173  sub     edx, 1
0x14001a176  jz      short loc_14001A188
0x14001a178  cmp     edx, 1
0x14001a17b  jnz     short loc_14001A190
0x14001a17d  mov     eax, [r14+0B0h]
0x14001a184  test    al, 4
0x14001a186  jnz     short loc_14001A190
0x14001a188  mov     rcx, r14; Object
0x14001a18b  call    TmpFinalizeEnlistment
0x14001a190  xor     edx, edx; Wait
0x14001a192  lea     rcx, [r14+40h]; Mutex
0x14001a196  call    cs:__imp_KeReleaseMutex
0x14001a19d  nop     dword ptr [rax+rax+00h]
0x14001a1a2  xor     r12b, r12b
0x14001a1a5  mov     [rsp+88h+var_58], r12b
0x14001a1aa  mov     rcx, [rsp+88h+arg_30]
0x14001a1b2  cmp     qword ptr [rcx+rbx*8], 0
0x14001a1b7  jz      short loc_14001A1D8
0x14001a1b9  add     dword ptr [rdi+0ECh], 0FFFFFFFFh
0x14001a1c0  mov     eax, [rdi+0ECh]
0x14001a1c6  jnz     short loc_14001A1D8
0x14001a1c8  mov     rax, [rcx+rbx*8]
0x14001a1cc  xor     edx, edx
0x14001a1ce  mov     rcx, rdi
0x14001a1d1  call    _guard_dispatch_icall
0x14001a1d6  mov     esi, eax
0x14001a1d8  lea     rbx, [r14+40h]
0x14001a1dc  test    r12b, r12b
0x14001a1df  jz      short loc_14001A1F2
0x14001a1e1  xor     edx, edx; Wait
0x14001a1e3  mov     rcx, rbx; Mutex
0x14001a1e6  call    cs:__imp_KeReleaseMutex
0x14001a1ed  nop     dword ptr [rax+rax+00h]
0x14001a1f2  mov     rcx, [rdi+58h]
0x14001a1f6  add     rcx, 20h ; ' '; Mutex
0x14001a1fa  xor     edx, edx; Wait
0x14001a1fc  call    cs:__imp_KeReleaseMutex
0x14001a203  nop     dword ptr [rax+rax+00h]
0x14001a208  mov     rcx, rdi; Object
0x14001a20b  call    cs:__imp_ObfDereferenceObject
0x14001a212  nop     dword ptr [rax+rax+00h]
0x14001a217  mov     rcx, r14; Object
0x14001a21a  call    cs:__imp_ObfDereferenceObject
0x14001a221  nop     dword ptr [rax+rax+00h]
0x14001a226  mov     eax, esi
0x14001a228  jmp     loc_14001A134
0x1400212a3  push    rbx
0x1400212a5  push    rbp
0x1400212a6  sub     rsp, 38h
0x1400212aa  mov     rbp, rdx
0x1400212ad  cmp     byte ptr [rbp+30h], 0
0x1400212b1  jz      short loc_1400212D0
0x1400212b3  mov     rcx, [rbp+90h]
0x1400212ba  add     rcx, 40h ; '@'; Mutex
0x1400212be  xor     edx, edx; Wait
0x1400212c0  call    cs:__imp_KeReleaseMutex
0x1400212c7  nop     dword ptr [rax+rax+00h]
0x1400212cc  mov     byte ptr [rbp+30h], 0
0x1400212d0  mov     rbx, [rbp+40h]
0x1400212d4  mov     rcx, [rbx+58h]
0x1400212d8  add     rcx, 20h ; ' '; Mutex
0x1400212dc  xor     edx, edx; Wait
0x1400212de  call    cs:__imp_KeReleaseMutex
0x1400212e5  nop     dword ptr [rax+rax+00h]
0x1400212ea  mov     rcx, rbx; Object
0x1400212ed  call    cs:__imp_ObfDereferenceObject
0x1400212f4  nop     dword ptr [rax+rax+00h]
0x1400212f9  mov     rcx, [rbp+90h]; Object
0x140021300  call    cs:__imp_ObfDereferenceObject
0x140021307  nop     dword ptr [rax+rax+00h]
0x14002130c  nop
0x14002130d  add     rsp, 38h
0x140021311  pop     rbp
0x140021312  pop     rbx
0x140021313  retn
```
