# CTextNormMultiResult::Serialize(void * *,long *)

- ea: `0x1800c0530`
- end: `0x1800c0665`
- name: `?Serialize@CTextNormMultiResult@@UEAAJPEAPEAXPEAJ@Z`
- size: `309`
- prototype: `__int64 __fastcall(CTextNormMultiResult *__hidden this, void **, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800040b8`
- `0x1800bed5c`
- `0x1800bfda4`
- `0x1800c0530`
- `0x1800c066c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c05cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c05cc`

## pseudocode

```c
__int64 __fastcall CTextNormMultiResult::Serialize(CTextNormMultiResult *this, void **a2, int *a3)
{
  int NodeArray; // edi
  int v6; // esi
  int v7; // r14d
  __int64 v8; // r15
  __int64 v9; // rbp
  signed int v10; // r15d
  int v11; // r12d
  unsigned __int8 *v12; // rax
  unsigned __int8 *v13; // r14
  __int64 v14; // rax
  unsigned __int8 *v15; // rcx
  __int64 v16; // rbp
  unsigned __int8 *v18; // [rsp+60h] [rbp+8h] BYREF
  void **v19; // [rsp+68h] [rbp+10h]

  v19 = a2;
  NodeArray = 0;
  *a2 = 0;
  *a3 = 0;
  v6 = *(_DWORD *)(*((_QWORD *)this + 11) + 24LL);
  if ( !*((_QWORD *)this + 13) )
  {
    LODWORD(v18) = 0;
    NodeArray = CTextNormMultiResult::MakeNodeArray(this, (int *)&v18);
    if ( NodeArray < 0 )
      return (unsigned int)NodeArray;
    if ( v6 != (_DWORD)v18 )
      return (unsigned int)-2147418113;
  }
  v7 = 20;
  if ( v6 > 0 )
  {
    v8 = *((_QWORD *)this + 13);
    v9 = 0;
    do
    {
      v7 += CTnMultiResNode::GetSerializedSize(*(CTnMultiResNode **)(v8 + 8 * v9));
      v9 = (unsigned int)(v9 + 1);
    }
    while ( (int)v9 < v6 );
  }
  v10 = (v7 + 1) & 0xFFFFFFFE;
  v11 = v10 - v7;
  if ( v10 <= v7 )
    v11 = 0;
  v12 = (unsigned __int8 *)CoTaskMemAlloc(v10 + 100LL);
  v13 = v12;
  if ( v12 )
  {
    *(_DWORD *)v12 = v10;
    *((_DWORD *)v12 + 1) = *((_DWORD *)this + 29);
    *((_DWORD *)v12 + 2) = *((_DWORD *)this + 28);
    *((_DWORD *)v12 + 3) = v6;
    v14 = *((_QWORD *)this + 12);
    if ( v14 )
      *((_DWORD *)this + 30) = *(_DWORD *)(v14 + 40);
    v15 = v13 + 20;
    v16 = 0;
    *((_DWORD *)v13 + 4) = *((_DWORD *)this + 30);
    v18 = v13 + 20;
    if ( v6 > 0 )
    {
      do
      {
        CTnMultiResNode::Serialize(*(CTnMultiResNode **)(*((_QWORD *)this + 13) + 8 * v16), &v18);
        v16 = (unsigned int)(v16 + 1);
      }
      while ( (int)v16 < v6 );
      v15 = v18;
    }
    memset_0(v15, 0, v11);
    *v19 = v13;
    *a3 = v10;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)NodeArray;
}

```

## disassembly

```asm
0x1800c0530  mov     [rsp+arg_10], rbx
0x1800c0535  mov     [rsp+arg_8], rdx
0x1800c053a  push    rbp
0x1800c053b  push    rsi
0x1800c053c  push    rdi
0x1800c053d  push    r12
0x1800c053f  push    r13
0x1800c0541  push    r14
0x1800c0543  push    r15
0x1800c0545  sub     rsp, 20h
0x1800c0549  xor     edi, edi
0x1800c054b  mov     r13, r8
0x1800c054e  mov     [rdx], rdi
0x1800c0551  mov     rbx, rcx
0x1800c0554  mov     [r8], edi
0x1800c0557  mov     rax, [rcx+58h]
0x1800c055b  mov     esi, [rax+18h]
0x1800c055e  cmp     [rcx+68h], rdi
0x1800c0562  jnz     short loc_1800C058C
0x1800c0564  lea     rdx, [rsp+58h+arg_0]; int *
0x1800c0569  mov     dword ptr [rsp+58h+arg_0], edi
0x1800c056d  call    ?MakeNodeArray@CTextNormMultiResult@@AEAAJPEAJ@Z; CTextNormMultiResult::MakeNodeArray(long *)
0x1800c0572  mov     edi, eax
0x1800c0574  test    eax, eax
0x1800c0576  js      loc_1800C064E
0x1800c057c  cmp     esi, dword ptr [rsp+58h+arg_0]
0x1800c0580  jz      short loc_1800C058C
0x1800c0582  mov     edi, 8000FFFFh
0x1800c0587  jmp     loc_1800C064E
0x1800c058c  mov     r14d, 14h
0x1800c0592  test    esi, esi
0x1800c0594  jle     short loc_1800C05AE
0x1800c0596  mov     r15, [rbx+68h]
0x1800c059a  xor     ebp, ebp
0x1800c059c  mov     rcx, [r15+rbp*8]; this
0x1800c05a0  call    ?GetSerializedSize@CTnMultiResNode@@QEAAJXZ; CTnMultiResNode::GetSerializedSize(void)
0x1800c05a5  add     r14d, eax
0x1800c05a8  inc     ebp
0x1800c05aa  cmp     ebp, esi
0x1800c05ac  jl      short loc_1800C059C
0x1800c05ae  xor     eax, eax
0x1800c05b0  lea     r15d, [r14+1]
0x1800c05b4  and     r15d, 0FFFFFFFEh
0x1800c05b8  mov     r12d, r15d
0x1800c05bb  movsxd  rcx, r15d
0x1800c05be  sub     r12d, r14d
0x1800c05c1  cmp     r15d, r14d
0x1800c05c4  cmovle  r12d, eax
0x1800c05c8  add     rcx, 64h ; 'd'; cb
0x1800c05cc  call    cs:__imp_CoTaskMemAlloc
0x1800c05d2  mov     r14, rax
0x1800c05d5  test    rax, rax
0x1800c05d8  jnz     short loc_1800C05E1
0x1800c05da  mov     edi, 8007000Eh
0x1800c05df  jmp     short loc_1800C064E
0x1800c05e1  mov     [rax], r15d
0x1800c05e4  mov     eax, [rbx+74h]
0x1800c05e7  mov     [r14+4], eax
0x1800c05eb  mov     eax, [rbx+70h]
0x1800c05ee  mov     [r14+8], eax
0x1800c05f2  mov     [r14+0Ch], esi
0x1800c05f6  mov     rax, [rbx+60h]
0x1800c05fa  test    rax, rax
0x1800c05fd  jz      short loc_1800C0605
0x1800c05ff  mov     eax, [rax+28h]
0x1800c0602  mov     [rbx+78h], eax
0x1800c0605  mov     eax, [rbx+78h]
0x1800c0608  lea     rcx, [r14+14h]
0x1800c060c  xor     ebp, ebp
0x1800c060e  mov     [r14+10h], eax
0x1800c0612  mov     [rsp+58h+arg_0], rcx
0x1800c0617  test    esi, esi
0x1800c0619  jle     short loc_1800C0638
0x1800c061b  mov     rcx, [rbx+68h]
0x1800c061f  lea     rdx, [rsp+58h+arg_0]; unsigned __int8 **
0x1800c0624  mov     rcx, [rcx+rbp*8]; this
0x1800c0628  call    ?Serialize@CTnMultiResNode@@QEAAJAEAPEAE@Z; CTnMultiResNode::Serialize(uchar * &)
0x1800c062d  inc     ebp
0x1800c062f  cmp     ebp, esi
0x1800c0631  jl      short loc_1800C061B
0x1800c0633  mov     rcx, [rsp+58h+arg_0]; void *
0x1800c0638  movsxd  r8, r12d; Size
0x1800c063b  xor     edx, edx; Val
0x1800c063d  call    memset_0
0x1800c0642  mov     rax, [rsp+58h+arg_8]
0x1800c0647  mov     [rax], r14
0x1800c064a  mov     [r13+0], r15d
0x1800c064e  mov     rbx, [rsp+58h+arg_10]
0x1800c0653  mov     eax, edi
0x1800c0655  add     rsp, 20h
0x1800c0659  pop     r15
0x1800c065b  pop     r14
0x1800c065d  pop     r13
0x1800c065f  pop     r12
0x1800c0661  pop     rdi
0x1800c0662  pop     rsi
0x1800c0663  pop     rbp
0x1800c0664  retn
```
