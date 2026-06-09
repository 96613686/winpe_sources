# CTextNormMultiResult::Serialize(void * *,long *)

- ea: `0x18000e1a0`
- end: `0x18000e2d5`
- name: `?Serialize@CTextNormMultiResult@@UEAAJPEAPEAXPEAJ@Z`
- size: `309`
- prototype: `__int64 __fastcall(CTextNormMultiResult *__hidden this, void **, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002ec0`
- `0x18000c79c`
- `0x18000d8d4`
- `0x18000e1a0`
- `0x18000e2dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e23c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e23c`

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
0x18000e1a0  mov     [rsp+arg_10], rbx
0x18000e1a5  mov     [rsp+arg_8], rdx
0x18000e1aa  push    rbp
0x18000e1ab  push    rsi
0x18000e1ac  push    rdi
0x18000e1ad  push    r12
0x18000e1af  push    r13
0x18000e1b1  push    r14
0x18000e1b3  push    r15
0x18000e1b5  sub     rsp, 20h
0x18000e1b9  xor     edi, edi
0x18000e1bb  mov     r13, r8
0x18000e1be  mov     [rdx], rdi
0x18000e1c1  mov     rbx, rcx
0x18000e1c4  mov     [r8], edi
0x18000e1c7  mov     rax, [rcx+58h]
0x18000e1cb  mov     esi, [rax+18h]
0x18000e1ce  cmp     [rcx+68h], rdi
0x18000e1d2  jnz     short loc_18000E1FC
0x18000e1d4  lea     rdx, [rsp+58h+arg_0]; int *
0x18000e1d9  mov     dword ptr [rsp+58h+arg_0], edi
0x18000e1dd  call    ?MakeNodeArray@CTextNormMultiResult@@AEAAJPEAJ@Z; CTextNormMultiResult::MakeNodeArray(long *)
0x18000e1e2  mov     edi, eax
0x18000e1e4  test    eax, eax
0x18000e1e6  js      loc_18000E2BE
0x18000e1ec  cmp     esi, dword ptr [rsp+58h+arg_0]
0x18000e1f0  jz      short loc_18000E1FC
0x18000e1f2  mov     edi, 8000FFFFh
0x18000e1f7  jmp     loc_18000E2BE
0x18000e1fc  mov     r14d, 14h
0x18000e202  test    esi, esi
0x18000e204  jle     short loc_18000E21E
0x18000e206  mov     r15, [rbx+68h]
0x18000e20a  xor     ebp, ebp
0x18000e20c  mov     rcx, [r15+rbp*8]; this
0x18000e210  call    ?GetSerializedSize@CTnMultiResNode@@QEAAJXZ; CTnMultiResNode::GetSerializedSize(void)
0x18000e215  add     r14d, eax
0x18000e218  inc     ebp
0x18000e21a  cmp     ebp, esi
0x18000e21c  jl      short loc_18000E20C
0x18000e21e  xor     eax, eax
0x18000e220  lea     r15d, [r14+1]
0x18000e224  and     r15d, 0FFFFFFFEh
0x18000e228  mov     r12d, r15d
0x18000e22b  movsxd  rcx, r15d
0x18000e22e  sub     r12d, r14d
0x18000e231  cmp     r15d, r14d
0x18000e234  cmovle  r12d, eax
0x18000e238  add     rcx, 64h ; 'd'; cb
0x18000e23c  call    cs:__imp_CoTaskMemAlloc
0x18000e242  mov     r14, rax
0x18000e245  test    rax, rax
0x18000e248  jnz     short loc_18000E251
0x18000e24a  mov     edi, 8007000Eh
0x18000e24f  jmp     short loc_18000E2BE
0x18000e251  mov     [rax], r15d
0x18000e254  mov     eax, [rbx+74h]
0x18000e257  mov     [r14+4], eax
0x18000e25b  mov     eax, [rbx+70h]
0x18000e25e  mov     [r14+8], eax
0x18000e262  mov     [r14+0Ch], esi
0x18000e266  mov     rax, [rbx+60h]
0x18000e26a  test    rax, rax
0x18000e26d  jz      short loc_18000E275
0x18000e26f  mov     eax, [rax+28h]
0x18000e272  mov     [rbx+78h], eax
0x18000e275  mov     eax, [rbx+78h]
0x18000e278  lea     rcx, [r14+14h]
0x18000e27c  xor     ebp, ebp
0x18000e27e  mov     [r14+10h], eax
0x18000e282  mov     [rsp+58h+arg_0], rcx
0x18000e287  test    esi, esi
0x18000e289  jle     short loc_18000E2A8
0x18000e28b  mov     rcx, [rbx+68h]
0x18000e28f  lea     rdx, [rsp+58h+arg_0]; unsigned __int8 **
0x18000e294  mov     rcx, [rcx+rbp*8]; this
0x18000e298  call    ?Serialize@CTnMultiResNode@@QEAAJAEAPEAE@Z; CTnMultiResNode::Serialize(uchar * &)
0x18000e29d  inc     ebp
0x18000e29f  cmp     ebp, esi
0x18000e2a1  jl      short loc_18000E28B
0x18000e2a3  mov     rcx, [rsp+58h+arg_0]; void *
0x18000e2a8  movsxd  r8, r12d; Size
0x18000e2ab  xor     edx, edx; Val
0x18000e2ad  call    memset_0
0x18000e2b2  mov     rax, [rsp+58h+arg_8]
0x18000e2b7  mov     [rax], r14
0x18000e2ba  mov     [r13+0], r15d
0x18000e2be  mov     rbx, [rsp+58h+arg_10]
0x18000e2c3  mov     eax, edi
0x18000e2c5  add     rsp, 20h
0x18000e2c9  pop     r15
0x18000e2cb  pop     r14
0x18000e2cd  pop     r13
0x18000e2cf  pop     r12
0x18000e2d1  pop     rdi
0x18000e2d2  pop     rsi
0x18000e2d3  pop     rbp
0x18000e2d4  retn
```
