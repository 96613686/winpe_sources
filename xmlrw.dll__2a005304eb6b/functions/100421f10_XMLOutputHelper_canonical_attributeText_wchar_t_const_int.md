# XMLOutputHelper::canonical_attributeText(wchar_t const *,int)

- ea: `0x100421f10`
- end: `0x1004221f8`
- name: `?canonical_attributeText@XMLOutputHelper@@IEAAXPEB_WH@Z`
- size: `744`
- prototype: `void __fastcall(XMLOutputHelper *__hidden this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x10041c2d0`

## callees

- `0x100421f10`
- `0x1004228c0`

## pseudocode

```c
void __fastcall XMLOutputHelper::canonical_attributeText(XMLOutputHelper *this, const wchar_t *a2, int a3)
{
  _WORD *v3; // rax
  int v6; // esi
  __int64 v7; // rcx
  _WORD *v8; // rax
  unsigned int v9; // edx
  const wchar_t *v10; // rdi
  __int16 v11; // cx
  const wchar_t *v12; // rdi
  __int16 v13; // cx
  const wchar_t *v14; // rdi
  __int16 v15; // cx
  const wchar_t *v16; // rdi
  __int16 v17; // cx
  const wchar_t *v18; // rdi
  __int16 v19; // cx
  const wchar_t *v20; // rdi
  __int16 v21; // cx
  __int64 v22; // rcx
  _WORD *v23; // rcx
  __int64 v24; // rax

  v3 = (_WORD *)*((_QWORD *)this + 544);
  v6 = a3;
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
    do
    {
      v9 = *a2++;
      --v6;
      if ( v9 > 0x3C )
      {
LABEL_38:
        **((_WORD **)this + 3) = v9;
        *((_QWORD *)this + 3) += 2LL;
        if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
          OutputHelper::_hardWrite(this);
      }
      else
      {
        switch ( v9 )
        {
          case 9u:
            v10 = L"&#x9;";
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
            break;
          case 0xAu:
            v12 = L"&#xA;";
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
            break;
          case 0xDu:
            v14 = L"&#xD;";
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
            break;
          case 0x22u:
            v16 = L"&quot;";
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
            break;
          case 0x26u:
            v18 = L"&amp;";
            v19 = 38;
            do
            {
              **((_WORD **)this + 3) = v19;
              *((_QWORD *)this + 3) += 2LL;
              if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
                OutputHelper::_hardWrite(this);
              v19 = v18[1];
              ++v18;
            }
            while ( v19 );
            break;
          case 0x3Cu:
            v20 = L"&lt;";
            v21 = 38;
            do
            {
              **((_WORD **)this + 3) = v21;
              *((_QWORD *)this + 3) += 2LL;
              if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
                OutputHelper::_hardWrite(this);
              v21 = v20[1];
              ++v20;
            }
            while ( v21 );
            break;
          default:
            goto LABEL_38;
        }
      }
    }
    while ( v6 );
  }
  v22 = *((_QWORD *)this + 544);
  if ( v22 )
  {
    v23 = (_WORD *)(v22 + 2);
    v24 = (__int64)(unsigned int)(*((_DWORD *)this + 6) - *((_DWORD *)this + 10)) >> 1;
    *((_QWORD *)this + 544) = v23;
    *v23 = v24;
  }
}

```

## disassembly

```asm
0x100421f10  push    rbx
0x100421f12  sub     rsp, 30h
0x100421f16  mov     rax, [rcx+1100h]
0x100421f1d  mov     rbx, rcx
0x100421f20  mov     [rsp+38h+arg_0], rbp
0x100421f25  mov     rbp, rdx
0x100421f28  mov     [rsp+38h+arg_8], rsi
0x100421f2d  mov     esi, r8d
0x100421f30  test    rax, rax
0x100421f33  jz      short loc_100421F5E
0x100421f35  mov     ecx, [rcx+18h]
0x100421f38  sub     ecx, [rbx+28h]
0x100421f3b  sar     rcx, 1
0x100421f3e  cmp     cx, [rax]
0x100421f41  jz      short loc_100421F53
0x100421f43  add     rax, 2
0x100421f47  mov     [rbx+1100h], rax
0x100421f4e  mov     [rax], cx
0x100421f51  jmp     short loc_100421F5E
0x100421f53  add     rax, 0FFFFFFFFFFFFFFFEh
0x100421f57  mov     [rbx+1100h], rax
0x100421f5e  test    r8d, r8d
0x100421f61  jz      loc_100422172
0x100421f67  mov     [rsp+38h+arg_10], rdi
0x100421f6c  mov     [rsp+38h+var_10], r14
0x100421f71  lea     r14, __ImageBase
0x100421f78  mov     [rsp+38h+var_18], r15
0x100421f7d  mov     r15d, 26h ; '&'
0x100421f83  movzx   edx, word ptr [rbp+0]
0x100421f87  lea     rbp, [rbp+2]
0x100421f8b  dec     esi
0x100421f8d  cmp     edx, 3Ch ; '<'
0x100421f90  ja      def_100421FB8; jumptable 0000000100421FB8 default case, cases 11,12,14-33,35-37,39-59
0x100421f96  lea     eax, [rdx-9]; switch 52 cases
0x100421f99  cmp     eax, 33h
0x100421f9c  ja      def_100421FB8; jumptable 0000000100421FB8 default case, cases 11,12,14-33,35-37,39-59
0x100421fa2  cdqe
0x100421fa4  movzx   eax, ds:(byte_1004221C4 - 100400000h)[r14+rax]
0x100421fad  mov     ecx, ds:(jpt_100421FB8 - 100400000h)[r14+rax*4]
0x100421fb5  add     rcx, r14
0x100421fb8  jmp     rcx; switch jump
0x100421fba  lea     rdi, aX9; jumptable 0000000100421FB8 case 9
0x100421fc1  movzx   ecx, r15w
0x100421fc5  nop     word ptr [rax+rax+00000000h]
0x100421fd0  mov     rax, [rbx+18h]
0x100421fd4  mov     [rax], cx
0x100421fd7  add     qword ptr [rbx+18h], 2
0x100421fdc  mov     rax, [rbx+18h]
0x100421fe0  cmp     rax, [rbx+20h]
0x100421fe4  jb      short loc_100421FEE
0x100421fe6  mov     rcx, rbx; this
0x100421fe9  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x100421fee  movzx   ecx, word ptr [rdi+2]
0x100421ff2  add     rdi, 2
0x100421ff6  test    cx, cx
0x100421ff9  jnz     short loc_100421FD0
0x100421ffb  jmp     loc_10042215B
0x100422000  lea     rdi, aXa; jumptable 0000000100421FB8 case 10
0x100422007  movzx   ecx, r15w
0x10042200b  nop     dword ptr [rax+rax+00h]
0x100422010  mov     rax, [rbx+18h]
0x100422014  mov     [rax], cx
0x100422017  add     qword ptr [rbx+18h], 2
0x10042201c  mov     rax, [rbx+18h]
0x100422020  cmp     rax, [rbx+20h]
0x100422024  jb      short loc_10042202E
0x100422026  mov     rcx, rbx; this
0x100422029  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10042202e  movzx   ecx, word ptr [rdi+2]
0x100422032  add     rdi, 2
0x100422036  test    cx, cx
0x100422039  jnz     short loc_100422010
0x10042203b  jmp     loc_10042215B
0x100422040  lea     rdi, aXd; jumptable 0000000100421FB8 case 13
0x100422047  movzx   ecx, r15w
0x10042204b  nop     dword ptr [rax+rax+00h]
0x100422050  mov     rax, [rbx+18h]
0x100422054  mov     [rax], cx
0x100422057  add     qword ptr [rbx+18h], 2
0x10042205c  mov     rax, [rbx+18h]
0x100422060  cmp     rax, [rbx+20h]
0x100422064  jb      short loc_10042206E
0x100422066  mov     rcx, rbx; this
0x100422069  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10042206e  movzx   ecx, word ptr [rdi+2]
0x100422072  add     rdi, 2
0x100422076  test    cx, cx
0x100422079  jnz     short loc_100422050
0x10042207b  jmp     loc_10042215B
0x100422080  lea     rdi, aQuot; jumptable 0000000100421FB8 case 34
0x100422087  movzx   ecx, r15w
0x10042208b  nop     dword ptr [rax+rax+00h]
0x100422090  mov     rax, [rbx+18h]
0x100422094  mov     [rax], cx
0x100422097  add     qword ptr [rbx+18h], 2
0x10042209c  mov     rax, [rbx+18h]
0x1004220a0  cmp     rax, [rbx+20h]
0x1004220a4  jb      short loc_1004220AE
0x1004220a6  mov     rcx, rbx; this
0x1004220a9  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x1004220ae  movzx   ecx, word ptr [rdi+2]
0x1004220b2  add     rdi, 2
0x1004220b6  test    cx, cx
0x1004220b9  jnz     short loc_100422090
0x1004220bb  jmp     loc_10042215B
0x1004220c0  lea     rdi, aAmp; jumptable 0000000100421FB8 case 38
0x1004220c7  movzx   ecx, r15w
0x1004220cb  nop     dword ptr [rax+rax+00h]
0x1004220d0  mov     rax, [rbx+18h]
0x1004220d4  mov     [rax], cx
0x1004220d7  add     qword ptr [rbx+18h], 2
0x1004220dc  mov     rax, [rbx+18h]
0x1004220e0  cmp     rax, [rbx+20h]
0x1004220e4  jb      short loc_1004220EE
0x1004220e6  mov     rcx, rbx; this
0x1004220e9  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x1004220ee  movzx   ecx, word ptr [rdi+2]
0x1004220f2  add     rdi, 2
0x1004220f6  test    cx, cx
0x1004220f9  jnz     short loc_1004220D0
0x1004220fb  jmp     short loc_10042215B
0x1004220fd  lea     rdi, aLt; jumptable 0000000100421FB8 case 60
0x100422104  movzx   ecx, r15w
0x100422108  nop     dword ptr [rax+rax+00000000h]
0x100422110  mov     rax, [rbx+18h]
0x100422114  mov     [rax], cx
0x100422117  add     qword ptr [rbx+18h], 2
0x10042211c  mov     rax, [rbx+18h]
0x100422120  cmp     rax, [rbx+20h]
0x100422124  jb      short loc_10042212E
0x100422126  mov     rcx, rbx; this
0x100422129  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10042212e  movzx   ecx, word ptr [rdi+2]
0x100422132  add     rdi, 2
0x100422136  test    cx, cx
0x100422139  jnz     short loc_100422110
0x10042213b  jmp     short loc_10042215B
0x10042213d  mov     rax, [rbx+18h]; jumptable 0000000100421FB8 default case, cases 11,12,14-33,35-37,39-59
0x100422141  mov     [rax], dx
0x100422144  add     qword ptr [rbx+18h], 2
0x100422149  mov     rax, [rbx+18h]
0x10042214d  cmp     rax, [rbx+20h]
0x100422151  jb      short loc_10042215B
0x100422153  mov     rcx, rbx; this
0x100422156  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10042215b  test    esi, esi
0x10042215d  jnz     loc_100421F83
0x100422163  mov     r15, [rsp+38h+var_18]
0x100422168  mov     r14, [rsp+38h+var_10]
0x10042216d  mov     rdi, [rsp+38h+arg_10]
0x100422172  mov     rcx, [rbx+1100h]
0x100422179  mov     rsi, [rsp+38h+arg_8]
0x10042217e  mov     rbp, [rsp+38h+arg_0]
0x100422183  test    rcx, rcx
0x100422186  jz      short loc_10042219F
0x100422188  mov     eax, [rbx+18h]
0x10042218b  add     rcx, 2
0x10042218f  sub     eax, [rbx+28h]
0x100422192  sar     rax, 1
0x100422195  mov     [rbx+1100h], rcx
0x10042219c  mov     [rcx], ax
0x10042219f  add     rsp, 30h
0x1004221a3  pop     rbx
0x1004221a4  retn
```
