# RfsTable64Remove

- ea: `0x140006f70`
- end: `0x14000714c`
- name: `RfsTable64Remove`
- size: `476`
- prototype: `__int64 __fastcall(PEX_SPIN_LOCK SpinLock)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400051f0`
- `0x140006b20`
- `0x140023260`

## callees

- `0x140006f70`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140006f9a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140006f9a`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400070d5`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000710e`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400070d5`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000710e`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400070f5`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400070f5`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400070ab`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400070e7`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400070ab`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400070e7`

## pseudocode

```c
unsigned __int64 __fastcall RfsTable64Remove(volatile LONG *SpinLock, __int64 a2)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v3; // rsi
  KIRQL v5; // r14
  __int64 v6; // r8
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rax
  unsigned __int64 *v9; // rdx
  unsigned __int64 v10; // rdi
  __int64 v11; // r11
  __int64 v12; // r10
  __int64 v13; // r9
  unsigned __int64 v14; // rbp
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 *v17; // rcx
  bool v18; // zf

  v2 = *((_QWORD *)SpinLock + 2);
  v3 = *((_QWORD *)SpinLock + 15) & a2;
  if ( (SpinLock[38] & 0x40) != 0 )
  {
    v5 = ExAcquireSpinLockExclusive(SpinLock);
  }
  else
  {
    v5 = 0;
    ExAcquirePushLockExclusiveEx(SpinLock, 0);
  }
  if ( (v3 & 3) == 1 )
  {
    v6 = 0;
    while ( 1 )
    {
      v7 = *(_QWORD *)&SpinLock[2 * v6 + 6];
      v8 = v7 & (v3 >> *(_QWORD *)&SpinLock[2 * v6 + 18]);
      if ( v8 > v7 )
        break;
      v9 = (unsigned __int64 *)(v2 + 8 * v8);
      v10 = *v9;
      if ( (*v9 & 3) != 2 )
      {
        if ( (v10 & 3) != 0 || (*((_QWORD *)SpinLock + 15) & *(_QWORD *)v10) != v3 )
          break;
        *v9 = -1;
        v11 = *((_QWORD *)SpinLock + 7);
        v12 = *((_QWORD *)SpinLock + 13);
        v13 = ~(v11 << v12);
        v14 = v11 & (v3 >> v12);
        v15 = ~(*((_QWORD *)SpinLock + 8) << *((_QWORD *)SpinLock + 14)) & (v3 & v13 | ((v11 & (v14 + 1)) << v12));
        if ( v15 == *((_QWORD *)SpinLock + 22) )
          v16 = v13 & v15 | ((v11 & (v14 + 2)) << v12);
        else
          v16 = ~(*((_QWORD *)SpinLock + 8) << *((_QWORD *)SpinLock + 14)) & (v3 & v13 | ((v11 & (v14 + 1)) << v12));
        --*((_QWORD *)SpinLock + 1);
        v17 = (__int64 *)*((_QWORD *)SpinLock + 18);
        if ( v17 )
          *v17 = v16;
        v18 = *((_QWORD *)SpinLock + 17) == -1;
        *((_QWORD *)SpinLock + 18) = v9;
        if ( v18 )
          *((_QWORD *)SpinLock + 17) = v16;
        if ( (SpinLock[38] & 0x40) != 0 )
          ExReleaseSpinLockExclusive(SpinLock, v5);
        else
          ExReleasePushLockEx(SpinLock, 0);
        return v10;
      }
      v6 = (unsigned int)(v6 + 1);
      v2 = v10 & 0xFFFFFFFFFFFFFFFCuLL;
    }
  }
  if ( (SpinLock[38] & 0x40) != 0 )
    ExReleaseSpinLockExclusive(SpinLock, v5);
  else
    ExReleasePushLockEx(SpinLock, 0);
  return 0;
}

```

## disassembly

```asm
0x140006f70  push    rbx
0x140006f72  push    rsi
0x140006f73  push    rdi
0x140006f74  push    r14
0x140006f76  sub     rsp, 28h
0x140006f7a  mov     rdi, [rcx+10h]
0x140006f7e  mov     rsi, rdx
0x140006f81  and     rsi, [rcx+78h]
0x140006f85  mov     rbx, rcx
0x140006f88  test    byte ptr [rcx+98h], 40h
0x140006f8f  jnz     loc_1400070F5
0x140006f95  xor     r14b, r14b
0x140006f98  xor     edx, edx
0x140006f9a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140006fa1  nop     dword ptr [rax+rax+00h]
0x140006fa6  nop     word ptr [rax+rax+00000000h]
0x140006fb0  movzx   eax, sil
0x140006fb4  and     al, 3
0x140006fb6  cmp     al, 1
0x140006fb8  jnz     loc_1400070C5
0x140006fbe  xor     r8d, r8d
0x140006fc1  mov     rdx, [rbx+r8*8+18h]
0x140006fc6  mov     rax, rsi
0x140006fc9  mov     rcx, [rbx+r8*8+48h]
0x140006fce  shr     rax, cl
0x140006fd1  and     rax, rdx
0x140006fd4  cmp     rax, rdx
0x140006fd7  ja      loc_1400070C5
0x140006fdd  lea     rdx, [rdi+rax*8]
0x140006fe1  mov     rdi, [rdi+rax*8]
0x140006fe5  mov     rax, rdi
0x140006fe8  and     eax, 3
0x140006feb  cmp     rax, 2
0x140006fef  jnz     short loc_140006FFA
0x140006ff1  inc     r8d
0x140006ff4  and     rdi, 0FFFFFFFFFFFFFFFCh
0x140006ff8  jmp     short loc_140006FC1
0x140006ffa  test    rax, rax
0x140006ffd  jnz     loc_1400070C5
0x140007003  mov     rax, [rdi]
0x140007006  and     rax, [rbx+78h]
0x14000700a  cmp     rax, rsi
0x14000700d  jnz     loc_1400070C5
0x140007013  mov     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x14000701a  mov     r11, [rbx+38h]
0x14000701e  mov     r10, [rbx+68h]
0x140007022  mov     r9, r11
0x140007025  mov     rcx, r10
0x140007028  mov     [rsp+48h+arg_0], rbp
0x14000702d  shl     r9, cl
0x140007030  mov     rbp, rsi
0x140007033  shr     rbp, cl
0x140007036  not     r9
0x140007039  and     rbp, r11
0x14000703c  mov     rax, r9
0x14000703f  and     rax, rsi
0x140007042  lea     r8, [rbp+1]
0x140007046  and     r8, r11
0x140007049  shl     r8, cl
0x14000704c  mov     rcx, [rbx+70h]
0x140007050  or      r8, rax
0x140007053  mov     rax, [rbx+40h]
0x140007057  shl     rax, cl
0x14000705a  not     rax
0x14000705d  and     r8, rax
0x140007060  cmp     r8, [rbx+0B0h]
0x140007067  jz      loc_140007128
0x14000706d  mov     rax, r8
0x140007070  dec     qword ptr [rbx+8]
0x140007074  mov     rcx, [rbx+90h]
0x14000707b  mov     rbp, [rsp+48h+arg_0]
0x140007080  test    rcx, rcx
0x140007083  jz      short loc_140007088
0x140007085  mov     [rcx], rax
0x140007088  cmp     qword ptr [rbx+88h], 0FFFFFFFFFFFFFFFFh
0x140007090  mov     [rbx+90h], rdx
0x140007097  jz      loc_140007140
0x14000709d  test    byte ptr [rbx+98h], 40h
0x1400070a4  mov     rcx, rbx; SpinLock
0x1400070a7  jnz     short loc_14000710A
0x1400070a9  xor     edx, edx
0x1400070ab  call    cs:__imp_ExReleasePushLockEx
0x1400070b2  nop     dword ptr [rax+rax+00h]
0x1400070b7  mov     rax, rdi
0x1400070ba  add     rsp, 28h
0x1400070be  pop     r14
0x1400070c0  pop     rdi
0x1400070c1  pop     rsi
0x1400070c2  pop     rbx
0x1400070c3  retn
0x1400070c5  test    byte ptr [rbx+98h], 40h
0x1400070cc  mov     rcx, rbx; SpinLock
0x1400070cf  jz      short loc_1400070E5
0x1400070d1  movzx   edx, r14b; OldIrql
0x1400070d5  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400070dc  nop     dword ptr [rax+rax+00h]
0x1400070e1  xor     eax, eax
0x1400070e3  jmp     short loc_1400070BA
0x1400070e5  xor     edx, edx
0x1400070e7  call    cs:__imp_ExReleasePushLockEx
0x1400070ee  nop     dword ptr [rax+rax+00h]
0x1400070f3  jmp     short loc_1400070E1
0x1400070f5  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400070fc  nop     dword ptr [rax+rax+00h]
0x140007101  movzx   r14d, al
0x140007105  jmp     loc_140006FA6
0x14000710a  movzx   edx, r14b; OldIrql
0x14000710e  call    cs:__imp_ExReleaseSpinLockExclusive
0x140007115  nop     dword ptr [rax+rax+00h]
0x14000711a  mov     rax, rdi
0x14000711d  add     rsp, 28h
0x140007121  pop     r14
0x140007123  pop     rdi
0x140007124  pop     rsi
0x140007125  pop     rbx
0x140007126  retn
0x140007128  lea     rax, [rbp+2]
0x14000712c  mov     rcx, r10
0x14000712f  and     rax, r11
0x140007132  and     r8, r9
0x140007135  shl     rax, cl
0x140007138  or      rax, r8
0x14000713b  jmp     loc_140007070
0x140007140  mov     [rbx+88h], rax
0x140007147  jmp     loc_14000709D
```
