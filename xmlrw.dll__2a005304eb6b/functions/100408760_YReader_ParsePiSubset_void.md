# YReader::ParsePiSubset(void)

- ea: `0x100408760`
- end: `0x10040896c`
- name: `?ParsePiSubset@YReader@@AEAAXXZ`
- size: `524`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x100408ea0`
- `0x100409110`

## callees

- `0x100401780`
- `0x100408760`
- `0x10040a270`
- `0x100415560`
- `0x1004394f0`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParsePiSubset(YReader *this)
{
  __int128 v1; // xmm0
  __int64 v3; // rax
  unsigned __int64 v4; // rdi
  unsigned int v5; // eax
  struct BlockAlloc::Header *v6; // rbx
  __int64 v7; // rbp
  void *v8; // rdx
  __int64 v9; // rcx
  struct BlockAlloc::Header *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r10
  __int64 v13; // r11
  __int16 v14; // cx
  __int16 v15; // r8
  __int16 v16; // cx
  __int16 v17; // r9
  _QWORD *v18; // rax
  _QWORD *v19; // rcx
  __int128 v20; // xmm0
  void *Buf1; // [rsp+20h] [rbp-48h] BYREF
  int v22; // [rsp+28h] [rbp-40h]
  __int128 v23; // [rsp+30h] [rbp-38h]
  __int128 v24; // [rsp+40h] [rbp-28h]

  v1 = *((_OWORD *)this + 94);
  *(_QWORD *)&v23 = 0;
  DWORD2(v23) = 0;
  v22 = 0;
  v3 = *((_QWORD *)this + 55);
  v24 = v1;
  *((_OWORD *)this + 94) = v23;
  v4 = *(_QWORD *)(v3 + 16);
  v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13));
  v6 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
  v7 = v5;
  v8 = (void *)*((_QWORD *)v6 + 2);
  if ( *((_DWORD *)v6 + 6) - (int)v8 < v5 )
  {
    v9 = *((_QWORD *)v6 + 1);
    if ( v9 )
    {
      while ( 1 )
      {
        v6 = (struct BlockAlloc::Header *)v9;
        if ( *(_DWORD *)(v9 + 24) - (int)v9 - 32 >= v5 )
          break;
        v9 = *(_QWORD *)(v9 + 8);
        if ( !v9 )
          goto LABEL_5;
      }
      *(_QWORD *)(v9 + 16) = v9 + 32;
    }
    else
    {
LABEL_5:
      _mm_lfence();
      v10 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v5, v6);
      *((_QWORD *)v6 + 1) = v10;
      v6 = v10;
    }
    *((_QWORD *)this + 55) = v6;
    v8 = (void *)*((_QWORD *)v6 + 2);
  }
  *((_QWORD *)v6 + 2) += v7;
  v11 = *((_QWORD *)this + 13);
  Buf1 = v8;
  (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v11 + 104LL))(v11, &Buf1);
  while ( (unsigned int)YReader::GetTokenDeclLiteral(this) != 18 )
    ;
  if ( v22 == dword_100450B78 )
  {
    v12 = CodeStringPtr::xml;
    v13 = (unsigned int)dword_100450B78;
    if ( !dword_100450B78 )
      goto LABEL_35;
    do
    {
      v14 = *(_WORD *)((char *)Buf1 + v12 - CodeStringPtr::xml);
      v12 += 2;
      v15 = v14 + 32;
      if ( (unsigned __int16)(v14 - 65) > 0x19u )
        v15 = v14;
      v16 = *(_WORD *)(v12 - 2);
      v17 = v16 + 32;
      if ( (unsigned __int16)(v16 - 65) > 0x19u )
        v17 = *(_WORD *)(v12 - 2);
      --v13;
    }
    while ( v13 && v15 && v15 == v17 );
    if ( v15 == v17 )
    {
LABEL_35:
      if ( memcmp(Buf1, CodeStringPtr::xml, 2LL * (unsigned int)dword_100450B78) )
      {
        MXRRaiseException(-1072894402);
        __debugbreak();
      }
      MXRRaiseException(-1072894403);
      __debugbreak();
    }
  }
  v18 = (_QWORD *)*((_QWORD *)this + 55);
  if ( (unsigned __int64)v18 >= v4 || v4 > v18[2] )
  {
    v18 = (_QWORD *)*v18;
    *((_QWORD *)this + 55) = v18;
    if ( !v18 )
    {
LABEL_31:
      MXRRaiseException(-2147467259);
      JUMPOUT(0x10040896BLL);
    }
    while ( (unsigned __int64)v18 >= v4 || v4 > v18[3] )
    {
      v19 = (_QWORD *)*v18;
      *((_QWORD *)this + 55) = *v18;
      v18 = v19;
      if ( !v19 )
        goto LABEL_31;
    }
  }
  v20 = v24;
  v18[2] = v4;
  *((_OWORD *)this + 94) = v20;
}

```

## disassembly

```asm
0x100408760  mov     [rsp+arg_8], rbx
0x100408765  mov     [rsp+arg_10], rbp
0x10040876a  push    rsi
0x10040876b  push    rdi
0x10040876c  push    r14
0x10040876e  sub     rsp, 50h
0x100408772  movups  xmm0, xmmword ptr [rcx+5E0h]
0x100408779  xor     eax, eax
0x10040877b  mov     rsi, rcx
0x10040877e  mov     qword ptr [rsp+68h+var_38], rax
0x100408783  mov     dword ptr [rsp+68h+var_38+8], eax
0x100408787  mov     [rsp+68h+var_40], eax
0x10040878b  mov     rax, [rcx+1B8h]
0x100408792  movups  [rsp+68h+var_28], xmm0
0x100408797  movups  xmm0, [rsp+68h+var_38]
0x10040879c  movups  xmmword ptr [rcx+5E0h], xmm0
0x1004087a3  mov     rdi, [rax+10h]
0x1004087a7  mov     rcx, [rcx+68h]
0x1004087ab  mov     rax, [rcx]
0x1004087ae  mov     rax, [rax+60h]
0x1004087b2  call    cs:__guard_dispatch_icall_fptr
0x1004087b8  mov     rbx, [rsi+1B8h]
0x1004087bf  mov     ebp, eax
0x1004087c1  mov     rdx, [rbx+10h]
0x1004087c5  mov     ecx, [rbx+18h]
0x1004087c8  sub     ecx, edx
0x1004087ca  cmp     ecx, eax
0x1004087cc  jnb     short loc_100408822
0x1004087ce  mov     rcx, [rbx+8]
0x1004087d2  test    rcx, rcx
0x1004087d5  jz      short loc_1004087FC
0x1004087d7  nop     word ptr [rax+rax+00000000h]
0x1004087e0  mov     eax, [rcx+18h]
0x1004087e3  mov     rbx, rcx
0x1004087e6  sub     eax, ecx
0x1004087e8  sub     eax, 20h ; ' '
0x1004087eb  cmp     eax, ebp
0x1004087ed  jnb     loc_1004088D8
0x1004087f3  mov     rcx, [rcx+8]
0x1004087f7  test    rcx, rcx
0x1004087fa  jnz     short loc_1004087E0
0x1004087fc  lfence
0x1004087ff  mov     r8, rbx; struct BlockAlloc::Header *
0x100408802  lea     rcx, [rsi+1A0h]; this
0x100408809  mov     edx, ebp; unsigned int
0x10040880b  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x100408810  mov     [rbx+8], rax
0x100408814  mov     rbx, rax
0x100408817  mov     [rsi+1B8h], rbx
0x10040881e  mov     rdx, [rbx+10h]
0x100408822  add     [rbx+10h], rbp
0x100408826  mov     rcx, [rsi+68h]
0x10040882a  mov     [rsp+68h+Buf1], rdx
0x10040882f  lea     rdx, [rsp+68h+Buf1]
0x100408834  mov     rax, [rcx]
0x100408837  mov     rax, [rax+68h]
0x10040883b  call    cs:__guard_dispatch_icall_fptr
0x100408841  mov     rcx, rsi; this
0x100408844  call    ?GetTokenDeclLiteral@YReader@@AEAAHXZ; YReader::GetTokenDeclLiteral(void)
0x100408849  cmp     eax, 12h
0x10040884c  jnz     short loc_100408841
0x10040884e  mov     eax, cs:dword_100450B78
0x100408854  cmp     [rsp+68h+var_40], eax
0x100408858  jnz     loc_1004088E5
0x10040885e  mov     rdx, cs:?xml@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100408865  mov     r14d, eax
0x100408868  mov     rbp, [rsp+68h+Buf1]
0x10040886d  mov     r10, rdx
0x100408870  mov     r11d, eax
0x100408873  test    eax, eax
0x100408875  jz      short loc_1004088C6
0x100408877  mov     rbx, rbp
0x10040887a  sub     rbx, rdx
0x10040887d  nop     dword ptr [rax]
0x100408880  movzx   ecx, word ptr [rbx+r10]
0x100408885  lea     r10, [r10+2]
0x100408889  lea     eax, [rcx-41h]
0x10040888c  cmp     ax, 19h
0x100408890  lea     r8d, [rcx+20h]
0x100408894  cmova   r8w, cx
0x100408899  movzx   ecx, word ptr [r10-2]
0x10040889e  lea     eax, [rcx-41h]
0x1004088a1  cmp     ax, 19h
0x1004088a5  lea     r9d, [rcx+20h]
0x1004088a9  cmova   r9w, cx
0x1004088ae  sub     r11, 1
0x1004088b2  jz      short loc_1004088C0
0x1004088b4  test    r8w, r8w
0x1004088b8  jz      short loc_1004088C0
0x1004088ba  cmp     r8w, r9w
0x1004088be  jz      short loc_100408880
0x1004088c0  cmp     r8w, r9w
0x1004088c4  jnz     short loc_1004088E5
0x1004088c6  lea     r8, [r14+r14]; Size
0x1004088ca  mov     rcx, rbp; Buf1
0x1004088cd  call    memcmp
0x1004088d2  test    eax, eax
0x1004088d4  jz      short loc_10040894B
0x1004088d6  jmp     short loc_100408956
0x1004088d8  lea     rax, [rcx+20h]
0x1004088dc  mov     [rcx+10h], rax
0x1004088e0  jmp     loc_100408817
0x1004088e5  mov     rax, [rsi+1B8h]
0x1004088ec  cmp     rax, rdi
0x1004088ef  jnb     short loc_1004088F7
0x1004088f1  cmp     rdi, [rax+10h]
0x1004088f5  jbe     short loc_100408925
0x1004088f7  mov     rax, [rax]
0x1004088fa  mov     [rsi+1B8h], rax
0x100408901  test    rax, rax
0x100408904  jz      short loc_100408961
0x100408906  cmp     rax, rdi
0x100408909  jnb     short loc_100408911
0x10040890b  cmp     rdi, [rax+18h]
0x10040890f  jbe     short loc_100408925
0x100408911  mov     rcx, [rax]
0x100408914  mov     [rsi+1B8h], rcx
0x10040891b  mov     rax, rcx
0x10040891e  test    rcx, rcx
0x100408921  jz      short loc_100408961
0x100408923  jmp     short loc_100408906
0x100408925  movups  xmm0, [rsp+68h+var_28]
0x10040892a  mov     rbx, [rsp+68h+arg_8]
0x10040892f  mov     rbp, [rsp+68h+arg_10]
0x100408937  mov     [rax+10h], rdi
0x10040893b  movups  xmmword ptr [rsi+5E0h], xmm0
0x100408942  add     rsp, 50h
0x100408946  pop     r14
0x100408948  pop     rdi
0x100408949  pop     rsi
0x10040894a  retn
0x10040894b  mov     ecx, 0C00CEE3Dh; int
0x100408950  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100408955  int     3; Trap to Debugger
0x100408956  mov     ecx, 0C00CEE3Eh; int
0x10040895b  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100408960  int     3; Trap to Debugger
0x100408961  mov     ecx, 80004005h; int
0x100408966  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
