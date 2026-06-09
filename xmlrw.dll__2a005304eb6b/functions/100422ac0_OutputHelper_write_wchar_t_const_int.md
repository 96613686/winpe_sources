# OutputHelper::_write(wchar_t const *,int)

- ea: `0x100422ac0`
- end: `0x100422b5b`
- name: `?_write@OutputHelper@@IEAAXPEB_WH@Z`
- size: `155`
- prototype: `void __fastcall(OutputHelper *__hidden this, const wchar_t *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x10041c100`
- `0x10041c1b0`
- `0x10041c560`

## callees

- `0x1004228c0`
- `0x100422ac0`
- `0x100425d50`

## pseudocode

```c
void __fastcall OutputHelper::_write(OutputHelper *this, const wchar_t *a2, int a3)
{
  int v3; // edi
  const wchar_t *v4; // rsi
  size_t v6; // rdi

  v3 = a3;
  v4 = a2;
  if ( (unsigned int)a3 > 0x10 )
  {
    if ( a3 > 0 )
    {
      do
      {
        --v3;
        **((_WORD **)this + 3) = *v4;
        *((_QWORD *)this + 3) += 2LL;
        if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
          OutputHelper::_hardWrite(this);
        ++v4;
      }
      while ( v3 );
    }
  }
  else
  {
    v6 = 2LL * a3;
    memmove(*((void **)this + 3), a2, v6);
    *((_QWORD *)this + 3) += v6;
    if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
      OutputHelper::_hardWrite(this);
  }
}

```

## disassembly

```asm
0x100422ac0  mov     [rsp+arg_0], rbx
0x100422ac5  mov     [rsp+arg_8], rsi
0x100422aca  push    rdi
0x100422acb  sub     rsp, 20h
0x100422acf  movsxd  rdi, r8d
0x100422ad2  mov     rsi, rdx
0x100422ad5  mov     rbx, rcx
0x100422ad8  cmp     edi, 10h
0x100422adb  ja      short loc_100422B11
0x100422add  mov     rcx, [rcx+18h]; void *
0x100422ae1  add     rdi, rdi
0x100422ae4  mov     r8, rdi; Size
0x100422ae7  call    memmove
0x100422aec  add     [rbx+18h], rdi
0x100422af0  mov     rax, [rbx+18h]
0x100422af4  cmp     rax, [rbx+20h]
0x100422af8  jb      short loc_100422B4B
0x100422afa  mov     rcx, rbx; this
0x100422afd  mov     rbx, [rsp+28h+arg_0]
0x100422b02  mov     rsi, [rsp+28h+arg_8]
0x100422b07  add     rsp, 20h
0x100422b0b  pop     rdi
0x100422b0c  jmp     ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x100422b11  test    r8d, r8d
0x100422b14  jle     short loc_100422B4B
0x100422b16  nop     word ptr [rax+rax+00000000h]
0x100422b20  movzx   eax, word ptr [rsi]
0x100422b23  dec     edi
0x100422b25  mov     rcx, [rbx+18h]
0x100422b29  mov     [rcx], ax
0x100422b2c  add     qword ptr [rbx+18h], 2
0x100422b31  mov     rax, [rbx+18h]
0x100422b35  cmp     rax, [rbx+20h]
0x100422b39  jb      short loc_100422B43
0x100422b3b  mov     rcx, rbx; this
0x100422b3e  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x100422b43  add     rsi, 2
0x100422b47  test    edi, edi
0x100422b49  jnz     short loc_100422B20
0x100422b4b  mov     rbx, [rsp+28h+arg_0]
0x100422b50  mov     rsi, [rsp+28h+arg_8]
0x100422b55  add     rsp, 20h
0x100422b59  pop     rdi
0x100422b5a  retn
```
