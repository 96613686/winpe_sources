# XMLOutputHelper::cdataText(wchar_t const *,int)

- ea: `0x1004219a0`
- end: `0x100421b98`
- name: `?cdataText@XMLOutputHelper@@QEAAXPEB_WH@Z`
- size: `504`
- prototype: `void __fastcall(XMLOutputHelper *__hidden this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x10041c3f0`

## callees

- `0x1004219a0`
- `0x1004228c0`

## pseudocode

```c
void __fastcall XMLOutputHelper::cdataText(XMLOutputHelper *this, const wchar_t *a2, int a3)
{
  _WORD *v3; // rax
  int v6; // edi
  __int64 v7; // rcx
  _WORD *v8; // rax
  unsigned __int16 v9; // cx
  int v10; // ebp
  _WORD *v11; // rcx
  __int64 v12; // rcx
  bool v13; // zf
  __int64 v14; // rcx
  _WORD *v15; // rcx
  __int64 v16; // rax

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
      *v8 = v7 | 0x4000;
    }
  }
  if ( a3 )
  {
    while ( 1 )
    {
      v9 = *a2;
      v10 = v6--;
      ++a2;
      if ( v9 > 0x5Du )
        goto LABEL_25;
      if ( v9 == 10 )
        break;
      if ( v9 != 13 )
      {
        if ( v9 == 62 )
        {
          if ( !*((_BYTE *)this + 4336) || (v12 = *((_QWORD *)this + 3), *(_WORD *)(v12 - 2) != 93) )
          {
            **((_WORD **)this + 3) = 62;
            goto LABEL_26;
          }
          *(_OWORD *)v12 = *(_OWORD *)L"]]><![CDATA[>";
          *(_QWORD *)(v12 + 16) = *(_QWORD *)L"ATA[>";
          *(_WORD *)(v12 + 24) = aCdata[12];
          *((_QWORD *)this + 3) += 26LL;
        }
        else
        {
          if ( v9 == 93 )
          {
            v11 = (_WORD *)*((_QWORD *)this + 3);
            *((_BYTE *)this + 4336) = *(v11 - 1) == 93;
            *v11 = 93;
          }
          else
          {
LABEL_25:
            **((_WORD **)this + 3) = v9;
          }
LABEL_26:
          *((_QWORD *)this + 3) += 2LL;
        }
        if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
          OutputHelper::_hardWrite(this);
        goto LABEL_29;
      }
      **((_WORD **)this + 3) = 13;
      *((_QWORD *)this + 3) += 2LL;
      **((_WORD **)this + 3) = 10;
      *((_QWORD *)this + 3) += 2LL;
      if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
        OutputHelper::_hardWrite(this);
      if ( !v6 )
        goto LABEL_30;
      v13 = *a2 == 10;
      if ( *a2 == 10 )
      {
        ++a2;
        v13 = 1;
      }
      if ( !v13 )
        v6 = v10;
      --v6;
LABEL_29:
      if ( !v6 )
        goto LABEL_30;
    }
    **((_WORD **)this + 3) = 13;
    *((_QWORD *)this + 3) += 2LL;
    **((_WORD **)this + 3) = 10;
    goto LABEL_26;
  }
LABEL_30:
  v14 = *((_QWORD *)this + 544);
  if ( v14 )
  {
    v15 = (_WORD *)(v14 + 2);
    v16 = (__int64)(unsigned int)(*((_DWORD *)this + 6) - *((_DWORD *)this + 10)) >> 1;
    *((_QWORD *)this + 544) = v15;
    *v15 = v16;
  }
}

```

## disassembly

```asm
0x1004219a0  push    rbx
0x1004219a2  sub     rsp, 40h
0x1004219a6  mov     rax, [rcx+1100h]
0x1004219ad  mov     rbx, rcx
0x1004219b0  mov     [rsp+48h+arg_8], rsi
0x1004219b5  mov     rsi, rdx
0x1004219b8  mov     [rsp+48h+arg_10], rdi
0x1004219bd  mov     edi, r8d
0x1004219c0  test    rax, rax
0x1004219c3  jz      short loc_1004219F6
0x1004219c5  mov     ecx, [rcx+18h]
0x1004219c8  sub     ecx, [rbx+28h]
0x1004219cb  sar     rcx, 1
0x1004219ce  cmp     cx, [rax]
0x1004219d1  jz      short loc_1004219EB
0x1004219d3  add     rax, 2
0x1004219d7  mov     edx, 4000h
0x1004219dc  or      cx, dx
0x1004219df  mov     [rbx+1100h], rax
0x1004219e6  mov     [rax], cx
0x1004219e9  jmp     short loc_1004219F6
0x1004219eb  add     rax, 0FFFFFFFFFFFFFFFEh
0x1004219ef  mov     [rbx+1100h], rax
0x1004219f6  test    r8d, r8d
0x1004219f9  jz      loc_100421B65
0x1004219ff  mov     [rsp+48h+arg_0], rbp
0x100421a04  mov     [rsp+48h+var_10], r12
0x100421a09  mov     [rsp+48h+var_18], r13
0x100421a0e  mov     r13d, 5Dh ; ']'
0x100421a14  mov     [rsp+48h+var_20], r14
0x100421a19  mov     [rsp+48h+var_28], r15
0x100421a1e  lea     r12d, [r13-1Fh]
0x100421a22  lea     r14d, [r13-50h]
0x100421a26  lea     r15d, [r13-53h]
0x100421a2a  nop     word ptr [rax+rax+00h]
0x100421a30  movzx   ecx, word ptr [rsi]
0x100421a33  mov     ebp, edi
0x100421a35  dec     edi
0x100421a37  add     rsi, 2
0x100421a3b  cmp     cx, r13w
0x100421a3f  ja      loc_100421B26
0x100421a45  cmp     cx, r15w
0x100421a49  jz      loc_100421B0F
0x100421a4f  cmp     cx, r14w
0x100421a53  jz      short loc_100421AC7
0x100421a55  cmp     cx, r12w
0x100421a59  jz      short loc_100421A80
0x100421a5b  cmp     cx, r13w
0x100421a5f  jnz     loc_100421B26
0x100421a65  mov     rcx, [rbx+18h]
0x100421a69  cmp     [rcx-2], r13w
0x100421a6e  setz    al
0x100421a71  mov     [rbx+10F0h], al
0x100421a77  mov     [rcx], r13w
0x100421a7b  jmp     loc_100421B2D
0x100421a80  cmp     byte ptr [rbx+10F0h], 0
0x100421a87  jz      short loc_100421ABD
0x100421a89  mov     rcx, [rbx+18h]
0x100421a8d  cmp     [rcx-2], r13w
0x100421a92  jnz     short loc_100421ABD
0x100421a94  movups  xmm0, xmmword ptr cs:aCdata; "]]><![CDATA[>"
0x100421a9b  movups  xmmword ptr [rcx], xmm0
0x100421a9e  movsd   xmm1, qword ptr cs:aCdata+10h; "ATA[>"
0x100421aa6  movsd   qword ptr [rcx+10h], xmm1
0x100421aab  movzx   eax, word ptr cs:aCdata+18h; ">"
0x100421ab2  mov     [rcx+18h], ax
0x100421ab6  add     qword ptr [rbx+18h], 1Ah
0x100421abb  jmp     short loc_100421B32
0x100421abd  mov     rax, [rbx+18h]
0x100421ac1  mov     [rax], r12w
0x100421ac5  jmp     short loc_100421B2D
0x100421ac7  mov     rax, [rbx+18h]
0x100421acb  mov     [rax], r14w
0x100421acf  add     qword ptr [rbx+18h], 2
0x100421ad4  mov     rax, [rbx+18h]
0x100421ad8  mov     [rax], r15w
0x100421adc  add     qword ptr [rbx+18h], 2
0x100421ae1  mov     rax, [rbx+18h]
0x100421ae5  cmp     rax, [rbx+20h]
0x100421ae9  jb      short loc_100421AF3
0x100421aeb  mov     rcx, rbx; this
0x100421aee  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x100421af3  test    edi, edi
0x100421af5  jz      short loc_100421B4C
0x100421af7  movzx   eax, word ptr [rsi]
0x100421afa  cmp     ax, r15w
0x100421afe  jnz     short loc_100421B08
0x100421b00  add     rsi, 2
0x100421b04  cmp     ax, r15w
0x100421b08  cmovnz  edi, ebp
0x100421b0b  dec     edi
0x100421b0d  jmp     short loc_100421B44
0x100421b0f  mov     rax, [rbx+18h]
0x100421b13  mov     [rax], r14w
0x100421b17  add     qword ptr [rbx+18h], 2
0x100421b1c  mov     rax, [rbx+18h]
0x100421b20  mov     [rax], r15w
0x100421b24  jmp     short loc_100421B2D
0x100421b26  mov     rax, [rbx+18h]
0x100421b2a  mov     [rax], cx
0x100421b2d  add     qword ptr [rbx+18h], 2
0x100421b32  mov     rax, [rbx+18h]
0x100421b36  cmp     rax, [rbx+20h]
0x100421b3a  jb      short loc_100421B44
0x100421b3c  mov     rcx, rbx; this
0x100421b3f  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x100421b44  test    edi, edi
0x100421b46  jnz     loc_100421A30
0x100421b4c  mov     r14, [rsp+48h+var_20]
0x100421b51  mov     r13, [rsp+48h+var_18]
0x100421b56  mov     r12, [rsp+48h+var_10]
0x100421b5b  mov     rbp, [rsp+48h+arg_0]
0x100421b60  mov     r15, [rsp+48h+var_28]
0x100421b65  mov     rcx, [rbx+1100h]
0x100421b6c  mov     rdi, [rsp+48h+arg_10]
0x100421b71  mov     rsi, [rsp+48h+arg_8]
0x100421b76  test    rcx, rcx
0x100421b79  jz      short loc_100421B92
0x100421b7b  mov     eax, [rbx+18h]
0x100421b7e  add     rcx, 2
0x100421b82  sub     eax, [rbx+28h]
0x100421b85  sar     rax, 1
0x100421b88  mov     [rbx+1100h], rcx
0x100421b8f  mov     [rcx], ax
0x100421b92  add     rsp, 40h
0x100421b96  pop     rbx
0x100421b97  retn
```
