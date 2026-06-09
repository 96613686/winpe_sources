# SIO_SLOTS::WriteCheckpoint(SC_PACKET *)

- ea: `0x140052680`
- end: `0x140052788`
- name: `?WriteCheckpoint@SIO_SLOTS@@QEAAJPEAVSC_PACKET@@@Z`
- size: `264`
- prototype: `__int64 __fastcall(SIO_SLOTS *__hidden this, struct SC_PACKET *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400400e0`
- `0x140048858`

## callees

- `0x140051c04`
- `0x140051f5c`
- `0x140052680`
- `0x140052924`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x1400526ca`
- `ntoskrnl!RtlComputeCrc32` at `0x140052725`
- `ntoskrnl!RtlComputeCrc32` at `0x1400526ca`
- `ntoskrnl!RtlComputeCrc32` at `0x140052725`

## pseudocode

```c
__int64 __fastcall SIO_SLOTS::WriteCheckpoint(SIO_SLOTS *this, struct SC_PACKET *a2)
{
  struct SIO_SPACE *Child; // r14
  int v5; // ebx
  __int64 v6; // rsi
  ULONG v7; // r8d
  unsigned int v8; // r9d
  int v9; // ebx

  Child = SIO_SLOTS::GetChild(this);
  v5 = *((_DWORD *)a2 + 48);
  v6 = *(_QWORD *)(*((_QWORD *)a2 + 15) + 32LL) + *(unsigned int *)(*((_QWORD *)a2 + 15) + 44LL);
  v7 = v5 - *(_DWORD *)(v6 + 64);
  *(_DWORD *)(v6 + 72) = v7;
  *(_DWORD *)(v6 + 52) = v5;
  *(_DWORD *)(v6 + 48) = RtlComputeCrc32(
                           0,
                           (PUCHAR)(*(_QWORD *)(v6 + 64)
                                  + *(_QWORD *)(*((_QWORD *)a2 + 15) + 32LL)
                                  + *(unsigned int *)(*((_QWORD *)a2 + 15) + 44LL)),
                           v7);
  v8 = *((_DWORD *)Child + 33) + v5 - 1 - (unsigned int)(*((_DWORD *)Child + 33) + v5 - 1) % *((_DWORD *)Child + 33);
  *((_QWORD *)a2 + 17) = *((_QWORD *)this + 5) + (unsigned int)(*((_DWORD *)this + 14) * *((_DWORD *)this + 12));
  *((_DWORD *)a2 + 36) = v8;
  v9 = SIO_SLOTS::WriteSynchronous(this, a2);
  if ( v9 >= 0 )
  {
    *(_DWORD *)(v6 + 36) = RtlComputeCrc32(0, (PUCHAR)v6, *(_DWORD *)(v6 + 28));
    *((_DWORD *)a2 + 36) = *((_DWORD *)Child + 33);
    v9 = SIO_SLOTS::WriteSynchronous(this, a2);
    if ( v9 >= 0 )
    {
      *((_DWORD *)this + 14) = *((_DWORD *)this + 14) == 0;
      *((_DWORD *)this + 16) = *(_DWORD *)(v6 + 56);
      *((_BYTE *)this + 72) = 0;
    }
  }
  SIO_SLOTS::LogStatus(this, 4, a2, (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140052680  push    rbx
0x140052682  push    rbp
0x140052683  push    rsi
0x140052684  push    rdi
0x140052685  push    r14
0x140052687  sub     rsp, 20h
0x14005268b  mov     rbp, rdx
0x14005268e  mov     rdi, rcx
0x140052691  call    ?GetChild@SIO_SLOTS@@QEAAPEAVSIO_SPACE@@XZ; SIO_SLOTS::GetChild(void)
0x140052696  mov     r8, [rbp+78h]
0x14005269a  mov     r14, rax
0x14005269d  mov     ebx, [rbp+0C0h]
0x1400526a3  mov     esi, [r8+2Ch]
0x1400526a7  add     rsi, [r8+20h]
0x1400526ab  mov     r8d, ebx
0x1400526ae  sub     r8d, [rsi+40h]; Length
0x1400526b2  mov     [rsi+48h], r8d
0x1400526b6  mov     [rsi+34h], ebx
0x1400526b9  mov     rcx, [rbp+78h]
0x1400526bd  mov     edx, [rcx+2Ch]
0x1400526c0  add     rdx, [rcx+20h]
0x1400526c4  xor     ecx, ecx; InitialCrc
0x1400526c6  add     rdx, [rsi+40h]; Buffer
0x1400526ca  call    cs:__imp_RtlComputeCrc32
0x1400526d1  nop     dword ptr [rax+rax+00h]
0x1400526d6  mov     [rsi+30h], eax
0x1400526d9  xor     edx, edx
0x1400526db  mov     r8d, [r14+84h]
0x1400526e2  lea     r9d, [rbx-1]
0x1400526e6  mov     ecx, [rdi+30h]
0x1400526e9  add     r9d, r8d
0x1400526ec  imul    ecx, [rdi+38h]
0x1400526f0  mov     eax, r9d
0x1400526f3  div     r8d
0x1400526f6  add     rcx, [rdi+28h]
0x1400526fa  sub     r9d, edx
0x1400526fd  mov     [rbp+88h], rcx
0x140052704  mov     rdx, rbp; struct SC_PACKET *
0x140052707  mov     [rbp+90h], r9d
0x14005270e  mov     rcx, rdi; this
0x140052711  call    ?WriteSynchronous@SIO_SLOTS@@QEAAJPEAVSC_PACKET@@@Z; SIO_SLOTS::WriteSynchronous(SC_PACKET *)
0x140052716  mov     ebx, eax
0x140052718  test    eax, eax
0x14005271a  js      short loc_140052767
0x14005271c  mov     r8d, [rsi+1Ch]; Length
0x140052720  mov     rdx, rsi; Buffer
0x140052723  xor     ecx, ecx; InitialCrc
0x140052725  call    cs:__imp_RtlComputeCrc32
0x14005272c  nop     dword ptr [rax+rax+00h]
0x140052731  mov     [rsi+24h], eax
0x140052734  mov     rdx, rbp; struct SC_PACKET *
0x140052737  mov     eax, [r14+84h]
0x14005273e  mov     rcx, rdi; this
0x140052741  mov     [rbp+90h], eax
0x140052747  call    ?WriteSynchronous@SIO_SLOTS@@QEAAJPEAVSC_PACKET@@@Z; SIO_SLOTS::WriteSynchronous(SC_PACKET *)
0x14005274c  mov     ebx, eax
0x14005274e  test    eax, eax
0x140052750  js      short loc_140052767
0x140052752  xor     eax, eax
0x140052754  cmp     [rdi+38h], eax
0x140052757  setz    al
0x14005275a  mov     [rdi+38h], eax
0x14005275d  mov     eax, [rsi+38h]
0x140052760  mov     [rdi+40h], eax
0x140052763  mov     byte ptr [rdi+48h], 0
0x140052767  mov     r9d, ebx
0x14005276a  mov     r8, rbp
0x14005276d  mov     edx, 4
0x140052772  mov     rcx, rdi
0x140052775  call    ?LogStatus@SIO_SLOTS@@AEAAXW4SIO_SLOTS_OPERATION@@PEAVSC_PACKET@@J@Z; SIO_SLOTS::LogStatus(SIO_SLOTS_OPERATION,SC_PACKET *,long)
0x14005277a  mov     eax, ebx
0x14005277c  add     rsp, 20h
0x140052780  pop     r14
0x140052782  pop     rdi
0x140052783  pop     rsi
0x140052784  pop     rbp
0x140052785  pop     rbx
0x140052786  retn
```
