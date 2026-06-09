# OutputHelper::_actuallyWriteWS(void)

- ea: `0x100422b70`
- end: `0x100422c27`
- name: `?_actuallyWriteWS@OutputHelper@@IEAAXXZ`
- size: `183`
- prototype: `void __fastcall(OutputHelper *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x10041c070`
- `0x10041c100`
- `0x10041c1b0`
- `0x10041c2d0`
- `0x10041c560`
- `0x10041c660`
- `0x10041c700`
- `0x100422990`

## callees

- `0x1004228c0`
- `0x100422b70`

## pseudocode

```c
void __fastcall OutputHelper::_actuallyWriteWS(OutputHelper *this)
{
  int v2; // edi

  if ( (*((_BYTE *)this + 48) & 1) != 0 )
  {
    **((_WORD **)this + 3) = 13;
    *((_QWORD *)this + 3) += 2LL;
    **((_WORD **)this + 3) = 10;
    *((_QWORD *)this + 3) += 2LL;
    if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
      OutputHelper::_hardWrite(this);
  }
  if ( (*((_BYTE *)this + 48) & 2) != 0 )
  {
    v2 = 0;
    if ( *((int *)this + 13) <= 0 )
    {
      *((_DWORD *)this + 12) = 0;
    }
    else
    {
      do
      {
        **((_WORD **)this + 3) = 9;
        *((_QWORD *)this + 3) += 2LL;
        if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
          OutputHelper::_hardWrite(this);
        ++v2;
      }
      while ( v2 < *((_DWORD *)this + 13) );
      *((_DWORD *)this + 12) = 0;
    }
  }
  else
  {
    *((_DWORD *)this + 12) = 0;
  }
}

```

## disassembly

```asm
0x100422b70  push    rbx
0x100422b72  sub     rsp, 20h
0x100422b76  test    byte ptr [rcx+30h], 1
0x100422b7a  mov     rbx, rcx
0x100422b7d  jz      short loc_100422BB3
0x100422b7f  mov     rax, [rcx+18h]
0x100422b83  mov     ecx, 0Dh
0x100422b88  mov     [rax], cx
0x100422b8b  mov     ecx, 0Ah
0x100422b90  add     qword ptr [rbx+18h], 2
0x100422b95  mov     rax, [rbx+18h]
0x100422b99  mov     [rax], cx
0x100422b9c  add     qword ptr [rbx+18h], 2
0x100422ba1  mov     rax, [rbx+18h]
0x100422ba5  cmp     rax, [rbx+20h]
0x100422ba9  jb      short loc_100422BB3
0x100422bab  mov     rcx, rbx; this
0x100422bae  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x100422bb3  test    byte ptr [rbx+30h], 2
0x100422bb7  jz      short loc_100422C1A
0x100422bb9  mov     [rsp+28h+arg_8], rdi
0x100422bbe  xor     edi, edi
0x100422bc0  cmp     [rbx+34h], edi
0x100422bc3  jle     short loc_100422C0C
0x100422bc5  mov     [rsp+28h+arg_0], rbp
0x100422bca  mov     ebp, 9
0x100422bcf  nop
0x100422bd0  mov     rax, [rbx+18h]
0x100422bd4  mov     [rax], bp
0x100422bd7  add     qword ptr [rbx+18h], 2
0x100422bdc  mov     rax, [rbx+18h]
0x100422be0  cmp     rax, [rbx+20h]
0x100422be4  jb      short loc_100422BEE
0x100422be6  mov     rcx, rbx; this
0x100422be9  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x100422bee  inc     edi
0x100422bf0  cmp     edi, [rbx+34h]
0x100422bf3  jl      short loc_100422BD0
0x100422bf5  mov     rbp, [rsp+28h+arg_0]
0x100422bfa  mov     rdi, [rsp+28h+arg_8]
0x100422bff  mov     dword ptr [rbx+30h], 0
0x100422c06  add     rsp, 20h
0x100422c0a  pop     rbx
0x100422c0b  retn
0x100422c0c  mov     [rbx+30h], edi
0x100422c0f  mov     rdi, [rsp+28h+arg_8]
0x100422c14  add     rsp, 20h
0x100422c18  pop     rbx
0x100422c19  retn
0x100422c1a  mov     dword ptr [rbx+30h], 0
0x100422c21  add     rsp, 20h
0x100422c25  pop     rbx
0x100422c26  retn
```
