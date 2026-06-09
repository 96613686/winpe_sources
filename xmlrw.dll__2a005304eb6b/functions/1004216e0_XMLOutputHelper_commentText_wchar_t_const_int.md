# XMLOutputHelper::commentText(wchar_t const *,int)

- ea: `0x1004216e0`
- end: `0x100421833`
- name: `?commentText@XMLOutputHelper@@QEAAXPEB_WH@Z`
- size: `339`
- prototype: `void __fastcall(XMLOutputHelper *__hidden this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10041c700`

## callees

- `0x1004216e0`
- `0x1004228c0`

## pseudocode

```c
void __fastcall XMLOutputHelper::commentText(XMLOutputHelper *this, const wchar_t *a2, int a3)
{
  int v3; // edi
  unsigned __int16 v6; // cx
  int v7; // ebp
  _WORD *v8; // rax
  _WORD *v9; // rax
  bool v10; // zf

  if ( a3 )
  {
    v3 = a3;
    while ( 1 )
    {
      v6 = *a2;
      v7 = v3--;
      ++a2;
      if ( v6 > 0x2Du )
        goto LABEL_20;
      if ( v6 == 10 )
        break;
      if ( v6 != 13 )
      {
        if ( v6 == 45 )
        {
          if ( *((_BYTE *)this + 4337) )
          {
            v8 = (_WORD *)*((_QWORD *)this + 3);
            if ( *(v8 - 1) == 45 )
            {
              *v8 = 32;
              *((_QWORD *)this + 3) += 2LL;
            }
          }
          v9 = (_WORD *)*((_QWORD *)this + 3);
          *((_BYTE *)this + 4337) = 1;
          *v9 = 45;
        }
        else
        {
LABEL_20:
          **((_WORD **)this + 3) = v6;
        }
LABEL_21:
        *((_QWORD *)this + 3) += 2LL;
        if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
          OutputHelper::_hardWrite(this);
        goto LABEL_23;
      }
      **((_WORD **)this + 3) = 13;
      *((_QWORD *)this + 3) += 2LL;
      **((_WORD **)this + 3) = 10;
      *((_QWORD *)this + 3) += 2LL;
      if ( *((_QWORD *)this + 3) >= *((_QWORD *)this + 4) )
        OutputHelper::_hardWrite(this);
      if ( !v3 )
        return;
      v10 = *a2 == 10;
      if ( *a2 == 10 )
      {
        ++a2;
        v10 = 1;
      }
      if ( !v10 )
        v3 = v7;
      --v3;
LABEL_23:
      if ( !v3 )
        return;
    }
    **((_WORD **)this + 3) = 13;
    *((_QWORD *)this + 3) += 2LL;
    **((_WORD **)this + 3) = 10;
    goto LABEL_21;
  }
}

```

## disassembly

```asm
0x1004216e0  test    r8d, r8d
0x1004216e3  jz      locret_100421832
0x1004216e9  push    rbx
0x1004216ea  push    rsi
0x1004216eb  push    rdi
0x1004216ec  sub     rsp, 30h
0x1004216f0  mov     [rsp+48h+arg_0], rbp
0x1004216f5  mov     edi, r8d
0x1004216f8  mov     [rsp+48h+arg_8], r12
0x1004216fd  mov     rsi, rdx
0x100421700  mov     r12d, 20h ; ' '
0x100421706  mov     [rsp+48h+arg_10], r13
0x10042170b  mov     [rsp+48h+var_20], r14
0x100421710  mov     rbx, rcx
0x100421713  mov     [rsp+48h+var_28], r15
0x100421718  lea     r13d, [r12+0Dh]
0x10042171d  lea     r14d, [r12-13h]
0x100421722  lea     r15d, [r12-16h]
0x100421727  nop     word ptr [rax+rax+00000000h]
0x100421730  movzx   ecx, word ptr [rsi]
0x100421733  mov     ebp, edi
0x100421735  dec     edi
0x100421737  add     rsi, 2
0x10042173b  cmp     cx, r13w
0x10042173f  ja      loc_1004217EC
0x100421745  cmp     cx, r15w
0x100421749  jz      loc_1004217D5
0x10042174f  cmp     cx, r14w
0x100421753  jz      short loc_10042178D
0x100421755  cmp     cx, r13w
0x100421759  jnz     loc_1004217EC
0x10042175f  cmp     byte ptr [rbx+10F1h], 0
0x100421766  jz      short loc_10042177C
0x100421768  mov     rax, [rbx+18h]
0x10042176c  cmp     [rax-2], r13w
0x100421771  jnz     short loc_10042177C
0x100421773  mov     [rax], r12w
0x100421777  add     qword ptr [rbx+18h], 2
0x10042177c  mov     rax, [rbx+18h]
0x100421780  mov     byte ptr [rbx+10F1h], 1
0x100421787  mov     [rax], r13w
0x10042178b  jmp     short loc_1004217F3
0x10042178d  mov     rax, [rbx+18h]
0x100421791  mov     [rax], r14w
0x100421795  add     qword ptr [rbx+18h], 2
0x10042179a  mov     rax, [rbx+18h]
0x10042179e  mov     [rax], r15w
0x1004217a2  add     qword ptr [rbx+18h], 2
0x1004217a7  mov     rax, [rbx+18h]
0x1004217ab  cmp     rax, [rbx+20h]
0x1004217af  jb      short loc_1004217B9
0x1004217b1  mov     rcx, rbx; this
0x1004217b4  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x1004217b9  test    edi, edi
0x1004217bb  jz      short loc_100421812
0x1004217bd  movzx   eax, word ptr [rsi]
0x1004217c0  cmp     ax, r15w
0x1004217c4  jnz     short loc_1004217CE
0x1004217c6  add     rsi, 2
0x1004217ca  cmp     ax, r15w
0x1004217ce  cmovnz  edi, ebp
0x1004217d1  dec     edi
0x1004217d3  jmp     short loc_10042180A
0x1004217d5  mov     rax, [rbx+18h]
0x1004217d9  mov     [rax], r14w
0x1004217dd  add     qword ptr [rbx+18h], 2
0x1004217e2  mov     rax, [rbx+18h]
0x1004217e6  mov     [rax], r15w
0x1004217ea  jmp     short loc_1004217F3
0x1004217ec  mov     rax, [rbx+18h]
0x1004217f0  mov     [rax], cx
0x1004217f3  add     qword ptr [rbx+18h], 2
0x1004217f8  mov     rax, [rbx+18h]
0x1004217fc  cmp     rax, [rbx+20h]
0x100421800  jb      short loc_10042180A
0x100421802  mov     rcx, rbx; this
0x100421805  call    ?_hardWrite@OutputHelper@@IEAAXXZ; OutputHelper::_hardWrite(void)
0x10042180a  test    edi, edi
0x10042180c  jnz     loc_100421730
0x100421812  mov     r14, [rsp+48h+var_20]
0x100421817  mov     r13, [rsp+48h+arg_10]
0x10042181c  mov     r12, [rsp+48h+arg_8]
0x100421821  mov     rbp, [rsp+48h+arg_0]
0x100421826  mov     r15, [rsp+48h+var_28]
0x10042182b  add     rsp, 30h
0x10042182f  pop     rdi
0x100421830  pop     rsi
0x100421831  pop     rbx
0x100421832  retn
```
