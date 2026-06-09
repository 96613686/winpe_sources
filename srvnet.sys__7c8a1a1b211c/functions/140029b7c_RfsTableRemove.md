# RfsTableRemove

- ea: `0x140029b7c`
- end: `0x140029ccd`
- name: `RfsTableRemove`
- size: `337`
- prototype: `__int64 __fastcall(PEX_SPIN_LOCK SpinLock)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140005570`
- `0x140022030`
- `0x1400221a0`
- `0x140023ae0`
- `0x140023f90`
- `0x140025990`
- `0x140026064`

## callees

- `0x140029b7c`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140029c86`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140029cb3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140029c86`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140029cb3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140029bac`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140029bac`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140029c76`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140029ca3`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140029c76`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140029ca3`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140029b96`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140029b96`

## pseudocode

```c
__int64 __fastcall RfsTableRemove(volatile LONG *SpinLock, unsigned int a2)
{
  unsigned __int64 v3; // rdi
  KIRQL v5; // bp
  __int64 v6; // r9
  unsigned int v7; // eax
  __int64 v8; // rdx
  _DWORD *v9; // r8
  int v10; // eax
  __int64 v11; // rdi
  int v12; // ecx
  int v13; // r10d
  int v14; // r11d
  int v15; // edx
  int *v16; // rax

  v3 = *((_QWORD *)SpinLock + 2);
  if ( (SpinLock[22] & 0x40) != 0 )
  {
    v5 = ExAcquireSpinLockExclusive(SpinLock);
  }
  else
  {
    v5 = 0;
    ExAcquirePushLockExclusiveEx(SpinLock, 0);
  }
  if ( (a2 & 3) == 1 )
  {
    v6 = 0;
    while ( 1 )
    {
      v7 = SpinLock[v6 + 6];
      v8 = v7 & (a2 >> SpinLock[v6 + 12]);
      if ( (unsigned int)v8 > v7 )
        break;
      v9 = (_DWORD *)(v3 + 8 * v8);
      v10 = *v9 & 3;
      if ( v10 != 2 )
      {
        if ( v10 )
          break;
        v11 = *(_QWORD *)v9;
        if ( **(_DWORD **)v9 != a2 )
          break;
        *v9 = -1;
        v12 = *((_DWORD *)SpinLock + 17);
        v13 = *((_DWORD *)SpinLock + 11);
        v14 = v13 & (a2 >> v12);
        v15 = a2 & ~(v13 << v12) | ((v13 & (v14 + 1)) << v12);
        if ( v15 == -1 )
          v15 = ~(v13 << v12) | ((v13 & (v14 + 2)) << v12);
        --*((_DWORD *)SpinLock + 2);
        v16 = (int *)*((_QWORD *)SpinLock + 10);
        if ( v16 )
          *v16 = v15;
        *((_QWORD *)SpinLock + 10) = v9;
        if ( *((_DWORD *)SpinLock + 19) == -1 )
          *((_DWORD *)SpinLock + 19) = v15;
        if ( (SpinLock[22] & 0x40) != 0 )
          ExReleaseSpinLockExclusive(SpinLock, v5);
        else
          ExReleasePushLockExclusiveEx(SpinLock, 0);
        return v11;
      }
      v6 = (unsigned int)(v6 + 1);
      v3 = *(_QWORD *)v9 & 0xFFFFFFFFFFFFFFFCuLL;
    }
  }
  if ( (SpinLock[22] & 0x40) != 0 )
    ExReleaseSpinLockExclusive(SpinLock, v5);
  else
    ExReleasePushLockExclusiveEx(SpinLock, 0);
  return 0;
}

```

## disassembly

```asm
0x140029b7c  push    rbx
0x140029b7e  push    rbp
0x140029b7f  push    rsi
0x140029b80  push    rdi
0x140029b81  push    r15
0x140029b83  sub     rsp, 20h
0x140029b87  test    byte ptr [rcx+58h], 40h
0x140029b8b  mov     esi, edx
0x140029b8d  mov     rdi, [rcx+10h]
0x140029b91  mov     rbx, rcx
0x140029b94  jz      short loc_140029BA7
0x140029b96  call    cs:__imp_ExAcquireSpinLockExclusive
0x140029b9d  nop     dword ptr [rax+rax+00h]
0x140029ba2  mov     bpl, al
0x140029ba5  jmp     short loc_140029BB8
0x140029ba7  xor     bpl, bpl
0x140029baa  xor     edx, edx
0x140029bac  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140029bb3  nop     dword ptr [rax+rax+00h]
0x140029bb8  mov     eax, esi
0x140029bba  and     al, 3
0x140029bbc  cmp     al, 1
0x140029bbe  jnz     loc_140029C97
0x140029bc4  xor     r9d, r9d
0x140029bc7  mov     eax, [rbx+r9*4+18h]
0x140029bcc  mov     edx, esi
0x140029bce  mov     ecx, [rbx+r9*4+30h]
0x140029bd3  shr     edx, cl
0x140029bd5  and     edx, eax
0x140029bd7  cmp     edx, eax
0x140029bd9  ja      loc_140029C97
0x140029bdf  lea     r8, [rdi+rdx*8]
0x140029be3  mov     eax, [r8]
0x140029be6  and     eax, 3
0x140029be9  cmp     eax, 2
0x140029bec  jnz     short loc_140029BFA
0x140029bee  mov     rdi, [r8]
0x140029bf1  inc     r9d
0x140029bf4  and     rdi, 0FFFFFFFFFFFFFFFCh
0x140029bf8  jmp     short loc_140029BC7
0x140029bfa  test    eax, eax
0x140029bfc  jnz     loc_140029C97
0x140029c02  mov     rdi, [r8]
0x140029c05  cmp     [rdi], esi
0x140029c07  jnz     loc_140029C97
0x140029c0d  or      r15d, 0FFFFFFFFh
0x140029c11  mov     r11d, esi
0x140029c14  mov     [r8], r15d
0x140029c17  mov     ecx, [rbx+44h]
0x140029c1a  mov     r10d, [rbx+2Ch]
0x140029c1e  mov     r9d, r10d
0x140029c21  shr     r11d, cl
0x140029c24  and     r11d, r10d
0x140029c27  shl     r9d, cl
0x140029c2a  not     r9d
0x140029c2d  mov     eax, r9d
0x140029c30  and     eax, esi
0x140029c32  lea     edx, [r11+1]
0x140029c36  and     edx, r10d
0x140029c39  shl     edx, cl
0x140029c3b  or      edx, eax
0x140029c3d  cmp     edx, r15d
0x140029c40  jnz     short loc_140029C4E
0x140029c42  lea     edx, [r11+2]
0x140029c46  and     edx, r10d
0x140029c49  shl     edx, cl
0x140029c4b  or      edx, r9d
0x140029c4e  add     [rbx+8], r15d
0x140029c52  mov     rax, [rbx+50h]
0x140029c56  test    rax, rax
0x140029c59  jz      short loc_140029C5D
0x140029c5b  mov     [rax], edx
0x140029c5d  mov     [rbx+50h], r8
0x140029c61  cmp     [rbx+4Ch], r15d
0x140029c65  jnz     short loc_140029C6A
0x140029c67  mov     [rbx+4Ch], edx
0x140029c6a  test    byte ptr [rbx+58h], 40h
0x140029c6e  mov     rcx, rbx; SpinLock
0x140029c71  jz      short loc_140029C84
0x140029c73  mov     dl, bpl; OldIrql
0x140029c76  call    cs:__imp_ExReleaseSpinLockExclusive
0x140029c7d  nop     dword ptr [rax+rax+00h]
0x140029c82  jmp     short loc_140029C92
0x140029c84  xor     edx, edx
0x140029c86  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140029c8d  nop     dword ptr [rax+rax+00h]
0x140029c92  mov     rax, rdi
0x140029c95  jmp     short loc_140029CC1
0x140029c97  test    byte ptr [rbx+58h], 40h
0x140029c9b  mov     rcx, rbx; SpinLock
0x140029c9e  jz      short loc_140029CB1
0x140029ca0  mov     dl, bpl; OldIrql
0x140029ca3  call    cs:__imp_ExReleaseSpinLockExclusive
0x140029caa  nop     dword ptr [rax+rax+00h]
0x140029caf  jmp     short loc_140029CBF
0x140029cb1  xor     edx, edx
0x140029cb3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140029cba  nop     dword ptr [rax+rax+00h]
0x140029cbf  xor     eax, eax
0x140029cc1  add     rsp, 20h
0x140029cc5  pop     r15
0x140029cc7  pop     rdi
0x140029cc8  pop     rsi
0x140029cc9  pop     rbp
0x140029cca  pop     rbx
0x140029ccb  retn
```
