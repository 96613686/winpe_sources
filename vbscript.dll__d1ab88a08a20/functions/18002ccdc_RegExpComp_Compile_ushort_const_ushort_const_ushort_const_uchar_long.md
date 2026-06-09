# RegExpComp::Compile(ushort const *,ushort const * *,ushort const * *,uchar * *,long *)

- ea: `0x18002ccdc`
- end: `0x18002cfbc`
- name: `?Compile@RegExpComp@@IEAAJPEBGPEAPEBG1PEAPEAEPEAJ@Z`
- size: `736`
- prototype: `__int64 __fastcall(RegExpComp *__hidden this, const unsigned __int16 *, const unsigned __int16 **, const unsigned __int16 **, unsigned __int8 **, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002cc30`

## callees

- `0x18000eca4`
- `0x18002a818`
- `0x18002bc6c`
- `0x18002bd78`
- `0x18002c07c`
- `0x18002ccdc`
- `0x18002d010`
- `0x18005ee54`
- `0x1800793a6`
- `0x18007941e`

## import_xrefs

- `msvcrt!realloc` at `0x18002cf61`
- `msvcrt!realloc` at `0x18002cf61`
- `msvcrt!free` at `0x18002ce24`
- `msvcrt!free` at `0x18002ce24`

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
0x18002ccdc  mov     rax, rsp
0x18002ccdf  mov     [rax+20h], rbx
0x18002cce3  mov     [rax+18h], r8
0x18002cce7  mov     [rax+10h], rdx
0x18002cceb  mov     [rax+8], rcx
0x18002ccef  push    rbp
0x18002ccf0  push    rsi
0x18002ccf1  push    rdi
0x18002ccf2  push    r14
0x18002ccf4  push    r15
0x18002ccf6  mov     rbp, rsp
0x18002ccf9  sub     rsp, 30h
0x18002ccfd  mov     rax, [rbp+arg_20]
0x18002cd01  xor     r15d, r15d
0x18002cd04  mov     [rcx+120h], rdx
0x18002cd0b  mov     rdx, rsp
0x18002cd0e  mov     [rcx+138h], r15
0x18002cd15  mov     [rcx+118h], r15d
0x18002cd1c  mov     [rcx+100h], r15d
0x18002cd23  mov     [rax], r15
0x18002cd26  mov     rax, [rbp+arg_28]
0x18002cd2a  mov     [rbp+var_10], r15
0x18002cd2e  mov     [rax], r15d
0x18002cd31  call    _setjmp_0
0x18002cd36  test    eax, eax
0x18002cd38  jz      short loc_18002CD6F
0x18002cd3a  mov     rcx, [rbp+arg_0]
0x18002cd3e  mov     eax, [rcx+100h]
0x18002cd44  cmp     eax, 8007000Eh
0x18002cd49  jz      short loc_18002CD53
0x18002cd4b  add     qword ptr [rcx+120h], 0FFFFFFFFFFFFFFFEh
0x18002cd53  mov     rdx, [rbp+arg_10]
0x18002cd57  test    rdx, rdx
0x18002cd5a  jz      loc_18002CFAA
0x18002cd60  mov     rcx, [rcx+120h]
0x18002cd67  mov     [rdx], rcx
0x18002cd6a  jmp     loc_18002CFAA
0x18002cd6f  mov     rbx, [rbp+arg_0]
0x18002cd73  mov     rcx, rbx; this
0x18002cd76  call    ?PnodeParse@RegExpComp@@IEAAPEAUNode@1@XZ; RegExpComp::PnodeParse(void)
0x18002cd7b  xor     r8d, r8d; int
0x18002cd7e  mov     rdx, rax; struct Node *
0x18002cd81  mov     rcx, rbx; this
0x18002cd84  mov     rsi, rax
0x18002cd87  call    ?AssignRemLen@RegExpComp@@IEAAJPEAUNode@1@J@Z; RegExpComp::AssignRemLen(RegExpComp::Node *,long)
0x18002cd8c  mov     r14d, eax
0x18002cd8f  mov     rax, [rbp+arg_10]
0x18002cd93  test    rax, rax
0x18002cd96  jz      short loc_18002CDA2
0x18002cd98  mov     rcx, [rbx+120h]
0x18002cd9f  mov     [rax], rcx
0x18002cda2  mov     rcx, [rbx+120h]
0x18002cda9  mov     rdx, [rbp+var_10]
0x18002cdad  mov     rdi, rcx
0x18002cdb0  sub     rdi, [rbp+Src]
0x18002cdb4  sar     rdi, 1
0x18002cdb7  add     edi, edi
0x18002cdb9  test    rdx, rdx
0x18002cdbc  jz      short loc_18002CE18
0x18002cdbe  cmp     word ptr [rcx], 2Fh ; '/'
0x18002cdc2  jnz     short loc_18002CE12
0x18002cdc4  lea     rax, [rcx+2]
0x18002cdc8  cmp     word ptr [rax], 67h ; 'g'
0x18002cdcc  jz      short loc_18002CDEC
0x18002cdce  cmp     word ptr [rax], 69h ; 'i'
0x18002cdd2  jz      short loc_18002CDE3
0x18002cdd4  cmp     word ptr [rax], 6Dh ; 'm'
0x18002cdd8  jnz     short loc_18002CDF9
0x18002cdda  or      dword ptr [rbx+140h], 4
0x18002cde1  jmp     short loc_18002CDF3
0x18002cde3  or      dword ptr [rbx+140h], 1
0x18002cdea  jmp     short loc_18002CDF3
0x18002cdec  or      dword ptr [rbx+140h], 2
0x18002cdf3  add     rax, 2
0x18002cdf7  jmp     short loc_18002CDC8
0x18002cdf9  mov     [rdx], rax
0x18002cdfc  test    byte ptr [rbx+140h], 1
0x18002ce03  jz      short loc_18002CE18
0x18002ce05  mov     rdx, rsi; struct Node *
0x18002ce08  mov     rcx, rbx; this
0x18002ce0b  call    ?MapToLowerCase@RegExpComp@@IEAAXPEAUNode@1@@Z; RegExpComp::MapToLowerCase(RegExpComp::Node *)
0x18002ce10  jmp     short loc_18002CE18
0x18002ce12  mov     rax, [rax]
0x18002ce15  mov     [rdx], rax
0x18002ce18  mov     rcx, [rbx+130h]; Block
0x18002ce1f  test    rcx, rcx
0x18002ce22  jz      short loc_18002CE30
0x18002ce24  call    cs:__imp_free
0x18002ce2b  nop     dword ptr [rax+rax+00h]
0x18002ce30  mov     rax, [rbx+108h]
0x18002ce37  mov     edx, 24h ; '$'; int
0x18002ce3c  mov     rcx, rbx; this
0x18002ce3f  mov     [rbx+130h], rax
0x18002ce46  mov     [rbx+108h], r15
0x18002ce4d  mov     [rbx+110h], r15d
0x18002ce54  mov     [rbx+118h], r15d
0x18002ce5b  call    ?EnsureSpace@RegExpBase@@IEAAXJ@Z; RegExpBase::EnsureSpace(long)
0x18002ce60  mov     rax, [rbx+108h]
0x18002ce67  xorps   xmm0, xmm0
0x18002ce6a  mov     dword ptr [rbx+118h], 24h ; '$'
0x18002ce74  xor     ecx, ecx
0x18002ce76  mov     rdx, rsi; struct Node *
0x18002ce79  movups  xmmword ptr [rax], xmm0
0x18002ce7c  movups  xmmword ptr [rax+10h], xmm0
0x18002ce80  mov     [rax+20h], ecx
0x18002ce83  mov     rcx, rbx; this
0x18002ce86  mov     rax, [rbx+108h]
0x18002ce8d  mov     dword ptr [rax], 4B74614Eh
0x18002ce93  call    ?GenCode@RegExpComp@@IEAAXPEAUNode@1@@Z; RegExpComp::GenCode(RegExpComp::Node *)
0x18002ce98  mov     dl, 11h; unsigned __int8
0x18002ce9a  mov     rcx, rbx; this
0x18002ce9d  call    ?PushByte@RegExpBase@@IEAAXE@Z; RegExpBase::PushByte(uchar)
0x18002cea2  mov     ecx, [rbx+118h]
0x18002cea8  test    cl, 1
0x18002ceab  jnz     short loc_18002CE98
0x18002cead  mov     rax, [rbx+108h]
0x18002ceb4  mov     [rax+0Ch], ecx
0x18002ceb7  test    edi, edi
0x18002ceb9  jle     short loc_18002CF09
0x18002cebb  mov     eax, [rbx+118h]
0x18002cec1  mov     rcx, rbx; this
0x18002cec4  lea     esi, [rax+rdi]
0x18002cec7  cmp     esi, eax
0x18002cec9  jge     short loc_18002CED6
0x18002cecb  mov     edx, 8007000Eh; int
0x18002ced0  call    ?Error@RegExpBase@@IEAAXJ@Z; RegExpBase::Error(long)
0x18002ced6  mov     edx, esi; int
0x18002ced8  call    ?EnsureSpace@RegExpBase@@IEAAXJ@Z; RegExpBase::EnsureSpace(long)
0x18002cedd  movsxd  rcx, dword ptr [rbx+118h]
0x18002cee4  add     rcx, [rbx+108h]; void *
0x18002ceeb  mov     rdx, [rbp+Src]; Src
0x18002ceef  movsxd  r8, edi; Size
0x18002cef2  call    memcpy_0
0x18002cef7  mov     [rbx+118h], esi
0x18002cefd  jmp     short loc_18002CF09
0x18002ceff  xor     edx, edx; unsigned __int8
0x18002cf01  mov     rcx, rbx; this
0x18002cf04  call    ?PushByte@RegExpBase@@IEAAXE@Z; RegExpBase::PushByte(uchar)
0x18002cf09  mov     eax, [rbx+118h]
0x18002cf0f  test    al, 3
0x18002cf11  jnz     short loc_18002CEFF
0x18002cf13  mov     rcx, [rbx+108h]
0x18002cf1a  mov     [rcx+4], eax
0x18002cf1d  mov     dword ptr [rcx+8], 24h ; '$'
0x18002cf24  mov     eax, [rbx+138h]
0x18002cf2a  inc     eax
0x18002cf2c  mov     [rcx+18h], eax
0x18002cf2f  mov     eax, [rbx+13Ch]
0x18002cf35  mov     [rcx+1Ch], eax
0x18002cf38  mov     [rcx+10h], edi
0x18002cf3b  mov     [rcx+14h], r14d
0x18002cf3f  mov     eax, [rbx+140h]
0x18002cf45  mov     [rcx+20h], eax
0x18002cf48  movsxd  rax, dword ptr [rbx+118h]
0x18002cf4f  cmp     eax, [rbx+110h]
0x18002cf55  jge     short loc_18002CF79
0x18002cf57  mov     rcx, [rbx+108h]; Block
0x18002cf5e  mov     rdx, rax; Size
0x18002cf61  call    cs:__imp_realloc
0x18002cf68  nop     dword ptr [rax+rax+00h]
0x18002cf6d  test    rax, rax
0x18002cf70  jz      short loc_18002CF79
0x18002cf72  mov     [rbx+108h], rax
0x18002cf79  mov     rcx, [rbx+108h]
0x18002cf80  mov     rax, [rbp+arg_20]
0x18002cf84  mov     [rax], rcx
0x18002cf87  mov     rax, [rbp+arg_28]
0x18002cf8b  mov     ecx, [rbx+118h]
0x18002cf91  mov     [rbx+108h], r15
0x18002cf98  mov     [rax], ecx
0x18002cf9a  xor     eax, eax
0x18002cf9c  mov     [rbx+118h], r15d
0x18002cfa3  mov     [rbx+110h], r15d
0x18002cfaa  mov     rbx, [rsp+30h+arg_18]
0x18002cfaf  add     rsp, 30h
0x18002cfb3  pop     r15
0x18002cfb5  pop     r14
0x18002cfb7  pop     rdi
0x18002cfb8  pop     rsi
0x18002cfb9  pop     rbp
0x18002cfba  retn
```
