# RtlpHpSegPageRangeCommit

- ea: `0x1400ccd44`
- end: `0x1400ccf03`
- name: `RtlpHpSegPageRangeCommit`
- size: `447`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400c8d4c`
- `0x1400cb50c`
- `0x1400ccb30`
- `0x1400cd78c`
- `0x1400cd890`

## callees

- `0x1400cbf34`
- `0x1400ccd44`
- `0x1400ccfe4`

## pseudocode

```c
__int64 __fastcall RtlpHpSegPageRangeCommit(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        _DWORD *a6)
{
  unsigned int v7; // esi
  unsigned int v10; // r13d
  int v11; // edx
  int v12; // r8d
  unsigned int v13; // r12d
  int v14; // r14d
  unsigned int v15; // r15d
  int v16; // eax
  unsigned __int64 v17; // rbx
  unsigned int v18; // eax
  __int64 result; // rax
  int v20; // [rsp+40h] [rbp-58h]
  int v21; // [rsp+A0h] [rbp+8h]
  int v22; // [rsp+A8h] [rbp+10h]
  unsigned int v23; // [rsp+B0h] [rbp+18h] BYREF
  unsigned int v24; // [rsp+B8h] [rbp+20h] BYREF

  v7 = a3;
  v21 = (a5 >> 22) & 2;
  v10 = a3 + a4;
  v11 = (*(_BYTE *)(a1 + 13) & 7) == 0 ? 0x7FFF : 511;
  v12 = 0;
  v13 = (unsigned int)((a2 - (a2 & *(_QWORD *)a1)) >> 5) << *(_BYTE *)(a1 + 9);
  v22 = v11;
  if ( a4 <= 0 )
    v12 = 2;
  v20 = v12;
  if ( a4 <= 0 )
    v10 = v7 - a4;
  v14 = 0;
  while ( v7 < v10 )
  {
    v23 = v7;
    v15 = v11 - (v11 & (v7 + v13)) + 1;
    if ( v15 >= v10 - v7 )
      v15 = v10 - v7;
    v24 = v15;
    v16 = RtlpHpSegPageRangeHandleCommit(a1, a2, (unsigned int)&v23, (unsigned int)&v24, v12);
    v17 = v16;
    if ( v16 )
    {
      if ( v16 > 0 )
      {
        v18 = 4096;
        if ( (a5 & 2) != 0 )
          v18 = 1073745920;
      }
      else
      {
        v18 = 0x4000;
      }
      result = RtlpHpSegMgrCommit((int *)a1, a2 & *(_QWORD *)a1, v13 + v23, v24, v17, v18, v21);
      if ( (int)result < 0 )
        return result;
      if ( (int)v17 > 0 )
        RtlpHpSegPageRangeHandleCommit(a1, a2, (unsigned int)&v23, (unsigned int)&v24, 1);
      _InterlockedAdd64((volatile signed __int64 *)(*(__int16 *)(a1 + 22) + a1 + 8), v17);
      *(_WORD *)(a2 + 28) = ~(v17 + ~*(_WORD *)(a2 + 28));
    }
    v11 = v22;
    v7 += v15;
    v12 = v20;
    v14 += v17;
  }
  if ( a6 )
    *a6 = v14;
  return 0;
}

```

## disassembly

```asm
0x1400ccd44  push    rbx
0x1400ccd46  push    rbp
0x1400ccd47  push    rsi
0x1400ccd48  push    rdi
0x1400ccd49  push    r12
0x1400ccd4b  push    r13
0x1400ccd4d  push    r14
0x1400ccd4f  push    r15
0x1400ccd51  sub     rsp, 58h
0x1400ccd55  mov     eax, [rsp+98h+arg_20]
0x1400ccd5c  mov     rbp, rdx
0x1400ccd5f  shr     eax, 16h
0x1400ccd62  mov     esi, r8d
0x1400ccd65  mov     r10d, 2
0x1400ccd6b  mov     r12, rbp
0x1400ccd6e  and     eax, r10d
0x1400ccd71  mov     rdi, rcx
0x1400ccd74  mov     [rsp+98h+arg_0], eax
0x1400ccd7b  mov     al, [rcx+0Dh]
0x1400ccd7e  lea     r13d, [rsi+r9]
0x1400ccd82  and     al, 7
0x1400ccd84  cmp     al, 1
0x1400ccd86  mov     rax, [rcx]
0x1400ccd89  mov     cl, [rcx+9]
0x1400ccd8c  sbb     edx, edx
0x1400ccd8e  and     rax, rbp
0x1400ccd91  sub     r12, rax
0x1400ccd94  and     edx, 7E00h
0x1400ccd9a  sar     r12, 5
0x1400ccd9e  add     edx, 1FFh
0x1400ccda4  xor     r8d, r8d
0x1400ccda7  shl     r12d, cl
0x1400ccdaa  test    r9d, r9d
0x1400ccdad  mov     [rsp+98h+arg_8], edx
0x1400ccdb4  mov     eax, esi
0x1400ccdb6  cmovle  r8d, r10d
0x1400ccdba  sub     eax, r9d
0x1400ccdbd  test    r9d, r9d
0x1400ccdc0  mov     [rsp+98h+var_58], r8d
0x1400ccdc5  cmovle  r13d, eax
0x1400ccdc9  xor     r14d, r14d
0x1400ccdcc  jmp     loc_1400CCED6
0x1400ccdd1  mov     r15d, edx
0x1400ccdd4  mov     [rsp+98h+var_78], r8d
0x1400ccdd9  lea     ecx, [rsi+r12]
0x1400ccddd  mov     [rsp+98h+arg_10], esi
0x1400ccde4  and     ecx, edx
0x1400ccde6  lea     r9, [rsp+98h+arg_18]
0x1400ccdee  sub     r15d, ecx
0x1400ccdf1  lea     r8, [rsp+98h+arg_10]
0x1400ccdf9  mov     eax, r13d
0x1400ccdfc  inc     r15d
0x1400ccdff  sub     eax, esi
0x1400cce01  mov     rdx, rbp
0x1400cce04  cmp     r15d, eax
0x1400cce07  mov     rcx, rdi
0x1400cce0a  cmovnb  r15d, eax
0x1400cce0e  mov     [rsp+98h+arg_18], r15d
0x1400cce16  call    RtlpHpSegPageRangeHandleCommit
0x1400cce1b  movsxd  rbx, eax
0x1400cce1e  test    eax, eax
0x1400cce20  jz      loc_1400CCEC4
0x1400cce26  mov     rdx, [rdi]
0x1400cce29  mov     r8d, [rsp+98h+arg_10]
0x1400cce31  and     rdx, rbp
0x1400cce34  add     r8d, r12d
0x1400cce37  test    eax, eax
0x1400cce39  jg      short loc_1400CCE42
0x1400cce3b  mov     eax, 4000h
0x1400cce40  jmp     short loc_1400CCE57
0x1400cce42  test    byte ptr [rsp+98h+arg_20], 2
0x1400cce4a  mov     eax, 1000h
0x1400cce4f  mov     ecx, 40001000h
0x1400cce54  cmovnz  eax, ecx
0x1400cce57  mov     ecx, [rsp+98h+arg_0]
0x1400cce5e  mov     r9d, [rsp+98h+arg_18]
0x1400cce66  mov     [rsp+98h+var_68], ecx
0x1400cce6a  mov     rcx, rdi
0x1400cce6d  mov     [rsp+98h+var_70], eax
0x1400cce71  mov     [rsp+98h+var_78], ebx
0x1400cce75  call    RtlpHpSegMgrCommit
0x1400cce7a  test    eax, eax
0x1400cce7c  js      short loc_1400CCEF1
0x1400cce7e  test    ebx, ebx
0x1400cce80  jle     short loc_1400CCEA5
0x1400cce82  lea     r9, [rsp+98h+arg_18]
0x1400cce8a  mov     [rsp+98h+var_78], 1
0x1400cce92  lea     r8, [rsp+98h+arg_10]
0x1400cce9a  mov     rdx, rbp
0x1400cce9d  mov     rcx, rdi
0x1400ccea0  call    RtlpHpSegPageRangeHandleCommit
0x1400ccea5  movsx   rax, word ptr [rdi+16h]
0x1400cceaa  mov     rcx, rbx
0x1400ccead  lock add [rax+rdi+8], rcx
0x1400cceb3  movzx   eax, word ptr [rbp+1Ch]
0x1400cceb7  not     ax
0x1400cceba  add     ax, bx
0x1400ccebd  not     ax
0x1400ccec0  mov     [rbp+1Ch], ax
0x1400ccec4  mov     edx, [rsp+98h+arg_8]
0x1400ccecb  add     esi, r15d
0x1400ccece  mov     r8d, [rsp+98h+var_58]
0x1400cced3  add     r14d, ebx
0x1400cced6  cmp     esi, r13d
0x1400cced9  jb      loc_1400CCDD1
0x1400ccedf  mov     rax, [rsp+98h+arg_28]
0x1400ccee7  test    rax, rax
0x1400cceea  jz      short loc_1400CCEEF
0x1400cceec  mov     [rax], r14d
0x1400cceef  xor     eax, eax
0x1400ccef1  add     rsp, 58h
0x1400ccef5  pop     r15
0x1400ccef7  pop     r14
0x1400ccef9  pop     r13
0x1400ccefb  pop     r12
0x1400ccefd  pop     rdi
0x1400ccefe  pop     rsi
0x1400cceff  pop     rbp
0x1400ccf00  pop     rbx
0x1400ccf01  retn
```
