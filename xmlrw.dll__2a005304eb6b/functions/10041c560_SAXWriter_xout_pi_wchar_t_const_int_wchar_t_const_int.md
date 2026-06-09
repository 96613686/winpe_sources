# SAXWriter::xout_pi(wchar_t const *,int,wchar_t const *,int)

- ea: `0x10041c560`
- end: `0x10041c654`
- name: `?xout_pi@SAXWriter@@MEAAXPEB_WH0H@Z`
- size: `244`
- prototype: `void __fastcall(SAXWriter *__hidden this, const wchar_t *, int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x10041c560`
- `0x100421840`
- `0x1004228c0`
- `0x100422ac0`
- `0x100422b70`

## pseudocode

```c
void __fastcall SAXWriter::xout_pi(SAXWriter *this, wchar_t *a2, int a3, const wchar_t *a4, int a5)
{
  __int64 v5; // rbx
  bool v9; // zf
  wchar_t i; // cx

  v5 = *((_QWORD *)this + 13);
  v9 = *(_DWORD *)(v5 + 48) == 0;
  *(_BYTE *)(v5 + 4338) = 0;
  if ( !v9 )
    OutputHelper::_actuallyWriteWS((OutputHelper *)v5);
  **(_WORD **)(v5 + 24) = 60;
  *(_QWORD *)(v5 + 24) += 2LL;
  **(_WORD **)(v5 + 24) = 63;
  *(_QWORD *)(v5 + 24) += 2LL;
  if ( a3 == -1 )
  {
    for ( i = *a2; i; ++a2 )
    {
      **(_WORD **)(v5 + 24) = i;
      *(_QWORD *)(v5 + 24) += 2LL;
      if ( *(_QWORD *)(v5 + 24) >= *(_QWORD *)(v5 + 32) )
        OutputHelper::_hardWrite((OutputHelper *)v5);
      i = a2[1];
    }
  }
  else
  {
    OutputHelper::_write((OutputHelper *)v5, a2, a3);
  }
  XMLOutputHelper::piText((XMLOutputHelper *)v5, a4, a5);
  **(_WORD **)(v5 + 24) = 63;
  *(_QWORD *)(v5 + 24) += 2LL;
  **(_WORD **)(v5 + 24) = 62;
  *(_QWORD *)(v5 + 24) += 2LL;
}

```

## disassembly

```asm
0x10041c560  mov     [rsp+arg_0], rbx
0x10041c565  mov     [rsp+arg_8], rbp
0x10041c56a  mov     [rsp+arg_10], rsi
0x10041c56f  mov     [rsp+arg_18], rdi
0x10041c574  push    r14
0x10041c576  sub     rsp, 20h
0x10041c57a  mov     rbx, [rcx+68h]
0x10041c57e  mov     rbp, r9
0x10041c581  mov     esi, r8d
0x10041c584  mov     rdi, rdx
0x10041c587  cmp     dword ptr [rbx+30h], 0
0x10041c58b  mov     byte ptr [rbx+10F2h], 0
0x10041c592  jz      short loc_10041C59C
0x10041c594  mov     rcx, rbx; this
0x10041c597  call    ?_actuallyWriteWS@OutputHelper@@IEAAXXZ; OutputHelper::_actuallyWriteWS(void)
0x10041c59c  mov     rax, [rbx+18h]
0x10041c5a0  mov     ecx, 3Ch ; '<'
0x10041c5a5  mov     r14d, 3Fh ; '?'
0x10041c5ab  mov     [rax], cx
0x10041c5ae  add     qword ptr [rbx+18h], 2
0x10041c5b3  mov     rax, [rbx+18h]
0x10041c5b7  mov     [rax], r14w
0x10041c5bb  add     qword ptr [rbx+18h], 2
0x10041c5c0  cmp     esi, 0FFFFFFFFh
0x10041c5c3  jnz     short loc_10041C5FD
0x10041c5c5  movzx   ecx, word ptr [rdi]
0x10041c5c8  test    cx, cx
0x10041c5cb  jz      short loc_10041C60B
0x10041c5cd  nop     dword ptr [rax]
0x10041c5d0  mov     rax, [rbx+18h]
0x10041c5d4  mov     [rax], cx
0x10041c5d7  add     qword ptr [rbx+18h], 2
0x10041c5dc  mov     rax, [rbx+18h]
0x10041c5e0  cmp     rax, [rbx+20h]
0x10041c5e4  jb      short loc_10041C5EE
0x10041c5e6  mov     rcx, rbx; this
0x10041c5e9  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10041c5ee  movzx   ecx, word ptr [rdi+2]
0x10041c5f2  add     rdi, 2
0x10041c5f6  test    cx, cx
0x10041c5f9  jnz     short loc_10041C5D0
0x10041c5fb  jmp     short loc_10041C60B
0x10041c5fd  mov     r8d, esi; int
0x10041c600  mov     rdx, rdi; wchar_t *
0x10041c603  mov     rcx, rbx; this
0x10041c606  call    ?_write@OutputHelper@@IEAAXPEB_WH@Z; OutputHelper::_write(wchar_t const *,int)
0x10041c60b  mov     r8d, [rsp+28h+arg_20]; int
0x10041c610  mov     rdx, rbp; wchar_t *
0x10041c613  mov     rcx, rbx; this
0x10041c616  call    ?piText@XMLOutputHelper@@QEAAXPEB_WH@Z; XMLOutputHelper::piText(wchar_t const *,int)
0x10041c61b  mov     rax, [rbx+18h]
0x10041c61f  mov     ecx, 3Eh ; '>'
0x10041c624  mov     rbp, [rsp+28h+arg_8]
0x10041c629  mov     rsi, [rsp+28h+arg_10]
0x10041c62e  mov     rdi, [rsp+28h+arg_18]
0x10041c633  mov     [rax], r14w
0x10041c637  add     qword ptr [rbx+18h], 2
0x10041c63c  mov     rax, [rbx+18h]
0x10041c640  mov     [rax], cx
0x10041c643  add     qword ptr [rbx+18h], 2
0x10041c648  mov     rbx, [rsp+28h+arg_0]
0x10041c64d  add     rsp, 20h
0x10041c651  pop     r14
0x10041c653  retn
```
