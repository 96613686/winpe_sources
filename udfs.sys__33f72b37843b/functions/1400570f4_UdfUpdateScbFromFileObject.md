# UdfUpdateScbFromFileObject

- ea: `0x1400570f4`
- end: `0x140057328`
- name: `UdfUpdateScbFromFileObject`
- size: `564`
- prototype: `__int64 __fastcall(int, int, __int64, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140055060`

## callees

- `0x140005e80`
- `0x1400062c0`
- `0x14000653c`
- `0x14000b128`
- `0x14001758c`
- `0x1400570f4`
- `0x140057330`

## pseudocode

```c
__int64 __fastcall UdfUpdateScbFromFileObject(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char v8; // r9
  int v9; // r10d
  ULONG v10; // r12d
  int v11; // r8d
  int v12; // edx
  int v13; // ecx
  ULONG v14; // ebx
  int v15; // r8d
  __int64 v16; // rcx
  char v17; // dl
  bool v18; // r14
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // r14
  _OWORD v23[2]; // [rsp+48h] [rbp-60h] BYREF
  __int64 v24; // [rsp+68h] [rbp-40h]

  memset(v23, 0, sizeof(v23));
  v24 = 0;
  v8 = HIWORD(*(_DWORD *)(a3 + 212)) & 1;
  v9 = *(_DWORD *)(a3 + 212) & 0x10;
  v10 = v9 != 0 ? 8 : 3;
  v11 = *(_DWORD *)(a4 + 4);
  v12 = (v9 != 0 ? 2048 : 4) | 0x20;
  if ( (v11 & 0x400) != 0 )
    v12 = v9 != 0 ? 2048 : 4;
  v13 = v12 | 0x10;
  if ( (v11 & 0x200) != 0 )
    v13 = v12;
  v14 = v13 | 0x20;
  if ( (v11 & 0x100) != 0 )
    v14 = v13;
  v15 = *(_DWORD *)(a2 + 80);
  if ( (v15 & 0x2000) != 0 )
  {
    v16 = *(_QWORD *)(a3 + 32);
    v17 = v8;
    if ( v16 != *(_QWORD *)(a3 + 312) )
      v17 = 1;
    v18 = v16 != *(_QWORD *)(a3 + 312);
    if ( v9 )
      v14 |= 0x400u;
    else
      v14 |= 8u;
  }
  else
  {
    v18 = 0;
    v17 = v8;
  }
  if ( (v15 & 0x1000) != 0 )
  {
    v19 = *(_DWORD *)(a3 + 220);
    if ( (v19 & 0x20) == 0 )
    {
      *(_DWORD *)(a3 + 220) = v19 | 0x20;
      v17 = 1;
    }
  }
  if ( v17 )
  {
    UdfMarkVolumeOpenAndQueueCloseDpc(a1);
    v23[0] = 0;
    UdfPrepareModifyIcbForScb(a1, a3, v23);
    if ( v18 )
    {
      v20 = *(_QWORD *)&v23[0];
      v21 = *(_QWORD *)(a3 + 32) - *(_QWORD *)(*(_QWORD *)&v23[0] + 56LL);
      *(_QWORD *)(*(_QWORD *)&v23[0] + 56LL) = *(_QWORD *)(a3 + 32);
      if ( *(_WORD *)v20 == 266 )
        *(_QWORD *)(v20 + 64) += v21;
      if ( (*(_DWORD *)(a3 + 212) & 0x80000) != 0 )
        *(_WORD *)(v20 + 34) &= 0xFFF8u;
    }
    else
    {
      v21 = 0;
    }
    UdfFinishModifyIcb(a1, (__int64)v23, 1, (__int16 *)a3);
    if ( (*(_DWORD *)(a3 + 212) & 0x10) != 0 && v21 )
    {
      UdfPrepareModifyIcbForScb(a1, *(_QWORD *)(*(_QWORD *)(a3 + 136) + 16LL), v23);
      *(_QWORD *)(*(_QWORD *)&v23[0] + 64LL) += v21;
      UdfFinishModifyIcb(a1, (__int64)v23, 1, *(__int16 **)(*(_QWORD *)(a3 + 136) + 16LL));
    }
    UdfUnpinView(a1, v23);
  }
  return UdfNotifyReportChange(a1, a4, *(_QWORD *)(a4 + 16), a2, a3, v14, v10);
}

```

## disassembly

```asm
0x1400570f4  mov     r11, rsp
0x1400570f7  mov     [r11+20h], r9
0x1400570fb  mov     [r11+18h], r8
0x1400570ff  mov     [r11+10h], rdx
0x140057103  mov     [r11+8], rcx
0x140057107  push    rbx
0x140057108  push    rsi
0x140057109  push    rdi
0x14005710a  push    r12
0x14005710c  push    r13
0x14005710e  push    r14
0x140057110  push    r15
0x140057112  sub     rsp, 70h
0x140057116  mov     r15, r9
0x140057119  mov     rdi, r8
0x14005711c  mov     r13, rdx
0x14005711f  mov     rsi, rcx
0x140057122  xorps   xmm0, xmm0
0x140057125  xor     eax, eax
0x140057127  movups  [rsp+0A8h+var_60], xmm0
0x14005712c  movups  [rsp+0A8h+var_50], xmm0
0x140057131  mov     [r11-40h], rax
0x140057135  mov     r10d, [r8+0D4h]
0x14005713c  mov     r9d, r10d
0x14005713f  shr     r9d, 10h
0x140057143  lea     r11d, [rax+1]
0x140057147  and     r9b, r11b
0x14005714a  and     r10d, 10h
0x14005714e  mov     eax, r10d
0x140057151  neg     eax
0x140057153  sbb     r12d, r12d
0x140057156  and     r12d, 5
0x14005715a  add     r12d, 3
0x14005715e  mov     [rsp+0A8h+var_64], r12d
0x140057163  mov     eax, r10d
0x140057166  neg     eax
0x140057168  sbb     ecx, ecx
0x14005716a  and     ecx, 7FCh
0x140057170  add     ecx, 4
0x140057173  mov     r8d, [r15+4]
0x140057177  mov     edx, ecx
0x140057179  or      edx, 20h
0x14005717c  bt      r8d, 0Ah
0x140057181  cmovb   edx, ecx
0x140057184  mov     ecx, edx
0x140057186  or      ecx, 10h
0x140057189  bt      r8d, 9
0x14005718e  cmovb   ecx, edx
0x140057191  mov     ebx, ecx
0x140057193  or      ebx, 20h
0x140057196  bt      r8d, 8
0x14005719b  cmovb   ebx, ecx
0x14005719e  mov     r8d, [r13+50h]
0x1400571a2  bt      r8d, 0Dh
0x1400571a7  jnb     short loc_1400571D0
0x1400571a9  mov     rcx, [rdi+20h]
0x1400571ad  movzx   edx, r9b
0x1400571b1  cmp     rcx, [rdi+138h]
0x1400571b8  cmovnz  edx, r11d
0x1400571bc  setnz   r14b
0x1400571c0  test    r10d, r10d
0x1400571c3  jz      short loc_1400571CB
0x1400571c5  bts     ebx, 0Ah
0x1400571c9  jmp     short loc_1400571D6
0x1400571cb  or      ebx, 8
0x1400571ce  jmp     short loc_1400571D6
0x1400571d0  xor     r14b, r14b
0x1400571d3  mov     dl, r9b
0x1400571d6  mov     [rsp+0A8h+var_68], ebx
0x1400571da  bt      r8d, 0Ch
0x1400571df  jnb     short loc_1400571F7
0x1400571e1  mov     eax, [rdi+0DCh]
0x1400571e7  test    al, 20h
0x1400571e9  jnz     short loc_1400571F7
0x1400571eb  or      eax, 20h
0x1400571ee  mov     [rdi+0DCh], eax
0x1400571f4  mov     dl, r11b
0x1400571f7  test    dl, dl
0x1400571f9  jz      loc_1400572F7
0x1400571ff  mov     rcx, rsi
0x140057202  call    UdfMarkVolumeOpenAndQueueCloseDpc
0x140057207  xorps   xmm0, xmm0
0x14005720a  movdqu  [rsp+0A8h+var_60], xmm0
0x140057210  lea     r8, [rsp+0A8h+var_60]
0x140057215  mov     rdx, rdi
0x140057218  mov     rcx, rsi
0x14005721b  call    UdfPrepareModifyIcbForScb
0x140057220  test    r14b, r14b
0x140057223  jz      short loc_14005725E
0x140057225  mov     rcx, qword ptr [rsp+0A8h+var_60]
0x14005722a  mov     rax, [rdi+20h]
0x14005722e  mov     r14, rax
0x140057231  sub     r14, [rcx+38h]
0x140057235  mov     [rcx+38h], rax
0x140057239  mov     eax, 10Ah
0x14005723e  cmp     [rcx], ax
0x140057241  jnz     short loc_140057247
0x140057243  add     [rcx+40h], r14
0x140057247  test    dword ptr [rdi+0D4h], 80000h
0x140057251  jz      short loc_140057261
0x140057253  mov     eax, 0FFF8h
0x140057258  and     [rcx+22h], ax
0x14005725c  jmp     short loc_140057261
0x14005725e  xor     r14d, r14d
0x140057261  mov     r9, rdi
0x140057264  mov     r8b, 1
0x140057267  lea     rdx, [rsp+0A8h+var_60]
0x14005726c  mov     rcx, rsi
0x14005726f  call    UdfFinishModifyIcb
0x140057274  mov     eax, [rdi+0D4h]
0x14005727a  test    al, 10h
0x14005727c  jz      short loc_1400572BF
0x14005727e  test    r14, r14
0x140057281  jz      short loc_1400572BF
0x140057283  mov     rdx, [rdi+88h]
0x14005728a  lea     r8, [rsp+0A8h+var_60]
0x14005728f  mov     rdx, [rdx+10h]
0x140057293  mov     rcx, rsi
0x140057296  call    UdfPrepareModifyIcbForScb
0x14005729b  mov     rax, qword ptr [rsp+0A8h+var_60]
0x1400572a0  add     [rax+40h], r14
0x1400572a4  mov     r9, [rdi+88h]
0x1400572ab  mov     r9, [r9+10h]
0x1400572af  mov     r8b, 1
0x1400572b2  lea     rdx, [rsp+0A8h+var_60]
0x1400572b7  mov     rcx, rsi
0x1400572ba  call    UdfFinishModifyIcb
0x1400572bf  jmp     short loc_1400572EA
0x1400572c1  mov     r15, [rsp+0A8h+arg_18]
0x1400572c9  mov     rdi, [rsp+0A8h+arg_10]
0x1400572d1  mov     r13, [rsp+0A8h+arg_8]
0x1400572d9  mov     rsi, [rsp+0A8h+arg_0]
0x1400572e1  mov     ebx, [rsp+0A8h+var_68]
0x1400572e5  mov     r12d, [rsp+0A8h+var_64]
0x1400572ea  lea     rdx, [rsp+0A8h+var_60]
0x1400572ef  mov     rcx, rsi
0x1400572f2  call    UdfUnpinView
0x1400572f7  mov     [rsp+0A8h+var_78], r12d; ULONG
0x1400572fc  mov     [rsp+0A8h+var_80], ebx; ULONG
0x140057300  mov     [rsp+0A8h+var_88], rdi; __int64
0x140057305  mov     r9, r13; int
0x140057308  mov     r8, [r15+10h]; int
0x14005730c  mov     rdx, r15; int
0x14005730f  mov     rcx, rsi; int
0x140057312  call    UdfNotifyReportChange
0x140057317  add     rsp, 70h
0x14005731b  pop     r15
0x14005731d  pop     r14
0x14005731f  pop     r13
0x140057321  pop     r12
0x140057323  pop     rdi
0x140057324  pop     rsi
0x140057325  pop     rbx
0x140057326  retn
0x14005ae32  push    rbp
0x14005ae34  sub     rsp, 40h
0x14005ae38  mov     rbp, rdx
0x14005ae3b  mov     rdx, rcx
0x14005ae3e  mov     rcx, [rbp+0B0h]
0x14005ae45  call    UdfExceptionFilter
0x14005ae4a  nop
0x14005ae4b  add     rsp, 40h
0x14005ae4f  pop     rbp
0x14005ae50  retn
```
