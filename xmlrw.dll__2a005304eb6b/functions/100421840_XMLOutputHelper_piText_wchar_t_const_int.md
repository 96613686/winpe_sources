# XMLOutputHelper::piText(wchar_t const *,int)

- ea: `0x100421840`
- end: `0x100421998`
- name: `?piText@XMLOutputHelper@@QEAAXPEB_WH@Z`
- size: `344`
- prototype: `void __fastcall(XMLOutputHelper *__hidden this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x10041c560`

## callees

- `0x100421840`
- `0x1004228c0`

## pseudocode

```c
void __fastcall XMLOutputHelper::piText(XMLOutputHelper *this, const wchar_t *a2, int a3)
{
  int v3; // edi
  unsigned __int16 v6; // cx
  int v7; // ebp
  _WORD *v8; // rax
  bool v9; // zf

  v3 = a3;
  if ( *((_BYTE *)this + 4338) )
  {
    if ( !a3 )
      return;
    while ( 1 )
    {
LABEL_5:
      v6 = *a2;
      v7 = v3--;
      ++a2;
      if ( v6 > 0x3Fu )
        goto LABEL_21;
      if ( v6 == 10 )
        break;
      if ( v6 != 13 )
      {
        if ( v6 == 62 )
        {
          v8 = (_WORD *)*((_QWORD *)this + 3);
          if ( *(v8 - 1) == 63 )
          {
            *v8 = 32;
            *((_QWORD *)this + 3) += 2LL;
            v8 = (_WORD *)*((_QWORD *)this + 3);
          }
          *v8 = 62;
        }
        else
        {
LABEL_21:
          **((_WORD **)this + 3) = v6;
        }
LABEL_22:
        *((_QWORD *)this + 3) += 2LL;
        if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
          OutputHelper::_hardWrite(this);
        goto LABEL_24;
      }
      **((_WORD **)this + 3) = 13;
      *((_QWORD *)this + 3) += 2LL;
      **((_WORD **)this + 3) = 10;
      *((_QWORD *)this + 3) += 2LL;
      if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
        OutputHelper::_hardWrite(this);
      if ( !v3 )
        return;
      v9 = *a2 == 10;
      if ( *a2 == 10 )
      {
        ++a2;
        v9 = 1;
      }
      if ( !v9 )
        v3 = v7;
      --v3;
LABEL_24:
      if ( !v3 )
        return;
    }
    **((_WORD **)this + 3) = 13;
    *((_QWORD *)this + 3) += 2LL;
    **((_WORD **)this + 3) = 10;
    goto LABEL_22;
  }
  if ( a3 )
  {
    **((_WORD **)this + 3) = 32;
    *((_QWORD *)this + 3) += 2LL;
    *((_BYTE *)this + 4338) = 1;
    goto LABEL_5;
  }
}

```

## disassembly

```asm
0x100421840  push    rbx
0x100421842  push    rsi
0x100421843  push    rdi
0x100421844  push    r12
0x100421846  sub     rsp, 28h
0x10042184a  cmp     byte ptr [rcx+10F2h], 0
0x100421851  mov     edi, r8d
0x100421854  mov     rsi, rdx
0x100421857  mov     rbx, rcx
0x10042185a  mov     r12d, 20h ; ' '
0x100421860  jnz     short loc_100421881
0x100421862  test    r8d, r8d
0x100421865  jz      loc_10042198E
0x10042186b  mov     rax, [rcx+18h]
0x10042186f  mov     [rax], r12w
0x100421873  add     qword ptr [rcx+18h], 2
0x100421878  mov     byte ptr [rcx+10F2h], 1
0x10042187f  jmp     short loc_10042188A
0x100421881  test    r8d, r8d
0x100421884  jz      loc_10042198E
0x10042188a  mov     [rsp+48h+arg_0], rbp
0x10042188f  mov     [rsp+48h+arg_8], r13
0x100421894  mov     r13d, 3Eh ; '>'
0x10042189a  mov     [rsp+48h+arg_10], r14
0x10042189f  mov     [rsp+48h+var_28], r15
0x1004218a4  lea     r14d, [r13-31h]
0x1004218a8  lea     r15d, [r13-34h]
0x1004218ac  nop     dword ptr [rax+00h]
0x1004218b0  movzx   ecx, word ptr [rsi]
0x1004218b3  mov     ebp, edi
0x1004218b5  dec     edi
0x1004218b7  add     rsi, 2
0x1004218bb  cmp     cx, 3Fh ; '?'
0x1004218bf  ja      loc_100421954
0x1004218c5  cmp     cx, r15w
0x1004218c9  jz      short loc_10042193D
0x1004218cb  cmp     cx, r14w
0x1004218cf  jz      short loc_1004218F5
0x1004218d1  cmp     cx, r13w
0x1004218d5  jnz     short loc_100421954
0x1004218d7  mov     rax, [rbx+18h]
0x1004218db  cmp     word ptr [rax-2], 3Fh ; '?'
0x1004218e0  jnz     short loc_1004218EF
0x1004218e2  mov     [rax], r12w
0x1004218e6  add     qword ptr [rbx+18h], 2
0x1004218eb  mov     rax, [rbx+18h]
0x1004218ef  mov     [rax], r13w
0x1004218f3  jmp     short loc_10042195B
0x1004218f5  mov     rax, [rbx+18h]
0x1004218f9  mov     [rax], r14w
0x1004218fd  add     qword ptr [rbx+18h], 2
0x100421902  mov     rax, [rbx+18h]
0x100421906  mov     [rax], r15w
0x10042190a  add     qword ptr [rbx+18h], 2
0x10042190f  mov     rax, [rbx+18h]
0x100421913  cmp     rax, [rbx+20h]
0x100421917  jb      short loc_100421921
0x100421919  mov     rcx, rbx; this
0x10042191c  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x100421921  test    edi, edi
0x100421923  jz      short loc_10042197A
0x100421925  movzx   eax, word ptr [rsi]
0x100421928  cmp     ax, r15w
0x10042192c  jnz     short loc_100421936
0x10042192e  add     rsi, 2
0x100421932  cmp     ax, r15w
0x100421936  cmovnz  edi, ebp
0x100421939  dec     edi
0x10042193b  jmp     short loc_100421972
0x10042193d  mov     rax, [rbx+18h]
0x100421941  mov     [rax], r14w
0x100421945  add     qword ptr [rbx+18h], 2
0x10042194a  mov     rax, [rbx+18h]
0x10042194e  mov     [rax], r15w
0x100421952  jmp     short loc_10042195B
0x100421954  mov     rax, [rbx+18h]
0x100421958  mov     [rax], cx
0x10042195b  add     qword ptr [rbx+18h], 2
0x100421960  mov     rax, [rbx+18h]
0x100421964  cmp     rax, [rbx+20h]
0x100421968  jb      short loc_100421972
0x10042196a  mov     rcx, rbx; this
0x10042196d  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x100421972  test    edi, edi
0x100421974  jnz     loc_1004218B0
0x10042197a  mov     r14, [rsp+48h+arg_10]
0x10042197f  mov     r13, [rsp+48h+arg_8]
0x100421984  mov     rbp, [rsp+48h+arg_0]
0x100421989  mov     r15, [rsp+48h+var_28]
0x10042198e  add     rsp, 28h
0x100421992  pop     r12
0x100421994  pop     rdi
0x100421995  pop     rsi
0x100421996  pop     rbx
0x100421997  retn
```
