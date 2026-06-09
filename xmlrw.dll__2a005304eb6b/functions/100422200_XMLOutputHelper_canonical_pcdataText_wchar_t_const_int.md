# XMLOutputHelper::canonical_pcdataText(wchar_t const *,int)

- ea: `0x100422200`
- end: `0x10042241f`
- name: `?canonical_pcdataText@XMLOutputHelper@@QEAAXPEB_WH@Z`
- size: `543`
- prototype: `void __fastcall(XMLOutputHelper *__hidden this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x10041c990`

## callees

- `0x100422200`
- `0x1004228c0`

## pseudocode

```c
void __fastcall XMLOutputHelper::canonical_pcdataText(XMLOutputHelper *this, const wchar_t *a2, int a3)
{
  _WORD *v3; // rax
  int v5; // esi
  __int64 v7; // rcx
  _WORD *v8; // rax
  unsigned __int16 v9; // cx
  const wchar_t *v10; // rdi
  __int16 v11; // cx
  const wchar_t *v12; // rdi
  __int16 v13; // cx
  const wchar_t *v14; // rdi
  __int16 v15; // cx
  const wchar_t *v16; // rdi
  __int16 v17; // cx
  __int64 v18; // rcx
  _WORD *v19; // rcx
  __int64 v20; // rax

  v3 = (_WORD *)*((_QWORD *)this + 544);
  v5 = a3;
  if ( v3 )
  {
    v7 = (__int64)(unsigned int)(*((_DWORD *)this + 6) - *((_DWORD *)this + 10)) >> 1;
    if ( (_WORD)v7 == *v3 )
    {
      *((_QWORD *)this + 544) = v3 - 1;
    }
    else
    {
      v8 = v3 + 1;
      *((_QWORD *)this + 544) = v8;
      *v8 = v7;
    }
  }
  if ( a3 )
  {
    while ( 1 )
    {
      v9 = *a2++;
      --v5;
      if ( v9 > 0x3Eu )
        break;
      switch ( v9 )
      {
        case 0xAu:
          **((_WORD **)this + 3) = 10;
          goto LABEL_34;
        case 0xDu:
          v16 = L"&#xD;";
          v17 = 38;
          do
          {
            **((_WORD **)this + 3) = v17;
            *((_QWORD *)this + 3) += 2LL;
            if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
              OutputHelper::_hardWrite(this);
            v17 = v16[1];
            ++v16;
          }
          while ( v17 );
          goto LABEL_36;
        case 0x26u:
          v14 = L"&amp;";
          v15 = 38;
          do
          {
            **((_WORD **)this + 3) = v15;
            *((_QWORD *)this + 3) += 2LL;
            if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
              OutputHelper::_hardWrite(this);
            v15 = v14[1];
            ++v14;
          }
          while ( v15 );
          goto LABEL_36;
        case 0x3Cu:
          v12 = L"&lt;";
          v13 = 38;
          do
          {
            **((_WORD **)this + 3) = v13;
            *((_QWORD *)this + 3) += 2LL;
            if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
              OutputHelper::_hardWrite(this);
            v13 = v12[1];
            ++v12;
          }
          while ( v13 );
          goto LABEL_36;
      }
      if ( v9 != 62 )
        break;
      v10 = L"&gt;";
      v11 = 38;
      do
      {
        **((_WORD **)this + 3) = v11;
        *((_QWORD *)this + 3) += 2LL;
        if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
          OutputHelper::_hardWrite(this);
        v11 = v10[1];
        ++v10;
      }
      while ( v11 );
LABEL_36:
      if ( !v5 )
        goto LABEL_37;
    }
    **((_WORD **)this + 3) = v9;
LABEL_34:
    *((_QWORD *)this + 3) += 2LL;
    if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
      OutputHelper::_hardWrite(this);
    goto LABEL_36;
  }
LABEL_37:
  v18 = *((_QWORD *)this + 544);
  if ( v18 )
  {
    v19 = (_WORD *)(v18 + 2);
    v20 = (__int64)(unsigned int)(*((_DWORD *)this + 6) - *((_DWORD *)this + 10)) >> 1;
    *((_QWORD *)this + 544) = v19;
    *v19 = v20;
  }
}

```

## disassembly

```asm
0x100422200  push    rbx
0x100422202  sub     rsp, 30h
0x100422206  mov     rax, [rcx+1100h]
0x10042220d  mov     rbx, rcx
0x100422210  mov     [rsp+38h+arg_8], rsi
0x100422215  mov     esi, r8d
0x100422218  mov     [rsp+38h+var_10], r14
0x10042221d  mov     r14, rdx
0x100422220  test    rax, rax
0x100422223  jz      short loc_10042224E
0x100422225  mov     ecx, [rcx+18h]
0x100422228  sub     ecx, [rbx+28h]
0x10042222b  sar     rcx, 1
0x10042222e  cmp     cx, [rax]
0x100422231  jz      short loc_100422243
0x100422233  add     rax, 2
0x100422237  mov     [rbx+1100h], rax
0x10042223e  mov     [rax], cx
0x100422241  jmp     short loc_10042224E
0x100422243  add     rax, 0FFFFFFFFFFFFFFFEh
0x100422247  mov     [rbx+1100h], rax
0x10042224e  test    r8d, r8d
0x100422251  jz      loc_1004223EC
0x100422257  mov     [rsp+38h+arg_0], rbp
0x10042225c  mov     ebp, 26h ; '&'
0x100422261  mov     [rsp+38h+arg_10], rdi
0x100422266  mov     [rsp+38h+var_18], r15
0x10042226b  lea     r15d, [rbp-1Ch]
0x10042226f  nop
0x100422270  movzx   ecx, word ptr [r14]
0x100422274  lea     r14, [r14+2]
0x100422278  dec     esi
0x10042227a  cmp     cx, 3Eh ; '>'
0x10042227e  ja      loc_1004223B7
0x100422284  cmp     cx, r15w
0x100422288  jz      loc_1004223AD
0x10042228e  cmp     cx, 0Dh
0x100422292  jz      loc_10042236D
0x100422298  cmp     cx, bp
0x10042229b  jz      loc_100422330
0x1004222a1  cmp     cx, 3Ch ; '<'
0x1004222a5  jz      short loc_1004222F0
0x1004222a7  cmp     cx, 3Eh ; '>'
0x1004222ab  jnz     loc_1004223B7
0x1004222b1  lea     rdi, aGt; "&gt;"
0x1004222b8  movzx   ecx, bp
0x1004222bb  nop     dword ptr [rax+rax+00h]
0x1004222c0  mov     rax, [rbx+18h]
0x1004222c4  mov     [rax], cx
0x1004222c7  add     qword ptr [rbx+18h], 2
0x1004222cc  mov     rax, [rbx+18h]
0x1004222d0  cmp     rax, [rbx+20h]
0x1004222d4  jb      short loc_1004222DE
0x1004222d6  mov     rcx, rbx; this
0x1004222d9  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x1004222de  movzx   ecx, word ptr [rdi+2]
0x1004222e2  add     rdi, 2
0x1004222e6  test    cx, cx
0x1004222e9  jnz     short loc_1004222C0
0x1004222eb  jmp     loc_1004223D5
0x1004222f0  lea     rdi, aLt; "&lt;"
0x1004222f7  movzx   ecx, bp
0x1004222fa  nop     word ptr [rax+rax+00h]
0x100422300  mov     rax, [rbx+18h]
0x100422304  mov     [rax], cx
0x100422307  add     qword ptr [rbx+18h], 2
0x10042230c  mov     rax, [rbx+18h]
0x100422310  cmp     rax, [rbx+20h]
0x100422314  jb      short loc_10042231E
0x100422316  mov     rcx, rbx; this
0x100422319  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10042231e  movzx   ecx, word ptr [rdi+2]
0x100422322  add     rdi, 2
0x100422326  test    cx, cx
0x100422329  jnz     short loc_100422300
0x10042232b  jmp     loc_1004223D5
0x100422330  lea     rdi, aAmp; "&amp;"
0x100422337  movzx   ecx, bp
0x10042233a  nop     word ptr [rax+rax+00h]
0x100422340  mov     rax, [rbx+18h]
0x100422344  mov     [rax], cx
0x100422347  add     qword ptr [rbx+18h], 2
0x10042234c  mov     rax, [rbx+18h]
0x100422350  cmp     rax, [rbx+20h]
0x100422354  jb      short loc_10042235E
0x100422356  mov     rcx, rbx; this
0x100422359  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10042235e  movzx   ecx, word ptr [rdi+2]
0x100422362  add     rdi, 2
0x100422366  test    cx, cx
0x100422369  jnz     short loc_100422340
0x10042236b  jmp     short loc_1004223D5
0x10042236d  lea     rdi, aXd; "&#xD;"
0x100422374  movzx   ecx, bp
0x100422377  nop     word ptr [rax+rax+00000000h]
0x100422380  mov     rax, [rbx+18h]
0x100422384  mov     [rax], cx
0x100422387  add     qword ptr [rbx+18h], 2
0x10042238c  mov     rax, [rbx+18h]
0x100422390  cmp     rax, [rbx+20h]
0x100422394  jb      short loc_10042239E
0x100422396  mov     rcx, rbx; this
0x100422399  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10042239e  movzx   ecx, word ptr [rdi+2]
0x1004223a2  add     rdi, 2
0x1004223a6  test    cx, cx
0x1004223a9  jnz     short loc_100422380
0x1004223ab  jmp     short loc_1004223D5
0x1004223ad  mov     rax, [rbx+18h]
0x1004223b1  mov     [rax], r15w
0x1004223b5  jmp     short loc_1004223BE
0x1004223b7  mov     rax, [rbx+18h]
0x1004223bb  mov     [rax], cx
0x1004223be  add     qword ptr [rbx+18h], 2
0x1004223c3  mov     rax, [rbx+18h]
0x1004223c7  cmp     rax, [rbx+20h]
0x1004223cb  jb      short loc_1004223D5
0x1004223cd  mov     rcx, rbx; this
0x1004223d0  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x1004223d5  test    esi, esi
0x1004223d7  jnz     loc_100422270
0x1004223dd  mov     r15, [rsp+38h+var_18]
0x1004223e2  mov     rdi, [rsp+38h+arg_10]
0x1004223e7  mov     rbp, [rsp+38h+arg_0]
0x1004223ec  mov     rcx, [rbx+1100h]
0x1004223f3  mov     r14, [rsp+38h+var_10]
0x1004223f8  mov     rsi, [rsp+38h+arg_8]
0x1004223fd  test    rcx, rcx
0x100422400  jz      short loc_100422419
0x100422402  mov     eax, [rbx+18h]
0x100422405  add     rcx, 2
0x100422409  sub     eax, [rbx+28h]
0x10042240c  sar     rax, 1
0x10042240f  mov     [rbx+1100h], rcx
0x100422416  mov     [rcx], ax
0x100422419  add     rsp, 30h
0x10042241d  pop     rbx
0x10042241e  retn
```
