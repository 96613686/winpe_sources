# PipeClose

- ea: `0x1400019c0`
- end: `0x140001b64`
- name: `PipeClose`
- size: `420`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140027d30`
- `0x140029c10`
- `0x14002c010`
- `0x14002f200`

## callees

- `0x1400019c0`
- `0x1400030b4`
- `0x140015bf8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001ae2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001ae2`
- `ntoskrnl!IofCompleteRequest` at `0x140001b40`
- `ntoskrnl!IofCompleteRequest` at `0x140001b40`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001afa`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001afa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001a26`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001a26`
- `vmbkmcl!VmbChannelCleanup` at `0x1400019f5`
- `vmbkmcl!VmbChannelCleanup` at `0x1400019f5`
- `vmbkmcl!VmbChannelDisable` at `0x1400019e2`
- `vmbkmcl!VmbChannelDisable` at `0x1400019e2`

## pseudocode

```c
_OWORD *__fastcall PipeClose(_BYTE *SpinLock, __int64 a2)
{
  KSPIN_LOCK v3; // rcx
  KIRQL v4; // al
  KIRQL v5; // bp
  PKSPIN_LOCK v6; // rdi
  KSPIN_LOCK v7; // rsi
  int v8; // eax
  KSPIN_LOCK *v9; // rax
  __int64 v10; // rax
  _QWORD *v11; // rcx
  __int64 v12; // rcx
  _OWORD *result; // rax
  __int64 v14; // rax
  _OWORD v15[3]; // [rsp+20h] [rbp-38h] BYREF

  v3 = *((_QWORD *)SpinLock + 32);
  v15[0] = 0;
  if ( v3 )
  {
    VmbChannelDisable(v3, a2);
    VmbChannelCleanup(*((_QWORD *)SpinLock + 32));
    *((_QWORD *)SpinLock + 32) = 0;
    SpinLock[445] = 0;
  }
  *((_QWORD *)&v15[0] + 1) = v15;
  *(_QWORD *)&v15[0] = v15;
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SpinLock);
  *((_DWORD *)SpinLock + 2) = 0;
  v5 = v4;
  v6 = (PKSPIN_LOCK)(SpinLock + 48);
  while ( 1 )
  {
    v7 = *v6;
    if ( (PKSPIN_LOCK)*v6 == v6 )
      break;
    v8 = *(_DWORD *)(v7 - 16);
    switch ( v8 )
    {
      case 1:
        if ( (unsigned __int8)PipeDequeueIrpForCompletion(v7 - 136, 3221226166LL) )
        {
          v9 = (KSPIN_LOCK *)*((_QWORD *)&v15[0] + 1);
          if ( **((_OWORD ***)&v15[0] + 1) != v15 )
            goto LABEL_21;
          *(_QWORD *)(v7 + 8) = *((_QWORD *)&v15[0] + 1);
          *(_QWORD *)v7 = v15;
          *v9 = v7;
          *((_QWORD *)&v15[0] + 1) = v7;
        }
        break;
      case 2:
        DvFreeHandleEntry(*(_QWORD *)(v7 - 8) + 392LL, *(unsigned int *)(v7 + 20));
        --*(_DWORD *)(*(_QWORD *)(v7 - 8) + 440LL);
LABEL_13:
        v10 = *(_QWORD *)v7;
        if ( *(_QWORD *)(*(_QWORD *)v7 + 8LL) != v7 || (v11 = *(_QWORD **)(v7 + 8), *v11 != v7) )
LABEL_21:
          __fastfail(3u);
        *v11 = v10;
        *(_QWORD *)(v10 + 8) = v11;
        ExFreePoolWithTag((PVOID)(v7 - 16), 0x73756256u);
        break;
      case 3:
        goto LABEL_13;
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v5);
  while ( 1 )
  {
    v12 = *(_QWORD *)&v15[0];
    result = v15;
    if ( *(_OWORD **)&v15[0] == v15 )
      return result;
    if ( *(_OWORD **)(*(_QWORD *)&v15[0] + 8LL) != v15 )
      goto LABEL_21;
    v14 = **(_QWORD **)&v15[0];
    if ( *(_QWORD *)(**(_QWORD **)&v15[0] + 8LL) != *(_QWORD *)&v15[0] )
      goto LABEL_21;
    *(_QWORD *)&v15[0] = **(_QWORD **)&v15[0];
    *(_QWORD *)(v14 + 8) = v15;
    IofCompleteRequest((PIRP)(v12 - 136), 0);
  }
}

```

## disassembly

```asm
0x1400019c0  push    rbx
0x1400019c2  push    rbp
0x1400019c3  push    rsi
0x1400019c4  push    rdi
0x1400019c5  sub     rsp, 38h
0x1400019c9  mov     rbx, rcx
0x1400019cc  xor     edi, edi
0x1400019ce  mov     rcx, [rcx+100h]
0x1400019d5  xorps   xmm0, xmm0
0x1400019d8  movups  [rsp+58h+var_38], xmm0
0x1400019dd  test    rcx, rcx
0x1400019e0  jz      short loc_140001A0F
0x1400019e2  call    cs:__imp_VmbChannelDisable
0x1400019e9  nop     dword ptr [rax+rax+00h]
0x1400019ee  mov     rcx, [rbx+100h]
0x1400019f5  call    cs:__imp_VmbChannelCleanup
0x1400019fc  nop     dword ptr [rax+rax+00h]
0x140001a01  mov     [rbx+100h], rdi
0x140001a08  mov     [rbx+1BDh], dil
0x140001a0f  lea     rax, [rsp+58h+var_38]
0x140001a14  mov     rcx, rbx; SpinLock
0x140001a17  mov     qword ptr [rsp+58h+var_38+8], rax
0x140001a1c  lea     rax, [rsp+58h+var_38]
0x140001a21  mov     qword ptr [rsp+58h+var_38], rax
0x140001a26  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001a2d  nop     dword ptr [rax+rax+00h]
0x140001a32  mov     [rbx+8], edi
0x140001a35  movzx   ebp, al
0x140001a38  lea     rdi, [rbx+30h]
0x140001a3c  mov     [rsp+58h+arg_0], r14
0x140001a41  mov     rsi, [rdi]
0x140001a44  cmp     rsi, rdi
0x140001a47  jz      loc_140001AF3
0x140001a4d  mov     eax, [rsi-10h]
0x140001a50  cmp     eax, 1
0x140001a53  jnz     short loc_140001A93
0x140001a55  lea     rcx, [rsi-88h]
0x140001a5c  mov     edx, 0C00002B6h
0x140001a61  call    PipeDequeueIrpForCompletion
0x140001a66  test    al, al
0x140001a68  jz      short loc_140001A41
0x140001a6a  mov     rax, qword ptr [rsp+58h+var_38+8]
0x140001a6f  lea     rcx, [rsp+58h+var_38]
0x140001a74  cmp     [rax], rcx
0x140001a77  jnz     loc_140001B4E
0x140001a7d  mov     [rsi+8], rax
0x140001a81  lea     rcx, [rsp+58h+var_38]
0x140001a86  mov     [rsi], rcx
0x140001a89  mov     [rax], rsi
0x140001a8c  mov     qword ptr [rsp+58h+var_38+8], rsi
0x140001a91  jmp     short loc_140001A41
0x140001a93  cmp     eax, 2
0x140001a96  jz      short loc_140001A9F
0x140001a98  cmp     eax, 3
0x140001a9b  jnz     short loc_140001A41
0x140001a9d  jmp     short loc_140001ABC
0x140001a9f  mov     rcx, [rsi-8]
0x140001aa3  mov     edx, [rsi+14h]
0x140001aa6  add     rcx, 188h
0x140001aad  call    DvFreeHandleEntry
0x140001ab2  mov     rax, [rsi-8]
0x140001ab6  dec     dword ptr [rax+1B8h]
0x140001abc  mov     rax, [rsi]
0x140001abf  cmp     [rax+8], rsi
0x140001ac3  jnz     loc_140001B4E
0x140001ac9  mov     rcx, [rsi+8]
0x140001acd  cmp     [rcx], rsi
0x140001ad0  jnz     short loc_140001B4E
0x140001ad2  mov     [rcx], rax
0x140001ad5  mov     edx, 73756256h; Tag
0x140001ada  mov     [rax+8], rcx
0x140001ade  lea     rcx, [rsi-10h]; P
0x140001ae2  call    cs:__imp_ExFreePoolWithTag
0x140001ae9  nop     dword ptr [rax+rax+00h]
0x140001aee  jmp     loc_140001A41
0x140001af3  movzx   edx, bpl; NewIrql
0x140001af7  mov     rcx, rbx; SpinLock
0x140001afa  call    cs:__imp_KeReleaseSpinLock
0x140001b01  nop     dword ptr [rax+rax+00h]
0x140001b06  mov     rcx, qword ptr [rsp+58h+var_38]
0x140001b0b  lea     rax, [rsp+58h+var_38]
0x140001b10  cmp     rcx, rax
0x140001b13  jz      short loc_140001B55
0x140001b15  lea     rax, [rsp+58h+var_38]
0x140001b1a  cmp     [rcx+8], rax
0x140001b1e  jnz     short loc_140001B4E
0x140001b20  mov     rax, [rcx]
0x140001b23  cmp     [rax+8], rcx
0x140001b27  jnz     short loc_140001B4E
0x140001b29  lea     rdx, [rsp+58h+var_38]
0x140001b2e  mov     qword ptr [rsp+58h+var_38], rax
0x140001b33  mov     [rax+8], rdx
0x140001b37  add     rcx, 0FFFFFFFFFFFFFF78h; Irp
0x140001b3e  xor     edx, edx; PriorityBoost
0x140001b40  call    cs:__imp_IofCompleteRequest
0x140001b47  nop     dword ptr [rax+rax+00h]
0x140001b4c  jmp     short loc_140001B06
0x140001b4e  mov     ecx, 3
0x140001b53  int     29h; Win8: RtlFailFast(ecx)
0x140001b55  mov     r14, [rsp+58h+arg_0]
0x140001b5a  add     rsp, 38h
0x140001b5e  pop     rdi
0x140001b5f  pop     rsi
0x140001b60  pop     rbp
0x140001b61  pop     rbx
0x140001b62  retn
```
