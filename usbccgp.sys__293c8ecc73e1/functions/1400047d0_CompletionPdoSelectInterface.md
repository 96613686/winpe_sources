# CompletionPdoSelectInterface

- ea: `0x1400047d0`
- end: `0x1400049ba`
- name: `CompletionPdoSelectInterface`
- size: `490`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1400047d0`
- `0x1400049c0`
- `0x1400054a0`
- `0x14000a6cc`
- `0x14000b4bc`
- `0x140010c08`
- `0x140014e00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000494a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000494a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140004925`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140004925`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004819`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004819`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400048f3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400048f3`

## pseudocode

```c
__int64 __fastcall CompletionPdoSelectInterface(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v4; // rax
  int v6; // r12d
  __int64 v7; // rbp
  __int64 v8; // rdi
  KIRQL v9; // al
  int v10; // edx
  __int64 v11; // rcx
  _QWORD *v12; // r14
  _BYTE *v13; // rdi
  char v14; // al
  int v15; // r9d
  void *v16; // rcx
  void *v17; // rax
  char v19; // [rsp+28h] [rbp-60h]
  KIRQL NewIrql; // [rsp+98h] [rbp+10h]

  v4 = *(_QWORD *)(a2 + 184);
  v6 = *(_DWORD *)(a2 + 48);
  v7 = a3[29];
  v8 = *(_QWORD *)(v4 + 8);
  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(v4 + 3) |= 1u;
  if ( v6 >= 0 )
  {
    v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v7 + 80));
    v11 = 32;
    v12 = *(_QWORD **)(v7 + 88);
    NewIrql = v9;
    if ( *(_WORD *)(v8 + 2) != 1 )
      v11 = 48;
    v13 = (_BYTE *)(v11 + v8);
    while ( 1 )
    {
      if ( !*v12 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_19;
        v19 = v13[2];
        v15 = 31;
        goto LABEL_12;
      }
      v14 = v13[2];
      if ( *(_BYTE *)(*v12 + 2LL) == v14 )
        break;
      v12 += 2;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 4;
      WPP_RECORDER_SF_qD(a3[49], v10, 1, 29, (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids, a3[28], v14);
    }
    v16 = (void *)v12[1];
    if ( v16 )
      ExFreePoolWithTag(v16, 0x43627355u);
    v17 = (void *)MemDup(v13, *(unsigned __int16 *)v13);
    v12[1] = v17;
    if ( v17 )
    {
      memmove(v17, v13, *(unsigned __int16 *)v13);
      goto LABEL_19;
    }
    *(_DWORD *)(a2 + 48) = -1073741670;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = 30;
      v19 = v6;
LABEL_12:
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_d(a3[49], v10, 8, v15, (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids, v19);
    }
LABEL_19:
    KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 80), NewIrql);
  }
  UsbcDecrementPendingCount(v7, a2);
  UsbcReleaseRemoveLock(v7, a2);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v7 + 200), (PVOID)a2, 0x20u);
  return 0;
}

```

## disassembly

```asm
0x1400047d0  push    rbx
0x1400047d2  push    rbp
0x1400047d3  push    rsi
0x1400047d4  push    rdi
0x1400047d5  push    r12
0x1400047d7  push    r13
0x1400047d9  push    r14
0x1400047db  push    r15
0x1400047dd  sub     rsp, 48h
0x1400047e1  cmp     byte ptr [rdx+41h], 0
0x1400047e5  mov     r13, r8
0x1400047e8  mov     rax, [rdx+0B8h]
0x1400047ef  mov     rbx, rdx
0x1400047f2  mov     r12d, [rdx+30h]
0x1400047f6  mov     esi, 1
0x1400047fb  mov     rbp, [r8+0E8h]
0x140004802  mov     rdi, [rax+8]
0x140004806  jnz     loc_14000498D
0x14000480c  test    r12d, r12d
0x14000480f  js      loc_1400048FF
0x140004815  lea     rcx, [rbp+50h]; SpinLock
0x140004819  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004820  nop     dword ptr [rax+rax+00h]
0x140004825  cmp     [rdi+2], si
0x140004829  mov     ecx, 20h ; ' '
0x14000482e  mov     r14, [rbp+58h]
0x140004832  mov     [rsp+88h+NewIrql], al
0x140004839  lea     eax, [rcx+10h]
0x14000483c  cmovnz  ecx, eax
0x14000483f  add     rdi, rcx
0x140004842  mov     rcx, [r14]
0x140004845  test    rcx, rcx
0x140004848  jz      short loc_140004859
0x14000484a  movzx   eax, byte ptr [rdi+2]
0x14000484e  cmp     [rcx+2], al
0x140004851  jz      short loc_140004899
0x140004853  add     r14, 10h
0x140004857  jmp     short loc_140004842
0x140004859  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140004860  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140004867  jz      short loc_1400048E8
0x140004869  movzx   eax, byte ptr [rdi+2]
0x14000486d  lea     r15, WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids
0x140004874  mov     dword ptr [rsp+88h+var_60], eax
0x140004878  mov     r9d, 1Fh
0x14000487e  mov     rcx, [r13+188h]
0x140004885  mov     r8d, 8
0x14000488b  mov     dl, 2
0x14000488d  mov     [rsp+88h+var_68], r15
0x140004892  call    WPP_RECORDER_SF_d
0x140004897  jmp     short loc_1400048E8
0x140004899  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400048a0  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400048a7  lea     r15, WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids
0x1400048ae  jnz     loc_14000495B
0x1400048b4  mov     rcx, [r14+8]; P
0x1400048b8  test    rcx, rcx
0x1400048bb  jnz     loc_140004945
0x1400048c1  movzx   edx, word ptr [rdi]; Size
0x1400048c4  mov     rcx, rdi; Src
0x1400048c7  call    MemDup
0x1400048cc  mov     [r14+8], rax
0x1400048d0  test    rax, rax
0x1400048d3  jz      loc_140004996
0x1400048d9  movzx   r8d, word ptr [rdi]; Size
0x1400048dd  mov     rdx, rdi; Src
0x1400048e0  mov     rcx, rax; void *
0x1400048e3  call    memmove
0x1400048e8  mov     dl, [rsp+88h+NewIrql]; NewIrql
0x1400048ef  lea     rcx, [rbp+50h]; SpinLock
0x1400048f3  call    cs:__imp_KeReleaseSpinLock
0x1400048fa  nop     dword ptr [rax+rax+00h]
0x1400048ff  mov     rdx, rbx
0x140004902  mov     rcx, rbp
0x140004905  call    UsbcDecrementPendingCount
0x14000490a  mov     rdx, rbx
0x14000490d  mov     rcx, rbp
0x140004910  call    UsbcReleaseRemoveLock
0x140004915  lea     rcx, [rbp+0C8h]; RemoveLock
0x14000491c  mov     r8d, 20h ; ' '; RemlockSize
0x140004922  mov     rdx, rbx; Tag
0x140004925  call    cs:__imp_IoReleaseRemoveLockEx
0x14000492c  nop     dword ptr [rax+rax+00h]
0x140004931  xor     eax, eax
0x140004933  add     rsp, 48h
0x140004937  pop     r15
0x140004939  pop     r14
0x14000493b  pop     r13
0x14000493d  pop     r12
0x14000493f  pop     rdi
0x140004940  pop     rsi
0x140004941  pop     rbp
0x140004942  pop     rbx
0x140004943  retn
0x140004945  mov     edx, 43627355h; Tag
0x14000494a  call    cs:__imp_ExFreePoolWithTag
0x140004951  nop     dword ptr [rax+rax+00h]
0x140004956  jmp     loc_1400048C1
0x14000495b  mov     rcx, [r13+188h]
0x140004962  mov     r9d, 1Dh
0x140004968  mov     [rsp+88h+var_58], eax
0x14000496c  mov     dl, 4
0x14000496e  mov     rax, [r13+0E0h]
0x140004975  mov     [rsp+88h+var_60], rax
0x14000497a  lea     r8d, [r9-1Ch]
0x14000497e  mov     [rsp+88h+var_68], r15
0x140004983  call    WPP_RECORDER_SF_qD
0x140004988  jmp     loc_1400048B4
0x14000498d  or      [rax+3], sil
0x140004991  jmp     loc_14000480C
0x140004996  mov     dword ptr [rbx+30h], 0C000009Ah
0x14000499d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400049a4  jz      loc_1400048E8
0x1400049aa  mov     r9d, 1Eh
0x1400049b0  mov     dword ptr [rsp+88h+var_60], r12d
0x1400049b5  jmp     loc_14000487E
```
