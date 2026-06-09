# CEnumJobs::Next(ulong,ushort * * *,ulong *)

- ea: `0x180029050`
- end: `0x1800292b5`
- name: `?Next@CEnumJobs@@UEAAJKPEAPEAPEAGPEAK@Z`
- size: `613`
- prototype: `__int64 __fastcall(CEnumJobs *__hidden this, unsigned int, unsigned __int16 ***, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180003ef0`
- `0x1800074c8`
- `0x1800087a6`
- `0x180028d74`
- `0x180029050`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029143`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800291ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029274`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029283`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029143`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800291ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029274`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029283`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800290d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800291bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002920e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800290d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800291bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002920e`

## pseudocode

```c
__int64 __fastcall CEnumJobs::Next(CEnumJobs *this, unsigned int a2, LPVOID *a3, unsigned int *a4)
{
  CEnumJobs *v7; // r12
  __int64 result; // rax
  unsigned int v9; // esi
  unsigned __int16 **v10; // rax
  unsigned __int16 *v11; // rcx
  unsigned __int16 *v12; // rbp
  __int64 v13; // rax
  _QWORD *v14; // rbx
  unsigned __int64 v15; // r13
  _WORD *v16; // rcx
  unsigned int v17; // ebx
  __int64 v18; // rbp
  int Next; // eax
  unsigned __int16 *v20; // r12
  unsigned __int16 **v21; // r13
  unsigned __int16 **v22; // rax
  __int64 v23; // rax
  unsigned __int64 v24; // r13
  LPVOID v25; // rax
  void *v26; // rdx
  unsigned __int16 *v27; // rcx
  LPVOID *v28; // r15
  int i; // ebx
  void *Block[11]; // [rsp+20h] [rbp-58h] BYREF

  v7 = this;
  if ( !a2 || a2 > 1 && !a4 || !a3 )
    return 2147942487LL;
  *a3 = 0;
  if ( *((_DWORD *)this + 149) )
  {
    if ( a4 )
      *a4 = 0;
    return 1;
  }
  Block[0] = 0;
  result = CEnumJobs::GetNext(this, (unsigned __int16 **)Block);
  v9 = result;
  if ( (_DWORD)result )
  {
    if ( a4 )
      *a4 = 0;
    *a3 = 0;
    return result;
  }
  v10 = (unsigned __int16 **)CoTaskMemAlloc(8u);
  *a3 = v10;
  if ( !v10 )
  {
    if ( a4 )
      *a4 = 0;
    v11 = (unsigned __int16 *)Block[0];
LABEL_17:
    operator delete(v11);
    return 2147942414LL;
  }
  v12 = (unsigned __int16 *)Block[0];
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)Block[0] + v13) );
  v14 = *a3;
  v15 = v13 + 1;
  *v14 = CoTaskMemAlloc(2 * (v13 + 1));
  v16 = *(_WORD **)*a3;
  if ( !v16 )
  {
    if ( a4 )
      *a4 = 0;
    CoTaskMemFree(*a3);
    v11 = v12;
    *a3 = 0;
    goto LABEL_17;
  }
  *v16 = 0;
  StringCchCopyW(*(unsigned __int16 **)*a3, v15, v12);
  operator delete(v12);
  if ( a2 == 1 )
  {
    if ( a4 )
      *a4 = 1;
    return 0;
  }
  else
  {
    v17 = 1;
    while ( 1 )
    {
      v18 = v17++;
      if ( v17 > a2 )
        goto LABEL_42;
      Next = CEnumJobs::GetNext(v7, (unsigned __int16 **)Block);
      v20 = (unsigned __int16 *)Block[0];
      v9 = Next;
      if ( Next )
        break;
      v21 = (unsigned __int16 **)*a3;
      v22 = (unsigned __int16 **)CoTaskMemAlloc(8LL * v17);
      *a3 = v22;
      if ( !v22 )
      {
        *a3 = v21;
LABEL_37:
        v9 = -2147024882;
        goto LABEL_39;
      }
      Block[0] = (void *)(8 * v18);
      memcpy_0(v22, v21, 8 * v18);
      CoTaskMemFree(v21);
      v23 = -1;
      do
        ++v23;
      while ( v20[v23] );
      v24 = v23 + 1;
      v25 = CoTaskMemAlloc(2 * (v23 + 1));
      v26 = Block[0];
      *(_QWORD *)((char *)Block[0] + (unsigned __int64)*a3) = v25;
      v27 = *(unsigned __int16 **)((char *)*a3 + (_QWORD)v26);
      if ( !v27 )
        goto LABEL_37;
      StringCchCopyW(v27, v24, v20);
      operator delete(v20);
      v7 = this;
      Block[0] = 0;
    }
    if ( Next >= 0 )
    {
LABEL_42:
      *a4 = v18;
      return v9;
    }
LABEL_39:
    v28 = (LPVOID *)*a3;
    for ( i = 0; i < (int)v18; ++i )
      CoTaskMemFree(v28[i]);
    CoTaskMemFree(v28);
    operator delete(v20);
    *a4 = 0;
    *a3 = 0;
    return v9;
  }
}

```

## disassembly

```asm
0x180029050  mov     [rsp+arg_0], rcx
0x180029055  push    rbx
0x180029056  push    rbp
0x180029057  push    rsi
0x180029058  push    rdi
0x180029059  push    r12
0x18002905b  push    r13
0x18002905d  push    r14
0x18002905f  push    r15
0x180029061  sub     rsp, 38h
0x180029065  xor     ebx, ebx
0x180029067  mov     rdi, r9
0x18002906a  mov     r14, r8
0x18002906d  mov     r15d, edx
0x180029070  mov     r12, rcx
0x180029073  test    edx, edx
0x180029075  jz      loc_18002929F
0x18002907b  cmp     edx, 1
0x18002907e  jbe     short loc_180029089
0x180029080  test    r9, r9
0x180029083  jz      loc_18002929F
0x180029089  test    r14, r14
0x18002908c  jz      loc_18002929F
0x180029092  mov     [r8], rbx
0x180029095  cmp     [rcx+254h], ebx
0x18002909b  jz      short loc_1800290AF
0x18002909d  test    rdi, rdi
0x1800290a0  jz      short loc_1800290A5
0x1800290a2  mov     [r9], ebx
0x1800290a5  mov     eax, 1
0x1800290aa  jmp     loc_1800292A4
0x1800290af  lea     rdx, [rsp+78h+Block]; unsigned __int16 **
0x1800290b4  mov     [rsp+78h+Block], rbx
0x1800290b9  call    ?GetNext@CEnumJobs@@AEAAJPEAPEAG@Z; CEnumJobs::GetNext(ushort * *)
0x1800290be  mov     esi, eax
0x1800290c0  test    eax, eax
0x1800290c2  jz      short loc_1800290D3
0x1800290c4  test    rdi, rdi
0x1800290c7  jz      short loc_1800290CB
0x1800290c9  mov     [rdi], ebx
0x1800290cb  mov     [r14], rbx
0x1800290ce  jmp     loc_1800292A4
0x1800290d3  mov     ecx, 8; cb
0x1800290d8  call    cs:__imp_CoTaskMemAlloc
0x1800290de  mov     [r14], rax
0x1800290e1  test    rax, rax
0x1800290e4  jnz     short loc_180029101
0x1800290e6  test    rdi, rdi
0x1800290e9  jz      short loc_1800290ED
0x1800290eb  mov     [rdi], ebx
0x1800290ed  mov     rcx, [rsp+78h+Block]; Block
0x1800290f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800290f7  mov     eax, 8007000Eh
0x1800290fc  jmp     loc_1800292A4
0x180029101  mov     rbp, [rsp+78h+Block]
0x180029106  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002910a  inc     rax
0x18002910d  cmp     [rbp+rax*2+0], bx
0x180029112  jnz     short loc_18002910A
0x180029114  mov     rbx, [r14]
0x180029117  lea     r13, [rax+1]
0x18002911b  lea     rcx, ds:0[r13*2]; cb
0x180029123  call    cs:__imp_CoTaskMemAlloc
0x180029129  mov     [rbx], rax
0x18002912c  xor     ebx, ebx
0x18002912e  mov     rax, [r14]
0x180029131  mov     rcx, [rax]
0x180029134  test    rcx, rcx
0x180029137  jnz     short loc_180029151
0x180029139  test    rdi, rdi
0x18002913c  jz      short loc_180029140
0x18002913e  mov     [rdi], ebx
0x180029140  mov     rcx, [r14]; pv
0x180029143  call    cs:__imp_CoTaskMemFree
0x180029149  mov     rcx, rbp
0x18002914c  mov     [r14], rbx
0x18002914f  jmp     short loc_1800290F2
0x180029151  mov     [rcx], bx
0x180029154  mov     r8, rbp; unsigned __int16 *
0x180029157  mov     rcx, [r14]
0x18002915a  mov     rdx, r13; unsigned __int64
0x18002915d  mov     rcx, [rcx]; unsigned __int16 *
0x180029160  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029165  mov     rcx, rbp; Block
0x180029168  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002916d  cmp     r15d, 1
0x180029171  jnz     short loc_180029182
0x180029173  test    rdi, rdi
0x180029176  jz      short loc_18002917B
0x180029178  mov     [rdi], r15d
0x18002917b  xor     eax, eax
0x18002917d  jmp     loc_1800292A4
0x180029182  mov     ebx, 1
0x180029187  xor     r13d, r13d
0x18002918a  mov     ebp, ebx
0x18002918c  inc     ebx
0x18002918e  cmp     ebx, r15d
0x180029191  ja      loc_180029299
0x180029197  lea     rdx, [rsp+78h+Block]; unsigned __int16 **
0x18002919c  mov     rcx, r12; this
0x18002919f  call    ?GetNext@CEnumJobs@@AEAAJPEAPEAG@Z; CEnumJobs::GetNext(ushort * *)
0x1800291a4  mov     r12, [rsp+78h+Block]
0x1800291a9  mov     esi, eax
0x1800291ab  test    eax, eax
0x1800291ad  jnz     loc_180029261
0x1800291b3  mov     r13, [r14]
0x1800291b6  mov     ecx, ebx
0x1800291b8  shl     rcx, 3; cb
0x1800291bc  call    cs:__imp_CoTaskMemAlloc
0x1800291c2  mov     [r14], rax
0x1800291c5  test    rax, rax
0x1800291c8  jz      loc_180029254
0x1800291ce  lea     rcx, ds:0[rbp*8]
0x1800291d6  mov     rdx, r13; Src
0x1800291d9  mov     [rsp+78h+Block], rcx
0x1800291de  mov     r8, rcx; Size
0x1800291e1  mov     rcx, rax; void *
0x1800291e4  call    memcpy_0
0x1800291e9  mov     rcx, r13; pv
0x1800291ec  call    cs:__imp_CoTaskMemFree
0x1800291f2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800291f6  xor     ecx, ecx
0x1800291f8  inc     rax
0x1800291fb  cmp     [r12+rax*2], cx
0x180029200  jnz     short loc_1800291F8
0x180029202  lea     r13, [rax+1]
0x180029206  lea     rcx, ds:0[r13*2]; cb
0x18002920e  call    cs:__imp_CoTaskMemAlloc
0x180029214  mov     rcx, [r14]
0x180029217  mov     rdx, [rsp+78h+Block]
0x18002921c  mov     [rdx+rcx], rax
0x180029220  mov     rax, [r14]
0x180029223  mov     rcx, [rdx+rax]; unsigned __int16 *
0x180029227  test    rcx, rcx
0x18002922a  jz      short loc_180029257
0x18002922c  mov     r8, r12; unsigned __int16 *
0x18002922f  mov     rdx, r13; unsigned __int64
0x180029232  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029237  mov     rcx, r12; Block
0x18002923a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002923f  mov     r12, [rsp+78h+arg_0]
0x180029247  xor     r13d, r13d
0x18002924a  mov     [rsp+78h+Block], r13
0x18002924f  jmp     loc_18002918A
0x180029254  mov     [r14], r13
0x180029257  mov     esi, 8007000Eh
0x18002925c  xor     r13d, r13d
0x18002925f  jmp     short loc_180029263
0x180029261  jns     short loc_180029299
0x180029263  mov     r15, [r14]
0x180029266  mov     ebx, r13d
0x180029269  test    ebp, ebp
0x18002926b  jle     short loc_180029280
0x18002926d  movsxd  rcx, ebx
0x180029270  mov     rcx, [r15+rcx*8]; pv
0x180029274  call    cs:__imp_CoTaskMemFree
0x18002927a  inc     ebx
0x18002927c  cmp     ebx, ebp
0x18002927e  jl      short loc_18002926D
0x180029280  mov     rcx, r15; pv
0x180029283  call    cs:__imp_CoTaskMemFree
0x180029289  mov     rcx, r12; Block
0x18002928c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029291  mov     [rdi], r13d
0x180029294  mov     [r14], r13
0x180029297  jmp     short loc_18002929B
0x180029299  mov     [rdi], ebp
0x18002929b  mov     eax, esi
0x18002929d  jmp     short loc_1800292A4
0x18002929f  mov     eax, 80070057h
0x1800292a4  add     rsp, 38h
0x1800292a8  pop     r15
0x1800292aa  pop     r14
0x1800292ac  pop     r13
0x1800292ae  pop     r12
0x1800292b0  pop     rdi
0x1800292b1  pop     rsi
0x1800292b2  pop     rbp
0x1800292b3  pop     rbx
0x1800292b4  retn
```
