# CAutoComplete::_DrawGrip(HDC__ *,tagRECT const *,int)

- ea: `0x1803f473c`
- end: `0x1803f499f`
- name: `?_DrawGrip@CAutoComplete@@IEBAHPEAUHDC__@@PEBUtagRECT@@H@Z`
- size: `611`
- prototype: `int(CAutoComplete *__hidden this, HDC, const struct tagRECT *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180089df0`

## callees

- `0x1803f473c`

## import_xrefs

- `USER32!GetSysColorBrush` at `0x1803f4789`
- `USER32!GetSysColorBrush` at `0x1803f4789`
- `USER32!GetSysColor` at `0x1803f4796`
- `USER32!GetSysColor` at `0x1803f47a7`
- `USER32!GetSysColor` at `0x1803f47fd`
- `USER32!GetSysColor` at `0x1803f4796`
- `USER32!GetSysColor` at `0x1803f47a7`
- `USER32!GetSysColor` at `0x1803f47fd`
- `GDI32!DeleteObject` at `0x1803f4873`
- `GDI32!DeleteObject` at `0x1803f48e7`
- `GDI32!DeleteObject` at `0x1803f497d`
- `GDI32!DeleteObject` at `0x1803f4873`
- `GDI32!DeleteObject` at `0x1803f48e7`
- `GDI32!DeleteObject` at `0x1803f497d`
- `GDI32!SelectObject` at `0x1803f47bb`
- `GDI32!SelectObject` at `0x1803f47f2`
- `GDI32!SelectObject` at `0x1803f4825`
- `GDI32!SelectObject` at `0x1803f486a`
- `GDI32!SelectObject` at `0x1803f48a0`
- `GDI32!SelectObject` at `0x1803f48de`
- `GDI32!SelectObject` at `0x1803f4911`
- `GDI32!SelectObject` at `0x1803f4974`
- `GDI32!SelectObject` at `0x1803f47bb`
- `GDI32!SelectObject` at `0x1803f47f2`
- `GDI32!SelectObject` at `0x1803f4825`
- `GDI32!SelectObject` at `0x1803f486a`
- `GDI32!SelectObject` at `0x1803f48a0`
- `GDI32!SelectObject` at `0x1803f48de`
- `GDI32!SelectObject` at `0x1803f4911`
- `GDI32!SelectObject` at `0x1803f4974`
- `GDI32!CreatePen` at `0x1803f480d`
- `GDI32!CreatePen` at `0x1803f4888`
- `GDI32!CreatePen` at `0x1803f48fd`
- `GDI32!CreatePen` at `0x1803f480d`
- `GDI32!CreatePen` at `0x1803f4888`
- `GDI32!CreatePen` at `0x1803f48fd`
- `GDI32!PatBlt` at `0x1803f47e6`
- `GDI32!PatBlt` at `0x1803f47e6`
- `GDI32!MoveToEx` at `0x1803f4845`
- `GDI32!MoveToEx` at `0x1803f48b9`
- `GDI32!MoveToEx` at `0x1803f492f`
- `GDI32!MoveToEx` at `0x1803f494f`
- `GDI32!MoveToEx` at `0x1803f4845`
- `GDI32!MoveToEx` at `0x1803f48b9`
- `GDI32!MoveToEx` at `0x1803f492f`
- `GDI32!MoveToEx` at `0x1803f494f`
- `GDI32!LineTo` at `0x1803f4853`
- `GDI32!LineTo` at `0x1803f48c7`
- `GDI32!LineTo` at `0x1803f493d`
- `GDI32!LineTo` at `0x1803f495e`
- `GDI32!LineTo` at `0x1803f4853`
- `GDI32!LineTo` at `0x1803f48c7`
- `GDI32!LineTo` at `0x1803f493d`
- `GDI32!LineTo` at `0x1803f495e`

## pseudocode

```c
__int64 __fastcall CAutoComplete::_DrawGrip(CAutoComplete *this, HDC a2, const struct tagRECT *a3, int a4)
{
  LONG top; // r11d
  int v7; // eax
  int v9; // ebp
  int v10; // r12d
  HBRUSH SysColorBrush; // r14
  HGDIOBJ v12; // rbx
  COLORREF v13; // eax
  HPEN Pen; // rax
  HPEN v15; // r15
  HGDIOBJ v16; // r13
  int v17; // r14d
  int i; // ebx
  HPEN v19; // rax
  HPEN v20; // r14
  HGDIOBJ v21; // rax
  LONG v22; // r15d
  void *v23; // r13
  LONG j; // ebx
  HPEN v25; // rax
  HPEN v26; // r14
  HGDIOBJ v27; // r15
  int v28; // ebx
  int v29; // edi
  DWORD SysColor; // [rsp+70h] [rbp+8h]
  DWORD color; // [rsp+88h] [rbp+20h]

  top = a3->top;
  v7 = a3->right - a3->left;
  if ( v7 >= a3->bottom - top )
    v7 = a3->bottom - top;
  v9 = v7 + a3->left;
  v10 = v7 + top;
  SysColorBrush = GetSysColorBrush(15);
  color = GetSysColor(20);
  SysColor = GetSysColor(16);
  if ( a4 )
  {
    v12 = SelectObject(a2, SysColorBrush);
    PatBlt(a2, a3->left, a3->top, a3->right - a3->left, a3->bottom - a3->top, 0xF00021u);
    SelectObject(a2, v12);
  }
  else
  {
    v13 = GetSysColor(15);
    Pen = CreatePen(0, 1, v13);
    v15 = Pen;
    if ( !Pen )
      return 0;
    v16 = SelectObject(a2, Pen);
    v17 = a3->top + 3;
    for ( i = a3->left + 3; i < v9; i += 4 )
    {
      MoveToEx(a2, i, v10, 0);
      LineTo(a2, v9, v17);
      v17 += 4;
    }
    SelectObject(a2, v16);
    DeleteObject(v15);
  }
  v19 = CreatePen(0, 1, color);
  v20 = v19;
  if ( !v19 )
    return 0;
  v21 = SelectObject(a2, v19);
  v22 = a3->top;
  v23 = v21;
  for ( j = a3->left; j < v9; j += 4 )
  {
    MoveToEx(a2, j, v10, 0);
    LineTo(a2, v9, v22);
    v22 += 4;
  }
  SelectObject(a2, v23);
  DeleteObject(v20);
  v25 = CreatePen(0, 1, SysColor);
  v26 = v25;
  if ( !v25 )
    return 0;
  v27 = SelectObject(a2, v25);
  v28 = a3->left + 1;
  v29 = a3->top + 1;
  while ( v28 < v9 )
  {
    MoveToEx(a2, v28, v10, 0);
    LineTo(a2, v9, v29);
    MoveToEx(a2, v28 + 1, v10, 0);
    LineTo(a2, v9, v29 + 1);
    v28 += 4;
    v29 += 4;
  }
  SelectObject(a2, v27);
  DeleteObject(v26);
  return 1;
}

```

## disassembly

```asm
0x1803f473c  mov     [rsp+arg_8], rbx
0x1803f4741  mov     qword ptr [rsp+arg_0], rcx
0x1803f4746  push    rbp
0x1803f4747  push    rsi
0x1803f4748  push    rdi
0x1803f4749  push    r12
0x1803f474b  push    r13
0x1803f474d  push    r14
0x1803f474f  push    r15
0x1803f4751  sub     rsp, 30h
0x1803f4755  mov     ecx, [r8]
0x1803f4758  mov     r15d, 0Fh
0x1803f475e  mov     r11d, [r8+4]
0x1803f4762  mov     ebx, r9d
0x1803f4765  mov     r10d, [r8+0Ch]
0x1803f4769  mov     rdi, r8
0x1803f476c  mov     eax, [r8+8]
0x1803f4770  sub     r10d, r11d
0x1803f4773  sub     eax, ecx
0x1803f4775  mov     rsi, rdx
0x1803f4778  cmp     eax, r10d
0x1803f477b  cmovge  eax, r10d
0x1803f477f  lea     ebp, [rax+rcx]
0x1803f4782  mov     ecx, r15d; nIndex
0x1803f4785  lea     r12d, [rax+r11]
0x1803f4789  call    cs:__imp_GetSysColorBrush
0x1803f478f  lea     ecx, [r15+5]; nIndex
0x1803f4793  mov     r14, rax
0x1803f4796  call    cs:__imp_GetSysColor
0x1803f479c  lea     ecx, [r15+1]; nIndex
0x1803f47a0  mov     [rsp+68h+color], eax
0x1803f47a7  call    cs:__imp_GetSysColor
0x1803f47ad  mov     [rsp+68h+arg_0], eax
0x1803f47b1  test    ebx, ebx
0x1803f47b3  jz      short loc_1803F47FA
0x1803f47b5  mov     rdx, r14; h
0x1803f47b8  mov     rcx, rsi; hdc
0x1803f47bb  call    cs:__imp_SelectObject
0x1803f47c1  mov     ecx, [rdi+0Ch]
0x1803f47c4  mov     rbx, rax
0x1803f47c7  mov     r8d, [rdi+4]; y
0x1803f47cb  sub     ecx, r8d
0x1803f47ce  mov     r9d, [rdi+8]
0x1803f47d2  sub     r9d, [rdi]; w
0x1803f47d5  mov     edx, [rdi]; x
0x1803f47d7  mov     [rsp+68h+rop], 0F00021h; rop
0x1803f47df  mov     [rsp+68h+h], ecx; h
0x1803f47e3  mov     rcx, rsi; hdc
0x1803f47e6  call    cs:__imp_PatBlt
0x1803f47ec  mov     rdx, rbx; h
0x1803f47ef  mov     rcx, rsi; hdc
0x1803f47f2  call    cs:__imp_SelectObject
0x1803f47f8  jmp     short loc_1803F4879
0x1803f47fa  mov     ecx, r15d; nIndex
0x1803f47fd  call    cs:__imp_GetSysColor
0x1803f4803  mov     edx, 1; cWidth
0x1803f4808  xor     ecx, ecx; iStyle
0x1803f480a  mov     r8d, eax; color
0x1803f480d  call    cs:__imp_CreatePen
0x1803f4813  mov     r15, rax
0x1803f4816  test    rax, rax
0x1803f4819  jz      loc_1803F4988
0x1803f481f  mov     rdx, rax; h
0x1803f4822  mov     rcx, rsi; hdc
0x1803f4825  call    cs:__imp_SelectObject
0x1803f482b  mov     r14d, [rdi+4]
0x1803f482f  mov     r13, rax
0x1803f4832  mov     ebx, [rdi]
0x1803f4834  add     r14d, 3
0x1803f4838  add     ebx, 3
0x1803f483b  jmp     short loc_1803F4860
0x1803f483d  xor     r9d, r9d; lppt
0x1803f4840  mov     r8d, r12d; y
0x1803f4843  mov     edx, ebx; x
0x1803f4845  call    cs:__imp_MoveToEx
0x1803f484b  mov     r8d, r14d; y
0x1803f484e  mov     edx, ebp; x
0x1803f4850  mov     rcx, rsi; hdc
0x1803f4853  call    cs:__imp_LineTo
0x1803f4859  add     ebx, 4
0x1803f485c  add     r14d, 4
0x1803f4860  mov     rcx, rsi; hdc
0x1803f4863  cmp     ebx, ebp
0x1803f4865  jl      short loc_1803F483D
0x1803f4867  mov     rdx, r13; h
0x1803f486a  call    cs:__imp_SelectObject
0x1803f4870  mov     rcx, r15; ho
0x1803f4873  call    cs:__imp_DeleteObject
0x1803f4879  mov     r8d, [rsp+68h+color]; color
0x1803f4881  mov     edx, 1; cWidth
0x1803f4886  xor     ecx, ecx; iStyle
0x1803f4888  call    cs:__imp_CreatePen
0x1803f488e  mov     r14, rax
0x1803f4891  test    rax, rax
0x1803f4894  jz      loc_1803F4988
0x1803f489a  mov     rdx, rax; h
0x1803f489d  mov     rcx, rsi; hdc
0x1803f48a0  call    cs:__imp_SelectObject
0x1803f48a6  mov     r15d, [rdi+4]
0x1803f48aa  mov     r13, rax
0x1803f48ad  mov     ebx, [rdi]
0x1803f48af  jmp     short loc_1803F48D4
0x1803f48b1  xor     r9d, r9d; lppt
0x1803f48b4  mov     r8d, r12d; y
0x1803f48b7  mov     edx, ebx; x
0x1803f48b9  call    cs:__imp_MoveToEx
0x1803f48bf  mov     r8d, r15d; y
0x1803f48c2  mov     edx, ebp; x
0x1803f48c4  mov     rcx, rsi; hdc
0x1803f48c7  call    cs:__imp_LineTo
0x1803f48cd  add     ebx, 4
0x1803f48d0  add     r15d, 4
0x1803f48d4  mov     rcx, rsi; hdc
0x1803f48d7  cmp     ebx, ebp
0x1803f48d9  jl      short loc_1803F48B1
0x1803f48db  mov     rdx, r13; h
0x1803f48de  call    cs:__imp_SelectObject
0x1803f48e4  mov     rcx, r14; ho
0x1803f48e7  call    cs:__imp_DeleteObject
0x1803f48ed  mov     r8d, [rsp+68h+arg_0]; color
0x1803f48f2  mov     r13d, 1
0x1803f48f8  mov     edx, r13d; cWidth
0x1803f48fb  xor     ecx, ecx; iStyle
0x1803f48fd  call    cs:__imp_CreatePen
0x1803f4903  mov     r14, rax
0x1803f4906  test    rax, rax
0x1803f4909  jz      short loc_1803F4988
0x1803f490b  mov     rdx, rax; h
0x1803f490e  mov     rcx, rsi; hdc
0x1803f4911  call    cs:__imp_SelectObject
0x1803f4917  mov     ebx, [rdi]
0x1803f4919  mov     r15, rax
0x1803f491c  mov     edi, [rdi+4]
0x1803f491f  add     ebx, r13d
0x1803f4922  add     edi, r13d
0x1803f4925  jmp     short loc_1803F496A
0x1803f4927  xor     r9d, r9d; lppt
0x1803f492a  mov     r8d, r12d; y
0x1803f492d  mov     edx, ebx; x
0x1803f492f  call    cs:__imp_MoveToEx
0x1803f4935  mov     r8d, edi; y
0x1803f4938  mov     edx, ebp; x
0x1803f493a  mov     rcx, rsi; hdc
0x1803f493d  call    cs:__imp_LineTo
0x1803f4943  xor     r9d, r9d; lppt
0x1803f4946  lea     edx, [rbx+1]; x
0x1803f4949  mov     r8d, r12d; y
0x1803f494c  mov     rcx, rsi; hdc
0x1803f494f  call    cs:__imp_MoveToEx
0x1803f4955  lea     r8d, [rdi+1]; y
0x1803f4959  mov     edx, ebp; x
0x1803f495b  mov     rcx, rsi; hdc
0x1803f495e  call    cs:__imp_LineTo
0x1803f4964  add     ebx, 4
0x1803f4967  add     edi, 4
0x1803f496a  mov     rcx, rsi; hdc
0x1803f496d  cmp     ebx, ebp
0x1803f496f  jl      short loc_1803F4927
0x1803f4971  mov     rdx, r15; h
0x1803f4974  call    cs:__imp_SelectObject
0x1803f497a  mov     rcx, r14; ho
0x1803f497d  call    cs:__imp_DeleteObject
0x1803f4983  mov     eax, r13d
0x1803f4986  jmp     short loc_1803F498A
0x1803f4988  xor     eax, eax
0x1803f498a  mov     rbx, [rsp+68h+arg_8]
0x1803f498f  add     rsp, 30h
0x1803f4993  pop     r15
0x1803f4995  pop     r14
0x1803f4997  pop     r13
0x1803f4999  pop     r12
0x1803f499b  pop     rdi
0x1803f499c  pop     rsi
0x1803f499d  pop     rbp
0x1803f499e  retn
```
