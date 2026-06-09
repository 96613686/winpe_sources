# RegExpComp::Compile(ushort const *,ushort const * *,ushort const * *,uchar * *,long *)

- ea: `0x180031978`
- end: `0x180031c4b`
- name: `?Compile@RegExpComp@@IEAAJPEBGPEAPEBG1PEAPEAEPEAJ@Z`
- size: `723`
- prototype: `__int64 __fastcall(RegExpComp *__hidden this, const unsigned __int16 *, const unsigned __int16 **, const unsigned __int16 **, unsigned __int8 **, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800318d4`

## callees

- `0x180010a48`
- `0x180031978`
- `0x180031c54`
- `0x180032fdc`
- `0x1800332e0`
- `0x180033488`
- `0x18003479c`
- `0x18005d290`
- `0x1800766b6`
- `0x18007672e`

## import_xrefs

- `msvcrt!realloc` at `0x180031bf7`
- `msvcrt!realloc` at `0x180031bf7`
- `msvcrt!free` at `0x180031ac0`
- `msvcrt!free` at `0x180031ac0`

## pseudocode

```c
__int64 __fastcall RegExpComp::Compile(
        RegExpComp *this,
        const unsigned __int16 *a2,
        const unsigned __int16 **a3,
        const unsigned __int16 **a4,
        unsigned __int8 **a5,
        int *a6)
{
  __int64 result; // rax
  struct Node *v7; // rsi
  int v8; // r14d
  int v9; // edi
  void *v10; // rcx
  __int64 v11; // rax
  int v12; // ecx
  int v13; // eax
  int v14; // esi
  int v15; // eax
  _DWORD *v16; // rcx
  void *v17; // rax
  int v18; // ecx

  *((_QWORD *)this + 36) = a2;
  *((_QWORD *)this + 39) = 0;
  *((_DWORD *)this + 70) = 0;
  *((_DWORD *)this + 64) = 0;
  *a5 = 0;
  *a6 = 0;
  if ( setjmp_0((_JBTYPE *)this) )
  {
    result = *((unsigned int *)this + 64);
    if ( (_DWORD)result != -2147024882 )
      *((_QWORD *)this + 36) -= 2LL;
    if ( a3 )
      *a3 = (const unsigned __int16 *)*((_QWORD *)this + 36);
  }
  else
  {
    v7 = RegExpComp::PnodeParse(this);
    v8 = RegExpComp::AssignRemLen(this, v7, 0);
    if ( a3 )
      *a3 = (const unsigned __int16 *)*((_QWORD *)this + 36);
    v9 = 2 * ((__int64)(*((_QWORD *)this + 36) - (_QWORD)a2) >> 1);
    v10 = (void *)*((_QWORD *)this + 38);
    if ( v10 )
      free(v10);
    *((_QWORD *)this + 38) = *((_QWORD *)this + 33);
    *((_QWORD *)this + 33) = 0;
    *((_DWORD *)this + 68) = 0;
    *((_DWORD *)this + 70) = 0;
    RegExpBase::EnsureSpace(this, 36);
    v11 = *((_QWORD *)this + 33);
    *((_DWORD *)this + 70) = 36;
    *(_OWORD *)v11 = 0;
    *(_OWORD *)(v11 + 16) = 0;
    *(_DWORD *)(v11 + 32) = 0;
    **((_DWORD **)this + 33) = 1265918286;
    RegExpComp::GenCode(this, v7);
    do
    {
      RegExpBase::PushByte(this, 0x11u);
      v12 = *((_DWORD *)this + 70);
    }
    while ( (v12 & 1) != 0 );
    *(_DWORD *)(*((_QWORD *)this + 33) + 12LL) = v12;
    if ( v9 > 0 )
    {
      v13 = *((_DWORD *)this + 70);
      v14 = v13 + v9;
      if ( v13 + v9 < v13 )
        RegExpBase::Error(this, -2147024882);
      RegExpBase::EnsureSpace(this, v14);
      memcpy_0((void *)(*((_QWORD *)this + 33) + *((int *)this + 70)), a2, v9);
      *((_DWORD *)this + 70) = v14;
    }
    while ( 1 )
    {
      v15 = *((_DWORD *)this + 70);
      if ( (v15 & 3) == 0 )
        break;
      RegExpBase::PushByte(this, 0);
    }
    v16 = (_DWORD *)*((_QWORD *)this + 33);
    v16[1] = v15;
    v16[2] = 36;
    v16[6] = *((_DWORD *)this + 78) + 1;
    v16[7] = *((_DWORD *)this + 79);
    v16[4] = v9;
    v16[5] = v8;
    v16[8] = *((_DWORD *)this + 80);
    if ( *((_DWORD *)this + 70) < *((_DWORD *)this + 68) )
    {
      v17 = realloc(*((void **)this + 33), *((int *)this + 70));
      if ( v17 )
        *((_QWORD *)this + 33) = v17;
    }
    *a5 = (unsigned __int8 *)*((_QWORD *)this + 33);
    v18 = *((_DWORD *)this + 70);
    *((_QWORD *)this + 33) = 0;
    *a6 = v18;
    result = 0;
    *((_DWORD *)this + 70) = 0;
    *((_DWORD *)this + 68) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180031978  mov     rax, rsp
0x18003197b  mov     [rax+20h], rbx
0x18003197f  mov     [rax+18h], r8
0x180031983  mov     [rax+10h], rdx
0x180031987  mov     [rax+8], rcx
0x18003198b  push    rbp
0x18003198c  push    rsi
0x18003198d  push    rdi
0x18003198e  push    r14
0x180031990  push    r15
0x180031992  mov     rbp, rsp
0x180031995  sub     rsp, 30h
0x180031999  mov     rax, [rbp+arg_20]
0x18003199d  xor     r15d, r15d
0x1800319a0  mov     [rcx+120h], rdx
0x1800319a7  mov     rdx, rsp
0x1800319aa  mov     [rcx+138h], r15
0x1800319b1  mov     [rcx+118h], r15d
0x1800319b8  mov     [rcx+100h], r15d
0x1800319bf  mov     [rax], r15
0x1800319c2  mov     rax, [rbp+arg_28]
0x1800319c6  mov     [rbp+var_10], r15
0x1800319ca  mov     [rax], r15d
0x1800319cd  call    _setjmp_0
0x1800319d2  test    eax, eax
0x1800319d4  jz      short loc_180031A0B
0x1800319d6  mov     rcx, [rbp+arg_0]
0x1800319da  mov     eax, [rcx+100h]
0x1800319e0  cmp     eax, 8007000Eh
0x1800319e5  jz      short loc_1800319EF
0x1800319e7  add     qword ptr [rcx+120h], 0FFFFFFFFFFFFFFFEh
0x1800319ef  mov     rdx, [rbp+arg_10]
0x1800319f3  test    rdx, rdx
0x1800319f6  jz      loc_180031C3A
0x1800319fc  mov     rcx, [rcx+120h]
0x180031a03  mov     [rdx], rcx
0x180031a06  jmp     loc_180031C3A
0x180031a0b  mov     rbx, [rbp+arg_0]
0x180031a0f  mov     rcx, rbx; this
0x180031a12  call    ?PnodeParse@RegExpComp@@IEAAPEAUNode@1@XZ; RegExpComp::PnodeParse(void)
0x180031a17  xor     r8d, r8d; int
0x180031a1a  mov     rdx, rax; struct Node *
0x180031a1d  mov     rcx, rbx; this
0x180031a20  mov     rsi, rax
0x180031a23  call    ?AssignRemLen@RegExpComp@@IEAAJPEAUNode@1@J@Z; RegExpComp::AssignRemLen(RegExpComp::Node *,long)
0x180031a28  mov     r14d, eax
0x180031a2b  mov     rax, [rbp+arg_10]
0x180031a2f  test    rax, rax
0x180031a32  jz      short loc_180031A3E
0x180031a34  mov     rcx, [rbx+120h]
0x180031a3b  mov     [rax], rcx
0x180031a3e  mov     rcx, [rbx+120h]
0x180031a45  mov     rdx, [rbp+var_10]
0x180031a49  mov     rdi, rcx
0x180031a4c  sub     rdi, [rbp+Src]
0x180031a50  sar     rdi, 1
0x180031a53  add     edi, edi
0x180031a55  test    rdx, rdx
0x180031a58  jz      short loc_180031AB4
0x180031a5a  cmp     word ptr [rcx], 2Fh ; '/'
0x180031a5e  jnz     short loc_180031AAE
0x180031a60  lea     rax, [rcx+2]
0x180031a64  cmp     word ptr [rax], 67h ; 'g'
0x180031a68  jz      short loc_180031A88
0x180031a6a  cmp     word ptr [rax], 69h ; 'i'
0x180031a6e  jz      short loc_180031A7F
0x180031a70  cmp     word ptr [rax], 6Dh ; 'm'
0x180031a74  jnz     short loc_180031A95
0x180031a76  or      dword ptr [rbx+140h], 4
0x180031a7d  jmp     short loc_180031A8F
0x180031a7f  or      dword ptr [rbx+140h], 1
0x180031a86  jmp     short loc_180031A8F
0x180031a88  or      dword ptr [rbx+140h], 2
0x180031a8f  add     rax, 2
0x180031a93  jmp     short loc_180031A64
0x180031a95  mov     [rdx], rax
0x180031a98  test    byte ptr [rbx+140h], 1
0x180031a9f  jz      short loc_180031AB4
0x180031aa1  mov     rdx, rsi; struct Node *
0x180031aa4  mov     rcx, rbx; this
0x180031aa7  call    ?MapToLowerCase@RegExpComp@@IEAAXPEAUNode@1@@Z; RegExpComp::MapToLowerCase(RegExpComp::Node *)
0x180031aac  jmp     short loc_180031AB4
0x180031aae  mov     rax, [rax]
0x180031ab1  mov     [rdx], rax
0x180031ab4  mov     rcx, [rbx+130h]; Block
0x180031abb  test    rcx, rcx
0x180031abe  jz      short loc_180031AC6
0x180031ac0  call    cs:__imp_free
0x180031ac6  mov     rax, [rbx+108h]
0x180031acd  mov     edx, 24h ; '$'; int
0x180031ad2  mov     rcx, rbx; this
0x180031ad5  mov     [rbx+130h], rax
0x180031adc  mov     [rbx+108h], r15
0x180031ae3  mov     [rbx+110h], r15d
0x180031aea  mov     [rbx+118h], r15d
0x180031af1  call    ?EnsureSpace@RegExpBase@@IEAAXJ@Z; RegExpBase::EnsureSpace(long)
0x180031af6  mov     rax, [rbx+108h]
0x180031afd  xorps   xmm0, xmm0
0x180031b00  mov     dword ptr [rbx+118h], 24h ; '$'
0x180031b0a  xor     ecx, ecx
0x180031b0c  mov     rdx, rsi; struct Node *
0x180031b0f  movups  xmmword ptr [rax], xmm0
0x180031b12  movups  xmmword ptr [rax+10h], xmm0
0x180031b16  mov     [rax+20h], ecx
0x180031b19  mov     rcx, rbx; this
0x180031b1c  mov     rax, [rbx+108h]
0x180031b23  mov     dword ptr [rax], 4B74614Eh
0x180031b29  call    ?GenCode@RegExpComp@@IEAAXPEAUNode@1@@Z; RegExpComp::GenCode(RegExpComp::Node *)
0x180031b2e  mov     dl, 11h; unsigned __int8
0x180031b30  mov     rcx, rbx; this
0x180031b33  call    ?PushByte@RegExpBase@@IEAAXE@Z; RegExpBase::PushByte(uchar)
0x180031b38  mov     ecx, [rbx+118h]
0x180031b3e  test    cl, 1
0x180031b41  jnz     short loc_180031B2E
0x180031b43  mov     rax, [rbx+108h]
0x180031b4a  mov     [rax+0Ch], ecx
0x180031b4d  test    edi, edi
0x180031b4f  jle     short loc_180031B9F
0x180031b51  mov     eax, [rbx+118h]
0x180031b57  mov     rcx, rbx; this
0x180031b5a  lea     esi, [rax+rdi]
0x180031b5d  cmp     esi, eax
0x180031b5f  jge     short loc_180031B6C
0x180031b61  mov     edx, 8007000Eh; int
0x180031b66  call    ?Error@RegExpBase@@IEAAXJ@Z; RegExpBase::Error(long)
0x180031b6c  mov     edx, esi; int
0x180031b6e  call    ?EnsureSpace@RegExpBase@@IEAAXJ@Z; RegExpBase::EnsureSpace(long)
0x180031b73  movsxd  rcx, dword ptr [rbx+118h]
0x180031b7a  add     rcx, [rbx+108h]; void *
0x180031b81  mov     rdx, [rbp+Src]; Src
0x180031b85  movsxd  r8, edi; Size
0x180031b88  call    memcpy_0
0x180031b8d  mov     [rbx+118h], esi
0x180031b93  jmp     short loc_180031B9F
0x180031b95  xor     edx, edx; unsigned __int8
0x180031b97  mov     rcx, rbx; this
0x180031b9a  call    ?PushByte@RegExpBase@@IEAAXE@Z; RegExpBase::PushByte(uchar)
0x180031b9f  mov     eax, [rbx+118h]
0x180031ba5  test    al, 3
0x180031ba7  jnz     short loc_180031B95
0x180031ba9  mov     rcx, [rbx+108h]
0x180031bb0  mov     [rcx+4], eax
0x180031bb3  mov     dword ptr [rcx+8], 24h ; '$'
0x180031bba  mov     eax, [rbx+138h]
0x180031bc0  inc     eax
0x180031bc2  mov     [rcx+18h], eax
0x180031bc5  mov     eax, [rbx+13Ch]
0x180031bcb  mov     [rcx+1Ch], eax
0x180031bce  mov     [rcx+10h], edi
0x180031bd1  mov     [rcx+14h], r14d
0x180031bd5  mov     eax, [rbx+140h]
0x180031bdb  mov     [rcx+20h], eax
0x180031bde  movsxd  rax, dword ptr [rbx+118h]
0x180031be5  cmp     eax, [rbx+110h]
0x180031beb  jge     short loc_180031C09
0x180031bed  mov     rcx, [rbx+108h]; Block
0x180031bf4  mov     rdx, rax; Size
0x180031bf7  call    cs:__imp_realloc
0x180031bfd  test    rax, rax
0x180031c00  jz      short loc_180031C09
0x180031c02  mov     [rbx+108h], rax
0x180031c09  mov     rcx, [rbx+108h]
0x180031c10  mov     rax, [rbp+arg_20]
0x180031c14  mov     [rax], rcx
0x180031c17  mov     rax, [rbp+arg_28]
0x180031c1b  mov     ecx, [rbx+118h]
0x180031c21  mov     [rbx+108h], r15
0x180031c28  mov     [rax], ecx
0x180031c2a  xor     eax, eax
0x180031c2c  mov     [rbx+118h], r15d
0x180031c33  mov     [rbx+110h], r15d
0x180031c3a  mov     rbx, [rsp+30h+arg_18]
0x180031c3f  add     rsp, 30h
0x180031c43  pop     r15
0x180031c45  pop     r14
0x180031c47  pop     rdi
0x180031c48  pop     rsi
0x180031c49  pop     rbp
0x180031c4a  retn
```
