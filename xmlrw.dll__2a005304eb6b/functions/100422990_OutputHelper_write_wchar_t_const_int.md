# OutputHelper::write(wchar_t const *,int)

- ea: `0x100422990`
- end: `0x100422ab5`
- name: `?write@OutputHelper@@QEAAXPEB_WH@Z`
- size: `293`
- prototype: `void __fastcall(OutputHelper *__hidden this, const wchar_t *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x10041c0c0`
- `0x10041c0f0`
- `0x10041c2d0`

## callees

- `0x1004228c0`
- `0x100422990`
- `0x100422b70`

## pseudocode

```c
void __fastcall OutputHelper::write(OutputHelper *this, const wchar_t *a2, int a3)
{
  unsigned __int16 v6; // cx
  int v7; // ebp
  _WORD *v8; // rax
  bool v9; // zf
  _WORD *v10; // rax

  if ( *((_DWORD *)this + 12) )
    OutputHelper::_actuallyWriteWS(this);
  if ( a3 )
  {
    while ( 1 )
    {
      v6 = *a2;
      v7 = a3--;
      ++a2;
      if ( v6 > 0xDu )
        break;
      if ( v6 == 10 )
      {
        **((_WORD **)this + 3) = 13;
        *((_QWORD *)this + 3) += 2LL;
        v10 = (_WORD *)*((_QWORD *)this + 3);
        if ( (unsigned __int64)v10 >= *((_QWORD *)this + 4) )
        {
          OutputHelper::_hardWrite(this);
          v10 = (_WORD *)*((_QWORD *)this + 3);
        }
        *v10 = 10;
        goto LABEL_21;
      }
      if ( v6 != 13 )
        break;
      **((_WORD **)this + 3) = 13;
      *((_QWORD *)this + 3) += 2LL;
      v8 = (_WORD *)*((_QWORD *)this + 3);
      if ( (unsigned __int64)v8 >= *((_QWORD *)this + 4) )
      {
        OutputHelper::_hardWrite(this);
        v8 = (_WORD *)*((_QWORD *)this + 3);
      }
      *v8 = 10;
      *((_QWORD *)this + 3) += 2LL;
      if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
        OutputHelper::_hardWrite(this);
      if ( !a3 )
        return;
      v9 = *a2 == 10;
      if ( *a2 == 10 )
      {
        ++a2;
        v9 = 1;
      }
      if ( !v9 )
        a3 = v7;
      --a3;
LABEL_23:
      if ( !a3 )
        return;
    }
    **((_WORD **)this + 3) = v6;
LABEL_21:
    *((_QWORD *)this + 3) += 2LL;
    if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
      OutputHelper::_hardWrite(this);
    goto LABEL_23;
  }
}

```

## disassembly

```asm
0x100422990  push    rbx
0x100422992  push    rsi
0x100422993  push    rdi
0x100422994  sub     rsp, 20h
0x100422998  cmp     dword ptr [rcx+30h], 0
0x10042299c  mov     edi, r8d
0x10042299f  mov     rsi, rdx
0x1004229a2  mov     rbx, rcx
0x1004229a5  jz      short loc_1004229AC
0x1004229a7  call    ?_actuallyWriteWS@OutputHelper@@IEAAXXZ; OutputHelper::_actuallyWriteWS(void)
0x1004229ac  test    edi, edi
0x1004229ae  jz      loc_100422AAD
0x1004229b4  mov     [rsp+38h+arg_0], rbp
0x1004229b9  mov     [rsp+38h+arg_8], r14
0x1004229be  mov     [rsp+38h+arg_10], r15
0x1004229c3  mov     r15d, 0Dh
0x1004229c9  lea     r14d, [r15-3]
0x1004229cd  nop     dword ptr [rax]
0x1004229d0  movzx   ecx, word ptr [rsi]
0x1004229d3  mov     ebp, edi
0x1004229d5  dec     edi
0x1004229d7  add     rsi, 2
0x1004229db  cmp     cx, r15w
0x1004229df  ja      loc_100422A78
0x1004229e5  cmp     cx, r14w
0x1004229e9  jz      short loc_100422A4F
0x1004229eb  cmp     cx, r15w
0x1004229ef  jnz     loc_100422A78
0x1004229f5  mov     rax, [rbx+18h]
0x1004229f9  mov     [rax], r15w
0x1004229fd  add     qword ptr [rbx+18h], 2
0x100422a02  mov     rax, [rbx+18h]
0x100422a06  cmp     rax, [rbx+20h]
0x100422a0a  jb      short loc_100422A18
0x100422a0c  mov     rcx, rbx; this
0x100422a0f  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x100422a14  mov     rax, [rbx+18h]
0x100422a18  mov     [rax], r14w
0x100422a1c  add     qword ptr [rbx+18h], 2
0x100422a21  mov     rax, [rbx+18h]
0x100422a25  cmp     rax, [rbx+20h]
0x100422a29  jb      short loc_100422A33
0x100422a2b  mov     rcx, rbx; this
0x100422a2e  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x100422a33  test    edi, edi
0x100422a35  jz      short loc_100422A9E
0x100422a37  movzx   eax, word ptr [rsi]
0x100422a3a  cmp     ax, r14w
0x100422a3e  jnz     short loc_100422A48
0x100422a40  add     rsi, 2
0x100422a44  cmp     ax, r14w
0x100422a48  cmovnz  edi, ebp
0x100422a4b  dec     edi
0x100422a4d  jmp     short loc_100422A96
0x100422a4f  mov     rax, [rbx+18h]
0x100422a53  mov     [rax], r15w
0x100422a57  add     qword ptr [rbx+18h], 2
0x100422a5c  mov     rax, [rbx+18h]
0x100422a60  cmp     rax, [rbx+20h]
0x100422a64  jb      short loc_100422A72
0x100422a66  mov     rcx, rbx; this
0x100422a69  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x100422a6e  mov     rax, [rbx+18h]
0x100422a72  mov     [rax], r14w
0x100422a76  jmp     short loc_100422A7F
0x100422a78  mov     rax, [rbx+18h]
0x100422a7c  mov     [rax], cx
0x100422a7f  add     qword ptr [rbx+18h], 2
0x100422a84  mov     rax, [rbx+18h]
0x100422a88  cmp     rax, [rbx+20h]
0x100422a8c  jb      short loc_100422A96
0x100422a8e  mov     rcx, rbx; this
0x100422a91  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x100422a96  test    edi, edi
0x100422a98  jnz     loc_1004229D0
0x100422a9e  mov     r14, [rsp+38h+arg_8]
0x100422aa3  mov     rbp, [rsp+38h+arg_0]
0x100422aa8  mov     r15, [rsp+38h+arg_10]
0x100422aad  add     rsp, 20h
0x100422ab1  pop     rdi
0x100422ab2  pop     rsi
0x100422ab3  pop     rbx
0x100422ab4  retn
```
