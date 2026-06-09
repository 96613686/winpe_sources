# SIO_SLOTS::WriteCheckpoint(SC_PACKET *)

- ea: `0x140052740`
- end: `0x140052848`
- name: `?WriteCheckpoint@SIO_SLOTS@@QEAAJPEAVSC_PACKET@@@Z`
- size: `264`
- prototype: `__int64 __fastcall(SIO_SLOTS *__hidden this, struct SC_PACKET *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400401a0`
- `0x140048918`

## callees

- `0x140051cc4`
- `0x14005201c`
- `0x140052740`
- `0x1400529e4`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x14005278a`
- `ntoskrnl!RtlComputeCrc32` at `0x1400527e5`
- `ntoskrnl!RtlComputeCrc32` at `0x14005278a`
- `ntoskrnl!RtlComputeCrc32` at `0x1400527e5`

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
0x140052740  push    rbx
0x140052742  push    rbp
0x140052743  push    rsi
0x140052744  push    rdi
0x140052745  push    r14
0x140052747  sub     rsp, 20h
0x14005274b  mov     rbp, rdx
0x14005274e  mov     rdi, rcx
0x140052751  call    ?GetChild@SIO_SLOTS@@QEAAPEAVSIO_SPACE@@XZ; SIO_SLOTS::GetChild(void)
0x140052756  mov     r8, [rbp+78h]
0x14005275a  mov     r14, rax
0x14005275d  mov     ebx, [rbp+0C0h]
0x140052763  mov     esi, [r8+2Ch]
0x140052767  add     rsi, [r8+20h]
0x14005276b  mov     r8d, ebx
0x14005276e  sub     r8d, [rsi+40h]; Length
0x140052772  mov     [rsi+48h], r8d
0x140052776  mov     [rsi+34h], ebx
0x140052779  mov     rcx, [rbp+78h]
0x14005277d  mov     edx, [rcx+2Ch]
0x140052780  add     rdx, [rcx+20h]
0x140052784  xor     ecx, ecx; InitialCrc
0x140052786  add     rdx, [rsi+40h]; Buffer
0x14005278a  call    cs:__imp_RtlComputeCrc32
0x140052791  nop     dword ptr [rax+rax+00h]
0x140052796  mov     [rsi+30h], eax
0x140052799  xor     edx, edx
0x14005279b  mov     r8d, [r14+84h]
0x1400527a2  lea     r9d, [rbx-1]
0x1400527a6  mov     ecx, [rdi+30h]
0x1400527a9  add     r9d, r8d
0x1400527ac  imul    ecx, [rdi+38h]
0x1400527b0  mov     eax, r9d
0x1400527b3  div     r8d
0x1400527b6  add     rcx, [rdi+28h]
0x1400527ba  sub     r9d, edx
0x1400527bd  mov     [rbp+88h], rcx
0x1400527c4  mov     rdx, rbp; struct SC_PACKET *
0x1400527c7  mov     [rbp+90h], r9d
0x1400527ce  mov     rcx, rdi; this
0x1400527d1  call    ?WriteSynchronous@SIO_SLOTS@@QEAAJPEAVSC_PACKET@@@Z; SIO_SLOTS::WriteSynchronous(SC_PACKET *)
0x1400527d6  mov     ebx, eax
0x1400527d8  test    eax, eax
0x1400527da  js      short loc_140052827
0x1400527dc  mov     r8d, [rsi+1Ch]; Length
0x1400527e0  mov     rdx, rsi; Buffer
0x1400527e3  xor     ecx, ecx; InitialCrc
0x1400527e5  call    cs:__imp_RtlComputeCrc32
0x1400527ec  nop     dword ptr [rax+rax+00h]
0x1400527f1  mov     [rsi+24h], eax
0x1400527f4  mov     rdx, rbp; struct SC_PACKET *
0x1400527f7  mov     eax, [r14+84h]
0x1400527fe  mov     rcx, rdi; this
0x140052801  mov     [rbp+90h], eax
0x140052807  call    ?WriteSynchronous@SIO_SLOTS@@QEAAJPEAVSC_PACKET@@@Z; SIO_SLOTS::WriteSynchronous(SC_PACKET *)
0x14005280c  mov     ebx, eax
0x14005280e  test    eax, eax
0x140052810  js      short loc_140052827
0x140052812  xor     eax, eax
0x140052814  cmp     [rdi+38h], eax
0x140052817  setz    al
0x14005281a  mov     [rdi+38h], eax
0x14005281d  mov     eax, [rsi+38h]
0x140052820  mov     [rdi+40h], eax
0x140052823  mov     byte ptr [rdi+48h], 0
0x140052827  mov     r9d, ebx
0x14005282a  mov     r8, rbp
0x14005282d  mov     edx, 4
0x140052832  mov     rcx, rdi
0x140052835  call    ?LogStatus@SIO_SLOTS@@AEAAXW4SIO_SLOTS_OPERATION@@PEAVSC_PACKET@@J@Z; SIO_SLOTS::LogStatus(SIO_SLOTS_OPERATION,SC_PACKET *,long)
0x14005283a  mov     eax, ebx
0x14005283c  add     rsp, 20h
0x140052840  pop     r14
0x140052842  pop     rdi
0x140052843  pop     rsi
0x140052844  pop     rbp
0x140052845  pop     rbx
0x140052846  retn
```
