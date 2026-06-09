# CTextNormMultiResult::GetTopResults(long,ushort * * *,long *)

- ea: `0x1800bf320`
- end: `0x1800bf4a7`
- name: `?GetTopResults@CTextNormMultiResult@@UEAAJJPEAPEAPEAGPEAJ@Z`
- size: `391`
- prototype: `__int64 __fastcall(CTextNormMultiResult *__hidden this, int, unsigned __int16 ***, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004312`
- `0x1800bbc0c`
- `0x1800bcd8c`
- `0x1800bf320`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bf3f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bf3f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTextNormMultiResult::GetTopResults(
        CTextNormMultiResult *this,
        __int64 a2,
        unsigned __int16 ***a3,
        int *a4)
{
  int v5; // ebx
  int v6; // r12d
  __int64 v7; // rsi
  SIZE_T v8; // rcx
  _QWORD *v9; // rdi
  _QWORD *v10; // rdx
  __int64 v11; // rax
  __int64 v12; // r9
  __int64 v13; // rax
  unsigned __int16 **v14; // rax
  unsigned __int16 **v15; // r14
  int v16; // ebp
  unsigned __int16 *v17; // rsi
  __int64 v18; // rax
  _WORD *v19; // rdx
  __int64 v20; // r15
  _QWORD v22[2]; // [rsp+20h] [rbp-88h] BYREF
  int v23; // [rsp+30h] [rbp-78h]
  __int64 v24; // [rsp+38h] [rbp-70h]
  __int64 v25; // [rsp+40h] [rbp-68h]
  int v26; // [rsp+48h] [rbp-60h]
  int v27; // [rsp+54h] [rbp-54h]

  v23 = 0;
  v24 = 0;
  v22[1] = 0;
  v22[0] = 0;
  v25 = 0;
  v26 = 10;
  v27 = 0;
  if ( (int)a2 <= 0 || !a3 || !a4 )
  {
    v5 = -2147024809;
    goto LABEL_28;
  }
  v5 = CTextNormMultiResult::ComputeTopResults(this, a2, v22, 0);
  if ( v5 >= 0 )
  {
    v6 = v23;
    if ( v23 < 1 )
    {
      v5 = -2147217404;
      goto LABEL_28;
    }
    v7 = v23;
    v8 = v7 * 8;
    v9 = (_QWORD *)v22[0];
    v10 = (_QWORD *)v22[0];
    if ( v22[0] )
    {
      while ( 1 )
      {
        v11 = v10[2];
        v10 = (_QWORD *)*v10;
        if ( !*(_QWORD *)v11 )
          goto LABEL_13;
        v12 = *(_QWORD *)(*(_QWORD *)v11 + 64LL);
        if ( v12 )
          break;
LABEL_14:
        if ( !v10 )
          goto LABEL_15;
      }
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)(v12 + 2 * v13) );
      v8 += 2 * v13;
LABEL_13:
      v8 += 2LL;
      goto LABEL_14;
    }
LABEL_15:
    v14 = (unsigned __int16 **)CoTaskMemAlloc(v8);
    v15 = v14;
    if ( v14 )
    {
      v16 = 0;
      v17 = (unsigned __int16 *)&v14[v7];
      while ( v9 )
      {
        v18 = v9[2];
        v9 = (_QWORD *)*v9;
        if ( *(_QWORD *)v18 )
        {
          v19 = *(_WORD **)(*(_QWORD *)v18 + 64LL);
          if ( v19 )
          {
            v20 = -1;
            do
              ++v20;
            while ( v19[v20] );
            v15[v16] = v17;
            memcpy_0(v17, v19, 2 * v20 + 2);
            v17 += v20 + 1;
          }
        }
        else
        {
          v15[v16] = v17;
          *v17++ = 0;
        }
        ++v16;
      }
      *a3 = v15;
      *a4 = v6;
    }
    else
    {
      v5 = -2147024882;
    }
  }
LABEL_28:
  CTnMultiResStringPackage::~CTnMultiResStringPackage((CTnMultiResStringPackage *)v22);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800bf320  mov     r11, rsp
0x1800bf323  mov     [r11+18h], r8
0x1800bf327  push    rbx
0x1800bf328  push    rbp
0x1800bf329  push    rsi
0x1800bf32a  push    rdi
0x1800bf32b  push    r12
0x1800bf32d  push    r13
0x1800bf32f  push    r14
0x1800bf331  push    r15
0x1800bf333  sub     rsp, 68h
0x1800bf337  mov     r13, r9
0x1800bf33a  mov     rax, r8
0x1800bf33d  xor     r15d, r15d
0x1800bf340  mov     [r11-78h], r15d
0x1800bf344  mov     [r11-70h], r15
0x1800bf348  mov     [r11-80h], r15
0x1800bf34c  mov     [rsp+0A8h+var_88], r15
0x1800bf351  mov     [r11-68h], r15
0x1800bf355  mov     [rsp+0A8h+var_60], 0Ah
0x1800bf35d  mov     [r11-54h], r15d
0x1800bf361  test    edx, edx
0x1800bf363  jle     loc_1800BF485
0x1800bf369  test    rax, rax
0x1800bf36c  jz      loc_1800BF485
0x1800bf372  test    r9, r9
0x1800bf375  jz      loc_1800BF485
0x1800bf37b  xor     r9d, r9d
0x1800bf37e  lea     r8, [rsp+0A8h+var_88]
0x1800bf383  call    ?ComputeTopResults@CTextNormMultiResult@@AEAAJJPEAVCTnMultiResStringPackage@@PEAV?$CSPList@PEAUIParseTreeNode@@PEAU1@@@@Z; CTextNormMultiResult::ComputeTopResults(long,CTnMultiResStringPackage *,CSPList<IParseTreeNode *,IParseTreeNode *> *)
0x1800bf388  mov     ebx, eax
0x1800bf38a  test    eax, eax
0x1800bf38c  js      loc_1800BF48A
0x1800bf392  movsxd  r12, [rsp+0A8h+var_78]
0x1800bf397  cmp     r12d, 1
0x1800bf39b  jge     short loc_1800BF3A7
0x1800bf39d  mov     ebx, 80041004h
0x1800bf3a2  jmp     loc_1800BF48A
0x1800bf3a7  lea     rsi, ds:0[r12*8]
0x1800bf3af  mov     rcx, rsi
0x1800bf3b2  mov     rdi, [rsp+0A8h+var_88]
0x1800bf3b7  mov     rdx, rdi
0x1800bf3ba  test    rdi, rdi
0x1800bf3bd  jz      short loc_1800BF3F2
0x1800bf3bf  mov     rax, [rdx+10h]
0x1800bf3c3  mov     rdx, [rdx]
0x1800bf3c6  mov     r8, [rax]
0x1800bf3c9  test    r8, r8
0x1800bf3cc  jz      short loc_1800BF3E9
0x1800bf3ce  mov     r9, [r8+40h]
0x1800bf3d2  test    r9, r9
0x1800bf3d5  jz      short loc_1800BF3ED
0x1800bf3d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bf3db  inc     rax
0x1800bf3de  cmp     [r9+rax*2], r15w
0x1800bf3e3  jnz     short loc_1800BF3DB
0x1800bf3e5  lea     rcx, [rcx+rax*2]
0x1800bf3e9  add     rcx, 2; cb
0x1800bf3ed  test    rdx, rdx
0x1800bf3f0  jnz     short loc_1800BF3BF
0x1800bf3f2  call    cs:__imp_CoTaskMemAlloc
0x1800bf3f8  mov     r14, rax
0x1800bf3fb  test    rax, rax
0x1800bf3fe  jnz     short loc_1800BF40A
0x1800bf400  mov     ebx, 8007000Eh
0x1800bf405  jmp     loc_1800BF48A
0x1800bf40a  mov     ebp, r15d
0x1800bf40d  add     rsi, r14
0x1800bf410  jmp     short loc_1800BF46F
0x1800bf412  mov     rax, [rdi+10h]
0x1800bf416  mov     rdi, [rdi]
0x1800bf419  mov     rcx, [rax]
0x1800bf41c  test    rcx, rcx
0x1800bf41f  jz      short loc_1800BF45E
0x1800bf421  mov     rdx, [rcx+40h]; Src
0x1800bf425  test    rdx, rdx
0x1800bf428  jz      short loc_1800BF46D
0x1800bf42a  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800bf42e  xor     eax, eax
0x1800bf430  inc     r15
0x1800bf433  cmp     [rdx+r15*2], ax
0x1800bf438  jnz     short loc_1800BF430
0x1800bf43a  movsxd  rax, ebp
0x1800bf43d  mov     [r14+rax*8], rsi
0x1800bf441  lea     r8, ds:2[r15*2]; Size
0x1800bf449  mov     rcx, rsi; void *
0x1800bf44c  call    memcpy_0
0x1800bf451  lea     rsi, [rsi+r15*2]
0x1800bf455  add     rsi, 2
0x1800bf459  xor     r15d, r15d
0x1800bf45c  jmp     short loc_1800BF46D
0x1800bf45e  movsxd  rax, ebp
0x1800bf461  mov     [r14+rax*8], rsi
0x1800bf465  mov     [rsi], r15w
0x1800bf469  add     rsi, 2
0x1800bf46d  inc     ebp
0x1800bf46f  test    rdi, rdi
0x1800bf472  jnz     short loc_1800BF412
0x1800bf474  mov     rax, [rsp+0A8h+arg_10]
0x1800bf47c  mov     [rax], r14
0x1800bf47f  mov     [r13+0], r12d
0x1800bf483  jmp     short loc_1800BF48A
0x1800bf485  mov     ebx, 80070057h
0x1800bf48a  lea     rcx, [rsp+0A8h+var_88]; this
0x1800bf48f  call    ??1CTnMultiResStringPackage@@QEAA@XZ; CTnMultiResStringPackage::~CTnMultiResStringPackage(void)
0x1800bf494  mov     eax, ebx
0x1800bf496  add     rsp, 68h
0x1800bf49a  pop     r15
0x1800bf49c  pop     r14
0x1800bf49e  pop     r13
0x1800bf4a0  pop     r12
0x1800bf4a2  pop     rdi
0x1800bf4a3  pop     rsi
0x1800bf4a4  pop     rbp
0x1800bf4a5  pop     rbx
0x1800bf4a6  retn
```
