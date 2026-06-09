# XMLOutputHelper::xmlDecl(TriState,wchar_t const *,bool)

- ea: `0x1004214b0`
- end: `0x1004216d0`
- name: `?xmlDecl@XMLOutputHelper@@QEAAXW4TriState@@PEB_W_N@Z`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x10041c980`

## callees

- `0x1004214b0`
- `0x1004228c0`

## string_xrefs

- `0x1004214ca`: `<?xml version="`

## pseudocode

```c
void __fastcall XMLOutputHelper::xmlDecl(OutputHelper *a1, int a2, const OLECHAR *a3, char a4)
{
  __int64 v6; // rcx
  unsigned __int64 v9; // rcx
  const OLECHAR *v10; // rdi
  OLECHAR v11; // dx
  unsigned __int64 v12; // rax
  __int16 *v13; // rdi
  __int16 v14; // dx
  _WORD *v15; // rax
  unsigned __int64 v16; // rcx

  v6 = *((_QWORD *)a1 + 3);
  *(_OWORD *)v6 = *(_OWORD *)L"<?xml version=\"";
  *(_QWORD *)(v6 + 16) = *(_QWORD *)L"rsion=\"";
  *(_DWORD *)(v6 + 24) = *(_DWORD *)L"n=\"";
  *(_WORD *)(v6 + 28) = aXmlVersion[14];
  *((_QWORD *)a1 + 3) += 30LL;
  v9 = *((_QWORD *)a1 + 3);
  if ( v9 >= *((_QWORD *)a1 + 4) )
  {
    OutputHelper::_hardWrite(a1);
    v9 = *((_QWORD *)a1 + 3);
  }
  v10 = L"1.0";
  if ( a3 )
    v10 = a3;
  v11 = *v10;
  if ( *v10 )
  {
    do
    {
      **((_WORD **)a1 + 3) = v11;
      *((_QWORD *)a1 + 3) += 2LL;
      v9 = *((_QWORD *)a1 + 3);
      if ( v9 >= *((_QWORD *)a1 + 4) )
      {
        OutputHelper::_hardWrite(a1);
        v9 = *((_QWORD *)a1 + 3);
      }
      v11 = v10[1];
      ++v10;
      v12 = v9;
    }
    while ( v11 );
  }
  else
  {
    v12 = v9;
  }
  if ( !a4 )
  {
    *(_OWORD *)v12 = *(_OWORD *)L"\" encoding=\"";
    *(_QWORD *)(v12 + 16) = *(_QWORD *)L"ng=\"";
    *((_QWORD *)a1 + 3) += 24LL;
    v9 = *((_QWORD *)a1 + 3);
    if ( v9 >= *((_QWORD *)a1 + 4) )
    {
      OutputHelper::_hardWrite(a1);
      v9 = *((_QWORD *)a1 + 3);
    }
    v13 = (__int16 *)*((_QWORD *)a1 + 27);
    v14 = *v13;
    if ( *v13 )
    {
      v15 = (_WORD *)v9;
      do
      {
        *v15 = v14;
        *((_QWORD *)a1 + 3) += 2LL;
        v9 = *((_QWORD *)a1 + 3);
        if ( v9 >= *((_QWORD *)a1 + 4) )
        {
          OutputHelper::_hardWrite(a1);
          v9 = *((_QWORD *)a1 + 3);
        }
        v14 = v13[1];
        ++v13;
        v15 = (_WORD *)v9;
      }
      while ( v14 );
    }
  }
  if ( a2 != -1 )
  {
    *(_OWORD *)v9 = *(_OWORD *)L"\" standalone=\"";
    *(_QWORD *)(v9 + 16) = *(_QWORD *)L"lone=\"";
    *(_DWORD *)(v9 + 24) = *(_DWORD *)L"=\"";
    *((_QWORD *)a1 + 3) += 28LL;
    v16 = *((_QWORD *)a1 + 3);
    if ( v16 >= *((_QWORD *)a1 + 4) )
    {
      OutputHelper::_hardWrite(a1);
      v16 = *((_QWORD *)a1 + 3);
    }
    if ( a2 == 1 )
    {
      *(_DWORD *)v16 = *(_DWORD *)L"yes";
      *(_WORD *)(v16 + 4) = aYes[2];
      *((_QWORD *)a1 + 3) += 6LL;
    }
    else
    {
      *(_DWORD *)v16 = 7274606;
      *((_QWORD *)a1 + 3) += 4LL;
    }
    if ( *((_QWORD *)a1 + 3) >= *((_QWORD *)a1 + 4) )
      OutputHelper::_hardWrite(a1);
  }
  **((_WORD **)a1 + 3) = 34;
  *((_QWORD *)a1 + 3) += 2LL;
  **((_WORD **)a1 + 3) = 63;
  *((_QWORD *)a1 + 3) += 2LL;
  **((_WORD **)a1 + 3) = 62;
  *((_QWORD *)a1 + 3) += 2LL;
  if ( *((_QWORD *)a1 + 3) >= *((_QWORD *)a1 + 4) )
    OutputHelper::_hardWrite(a1);
}

```

## disassembly

```asm
0x1004214b0  mov     [rsp+arg_0], rbx
0x1004214b5  mov     [rsp+arg_8], rbp
0x1004214ba  mov     [rsp+arg_10], rsi
0x1004214bf  mov     [rsp+arg_18], rdi
0x1004214c4  push    r14
0x1004214c6  sub     rsp, 20h
0x1004214ca  movups  xmm0, xmmword ptr cs:aXmlVersion; "<?xml version=\""
0x1004214d1  mov     rbx, rcx
0x1004214d4  movzx   ebp, r9b
0x1004214d8  mov     rcx, [rcx+18h]
0x1004214dc  mov     rsi, r8
0x1004214df  mov     r14d, edx
0x1004214e2  movups  xmmword ptr [rcx], xmm0
0x1004214e5  movsd   xmm1, qword ptr cs:aXmlVersion+10h; "rsion=\""
0x1004214ed  movsd   qword ptr [rcx+10h], xmm1
0x1004214f2  mov     eax, dword ptr cs:aXmlVersion+18h; "n=\""
0x1004214f8  mov     [rcx+18h], eax
0x1004214fb  movzx   eax, word ptr cs:aXmlVersion+1Ch; "\""
0x100421502  mov     [rcx+1Ch], ax
0x100421506  add     qword ptr [rbx+18h], 1Eh
0x10042150b  mov     rcx, [rbx+18h]
0x10042150f  cmp     rcx, [rbx+20h]
0x100421513  jb      short loc_100421521
0x100421515  mov     rcx, rbx; this
0x100421518  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10042151d  mov     rcx, [rbx+18h]
0x100421521  test    rsi, rsi
0x100421524  lea     rdi, psz; "1.0"
0x10042152b  cmovnz  rdi, rsi
0x10042152f  movzx   edx, word ptr [rdi]
0x100421532  test    dx, dx
0x100421535  jz      short loc_100421574
0x100421537  nop     word ptr [rax+rax+00000000h]
0x100421540  mov     rax, [rbx+18h]
0x100421544  mov     [rax], dx
0x100421547  add     qword ptr [rbx+18h], 2
0x10042154c  mov     rcx, [rbx+18h]
0x100421550  cmp     rcx, [rbx+20h]
0x100421554  jb      short loc_100421562
0x100421556  mov     rcx, rbx; this
0x100421559  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10042155e  mov     rcx, [rbx+18h]
0x100421562  movzx   edx, word ptr [rdi+2]
0x100421566  add     rdi, 2
0x10042156a  mov     rax, rcx
0x10042156d  test    dx, dx
0x100421570  jnz     short loc_100421540
0x100421572  jmp     short loc_100421577
0x100421574  mov     rax, rcx
0x100421577  test    bpl, bpl
0x10042157a  jnz     short loc_1004215EE
0x10042157c  movups  xmm0, xmmword ptr cs:aEncoding; "\" encoding=\""
0x100421583  movups  xmmword ptr [rax], xmm0
0x100421586  movsd   xmm1, qword ptr cs:aEncoding+10h; "ng=\""
0x10042158e  movsd   qword ptr [rax+10h], xmm1
0x100421593  add     qword ptr [rbx+18h], 18h
0x100421598  mov     rcx, [rbx+18h]
0x10042159c  cmp     rcx, [rbx+20h]
0x1004215a0  jb      short loc_1004215AE
0x1004215a2  mov     rcx, rbx; this
0x1004215a5  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x1004215aa  mov     rcx, [rbx+18h]
0x1004215ae  mov     rdi, [rbx+0D8h]
0x1004215b5  movzx   edx, word ptr [rdi]
0x1004215b8  test    dx, dx
0x1004215bb  jz      short loc_1004215EE
0x1004215bd  mov     rax, rcx
0x1004215c0  mov     [rax], dx
0x1004215c3  add     qword ptr [rbx+18h], 2
0x1004215c8  mov     rcx, [rbx+18h]
0x1004215cc  cmp     rcx, [rbx+20h]
0x1004215d0  jb      short loc_1004215DE
0x1004215d2  mov     rcx, rbx; this
0x1004215d5  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x1004215da  mov     rcx, [rbx+18h]
0x1004215de  movzx   edx, word ptr [rdi+2]
0x1004215e2  add     rdi, 2
0x1004215e6  mov     rax, rcx
0x1004215e9  test    dx, dx
0x1004215ec  jnz     short loc_1004215C0
0x1004215ee  cmp     r14d, 0FFFFFFFFh
0x1004215f2  jz      short loc_100421670
0x1004215f4  movups  xmm0, xmmword ptr cs:aStandalone; "\" standalone=\""
0x1004215fb  movups  xmmword ptr [rcx], xmm0
0x1004215fe  movsd   xmm1, qword ptr cs:aStandalone+10h; "lone=\""
0x100421606  movsd   qword ptr [rcx+10h], xmm1
0x10042160b  mov     eax, dword ptr cs:aStandalone+18h; "=\""
0x100421611  mov     [rcx+18h], eax
0x100421614  add     qword ptr [rbx+18h], 1Ch
0x100421619  mov     rcx, [rbx+18h]
0x10042161d  cmp     rcx, [rbx+20h]
0x100421621  jb      short loc_10042162F
0x100421623  mov     rcx, rbx; this
0x100421626  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10042162b  mov     rcx, [rbx+18h]
0x10042162f  cmp     r14d, 1
0x100421633  jnz     short loc_10042164F
0x100421635  mov     eax, dword ptr cs:aYes; "yes"
0x10042163b  mov     [rcx], eax
0x10042163d  movzx   eax, word ptr cs:aYes+4; "s"
0x100421644  mov     [rcx+4], ax
0x100421648  add     qword ptr [rbx+18h], 6
0x10042164d  jmp     short loc_10042165A
0x10042164f  mov     dword ptr [rcx], 6F006Eh
0x100421655  add     qword ptr [rbx+18h], 4
0x10042165a  mov     rax, [rbx+18h]
0x10042165e  cmp     rax, [rbx+20h]
0x100421662  jb      short loc_100421670
0x100421664  mov     rcx, rbx; this
0x100421667  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10042166c  nop     dword ptr [rax+00h]
0x100421670  mov     rax, [rbx+18h]
0x100421674  mov     ecx, 22h ; '"'
0x100421679  mov     [rax], cx
0x10042167c  mov     ecx, 3Fh ; '?'
0x100421681  add     qword ptr [rbx+18h], 2
0x100421686  mov     rax, [rbx+18h]
0x10042168a  mov     [rax], cx
0x10042168d  mov     ecx, 3Eh ; '>'
0x100421692  add     qword ptr [rbx+18h], 2
0x100421697  mov     rax, [rbx+18h]
0x10042169b  mov     [rax], cx
0x10042169e  add     qword ptr [rbx+18h], 2
0x1004216a3  mov     rax, [rbx+18h]
0x1004216a7  cmp     rax, [rbx+20h]
0x1004216ab  jb      short loc_1004216B5
0x1004216ad  mov     rcx, rbx; this
0x1004216b0  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x1004216b5  mov     rbx, [rsp+28h+arg_0]
0x1004216ba  mov     rbp, [rsp+28h+arg_8]
0x1004216bf  mov     rsi, [rsp+28h+arg_10]
0x1004216c4  mov     rdi, [rsp+28h+arg_18]
0x1004216c9  add     rsp, 20h
0x1004216cd  pop     r14
0x1004216cf  retn
```
