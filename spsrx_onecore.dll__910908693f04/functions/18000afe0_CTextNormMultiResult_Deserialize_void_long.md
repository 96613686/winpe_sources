# CTextNormMultiResult::Deserialize(void *,long)

- ea: `0x18000afe0`
- end: `0x18000b1ff`
- name: `?Deserialize@CTextNormMultiResult@@UEAAJPEAXJ@Z`
- size: `543`
- prototype: `__int64 __fastcall(CTextNormMultiResult *this, unsigned __int8 *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180001c50`
- `0x180002ec0`
- `0x180002ecc`
- `0x180008e98`
- `0x180008fa4`
- `0x18000afe0`
- `0x18000b208`
- `0x18000e06c`

## pseudocode

```c
__int64 __fastcall CTextNormMultiResult::Deserialize(CTextNormMultiResult *this, unsigned __int8 *a2, int a3)
{
  int v6; // ebx
  unsigned __int8 *v7; // r14
  unsigned __int64 v8; // rsi
  int *v9; // r12
  unsigned __int64 v10; // rax
  void *v11; // rax
  int v12; // r15d
  __int64 v13; // rdx
  int v14; // r15d
  void *v15; // rdx
  unsigned __int8 *v17; // [rsp+30h] [rbp-10h] BYREF
  __int64 v18; // [rsp+38h] [rbp-8h]
  int v19; // [rsp+78h] [rbp+38h] BYREF
  int v20; // [rsp+88h] [rbp+48h] BYREF

  v17 = 0;
  v20 = 0;
  v18 = 0;
  if ( !a2 || a3 <= 0 )
    goto LABEL_25;
  v17 = a2;
  v19 = 0;
  v6 = SafeMemCopyAndAdvanceInput<long>(&v19, &v17, &a2[a3]);
  if ( v6 < 0 )
    goto LABEL_26;
  if ( v19 > a3 || v19 < 0 )
  {
LABEL_25:
    v6 = -2147024809;
    goto LABEL_26;
  }
  v7 = &a2[v19];
  v6 = SafeMemCopyAndAdvanceInput<long>((char *)this + 116, &v17, v7);
  if ( v6 < 0 )
    goto LABEL_26;
  v6 = SafeMemCopyAndAdvanceInput<long>((char *)this + 112, &v17, v7);
  if ( v6 < 0 )
    goto LABEL_26;
  v6 = SafeMemCopyAndAdvanceInput<long>(&v20, &v17, v7);
  if ( v6 < 0 )
    goto LABEL_26;
  v8 = v20;
  if ( v20 < 1 )
    goto LABEL_10;
  v9 = (int *)((char *)this + 120);
  v6 = SafeMemCopyAndAdvanceInput<long>((char *)this + 120, &v17, v7);
  if ( v6 < 0 )
    goto LABEL_26;
  if ( *v9 < 0 || *v9 >= (int)v8 )
  {
LABEL_10:
    v6 = -2147418113;
  }
  else
  {
    v10 = 8 * v8;
    if ( !is_mul_ok(v8, 8u) )
      v10 = -1;
    v11 = operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
    *((_QWORD *)this + 13) = v11;
    if ( v11 )
    {
      memset_0(v11, 0, 8 * v8);
      v12 = 0;
      if ( (int)v8 <= 0 )
      {
LABEL_21:
        v14 = 0;
        if ( (int)v8 <= 0 )
        {
LABEL_24:
          *((_QWORD *)this + 12) = *(_QWORD *)(*((_QWORD *)this + 13) + 8LL * *v9);
          *((_DWORD *)this + 17) = 1;
          return (unsigned int)v6;
        }
        while ( 1 )
        {
          v6 = CTnMultiResNode::Deserialize(
                 *(CTnMultiResNode **)(*((_QWORD *)this + 13) + 8LL * v14),
                 &v17,
                 *((struct CTnMultiResNode ***)this + 13),
                 v7,
                 v8);
          if ( v6 < 0 )
            break;
          if ( ++v14 >= (int)v8 )
            goto LABEL_24;
        }
      }
      else
      {
        while ( 1 )
        {
          v6 = CSpClassFactory::CreateProduct<CTnMultiResNode>(*((CSpClassFactory **)this + 11));
          if ( v6 < 0 )
            break;
          v13 = v12++;
          *(_QWORD *)(*((_QWORD *)this + 13) + 8 * v13) = v18;
          if ( v12 >= (int)v8 )
            goto LABEL_21;
        }
      }
    }
    else
    {
      v6 = -2147024882;
    }
  }
LABEL_26:
  CSpClassFactory::RemoveAll(*((CSpClassFactory **)this + 11));
  v15 = (void *)*((_QWORD *)this + 13);
  if ( v15 )
    CWinHeap::Free((CWinHeap *)&g_heap, v15);
  *((_QWORD *)this + 13) = 0;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000afe0  mov     [rsp-28h+arg_0], rbx
0x18000afe5  mov     [rsp-28h+arg_10], rsi
0x18000afea  push    rbp
0x18000afeb  push    rdi
0x18000afec  push    r12
0x18000afee  push    r14
0x18000aff0  push    r15
0x18000aff2  mov     rbp, rsp
0x18000aff5  sub     rsp, 40h
0x18000aff9  movsxd  r14, r8d
0x18000affc  mov     rsi, rdx
0x18000afff  mov     [rbp+var_10], 0
0x18000b007  mov     rdi, rcx
0x18000b00a  mov     [rbp+arg_18], 0
0x18000b011  mov     [rbp+var_8], 0
0x18000b019  test    rdx, rdx
0x18000b01c  jz      loc_18000B1B9
0x18000b022  test    r8d, r8d
0x18000b025  jle     loc_18000B1B9
0x18000b02b  mov     [rbp+var_10], rdx
0x18000b02f  lea     r8, [rdx+r14]
0x18000b033  lea     rdx, [rbp+var_10]
0x18000b037  mov     [rbp+arg_8], 0
0x18000b03e  lea     rcx, [rbp+arg_8]
0x18000b042  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000b047  mov     ebx, eax
0x18000b049  test    eax, eax
0x18000b04b  js      loc_18000B1BE
0x18000b051  movsxd  rax, [rbp+arg_8]
0x18000b055  cmp     eax, r14d
0x18000b058  jg      loc_18000B1B9
0x18000b05e  test    eax, eax
0x18000b060  js      loc_18000B1B9
0x18000b066  lea     r14, [rsi+rax]
0x18000b06a  mov     r8, r14
0x18000b06d  lea     rcx, [rdi+74h]
0x18000b071  lea     rdx, [rbp+var_10]
0x18000b075  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000b07a  mov     ebx, eax
0x18000b07c  test    eax, eax
0x18000b07e  js      loc_18000B1BE
0x18000b084  lea     rcx, [rdi+70h]
0x18000b088  mov     r8, r14
0x18000b08b  lea     rdx, [rbp+var_10]
0x18000b08f  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000b094  mov     ebx, eax
0x18000b096  test    eax, eax
0x18000b098  js      loc_18000B1BE
0x18000b09e  mov     r8, r14
0x18000b0a1  lea     rdx, [rbp+var_10]
0x18000b0a5  lea     rcx, [rbp+arg_18]
0x18000b0a9  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000b0ae  mov     ebx, eax
0x18000b0b0  test    eax, eax
0x18000b0b2  js      loc_18000B1BE
0x18000b0b8  movsxd  rsi, [rbp+arg_18]
0x18000b0bc  cmp     esi, 1
0x18000b0bf  jge     short loc_18000B0CB
0x18000b0c1  mov     ebx, 8000FFFFh
0x18000b0c6  jmp     loc_18000B1BE
0x18000b0cb  lea     r12, [rdi+78h]
0x18000b0cf  mov     r8, r14
0x18000b0d2  mov     rcx, r12
0x18000b0d5  lea     rdx, [rbp+var_10]
0x18000b0d9  call    ??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)
0x18000b0de  mov     ebx, eax
0x18000b0e0  test    eax, eax
0x18000b0e2  js      loc_18000B1BE
0x18000b0e8  cmp     dword ptr [r12], 0
0x18000b0ed  jl      short loc_18000B0C1
0x18000b0ef  cmp     [r12], esi
0x18000b0f3  jge     short loc_18000B0C1
0x18000b0f5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b0fc  mov     eax, 8
0x18000b101  mul     rsi
0x18000b104  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b10b  cmovb   rax, rcx
0x18000b10f  mov     rcx, rax; unsigned __int64
0x18000b112  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000b117  mov     [rdi+68h], rax
0x18000b11b  test    rax, rax
0x18000b11e  jnz     short loc_18000B12A
0x18000b120  mov     ebx, 8007000Eh
0x18000b125  jmp     loc_18000B1BE
0x18000b12a  lea     r8, ds:0[rsi*8]; Size
0x18000b132  xor     edx, edx; Val
0x18000b134  mov     rcx, rax; void *
0x18000b137  call    memset_0
0x18000b13c  xor     r15d, r15d
0x18000b13f  test    esi, esi
0x18000b141  jle     short loc_18000B16D
0x18000b143  mov     rcx, [rdi+58h]; this
0x18000b147  lea     rdx, [rbp+var_8]
0x18000b14b  call    ??$CreateProduct@VCTnMultiResNode@@@CSpClassFactory@@QEAAJPEAPEAVCTnMultiResNode@@@Z; CSpClassFactory::CreateProduct<CTnMultiResNode>(CTnMultiResNode * *)
0x18000b150  mov     ebx, eax
0x18000b152  test    eax, eax
0x18000b154  js      short loc_18000B1BE
0x18000b156  mov     rcx, [rdi+68h]
0x18000b15a  mov     rax, [rbp+var_8]
0x18000b15e  movsxd  rdx, r15d
0x18000b161  inc     r15d
0x18000b164  mov     [rcx+rdx*8], rax
0x18000b168  cmp     r15d, esi
0x18000b16b  jl      short loc_18000B143
0x18000b16d  xor     r15d, r15d
0x18000b170  test    esi, esi
0x18000b172  jle     short loc_18000B1A0
0x18000b174  mov     rax, [rdi+68h]
0x18000b178  lea     rdx, [rbp+var_10]; unsigned __int8 **
0x18000b17c  movsxd  rcx, r15d
0x18000b17f  mov     r9, r14; unsigned __int8 *
0x18000b182  mov     r8, rax; struct CTnMultiResNode **
0x18000b185  mov     [rsp+40h+var_20], esi; int
0x18000b189  mov     rcx, [rax+rcx*8]; this
0x18000b18d  call    ?Deserialize@CTnMultiResNode@@QEAAJAEAPEAEPEAPEAV1@PEAEJ@Z; CTnMultiResNode::Deserialize(uchar * &,CTnMultiResNode * *,uchar *,long)
0x18000b192  mov     ebx, eax
0x18000b194  test    eax, eax
0x18000b196  js      short loc_18000B1BE
0x18000b198  inc     r15d
0x18000b19b  cmp     r15d, esi
0x18000b19e  jl      short loc_18000B174
0x18000b1a0  movsxd  rcx, dword ptr [r12]
0x18000b1a4  mov     rax, [rdi+68h]
0x18000b1a8  mov     rcx, [rax+rcx*8]
0x18000b1ac  mov     [rdi+60h], rcx
0x18000b1b0  mov     dword ptr [rdi+44h], 1
0x18000b1b7  jmp     short loc_18000B1E4
0x18000b1b9  mov     ebx, 80070057h
0x18000b1be  mov     rcx, [rdi+58h]; this
0x18000b1c2  call    ?RemoveAll@CSpClassFactory@@QEAAJXZ; CSpClassFactory::RemoveAll(void)
0x18000b1c7  mov     rdx, [rdi+68h]; void *
0x18000b1cb  test    rdx, rdx
0x18000b1ce  jz      short loc_18000B1DC
0x18000b1d0  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18000b1d7  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18000b1dc  mov     qword ptr [rdi+68h], 0
0x18000b1e4  lea     r11, [rsp+40h+var_s0]
0x18000b1e9  mov     eax, ebx
0x18000b1eb  mov     rbx, [r11+30h]
0x18000b1ef  mov     rsi, [r11+40h]
0x18000b1f3  mov     rsp, r11
0x18000b1f6  pop     r15
0x18000b1f8  pop     r14
0x18000b1fa  pop     r12
0x18000b1fc  pop     rdi
0x18000b1fd  pop     rbp
0x18000b1fe  retn
```
